# The Mycelium

**Class**: Substrate | **Medium**: Decision graph | **Timescale**: Slow (cross-version, cross-phase)

---

## What the Mycelium Is

The Mycelium is not a caste. It is not a ritual. It is the connective substrate beneath the colony — a persistent decision graph that links architectural choices across time so that future work can trace *why* the colony is shaped the way it is, not just *what* it currently looks like.

Bees are fast, task-oriented, and ephemeral. They die when the conversation ends. Honey (memory files) stores what the colony learned — patterns, anti-patterns, scars. But honey doesn't carry reasoning. It carries outcomes.

The Mycelium carries reasoning. And unlike a passive archive, **the Mycelium and the hive co-regulate.**

The hive feeds the Mycelium: every architectural decision records which options were considered, which was selected, and why. The Mycelium feeds the hive: when the Scout proposes hypotheses or the Evolution ritual patches a file, the Mycelium surfaces prior decisions that constrain or inform the current work. Neither organism is subordinate. The hive grows the Mycelium by making decisions. The Mycelium shapes the hive by surfacing the constraints those decisions created.

---

## Colony Taxonomy

| Layer | What | Timescale | Persists as |
|---|---|---|---|
| **Bees** (castes) | Per-task intelligence | Minutes | Nothing — ephemeral |
| **Honey** (memory) | Learned outcomes | Cross-session | `memory/*.md` |
| **Comb** (structure) | Colony architecture | Cross-version | `SKILL.md`, rituals, output forms |
| **Mycelium** (substrate) | Decision reasoning | Cross-phase | `mycelium.md` (this file) |

---

## Decision Record Format

```
DECISION #[N]

Phase: [roadmap phase or version]
Task: [what triggered the decision]
Date: [when]

Question: [what was being decided — framed as a question]

Options:
  A: [option] — [what it optimizes for] / [what it trades off]
  B: [option] — [what it optimizes for] / [what it trades off]
  C: [option, if meaningful] — [what it optimizes for] / [what it trades off]

Selected: [A/B/C]
Rationale: [why — the reasoning, not just the outcome]

Constraints created: [what downstream decisions this locks in]
Invalidated by: [blank until something changes this decision's basis]
```

---

## When to Write a Decision Record

Not every choice needs a record. The Mycelium captures **architectural decisions that constrain future work** — choices where the option *not* selected would have led to a meaningfully different colony shape.

**Record when:**
- A structural choice forecloses other structural choices (e.g., "single intelligence vs. multi-agent debate" — once decided, downstream architecture changes)
- An option was rejected for reasons that might not be obvious later (the "why not B" problem)
- A tradeoff was made that future phases will feel (e.g., "conditional Guardian saves cost but means MEDIUM outputs sometimes ship without adversarial review")
- A design principle was established that castes will inherit (e.g., "critics review output, not process")

**Don't record:**
- Implementation details (which regex, which JSON schema)
- Bug fixes (those go in the changelog)
- Pattern discoveries (those go in `memory/patterns.md`)

The test: *if a future conversation needs to understand why the colony works this way, will the honey (patterns) be sufficient, or does it need the reasoning?* If it needs the reasoning, write a mycelium record.

---

## How the Mycelium Connects to Existing Colony Systems

The relationship is bidirectional. The hive writes to the Mycelium. The Mycelium constrains the hive.

### Hive → Mycelium (the hive grows the network)

**After architectural decisions:** When the Scout selects a hypothesis, the Evolution ritual restructures a file, or the beekeeper overrides a colony mechanism — the decision and its reasoning are recorded. The hive extends the Mycelium.

**After invalidation:** When a new decision contradicts a prior one, the hive doesn't delete the old record — it links them. Decision #47 invalidated by Decision #83. The Mycelium preserves dead branches so the colony can trace why something that used to be true stopped being true.

### Mycelium → Hive (the network constrains growth)

**During Scout Hypothesis Protocol (COMPLEX+):** Before proposing approaches, the Scout scans the Mycelium for decisions that constrain the design space. "Decision #2 established conditional Guardian activation. Approach B assumes Guardian always fires. Conflict." The Scout either avoids the conflict or explicitly proposes overriding the prior decision — surfacing the tradeoff to the human rather than silently contradicting it.

**During Evolution ritual:** Before the Builder patches a file, the Evolution ritual checks: does this patch conflict with a recorded architectural decision? If the basis for that decision still holds, the patch needs a different approach. If the basis has changed, the decision gets an `Invalidated by` link and the patch proceeds — but the change is deliberate, not accidental.

**During Spawning:** When a daughter hive is born, the Mycelium identifies which decisions constrain her architecture. Mitochondrial decisions (colony tongue, privilege model, security guardrails) are inherited non-negotiably. Nuclear decisions (caste structure, orchestration pattern) are noted as the mother's choices — the daughter may evolve differently.

