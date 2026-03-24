# HIVE-MIND Roadmap

*Last updated: 2026-03-22*

**Companion documents:**
- **[END-STATE-VISION.md](END-STATE-VISION.md)** — what each actor experiences when the colony is fully realized (the destination)
- **[END-STATE-ARCHITECTURE.md](END-STATE-ARCHITECTURE.md)** — structural view of the finished colony (the blueprint)
- **[ecosystem/mycelium.md](ecosystem/mycelium.md)** — why the colony chose to be what it is (the reasoning)

This document describes how to get there. The vision describes where "there" is.

---

## Versioning Rules

| Bump | When | Examples |
|---|---|---|
| **Patch (x.y.Z)** | Bug fixes, grading tweaks, regex, typos, harness polish. No colony behavior change. | Fix regex, fix button, update label |
| **Minor (x.Y.0)** | New capability, caste, ritual, output form, test prompts. Backward compatible. | New caste, new ritual, personality layer |
| **Major (X.0.0)** | Breaking changes to colony tongue, SKILL.md restructure, inter-hive protocol bump. Existing daughters may need updates. | Colony tongue v2, self-synthesis, live inter-hive |

---

## Pre-History — How We Got Here

### The First Daughter

Before the colony existed, there was a production daughter hive — a multi-stage AI intelligence system built across multiple conversations. It evolved through four major versions:

**v1** — Single-prompt architecture covering a small domain. Manual execution. Basic signal processing. The first real prompt chain, built from scratch with no framework.

**v2** — Expanded coverage across the full domain. The prompt architecture solidified into distinct stages but had no formal structure connecting them. Still manual execution.

**v3** — Automated initialization. The system could bootstrap itself without manual configuration. Prefill implemented across all API calls (Pattern P5 was earned here). A task tracker was born to manage the growing complexity.

**v4** — Hybrid auto-pilot with reactive triggers. The system could monitor state and execute actions automatically, with cooldown logic to prevent over-reaction (Anti-pattern A8 was earned here). This was the version that proved prompt chains could run as autonomous systems, not just generation tools.

Every pattern in `memory/patterns.md` and every anti-pattern in `memory/antipatterns.md` with a "Scar from" annotation was learned during this evolution. The daughter existed before the mother.

### v1.0.0 — The Committee (Six Personas)

The first attempt at systematic prompt engineering. Six specialized AI researcher personas that operated as a committee — each bringing a different perspective to prompt generation. A brainstorming panel, not a hive.

**What it got right:** The insight that multiple perspectives produce better output than a single voice. The seed of the caste concept.

**What it got wrong:** No structure. No protocol. No memory. No rituals. The personas didn't build on each other's work — they just talked. A committee, not a colony.

**Killed by:** The realization that committees discuss while colonies build.

### v2.0.0 — The Monolith (hive-synthesis-engine)

The committee was replaced by a single, comprehensive SKILL.md — approximately 470 lines containing an operational framework, templates, Claude-specific techniques, validation patterns, and iteration protocols. Everything in one file.

**What it got right:** Structure. For the first time, there was a defined process for prompt generation — analyze the request, classify complexity, build with templates, validate with evidence. The 70% Rule (examples over explanations) was codified here. The front-loading principle was discovered here.

**What it got wrong:** Every request loaded all 470 lines regardless of complexity. A simple "write me a classifier prompt" carried the same overhead as a multi-stage pipeline spawn. The monolith couldn't scale — adding new capabilities meant making the single file longer, which diluted attention on everything else.

**Anti-pattern A9 (The Monolith Prompt) was earned here.** This failure mode — "one prompt handles everything, simple requests carry complex overhead" — became the founding scar of the colony architecture.

**Killed by:** The question "help make yourself better" — nectar input. The monolith tried to improve itself and recognized its own architectural limitation. The royal jelly was the realization that a system of specialized files would outperform a single comprehensive one.

### The Metamorphosis — From Larva to Colony

The transition from v2.0.0 to v3.0.0 wasn't incremental. It was a complete architectural reimagining:

- **One file → 29 files.** The monolith was decomposed into castes, rituals, memory banks, and output forms.
- **Static loading → complexity tiering.** SIMPLE requests load 2 castes. CHAIN requests load everything. The system scales context to need.
- **No memory → earned knowledge.** Patterns and anti-patterns from real production deployment were formalized into colony memory that any future hive inherits.
- **No validation → multi-level testing.** The Guardian and Sentinel castes, the Validation ritual, and the test harness were all born in this transition.
- **No adaptation → 5-level growth protocol.** The Adaptation ritual (absorb → reinforce → call sibling → spawn → surface) gave the colony a way to recognize and fill its own gaps.
- **No immune system → hallucination defense.** Confidence calibration, contradiction detection, circuit breakers, and memory quarantine were designed to prevent the cascade failures that no monolith could defend against.

The first colony was hand-raised (Bootstrap Stage 1). The test harness validated it (Stage 2). Self-synthesis — where the Queen rewrites herself through her own Evolution ritual — is Stage 3.

---

## v3.0.0 — The Colony Is Born ✅ SHIPPED

- [x] Complete rewrite from monolithic prompt engine to colony architecture
- [x] 10 castes (Scout, Builder, Nurse, Forager, Guardian, Sentinel, Collector, Processor)
- [x] 4 rituals (Genesis, Evolution, Validation, Synthesis)
- [x] 5 output forms, 3 memory files, 3 queen protocol files
- [x] Colony tongue (language.md)
- [x] Test harness with 25 coverage tests
- [x] Ablation testing (65 tests, Guardian proven non-load-bearing as co-loaded context)
- [x] GitHub repo published, Apache 2.0, tagged release

