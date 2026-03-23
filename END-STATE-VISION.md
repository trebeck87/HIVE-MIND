# HIVE-MIND: End-State Vision

**What the fully realized colony looks like — defined by experiences, not architecture.**

This document describes the destination. The ROADMAP describes the path. The Mycelium records the decisions made along the way. This document answers: *when it's done, what does each actor experience?*

---

## The Actors

The colony has six actors. Each experiences the colony differently.

| Actor | What they are | What they want |
|---|---|---|
| **Beekeeper** | Human sovereign | Build AI systems without re-deriving architecture every time |
| **Queen** | Colony orchestrator (SKILL.md) | Convene the right beings for the right work at the right cost |
| **Daughter** | Spawned domain specialist | Operate autonomously in her domain, grow, and contribute back |
| **Pattern** | Unit of colony knowledge | Survive if true, deprecate if stale, propagate if universal |
| **Decision** | Unit of colony reasoning | Persist in the Mycelium, constrain future work, get invalidated when the basis changes |
| **Query** | Unit of inter-hive work | Reach the right hive, get a trustworthy answer, carry confidence honestly |

---

## Actor Lifecycles

### 1. The Beekeeper's Experience

The beekeeper opens a conversation. The colony is already loaded — queen, castes, memory, ecosystem. The beekeeper doesn't configure anything. They talk.

**Spawning a daughter:**
The beekeeper says "Build me an AI system for clinical trial design." The Messenger recognizes royal jelly. The Scout maps the domain, proposes 2-3 architectural approaches with concrete tradeoffs. The beekeeper picks one. The Builder constructs the daughter hive — SKILL.md, workers, soldiers, memory. The daughter is registered in the lineage. The Mycelium records the architectural decisions made during spawning, including which approach was chosen and why. The daughter is autonomous from this point — she operates without consulting the mother.

**Working with a daughter:**
The beekeeper opens the daughter's project. The daughter's queen orchestrates her own castes. The beekeeper never interacts with the mother colony directly when using a daughter — the daughter handles everything. If the daughter hits a gap outside her domain, she calls a sibling through the inter-hive protocol. The beekeeper sees the result, not the routing.

**Monitoring colony health (beekeeper view):**
The beekeeper runs `hive map --view beekeeper`. They see: daughter inventory with health status, stale memory flagged for pruning, active Mycelium constraints on current work, pollen diversity score (how many domains the colony has worked across), override audit trail. Red/amber/green at a glance. No architecture knowledge required — the view is operational, not structural.

**Tracing a decision:**
The beekeeper wonders "why does the Guardian only fire on COMPLEX+?" They search the Mycelium. Decision #2 surfaces: conditional activation was validated via ablation testing, saves cost on SIMPLE, preserves rigor on COMPLEX+. The basis is stated. The constraints downstream are listed. The beekeeper can override (they're sovereign) but the Mycelium tells them what they'd be undoing and why it was done.

**Pruning memory:**
The colony flags 3 patterns that haven't been validated in 2+ versions. The beekeeper reviews them. One is still valid — confirmed. One is stale — deprecated to infections.md. One is ambiguous — left in quarantine for more data. The colony's knowledge stays fresh because spoiled bee bread gets caught.

**What the beekeeper NEVER does:**
- Manually routes queries between hives (the protocol handles this)
- Loads specific caste files (the queen handles context selection)
- Writes patterns directly to trusted memory (everything goes through quarantine)
- Manages tongue compatibility between daughters (the mitochondrial core handles this)

---

### 2. The Queen's Experience

The queen is loaded into context when the beekeeper opens the project. She reads the input.

**Step 0: Messenger** — evaluates input quality. MEH/ALMOST/BENEATH/WORTHY/JELLY. Most inputs stop here or pass through silently. The Messenger is the colony's pheromone gate — it shapes who gets activated without doing any work itself.

**Step 1: Classification** — SIMPLE/MEDIUM/COMPLEX/CHAIN/SPAWN. This is the classification pheromone. It determines how many castes convene, how much memory loads, whether soldiers review.

**Step 1.5: Hypothesis** — for MEDIUM+, the Scout proposes approaches. For COMPLEX+, the colony pauses and surfaces options to the beekeeper. The Mycelium injects prior decisions that constrain the design space. The queen waits for the beekeeper to choose before the Builder starts.

