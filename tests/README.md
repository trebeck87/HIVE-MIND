# Tests

Colony validation test harness.

## Test Harness

The `hive-test-harness.jsx` is a React artifact that runs inside Claude.ai. It embeds all colony files and sends test prompts to Claude via the Anthropic API, grading outputs against a tier-appropriate rubric.

### Features
- **Coverage tests** — 25 pre-written tests across SIMPLE, MEDIUM, COMPLEX, CHAIN, SPAWN
- **Adaptive tests** — auto-generated targeting weakest areas from prior results
- **Ablation tests** — remove individual caste files to measure their impact
- **Stress tests** — adversarial and edge case inputs
- **Saturation curve** — tracks new failure modes per wave (stop when flat)
- **Persistent results** — survive page reloads via storage API

### Smart Grading
- Detects **clarification responses** (Scout surfacing ambiguity) and grades appropriately
- Detects **tier escalation** (colony overriding assigned tier) and grades against the chosen tier
- Excludes API errors from pass/fail metrics
- Tier-appropriate check counts (SIMPLE: 6 checks, SPAWN: 16 checks)

### Running
1. Open the `.jsx` artifact in Claude.ai
2. Click **▶ Run Next Wave**
3. Wave 1 runs coverage (25 tests, ~$2)
4. Subsequent waves auto-adapt to target weaknesses
5. Keep running until saturation curve flatlines

### Results (v3.0 validation)
- 65 tests across 5 waves
- 95% average score
- Zero new failure modes for 2 consecutive waves
- Ablation: Guardian removal had zero score impact → redesigned as second-pass reviewer