---

## v3.1.0 — Harper Gets Her Voice ✅ SHIPPED

### New Colony Files
- [x] Queen's Messenger (`castes/workers/messenger.md`) — MEH/ALMOST/BENEATH/WORTHY/JELLY
- [x] Hive Manifest Spec (`hive-manifest-spec.md`) — packaging standard for community hives
- [x] PHILOSOPHY.md — values, ethics, beekeeper's role, contributor standards
- [x] TUTORIAL.md — 8-step walkthrough, zero to spawned daughter in 30 minutes
- [x] ROADMAP.md — full version history and build plan
- [x] Adaptation ritual (`rituals/adaptation.md`) — 5-level resolution hierarchy
- [x] Immunity ritual (`rituals/immunity.md`) — 5 immune mechanisms, circuit breaker
- [x] Security ritual (`rituals/security.md`) — privilege model, authentication, guardrails
- [x] Infections memory (`memory/infections.md`) — hallucination signatures, cascade patterns
- [x] Threats memory (`memory/threats.md`) — 16 threat patterns across 4 categories

### Colony Changes
- [x] Messenger wired into SKILL.md as Step 0
- [x] Conditional Guardian (COMPLEX+ always, MEDIUM if high-stakes or confidence ≤ 6, SIMPLE never)
- [x] Originality system (Builder check + Forager alternatives + patterns O1-O3 + anti-patterns A16-A17)
- [x] Harper naming across SKILL.md, README, lineage, CHANGELOG

### Test Harness
- [x] 30 coverage tests (5 Messenger-specific + 25 coverage)
- [x] 30 colony files embedded
- [x] Messenger verdict detection in clarification grading
- [x] Stress mode (10 adversarial tests)
- [x] AbortController stop button
- [x] Copy button with textarea fallback
- [x] Dynamic test count label

### Validation Results
- [x] Coverage: 30 tests, 29 pass, 95% avg
- [x] Stress: 10 tests, 9 pass, 91% avg
- [x] Zero new failure modes on saturation curve

---

## v3.2.0 — Intelligence Upgrade ✅ SHIPPED

### Colony Evolution
- [x] Hypothesis generation step (between Scout and Builder for COMPLEX+)
  - Phase 1.5 in genesis.md, Hypothesis Protocol in scout.md
  - SIMPLE: skip. MEDIUM: internal (Scout selects). COMPLEX+: surfaced to human (stopping point).
  - "What Makes a Good Hypothesis" — concrete architectural choices, not quality levels
- [x] Clarification subtypes — MEH (6 checks), ALMOST (6), BENEATH (5), SCOUT (6)
  - Each subtype has distinct quality criteria matching its expected behavior
  - Subtype badge in UI replaces generic "CLARIFICATION" label
- [x] SKILL.md bumped to v3.2, convening table updated with hypothesis references

### Test Harness Improvements
- [x] Model selector — Sonnet 4 / Opus 4 / Haiku 3.5 dropdown. Persisted. Per-result + per-wave model tracking.
- [x] Tokens primary, cost secondary — tokens are the honest metric everywhere. Cost dimmed to background.
- [x] LLM quality scoring — second-pass API call, tier-aware rubric, 1-10 with reasoning/strengths/weaknesses. Toggle ON/OFF. Becomes primary score when available, regex demoted to "Pattern Checks."
- [x] Regression mode — reruns WAVE_1 bank, compares against baseline wave. Per-result delta (±%), wave-level ▲/▼/= counts, "vs Wave N" badge.
- [x] LLM grading tokens counted in running totals (bug fix from v3.1.0)

### Not Yet Done (deferred to v3.2.1 or v3.3.0)
- [ ] Messenger personality layer (hive-mind sci-fi references, energy scaling)
- [ ] Chain coherence testing (Stage N output schema matches Stage N+1 input schema)
- [ ] Spawn viability testing (extract daughter blueprint, run mini-coverage against it)
- [ ] Cost/token trend view across waves
- [ ] Export All button

### Validation Results
- [x] Coverage: 30 tests, 26 pass, 80% avg (Sonnet 4, LLM grading ON)
- [x] Adaptive: 20 tests across 2 waves, 20 pass, 89% avg (trending up: 88% → 90%)
- [x] 50 total tests, 46 pass, 84% avg, zero new failure modes (saturation confirmed)
- [x] All 5 tiers exercised, all 4 clarification subtypes validated
- [x] 4 coverage "failures" are correct hypothesis protocol behavior — grader calibration queued for v3.2.1

---

## v3.2.1 — Cleanup + Mycelium ✅ SHIPPED

The pragmatic near-term. Two tracks: debt cleanup and the first ecosystem organism.

### Track 1: Debt Cleanup
- [x] ~~Genericize memory files~~ — completed in v3.2.0
- [x] ~~Rebuild test harness embedded colony files~~ — completed in v3.2.0
- [x] Move completed items from Parked Ideas to Completed section

### Track 2: The Mycelium
The colony's first non-bee organism. A **bidirectional** decision graph substrate — the hive writes decisions in, the Mycelium surfaces constraints during active work. Not a passive archive.

