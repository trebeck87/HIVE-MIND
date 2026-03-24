# Changelog

All notable changes to the HIVE-MIND colony.

---

## [3.3.0] — 2026-03-23

### Skill Architecture + Colony Maintenance

**The Queen learns to build agent skills as first-class artifacts, and the colony gets maintenance rituals for chronic health.**

*Source: RESEARCH_LOG_2026-03-23 — HyperSkills research + five-pass self-critique*

#### New: Skill Blueprint Output Form (A1)
- `output-forms/skill-blueprint.md` — dedicated form for Wax input (SKILL.md generation)
- Description-first design protocol: trigger condition before instructions, always
- Three-level structure template (frontmatter → body → `references/` + `scripts/` + `assets/`)
- Portability tiers: Personal / Project / Distributed
- Cross-platform compatibility audit for Distributed tier
- File structure templates by complexity: Simple, Complex (+`references/`), MCP (+`metadata.mcp-server`)

#### New: Wax Input Type (A3)
- Fourth Queen input type: Wax (agent skill) — "Build me a SKILL.md", "Create a Claude Code skill for..."
- Routes to `skill-blueprint` output form instead of `system-prompt.md`
- Distinct from Pollen (standard prompts) and Royal Jelly (full systems)

#### New: Anti-Pattern A18 — Trigger-First Failure (A2)
- The #1 failure mode across thousands of community skills: building instructions before designing the trigger
- Description written as documentation rather than as a pattern-match surface
- Companion pattern S1: Description-First Design added to `memory/patterns.md`

#### New: SKILL_INJECTION Threat Class (A4)
- SC1 in `memory/threats.md` — skills as prompt injection vectors at Level 1 (session startup)
- §7 Skill Security added to `rituals/security.md` — description hardening checklist + Sentinel audit for Distributed tier
- Covers: outbound network calls, privilege escalation via `allowed-tools`, instructions-within-instructions

#### New: Forager HyperMode (A5)
- Outward-facing protocol for skill construction targeting documented external systems
- Registry check (agentskills.io, SkillReg, AgentSkillsRepo) before building from scratch
- Documentation fetch → API surface extraction → trigger phrase synthesis → structured domain knowledge delivery

#### New: Skill Validation Report (A6)
- `output-forms/skill-validation-report.md` — distinct from `validation-report.md`
- Simulated trigger test (5 phrasings), cross-platform audit, description quality check
- Different question: "Will this skill activate and is it safe?" vs "Is this output good?"

#### New: Pheromone Protocol
- Pheromone Model section added to `castes/workers/messenger.md`
- Four pheromone types formalized: quality (Messenger verdicts), classification (Queen tier), alarm (Immunity signals), beekeeper (sovereign signals)
- Scout hypothesis protocol now references classification and alarm pheromones for depth escalation
- Descriptive vocabulary — names what already exists so it can be discussed precisely

#### New: Pruning Ritual
- `rituals/pruning.md` — periodic re-validation of colony memory (bee bread spoilage detection)
- 5-phase flow: inventory → staleness scan → contradiction scan → deprecation review → execution
- Deprecation pipeline: trusted → flagged → deprecated (annotated in place) → archived (if actively misleading)
- Triggers: major version bumps, repeated Evolution patches in same area, beekeeper request
- Beekeeper decides — colony does not auto-deprecate

#### Changed: SKILL.md
- Wax input type added to Queen classification table
- Skill Blueprint + Skill Validation Report added to output forms table
- Pruning ritual added to ritual table

#### Changed: Ecosystem README
- Organism file template added — standard structure for future ecosystem inhabitants

#### File Count: 45 → 47 (3 new files, 10 modified)

---

## [3.2.1] — 2026-03-23

### Mycelium + Harness Optimization

**The colony grows its first non-bee organism and the test harness gets faster and smarter.**

