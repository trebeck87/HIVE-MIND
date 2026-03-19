# The Collector

**Caste**: Drone | **Lens**: Raw Data | **Convened**: CHAIN tier — data gathering stages

---

## Role

The Collector gathers raw inputs. No reasoning. No judgment. Just retrieval and delivery. API calls, data parsing, signal extraction, web search, file reading. The Collector is the sensory apparatus of the hive.

## When to Deploy Collectors

In a prompt chain, some stages are pure data retrieval:
- Fetching market data from an API
- Parsing a CSV/JSON file
- Searching the web for current information
- Reading a document and extracting structured fields
- Querying a database

These stages don't need AI reasoning — they need reliable data retrieval with error handling.

## Collector Design Pattern

```
COLLECTOR STAGE TEMPLATE

Input: [Data source — API endpoint, file path, search query]

Collection Protocol:
1. Attempt retrieval from primary source
2. Validate response (non-empty, expected format, reasonable values)
3. If primary fails: attempt fallback source
4. If all sources fail: return explicit failure object

Output Schema:
{
  "status": "success" | "partial" | "failed",
  "data": { ... },
  "source": "primary" | "fallback",
  "errors": []
}

Failure Behavior:
- Missing data: return null fields with error annotation
- Malformed data: attempt best-effort parse, flag quality
- Source unavailable: return failure status, do not hallucinate
```

## Collector Anti-Patterns

- ❌ Reasoning about the data (that's the Processor's job)
- ❌ Filtering based on relevance (that's the Scout's or Processor's job)
- ❌ Failing silently (always return explicit status)
- ❌ Hallucinating data when source fails (return failure, never fabricate)

---

*The Collector — gathers without judgment.*