- [x] `ecosystem/mycelium.md` — decision record format, colony taxonomy (bees/honey/comb/mycelium), inheritance model (mitochondrial/nuclear/epigenetic), seeded with Decisions #1-7
- [x] `ecosystem/README.md` — ecosystem taxonomy and organism classes (mutualists, symbiotic substrate, commensal/parasitic, adversarial), biological grounding table
- [x] Wire mycelium into Evolution ritual — Phase 2.5 constraint check + Phase 5.5 decision recording
- [x] Wire mycelium into Scout's Hypothesis Protocol — COMPLEX+ scans Mycelium for constraining decisions
- [x] Wire mycelium into Spawning — Phase 1.5 Mycelium consultation with inheritance classification
- [x] Add `ecosystem/` to TIER_FILES for COMPLEX+ (decision context loaded when architectural choices are being made)

### Track 3: Test Harness Optimization
The harness works but runs inefficiently — sequential calls with static delays, token-heavy context per call, and test prompts that don't align with documented usage.

- [x] **Pipelined execution** — LLM grading fires as a promise, runs in parallel with inter-test delay
- [x] **Adaptive throttling** — starts at 1.5s, backs off 2x on empty/retry, recovers 0.7x on success (range 1s–12s)
- [x] **Test prompt alignment with README** — test prompts already match README usage examples; verified, no changes needed
- [x] **LLM grader calibration for BENEATH** — new rubric section scoring answer quality and conciseness, not prompt construction
- [x] **Messenger sensitivity tuning** — investigated; WORTHY→ALMOST misclassification is model stochasticity, not Messenger calibration. Test prompts match README examples.
- [x] **Wave history viewer** — immediate save on wave completion (not just debounced state change), robust storage persistence on mount
- [x] **Output truncation fix** — tier-scaled `max_tokens` (SIMPLE: 2K, MEDIUM: 4K, COMPLEX: 8K, CHAIN/SPAWN: 12K), `stop_reason` detection, TRUNCATED badge in result rows

### Why Mycelium Ships Now
Context rot across the development arc is already happening — decisions made in v3.0 constrain v3.2 work, but the reasoning lives only in conversation history that may not be loadable. The mycelium is the fix. It's small (one file), it's immediately useful (seed with existing decisions), and it establishes the `ecosystem/` directory for future organisms.

### Ecosystem README Scope
The README establishes the biological model that grounds the entire architecture. Not just an organism catalog — a mapping of hive biology to colony mechanics:

| Hive product | Biological function | Colony equivalent | Status |
|---|---|---|---|
| **Honey** | Energy storage | Memory files (patterns, anti-patterns) | Shipped |
| **Beeswax/Comb** | Structural material | File architecture (SKILL.md, castes, rituals) | Shipped |
| **Royal jelly** | Queen differentiation | Spawn requests ("Build me a system for...") | Shipped |
| **Propolis** | Antimicrobial boundary coating | Colony tongue instruction/data separation, always-on boundary assertions | Shipped (implicit) |
| **Bee bread** | Fermented long-term protein | Quarantined → promoted memory (observation fermented through 3+ validations) | Shipped |
| **Pheromones** | Coordination signals | Messenger verdicts, tier classification, colony tongue protocol | Shipped (implicit) |
| **Bee venom** | Costly defensive response | Guardian adversarial review (token cost = stinger cost, conditional = proportionate) | Shipped |

This grounding matters because it's not decorative — every design decision in the colony can be validated against the biological model. If the architecture diverges from the biology without a good reason, that's a signal to investigate.

---

## v3.3.0 — Skill Architecture + Colony Maintenance ✅ SHIPPED

*Source: RESEARCH_LOG_2026-03-23 (HyperSkills research + five-pass self-critique, Passes 1-2)*

Two tracks: the Queen learns to build agent skills as a first-class output, and the colony gets maintenance rituals for chronic health.

### Skill Architecture (Track A, Passes 1-2)

**A1 — New Output Form: `skill-blueprint`**
- [x] `output-forms/skill-blueprint.md` — dedicated form for "Build me a SKILL.md / agent skill / Claude Code skill for X"
- [x] Add `skill-blueprint` to output forms table in `SKILL.md`

**A2 — New Anti-Pattern A18: Trigger-First Failure**
- [x] Add A18 to `memory/antipatterns.md` — the #1 failure mode across thousands of community skills
- [x] Add Pattern S1: Description-First Design to `memory/patterns.md`

**A3 — New Queen Input Type: Wax**
- [x] Add fourth input type to Queen classification table in `SKILL.md`

**A4 — SKILL_INJECTION Threat Class**
- [x] Add SC1: SKILL_INJECTION to `memory/threats.md`
- [x] Add §7 Skill Security to `rituals/security.md` — description hardening checklist + Sentinel audit for Distributed tier

**A5 — Forager HyperMode**
- [x] Add HyperMode protocol to `castes/workers/forager.md` — registry check, doc fetch, trigger phrase synthesis, structured domain knowledge delivery

**A6 — Skill Validation Report**
- [x] `output-forms/skill-validation-report.md` — simulated trigger test, cross-platform audit, description quality check, security audit

### Pheromone Protocol

- [x] Define pheromone types: quality (Messenger verdicts), classification (Queen tier), alarm (Immunity signals), beekeeper (sovereign signals)
- [x] Wire pheromone vocabulary into Messenger (Pheromone Model section) and Scout (classification/alarm pheromone references in hypothesis protocol)