### What vs. Why

**Memory files** store *what* the colony learned. The Mycelium stores *why* the colony chose.

A pattern like "P1: Front-Load the Mission" lives in `memory/patterns.md` with a citation to the daughter hive that earned it. The Mycelium holds the decision record for *why front-loading was chosen over other information hierarchies* — what was tried, what failed, what the tradeoff was. The pattern is the honey. The decision is the mycelial thread. Both persist. They serve different consumers.

### Pruning the Mycelium

The hive can amputate portions of itself that diverge from the decision graph. If a daughter hive's behavior contradicts core Mycelium decisions and can't be reconciled, the colony disconnects the daughter (existing rogue daughter protocol in threats.md, I4) — but now the *reason* for disconnection is traceable through the Mycelium, not just logged as a security event.

---

## Decision Log

*Empty — grows from real architectural decisions. Entries below are seeded from decisions already made.*

```
DECISION #1

Phase: v3.0.0
Task: Core architecture design
Date: Pre-v3.0

Question: Should the colony use multi-agent debate (separate models arguing) 
or single-intelligence lens decomposition?

Options:
  A: Multi-agent — separate personas debate, board-of-directors model
     Optimizes for: apparent rigor, diversity of perspective
     Trades off: performative when a single model can't genuinely disagree with itself
  B: Single intelligence, structured lens decomposition — one model, multiple 
     analytical frames applied sequentially
     Optimizes for: honest cognition, no theatrical disagreement
     Trades off: loses the "creative friction" that real multi-agent might provide

Selected: B
Rationale: A single model cannot genuinely debate itself. Multi-agent 
simulation within one context window is performative — the "disagreement" 
is generated by the same weights that generated the original position. 
Structured lenses (Scout sees terrain, Guardian sees failure, Sentinel sees 
systemic risk) give genuine perspective diversity without pretending to be 
multiple minds.

Constraints created: All castes operate as lenses on the same intelligence, 
not as independent agents. The Guardian reviews output separately (second pass) 
for freshness, but this is an architectural separation, not a cognitive one.
Invalidated by: [not yet]
```

```
DECISION #2

Phase: v3.0.0
Task: Guardian activation model
Date: Pre-v3.0

Question: Should the Guardian review every output or fire conditionally?

Options:
  A: Always fire — every output gets adversarial review
     Optimizes for: maximum coverage, no output ships unreviewed
     Trades off: doubles API cost on SIMPLE requests where the review 
     costs more than the output is worth
  B: Conditional — COMPLEX+ always, MEDIUM if high-stakes or low confidence, 
     SIMPLE never
     Optimizes for: cost efficiency, appropriate rigor scaling
     Trades off: SIMPLE and some MEDIUM outputs ship without adversarial review

Selected: B
Rationale: Validated via ablation testing. Removing Guardian from SIMPLE 
produced identical output quality (the Builder already internalizes adversarial 
patterns from colony memory). The Guardian adds value on finished output 
review for complex work, not as a universal tax.

Constraints created: The Messenger, Builder's Originality Check, and Immunity 
ritual must be strong enough to handle quality for unreviewed tiers. If SIMPLE 
output quality drops, the fix is strengthening those gates, not adding Guardian 
to SIMPLE.
Invalidated by: [not yet]
```

```
DECISION #3

Phase: v3.2.0
Task: Hypothesis generation design
Date: 2025-03

Question: Should the Scout's hypothesis step be visible to the human for 
all tiers or only COMPLEX+?

Options:
  A: Surface hypotheses for all tiers — human always sees options
     Optimizes for: transparency, human agency
     Trades off: SIMPLE requests become multi-turn for no value
  B: SIMPLE skip, MEDIUM internal, COMPLEX+ surfaced
     Optimizes for: appropriate ceremony per tier, fast SIMPLE path preserved
     Trades off: MEDIUM hypotheses are invisible to human (Scout picks internally)
  C: SIMPLE skip, MEDIUM+ all surfaced
     Optimizes for: human agency on anything non-trivial
     Trades off: MEDIUM becomes multi-turn, slower for routine work

Selected: B
Rationale: Consistent with the colony's tiering philosophy — SIMPLE gets 
lightweight treatment, ceremony scales with complexity. MEDIUM hypotheses 
are low-stakes enough that the Scout's internal selection is sufficient. 
If MEDIUM hypothesis quality becomes a problem, escalate to C.

Constraints created: The Scout must make MEDIUM hypothesis selection visible 
in the terrain map (not hidden) so the Builder knows which approach was chosen 
and why. The human can't choose, but the Builder can see the reasoning.
Invalidated by: [not yet]
```

