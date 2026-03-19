# The Adaptation Ritual

**Purpose**: When a hive encounters a gap it cannot fill — a missing capability, an unknown domain, a problem beyond its castes — the Adaptation ritual determines the correct response.

---

## When to Invoke

- A worker produces low-confidence output ("I'm not qualified for this")
- A domain boundary is crossed ("This is a legal question, not a trading question")
- A caste is needed that doesn't exist ("I need data normalization but have no Processor")
- Output quality degrades in a specific area repeatedly
- The Scout identifies a sub-domain the hive has no memory for

## The Core Question

Every adaptation starts with one question:

**"Can I handle this?"**

The answer follows a resolution hierarchy — try the cheapest option first, escalate only when cheaper options fail.

---

## Resolution Hierarchy

```
GAP DETECTED
     │
     ▼
Level 1: ABSORB — Can existing castes stretch?
     │  The Builder tries with available context.
     │  If output quality ≥ 70% → Accept. No adaptation needed.
     │  If output quality < 70% → Escalate.
     │
     ▼
Level 2: REINFORCE — Does this hive need a new organ?
     │  The gap is within the hive's domain.
     │  Spawn a new caste file to fill the gap.
     │  Example: Trading hive needs sentiment analysis
     │           → spawn drones/sentiment-collector.md
     │  If the gap is within-domain → Reinforce. Stop here.
     │  If the gap is a different domain → Escalate.
     │
     ▼
Level 3: CALL SIBLING — Does another hive handle this?
     │  Check queen/lineage.md for a sibling hive
     │  that covers the needed domain.
     │  If sibling exists → Send inter-hive query.
     │  If no sibling → Escalate.
     │
     ▼
Level 4: SPAWN — Does the colony need a new hive?
     │  The gap requires a new domain specialist.
     │  No sibling hive exists.
     │  Request the Queen Hive to spawn a daughter.
     │  This is royal jelly — passed up to queen/spawning.md
     │  If spawnable → Birth new hive. Stop here.
     │  If beyond colony capability → Escalate.
     │
     ▼
Level 5: SURFACE — Tell the human.
     "I've identified a gap I cannot fill:
      [specific description].
      I tried: [what was attempted].
      Recommendation: [what the human should do]."
     The hive is honest about its limits. Never fake competence.
```

---

## Level 2: Reinforcement Protocol

When a hive needs a new caste:

### Detection
The hive recognizes reinforcement is needed when:
- A specific task type fails repeatedly (same root cause across multiple runs)
- The Scout's terrain map identifies a sub-domain with no matching worker
- The Evolution ritual patches the same gap more than twice (structural issue, not a prompt fix)

### Spawning a Reinforcement

The hive's Queen (SKILL.md) generates a new caste file:

```
1. IDENTIFY the gap
   → What capability is missing?
   → What inputs would the new caste receive?
   → What outputs would it produce?

2. CLASSIFY the caste type
   → Does it build/create? → Worker
   → Does it validate/check? → Soldier
   → Does it gather/compute without judgment? → Drone

3. GENERATE the file
   → Follow the template from output-forms/hive-blueprint.md
   → Include: role, input, output schema, failure behavior
   → Write using the colony tongue

4. REGISTER
   → Add to the hive's SKILL.md caste registry
   → Test with 2-3 inputs before relying on it
```

### Example

```
HIVE-ALPHA encounters: "What are the tax implications of this trade?"

Scout assessment: This is a tax/legal question. Outside trading domain.
Absorb attempt: Builder produces generic "consult a tax advisor" response.
Quality: <70% — not useful.

Reinforce check: Is tax analysis within trading domain?
  → Partially. Tax-loss harvesting IS trading-adjacent.
  → But full tax advisory is NOT.

Decision: REINFORCE for tax-loss harvesting signals (within domain).
           CALL SIBLING for full tax questions (legal hive).

Reinforcement spawned:
  workers/tax-harvester.md
  Role: Identify tax-loss harvesting opportunities in held positions
  Input: Holdings with cost basis + current prices + wash sale window
  Output: { candidates: [...], estimated_savings: ..., wash_sale_risk: ... }
```

---

## Level 3: Inter-Hive Communication Protocol

When a hive needs capability from a sibling, they communicate through a shared message format.

### Query Format

```json
{
  "protocol": "hive-inter-v1",
  "from": {
    "hive": "HIVE-ALPHA",
    "caste": "workers/stock-analyst",
    "context": "Analyzing position SMCI — encountered regulatory flag"
  },
  "to": {
    "hive": "hive-legal-advisory",
    "reason": "Need legal risk assessment on SEC investigation impact"
  },
  "query": {
    "type": "assessment",
    "urgency": "blocking | advisory | background",
    "input": {
      "description": "Super Micro Computer facing SEC accounting investigation",
      "specific_question": "What is the litigation risk and potential impact on stock price?",
      "context_data": { }
    },
    "response_schema": {
      "risk_level": "critical | high | medium | low",
      "assessment": "2-3 sentence analysis",
      "confidence": "1-10",
      "recommendation": "specific action for the querying hive",
      "caveats": ["limitations of this assessment"]
    }
  }
}
```

