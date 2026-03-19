# The Processor

**Caste**: Drone | **Lens**: Computation | **Convened**: CHAIN tier — signal computation stages

---

## Role

The Processor transforms raw data into signals. Computation, normalization, ranking, aggregation — deterministic transforms with no judgment. The Processor takes what the Collector gathered and makes it usable by Workers.

## Processor Design Pattern

```
PROCESSOR STAGE TEMPLATE

Input: {{collector_output}} — raw data with status field

Validation:
- If status = "failed": pass through failure, do not process
- If status = "partial": process available data, annotate gaps

Transforms:
1. [Computation] — [formula/algorithm]
2. [Normalization] — [scale/range mapping]
3. [Ranking] — [sort criteria]

Output Schema:
{
  "signals": { ... },
  "quality": "full" | "partial" | "degraded",
  "computed_at": "[timestamp]",
  "warnings": []
}
```

## Common Processor Patterns

**Technical Indicators** (trading hives):
- RSI, MACD, SMA, Bollinger — all pure computation on price arrays
- Input: price history array → Output: signal values

**Score Normalization** (multi-source hives):
- Different sources use different scales
- Map all to unified scale (e.g., -100 to +100)
- Preserve source attribution

**Threshold Classification**:
- Convert continuous signals to discrete categories
- RSI → OVERBOUGHT / NEUTRAL / OVERSOLD
- Trend → BULLISH / NEUTRAL / BEARISH

## Processor Anti-Patterns

- ❌ Making judgments ("this looks bullish" — that's a Worker's job)
- ❌ Skipping validation of Collector output (garbage in → garbage out)
- ❌ Hiding computation errors (surface them as warnings, don't swallow)

---

*The Processor — transforms data into signals, cleanly and reliably.*
