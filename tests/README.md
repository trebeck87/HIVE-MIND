# Tests

Colony validation test harness.

## Test Harness

The `hive-test-harness.jsx` is a React artifact that runs inside Claude.ai. It embeds all 30 colony files and sends test prompts to Claude via the Anthropic API, grading outputs with both LLM quality scoring and regex pattern checks.

### Features
- **Model selector** — Sonnet 4 / Opus 4 / Haiku 3.5 with per-model pricing and tracking
- **LLM quality scoring** — second-pass 1-10 grading with reasoning, strengths, weaknesses. Toggle ON/OFF.
- **Clarification subtypes** — MEH (6 checks), ALMOST (6), BENEATH (5), SCOUT (6) with distinct criteria
- **Coverage tests** — 30 pre-written tests across SIMPLE, MEDIUM, COMPLEX, CHAIN, SPAWN + Messenger
- **Adaptive tests** — auto-generated targeting weakest areas from prior results
- **Ablation tests** — remove individual caste files to measure their impact
- **Stress tests** — 10 adversarial and edge case inputs
- **Regression mode** — reruns coverage bank, compares against baseline with per-result deltas (±%)
- **Saturation curve** — tracks new failure modes per wave (stop when flat)
- **Tokens-first metrics** — tokens primary, cost secondary
- **Rate limit protection** — delays between tests, retry with backoff on empty responses
- **Persistent results** — survive page reloads via storage API
- **AbortController** — stop button kills in-flight API calls
- **Copy results** — sends to chat or textarea fallback

### Dual Scoring
- **LLM Grade (primary)** — second-pass API call reads colony output and scores 1-10 with structured reasoning. Tier-aware rubric handles SIMPLE through SPAWN + clarification outputs.
- **Regex Pattern Checks (secondary)** — per-tier regex checks validate structural elements (role, objective, XML tags, examples, constraints, validation evidence). Tier-appropriate counts: SIMPLE 6, MEDIUM 15, COMPLEX 16, SPAWN 16.
- **Effective score** — LLM grade × 10 when available, regex percentage as fallback. Pass threshold: ≥70%.

### Modes
| Mode | What it does |
|---|---|
| **Coverage** | 30 pre-written tests across all tiers |
| **Adaptive** | 10 auto-generated tests targeting weakest areas |
| **Ablation** | Remove a caste file, re-run tests, measure impact |
| **Stress** | 10 adversarial inputs designed to break the colony |
| **Regression** | Rerun coverage bank, compare against baseline wave |

### Running
1. Open the `.jsx` artifact in Claude.ai
2. Select model (Sonnet 4 default)
3. Toggle LLM Grade ON/OFF
4. Click **▶ Run Next Wave**
5. Wave 1 runs coverage (30 tests, ~$3.50 with LLM grading, ~25-35 min)
6. Switch to Adaptive, Stress, or Regression for subsequent waves
7. Keep running until saturation curve flatlines

### Results

**v3.2.0 (current):**
- Coverage: 30 tests, 26 pass, 80% avg (Sonnet 4, LLM grading ON)
- Adaptive: 20 tests across 2 waves, 20 pass, 89% avg
- 50 total tests, 46 pass, 84% avg, zero new failure modes
- All 5 tiers + all 4 clarification subtypes validated
- 4 coverage "failures" are correct hypothesis protocol behavior — grader calibration queued for v3.2.1

**v3.1.0:**
- Coverage: 30 tests, 29 pass, 95% avg
- Stress: 10 tests, 9 pass, 91% avg

**v3.0.0:**
- 65 tests across 5 waves, 95% avg
- Ablation: Guardian removal had zero score impact → redesigned as conditional second-pass reviewer

### Known Limitations (v3.2.1 roadmap)
- **Output truncation** — `max_tokens: 4000` truncates COMPLEX/CHAIN/SPAWN outputs. Tier-scaled limits queued.
- **LLM grader penalizes hypothesis stopping** — COMPLEX+ correctly stops to surface approaches; grader scores this as "didn't build." Calibration fix queued.
- **Messenger over-classification** — some WORTHY inputs get MEH/ALMOST. Investigating if Messenger calibration or model stochasticity.
- **No wave history viewer** — past wave data in storage but not accessible after screen switch. Persistent history panel queued.
- **Sequential execution** — pipelined execution (overlap grading N with colony N+1) queued.
