# Colony Examples

Reference outputs at each complexity tier. The Builder and Forager consult these when constructing new outputs.

---

## SIMPLE Tier Example: Content Classifier (~80 tokens)

**Request**: "Write a prompt to classify customer support tickets by urgency"

**Output**:
```
You are a support ticket classifier.

Given a customer message, classify its urgency as CRITICAL, HIGH, MEDIUM, or LOW.

CRITICAL: System down, data loss, security breach
HIGH: Feature broken, blocking work, deadline at risk
MEDIUM: Bug present but workaround exists, feature request
LOW: Question, feedback, cosmetic issue

Respond with only the urgency level, nothing else.

Example:
Input: "Our entire team can't log in and we have a client demo in 30 minutes"
Output: CRITICAL

Input: "The export button puts the date in US format, we need European format"
Output: LOW
```

**Why this works**: Role in 5 words. Clear taxonomy. Two calibrating examples at opposite ends. No scaffolding overhead.

---

## MEDIUM Tier Example: Meeting Notes Synthesizer (~280 tokens)

**Request**: "Build a prompt that turns raw meeting transcripts into structured notes"

**Output**:
```
You are a meeting analyst. Transform raw transcripts into structured, actionable notes.

<objective>
Extract decisions, action items, and key discussion points from meeting transcripts. Prioritize what changed (decisions) over what was discussed (conversation).
</objective>

<output_format>
## [Meeting Topic] — [Date]

### Decisions Made
1. [Decision]: [Context in ≤15 words] — Owner: [name]

### Action Items
1. [Task] — Owner: [name] — Due: [date or "TBD"]

### Key Discussion Points
- [Point]: [1-2 sentence summary]

### Open Questions
- [Question]: [Who needs to answer]
</output_format>

<constraints>
- Every action item MUST have an owner. If unclear from transcript, note "[Owner unclear]"
- Decisions are only items where the group agreed on a direction. Suggestions and ideas go under Discussion
- If the transcript is truncated, process available content and note: "[Transcript incomplete]"
</constraints>

<example>
Input: "...so we agreed to push the launch to March 15th. Sarah will update the timeline doc. Oh and Mike brought up adding SSO but we didn't decide on that yet..."

Output:
### Decisions Made
1. Launch pushed to March 15th: Team agreed on new date — Owner: [team lead]

### Action Items
1. Update timeline document — Owner: Sarah — Due: TBD

### Key Discussion Points
- SSO integration: Mike proposed adding SSO. No decision reached.

### Open Questions
- SSO integration: Does the team want to pursue this? — Mike to propose scope
</example>
```

**Why this works**: Clear objective distinguishing decisions from discussion. Concrete output format. Constraint on owner attribution handles the most common gap. Example shows how to handle a mixed-signal transcript.

---

## COMPLEX Tier Example: HIVE-ALPHA Individual Stock Analysis (~500 tokens)

**Request**: "Build a prompt for single-stock AI equity analysis with conviction scoring"

See HIVE-ALPHA Stage 2 in `queen/lineage.md` — this is a production-deployed example with:
- `<core_objective>` front-loaded
- `<output_format>` with typed JSON schema
- `<constraints>` with conviction scale definition
- `<edge_case_handling>` for signal conflicts
- `<trading_frequency_awareness>` for auto-pilot context
- `<examples>` with 1 GOOD + 1 BAD annotated output (70% Rule applied)

**Why this works**: Domain-specific edge cases (RSI overbought + bullish, micro cap vol > 80%) prevent generic output. Anti-pattern example calibrates quality floor. Prefill forces JSON compliance.

---

## CHAIN Tier Example: HIVE-ALPHA Portfolio Pipeline (3 stages)

**Request**: "Build a multi-stage AI trading intelligence pipeline"

See HIVE-ALPHA Prompt Architecture document. Production chain with:
- Stage 1: Portfolio Construction (batch allocation, ~14 candidates)
- Stage 2: Individual Analysis (single-stock deep dive)
- Stage 3: Sweep Rebalancing (rapid batch re-analysis with auto-execution)

Architecture demonstrates:
- Per-stage system prompts, user templates, output schemas
- Per-stage pass conditions and failure behaviors
- Orchestration: state management, error propagation, human checkpoints
- Client-side execution logic (auto-execution rules table)
- Validation evidence per stage

**Why this works**: Clean separation of concerns. Each stage has a single job. Failure in one stage doesn't halt the system. Human checkpoints at appropriate intervention points.

---

## SPAWN Tier Example: HIVE-ALPHA as Daughter Hive

**Request**: "Build me an AI system for BTC portfolio analysis"

This request was royal jelly. The Queen spawned a full daughter hive with:
- Daughter Queen (SKILL.md): 5-stage orchestration
- Workers: Portfolio Builder, Stock Analyst, Sweep Runner
- Soldiers: Risk Monitor (overbought/bearish, stop-loss, circuit breaker)
- Drones: Price Engine, Signal Computer
- Memory: Trade history, regime patterns

The daughter evolved autonomously through 4 iterations:
1. v1→v2: 10 stocks → 49 stocks (coverage expansion)
2. v2→v3: Manual start → automated initialization (Stage 1 prompt created)
3. v3→v4: Manual-only trading → hybrid auto-pilot (frequency model)
4. v4→current: Prompt foundation patches (few-shot, prefill, portfolio context)

Each evolution followed the colony's Evolution ritual: diagnose → patch → re-test → learn.

---

*Colony Examples — reference outputs that prove the patterns work.*