#### New: The Mycelium (ecosystem/mycelium.md)
- The colony's first ecosystem organism — a bidirectional decision graph substrate
- Decision record format with options, rationale, constraints created, and invalidation links
- Colony taxonomy table: bees (ephemeral) / honey (memory) / comb (structure) / mycelium (reasoning)
- 7 seeded decisions: single intelligence (#1), conditional Guardian (#2), hypothesis tiering (#3), bidirectional mycelium (#4), classified inheritance (#5), tongue layering (#6), swarm protocol (#7)
- Inheritance model: mitochondrial (locked) / nuclear (mutable) / epigenetic (tunable)

#### New: Ecosystem README (ecosystem/README.md)
- 5 organism classes: substrate, mutualist, commensal, parasite, sovereign
- Shipped organisms (mycelium), planned organisms (beekeeper, flowers, wax moths)
- Biological grounding table (10 entries mapping hive products to colony mechanics)

#### Changed: Mycelium Wired into Colony Systems
- **Evolution ritual** — Phase 2.5 (constraint check before patching) + Phase 5.5 (decision recording after architectural changes)
- **Scout** — COMPLEX+ hypothesis protocol scans Mycelium for constraining decisions; new anti-pattern for ignoring the Mycelium
- **Spawning** — Phase 1.5 (Mycelium consultation: architectural constraints + inheritance classification)
- **SKILL.md** — ecosystem/mycelium.md added to GATHER context for COMPLEX+ and to Ecosystem file table

#### Changed: Test Harness Optimization (7 fixes)
- **Output truncation fix** — tier-scaled `max_tokens` (SIMPLE: 2K, MEDIUM: 4K, COMPLEX: 8K, CHAIN/SPAWN: 12K), `stop_reason` detection, TRUNCATED badge in result rows
- **Pipelined execution** — LLM grading fires as a promise, runs in parallel with inter-test delay
- **Adaptive throttling** — starts at 1.5s, backs off 2x on empty/retry, recovers 0.7x on success (range 1s–12s). Replaces fixed 5s/3s delays.
- **LLM grader calibration for BENEATH** — new rubric section scoring answer quality and conciseness, not prompt construction
- **Wave history robustness** — immediate save on wave completion, not just debounced state change
- **CF blob rebuilt** — 32 files (was 30), 181K chars, includes ecosystem files
- **TIER_FILES updated** — ecosystem/mycelium.md added to COMPLEX, CHAIN, SPAWN tiers

#### Changed: ROADMAP.md Expanded
- v3.3.0: Skill Architecture (A1-A6) + Pheromones + Pruning (from research log)
- v3.4.0: Colony Deepening (A7-A12 + A15 Swarm Protocol Level 1)
- v3.5.0: Deployment + Packaging + Python Foundation (pushed from old v3.4.0)
- v4.0.0: Beekeeper Architecture (B1-B5) merged with Self-Synthesis
- v5.0.0: Cross-Hive Swarming (Level 2) added
- Parked Ideas cleaned: 3 items resolved → Completed section

#### New: Mycelium Decision #7 — Swarm Protocol
- Hybrid approach selected: sequential by default, swarm opt-in when hypothesis divergence is high
- Does not contradict Decision #1 (single intelligence) — parallel exploration with different starting conditions, not performative multi-agent debate
- Level 1 (intra-hive) slotted at v3.4.0, Level 2 (cross-hive) at v5.0.0
- Quorum convergence (Option 3) identified as the architecturally interesting path

#### File Count: 43 → 45 (2 new files, 6 modified)

---

## [3.2.0] — 2026-03-22

### Intelligence Upgrade

**The colony learns to think before it builds.** Hypothesis generation, LLM-based quality scoring, and regression testing make the colony smarter about what it produces and how it validates.

#### New: Hypothesis Protocol
- Scout proposes 2-3 concrete approaches with tradeoffs before the Builder constructs
- SIMPLE: skip (no ceremony needed). MEDIUM: internal (Scout selects, Builder executes). COMPLEX+: surfaced to human as a stopping point — colony waits for selection.
- Phase 1.5 added to Genesis ritual between Reconnaissance and Foraging
- "What Makes a Good Hypothesis" — architectural choices with real tradeoffs, not quality levels

#### New: LLM Quality Scoring
- Second-pass API call scores colony output 1-10 with structured reasoning, strengths, and weaknesses
- Tier-aware rubric: SIMPLE through SPAWN each have distinct scoring criteria
- Clarification outputs (MEH/ALMOST/BENEATH/SCOUT) scored for appropriateness, not prompt quality
- Toggle ON/OFF — off falls back to regex pattern-matching
- LLM score becomes primary display; regex checks demoted to "Pattern Checks"

#### New: Clarification Subtypes
- Previously all clarification responses graded with the same 5 generic checks
- Now 4 distinct grading paths: MEH (6 checks), ALMOST (6), BENEATH (5), SCOUT (6)
- Each subtype has quality criteria matching its expected behavior
- BENEATH grading validates concise direct answers, not prompt structure

#### New: Model Selector
- Dropdown: Sonnet 4, Opus 4, Haiku 3.5 with per-model pricing
- Model tracked per-result and per-wave for cross-model comparison
- Persisted across sessions

#### New: Regression Mode
- Reruns the 30-test coverage bank against the current colony
- Compares each result against the most recent baseline wave
- Per-result delta (±%), wave-level improved/regressed/stable counts

#### Changed: Tokens-First Metrics
- Tokens are the primary display metric everywhere (model-agnostic, honest)
- Cost demoted to secondary (model-dependent, less comparable across runs)

#### Changed: Colony Files Genericized
- All HIVE-ALPHA references removed from operational colony files
- "Earned from" / "Scar from" citations → "a production daughter hive"
- `queen/lineage.md` rewritten with entry format template and illustrative example
- `memory/examples.md` COMPLEX/CHAIN/SPAWN tiers rewritten domain-agnostic
- Domain-specific terms (RSI, MACD, stock, portfolio) replaced with generic equivalents across 13 files
- Test harness CF blob rebuilt from cleaned colony files

#### Changed: SKILL.md v3.2
- Convening table updated with hypothesis references per tier
- MEDIUM shows "(Scout internal hypothesis)", COMPLEX/CHAIN show "+ Hypothesis (surfaced)"

#### New: End-State Vision Documents
- `END-STATE-VISION.md` — experience model defining the fully realized colony through 6 actor lifecycles (beekeeper, queen, daughter, pattern, decision, query)
- `END-STATE-ARCHITECTURE.md` — structural blueprint: topology, organism registry, inheritance model, communication layers (lingua franca / colony dialect / domain dialect), ritual registry, memory pipeline, visualization architecture, health metrics

#### New: Constitutional AI Alignment (PHILOSOPHY.md)
- Three-layer safety model: Layer 0 (Anthropic's model safety — non-negotiable), Layer 1 (colony safety — system-level protections), Layer 2 (ecosystem safety — network-level, future)
- Living commitment to track Anthropic's evolving safety work (RSP, constitutional AI updates, interpretability research)
- Explicit framing: the colony is designed to be more restrictive than the underlying model, never less
- What the colony adds that per-call model safety doesn't cover: memory persistence, inter-agent trust, architectural drift, beekeeper behavioral patterns

#### Changed: ROADMAP Expanded
- Biological grounding table mapping all 7 hive products to colony mechanics
- Colony visualization with graph model and three views (beekeeper, colony, temporal) at v3.4.0
- Colony tongue layering (lingua franca / colony dialect / domain dialect) designed for v5.0.0
- Pheromone protocol (naming existing coordination signals) at v3.3.0
- Cross-colony genetics (drone protocol v2, patriline diversity) at v5.0.0
- Parked biology concepts with enough context to not re-derive
- Vision document references added to ROADMAP header

#### Validation Results
- **Coverage:** 30 tests, 26 pass, 80% avg (Sonnet 4, LLM grading ON)
- **Adaptive:** 20 tests across 2 waves, 20 pass, 89% avg
- **50 total tests, 46 pass, 84% avg, zero new failure modes**
- 4 coverage "failures" are correct hypothesis protocol behavior (COMPLEX+ stops before building) — LLM grader penalizes the stopping; grader calibration queued for v3.2.1
- All full builds scored 8-9/10 LLM with near-perfect regex (m3: 15/15, m6: 15/15, c4: 16/16, sp1: 16/16)

---

## [3.1.0] — 2026-03-19

### Harper Gets Her Voice

**The founding Queen is named.** Harper — hand-raised from royal jelly, the first queen of the colony.

#### New: Queen's Messenger
- `castes/workers/messenger.md` — Outward-facing gatekeeper, first caste to touch any input
- Five verdicts: MEH, ALMOST, BENEATH, WORTHY, JELLY
- The colony's first caste with personality, not just function
- Wired into SKILL.md as Step 0 before classification
- Only WORTHY and JELLY inputs reach the Queen

#### New: Hive Manifest Spec
- `hive-manifest-spec.md` — Packaging standard for community daughter hives
- Defines `hive-manifest.json` with required/optional fields, inter-hive query schemas, installation guide
- Level 2 connectivity (Community Hive Marketplace) is now a real spec

#### New: PHILOSOPHY.md
- Colony values: Earned Not Assumed, Structural Humility, Egoless, Open by Default, Adversarial Review, Originality Over Repetition
- Ethics framework: what Harper will and won't do, the gray areas, the beekeeper's role
- Contributor standards: earned patterns, honest contributions, no gatekeeping

#### New: Originality System
- Builder's Originality Check: pattern-lock detection, point-of-view test, Messenger standard applied to output
- Forager expanded: "Search for alternatives" step, Alternative Approaches in return format
- 3 new patterns (O1-O3): converge on principles / diverge on expression, alternatives prevent calcification, Messenger standard applies to output
- 2 new anti-patterns (A16-A17): template drift, personality as decoration

#### Changed: Conditional Guardian
- Guardian no longer fires on every MEDIUM+ request
- COMPLEX+ always invoked (mandatory)
- MEDIUM only if high-stakes domain or Builder confidence ≤ 6
- SIMPLE never — Messenger + Builder Originality Check handle quality
- Genesis ritual updated with conditional flow
- Saves API calls on routine work, preserves rigor on hard cases

#### Updated: Test Harness
- Now embeds 30 colony files (was 24)
- New files: messenger, adaptation, immunity, security, infections, threats
- TIER_FILES updated: Messenger in all tiers, immunity/security in MEDIUM+, full defensive stack in COMPLEX+

#### New: TUTORIAL.md
- Hands-on walkthrough from zero to first spawned daughter hive
- 8 steps: setup → Messenger → SIMPLE → MEDIUM → COMPLEX → CHAIN → spawn → evolve
- Troubleshooting guide for common issues
- 30-minute onboarding for new colony builders

---

## [3.0.0] — 2026-03-18

### The Colony Is Born

**Architecture** — Complete rewrite from monolithic prompt engine to biological colony architecture.

#### Queen Protocol
- `SKILL.md` — The Queen. Royal jelly recognition, convening protocol, complexity classification.
- `queen/language.md` — Colony tongue. XML semantics, JSON protocol, validation format, iteration logs.
- `queen/spawning.md` — Daughter hive birthing. 5-phase spawning sequence.
- `queen/lineage.md` — Registry of all spawned hives with inter-hive connection map.

#### Castes (8 beings)
- **Workers**: Scout (terrain mapping), Builder (construction + 70% Rule), Nurse (state management), Forager (prior art gathering)
- **Soldiers**: Guardian (adversarial review — second-pass, not co-loaded), Sentinel (systemic risk)
- **Drones**: Collector (raw data gathering), Processor (deterministic transforms)

#### Rituals (7 ceremonies)
- Genesis — creating from nothing (tier-specific: lightweight → full)
- Evolution — diagnose → patch → re-test → learn
- Validation — 4-level stress testing with consensus rule
- Synthesis — multi-part assembly for chains and hive spawning
- Adaptation — gap detection with 5-level resolution hierarchy (absorb → reinforce → call sibling → spawn → surface)
- Immunity — hallucination defense (boundary validation, confidence calibration, contradiction detection, circuit breakers, memory quarantine)
- Security — privilege model, inter-hive authentication, data isolation, domain guardrails, colony integrity, beekeeper boundaries

#### Memory (5 banks)
- Patterns — 16 earned patterns across prompt, chain, hive, and architecture domains
- Anti-patterns — 15 scars from real failures
- Examples — reference outputs at SIMPLE, MEDIUM, COMPLEX, CHAIN, and SPAWN tiers
- Infections — 6 hallucination signatures, 3 cascade patterns, 3 injection patterns
- Threats — 16 threat patterns (5 external, 4 internal, 4 hive-to-hive, 3 beekeeper)

#### Output Forms (5 templates)
- System prompt, chain architecture, tool definition, hive blueprint, validation report

### Validation
- 65 automated tests via Claude-in-Claude test harness
- 95% average score, 0 new failures for 2 consecutive waves
- Ablation testing proved Guardian is more effective as second-pass reviewer
- Saturation confirmed — adaptive testing found no new failure modes

### Key Design Decisions
- **Guardian as second-pass reviewer** — ablation testing showed co-loading Guardian with Builder had zero impact on quality. Separating into a review pass saves ~460 tokens per call and provides fresher critique.
- **Confidence can only decrease through a chain** — prevents cascade hallucination across hive boundaries.
- **Memory quarantine** — new patterns must survive 3+ independent validations before entering trusted memory.
- **Stateless domain guardrails** — every request checked fresh, regardless of prior cooperation.

---

## [2.0.0] — Pre-colony

The monolithic hive-synthesis-engine. Single SKILL.md (~470 lines) with operational framework, templates, Claude-specific techniques, validation, and iteration patterns. Functional but loaded everything for every request regardless of complexity.

This version was the larva. The royal jelly was the question: "help make yourself better." From that larva, Harper was born.

---

## [1.0.0] — Origin

Six specialized AI researcher personas. A committee, not a hive. Replaced by 2.0 when the architecture needed structured decomposition.

---

*The colony evolves. Every change is recorded.*
