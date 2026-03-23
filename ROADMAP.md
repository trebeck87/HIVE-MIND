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

## v3.2.0 — Intelligence Upgrade ✅ BUILT (pending tag)

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

## v3.2.1 — Cleanup + Mycelium 🔜 NEXT

The pragmatic near-term. Two tracks: debt cleanup and the first ecosystem organism.

### Track 1: Debt Cleanup
- [x] ~~Genericize memory files~~ — completed in v3.2.0
- [x] ~~Rebuild test harness embedded colony files~~ — completed in v3.2.0
- [ ] Move completed items from Parked Ideas to Completed section

### Track 2: The Mycelium
The colony's first non-bee organism. A **bidirectional** decision graph substrate — the hive writes decisions in, the Mycelium surfaces constraints during active work. Not a passive archive.

- [ ] `ecosystem/mycelium.md` — decision record format, colony taxonomy (bees/honey/comb/mycelium), inheritance model (mitochondrial/nuclear/epigenetic), seeded with Decisions #1-6
- [ ] `ecosystem/README.md` — ecosystem taxonomy and organism classes (mutualists, symbiotic substrate, commensal/parasitic, adversarial), biological grounding table
- [ ] Wire mycelium into Evolution ritual — before patching, check ADL for prior decisions that constrain the change
- [ ] Wire mycelium into Scout's Hypothesis Protocol — hypotheses for COMPLEX+ reference relevant prior decisions
- [ ] Wire mycelium into Spawning — surface mitochondrial vs. nuclear trait boundary during daughter creation
- [ ] Add `ecosystem/` to TIER_FILES for COMPLEX+ (decision context loaded when architectural choices are being made)

### Track 3: Test Harness Optimization
The harness works but runs inefficiently — sequential calls with static delays, token-heavy context per call, and test prompts that don't align with documented usage.

- [ ] **Pipelined execution** — overlap LLM grading call for test N with colony call for test N+1. The grading call is ~8K tokens; the colony call is ~150K. Pipelining cuts dead time in half without doubling peak token throughput.
- [ ] **Adaptive throttling** — replace static delays with backoff-on-empty. Start fast, increase delay when rate limiter hits, decrease when calls succeed. Currently using fixed 5s/3s delays regardless of model or load.
- [ ] **Test prompt alignment with README** — swap test prompts to match README usage examples where applicable. Users who follow the README should see behavior consistent with what the test bank validated.
- [ ] **LLM grader calibration for BENEATH** — the grader currently penalizes BENEATH responses for "not building a prompt." BENEATH responses are correct colony behavior (answering directly, no ritual). The grading rubric should score BENEATH on answer quality and conciseness, not on prompt construction.
- [ ] **Messenger sensitivity tuning** — the colony classifies some WORTHY inputs as MEH/ALMOST (e.g., "Write a prompt to classify customer support tickets by urgency" triggered ALMOST). Investigate whether this is Messenger calibration or model stochasticity. If consistent, patch messenger.md.
- [ ] **Wave history viewer** — persistent view of all saved waves in storage, accessible without re-running. Currently wave data saves to `window.storage` but is only visible while the artifact is open with the wave in state. If the user switches screens mid-run or closes the artifact, completed wave data exists in storage but can't be accessed. Add a "Load History" panel that reads from storage on mount and displays past waves independently of current run state.
- [ ] **Output truncation fix** — `callAPI` hardcodes `max_tokens: 4000`. COMPLEX/CHAIN/SPAWN outputs with hypothesis proposals, validation evidence, and full prompt construction routinely exceed this. Colony gets cut off mid-output, causing downstream regex failures on elements that would have appeared later. Fix: tier-scaled max_tokens (SIMPLE: 2000, MEDIUM: 4000, COMPLEX: 8000, CHAIN/SPAWN: 12000) or a dynamic approach based on system prompt size. Also display a truncation warning in the result row when `stop_reason` is `max_tokens`.

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

## v3.3.0 — Beekeeper + Pheromones + Pruning

The Beekeeper is the first mutualist organism. The sovereign is currently modeled as a permission tier in `rituals/security.md` — that's necessary but insufficient. The Beekeeper is an organism with behaviors, communication patterns, and failure modes.

### Beekeeper Organism
- [ ] `ecosystem/beekeeper.md` — behavioral model of the human sovereign
  - Communication patterns (how the beekeeper provides direction, feedback, overrides)
  - Productive interaction patterns (what makes a good beekeeper)
  - Failure modes (not just B1-B3 threats, but B4: underspecification, B5: contradictory direction, B6: absent beekeeper)
  - Override audit trail format (links to mycelium decision records)
