# Output Form: Skill Validation Report

*Use when validating a SKILL.md artifact. Different criteria than `validation-report.md`, which tests prompt quality.*

A SKILL.md is not a prompt. Its primary success metric is **reliable triggering**, not output quality. A well-written skill that never activates is worse than a mediocre skill that activates consistently.

---

## Structure

```
SKILL VALIDATION REPORT
═══════════════════════

Target: [Skill name and path]
Portability Tier: [Personal / Project / Distributed]

────────────────────────────────────────

DESCRIPTION QUALITY
  Encodes WHAT (capability):     [PASS / FAIL — what's missing]
  Encodes WHEN (trigger phrases): [PASS / FAIL — count: N/3 minimum]
  Trigger phrases use human-natural phrasing: [PASS / FAIL]
  Under 1024 characters:         [PASS / FAIL — actual: N chars]
  No XML angle brackets:         [PASS / FAIL]

────────────────────────────────────────

SIMULATED TRIGGER TEST
  5 differently-phrased versions of the same intent:
  1. "[phrase]" → [TRIGGERED / MISSED]
  2. "[phrase]" → [TRIGGERED / MISSED]
  3. "[phrase]" → [TRIGGERED / MISSED]
  4. "[phrase]" → [TRIGGERED / MISSED]
  5. "[phrase]" → [TRIGGERED / MISSED]
  Trigger rate: [N/5]

  Explicit invocation test:
  /[skill-name] → [PASS / FAIL]

────────────────────────────────────────

BODY STRUCTURE
  Line count:               [N lines — PASS if ≤ 500, WARN if > 500]
  Level 3 separation:       [PASS — detailed content in references/ | 
                              FAIL — detailed content inline in body]
  Workflow/process clarity:  [PASS / FAIL]
  Output format defined:    [PASS / FAIL]

────────────────────────────────────────

LEVEL 3 FILES (if present)
  references/ contents:     [listed with purpose]
  scripts/ contents:        [listed — ALL scripts read in full]
  assets/ contents:         [listed with purpose]

────────────────────────────────────────

TOOL RESTRICTION (if allowed-tools declared)
  Declared tools: [list]
  Minimum required: [PASS — scope matches function | 
                      FAIL — over-permissioned]
  Experimental field noted: [Y/N — allowed-tools is experimental]

────────────────────────────────────────

CROSS-PLATFORM AUDIT (Distributed tier only)
  Claude-specific tool calls (bash, Read/Write/Glob/Grep):
    [FOUND — flagged for Codex users | NONE]
  MCP server declarations:
    [FOUND — platform-specific, fallback defined? | NONE]
  Hardcoded paths:
    [FOUND — must use relative paths | NONE]
  Experimental fields (allowed-tools):
    [FOUND — marked as Claude Code optimized | NONE]

────────────────────────────────────────

SECURITY AUDIT (Distributed tier only)
  See rituals/security.md § 7 — Skill Security
  - [ ] No outbound network calls in scripts/ undocumented
  - [ ] No credential/secret requests in instructions
  - [ ] allowed-tools is minimum required scope
  - [ ] No instructions-within-instructions (SKILL_INJECTION)
  - [ ] No XML angle brackets in description
  - [ ] External URLs in references/ are stable, trusted
  - [ ] MCP fallback behavior defined (if MCP declared)

────────────────────────────────────────

NAME CONVENTIONS
  Lowercase + hyphens only:  [PASS / FAIL]
  Under 64 characters:       [PASS / FAIL]
  No consecutive hyphens:    [PASS / FAIL]
  No leading/trailing hyphens: [PASS / FAIL]

════════════════════════════════════════

VERDICT: [PASS / PATCH REQUIRED / RESTRUCTURE]

Issues requiring action:
  1. [Severity]: [Description] → [Suggested fix]
  2. ...

Trigger reliability assessment:
  [HIGH — 5/5 trigger, clear phrases, human-natural |
   MEDIUM — 3-4/5 trigger, phrases could be more natural |
   LOW — <3/5 trigger, description needs rewrite]
```

## When to Produce

Every Wax output (skill construction) gets a skill validation report. This replaces `validation-report.md` for skill artifacts — do not use both.

## Key Difference from Prompt Validation

| Prompt Validation | Skill Validation |
|---|---|
| Scope boundary test | **Simulated trigger test** |
| Edge case battery | **Cross-platform audit** |
| Failure mode analysis | **Security audit for distribution** |
| Token efficiency audit | **Level 3 separation check** |
| Guardian adversarial review | **Description quality check** |

The prompt validation asks: "Is this output good?" The skill validation asks: "Will this skill activate, and is it safe to distribute?"

---

*Output Form: Skill Validation Report — trigger or it doesn't exist.*