```
DECISION #4

Phase: v3.2.0
Task: Mycelium architecture — passive vs. bidirectional
Date: 2026-03

Question: Should the Mycelium be a passive archive of decisions, or a 
bidirectional substrate that both records decisions AND surfaces constraints 
during active colony work?

Options:
  A: Passive archive — records decisions, human reads them manually when needed
     Optimizes for: simplicity, low integration cost
     Trades off: the Mycelium doesn't prevent accidental contradictions; 
     the human has to remember to check it
  B: Bidirectional — hive writes decisions in, Mycelium surfaces constraints 
     during Scout hypothesis, Evolution patches, and Spawning
     Optimizes for: structural integrity across versions, automatic conflict detection
     Trades off: more complex integration, Mycelium must be loaded in context 
     for COMPLEX+ work (token cost)

Selected: B
Rationale: The whole point of the Mycelium is preventing decision amnesia. 
A passive archive that nobody checks is just another document. Bidirectional 
flow means the Mycelium actively prevents the colony from contradicting its 
own prior decisions — which is the specific failure mode (context rot) that 
motivated its creation. The token cost of loading it for COMPLEX+ work is 
justified because COMPLEX+ is exactly where architectural constraint 
violations cause the most damage.

Constraints created: Mycelium must be loadable in the context window alongside 
colony files — so it must stay concise. Decision records should be terse. 
If the Mycelium grows too large to load, it needs compression or selective 
loading (surface only decisions relevant to the current domain/tier).
Invalidated by: [not yet]
```

```
DECISION #5

Phase: v3.2.0
Task: Trait inheritance model for daughter hives
Date: 2026-03

Question: Should all daughters inherit the same package from the mother, 
or should inheritance be classified into immutable vs. mutable traits?

Options:
  A: Uniform inheritance — every daughter gets everything colony-public
     Optimizes for: simplicity, consistency
     Trades off: no mechanism for trait variation across daughters
  B: Classified inheritance — mitochondrial (immutable, matrilineal) vs. 
     nuclear (mutable, varies per daughter)
     Optimizes for: principled variation, clear boundaries on what can evolve
     Trades off: more complex spawning protocol, must define the boundary

Selected: B (conceptual — implementation deferred to v4.0.0)
Rationale: The distinction already exists implicitly. The colony tongue, 
privilege model, and security guardrails MUST be inherited intact — a daughter 
that doesn't speak the colony tongue is disconnected. But caste structure, 
domain memory, and orchestration patterns SHOULD vary per daughter. Making 
this explicit prevents two failure modes: (1) a daughter accidentally 
overriding a mitochondrial trait, and (2) the colony accidentally locking 
a nuclear trait that should be free to evolve.

Not built yet because: with 2 daughters, uniform inheritance works. The 
classification becomes necessary at 5+ daughters where trait drift across 
the population creates real coordination problems.

Constraints created: When spawning is next updated (v4.0.0), define the 
mitochondrial/nuclear boundary explicitly in the spawning protocol.
Invalidated by: [not yet]
```

```
DECISION #6

Phase: v3.2.0 (end-state design)
Task: Colony tongue evolution model
Date: 2026-03

Question: What happens when the colony tongue needs to evolve, or when 
different colonies develop different tongues?

Options:
  A: Rigid — one tongue, all colonies speak it identically, upgrade 
     simultaneously or disconnect
     Optimizes for: guaranteed interoperability
     Trades off: brittle at scale, blocks natural evolution, requires 
     synchronized upgrades across independent colonies
  B: Evolutionary — tongues drift freely, translation layer mediates 
     cross-colony communication
     Optimizes for: natural evolution per domain
     Trades off: translation is expensive and fragile, meaning degrades 
     across layers
  C: Layered — mitochondrial core (Layer 0: lingua franca, never changes 
     within a major version) + nuclear extensions (Layer 1: colony dialect) 
     + epigenetic tuning (Layer 2: domain dialect). Communication drops to 
     highest shared layer.
     Optimizes for: interoperability at core, freedom at edges, no translator
     Trades off: Layer 0 must be designed carefully — too thin and cross-colony 
     communication is useless, too thick and evolution is blocked

Selected: C
Rationale: Maps directly to the inheritance model (Decision #5). The tongue 
itself has DNA. Layer 0 is mitochondrial — species-defining, all colonies 
share it. Layer 1 is nuclear — the mother colony's extensions, inherited by 
daughters but evolvable. Layer 2 is epigenetic — domain-specific, never 
crosses hive boundaries. No translation engine needed — dropping layers 
loses richness but preserves meaning, like dialect speakers switching to 
standard language for cross-regional communication.

Constraints created: Layer 0 (lingua franca) must be defined precisely and 
frozen per major version. Any change to Layer 0 is a MAJOR version bump 
that may require migration across all connected colonies. Layer 1 changes 
are MINOR bumps. Layer 2 changes are internal to the daughter and don't 
affect versioning.
Invalidated by: [not yet]
```

