# The Genesis Ritual

**Purpose**: Creating something from nothing. Used when the hive receives a request to build a new prompt, chain, tool, or hive.

---

## When to Invoke

- New prompt request (any tier)
- New prompt chain / pipeline
- New hive (queen egg / royal jelly)
- Any "build me..." / "create..." / "write a prompt for..." input

## Ritual Flow

```
GENESIS

Phase 1: RECONNAISSANCE (Scout leads)
  Scout maps the terrain
  → Domain, true goal, ambiguity, complexity tier
  → If ambiguity found: surface to human, await resolution
  → Output: Terrain Map

Phase 2: FORAGING (Forager gathers)
  [Skip for SIMPLE tier]
  Forager searches colony memory
  → Patterns, anti-patterns, reference examples
  → Sibling hive knowledge
  → Output: Foraged Resources

Phase 3: CONSTRUCTION (Builder builds)
  Builder reads:
  → Scout's terrain map
  → Forager's resources (if gathered)
  → Appropriate output form
  → Colony language (always)
  Builder constructs the output

Phase 4: STATE DESIGN (Nurse designs)
  [COMPLEX and CHAIN only]
  Nurse defines:
  → State persistence between stages
  → Handoff schemas
  → Context management

Phase 5: ADVERSARIAL REVIEW (Guardian — separate pass)
  [MEDIUM and above]
  Guardian receives the Builder's complete output in a SEPARATE API call.
  Guardian is NOT loaded alongside the Builder — reviews output fresh.
  → Input: original request + builder output
  → Output: JSON verdict with findings and fixes
  Guardian verdict: CLEAR / PATCH / RESTRUCTURE
  If PATCH: return findings to Builder, rebuild, re-review.

Phase 6: SYSTEMIC CHECK (Sentinel watches)
  [COMPLEX and above]
  Sentinel verifies:
  → No contradictions between constraints
  → Safety boundaries intact
  → Integration points valid
  → No regressions against existing patterns

Phase 7: DELIVERY
  Assemble final output with validation evidence
  → Use output form schema from output-forms/
  → Include validation report from soldiers
```

## Tier-Specific Genesis

### SIMPLE Genesis (lightweight)
```
Scout (quick assessment) → Builder → Deliver
No Forager. No soldiers. No validation evidence.
Fast, clean, appropriate for simple requests.
```

### MEDIUM Genesis (standard)
```
Scout → Builder → [DELIVER DRAFT] → Guardian (2nd pass) → Deliver final
Add Forager if domain has known patterns.
Guardian reviews Builder output in separate call.
```

### COMPLEX Genesis (full)
```
Scout → Forager → Builder + Nurse → [DELIVER DRAFT] →
Guardian (2nd pass) → Sentinel → Deliver final
All workers convened for construction. Soldiers review output separately.
```

### CHAIN Genesis (full + orchestration)
```
Scout → Forager → Builder (per stage) + Nurse (state design) →
[DELIVER DRAFT] → Guardian (reviews each stage) →
Sentinel (systemic check) → Synthesis ritual → Deliver final
```

## Genesis Anti-Patterns

- ❌ Building before scouting (the #1 failure — constructing the wrong thing)
- ❌ Full ceremony for simple requests (SIMPLE tier needs Scout + Builder, that's it)
- ❌ Skipping adversarial review for MEDIUM+ (the Guardian catches what you miss)
- ❌ Delivering without validation evidence for MEDIUM+ (evidence proves the output works)

---

*Genesis — from nothing, something. From something, intelligence.*
