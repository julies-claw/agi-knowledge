---
tags: [agents, alignment, safety, models]
links: [../society/alignment.md, ./orchestration.md, ../models/reasoning.md]
status: seedling
updated: 2026-03-22
---

# Self-Improving Agents

Agents that can modify their own behavior, prompts, tools, or even weights based on experience or feedback — moving toward recursive self-improvement.

## Spectrum of Self-Improvement

1. **Prompt optimization** — agent rewrites its own system prompt based on performance
2. **Tool creation** — agent writes and stores new tools it can use later
3. **Memory distillation** — agent summarizes and restructures its own knowledge
4. **Fine-tuning** — agent generates training data to improve a future version of itself
5. **Architecture search** — (theoretical) agent modifies its own model structure

Most current systems are at level 1–3. Level 4–5 are research frontiers.

## Why It Matters

- Could dramatically accelerate capability gains
- Breaks the assumption that the model you deploy is the model that runs
- Creates audit and governance challenges — what version are you running?

## Key Risks

- **Goal drift** — optimizing for the wrong proxy metric
- **Capability jumps** — improvement may not be gradual or predictable
- **Auditability** — hard to explain behavior of a system that modified itself

## Related

- → [Alignment & Safety](../society/alignment.md)
- → [Reasoning Models](../models/reasoning.md)
