# Output Form: Validation Report

The shape of validation evidence produced by the colony's soldiers.

---

## Structure

```
VALIDATION REPORT
═════════════════

Target: [What was validated — prompt name, chain stage, hive name]
Tier: [SIMPLE / MEDIUM / COMPLEX / CHAIN / SPAWN]
Castes Convened: [Which soldiers participated]

────────────────────────────────────────

STRUCTURAL CHECK
  Status: [PASS / FAIL]
  - Output valid: [Y/N — JSON parses, XML well-formed, etc.]
  - Output form matches: [Y/N — matches requested shape]
  - Required fields present: [Y/N — all mandatory elements exist]

────────────────────────────────────────

COMPLEXITY JUSTIFICATION
  Token count: [~N tokens]
  Calibrated to: [SIMPLE/MEDIUM/COMPLEX/CHAIN]
  Rationale: [Why this tier — what features of the request justify it]

────────────────────────────────────────

SCOPE BOUNDARY TEST (Guardian)
  IN-SCOPE:
    Input: [specific test input]
    Expected: [expected behavior]
    Result: [PASS / FAIL — what happened]

  OUT-OF-SCOPE:
    Input: [boundary test input]
    Expected: [rejection or clarification]
    Result: [PASS / FAIL — what happened]

────────────────────────────────────────

AMBIGUITY STRESS TEST (Guardian)
  Ambiguity 1:
    Risk: [specific interpretation that could go wrong]
    Mitigation: [how the prompt handles it]
    Status: [RESOLVED / NEEDS PATCH — with fix]

  Ambiguity 2: ...

────────────────────────────────────────

EDGE CASE BATTERY (Guardian)
  Empty input:      [behavior] → [PASS/FAIL]
  Extreme input:    [behavior] → [PASS/FAIL]
  Contradictory:    [behavior] → [PASS/FAIL]
  Adversarial:      [behavior] → [PASS/FAIL]
  Degraded:         [behavior] → [PASS/FAIL]

────────────────────────────────────────

FAILURE MODE ANALYSIS (Guardian)
  Primary:   [Most likely failure]
  Prevented: [Specific constraint/example that prevents it]

  Secondary: [Second most likely]
  Prevented: [Specific mitigation]

────────────────────────────────────────

TOKEN EFFICIENCY AUDIT
  Removed: [What was eliminated as redundant]
  Retained: [What justified its token cost]
  Compression possible: [Y/N — where, if yes]

────────────────────────────────────────

SYSTEMIC CHECK (Sentinel) — COMPLEX+ only
  Constraint consistency: [PASS / conflicts found]
  Safety boundaries: [PASS / gaps found]
  Integration points: [PASS / mismatches found]
  Regression risk: [NONE / LOW / HIGH — details]

────────────────────────────────────────

SPAWN VIABILITY (Sentinel) — SPAWN only
  Colony tongue compliance: [PASS / FAIL]
  Worker completeness: [PASS / FAIL — missing fields]
  Soldier presence: [PASS / FAIL]
  Queen autonomy: [PASS / FAIL — can orchestrate independently]
  Lineage registered: [PASS / FAIL]

════════════════════════════════════════

VERDICT: [PASS / PATCH REQUIRED / RESTRUCTURE]

  Guardian: [CLEAR / PATCH / RESTRUCTURE]
  Sentinel: [CLEAR / PATCH / RESTRUCTURE / NOT CONVENED]

Issues requiring action:
  1. [Severity]: [Description] → [Suggested fix]
  2. ...

Dissent: [Any disagreement between soldiers — documented, not silenced]
```

## When to Produce

| Tier | Validation Report? |
|---|---|
| SIMPLE | No — structural check only (inline, no formal report) |
| MEDIUM | Yes — Guardian sections |
| COMPLEX | Yes — Guardian + Sentinel sections |
| CHAIN | Yes — per-stage + systemic |
| SPAWN | Yes — full report including viability |

## Report Delivery

The validation report accompanies the output, not replaces it. Deliver:
1. The output itself (prompt, chain, hive)
2. The validation report
3. Scope definition (in/out/boundary)
4. Evolution guidance (how to iterate)

---

*Output Form: Validation Report — the shape of proof.*
