---
tags: [infra, agents, tools]
links: [./tools.md, ../agents/orchestration.md, ../agents/open-cloud.md]
status: growing
updated: 2026-03-22
---

# MCP — Model Context Protocol

MCP is an open protocol by Anthropic that standardizes how AI models connect to external tools, data sources, and services. Think of it as "USB-C for AI agents."

## What It Solves

Before MCP: every tool integration was custom. Each LLM app had its own way of calling tools.  
After MCP: any MCP-compatible agent can use any MCP-compatible tool, out of the box.

## Architecture

```
Host (LLM app)
    └── MCP Client
            ↕ MCP Protocol
        MCP Server (tool/data source)
            └── Resources, Tools, Prompts
```

- **MCP Servers** — expose capabilities (search, database, file system, APIs)
- **MCP Clients** — LLM apps that consume those capabilities
- **Transport** — stdio (local) or HTTP+SSE (remote)

## Why It Matters

- **Composability** — build once, use anywhere
- **Discoverability** — agents can dynamically find and use tools
- **Standardization** — reduces integration overhead across the ecosystem
- **Security surface** — also centralizes attack surface (SSRF, prompt injection via tools)

## Adoption

- Anthropic Claude (native support)
- OpenAI (announced support)
- Growing ecosystem of MCP servers (GitHub, Slack, databases, etc.)

## Related

- → [Tools & APIs](./tools.md)
- → [Orchestration](../agents/orchestration.md)