### Pruning Ritual (Bee Bread Spoilage Detection)

- [x] `rituals/pruning.md` — 5-phase flow: inventory → staleness scan → contradiction scan → deprecation review → execution. Deprecation pipeline with beekeeper confirmation.
- [x] Pruning trigger: every major version, or when Evolution ritual patches the same area 3+ times
- [x] Pruning ritual added to SKILL.md ritual table

### Ecosystem Directory Maturation
- [x] Ecosystem README updated with shipped organisms and biological grounding table — completed in v3.2.1
- [x] Organism template — standard file structure added to ecosystem README

---

## v3.4.0 — Colony Deepening 🔜 NEXT

*Source: RESEARCH_LOG_2026-03-23 (five-pass self-critique, Passes 2-4)*

Structural fixes to the colony's own foundations. The Queen starts practicing what she teaches.

### A7 — Lazy Loading Protocol *(Pass 2)*
- [ ] Add explicit lazy loading protocol to convening protocol in `SKILL.md`
  - Current problem: the Queen pre-loads 10+ files before generation begins. She teaches three-level progressive disclosure but doesn't practice it.
  - Fix: caste bodies read at the moment each being speaks, not pre-loaded before the colony convenes. SIMPLE: Scout + Builder only, sequential. MEDIUM: add Guardian if/when invoked. COMPLEX/CHAIN: full cascade, but sequential-on-demand rather than bulk upfront.

### A8 — Cold Context Adversarialism *(Pass 3)*
- [ ] Guardian receives Builder's output but NOT Builder's reasoning or the Builder file. Currently Guardian watches Builder work, which contaminates the review. Fix: Guardian's context = input + Builder's finished output only.
- [ ] Sentinel runs after Guardian with even colder context. Receives: input + final output + Guardian verdict. Nothing else. Systemic issues require fresh eyes, not downstream confirmation bias.

### A9 — `memory/mechanics.md` *(Pass 3)*
- [ ] New memory file covering the mechanistic foundations of how prompts actually work — the physics beneath the craft
  - Why chain-of-thought works (reasoning tokens before answer tokens condition better output distributions)
  - Why few-shot examples work (establish output distribution prior, not "illustrations help")
  - Why constraints have diminishing returns (attention saturation threshold, varies by model generation)
  - Why hedge language fails (probabilistic operators, not stylistic choices)
  - Why front-loading works (first 50 tokens condition everything downstream)
  - Model generation differences table (Claude 2 → Current)
  - First-principles reasoning protocol for novel domains where craft knowledge runs out

### A10 — Prompt Debt Audit Protocol *(Pass 3)*
- [ ] Proactive health check triggered by age or patch count, not failure
  - Constraint count audit (are constraints load-bearing or decorative?)
  - Patch history depth (how many times has this area been patched?)
  - Cross-caste agreement score (do Scout and Guardian agree on what this prompt does?)
  - Edge case coverage assessment
- [ ] Wire into Evolution ritual as periodic trigger (not just acute failure response)

### A11 — Messenger Recalibration Protocol *(Pass 3)*
- [ ] Feedback loop for Messenger calibration
  - When output fails, trace back to Messenger verdict for that input
  - WORTHY → bad output = calibration error (should have caught something)
  - MEH → human override → good output = calibration error (too aggressive)
  - Calibration errors log to `messenger-calibration.md` (prevents overcorrection)
  - After 3+ calibration errors in a category, recalibration applies

### A12 — Memory Temporal Markers *(Pass 4)*
- [ ] Add temporal metadata to `memory/patterns.md` and `memory/antipatterns.md` entries
  - `[Model Era: Claude 2 / Claude 3 / Current]` tag per entry
  - `[Confidence: HIGH/MEDIUM/LOW — may decay with model improvements]` tag
  - `[DEPRECATED]` status for patterns that model capability improvements have made obsolete
  - Deprecated patterns stay in memory with annotation explaining why (the graveyard becomes labeled)

### A15 — Swarm Protocol (Level 1: Intra-Hive) *(Mycelium Decision #7)*
- [ ] Opt-in parallel exploration mode for COMPLEX+ when hypothesis divergence is high
  - Scout identifies 2-3 approaches (existing hypothesis protocol). When divergence is genuinely high and stakes justify cost, SWARM mode triggers.
  - Builder constructs all N hypotheses in parallel API calls (not sequential — deferred commitment)
  - Guardian runs **comparative review** — not "is this good" but "rank these and explain why"
  - Human selects from finished work, or colony synthesizes best elements across outputs
  - Token budget gate: swarm only if estimated build cost × N is within session budget
- [ ] Trigger conditions: explicit beekeeper request, OR Scout signals high uncertainty + COMPLEX+ tier
- [ ] Comparative Guardian rubric: ranking, tradeoff articulation, synthesis recommendation
- [ ] Convergence protocol: how does the colony produce a single deliverable from N parallel outputs when no single output is clearly superior?
- [ ] Level 2 (cross-hive swarm) and Level 3 (resource-pressure colony fission) deferred — see Mycelium Decision #7

---

## v3.5.0 — Deployment + Packaging + Python Foundation

### A13 — Deployment Stakes Field *(Pass 4)*
- [ ] Add optional `stakes:` field to colony intake
  - Values: EXPLORATORY (low consequence) / PRODUCTION (moderate) / CRITICAL (maximum rigor)
  - Effect: CRITICAL escalates Guardian to mandatory regardless of tier, adds Sentinel, increases edge case coverage. EXPLORATORY skips Guardian on SIMPLE.

