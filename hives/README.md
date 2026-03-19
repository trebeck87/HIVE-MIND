# Spawned Hives

This directory contains daughter hives spawned by the Queen.

Each daughter hive is autonomous — she orchestrates her own workers, evolves her own prompts, and speaks the colony tongue. See `queen/lineage.md` for the registry of all hives and their connections.

## Adding a Hive

Hives are spawned through `queen/spawning.md`. Each follows the structure defined in `output-forms/hive-blueprint.md`:

```
hive-name/
├── SKILL.md              ← Daughter Queen
├── workers/              ← Domain-specific workers
├── soldiers/             ← Quality/safety validators
├── drones/               ← Data pipeline (if needed)
└── memory/               ← Domain-specific knowledge
```

## Current Hives

See `queen/lineage.md` for the authoritative registry.
