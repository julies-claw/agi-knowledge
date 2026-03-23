---
tags: [infra, agents, memory]
links: [../infra/memory.md, ../agents/long-running.md, ../agents/context-engineering.md]
status: growing
updated: 2026-03-22
---

# Agent Memory Systems — Landscape (2026)

Giving agents persistent memory across sessions is a solved problem in theory but a messy ecosystem in practice. Two main philosophies are competing.

## Two Philosophies

### Mem0 — Memory as a Layer
- Drop into any existing agent stack
- Handles storage + retrieval passively (extracts memories from conversations)
- Semantic search over stored memories
- GitHub: ~48K stars | YC-backed ($24M Series A)
- Benchmark (LongMemEval): 49.0%
- License: Apache 2.0
- Think of it as: "add memory to your agent in 5 lines of code"

### Letta (formerly MemGPT) — Memory as an OS
- Full agent runtime, not a library
- Agent self-edits its own tiered memory (like an OS managing RAM/disk)
  - Core memory (RAM-like, always in context)
  - Recall memory (recent, searchable cache)
  - Archival memory (cold storage, retrieved on demand)
- Agent makes tool calls to query its own memory
- GitHub: ~21K stars | Felicis-backed ($10M seed)
- Has ADE (Agent Development Environment) — visual tooling
- Think of it as: "your agent lives inside Letta"

Source: Vectorize.io comparison (Mar 2026)

## Other Notable Players (2026)

- **Zep** — fast, structured memory for production agents
- **Hindsight** — memory from feedback/corrections
- **Memvid** — video-based memory (novel modality)

## When to Use What

| Scenario | Best fit |
|---|---|
| Adding memory to existing LangChain/CrewAI agent | Mem0 |
| Building agent from scratch, want full control | Letta |
| Production, compliance requirements (HIPAA, SOC2) | Mem0 managed |
| Research, want OS-inspired memory architecture | Letta |

## The Deeper Problem

Memory systems solve *retrieval*, but not *forgetting well*. As agents accumulate more memories, retrieval quality degrades. The field hasn't solved memory curation and decay at scale.

## Sources

- Vectorize.io: "Mem0 vs Letta (MemGPT): AI Agent Memory Compared" (Mar 2026)
- Vectorize.io: "Best AI Agent Memory Systems" (Mar 14, 2026)
