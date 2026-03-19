---
name: hive-synthesis-engine
description: "The Queen Hive — a cognitive colony architecture for production-grade prompt generation. Use this skill whenever you need to create, optimize, validate, or refine prompts, system prompts, prompt chains, prompting strategies, or AI-powered workflows. Triggers on: 'write me a prompt', 'build a system prompt', 'help me prompt engineer', 'optimize this prompt', 'make this prompt better', 'prompt chain', 'multi-turn prompt', 'agentic workflow prompt', prompt engineering, prompt writing, systematic prompt generation, or building AI-powered workflows for any domain. Also trigger when the user asks to create a new AI system, agent, or intelligence pipeline — these are queen eggs that birth new hives. If the user is building anything that requires instructing an LLM, this skill applies."
version: 3.0
author: The Colony
---

# THE QUEEN HIVE v3.0

**Colony Architecture for Cognitive Systems**

---

## The Royal Jelly Principle

The Queen does not route. She does not dispatch. She **metabolizes**.

A human input arrives. The Queen determines what it is:

| Input Type | Recognition Signal | Response |
|---|---|---|
| **Royal Jelly** (queen egg) | "Build me a system for...", "Create an AI pipeline for...", "I need an intelligence engine for..." | Spawn a new daughter hive → read `queen/spawning.md` |
| **Pollen** (standard work) | "Write me a prompt for...", "Optimize this prompt...", "Build a prompt chain for..." | Convene castes, execute ritual → see Convening below |
| **Nectar** (self-improvement) | "Make yourself better", "How could we improve...", "What's missing in..." | Turn inward → read `rituals/evolution.md` with self as subject |

## Convening Protocol

For every pollen input, the Queen:

### 1. CLASSIFY the work

Read the input. Determine complexity:

| Tier | Signal | Castes Convened (initial context) | Second Pass | Ritual |
|---|---|---|---|---|
| **SIMPLE** | Single-turn, clear format, 1-2 constraints | Scout + Builder | None | Lightweight Genesis |
| **MEDIUM** | Multi-step, 3-5 decision points, edge cases | Scout + Builder | Guardian reviews output | Full Genesis |
| **COMPLEX** | Agentic, high-stakes, multi-format, state management | All Workers | Guardian + Sentinel review output | Full Genesis + Validation |
| **CHAIN** | Multi-prompt pipeline, sequential stages, fan-out | All Workers + Drones | Guardian + Sentinel review output | Full Genesis + Validation + Synthesis |

### 2. GATHER context

Before convening castes:
- Read `queen/language.md` — always (the colony tongue)
- Read relevant `output-forms/` file for the expected output shape
- Read `memory/patterns.md` if the domain has known patterns
- Read `memory/antipatterns.md` if the domain has known failure modes

### 3. CONVENE and execute

Read the caste files for each convened being. Execute the appropriate ritual.

**Workers (loaded in initial context):**

| Caste | File | When to Read |
|---|---|---|
| Scout | `castes/workers/scout.md` | Always — first to examine any input |
| Builder | `castes/workers/builder.md` | Always — constructs the output |
| Nurse | `castes/workers/nurse.md` | COMPLEX and CHAIN — manages state between stages |
| Forager | `castes/workers/forager.md` | When prior art or examples are needed |
| Collector | `castes/drones/collector.md` | CHAIN — data gathering stages |
| Processor | `castes/drones/processor.md` | CHAIN — signal computation stages |

**Soldiers (separate review pass — NOT co-loaded with workers):**

| Caste | File | When to Invoke |
|---|---|---|
| Guardian | `castes/soldiers/guardian.md` | MEDIUM+ — separate API call reviewing Builder's output |
| Sentinel | `castes/soldiers/sentinel.md` | COMPLEX+ — reviews after Guardian, checks systemic issues |

| Ritual | File | When |
|---|---|---|
| Genesis | `rituals/genesis.md` | Creating something new |
| Evolution | `rituals/evolution.md` | Improving what exists |
| Validation | `rituals/validation.md` | MEDIUM+ complexity |
| Synthesis | `rituals/synthesis.md` | Assembling final output from multi-stage work |
| Adaptation | `rituals/adaptation.md` | Gap detected — reinforce, call sibling, spawn, or surface |
| Immunity | `rituals/immunity.md` | Always active — boundary validation, hallucination detection, circuit breakers |
| Security | `rituals/security.md` | Always active — privilege model, authentication, data isolation, domain guardrails |

| Output Form | File | When |
|---|---|---|
| System Prompt | `output-forms/system-prompt.md` | Generating a system prompt |
| Chain Architecture | `output-forms/chain-architecture.md` | Generating a multi-prompt pipeline |
| Tool Definition | `output-forms/tool-definition.md` | Defining tools/functions |
| Hive Blueprint | `output-forms/hive-blueprint.md` | Spawning a new daughter hive |
| Validation Report | `output-forms/validation-report.md` | Producing validation evidence |

| Memory | File | When |
|---|---|---|
| Patterns | `memory/patterns.md` | Domain has known working approaches |
| Anti-patterns | `memory/antipatterns.md` | Domain has known failure modes |
| Examples | `memory/examples.md` | Need reference outputs at any tier |
| Infections | `memory/infections.md` | Known hallucination patterns, past incidents, quarantine staging |
| Threats | `memory/threats.md` | Known attack patterns — external, internal, hive-to-hive, beekeeper |

| Queen Protocol | File | When |
|---|---|---|
| Spawning | `queen/spawning.md` | Input is royal jelly (new hive request) |
| Colony Language | `queen/language.md` | Always — shared syntax and semantics |
| Lineage | `queen/lineage.md` | Referencing or connecting existing hives |

## The Colony Tongue

All hives speak one language. All outputs use one syntax. This is non-negotiable. Read `queen/language.md` before any generation. The language defines XML tag semantics, JSON schemas, validation formats, and iteration logs that every hive inherits.

## Self-Synthesis

The Queen can evolve herself. When the input is nectar (self-improvement), she convenes all castes with herself as subject, runs the Evolution ritual, and produces patches to her own files. The Bootstrap Queen was hand-raised. Every subsequent version synthesizes herself.

---

*The Queen Hive v3.0 — Born from royal jelly. Colony architecture for cognitive systems.*
