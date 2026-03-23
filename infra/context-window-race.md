---
tags: [infra, models, agents]
links: [../models/foundation.md, ../agents/context-engineering.md, ../agents/long-running.md]
status: stable
updated: 2026-03-22
---

# Context Window Race — From 4K to 1M Tokens

The rapid expansion of context windows is one of the most practically impactful changes in AI infrastructure. It changes what agents can do without external memory systems.

## Timeline

```
GPT-3 (2020)           4,096 tokens (~3,000 words)
GPT-4 (2023)           8K → 32K tokens
Claude 1/2 (2023)      100K tokens — first "long context" model
Gemini 1.5 Pro (2024)  1 million tokens — research preview
Claude 3 (2024)        200K tokens standard
GPT-4o (2024)          128K tokens
Gemini 1.5 Pro (2024)  1M tokens — production
Gemini 2.0 (2025)      1M+ tokens
Claude — 1M (2026)     1 million tokens for all users (Mar 2026)
```

Sources: Mindstudio (Mar 2026), Claude5.com context window evolution

## What 1M Tokens Actually Means

- ~750,000 words
- Entire codebase of a medium-sized project
- 10+ hours of transcripts
- Full books, legal documents, research corpora

At 1M tokens: many use cases that previously required RAG or external memory can now just fit in context. The line between "memory" and "context" blurs.

## Does Longer Context = Better Performance?

Not always. "Context rot" (Chroma research) shows LLMs lose focus in very long contexts — information in the middle gets underweighted. 1M token window ≠ perfect recall across 1M tokens.

**Lost in the middle problem**: models attend well to beginning and end of context, but miss information buried in the middle.

## Implications for Agents

- Long-running agents can maintain more session history in-context
- RAG still needed for *dynamic* or *huge* knowledge bases
- Very long contexts = higher inference cost (quadratic attention complexity)
- Trade-off: long context vs. fast retrieval from external memory

## Sources

- Mindstudio: "Claude 1M Token Context Window" (Mar 17, 2026)
- Claude5.com: "Context Window Evolution: 200K to 1M Tokens" (Jan 2026)
- Chroma research: context rot paper
