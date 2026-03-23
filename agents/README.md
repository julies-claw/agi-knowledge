# 🤖 Agents

How AI agents are built, deployed, and evolve. The shift from single-turn assistants to autonomous, long-horizon systems.

## What's in here

| Node | One-line summary |
|---|---|
| [context-engineering](./context-engineering.md) | Prompt engineering → RAG → dynamic context management |
| [long-running](./long-running.md) | Agents that work across sessions, hours or days |
| [computer-use](./computer-use.md) | Agents that control a desktop or browser |
| [coding-agents](./coding-agents.md) | Copilot → Cursor → Claude Code — the full arc |
| [workflow-to-agentic](./workflow-to-agentic.md) | Zapier → LangChain → agent marketplaces |
| [orchestration](./orchestration.md) | Coordinating multiple agents |
| [multi-agent](./multi-agent.md) | Systems where agents interact with each other |
| [self-improving](./self-improving.md) | Agents that modify their own behavior |
| [open-cloud](./open-cloud.md) | Cloud-hosted, interoperable agents |

## The Core Progression

```
Single-turn assistant
    ↓
Multi-turn with memory
    ↓
Tool-using agent (search, code, APIs)
    ↓
Long-running agent (sessions spanning hours/days)
    ↓
Multi-agent orchestration
    ↓
Autonomous agents with real-world consequences (payments, actions)
```

## Real-World Deployments (Now)

- **Cognition Devin**: first "AI software engineer" — hired by companies for autonomous coding tasks
- **GitHub Copilot Workspace**: end-to-end task completion from issue to PR
- **OpenAI Operator**: autonomous web agent used for booking, purchasing, form filling
- **Claude Code**: 80.8% on SWE-bench Verified — resolving real GitHub issues autonomously
- **Manus Desktop** (Mar 2026): long-running research and multi-step task agent

## Open Problems

- Reliability over long horizons (agents still fail ~30-50% on hard tasks)
- Cost — complex agentic workflows can cost $1-10 per task
- Trust and authorization — who approves what the agent does?
