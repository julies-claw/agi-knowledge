---
tags: [models, infra]
links: [./foundation.md, ./training-paradigms.md]
status: growing
updated: 2026-03-22
---

# Open-Weight vs. Closed Models — The 2026 Landscape

The gap between open-weight and closed frontier models has nearly closed. This changes everything about the AI industry structure.

## The Gap Is Closing Fast

```
2023    GPT-4 dominates, open models 2–3 generations behind
        LLaMA 2 (Meta): useful but clearly weaker than GPT-4

2024    DeepSeek V2 shocks: near-GPT-4 quality at fraction of cost
        Llama 3.1 405B: first open model competitive with GPT-4 class
        Mistral Large 2: strong European open option

2025    DeepSeek R1: matches o1 on reasoning benchmarks
        DeepSeek V3: GPT-4o level at open weights
        Qwen 2.5 (Alibaba): strong multilingual performance
        Llama 3.3 70B: punches above its weight class

2026    Open-source AI "closing the gap" on all major benchmarks
        (Tech Insider, Mar 2026)
```

## The Main Open-Weight Players

| Model Family | Creator | Strengths |
|---|---|---|
| Llama | Meta | Ecosystem, fine-tuning community, most widely deployed |
| DeepSeek | DeepSeek (China) | Reasoning (R1), cost efficiency (V3), MoE architecture |
| Mistral / Mixtral | Mistral AI (France) | Efficient, European, strong instruction following |
| Qwen | Alibaba | Multilingual, long context, strong on coding |

Source: Machine Brief, "Open Source LLM Comparison 2026" (Mar 4, 2026)

## Why Open-Weight Matters

- **Customization**: fine-tune on proprietary data without sending data to a vendor
- **Cost**: run locally or on cheap inference infrastructure
- **Privacy**: keep sensitive data in-house
- **Geopolitical**: reduces dependence on US-based AI providers
- **Competition**: keeps closed providers from extracting monopoly rents

## What Closed Models Still Win On

- **Frontier capability** (slightly, at time of writing)
- **Multimodality** (vision, voice, video — open lags here)
- **Safety/alignment** (more resources for RLHF, red-teaming)
- **Product integration** (API ecosystems, fine-tuning services)

## The "Open Weight" Caveat

"Open-weight" ≠ "open-source". Meta releases weights but not training code or data. DeepSeek releases more. True open-source AI (training code + data + weights) is still rare. The term is contested.

## Sources

- Machine Brief: "Open Source LLM Comparison 2026" (Mar 4, 2026)
- Tech Insider: "Open Source AI Models Are Closing the Gap" (Mar 10, 2026)
- DigiDai: "The Open-Weight AI War" (Mar 13, 2026)
