# Tests

Colony validation test harness.

## Test Harness

The `hive-test-harness.jsx` is a React artifact that runs inside Claude.ai. It embeds all 30 colony files and sends test prompts to Claude via the Anthropic API, grading outputs against a tier-appropriate rubric.

### Features
- **Coverage tests** — 30 pre-written tests across SIMPLE, MEDIUM, COMPLEX, CHAIN, SPAWN + 5 Messenger-specific
- **Adaptive tests** — auto-generated targeting weakest areas from prior results
- **Ablation tests** — remove individual caste files to measure their impact
- **Stress tests** — 10 adversarial and edge case inputs (injection attacks, empty input, impossible requests, circular dependencies)
- **Saturation curve** — tracks new failure modes per wave (stop when flat)
- **Persistent results** — survive page reloads via storage API
- **AbortController** — stop button kills in-flight API calls immediately
- **Copy results** — textarea fallback for exporting wave data

### Smart Grading
- Detects **clarification responses** (Messenger/Scout surfacing ambiguity) and grades with clarification-specific checks
- Detects **tier escalation** (colony overriding assigned tier) and grades against the chosen tier
- Excludes API errors from pass/fail metrics
- Tier-appropriate check counts (SIMPLE: 6 checks, SPAWN: 16 checks)

### Modes
| Mode | What it does |
|---|---|
| **Coverage** | 30 pre-written tests across all tiers |
| **Adaptive** | 10 auto-generated tests targeting weakest areas |
| **Ablation** | Remove a caste file, re-run tests, measure impact |
| **Stress** | 10 adversarial inputs designed to break the colony |

### Running
1. Open the `.jsx` artifact in Claude.ai
2. Select mode (Coverage is default)
3. Click **▶ Run Next Wave**
4. Wave 1 runs coverage (30 tests, ~$3)
5. Switch to Stress or Adaptive for subsequent waves
6. Keep running until saturation curve flatlines

### Results (v3.1.0 validation)
- 100+ tests across coverage, adaptive, ablation, and stress waves
- **95% average score** on coverage (30 tests)
- **91% average score** on stress (10 adversarial tests)
- Zero new failure modes for consecutive waves (saturation confirmed)
- Ablation: Guardian removal had zero score impact → redesigned as conditional second-pass reviewer
