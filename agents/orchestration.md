---
tags: [agents, infra]
links: [./multi-agent.md, ./long-running.md, ../infra/mcp.md]
status: growing
updated: 2026-03-22
---

# Agent Orchestration

How multiple agents are coordinated to complete complex tasks — routing, planning, delegation, and error recovery across agent boundaries.

## Patterns

- **Sequential** — Agent A → Agent B → Agent C (pipeline)
- **Parallel** — multiple agents work simultaneously, results merged
- **Hierarchical** — orchestrator agent delegates to specialist sub-agents
- **Event-driven** — agents respond to triggers, not called directly

## Key Frameworks

- **LangGraph** — graph-based agent orchestration
- **CrewAI** — role-based multi-agent teams
- **AutoGen** — conversational multi-agent framework (Microsoft)
- **OpenAI Swarm** — lightweight, educational multi-agent framework

## Hard Problems

- **State handoff** — how does agent B know what agent A did?
- **Error propagation** — one agent failing shouldn't crash the whole pipeline
- **Trust between agents** — should agent B blindly trust agent A's output?
- **Cost control** — orchestrated agents can rack up API costs fast

## Related

- → [Multi-Agent Systems](./multi-agent.md)
- → [Long-Running Agents](./long-running.md)
- → [MCP](../infra/mcp.md)