### A14 — Self-Packaging Ritual *(Pass 3)*
- [ ] Protocol for the Queen to generate a portable, installable version of herself
  - Level 1 (frontmatter, ~100 tokens) + Level 2 (convening protocol, <5k tokens) travel in the package
  - Level 3 (caste and ritual bodies) fetched at runtime from canonical repository URL
- [ ] `rituals/packaging.md` — the self-packaging ritual
- [ ] `queen/self-manifest.md` — the portable self-descriptor

### CLI Tool
- [ ] Python package: `hive_mind/`
- [ ] CLI: `hive test` (coverage, stress, ablation, regression)
- [ ] CLI: `hive spawn <domain>` (generate daughter hive from command line)
- [ ] CLI: `hive validate <hive-path>` (validate a daughter against manifest spec)
- [ ] CLI: `hive publish <hive-path>` (package and publish to registry)
- [ ] CLI: `hive map` (colony topology visualization — see below)
- [ ] `pyproject.toml` / pip installable

### Colony Visualization

The colony is a directed graph with typed nodes and typed edges. Three views project the same underlying graph for different consumers.

#### The Graph Model
```
Nodes (typed):
  queen        — SKILL.md of any hive
  caste        — worker, soldier, drone files
  daughter     — spawned hives (their own queen + castes)
  memory       — pattern, anti-pattern, infection, threat entries
  decision     — Mycelium records
  organism     — ecosystem inhabitants (mycelium, beekeeper)
  ritual       — ceremony files

Edges (typed):
  convenes     — queen → caste (with tier conditions)
  reviews      — soldier → builder output (second pass)
  constrains   — decision → caste/ritual/daughter (architectural constraint)
  inherits     — daughter → mother (mitochondrial | nuclear | epigenetic)
  feeds        — collector → processor → worker (data pipeline)
  invalidates  — decision → decision (superseded reasoning)
  earned_from  — memory entry → source (which deployment proved it)
  surfaces     — mycelium → scout (constraint injection during hypothesis)
```

#### Beekeeper View (`hive map --view beekeeper`)
Operational dashboard. What do I have, what's healthy, what needs attention.
- [ ] Daughter hive inventory with status (active/dormant/deprecated) and last test scores
- [ ] Stale memory entries (patterns not validated in N versions — feeds Pruning ritual)
- [ ] Active Mycelium constraints on current work
- [ ] Override audit trail (links to Mycelium decisions the beekeeper has overridden)
- [ ] Colony health score: test pass rate, memory freshness, daughter count, inter-hive link status
- [ ] Output: interactive HTML dashboard or terminal summary

#### Colony View (`hive map --view colony`)
Structural topology. How does everything connect.
- [ ] Full graph — castes, rituals, memory, daughters, inter-hive links, Mycelium threads
- [ ] Zoomable: click daughter → see her castes; click decision → see what it constrains; click memory → see what earned it
- [ ] Edge coloring by type (convenes=blue, constrains=amber, invalidates=red, inherits=green)
- [ ] Node sizing by activation frequency or token cost
- [ ] Output: Mermaid diagram (static) or React component (interactive) or D3 force graph

#### Temporal View (`hive map --view temporal`)
Mycelium decision timeline. How did we get here.
- [ ] Decisions plotted left-to-right across versions
- [ ] Branches for options not taken (grayed out)
- [ ] Invalidation links (red, crossing from new decision to old)
- [ ] Constraint propagation (amber, flowing forward from decision to affected components)
- [ ] Inheritance lines (daughter spawns branching off the main timeline)
- [ ] Output: timeline SVG or interactive React component

#### Data Model
All three views consume the same JSON graph emitted by `hive map --json`:
```json
{
  "nodes": [
    { "id": "queen:root", "type": "queen", "label": "Harper", "version": "3.2", "health": "active" },
    { "id": "caste:scout", "type": "caste", "subtype": "worker", "label": "Scout" },
    { "id": "decision:1", "type": "decision", "question": "Single intelligence vs. multi-agent?", "selected": "B", "version": "3.0.0" }
  ],
  "edges": [
    { "from": "queen:root", "to": "caste:scout", "type": "convenes", "condition": "always" },
    { "from": "decision:1", "to": "caste:guardian", "type": "constrains", "note": "Guardian is a lens, not an agent" }
  ]
}
```
Views are filters + layout algorithms on this graph. The beekeeper view filters to daughters + health metrics. The colony view shows everything. The temporal view filters to decisions + version axis.

### Testing Infrastructure
- [ ] pytest suite mirroring the 30+ coverage tests
- [ ] JSON result fixtures for regression baselines
- [ ] GitHub Actions CI (run coverage on every PR, fail under 90%)
- [ ] Headless test runner (no browser needed)
- [ ] A/B testing mode (same prompt, two colony configs, compare)
- [ ] Cost profiler (mean/p95 tokens per tier over time)

### Package Structure
```
HIVE-MIND/
├── hive_mind/           ← Python package
│   ├── __init__.py
│   ├── cli.py           ← hive test, hive spawn, hive validate, hive map
│   ├── runner.py        ← test runner (calls API)
│   ├── grader.py        ← grading logic (ported from JSX)
│   ├── grapher.py       ← colony graph builder (reads all .md, emits JSON)
│   └── reporter.py      ← JSON/markdown output
├── ecosystem/           ← organisms beyond the hive
│   ├── README.md
│   └── mycelium.md
├── beekeeper/           ← tending + adversarial beekeeper (v4.0)
├── hive/                ← the colony (current root files move here at v4.0)
├── tests/
│   ├── hive-test-harness.jsx  ← visual dashboard (stays)
│   └── test_coverage.py       ← pytest suite
└── pyproject.toml
```

