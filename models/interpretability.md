---
tags: [models, safety, society]
links: [../society/alignment.md, ./foundation.md]
status: seedling
updated: 2026-03-22
---

# Mechanistic Interpretability — Understanding What Models Actually Do

Interpretability research tries to reverse-engineer neural networks: what are the internal representations, circuits, and features that produce model behavior?

## Why It Matters

- **Safety**: can't align what you can't understand
- **Trust**: auditing model behavior for deployment decisions
- **Science**: understand intelligence itself
- **Debugging**: find and fix specific failure modes

## Anthropic's Research Program

Anthropic is the most prominent lab doing mechanistic interpretability:

**"Tracing the thoughts of a large language model"** (Mar 27, 2025)
- Traced internal reasoning steps in Claude
- Found that models sometimes "plan ahead" in ways not visible in output tokens
- Evidence of internal representations that don't map to human concepts

**Circuits work** (transformer-circuits.pub, ongoing)
- Identify "circuits" — small subgraphs of model that implement specific behaviors
- E.g., induction heads (enable in-context learning), attention patterns
- July 2025 update published

**Open-source interpretability tools** (Jun 2025)
- Anthropic released tooling for the broader research community
- Sparse Autoencoder (SAE) techniques for finding monosemantic features

Source: Anthropic research blog (Mar 2025), TheSequence (Jun 2025), Goodfire/Neuronpedia (Aug 2025)

## Key Concepts

- **Superposition**: models represent more features than they have neurons by storing them in superposition — makes interpretation hard
- **Monosemanticity**: a neuron that fires for only one concept (rare, but interpretable)
- **Features**: directions in activation space that correspond to meaningful concepts
- **Circuits**: subgraphs that implement specific capabilities

## Current State

Still early. We can interpret small models and specific behaviors. Frontier model internals are largely a black box. The gap between "understand a small transformer" and "understand GPT-5" is vast.

## Sources

- Anthropic: "Tracing the thoughts of a large language model" (Mar 27, 2025)
- transformer-circuits.pub: Circuits Updates July 2025
- TheSequence: "Inside Anthropic's New Open Source AI Interpretability Tools" (Jun 2025)
- Goodfire/Neuronpedia: "The Circuits Research Landscape" (Aug 2025)
