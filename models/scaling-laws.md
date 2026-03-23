---
tags: [models, infra, training]
links: [./training-paradigms.md, ./foundation.md, ../infra/inference-economics.md]
status: stable
updated: 2026-03-22
---

# Scaling Laws — From Chinchilla to Test-Time Compute

How AI capability scales with compute, data, and model size. The story of scaling laws is the story of AI strategy.

## The Original Scaling Laws (OpenAI, 2020)

Kaplan et al.: loss scales predictably as a power law with:
- Model parameters (N)
- Training tokens (D)
- Compute budget (C)

Implication: bigger models + more data + more compute = better performance, reliably.
This justified the "race to scale" — just spend more.

## Chinchilla (DeepMind, 2022) — The Correction

Hoffmann et al. showed OpenAI's models were undertrained:
- Optimal: scale data and model size **equally**
- GPT-3 (175B params, 300B tokens) was too big relative to its data
- Chinchilla-optimal: for a given compute budget, use a smaller model trained on more data

Impact: Meta's Llama, Mistral, and others adopted Chinchilla-optimal training → strong smaller models.

## Beyond Chinchilla — Inference Matters Too

Sardana & Frankle (ICML 2024): Chinchilla assumes you train once and use once.
If you're running inference at scale (many queries), it's worth **overtraining** a smaller model:
- A smaller overtraind model is cheaper to run at inference
- At scale, inference cost dwarfs training cost
- Llama 3 8B: deliberately overtrained well beyond Chinchilla-optimal

This is why: **inference economics now drives training decisions**.

## The New Scaling Axis: Test-Time Compute

OpenAI o1 (Sep 2024) introduced a third scaling axis:
- Pre-training compute (fixed at deploy time)
- Fine-tuning / RLHF compute
- **Test-time compute** — spend more at inference to "think harder"

Key finding: for hard reasoning tasks, scaling test-time compute can substitute for more pre-training.
New scaling law: more thinking steps at inference → better answers on hard problems.

## Where We Are Now (2026)

```
Training scaling: hitting diminishing returns on web-scale text
                  → synthetic data to supplement
                  → new data sources (video, code, scientific papers)

Inference scaling: still strong signal
                   → reasoning models (o1, o3, R1) exploit this

Post-training:     most of the performance gap between labs is here
                   → RLHF, DPO, RLAIF, GRPO
                   → Small data, high quality > big data, low quality
```

## Sources

- Kaplan et al., OpenAI (2020): original scaling laws
- Hoffmann et al., DeepMind (2022): Chinchilla paper
- Sardana & Frankle, ICML 2024: "Beyond Chinchilla-Optimal"
- OpenAI o1 system card (Sep 2024): test-time compute
- LifeArchitect.ai: plain English Chinchilla explainer (Feb 2026)
