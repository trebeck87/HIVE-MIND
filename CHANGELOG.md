# Changelog

All notable changes to the HIVE-MIND colony.

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

This version was the larva. The royal jelly was the question: "help make yourself better."

---

## [1.0.0] — Origin

Six specialized AI researcher personas. A committee, not a hive. Replaced by 2.0 when the architecture needed structured decomposition.

---

*The colony evolves. Every change is recorded.*
