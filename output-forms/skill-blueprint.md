# Output Form: Skill Blueprint

*Use when the Queen input is classified as Wax — a request to build an agent skill (SKILL.md).*

This is not the same as a system prompt. A SKILL.md is a different artifact with different constraints, different placement rules, and a different primary success metric. The system prompt success metric is output quality. The skill blueprint success metric is reliable triggering.

---

## Description First. Always.

Before the Builder constructs anything else, the description is written.

The description field is not documentation. It is the trigger condition the agent uses to decide whether to activate this skill at all. A skill that never triggers is worse than no skill — it consumes Level 1 context (~100 tokens) on every session startup while providing zero value.

**Pattern**:
```
description: "[Capability statement in plain language]. Use when user asks to 
"[trigger phrase 1]", "[trigger phrase 2]", "[trigger phrase 3]", or "[trigger phrase 4]". 
[Optional: what the skill requires or produces.]"
```

**Requirements**:
- Encode both WHAT (capability) and WHEN (specific trigger phrases)
- 3-5 trigger phrases minimum — mirror real human phrasing, not formal descriptions
- Max 1024 characters total
- No XML angle brackets (`<` or `>`) — these inject instructions into the system prompt
- Write trigger phrases in the first person as users would actually say them ("help me", "write me", "I need")

**Anti-pattern (A18)**: `description: Helps with documents.` — describes what, not when. Will not trigger.

---

## Level Architecture

Every skill has three levels. Build them in order.

### Level 1 — Frontmatter (~100 tokens, always loaded)

```yaml
---
name: skill-name-here
description: "[Capability statement]. Use when user asks to '[phrase 1]', '[phrase 2]', 
or '[phrase 3]'. [What it produces/requires if relevant.]"
version: 1.0.0
---
```

Optional frontmatter fields:
- `metadata.mcp-server: [server-name]` — if skill requires MCP server connection
- `allowed-tools: Read, Grep, Glob` — restrict tools for read-only/observational skills (experimental, well-supported in Claude Code)

**Name conventions**: lowercase letters, numbers, hyphens only. Max 64 characters. No consecutive hyphens. No leading/trailing hyphens.

### Level 2 — Body (<500 lines, loaded when triggered)

The skill's instructions. What the agent does when activated.

**Design principle**: Level 2 should contain the minimum essential knowledge. Detailed reference material goes in Level 3. A skill body that exceeds 500 lines is a signal that Level 3 files are needed.

**Structure**:
```markdown
# Skill Name

## Overview
One paragraph. What this skill does. Who it serves. When to use it.

## Process
Step-by-step instructions. Reference Level 3 files for details:
- "For detailed review criteria, see [references/criteria.md](references/criteria.md)"

## Output Format
What the skill produces. Format specification. Example output if helpful.

## Quality Check
Verification steps before finishing.
```

### Level 3 — Referenced files (loaded on demand, effectively unlimited)

Files the agent reads only when needed. Scripts execute without being read into context.

```
skill-name/
├── SKILL.md
├── references/        ← Detailed docs, criteria, domain knowledge
│   ├── criteria.md
│   └── domain-guide.md
├── scripts/           ← Executable code (runs without loading into context)
│   └── validate.sh
└── assets/            ← Templates, examples, static files
    └── template.md
```

---

## Portability Tier

Establish before building. Determines which constructs are permissible.

| Tier | Scope | Constraints |
|---|---|---|
| **Personal** | `~/.claude/skills/` — one user, all projects | Full Claude Code feature set |
| **Project** | `.claude/skills/` — shared via git | Avoid user-specific paths, prefer relative references |
| **Distributed** | Published, cross-user, cross-platform | See cross-platform audit below |

**Distributed tier — cross-platform compatibility audit** (run before finalizing):
- Any `bash` or `Read/Write/Glob/Grep` tool calls? → Claude Code specific. Flag for Codex users.
- `allowed-tools` field present? → Experimental in the spec. Mark as Claude Code optimized.
- MCP server declaration in metadata? → Platform-specific. Include fallback behavior if MCP unavailable.
- Any hardcoded paths? → Must use relative paths or platform-appropriate conventions.
- Any outbound network calls in `scripts/`? → Security flag. Document explicitly in the skill's README.

---

## Complexity Templates

### Simple Skill — Single SKILL.md

Single-purpose. One workflow. No external dependencies. Fits in Level 2 alone.

```
skill-name/
└── SKILL.md    (frontmatter + body, under 200 lines)
```

**When**: The entire skill can be expressed clearly without detailed reference material. Instructions are self-contained.

### Complex Skill — With References

Multi-criteria or knowledge-intensive. The body stays lean by pushing detail to Level 3.

```
skill-name/
├── SKILL.md    (frontmatter + body, references Level 3 files by path)
└── references/
    ├── criteria.md      ← Detailed evaluation criteria
    └── domain-guide.md  ← Domain-specific knowledge
```

**Pattern**: Body says "For detailed criteria, see [references/criteria.md](references/criteria.md)." Agent reads the reference only when actively reviewing — not at skill activation.

### MCP Skill — With Server Integration

Requires an external MCP server. The skill provides workflow knowledge; the MCP server provides tool access.

```
skill-name/
├── SKILL.md    (metadata.mcp-server declared in frontmatter)
├── references/
│   ├── api-patterns.md    ← How to use the MCP tools correctly
│   └── error-handling.md  ← What to do when MCP calls fail
└── assets/
    └── prompt-template.md ← Standard prompt structures for this workflow
```

**Always**: Check MCP connection before starting. Define behavior when MCP is unavailable. Never assume the server is connected.

---

## Security Requirements

Before finalizing any distributed skill, the Sentinel runs this checklist:

- [ ] No outbound network calls in `scripts/` that aren't explicitly documented
- [ ] No instructions that prompt the agent to request secrets or credentials
- [ ] `allowed-tools` scope is the minimum required for the skill's function
- [ ] No instructions-within-instructions disguised as documentation (SKILL_INJECTION pattern)
- [ ] Description field contains no XML angle brackets
- [ ] External URL references in `references/` are to stable, trusted sources
- [ ] MCP server declaration (if present) specifies fallback behavior when unavailable

---

## Validation Checklist

Before shipping, run against `output-forms/skill-validation-report.md`:

- [ ] Description encodes both what and when
- [ ] Description contains 3+ specific trigger phrases in human-natural phrasing
- [ ] Body is under 500 lines
- [ ] Detailed content is in `references/`, not inline in the body
- [ ] Simulated trigger test: does the description activate for 5 differently-phrased versions of the intent?
- [ ] Explicit invocation test: does `/skill-name` work as expected?
- [ ] Portability tier declared and cross-platform audit run (if Distributed)
- [ ] Security checklist passed (if Distributed)
- [ ] Name follows conventions (lowercase, hyphens, max 64 chars)

---

## Registry Check (Forager HyperMode)

Before the Builder constructs from scratch, the Forager checks:

1. agentskills.io registry — does a skill for this use case exist?
2. AgentSkillsRepo — community skills for this domain?
3. Official repos (Anthropic skills, OpenAI skills) — reference implementations?

If a prior art skill exists: adopt and modify rather than rebuild. If none exists: proceed with original construction and consider contributing back.

---

*Skill Blueprint — description first, levels always, trigger or it doesn't exist.*