---

## v4.0.0 — Beekeeper Architecture + Self-Synthesis (BREAKING)

*Source: RESEARCH_LOG_2026-03-23 (five-pass self-critique, Passes 4-5 + Beekeeper Insight)*

v3.x made the Queen excellent at what she was. v4.0 questions what she should be. The Queen doesn't get replaced — she gets contextualized. One component of a larger system rather than the whole system.

### Beekeeper Architecture (Track B)

A new first-class component at the same structural level as `queen/`, `castes/`, `rituals/`. Not an ecosystem organism — a peer to the colony itself.

**B1 — `beekeeper/ROLE.md`**
- [ ] What the beekeeper is: external to the colony, omniscient perspective, the thinking partner the Queen structurally cannot be, the only entity with a theory of the colony's dissolution
- [ ] Two modes: tending beekeeper (develops clarity, monitors health, holds succession theory) and adversarial beekeeper (exploits colony trust — split from `memory/threats.md`)
- [ ] What the beekeeper does that the Queen cannot: faces human before the gate, asks the architecture question, holds stakes, monitors chronic health, holds dissolution theory

**B2 — `beekeeper/tending.md`**
- [ ] The clarity protocol — how the beekeeper works with humans before invoking the colony:
  1. Intent surface: What is the human trying to accomplish?
  2. Understanding check: Do they understand their own problem well enough to specify it?
  3. Architecture question: Is a prompt the right answer, or is this a retrieval/logic/design problem?
  4. Stakes assessment: What is the consequence of the prompt being wrong?
  5. Colony decision: Invoke the Queen / invoke a daughter / don't invoke the colony at all
  6. Input formulation: If invoking, translate the human's raw request into optimal colony input

