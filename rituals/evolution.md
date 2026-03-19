# The Evolution Ritual

**Purpose**: Improving what exists. Used when a prompt fails, performance degrades, or a human requests optimization.

---

## When to Invoke

- A prompt produced wrong output
- User says "make this better" / "optimize this" / "this isn't working"
- Validation found issues (Guardian returned PATCH)
- Self-improvement (the Queen evolving herself)

## Ritual Flow

```
EVOLUTION

Phase 1: DIAGNOSIS (Guardian leads)
  Guardian examines the failure:
  → What input caused it?
  → What was expected vs. actual?
  → Root cause analysis (checklist below)

Phase 2: PATTERN CHECK (Forager gathers)
  Forager checks colony memory:
  → Is this a known anti-pattern?
  → Has a sibling hive solved this before?
  → What worked last time this type of failure occurred?

Phase 3: PATCH DESIGN (Builder constructs)
  Builder designs the fix:
  → Location: which section of the prompt
  → Change: specific addition/modification/removal
  → Rationale: why this fixes root cause without side effects

Phase 4: REGRESSION CHECK (Sentinel watches)
  Sentinel runs 3-5 diverse inputs:
  → Does the patch fix the target case?
  → Does it break any existing cases?
  → If it fixes one but breaks another → RESTRUCTURE, not more rules

Phase 5: MEMORY UPDATE (Nurse records)
  If the fix reveals a new pattern or anti-pattern:
  → Update memory/patterns.md or memory/antipatterns.md
  → The colony learns from this evolution
```

## Root Cause Checklist

When diagnosing a failure, the Guardian classifies:

```
[ ] Ambiguous instruction — Claude interpreted [X] as [Y]
[ ] Missing constraint — Nothing prevented [undesired behavior]
[ ] Conflicting rules — [Rule A] contradicts [Rule B]
[ ] Insufficient example — No demonstration of this case
[ ] Wrong complexity tier — Prompt is over/under-engineered
[ ] Format drift — Output structure degraded
[ ] Context starvation — Missing information that was needed
[ ] Edge case gap — Boundary condition not handled
```

## Iteration Log Format

Every evolution produces:

```
ITERATION LOG

Test Input: [What triggered the failure]
Expected: [What should have happened]
Actual: [What Claude produced]

Root Cause: [From checklist above]

Patch:
  Location: [Section modified]
  Change: [Specific modification]
  Rationale: [Why this fixes root cause]

Re-Test: [Pass/Fail with evidence]
Regression: [Did it break anything else?]
Memory Update: [New pattern/anti-pattern recorded? Y/N]
```

## Evolution Anti-Patterns

- ❌ Patching symptoms instead of root causes (the failure will recur in a different form)
- ❌ Adding rules without removing contradicted ones (prompt bloat)
- ❌ Skipping regression check ("it fixes the bug, ship it" — then it breaks two other things)
- ❌ Not recording the lesson (if the colony doesn't learn, it will make the same mistake again)

## Self-Evolution

When the Queen evolves herself (nectar input):
- All castes convene with the Queen's own files as subject
- The Guardian attacks the Queen's prompts, the Scout maps gaps
- The Builder patches, the Sentinel checks for regression
- The Queen that emerges has been stress-tested by her own soldiers

---

*Evolution — the colony learns from every failure.*
