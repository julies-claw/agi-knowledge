---
tags: [agents, infra, cloud]
links: [./long-running.md, ./orchestration.md, ../infra/mcp.md]
status: seedling
updated: 2026-03-22
---

# Open Cloud Agents

Agents that run in cloud environments, accessible via APIs, often as a service. The "open" framing implies interoperability — agents that can be called by other agents, composed into pipelines, and discovered dynamically.

## What Makes Them "Open"

- Standardized interfaces (e.g. MCP, OpenAI tool format)
- Discoverable via registries or marketplaces
- Callable by other agents, not just humans
- Stateless or stateful depending on design

## Examples / Players

- OpenAI Assistants API
- Anthropic Claude (via API)
- Google Vertex AI agents
- Custom agents deployed on cloud infra (AWS, GCP, Azure)

## Key Tensions

- **Openness vs. security** — discoverable = potentially exploitable
- **Stateless vs. stateful** — stateless is simpler but limits long-horizon tasks
- **Vendor lock-in** — "open" often means open to that platform's ecosystem

## Related

- → [Long-Running Agents](./long-running.md)
- → [Orchestration](./orchestration.md)
- → [MCP](../infra/mcp.md)
