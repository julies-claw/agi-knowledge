# 🗺️ Knowledge Map

> The top-level view. Every node and how they connect.
> Last updated: 2026-03-22 | Total nodes: 40+

```
AGI Era
│
├── 🧠 MODELS
│   ├── Foundation models            → models/foundation.md
│   ├── Training paradigms (timeline)→ models/training-paradigms.md  ★ start here
│   ├── Scaling laws                 → models/scaling-laws.md
│   ├── Reasoning models             → models/reasoning.md
│   ├── Open vs. closed models       → models/open-vs-closed.md
│   ├── Multimodal                   → models/multimodal.md
│   ├── Image generation             → models/image-generation.md
│   ├── Video generation             → models/video-generation.md
│   ├── Synthetic data               → models/synthetic-data.md
│   └── Interpretability             → models/interpretability.md
│
├── 🤖 AGENTS
│   ├── Context engineering (timeline)→ agents/context-engineering.md  ★ key concept
│   ├── Long-running agents          → agents/long-running.md
│   ├── Computer use agents          → agents/computer-use.md
│   ├── Coding agents (timeline)     → agents/coding-agents.md
│   ├── Workflow → Agentic (timeline)→ agents/workflow-to-agentic.md
│   ├── Orchestration                → agents/orchestration.md
│   ├── Multi-agent systems          → agents/multi-agent.md
│   ├── Self-improving agents        → agents/self-improving.md
│   └── Open cloud agents            → agents/open-cloud.md
│
├── 🔐 IDENTITY & SECURITY
│   ├── Agent identity (non-human)   → identity/agent-identity.md  ★ core problem
│   ├── Credentials                  → identity/credentials.md
│   ├── Authentication               → identity/authn.md
│   ├── Authorization                → identity/authz.md
│   ├── TEE & self-custody           → identity/tee.md
│   └── Prompt injection             → identity/prompt-injection.md  ★ active threat
│
├── 📡 OBSERVABILITY
│   ├── Tracing & logging            → observability/tracing.md
│   ├── Agent benchmarks             → observability/agent-benchmarks.md
│   ├── Evals                        → observability/evals.md
│   ├── Hallucination                → observability/hallucination.md
│   └── Reliability / SLOs           → observability/reliability.md
│
├── 💸 COMMERCE
│   ├── A2A — Agent-to-agent         → commerce/a2a.md  ★ emerging category
│   ├── Agentic payments             → commerce/payments.md
│   ├── x402 protocol                → commerce/x402.md
│   ├── Agent wallets (Coinbase)     → commerce/agent-wallets.md
│   ├── Trust & settlement           → commerce/trust.md
│   └── AI in legal                  → commerce/ai-legal.md
│
├── ⚙️ INFRA
│   ├── Inference economics (1000×)  → infra/inference-economics.md  ★ key trend
│   ├── Context window race          → infra/context-window-race.md
│   ├── Agent protocols (MCP/A2A/ANP)→ infra/agent-protocols.md
│   ├── MCP ecosystem                → infra/mcp-ecosystem.md
│   ├── Agent memory systems         → infra/agent-memory-systems.md
│   ├── Voice agents                 → infra/voice-agents.md
│   ├── AI energy / nuclear          → infra/ai-energy.md
│   ├── Tools & APIs                 → infra/tools.md
│   └── Memory & storage             → infra/memory.md
│
└── 🌍 SOCIETY
    ├── AI + Biology (diffusion)     → society/ai-bio.md  ★ compounding fast
    ├── Humanoid robots              → society/humanoid-robots.md
    ├── AI search disruption         → society/ai-search-disruption.md
    ├── AI labor impact              → society/ai-labor-impact.md
    ├── AI investment landscape      → society/ai-investment-landscape.md
    ├── AI governance 2026           → society/ai-governance-2026.md
    ├── Alignment & safety           → society/alignment.md
    └── Economic impact              → society/economic-impact.md
```

## ★ Start Here (Most Impactful Nodes)

1. `models/training-paradigms.md` — understand the full arc: pre-training → RLHF → RL → test-time compute
2. `agents/context-engineering.md` — why "prompt engineering" is an outdated frame
3. `identity/agent-identity.md` — the unsolved problem under all of agentic commerce
4. `identity/prompt-injection.md` — the #1 active security threat to agents
5. `infra/inference-economics.md` — why 1,000× cost drop changes everything
6. `commerce/a2a.md` — agent-to-agent commerce, still early but building fast

## Key Cross-Connections

- **Agent identity** ↔ **A2A commerce** — you can't have trustless A2A without identity primitives
- **Long-running agents** ↔ **Observability** — hard to trust what you can't see
- **Test-time compute** ↔ **Inference economics** — reasoning models are expensive; cost collapse makes them viable
- **MCP** ↔ **A2A** ↔ **ANP** — the protocol stack for the agentic internet
- **Open-weight models** ↔ **Inference economics** — open models + cheap inference = accessible frontier AI
- **AI search disruption** ↔ **Agentic SEO** — the content economy is being restructured
- **x402** ↔ **Agent wallets** ↔ **A2A** — the payment rails for the agent economy
- **Humanoid robots** ↔ **Long-running agents** — the physical instantiation of autonomous agents
- **AI biology** ↔ **Diffusion models** — AlphaFold 3 is a diffusion model; design replaces prediction
