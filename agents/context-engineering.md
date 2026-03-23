---
tags: [agents, context, infra]
links: [./long-running.md, ../infra/memory.md, ../infra/mcp.md]
status: growing
updated: 2026-03-22
---

# Context Engineering — Evolution

How we manage what the model "sees" at any given moment. This has gone through several distinct phases.

## Timeline

```
~2022          Prompt Engineering
               → Focus: writing better system prompts and instructions
               → One-shot or few-shot tasks, mostly single-turn
               → "The art of talking to an LLM"

2023           RAG (Retrieval-Augmented Generation)
               → Problem: models don't know recent/private info
               → Solution: retrieve relevant docs, inject into context
               → Vector databases (Pinecone, Weaviate, Chroma) boom
               → Still fundamentally about filling a prompt

2024–now       Context Engineering
               → Term coined/popularized by Anthropic engineering team
               → Shift: not just "what to put in the prompt"
                 but "what is the optimal set of tokens at each inference step"
               → Includes: system prompt + tools + MCP + external data
                 + message history + retrieved memory — all managed dynamically
               → Key insight: context is a state that evolves over time,
                 not a template you write once
               → "Context rot" discovered: LLMs lose focus as context grows
                 (Chroma research on needle-in-haystack benchmarks)
```

## What Context Engineering Actually Means (per Anthropic)

> "Context engineering is the art and science of curating what will go into the limited
> context window from that constantly evolving universe of possible information."

At each inference step, you decide:
- What instructions does the model need right now?
- What tools should be available?
- Which memories / docs are relevant to this exact step?
- What of the conversation history is still useful vs. noise?

## Key Techniques

- **Context compaction** — summarize old turns instead of dropping them
  (Claude Agent SDK uses this for long-running tasks)
- **MCP (Model Context Protocol)** — standardized way to inject tools/data dynamically
- **Selective memory retrieval** — don't dump everything, retrieve what's relevant
- **Context window management** — know your limits, prune aggressively

## Why It Matters for Agents

Single-turn LLMs: context is mostly static (system prompt + user message)
Agents: context is dynamic, evolves with every tool call and action
→ Context engineering becomes an ongoing loop, not a one-time design task

## Sources

- Anthropic Engineering Blog: "Effective context engineering for AI agents"
  https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- Karpathy tweet (2025): "context engineering" framing
- Chroma Research: "context rot" in long contexts
