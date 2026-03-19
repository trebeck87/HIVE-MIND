# Output Form: Hive Blueprint

The shape of a newly spawned daughter hive. Used by `queen/spawning.md` during the Spawning Ritual.

---

## File Structure

```
{hive-name}/
├── SKILL.md                    ← Daughter Queen
├── workers/
│   ├── {worker-1}.md           ← Core task workers
│   └── {worker-2}.md              (1 per distinct task)
├── soldiers/
│   └── {soldier-1}.md          ← Quality/safety (minimum 1)
├── drones/                     ← Only if data pipeline needed
│   ├── {collector}.md
│   └── {processor}.md
└── memory/
    └── {domain-knowledge}.md   ← Domain-specific patterns
```

## Daughter Queen (SKILL.md) Template

```markdown
---
name: {hive-name}
description: "[What this hive does]. Use this skill when [trigger conditions].
  Also trigger when [adjacent conditions]. If the user [broader recognition
  patterns], this skill applies."
version: 1.0
author: The Colony
---

# {HIVE NAME}

## Domain
[What domain this hive operates in. 2-3 sentences.]

## Orchestration
[How the daughter queen coordinates her castes.
 If chain: stage flow diagram.
 If parallel: which workers can run concurrently.
 If conditional: decision tree for which worker to invoke.]

## Caste Registry

| Caste | File | When to Read |
|---|---|---|
| {Worker 1} | workers/{name}.md | [trigger] |
| {Worker 2} | workers/{name}.md | [trigger] |
| {Soldier 1} | soldiers/{name}.md | [trigger] |

## Colony Inheritance
This hive speaks the colony tongue (queen/language.md).
Validation follows colony protocol (rituals/validation.md).
Evolution follows colony protocol (rituals/evolution.md).
```

## Worker File Template

```markdown
# {Worker Name}

**Role**: [What this worker does — 1-2 sentences]
**Input**: [What it receives]
**Output**: [What it produces — with schema]

## System Prompt
```
[Full system prompt following output-forms/system-prompt.md]
```

## User Message Template
```
[Template with {PLACEHOLDER} variables]
```

## Output Schema
```json
[Exact output shape]
```

## Failure Behavior
[What happens when this worker fails]
```

## Soldier File Template

```markdown
# {Soldier Name}

**Role**: [What this soldier checks — 1-2 sentences]
**Monitors**: [What signals/conditions it watches]

## Check Protocol
[Step-by-step validation this soldier performs]

## Alert Thresholds
| Condition | Severity | Action |
|---|---|---|
| [condition] | [critical/warning/info] | [response] |

## Override Rules
[When the soldier's alerts can be overridden and by whom]
```

## Viability Checklist

Before delivery, verify the daughter hive:
- [ ] SKILL.md can orchestrate all workers independently
- [ ] Every worker has a system prompt, user template, output schema, and failure behavior
- [ ] At least one soldier exists for quality control
- [ ] Colony tongue is spoken (XML tags, JSON protocol, validation format)
- [ ] Registered in queen/lineage.md

---

*Output Form: Hive Blueprint — the shape of a new colony member.*
