# 🗺️ Knowledge Map

> The top-level view. Every major node and how they connect.

```
AGI Era
│
├── 🤖 AGENTS
│   ├── Long-running agents          → agents/long-running.md
│   ├── Open cloud / cloud agents    → agents/open-cloud.md
│   ├── Self-improving agents        → agents/self-improving.md
│   ├── Agent orchestration          → agents/orchestration.md
│   └── Multi-agent systems (MAS)    → agents/multi-agent.md
│
├── 🔐 IDENTITY & SECURITY
│   ├── Credentials                  → identity/credentials.md
│   ├── Authentication (AuthN)       → identity/authn.md
│   ├── Authorization (AuthZ)        → identity/authz.md
│   ├── Agent identity (non-human)   → identity/agent-identity.md
│   └── TEE & self-custody           → identity/tee.md
│
├── 📡 OBSERVABILITY
│   ├── Tracing & logging            → observability/tracing.md
│   ├── Evals & benchmarks           → observability/evals.md
│   └── Reliability / SLOs           → observability/reliability.md
│
├── 💸 COMMERCE
│   ├── Agentic payments             → commerce/payments.md
│   ├── A2A (agent-to-agent)         → commerce/a2a.md
│   ├── x402 protocol                → commerce/x402.md
│   └── Trust & settlement           → commerce/trust.md
│
├── 🧱 MODELS
│   ├── Foundation models            → models/foundation.md
│   ├── Reasoning models             → models/reasoning.md
│   └── Multimodal                   → models/multimodal.md
│
├── ⚙️ INFRA
│   ├── MCP (Model Context Protocol) → infra/mcp.md
│   ├── Tool use & APIs              → infra/tools.md
│   └── Memory & storage             → infra/memory.md
│
└── 🌍 SOCIETY
    ├── Alignment & safety           → society/alignment.md
    ├── Governance                   → society/governance.md
    └── Economic impact              → society/economic-impact.md
```

## Key Cross-Connections

- **Agent identity** ↔ **Credentials** — agents need non-human identity primitives
- **Long-running agents** ↔ **Observability** — hard to debug what you can't see
- **Self-improving agents** ↔ **Alignment** — capability growth requires safety guardrails
- **A2A commerce** ↔ **Agent identity** — trust requires knowing who (what) you're transacting with
- **x402** ↔ **Credentials** — payment authorization is an identity problem
- **Open cloud agents** ↔ **Infra/MCP** — cloud-native agents need standardized tool protocols