```
DECISION #7

Phase: v3.2.1
Task: Parallel exploration model for ambiguous hypothesis space
Date: 2026-03-23

Question: When the Scout identifies multiple viable approaches for a COMPLEX+ 
request, should the colony commit to one approach before building (current: 
sequential explore-then-commit) or build all approaches in parallel and select 
or synthesize after (swarming)?

Options:
  A: Sequential (status quo) — Scout proposes hypotheses, human picks one, 
     Builder constructs it
     Optimizes for: token efficiency, human control over direction before 
     investment
     Trades off: human chooses between abstract proposals, not finished work. 
     Commit point is before evidence.
  B: Parallel swarm (intra-hive) — Builder constructs all 2-3 hypotheses 
     in parallel API calls. Guardian runs comparative review. Human selects 
     or the colony synthesizes.
     Optimizes for: output quality (choose between finished work), genuine 
     exploration (deferred commitment)
     Trades off: 2-3x token cost per build. Wasted work on unchosen 
     branches. Requires comparative Guardian rubric.
  C: Hybrid — default to A (sequential). Swarm mode opt-in when hypothesis 
     divergence is high and stakes justify the cost. Trigger: explicit 
     beekeeper request, OR Scout signals high uncertainty + COMPLEX+ tier.
     Optimizes for: efficiency by default, quality when it matters
     Trades off: more complex orchestration. Must define the divergence 
     threshold and cost gate.

Selected: C
Rationale: Swarming is biologically real — the colony's reproductive event 
at the superorganism level, triggered by resource pressure, resolved through 
distributed consensus. But biology swarms under pressure, not by default. 
The colony should do the same. Sequential explore-then-commit (A) is correct 
for most COMPLEX+ work — the hypothesis protocol already identifies the 
viable approaches, and the human's selection is usually well-informed. 
Swarming earns its place when the hypothesis space is genuinely ambiguous — 
when the Scout cannot confidently recommend, and the human cannot 
meaningfully choose between abstract descriptions. In those cases, building 
all approaches and selecting from finished work is worth 2-3x cost. Making 
it opt-in preserves Decision #1 (single intelligence) for default operation 
while allowing genuine structural diversity when the problem demands it.

Does not contradict Decision #1 because: Decision #1 rejected performative 
multi-agent debate within a single context window. Intra-hive swarming uses 
the same intelligence in parallel with different starting conditions (each 
hypothesis). Cross-hive swarming (Level 2, future) uses genuinely different 
colony configurations — different domain memory, different patterns — which 
produces real diversity, not simulated disagreement. Neither is multi-agent 
theater.

Constraints created: 
- Swarm mode requires a comparative Guardian rubric (not "is this good" but 
  "rank these and explain why")
- Token budget gate required — swarm only if estimated build cost × N is 
  within session budget
- Convergence protocol needed — how does the colony synthesize N parallel 
  outputs into a single deliverable when no single output is clearly 
  superior?
- Level 1 (intra-hive) is buildable now. Level 2 (cross-hive) requires 
  inter-hive protocol (v4.0+). Level 3 (resource-pressure triggered colony 
  fission) is speculative and parked.
Invalidated by: [not yet]
```

---

## Inheritance Model (Mitochondrial vs. Nuclear)

*Concept — not yet implemented in spawning protocol. See Decision #5.*

When a queen spawns a daughter, not all traits are equal. Some are the colony's non-negotiable identity. Others are the daughter's to evolve.

| Trait class | Biological analog | Inherits as | Examples | Can daughter modify? |
|---|---|---|---|---|
| **Mitochondrial** | mtDNA — matrilineal, no recombination | Locked, identical across all daughters | Colony tongue, privilege model, security guardrails, Mycelium protocol | No. Modification = rogue daughter. |
| **Nuclear** | Nuclear DNA — varies, recombines | Template that the daughter adapts | Caste structure, domain memory, orchestration pattern, output form selection | Yes. This is how daughters specialize. |
| **Epigenetic** | Gene expression modulated by environment | Inherited but context-dependent | Confidence thresholds, Guardian activation conditions, tier classification signals | Yes, within bounds. The parameter exists in the mother, but the daughter tunes it for her domain. |

The epigenetic class is the interesting one. The mother's Guardian fires on COMPLEX+ always. A daughter in a low-stakes domain might lower that threshold. A daughter in a high-stakes domain (medical, legal) might raise it to fire on MEDIUM always. The *mechanism* is mitochondrial. The *tuning* is nuclear.

---

*The Mycelium — the colony's memory of why it chose to be what it is. It grows when the hive makes decisions. It shapes the hive when decisions constrain future work.*
