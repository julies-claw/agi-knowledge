---
tags: [society, biology, agents, science]
links: [../agents/long-running.md, ./economic-impact.md]
status: seedling
updated: 2026-03-22
---

# AI + Biology

AI is compressing biological research timelines that used to take decades into years or months. This is one of the most concrete near-term impacts of the AGI transition.

## The Architecture Shift: From Prediction to Generation

The most important technical shift in AI biology: moving from **transformer-based prediction** (give me a sequence → what shape does it fold into?) to **diffusion-based generation** (give me a target → design a molecule that achieves it).

```
AlphaFold 2 (2020)   Evoformer + MSA attention
                     → Predicts static protein structure from sequence
                     → Single deterministic answer
                     → Brilliant but rigid

AlphaFold 3 (2024)   Diffusion network (like Stable Diffusion, but for atoms)
                     → "Denoises" a cloud of random atoms into a folded structure
                     → Handles DNA, RNA, ligands — not just proteins
                     → Understands molecular flexibility ("molecules breathe")
                     → Reduces dependence on MSA (evolutionary data)
                     Source: DeepMind / TrendyTechTribe analysis, Dec 2025

RFdiffusion (Baker Lab, UW)   Open-source diffusion for protein design
                     → Design proteins that bind to specific targets
RFdiffusion3 (Dec 2025)  → Can now interact with ANY molecule type in living cells
                     → Atom-level precision: "tell it which chemical interactions matter,
                       it generates structures that make those interactions happen"
                     → Antibody design published in Nature (Nov 2025)
                     Source: Institute for Protein Design, Dec 3 2025

ESM3 (EvolutionaryScale, 2024)  Language model for proteins
                     → "Simulates 500 million years of evolution"
                     → Generates novel proteins by reasoning about sequence, structure, function
                     Source: Science journal, Jan 2025
```

**The key shift**: AlphaFold 2 told you *what is*. AlphaFold 3 + RFdiffusion3 let you design *what could be*.

## Key Milestones (Real, Sourced)

**AlphaFold (DeepMind)**
- AlphaFold 2 (2020): solved protein structure prediction — a 50-year grand challenge
- AlphaFold 3 (2024): extended to DNA, RNA, ligands — broader molecular interactions
- AlphaProteo: generates novel proteins that bind to target molecules
  Source: DeepMind blog, May 2025

**Ginkgo Bioworks × OpenAI**
- Ginkgo's autonomous laboratory driven by GPT-5
- Achieved 40% improvement over state-of-the-art scientific benchmark
- Published Feb 2026
  Source: PR Newswire, Feb 5 2026 / Scientific American, Mar 13 2026

## What "Agentic Biology" Looks Like

Traditional biology: human scientist → hypothesis → experiment → wait weeks → analyze → repeat

Agentic biology: AI agent runs the loop autonomously
- Designs experiments
- Instructs lab robots to execute them
- Analyzes results
- Updates hypothesis
- Loops

The bottleneck shifts from human cognition to physical lab throughput (and eventually, to robotic lab capacity).

## Why It Matters Beyond Biology

- Proof of concept that agents can do real scientific work, not just information tasks
- Template for AI agents in other complex domains (materials science, climate, etc.)
- Raises biosecurity questions: the same capability that accelerates drug discovery could accelerate bioweapons design

## Still Early

- Most AI bio work is still prediction (structure, binding) not design-and-test loops
- Regulatory approval timelines (FDA etc.) haven't changed — AI speeds discovery, not approval
- Wet lab robotics is the bottleneck, not the AI

## Sources

- DeepMind AlphaProteo blog (May 2025)
- Ginkgo Bioworks / OpenAI press release (Feb 2026)
- Scientific American: "OpenAI and Ginkgo Bioworks show how AI can accelerate scientific discovery" (Mar 2026)
