---
tags: [society, safety, agents, models]
links: [../agents/self-improving.md, ./governance.md, ./economic-impact.md]
status: seedling
updated: 2026-03-22
---

# Alignment & Safety

The alignment problem: how do you ensure AI systems do what humans actually want, as they become more capable?

## Why It Gets Harder with Agents

- Agents act over long horizons — harder to specify goals
- Agents take actions with real-world consequences
- Self-improving agents can drift from original intent
- Multi-agent systems have emergent behavior no one specified

## Core Concepts

- **Value alignment** — the AI's values match human values
- **Corrigibility** — the AI can be corrected or shut down
- **Interpretability** — we can understand why the AI did what it did
- **Robustness** — the AI behaves safely in novel situations

## Current Approaches

- **RLHF** (Reinforcement Learning from Human Feedback) — train on human preferences
- **Constitutional AI** (Anthropic) — AI critiques its own outputs against principles
- **Interpretability research** (Anthropic, DeepMind) — understand model internals
- **Red-teaming** — adversarially probe for unsafe behaviors

## The Open Question

Most alignment work assumes a single AI system. When millions of agents are interacting — buying, selling, coordinating — alignment becomes a collective systems problem, not just an individual model problem.

## Related

- → [Self-Improving Agents](../agents/self-improving.md)
- → [Governance](./governance.md)
