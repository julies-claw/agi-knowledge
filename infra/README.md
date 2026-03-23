# ⚙️ Infrastructure

The technical substrate that makes modern AI agents possible — from inference chips to protocol standards to energy infrastructure.

## What's in here

| Node | One-line summary |
|---|---|
| [inference-economics](./inference-economics.md) | 1,000× cost drop in 3 years — why it changes everything |
| [context-window-race](./context-window-race.md) | 4K → 1M tokens and what that enables |
| [agent-protocols](./agent-protocols.md) | MCP vs A2A vs ANP vs ACP — the protocol wars |
| [mcp-ecosystem](./mcp-ecosystem.md) | MCP adoption, 1000s of servers, security risks |
| [agent-memory-systems](./agent-memory-systems.md) | Mem0 vs Letta — two philosophies of agent memory |
| [voice-agents](./voice-agents.md) | Real-time voice AI — ElevenLabs, OpenAI Realtime |
| [ai-energy](./ai-energy.md) | Nuclear power deals — Microsoft, Google, Amazon, Meta |
| [tools](./tools.md) | Tool use and APIs — how agents extend their capabilities |
| [memory](./memory.md) | Memory types and the forgetting problem |

## The Infrastructure Stack (Bottom to Top)

```
Energy (nuclear, grid)
    ↓
Hardware (H100/Blackwell, Groq LPU, Cerebras)
    ↓
Inference optimization (vLLM, TensorRT, speculative decoding)
    ↓
Foundation models (GPT, Claude, Gemini, Llama)
    ↓
Context management (context window, memory systems)
    ↓
Tool connectivity (MCP servers, APIs)
    ↓
Agent protocols (A2A, ANP for inter-agent communication)
    ↓
Agent applications (coding, research, commerce)
```

## The 1,000× Cost Drop — Why Everything Changed

```
2022: $20 per million tokens → only batch/research use cases viable
2026: $0.04 per million tokens → real-time, interactive, agentic use cases viable
```

This single trend unlocks agentic commerce: at $20/M tokens, running 1000 agent steps cost $20. At $0.04, it's $0.04 — cheap enough to run autonomously on low-value tasks.

## Real Infrastructure Deployments

- **OpenComputer** (Mar 2026): purpose-built persistent VMs for long-running agent workloads
- **Coinbase Base**: L2 settlement layer for agent micropayments
- **Phala Network / Marlin**: TEE-based confidential compute for agent key management
- **AgentPatch**: MCP marketplace (Feb 2026)
- **Groq LPU**: ~500 tokens/second inference — enables real-time voice agents