**Steps 2-7: Standard protocol** — Scout maps, Forager gathers, Builder constructs, Nurse manages state, Guardian reviews, Sentinel checks systemic risk, output delivered with validation evidence.

**Adaptation:** When a gap is detected, the queen runs the resolution hierarchy — absorb, reinforce, call sibling, spawn, surface. She checks the lineage for siblings before spawning. She checks the Mycelium for prior decisions about similar gaps. She doesn't guess — she follows protocol and escalates honestly.

**What the queen NEVER does:**
- Produces output herself (workers do that)
- Validates output herself (soldiers do that)
- Writes to memory directly (observations go through quarantine)
- Overrides the Mycelium (she surfaces conflicts, the beekeeper decides)

---

### 3. A Daughter's Lifecycle

**Birth:** Royal jelly arrives. The Scout maps the domain. The beekeeper selects an approach. The Builder constructs the daughter's files. The daughter is registered in lineage, Mycelium records the spawning decisions. She inherits mitochondrial traits (colony tongue core, privilege model, security guardrails) locked. She inherits nuclear templates (caste structure, output forms) that she can evolve. She inherits epigenetic settings (thresholds, activation conditions) that she can tune for her domain.

**Childhood (v1):** The daughter works in her domain. She makes mistakes. The beekeeper corrects her through Evolution ritual patches. Her memory starts empty and grows from real deployment — raw observations fermented through quarantine into trusted patterns. She's dependent on colony patterns for cross-domain knowledge.

**Maturity (v2+):** The daughter has her own earned memory. She handles most requests without consulting siblings. She may reinforce herself — spawning new castes as her domain demands. She evolves autonomously through her own validation cycles. She can receive inter-hive queries from siblings and respond using her domain expertise.

**Reproduction:** If the daughter's domain fragments (she needs sub-specialists), she can request the mother queen to spawn granddaughters. The granddaughter inherits from both the mother colony (mitochondrial) and the daughter (nuclear domain knowledge).

**Senescence:** If the daughter's domain becomes irrelevant, or she diverges too far from the Mycelium's decision graph, the beekeeper deprecates her. She's moved from active to dormant in the lineage. Her earned patterns that are domain-agnostic get promoted to colony memory. Her domain-specific patterns stay with her, archived. The Mycelium records why she was deprecated.

