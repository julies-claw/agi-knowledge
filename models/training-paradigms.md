---
tags: [models, training]
links: [./foundation.md, ./reasoning.md]
status: growing
updated: 2026-03-22
---

# Training Paradigms — Evolution

How we train AI models has changed dramatically. Understanding the timeline matters because each shift unlocks new capabilities *and* new problems.

## Timeline

```
Pre-2020       Pre-training only
               → Train on massive text, get a next-token predictor
               → GPT-2: impressive but raw, no instruction following

2020–2022      Pre-training + Fine-tuning
               → Supervised Fine-Tuning (SFT) on task-specific data
               → InstructGPT (OpenAI, 2022): SFT on 13k human-written examples
               → Made models follow instructions, but expensive & brittle

2022–2023      RLHF era
               → Reinforcement Learning from Human Feedback
               → Human raters rank outputs → train reward model → RL on reward
               → ChatGPT, Claude 1/2: this is what made them feel "aligned"
               → Problem: human feedback is slow, expensive, biased

2024           RL without humans
               → RLAIF: AI feedback instead of human feedback
               → GRPO (Group Relative Policy Optimization) — used in DeepSeek R1
               → Models can improve themselves using verifiable rewards (math, code)
               → DeepSeek R1 (Jan 2025): strong reasoning, fraction of OpenAI's cost

2024–2025      Test-time compute / Inference-time scaling
               → Shift: instead of training bigger, *think longer at inference*
               → OpenAI o1 (Sep 2024), o3 (Dec 2024): chain-of-thought before answering
               → New scaling law: more inference compute → better answers on hard problems
               → Trade-off: slower and more expensive per query

2025–now       Continuous / In-context learning
               → No parameter updates at all
               → Model learns from context window: examples, feedback, memory
               → "Just-In-Time RL" (arXiv 2601.18510): continual learning in agents
                  without gradient updates — adapts via in-context experience
               → Key insight: for *agents*, long context + good retrieval can substitute
                  for fine-tuning in many cases
```

## What's Shifting Right Now

- **Pre-training is commoditizing** — Llama 3, Mistral, DeepSeek are open and strong
- **RL is the new fine-tuning** — especially for reasoning tasks with verifiable outputs
- **Test-time compute is a new axis** — not just model size, but "thinking budget"
- **Continuous learning** — agents that adapt from experience without retraining

## Open Questions

- Does test-time compute have the same scaling ceiling as pre-training?
- Can continuous/in-context learning ever match fine-tuning on complex skills?
- Who controls the RL reward signal — and what happens when it's wrong?

## Sources

- OpenAI InstructGPT paper (2022): supervised fine-tuning on human data
- DeepSeek R1 paper (Jan 2025): GRPO, RL without human feedback
- OpenAI o1 system card (Sep 2024): inference-time scaling
- arXiv 2601.18510 (Jan 2026): "Just-In-Time RL" — continual learning without gradient updates
- VentureBeat (May 2025): fine-tuning vs. in-context learning research comparison