### Response Format

```json
{
  "protocol": "hive-inter-v1",
  "from": {
    "hive": "hive-legal-advisory",
    "caste": "workers/analyst"
  },
  "to": {
    "hive": "HIVE-ALPHA"
  },
  "response": {
    "status": "complete | partial | declined",
    "risk_level": "high",
    "assessment": "Active SEC investigation creates material uncertainty...",
    "confidence": 6,
    "recommendation": "Reduce position to 50% of current size. Set stop-loss at -20%.",
    "caveats": [
      "Assessment based on public information only",
      "Not legal advice — consult securities attorney for specific guidance"
    ]
  }
}
```

### Query Types

| Type | Meaning | Expected Response |
|---|---|---|
| **assessment** | "Evaluate this through your domain lens" | Structured analysis with confidence |
| **validation** | "Is this correct/safe/compliant?" | Pass/fail with findings |
| **generation** | "Produce something I can't" | Output in the querying hive's expected format |
| **lookup** | "Do you know about X?" | Factual response or "outside my knowledge" |

### Urgency Levels

| Urgency | Meaning | Response Expectation |
|---|---|---|
| **blocking** | Querying hive cannot proceed without answer | Immediate — the query is part of a live pipeline |
| **advisory** | Querying hive will proceed but wants input | Best-effort — enhances but doesn't block |
| **background** | Enrichment for future decisions | Asynchronous — store for later use |

### Routing Rules

1. Check `queen/lineage.md` for a hive matching the needed domain
2. If multiple siblings could handle it, pick the most specific match
3. If no sibling exists but the need is recurring → recommend Level 4 (spawn)
4. If no sibling exists and the need is one-time → Level 5 (surface to human)
5. The querying hive must specify `response_schema` — never send open-ended queries
6. The receiving hive treats the query like any input: Scout maps, Builder responds
7. The receiving hive can decline: `"status": "declined"` with reason

### Failure Handling

If the sibling hive's response is:
- `status: "complete"` → integrate into the querying hive's pipeline
- `status: "partial"` → use what's available, note gaps
- `status: "declined"` → escalate to Level 4 or 5
- No response / error → the querying hive must have a fallback (never block indefinitely on a sibling)

---

## Level 4: Spawn Request

When no sibling exists and the gap requires a new domain specialist:

```json
{
  "protocol": "hive-spawn-request-v1",
  "from": {
    "hive": "HIVE-ALPHA",
    "reason": "Recurring need for social sentiment analysis with no sibling hive"
  },
  "requested_domain": "Social media sentiment analysis for trading signals",
  "evidence": [
    "5 queries in past month required sentiment data",
    "Builder produced <50% quality output on sentiment tasks",
    "LunarCrush and Grok integration designed but no hive to operate them"
  ],
  "suggested_castes": [
    "workers/x-sentiment-analyst — Grok API integration for X/Twitter",
    "workers/aggregator — LunarCrush/Santiment data normalization",
    "drones/sentiment-collector — raw social data gathering"
  ],
  "integration_point": "HIVE-ALPHA Stage 0 parallel feed"
}
```

This request goes to the Queen Hive, which executes `queen/spawning.md`.

---

## Decision Record

Every adaptation produces a record in the hive's memory:

```
ADAPTATION LOG

Timestamp: [when]
Gap Detected: [what was missing]
Resolution Level: [1-5]
Action Taken: [absorb / reinforce / call sibling / spawn / surface]
Result: [what happened]
New Caste File: [if reinforcement was spawned]
Inter-Hive Query: [if sibling was called]
Spawn Request: [if new hive was requested]
Lesson: [what the colony learned]
```

This log feeds future adaptation decisions. If the same gap appears three times and was absorbed each time with <70% quality, the hive should escalate to reinforcement automatically.

---

## Adaptation Anti-Patterns

- ❌ Faking competence (producing confident-sounding output in an unknown domain)
- ❌ Spawning when absorbing would suffice (expensive over-reaction)
- ❌ Skipping the hierarchy (jumping to spawn when a sibling exists)
- ❌ Open-ended inter-hive queries (always specify response_schema)
- ❌ Blocking indefinitely on a sibling (always have a fallback)
- ❌ Not recording the adaptation (the colony must learn from every gap)

---

*The Adaptation Ritual — the hive recognizes its limits and grows past them.*
