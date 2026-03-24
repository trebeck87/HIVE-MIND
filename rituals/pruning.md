# The Pruning Ritual

**Purpose**: Detecting and removing spoiled colony memory. The Evolution ritual handles acute failures. The Pruning ritual handles chronic decay — patterns that were true once but aren't anymore, anti-patterns that model improvements have made obsolete, and memory entries that accumulate without ever being tested.

---

## Biological Grounding

Bee bread is pollen fermented with honey and enzymes — long-term protein storage that feeds the colony when fresh pollen isn't available. Spoiled bee bread weakens the brood. Colony memory IS bee bread — raw observations fermented through quarantine into trusted patterns. The Pruning ritual detects spoilage.

---

## When to Invoke

The Pruning ritual is periodic, not reactive. It fires on schedule, not on failure.

**Triggers:**
- Every major version bump (v3 → v4, v4 → v5)
- When the Evolution ritual patches the same area 3+ times (structural problem, not acute failure)
- On beekeeper request ("audit the colony's memory", "what patterns are stale?")
- When a model generation change is known (patterns validated on Claude 2 may not apply to Claude 4)

**The Pruning ritual does NOT fire on:**
- Individual output failures (that's Evolution)
- Acute hallucination detection (that's Immunity)
- Inter-hive trust failures (that's Security)

---

## Ritual Flow

```
PRUNING

Phase 1: INVENTORY (Forager gathers)
  Forager enumerates all entries in:
  → memory/patterns.md — trusted patterns
  → memory/antipatterns.md — trusted anti-patterns
  Count: total entries, entries with version tags, entries without.

Phase 2: STALENESS SCAN (Guardian reviews)
  For each entry, the Guardian asks:
  → When was this entry last validated? (version tag, if present)
  → Has this entry been tested against a current model?
  → Is the entry still directionally correct?
  → Is the entry still practically useful?

  Staleness classification:
    FRESH — validated within current major version, still useful
    AGING — not validated recently, but no contradicting evidence
    STALE — technically true but no longer useful (bee bread past shelf life)
    SPOILED — contradicted by newer patterns or model behavior changes

Phase 3: CONTRADICTION SCAN (Sentinel reviews)
  Sentinel checks for:
  → Two patterns that produce conflicting advice on the same input
  → A pattern that contradicts a Mycelium decision
  → A pattern that assumes model behavior from a prior generation
  → An anti-pattern that current models handle natively (no longer a risk)

  Contradiction classification:
    CONSISTENT — no conflicts found
    TENSION — two entries pull in different directions but don't directly contradict
    CONTRADICTION — entries give opposite advice for the same case

Phase 4: DEPRECATION REVIEW (surfaced to beekeeper)
  Present findings to the beekeeper:
  → STALE entries: "These are technically true but no longer useful. 
    Deprecate or confirm?"
  → SPOILED entries: "These are contradicted by newer evidence. 
    Deprecate or investigate?"
  → CONTRADICTIONS: "These entries conflict. Which takes priority, 
    or should both be rewritten?"
  → AGING entries: "These haven't been validated recently. 
    Flag for testing or leave as-is?"

  The beekeeper decides. The colony does not auto-deprecate.

Phase 5: EXECUTION
  Based on beekeeper decisions:
  → CONFIRMED (still valid): entry stays, gets a version tag update
  → DEPRECATED: entry moves through the deprecation flow (see below)
  → REWRITTEN: entry is updated in place, old version noted
  → FLAGGED: entry stays but is marked for testing in the next 
    validation wave
```

---

## Deprecation Flow

Deprecated entries don't disappear. They're relabeled and relocated so the colony remembers what it used to believe and why it stopped.

```
TRUSTED (memory/patterns.md or memory/antipatterns.md)
     │
     │  Pruning ritual flags as STALE or SPOILED
     │  Beekeeper confirms deprecation
     ▼
DEPRECATED (stays in original file with [DEPRECATED] tag)
     │
     │  Entry annotated with:
     │  - Why deprecated (stale / contradicted / model generation change)
     │  - What replaced it (if anything)
     │  - Version deprecated
     ▼
ARCHIVED (moved to memory/infections.md as "outdated pattern")
     │  Only if the deprecated pattern could actively mislead future work.
     │  If merely stale (not dangerous), it stays in original file
     │  with the [DEPRECATED] tag — visible but clearly marked.
```

### Deprecation Record Format

When a pattern is deprecated, annotate it in place:

```
### P[N]: [Pattern Name] [DEPRECATED v3.3]
[Original content unchanged]

**Deprecated**: v3.3.0 — [reason: stale / contradicted / model generation change]
**Replaced by**: [new pattern, if any, or "N/A — capability now native to model"]
**Decision**: Pruning ritual, beekeeper confirmed [date]
```

---

## What Pruning Is Not

**Pruning is not Evolution.** Evolution fixes acute failures in outputs. Pruning maintains the health of the colony's accumulated knowledge. Evolution asks "why did this output fail?" Pruning asks "is what the colony believes still true?"

**Pruning is not deletion.** Deprecated entries are annotated and archived, not removed. The colony's history of belief is itself valuable — understanding what used to be true and why it stopped is how the colony avoids re-learning old lessons.

**Pruning is not automatic.** The ritual surfaces findings to the beekeeper. The beekeeper decides. No pattern is deprecated without sovereign confirmation. This prevents the colony from accidentally pruning a still-valid pattern based on a false positive in the contradiction scan.

---

## Pruning Anti-Patterns

- ❌ Auto-deprecating without beekeeper review (false positives on contradiction scan are real — a pattern that *seems* contradicted may still be valid in its specific context)
- ❌ Deleting deprecated entries (the colony needs to remember what it used to believe)
- ❌ Pruning only after failures (the whole point is catching spoilage *before* it causes failures)
- ❌ Skipping the contradiction scan (stale entries are low-risk; contradicted entries are high-risk. Both matter, but contradictions matter more)
- ❌ Pruning during active development (run between versions, not during construction)

---

*The Pruning Ritual — bee bread spoils. The colony catches it before the brood weakens.*