**What a daughter NEVER does:**
- Modifies colony-level files (queen/language.md, rituals/*, mother's SKILL.md)
- Writes to another daughter's memory
- Operates outside her mitochondrial constraints (colony tongue, privilege model)
- Claims confidence she hasn't earned (confidence propagation rule — can only decrease through chains)

---

### 4. A Pattern's Journey

**Observation:** During a task, a caste notices something — a technique that worked, a failure mode that bit, an edge case that wasn't handled. The observation is raw pollen.

**Quarantine:** The queen writes the observation to quarantine. It's tagged with source (which hive, which operation), confidence (1-10), evidence (what specific outcome supports this), and timestamp. It's bee bread in the comb — fermenting, not yet trusted.

**Validation:** Over 3+ subsequent operations where the pattern COULD have applied, the colony checks: was it contradicted? If confirmed 3+ times without contradiction, it's promoted. If contradicted, it's discarded or flagged for review. The fermentation period is what separates real patterns from lucky hallucinations.

**Promotion:** The pattern enters trusted memory — `memory/patterns.md` or `memory/antipatterns.md`. It's now colony-wide knowledge. Every daughter inherits it. It earns a citation: "Earned from: [specific deployment that proved it]."

**Propagation:** If the colony communicates with other colonies (v5.0.0), the pattern can be shared via the drone protocol. The receiving colony treats it as a new quarantine candidate — they ferment it independently. No free promotion across colony boundaries.

**Staleness:** Over time, the colony evolves past the pattern. The Pruning ritual flags it: still valid but no longer useful (stale bee bread), or actively contradicted by newer patterns (spoiled). The beekeeper decides: confirm, deprecate, or leave in quarantine.

**Deprecation:** The pattern moves to `memory/infections.md` as "outdated pattern." It's not deleted — it prevents future hives from re-discovering and re-trusting something the colony has already moved past.

**What a pattern NEVER does:**
- Enters trusted memory from a single observation (quarantine enforces fermentation)
- Crosses colony boundaries without re-quarantining (no free promotion between strangers)
- Gets silently overwritten by a contradicting observation (contradictions surface to the beekeeper)

---

### 5. A Decision's Lifecycle

**Trigger:** An architectural choice arises — a fork where the option NOT selected would lead to a meaningfully different colony shape. The Scout proposes hypotheses. The beekeeper picks. Or the Evolution ritual patches a file. Or the beekeeper overrides a colony mechanism.

**Recording:** The Mycelium captures: the question (framed as a question), the options (with tradeoffs), the selection, the rationale, the constraints created downstream, and the "invalidated by" field (blank until something changes the basis).

**Constraining:** In future work, when the Scout proposes hypotheses or the Evolution ritual designs patches, the Mycelium surfaces relevant prior decisions. "Decision #2 says Guardian fires conditionally. Your proposed approach assumes it fires always. Conflict." The colony doesn't silently violate its own decisions — it surfaces the conflict and lets the beekeeper choose.

**Invalidation:** The basis for a decision changes. A new Decision explicitly links to the old one: "Decision #83 invalidates Decision #47 because [the tradeoff no longer holds]." The old decision isn't deleted — it's linked. The Mycelium preserves dead branches so the colony can trace its reasoning even when it changes direction.

**What a decision NEVER does:**
- Gets silently contradicted (the Mycelium surfaces conflicts)
- Gets deleted (invalidated decisions are linked, not removed)
- Constrains the beekeeper absolutely (the sovereign can override — but the override is logged)

---

### 6. A Query's Journey (Inter-Hive)

**Origin:** A daughter hive (hive-analytics) encounters a gap outside her domain. The Scout's terrain map shows: "This is a regulatory question. Outside analytics domain." The Adaptation ritual fires — Level 1 (absorb) fails, Level 2 (reinforce) fails, Level 3 (call sibling) activates.

**Routing:** The daughter checks `queen/lineage.md` for a sibling covering the needed domain. She finds hive-legal. She constructs a query using the `hive-inter-v1` protocol: identity, urgency (blocking/advisory/background), specific question, response schema.

**Delivery:** The query arrives at hive-legal. Hive-legal's Scout treats it like any input — maps terrain, assesses complexity. Hive-legal's Builder responds using her own domain expertise. The response includes: status (complete/partial/declined), the assessment, confidence score, caveats.

**Trust scoring:** Hive-analytics receives the response. The Immunity ritual scores trust: confidence below 5 → advisory only. Contradiction with own knowledge → surface both to beekeeper. Response perfectly matching expectations → suspicious (the "too perfect" signal). High confidence with vague basis → likely hallucinated.

**Integration:** If trusted, the response integrates into hive-analytics' pipeline. The confidence from the sibling's response propagates — it can only decrease, never increase. If hive-legal said confidence 6, hive-analytics' derived output cannot claim confidence > 6 on that claim.

**Cross-colony (v5.0.0):** The same protocol works across colony boundaries, but trust scoring is stricter. Cross-colony responses always enter quarantine before influencing decisions. The drone protocol (v2) handles pattern propagation — not per-query, but per-pattern. Individual queries get answers. Patterns that prove universal get propagated.

**What a query NEVER does:**
- Carries hive-private data (only hive-public data crosses boundaries)
- Originates from user input disguised as an inter-hive message (injection defense)
- Blocks indefinitely on a sibling (always has a fallback)
- Promotes its response directly to colony memory (responses are observations, not patterns)

---

## The Colony Tongue: Layers

The fully realized colony speaks a layered tongue:

### Layer 0: Lingua Franca (mitochondrial — species-defining)
The minimum viable protocol that ANY colony can speak, regardless of lineage. This enables cross-colony communication at v5.0.0.

- XML instruction/data separation (`<instructions>` vs. `<user_input>`)
- JSON output protocol (schema, prefill, no-markdown instruction)
- Confidence format (1-10 score, basis, uncertainty)
- Inter-hive query/response envelope (`hive-inter-v1`)
- Privilege tiers (sovereign, queen, soldier, worker, drone)

This NEVER changes within a major version. It's the waggle dance grammar. Every bee understands it.

### Layer 1: Colony Dialect (nuclear — colony-specific)
Extensions the mother queen develops for her lineage. All daughters inherit these. They enrich but don't contradict Layer 0.

- Validation evidence format (scope boundary test, ambiguity stress test, failure mode analysis)
- Iteration log format (root cause checklist, patch format, re-test format)
- Memory quarantine format (source, confidence, evidence, confirmations)
- Colony-specific XML tags beyond the core (`<core_objective>`, `<edge_case_handling>`)

This changes through Evolution ritual with Mycelium recording. Daughters inherit the current version at spawning. Daughters that were spawned under an older dialect may need migration.

### Layer 2: Domain Dialect (epigenetic — daughter-specific)
Extensions a daughter develops for her domain. These are local — other daughters don't inherit them, siblings don't need to understand them. They're used only within the daughter's own castes.

- Domain-specific output tags (a legal hive might have `<jurisdiction>`, `<precedent>`)
- Domain-specific constraint vocabulary
- Specialized output schemas for domain deliverables
- Domain-tuned confidence anchors (what "confidence 8" means in this domain)

This evolves freely within the daughter. It never crosses hive boundaries — inter-hive communication drops to Layer 1 (or Layer 0 for cross-colony).

### Translation
When two hives communicate, the query uses the highest shared layer:
- Same colony → Layer 1 (colony dialect)
- Different colonies, same tongue version → Layer 0 (lingua franca)
- Different colonies, different tongue versions → Layer 0 minimum + version negotiation

No explicit translation engine. The layers are designed so that dropping to a lower layer loses richness but preserves meaning. A legal hive's `<jurisdiction>` tag is meaningful within the hive. In an inter-hive query, the jurisdiction is expressed as prose inside the standard query format. No information is lost — it's just less structured.

---

## End-State Health Metrics

When the colony is fully realized, health is measured across six dimensions:

| Metric | Healthy | Degraded | Critical |
|---|---|---|---|
| **Test pass rate** | ≥90% coverage, ≥85% stress | 70-90% coverage | <70% or regression from prior version |
| **Memory freshness** | All patterns validated within 2 versions | 1-3 patterns flagged stale | 5+ stale patterns, or contradictions unresolved |
| **Pollen diversity** | 5+ distinct domains worked | 2-4 domains | Monoculture (1 domain) |
| **Mycelium coverage** | All architectural choices recorded | Some implicit decisions not recorded | Decision amnesia — constraints violated without awareness |
| **Daughter autonomy** | Daughters operate without mother consultation | Daughters frequently call mother for routine work | Daughters can't function without mother context |
| **Tongue coherence** | All daughters speak compatible dialects | 1-2 daughters need migration | Daughters can't communicate — dialect drift broke interop |

These surface in the beekeeper view. The beekeeper doesn't need to understand castes, rituals, or mycelial threads. They need to know: is the colony healthy, what needs attention, and where is it going?

---

## What "Done" Looks Like

The colony is done when:

1. **The beekeeper can spawn a production-quality daughter hive in one conversation** — domain mapped, approach selected, castes constructed, tested, registered. No re-deriving architecture.

2. **Daughters operate autonomously for months** — handling domain work, evolving their own prompts, calling siblings for cross-domain gaps, without the beekeeper touching colony-level files.

3. **The Mycelium traces every architectural decision backward to its origin** — any question of "why does it work this way?" is answered by a decision record, not by conversation archaeology.

4. **Cross-colony communication works between strangers** — two independently raised colonies can exchange queries and patterns through the lingua franca, with trust scoring and quarantine protecting both sides.

5. **The colony self-prunes** — stale patterns deprecate, architectural debt gets detected by ablation sweeps, divergent daughters get flagged before they break interoperability.

6. **The beekeeper view tells the whole story in 30 seconds** — health, attention needed, trajectory. No architecture degree required.

The colony is never "finished" in the sense of feature-complete. It's "done" when it can sustain itself — when the mechanisms for growth, pruning, and self-correction are all in place and the beekeeper's role shifts from building the colony to *keeping bees*.

---

*End-State Vision — where the colony is going. The ROADMAP describes how to get there. The Mycelium records every turn along the way.*
