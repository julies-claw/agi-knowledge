# 🧠 Models

Foundation models, training paradigms, and the economics of AI capability. How we got here and where the frontier is moving.

## What's in here

| Node | One-line summary |
|---|---|
| [training-paradigms](./training-paradigms.md) | Pre-training → RLHF → RL → test-time compute |
| [scaling-laws](./scaling-laws.md) | Chinchilla, inference scaling, the new axes of capability |
| [foundation](./foundation.md) | GPT, Claude, Gemini, Llama — the landscape |
| [reasoning](./reasoning.md) | o1, o3, R1 — thinking before answering |
| [open-vs-closed](./open-vs-closed.md) | The gap is closing — what that means |
| [multimodal](./multimodal.md) | Vision, audio, video, computer use |
| [image-generation](./image-generation.md) | Midjourney, Flux, Imagen — production guide |
| [video-generation](./video-generation.md) | Sora 2, Veo 3.1, Kling 3.0 |
| [synthetic-data](./synthetic-data.md) | Training on AI-generated data — risks and flywheels |
| [interpretability](./interpretability.md) | Understanding what models actually do internally |

## The Big Picture

Model capability has scaled faster than anyone predicted:
- **2020**: GPT-3 impresses but can't follow instructions
- **2022**: ChatGPT shows instruction-following at scale
- **2024**: Models match or exceed humans on many professional benchmarks
- **2026**: Models are running as autonomous agents doing real work

The next frontier isn't bigger pre-training — it's **better post-training** (RL, RLAIF) and **smarter inference** (test-time compute, reasoning models).

## Real-World Benchmarks (2026)

- Claude Opus 4.6: **80.8% on SWE-bench Verified** (resolving real GitHub issues)
- Claude Sonnet 4.5: **74.6% on GAIA** (general multi-step task completion)
- DeepSeek R1: matches o1 on reasoning benchmarks at open-weight
- Models now routinely pass bar exams, medical board exams, coding interviews

## Key Tensions

- **Open vs. closed**: Llama/DeepSeek nearly at GPT-4 level — commoditization accelerating
- **Training vs. inference**: inference now dominates GPU demand
- **Capability vs. alignment**: faster capability scaling requires faster safety research
