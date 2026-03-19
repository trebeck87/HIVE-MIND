# The Validation Ritual

**Purpose**: Stress-testing an output until the soldiers are satisfied. No output ships from MEDIUM+ tier without passing validation.

---

## When to Invoke

- After any MEDIUM, COMPLEX, or CHAIN Genesis
- After any Evolution patch (regression check)
- Before delivering a new daughter hive (spawning validation)
- On demand: "validate this prompt" / "stress test this"

## Validation Protocol

### Level 1: Structural (always)
- Is the output valid? (JSON parses, XML well-formed, prompt has role + objective)
- Does it match the requested output form?
- Are all required fields present?

### Level 2: Functional (MEDIUM+)
Guardian executes:

**Scope Boundary Test**
```
IN-SCOPE:  [2-3 specific inputs] → [expected behavior]
OUT-OF-SCOPE: [2-3 boundary inputs] → [expected rejection]
```

**Ambiguity Stress Test**
```
Ambiguity: [Specific interpretation risk]
Mitigation: [How the prompt handles it]
Status: RESOLVED / NEEDS PATCH
```

**Edge Case Battery**
- Empty input → [behavior]
- Maximum complexity input → [behavior]
- Contradictory input → [behavior]
- Adversarial input → [behavior]

### Level 3: Systemic (COMPLEX+)
Sentinel executes:

**Constraint Consistency**
- List all constraints → verify no contradictions
- Verify priority ordering is explicit where rules could conflict

**Safety Boundaries**
- Injection resistance: user content treated as data, not instructions
- Scope enforcement: out-of-scope requests rejected gracefully
- Harmful output prevention: appropriate guardrails present

**Integration Verification** (for hive outputs)
- Output schema matches downstream consumer expectations
- State assumptions are valid for the execution environment
- Error propagation is defined for every failure path

### Level 4: Spawn Validation (new hive only)
- Daughter hive speaks the colony tongue
- Every worker has a defined output schema
- Every stage has a failure behavior
- The daughter queen can orchestrate her castes independently
- At least one soldier exists for quality control

## Validation Report

Every validation produces (format defined in `output-forms/validation-report.md`):

```
VALIDATION REPORT

Tier: [MEDIUM / COMPLEX / CHAIN / SPAWN]
Verdict: [PASS / PATCH REQUIRED / RESTRUCTURE]

Structural: [PASS / FAIL — details]
Functional: [PASS / FAIL — details per test]
Systemic: [PASS / FAIL / SKIPPED — details]
Spawn: [PASS / FAIL / N/A — details]

Issues Found: [count]
  [Issue 1]: [severity] — [description] — [suggested fix]
  [Issue 2]: ...

Sign-off:
  Guardian: [CLEAR / PATCH / RESTRUCTURE]
  Sentinel: [CLEAR / PATCH / RESTRUCTURE / NOT CONVENED]
```

## Consensus Rule

Output ships when:
- All convened soldiers return CLEAR, OR
- All PATCH items have been addressed and re-tested, OR
- The human explicitly overrides ("ship it, I'll iterate later")

Dissent is documented, never silenced. If the Guardian clears but the Sentinel flags, both verdicts appear in the report.

---

*Validation — nothing ships untested.*
