---
tags: [models, agents]
links: [./foundation.md, ../agents/self-improving.md, ../observability/evals.md]
status: seedling
updated: 2026-03-22
---

# Reasoning Models

Models that "think before they answer" — using chain-of-thought, extended compute at inference time to solve harder problems.

## Key Models

- **OpenAI o1/o3** — first mainstream reasoning models, strong at math/coding
- **DeepSeek R1** — open-weight reasoning model, shocked the industry with efficiency
- **Claude 3.7 Sonnet** — extended thinking mode
- **Gemini 2.0 Flash Thinking** — Google's reasoning variant

## How It Works (Simplified)

Instead of immediately generating an answer, reasoning models generate a scratchpad of intermediate thoughts — then produce the final answer. More compute at inference = better answers for hard problems.

## Implications for Agents

- Reasoning models make better decisions in complex multi-step tasks
- They're slower and more expensive than standard models
- The right pattern: use reasoning for planning/decision, fast models for execution
- Self-improving agents may use reasoning to critique and rewrite their own behavior

## Open Questions

- Is chain-of-thought reasoning "real" reasoning or pattern matching?
- How do you eval reasoning quality, not just answer correctness?
- What's the ceiling on inference-time compute scaling?

## Related

- → [Foundation Models](./foundation.md)
- → [Self-Improving Agents](../agents/self-improving.md)
