---
tags: [infra, agents]
links: [./tools.md, ../agents/long-running.md, ../agents/self-improving.md]
status: seedling
updated: 2026-03-22
---

# Memory & Storage for Agents

How agents remember things — across turns, across sessions, across lifetimes.

## Memory Types

| Type | Scope | Example |
|------|-------|---------|
| In-context | Current session | Chat history in the prompt |
| External (short-term) | Session/task | Redis, scratch pad |
| External (long-term) | Persistent | Vector DB, structured DB |
| Parametric | Baked into model | What the model "knows" from training |

## Retrieval-Augmented Memory

Most production agents use RAG-style memory:
1. Store experiences/facts as embeddings in a vector DB
2. On new input, retrieve semantically relevant memories
3. Inject into context

## The Forgetting Problem

Agents with large memory stores face retrieval quality issues — the more they know, the harder it is to find the right thing. Memory compression and summarization are active research areas.

## Memory for Self-Improving Agents

Self-improving agents need memory that can be written to, not just read from. They need to update their own beliefs, correct mistakes, and build on past experiences. This is one of the hardest open problems.

## Related

- → [Tools & APIs](./tools.md)
- → [Long-Running Agents](../agents/long-running.md)
- → [Self-Improving Agents](../agents/self-improving.md)
