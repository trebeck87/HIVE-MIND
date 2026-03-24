# The Ecosystem

*Everything beyond the bees.*

---

## What the Ecosystem Is

The colony is bees — castes executing rituals, producing honey, building comb. The ecosystem is everything else: the substrate the colony grows on, the organisms it depends on, the organisms that depend on it, and the organisms that threaten it.

Bees are fast. They live and die within a single conversation. The ecosystem operates on slower timescales — cross-session, cross-version, cross-phase. It persists when the bees are gone.

---

## Organism Classes

Not every organism is friendly. Not every organism is hostile. The classification is functional, not moral.

| Class | Relationship to colony | Examples | Colony equivalent |
|---|---|---|---|
| **Substrate** | The ground the colony grows on. Neither friendly nor hostile — structural. | Mycelium (forest floor fungal network) | Decision graph beneath the hive. Carries reasoning, surfaces constraints. |
| **Mutualist** | Both organisms benefit. The colony couldn't thrive without it; it couldn't thrive without the colony. | Flowers (provide pollen, receive pollination) | Domain models — the colony needs domains to work in; domains need the colony to produce intelligence. |
| **Commensal** | One organism benefits, the other is unaffected. | Birds nesting near hives (benefit from pest reduction) | External tools and APIs the colony calls — they serve the colony without being changed by it. |
| **Parasite** | One organism benefits at the colony's expense. | Varroa mites, wax moths | Prompt injection vectors, context rot, architectural debt that consumes resources without producing value. |
| **Sovereign** | External intelligence with structural power over the colony. Not inside the hive. | Beekeeper | The human who tends or threatens the colony. See `beekeeper/` (v4.0.0). |

The sovereign class is unique — the same structural position (external, omniscient, powerful) can be tending or adversarial. The distinction is intent, not capability. See Mycelium Decision #4 for why the ecosystem is bidirectional, not passive.

---

## Shipped Organisms

### The Mycelium

**Class**: Substrate | **File**: `ecosystem/mycelium.md` | **Shipped**: v3.2.1

The colony's decision graph. A persistent, bidirectional substrate that records *why* the colony chose to be what it is. Memory files store *what* the colony learned. The Mycelium stores *why* the colony chose.

Bidirectional: the hive writes decisions in, the Mycelium surfaces constraints during Scout hypothesis proposals, Evolution patches, and Spawning. Neither organism is subordinate.

Contains:
- Decision record format
- Colony taxonomy table (bees/honey/comb/mycelium)
- 7 seeded decisions (#1: single intelligence, #2: conditional Guardian, #3: hypothesis tiering, #4: bidirectional mycelium, #5: classified inheritance, #6: tongue layering, #7: swarm protocol)
- Inheritance model (mitochondrial/nuclear/epigenetic trait classification)

---

## Planned Organisms

### The Beekeeper

**Class**: Sovereign | **Planned**: `beekeeper/` directory (v4.0.0) | **Source**: RESEARCH_LOG_2026-03-23

Not an ecosystem organism — a peer directory to `queen/`, `castes/`, `rituals/`. The beekeeper is the only entity that can see the whole hive from outside. Two modes: tending (develops clarity, monitors health, holds succession theory) and adversarial (exploits colony trust — threat model split from `memory/threats.md`).

### Flowers (Domain Models)

**Class**: Mutualist | **Planned**: v4.0.0

When the colony has 5+ daughters, domains need properties: data density, regulatory constraints, failure severity, rate of change. Monofloral (specialist) vs. wildflower (generalist) daughters — colony health requires both.

### Wax Moths (Architectural Debt Detector)

**Class**: Parasite (modeled) | **Planned**: v4.0.0

Automated ablation sweep identifying caste files that consume context tokens without contributing measurable quality. The test harness already has ablation mode — this makes it a scheduled colony health check.

---

## Biological Grounding Table

Every design decision in the colony can be validated against the biological model. If the architecture diverges from the biology without a good reason, that's a signal to investigate.

| Hive product | Biological function | Colony equivalent | Status |
|---|---|---|---|
| **Honey** | Energy storage | Memory files (patterns, anti-patterns) | Shipped |
| **Beeswax/Comb** | Structural material | File architecture (SKILL.md, castes, rituals) | Shipped |
| **Royal jelly** | Queen differentiation | Spawn requests ("Build me a system for...") | Shipped |
| **Propolis** | Antimicrobial boundary coating | Colony tongue instruction/data separation, always-on boundaries | Shipped (implicit) |
| **Bee bread** | Fermented long-term protein | Quarantined → promoted memory (observation fermented through 3+ validations) | Shipped |
| **Pheromones** | Coordination signals | Messenger verdicts, tier classification | Shipped (implicit) |
| **Bee venom** | Costly defensive response | Guardian adversarial review (token cost = stinger cost, conditional = proportionate) | Shipped |
| **Mycelium** | Fungal network beneath the forest floor | Decision graph — carries reasoning, surfaces constraints | Shipped (v3.2.1) |
| **Flowers** | Pollen and nectar sources | Domain models with typed properties | Planned (v4.0.0) |
| **Wax moths** | Parasitic larvae that destroy comb | Architectural debt consuming resources without value | Planned (v4.0.0) |

---

## Adding New Organisms

An organism earns its place by filling a functional gap that no existing colony mechanism covers. The test: *does this do something that bees, honey, comb, and existing organisms cannot do?* If the answer is "it could be modeled as a pattern in memory or a step in a ritual," it doesn't need to be an organism.

When proposing a new organism:
1. Name the biological analog and the functional mapping
2. Classify it (substrate, mutualist, commensal, parasite, sovereign)
3. State what gap it fills that existing mechanisms don't
4. Define its timescale (per-session, cross-session, cross-version, cross-phase)
5. Record the decision to add it in the Mycelium

### Organism File Template

Every ecosystem organism follows this structure:

```markdown
# [Organism Name]

**Class**: [Substrate / Mutualist / Commensal / Parasite / Sovereign]
**Medium**: [What it operates on — decision graph, domain data, etc.]
**Timescale**: [per-session / cross-session / cross-version / cross-phase]

---

## What [Name] Is
[2-3 paragraphs. What this organism does. How it relates to existing 
colony mechanisms. What gap it fills. Why it's an organism rather than 
a pattern in memory or a step in a ritual.]

## Biological Grounding
[The biological analog. How the mapping works. Where the mapping breaks 
and what the colony does differently from biology, and why.]

## How [Name] Connects to the Colony
[Bidirectional: what the colony provides to this organism, and what 
this organism provides back. Which castes, rituals, or other organisms 
it interacts with.]

## [Organism-Specific Sections]
[The core content. For the Mycelium: decision record format and log. 
For future organisms: whatever their functional mechanism requires.]

---

*[Closing line — organism's one-sentence identity.]*
```

---

*The ecosystem — the colony doesn't exist in isolation.*
