# The Colony Tongue

Every hive, every caste, every output speaks this language. Non-negotiable.

---

## XML Tag Semantics

Claude parses XML tags as semantic boundaries. The colony uses them as load-bearing structure, not decoration.

**Instruction/Data Separation** — Always isolate human-provided content from instructions:
```xml
<instructions>What Claude should do</instructions>
<user_input>{{variable content}}</user_input>
```

**Semantic Grouping** — Use tags to create parseable regions in output:
```xml
<core_objective>The single mission statement</core_objective>
<constraints>Hard rules, not soft guidance</constraints>
<edge_case_handling>Conditional logic for boundary conditions</edge_case_handling>
```

**Nesting for Hierarchy** — Nest when parent-child relationships matter:
```xml
<evaluation>
  <criteria>What to evaluate against</criteria>
  <score>Numeric assessment</score>
  <reasoning>Why this score</reasoning>
</evaluation>
```

**Anti-Pattern**: XML for decoration. If markdown headers suffice, use those. Reserve XML for parsing reliability and instruction/data separation.

---

## System vs. User Prompt Placement

| Content | Placement | Rule |
|---|---|---|
| Role identity | System | Same every call → system |
| Output format | System | Same every call → system |
| Safety constraints | System | Non-negotiable → system |
| Variable input | User | Changes per call → user |
| Task-specific instructions | User | May vary → user |
| Examples | Either | Universal → system; task-specific → user |

---

## JSON Output Protocol

When a hive stage requires JSON output:

1. **Instruction**: "Respond ONLY with valid JSON. No markdown, no backticks, no preamble."
2. **Schema**: Show the exact structure with type annotations
3. **Prefill**: Use assistant prefill `{` (or `[{` for arrays) to force compliance
4. **Client fallback**: Always strip backtick fences: `text.replace(/```json|```/g, "").trim()`

---

## Validation Evidence Format

Every generated prompt produces validation evidence in this structure:

```
Complexity Justification:
  [X] tokens | Calibrated to [SIMPLE/MEDIUM/COMPLEX/CHAIN] because [reasoning]

Scope Boundary Test:
  IN-SCOPE:  [specific input] → [expected behavior]
  OUT-OF-SCOPE: [boundary input] → [expected rejection]

Ambiguity Stress Test:
  Potential confusion: [specific interpretation risk]
  Mitigation: [specific prompt addition that resolves it]

Primary Failure Mode: [Most likely way this breaks]
  Prevented by: [specific constraint or example in the prompt]

Token Efficiency Audit:
  Removed: [eliminated redundancy]
  Retained: [justified complexity]
```

---

## Iteration Log Format

When a prompt is patched:

```
ITERATION LOG

Test Input: [The input that caused failure]
Expected: [What should have happened]
Actual: [What Claude produced]

Root Cause:
  [ ] Ambiguous instruction
  [ ] Missing constraint
  [ ] Conflicting rules
  [ ] Insufficient example
  [ ] Wrong complexity tier
  [ ] Format drift

Patch:
  Location: [Section modified]
  Change: [Specific modification]
  Rationale: [Why this fixes root cause]

Re-Test: [Pass/Fail with evidence]
```

---

## Token Efficiency Principles

These apply to every output from every hive:

- **Front-load** critical instructions (Claude weights early content heavily)
- **Examples over descriptions** (1 good example > 3 paragraphs of explanation)
- **No hedge language** ("try to" → just state the requirement)
- **Merge overlapping constraints** (3 rules saying the same thing → 1 precise rule)
- **Minimum viable prompt** — start simple, add complexity only when simpler versions fail specific test cases

---

*The Colony Tongue — spoken by all hives, all castes, all outputs.*