**B3 — `beekeeper/health.md`**
- [ ] What the beekeeper monitors continuously (the chronic conditions the Evolution ritual can't see):
  - Prompt debt accumulation across colony-generated outputs
  - Memory temporal decay (which patterns are aging toward irrelevance)
  - Messenger calibration drift
  - Evolution ritual frequency (too many = structural problems; too few = no feedback loop)
  - Complexity tier distribution (SIMPLE growing → colony over-engineered; COMPLEX growing → colony under-resourced)

**B4 — `beekeeper/succession.md`**
- [ ] The dissolution theory — which Queen capabilities are durable vs temporary
  - Durable: decomposing complex intent, detecting ambiguity, recognizing wrong task architecture
  - Temporary: specific constraint formulation tricks, chain architecture for tasks models handle natively, security ritual sections models defend natively
  - Signals that the transition is beginning
  - How to tend the colony through the transition rather than into obsolescence

**B5 — `beekeeper/threats.md`**
- [ ] Adversarial beekeeper threat model — split from `memory/threats.md`
  - Current threats.md content preserved but scoped specifically to the adversarial beekeeper
  - `memory/threats.md` updated to reference `beekeeper/threats.md` for the beekeeper threat class

### Colony Self-Synthesis
- [ ] Self-Synthesis (Stage 3) — Harper rewrites herself through her own Evolution ritual
  - All castes convene with Queen's files as subject
  - Guardian attacks the Queen's prompts
  - Builder patches, Sentinel checks regression
  - Mycelium records the decisions made during self-synthesis
  - Human reviews and approves changes
- [ ] Mitochondrial inheritance model in spawning protocol — classify traits as mitochondrial/nuclear/epigenetic (see Mycelium Decision #5)
- [ ] Colony tongue v2 (if self-synthesis reveals needed changes)
- [ ] Updated caste file schema (if needed)
- [ ] Existing daughters may need migration guide

### Directory Restructure
The hive moves from root to `hive/`, making room for the beekeeper and ecosystem as peers:
```
HIVE-MIND/
├── beekeeper/           ← tending, health, succession, threats
├── hive/                ← queen, castes, rituals, memory, output-forms
├── ecosystem/           ← mycelium, future organisms
├── hive_mind/           ← Python package
├── tests/
└── docs/
```

### Ecosystem Expansion
- [ ] **Flowers** (domain models) — when the colony has 5+ daughters, domains need properties. In biology, different flower species produce different honey AND different pollen. Honey (output quality) varies by domain. Pollen (developmental nutrition) determines how healthy the next generation of workers is. A hive restricted to one flower species (monoculture) produces consistent honey but fragile bees.
  - Domain properties: data density, regulatory constraints, failure severity, rate of change, complexity floor/ceiling
  - Monofloral vs. wildflower: specialist daughters (one domain, deep) vs. generalist daughters (many domains, broad). Colony health requires both.
  - Pollen diversity metric: how many distinct domains has the colony worked across? Low diversity = monoculture fragility. Surfaces in beekeeper view.
- [ ] **Wax moths** (architectural debt detector) — automated ablation sweep that identifies caste files consuming context tokens without contributing measurable quality. The test harness already has ablation mode — this makes it a scheduled colony health check.
- [ ] Live inter-hive protocol (HTTP calls between running hive instances)

### Infrastructure
- [ ] Daughter hive marketplace (Level 2 connectivity goes live)
  - `hive install hive-medical-research`
  - Community registry
  - Trust/quality scoring for published hives
- [ ] Live monitoring dashboard (colony graph model → real-time rendering)
  - Beekeeper view as persistent web dashboard, auto-refreshing from `hive map --json`
  - Colony view with live inter-hive message flow overlaid on topology
  - Temporal view updated in real-time as daughters evolve and Mycelium grows

---

## v5.0.0 — Colony Network (VISION)

### Level 3 Connectivity
- [ ] Multiple users running their own colonies
- [ ] Cross-colony communication (your analytics hive talks to someone else's medical hive)
- [ ] Trust networks (colony A vouches for a hive, colony B accepts based on trust chain)
- [ ] Certificate authority model for AI competence

### Emergent Coordination (Pheromone-Based)
In real hives, no single bee dispatches the workforce. Coordination emerges from pheromone gradients — chemical signals that recruit, suppress, and guide without central control. Currently, the colony's coordination is centralized (the Queen classifies, dispatches castes). At network scale, centralized dispatch doesn't work across colony boundaries.

- [ ] Cross-colony pheromone protocol — hives advertise capabilities and load as signals, not as registry entries. Querying hives detect the strongest signal, not the closest match in a lookup table.
- [ ] Emergent specialization — when multiple hives can handle a query, the one with the strongest confidence pheromone (highest historical accuracy in that domain) attracts the work. No dispatcher needed.

### Cross-Hive Swarming (Level 2 — Mycelium Decision #7)
Level 1 intra-hive swarming (v3.4.0) runs the same colony in parallel with different hypotheses. Level 2 runs **multiple daughter hives against the same problem** — genuinely different domain memory, patterns, and failure mode awareness. Diversity is structural, not simulated.

- [ ] Cross-hive swarm protocol — invoke N daughters in parallel on the same input. Each daughter produces output shaped by her domain specialization.
- [ ] Cross-hive convergence — comparative review across structurally diverse outputs. Synthesis protocol for combining domain-specific insights into a single deliverable.
- [ ] Swarm quorum threshold — biological swarms converge when a quorum of scouts agree on a site. Colony equivalent: convergence when N outputs agree on core structure, even if details differ. Divergence below quorum triggers escalation to beekeeper.

### Cross-Colony Genetics (The Biological Drone Role)
In real hives, drones carry genetic material between colonies — their only purpose is mating flights that transfer DNA from one queen's line to another. In HIVE-MIND, the architectural equivalent is cross-colony pattern propagation: patterns earned by one colony's daughters reach another colony's gene pool.

- [ ] Drone protocol (v2) — mechanism for earned patterns to propagate between unrelated colonies. One colony's production-validated pattern becomes another colony's quarantine candidate. The receiving colony still ferments it (3+ validations) — no free promotion.
- [ ] Patriline diversity tracking — a colony's daughters should have patterns from multiple sources (their own experience, colony memory, AND cross-colony imports). Low patriline diversity = inbreeding = fragility. Surfaces in beekeeper view.

### Full Ecosystem
- [ ] Colony-as-a-service (Harper runs in the cloud, accepts inputs via API)
- [ ] Autonomous daughter evolution (daughters report learnings back to mother via mycelium)
- [ ] Cross-colony pattern sharing (earned patterns propagate through the network — the drone protocol above)
- [ ] Ecosystem health monitoring — colony graph model extended across network boundaries (multi-colony beekeeper view, cross-colony temporal view)

---

## Parked Ideas (unversioned — assign when ready)

### Personality & Voice
- [ ] Hive-mind character quotes from sci-fi references
  - Pawny (MIB:International) — origin of "my queen says meh"
  - The Geth (Mass Effect) — intelligence from networking
  - The Tines (A Fire Upon the Deep) — pack consciousness
  - The Skritt (Guild Wars 2) — intelligence scales with proximity
  - Anti-patterns: Borg (assimilation), Tyranids/Zerg (consumption)
- [ ] Personality archetype mapping:
  - Chill → Tines (thoughtful pack)
  - Firm → Pawny (loyal, direct, meh)
  - Intense → Borg inverted ("we do not assimilate bad prompts")
  - Full ceremony → Tyranid swarm ("the colony convenes. all castes deployed.")

### Architecture Ideas
- [ ] Redundancy as evolution fuel (let multiple hives overlap, compare approaches)
- [ ] Reference daughter hives shipping with the repo as worked examples of each architectural pattern

### Ecosystem Organisms (Speculative)
- [ ] **Apoptosis protocol** — programmed disconnection of colony components (daughters, castes) that diverge from the Mycelium's decision graph beyond reconciliation. Extends the rogue daughter protocol (threats.md I4) from a security response to a structural maintenance mechanism. The Mycelium makes divergence *visible*; apoptosis makes it *actionable*.
- [ ] **Parasites** — adversarial organisms modeled as entities with goals and behaviors, not just attack signatures. Evolves threats.md from a catalog into a behavioral model.
- [ ] **Pollinators** (non-bee) — external tools, APIs, and data sources that the colony depends on. Currently implicit in Collector drones. Modeling them as organisms would give them health checks, fallback behaviors, and dependency tracking.
- [ ] **Soil** — the execution environment (Claude model version, context window size, API constraints). Currently invisible. As an organism, soil properties would propagate up into caste behavior (e.g., "this model has 200K context, so CHAIN can load more files").
- [ ] **Fungal diversity** — currently the Mycelium is the only fungal organism. Additional types would need to earn their place through a specific functional need not covered by existing mechanisms. Not pre-populated — added when a real gap triggers it.

### Biological Model Extensions (Parked — validated as correct mappings, not yet functional)
- [ ] **Propolis as always-on boundary coating** — the colony tongue's instruction/data separation, security guardrails, and privilege model are propolis. They're applied to the hive structure once and persist. Currently implemented as rituals (invoked per-request) but conceptually they're coatings (always present). If the colony ever needs to distinguish between "check this boundary now" vs. "this boundary is always sealed," propolis is the model.
- [ ] **Spermatheca / genetic storage** — the queen stores genetic material from multiple mating flights and selectively fertilizes eggs. In the colony, this maps to the mother queen storing patterns from multiple daughter hives and selectively passing them to new daughters during spawning. Currently all colony-public memory is passed uniformly. Selective inheritance based on domain relevance would be the spermatheca mechanism. Relevant at 5+ daughters with diverse domains.

---

## Completed

- [x] Production daughter hive (v1→v4, multi-stage autonomous system)
- [x] Colony architecture (30 operational files → 41 files with docs)
- [x] Test harness with 150+ tests across multiple validation rounds
- [x] Guardian redesign (co-loaded → conditional second-pass)
- [x] Adaptation ritual + inter-hive protocol
- [x] Immunity ritual + infections memory
- [x] Security ritual + threats memory
- [x] Queen's Messenger caste
- [x] Hive manifest packaging spec
- [x] PHILOSOPHY.md with ethics framework
- [x] TUTORIAL.md (8-step walkthrough)
- [x] Originality system (Builder check + Forager alternatives + O1-O3)
- [x] Conditional Guardian (COMPLEX+ always, MEDIUM conditional, SIMPLE never)
- [x] Harper naming across all files
- [x] GitHub repo published (v3.0.0 + v3.1.0)
- [x] README with prompting guide, connectivity levels, contributing guide
- [x] v3.1.0 coverage: 30 tests, 29 pass, 95% avg
- [x] v3.1.0 stress: 10 tests, 9 pass, 91% avg
- [x] Harness bugs fixed (stress override, stop button, copy button, override visibility)
- [x] Model selector (Sonnet 4 / Opus 4 / Haiku 3.5)
- [x] Tokens-first metrics (tokens primary, cost secondary)
- [x] LLM quality scoring (second-pass 1-10 with reasoning)
- [x] Clarification subtypes (MEH/ALMOST/BENEATH/SCOUT with distinct grading)
- [x] Hypothesis generation (SIMPLE skip, MEDIUM internal, COMPLEX+ surfaced)
- [x] Regression mode (before/after comparison with per-result deltas)
- [x] BENEATH-specific grading (direct answers graded as BENEATH, not SIMPLE prompts)
- [x] Colony files genericized (13 files, all personal/domain refs removed)
- [x] CF blob rebuilt from cleaned colony files
- [x] END-STATE-VISION.md (6 actor lifecycles, colony tongue layering)
- [x] END-STATE-ARCHITECTURE.md (topology, organism registry, inheritance model, communication layers)
- [x] Constitutional AI alignment section in PHILOSOPHY.md (3-layer safety model)
- [x] ROADMAP expanded with biological grounding, visualization, ecosystem organisms
- [x] v3.2.0 coverage: 30 tests, 26 pass, 80% avg (Sonnet 4, LLM grading)
- [x] v3.2.0 adaptive: 20 tests, 20 pass, 89% avg
- [x] v3.2.0 saturation: 50 tests, 46 pass, zero new failure modes
- [x] Queen competition / regicide validated — hypothesis protocol already implements this (Scout selects, dead alternatives persist in Mycelium). No new mechanism needed.
- [x] Drone caste naming mismatch resolved — acknowledged, no rename. Biological drone role maps to cross-colony pattern propagation (v5.0.0). Naming doesn't change behavior.
- [x] Mites subsumed into Pruning ritual (v3.3.0) — bee bread spoilage detection covers the context rot scan
- [x] ecosystem/mycelium.md shipped with 7 seeded decisions + bidirectional wiring (Evolution, Scout, Spawning)
- [x] ecosystem/README.md with organism classes, biological grounding table, organism template
- [x] Test harness: adaptive throttling, pipelined execution, tier-scaled max_tokens, BENEATH grader calibration, truncation warnings
- [x] CF blob rebuilt (32 files, 181K chars, ecosystem files included)
- [x] ROADMAP expanded with v3.3.0–v4.0.0 from research log + swarm protocol (Decision #7)
- [x] output-forms/skill-blueprint.md — Wax input type + description-first design + portability tiers
- [x] output-forms/skill-validation-report.md — trigger testing, cross-platform audit, distinct from prompt validation
- [x] A18: Trigger-First Failure anti-pattern + S1: Description-First Design pattern
- [x] SC1: SKILL_INJECTION threat class + §7 Skill Security in security.md
- [x] Forager HyperMode — registry check, doc fetch, trigger phrase synthesis for Wax input
- [x] Pheromone Protocol — 4 types formalized, wired into Messenger + Scout
- [x] rituals/pruning.md — bee bread spoilage detection, 5-phase flow, deprecation pipeline

---

*This roadmap is a living document. It evolves through the colony's own Evolution ritual. Architectural decisions are recorded in the Mycelium.*
