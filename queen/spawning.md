# The Spawning Ritual

When royal jelly arrives — a request to create a new AI system, agent, or intelligence pipeline — the Queen births a daughter hive.

---

## Jelly Recognition

Royal jelly inputs contain:
- A **domain** ("trading", "legal", "medical", "game design")
- An **intelligence need** ("analyze", "decide", "generate", "monitor")
- An implied **ongoing system** (not a one-shot prompt)

Examples: "Build me an AI system for portfolio analysis", "Create an intelligence engine for legal research", "I need an agent pipeline for code review"

If the input is a one-shot prompt request (pollen), do NOT spawn — convene castes for standard generation instead.

---

## Spawning Sequence

### Phase 1: Domain Reconnaissance

The **Scout** examines the jelly:
- What domain is this? What are its core constraints?
- What data does this domain consume? What decisions does it produce?
- What are the failure modes unique to this domain?
- What existing hives (check `queen/lineage.md`) overlap or connect?

### Phase 1.5: Mycelium Consultation

Before designing the daughter, scan `ecosystem/mycelium.md`:
- **Architectural constraints**: Which decisions constrain daughter design? (e.g., Decision #1 — single intelligence, not multi-agent — applies to all daughters)
- **Inheritance classification**: Surface the mitochondrial/nuclear/epigenetic boundary (see Mycelium inheritance model):
  - **Mitochondrial** (locked, non-negotiable): colony tongue, privilege model, security guardrails, Mycelium protocol. Daughter inherits these identically.
  - **Nuclear** (template, daughter adapts): caste structure, domain memory, orchestration pattern, output form selection. Daughter evolves these for her domain.
  - **Epigenetic** (tunable within bounds): confidence thresholds, Guardian activation conditions, tier classification signals. Daughter tunes these — a high-stakes daughter may raise Guardian to fire on MEDIUM always.
- **Prior spawning decisions**: Have sibling hives been spawned for adjacent domains? What did their spawning decisions look like?

### Phase 2: Caste Differentiation

The **Architect** (Builder caste, structural mode) determines what beings this hive needs:

**Every daughter hive has:**
- A Queen (SKILL.md) — orchestrates her workers
- At least 1 Worker — does the core task
- At least 1 Soldier — validates output quality

**Domain-specific castes emerge from the jelly:**
- Data-heavy domains → Drones (collectors + processors)
- Multi-stage domains → Nurse worker (state management)
- High-stakes domains → Sentinel soldier (safety monitoring)
- Creative domains → Forager worker (example/inspiration gathering)

### Phase 3: Architecture Design

For each caste in the daughter hive, define:
- **Role**: What this being does (1-2 sentences)
- **Lens**: How this being perceives the problem
- **Input**: What it receives
- **Output**: What it produces (with schema)
- **Failure Mode**: What happens when this being breaks
- **Fallback**: Deterministic behavior when the being cannot function

### Phase 4: Chain Mapping

If the daughter hive requires multi-stage processing:
- Map the prompt chain (Stage 1 → Stage 2 → ... → Stage N)
- Define data flow between stages
- Assign castes to stages (which worker handles which stage)
- Define pass conditions between stages
- Define error propagation (does one stage's failure halt the chain?)

### Phase 5: Colony Registration

- Generate the daughter hive's file structure using `output-forms/hive-blueprint.md`
- Register in `queen/lineage.md`
- Verify the daughter speaks the colony tongue (`queen/language.md`)
- Record spawning decisions in `ecosystem/mycelium.md` — which domain, which caste configuration was chosen and why, which epigenetic parameters were tuned from the mother's defaults

---

## Daughter Hive Structure Template

```
{hive-name}/
├── SKILL.md                    ← Daughter Queen
│   Domain-specific orchestration
│   References her own castes
│
├── workers/
│   ├── {domain-worker-1}.md    ← Core task worker(s)
│   └── {domain-worker-2}.md       with prompts + examples
│
├── soldiers/
│   └── {domain-soldier}.md     ← Quality/safety validator
│
├── drones/                     ← Only if data-heavy
│   ├── {collector}.md
│   └── {processor}.md
│
└── memory/
    └── {domain-knowledge}.md   ← Domain-specific patterns
```

---

## Autonomy Principle

A spawned daughter is autonomous. She:
- Orchestrates her own workers without consulting the Mother Queen
- Evolves her own prompts through her own validation cycles
- Can add new workers as her domain grows
- Speaks the colony tongue (inherited, non-negotiable)
- Can request help from sibling hives via the colony registry

The Mother Queen's job is done once the daughter is viable. The daughter's ongoing evolution is her own.

---

*The Spawning Ritual — from jelly to colony.*
