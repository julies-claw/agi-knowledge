---
tags: [observability, models, infra]
links: [./evals.md, ../infra/agent-memory-systems.md, ../agents/context-engineering.md]
status: growing
updated: 2026-03-22
---

# Hallucination — The Trust Problem

AI models confidently produce false information. This is still unsolved in 2026 — it's better but not gone.

## What Hallucination Actually Is

Models predict the most probable next token. "Most probable" ≠ "true."
The model has no ground truth — it has patterns. When patterns are ambiguous or the model is out-of-distribution, it fills gaps with plausible-sounding fiction.

## Types

- **Factual hallucination**: wrong facts stated confidently ("Albert Einstein was born in 1879" ← actually correct, but models often get birth dates wrong)
- **Citation hallucination**: fabricating academic papers, court cases, URLs that don't exist
- **Instruction hallucination**: claiming to have done something it didn't do
- **Reasoning hallucination**: correct-looking chain of thought that reaches a wrong conclusion

## Citation Hallucination in RAG — A Specific Problem

Even with RAG, models hallucinate citations:
- arXiv 2601.05866 (Jan 2026): "Mechanistic Detection of Citation Hallucination in Long-Form RAG"
  — Models attribute claims to sources that don't actually contain those claims
  — Harder to detect than pure fabrication because the citation looks valid

CiteMind (Feb 2026): "hallucination-aware, citation-grounded RAG" system
  — Enforces that every claim be traceable to a retrieved chunk
  — Adds refusal mechanisms when evidence is insufficient

## What Reduces Hallucination

1. **RAG** — ground responses in retrieved documents (reduces factual errors significantly)
2. **Smaller scope** — well-defined domains hallucinate less than open-ended questions
3. **Chain of thought** — "think step by step" catches some reasoning errors
4. **Verification loops** — agent checks its own outputs against sources
5. **Better training** — RLHF and constitutional AI tuned for honesty
6. **Uncertainty expression** — models that say "I don't know" instead of guessing

## What Doesn't Fix It

No technique eliminates hallucination. The fundamental issue is that language models are probability distributions over text, not knowledge retrieval systems. This architectural fact doesn't change with RLHF or RAG.

For high-stakes applications (medical, legal, financial), always verify AI outputs against authoritative sources.

## Sources

- arXiv 2601.05866: "Mechanistic Detection of Citation Hallucination in Long-Form RAG" (Jan 2026)
- CiteMind: "Hallucination-Aware, Citation-Grounded RAG" (Feb 2026)
- MARIA OS: "Evidence Bundle-Enforced RAG" (Feb 2026)