- [ ] Integrate beekeeper model into Messenger — Messenger adapts tone/depth based on observed beekeeper patterns
- [ ] Integrate beekeeper model into Scout — hypothesis surfacing format adapts to beekeeper preferences

### Pheromone Protocol
In real hives, pheromones coordinate colony behavior without central dispatch — queen mandibular pheromone maintains social cohesion, alarm pheromone recruits defenders, Nasonov pheromone guides foragers home. The colony already has implicit pheromones (Messenger verdicts, tier classification, colony tongue). Making them explicit creates a coordination model.

- [ ] Define pheromone types in the colony:
  - **Classification pheromones** — tier signals (SIMPLE/MEDIUM/COMPLEX/CHAIN) that determine which castes convene. Currently in SKILL.md as a table. Formalized as a signal protocol.
  - **Quality pheromones** — Messenger verdicts (MEH/ALMOST/BENEATH/WORTHY/JELLY) that gate colony activation. Already shipped, but framing them as pheromones clarifies that they're coordination signals, not decisions.
  - **Alarm pheromones** — circuit breaker trips, Guardian RESTRUCTURE verdicts, confidence ≤ 4 streaks. Signals that recruit defensive castes. Currently in immunity.md as thresholds.
  - **Beekeeper pheromones** — the sovereign's communication patterns. Direction, urgency, domain context, satisfaction signals. This is what the beekeeper organism model captures.
- [ ] Wire pheromone vocabulary into Messenger and Scout documentation (not new mechanics — naming what exists so it can be discussed precisely)

### Pruning Ritual (Bee Bread Spoilage Detection)
In biology, bee bread is pollen fermented with honey and enzymes — long-term protein storage that feeds the colony when fresh pollen isn't available. Spoiled bee bread weakens the brood. Colony memory IS bee bread — raw observations fermented through quarantine into trusted patterns. The Pruning ritual detects spoilage.

- [ ] `rituals/pruning.md` — periodic re-validation of colony memory
  - Guardian + Sentinel review existing `memory/patterns.md` entries against current colony behavior
  - Flag stale entries (technically true but no longer useful — bee bread past its shelf life)
  - Flag contradicted entries (superseded by newer patterns — actively spoiled)
  - Deprecation flow: trusted → flagged → deprecated → moved to infections.md as "outdated pattern"
- [ ] Pruning trigger: every major version, or when Evolution ritual patches the same area 3+ times

### Ecosystem Directory Maturation
- [ ] Ecosystem README updated with shipped organisms (mycelium, beekeeper) and biological grounding table
- [ ] Organism template — standard format for future ecosystem inhabitants

---

## v3.4.0 — Python Foundation + Colony Visualization

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
│   ├── mycelium.md
│   └── beekeeper.md
├── hive/                ← the colony (current root files move here at v4.0)
├── tests/
│   ├── hive-test-harness.jsx  ← visual dashboard (stays)
│   └── test_coverage.py       ← pytest suite
└── pyproject.toml
```

---

## v4.0.0 — Self-Synthesis + Ecosystem (BREAKING)

### Colony Evolution
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
The hive moves from root to `hive/`, making room for the ecosystem as a peer:
```
HIVE-MIND/
├── hive/                ← queen, castes, rituals, memory, output-forms
├── ecosystem/           ← mycelium, beekeeper, future organisms
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
- [ ] **Drone caste naming mismatch** — HIVE-MIND drones do compute-without-judgment. Biological drones carry genetic material between colonies (mating flights). The biological drone role maps to cross-colony pattern propagation (v5.0.0 drone protocol). The naming mismatch is acknowledged but not worth a rename — it would break existing documentation for a taxonomy correction that doesn't change behavior.
- [ ] **Mites (context rot detector)** — passive scan for trusted patterns that haven't been validated in N versions. Folded into Pruning ritual (v3.3.0) as "bee bread spoilage detection." May resurface as its own organism if the Pruning ritual proves insufficient.
- [ ] **Queen competition / regicide** — in biology, the first queen to emerge kills rival queens in their cells. In the colony, the Scout's hypothesis protocol selects one approach and kills alternatives. The "dead" alternatives persist in the Mycelium as branches not taken. No new mechanism needed — validates existing design.
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

---

*This roadmap is a living document. It evolves through the colony's own Evolution ritual. Architectural decisions are recorded in the Mycelium.*
