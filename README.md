# HIVE-MIND

### A Cognitive Colony Architecture for AI Systems

---

## What Is This?

A modular prompt engineering framework built on biological hive intelligence. Instead of a single monolithic prompt, the Queen Hive is a colony of specialized beings — workers, soldiers, drones — that convene around problems, challenge each other, and produce validated output through shared rituals.

The Queen Hive can:
- **Generate production-grade prompts** across any complexity tier (simple → chain pipelines)
- **Spawn autonomous daughter hives** for new domains (trading, legal, medical, any field)
- **Communicate between hives** through a structured inter-hive protocol
- **Self-improve** through evolution rituals and colony memory
- **Defend against hallucination** with an immune system (confidence calibration, contradiction detection, circuit breakers)
- **Enforce security** with privilege models, authentication, and domain guardrails

## Architecture

```
HIVE-MIND
│
├── SKILL.md                    ← The Queen — orchestrates everything
│
├── queen/                      ← Colony Protocol
│   ├── language.md               Shared syntax (the colony tongue)
│   ├── spawning.md               How daughter hives are born
│   └── lineage.md                Registry of all spawned hives
│
├── castes/                     ← The Beings
│   ├── workers/                  Build things (loaded in context)
│   │   ├── scout.md                Maps terrain before anyone builds
│   │   ├── builder.md              Constructs the output
│   │   ├── nurse.md                Manages state across stages
│   │   └── forager.md              Gathers prior art from memory
│   ├── soldiers/                 Review things (separate pass)
│   │   ├── guardian.md             Adversarial review of finished work
│   │   └── sentinel.md            Systemic risk and regression
│   └── drones/                   Compute things (no judgment)
│       ├── collector.md            Raw data gathering
│       └── processor.md           Deterministic transforms
│
├── rituals/                    ← Ceremonies
│   ├── genesis.md                Creating from nothing
│   ├── evolution.md              Diagnose → Patch → Learn
│   ├── validation.md             Stress-test to consensus
│   ├── synthesis.md              Assembly of multi-part work
│   ├── adaptation.md             Gap-filling (reinforce/call/spawn/surface)
│   ├── immunity.md               Hallucination defense & circuit breakers
│   └── security.md               Privilege model, auth & guardrails
│
├── memory/                     ← Colony Knowledge
│   ├── patterns.md               What works (earned wisdom)
│   ├── antipatterns.md           What fails (scar tissue)
│   ├── examples.md               Reference outputs per tier
│   ├── infections.md             Known hallucination signatures
│   └── threats.md                Known attack patterns
│
└── output-forms/               ← Output Templates
    ├── system-prompt.md          Shape of a system prompt
    ├── chain-architecture.md     Shape of a prompt chain doc
    ├── tool-definition.md        Shape of tool/function schemas
    ├── hive-blueprint.md         Shape of a new daughter hive
    └── validation-report.md      Shape of validation evidence
```

## Core Concepts

### The Royal Jelly Principle

The Queen recognizes three types of input:

| Input | Signal | Response |
|---|---|---|
| **Royal Jelly** | "Build me a system for..." | Spawn a new daughter hive |
| **Pollen** | "Write me a prompt for..." | Convene castes, generate output |
| **Nectar** | "Make yourself better..." | Self-improvement through evolution |

### Castes

Workers build. Soldiers review (in a separate pass — not co-loaded). Drones compute without judgment. This separation is enforced by a privilege model — workers can't validate their own output, drones can't make decisions.

### Rituals

| Ritual | Purpose |
|---|---|
| Genesis | Creating something new |
| Evolution | Improving what exists |
| Validation | Stress-testing to consensus |
| Synthesis | Assembling multi-part output |
| Adaptation | Growing new capabilities when gaps are found |
| Immunity | Defending against hallucination and cascade failure |
| Security | Privilege enforcement, authentication, domain guardrails |

### Colony Memory

Knowledge is earned, not assumed. Every pattern cites the real deployment experience that proved it. Anti-patterns carry scar tissue from actual failures. New observations go through quarantine before entering trusted memory.

## Spawned Hives

| Hive | Domain | Status |
|---|---|---|
| **HIVE-ALPHA** | AI sector equity trading intelligence | Active (v4) |
| **hive-legal-advisory** | Legal counsel & contract analysis | Active |
| **Social Sentiment** | X/Twitter BTC sentiment analysis | Planned (blocked on API key) |

## Validation

Tested across 65 automated tests using Claude-in-Claude:
- **95% average score** across all tiers
- **Zero new failure modes** for two consecutive waves (saturation confirmed)
- **Ablation testing** confirmed Guardian works better as a second-pass reviewer than co-loaded context
- Tests covered: SIMPLE, MEDIUM, COMPLEX, CHAIN, SPAWN tiers + adaptive + stress + ablation

## Usage

This is a Claude skill. To use it:

1. Add the `SKILL.md` and directory structure to your Claude Project's knowledge
2. Ask Claude to generate prompts, build chains, or spawn hives
3. The Queen will convene the appropriate castes and execute the right ritual

The colony tongue ensures all outputs follow consistent XML semantics, JSON protocols, and validation formats.

## Origin

Born from a conversation about prompt engineering that evolved into a question about cognitive architecture. The first Queen was hand-raised (Bootstrap Stage 1), validated through automated testing (Stage 2), and is ready for self-synthesis (Stage 3 — where the Queen rewrites herself through her own Evolution ritual).

---

*HIVE-MIND — colony architecture for cognitive systems.*
