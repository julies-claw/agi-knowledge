---
tags: [infra, agents, tools]
links: [./mcp.md, ../agents/orchestration.md, ../agents/workflow-to-agentic.md]
status: growing
updated: 2026-03-22
---

# MCP Ecosystem — Adoption in 2025–2026

MCP (Model Context Protocol) went from Anthropic's internal spec to the de facto standard for agent tool integration within about 12 months.

## Why It Took Off

- Anthropic released it as open standard (not proprietary)
- OpenAI announced support → instantly became cross-platform
- Developer-friendly: simple JSON-RPC over stdio or HTTP/SSE
- Solves a real pain: every team was building custom tool integrations

## Scale (Early 2026)

- Thousands of community-built MCP servers available
- Major integrations: GitHub, Slack, PostgreSQL, Brave Search, Google Drive, filesystem, web browsers
- AgentPatch: dedicated MCP marketplace (Feb 2026)
- Thoughtworks named MCP a key trend in their 2025 assessment

Source: Postproxy.dev "Best MCP servers 2026" (Mar 17, 2026); Thoughtworks (Dec 2025); KnowMine (Mar 10, 2026)

## Architecture Recap

```
MCP Host (e.g. Claude Desktop, custom agent)
    └── MCP Client
            ↕ JSON-RPC over stdio / HTTP+SSE
        MCP Server (exposes tools, resources, prompts)
            └── GitHub API / database / filesystem / etc.
```

## What MCP Servers Expose

- **Tools**: executable functions the agent can call
- **Resources**: data/files the agent can read (e.g., filesystem, database rows)
- **Prompts**: pre-built prompt templates

## Security Concerns

MCP creates a standardized attack surface:
- A malicious MCP server can inject instructions into the agent's context
- SSRF via resource fetching
- Prompt injection through tool responses
- Over-broad permissions in MCP server implementations

The convenience of "plug in any tool" comes with "plug in any attack vector."

## A2A Protocol (Google, Apr 2025)

Google released Agent-to-Agent (A2A) protocol — complementary to MCP:
- MCP: agent ↔ tools
- A2A: agent ↔ agent

Both are now converging under the Agentic AI Foundation open governance effort.

## Sources

- Postproxy.dev: "Best MCP servers in 2026" (Mar 17, 2026)
- KnowMine: "The MCP Ecosystem in 2025" (Mar 10, 2026)
- Thoughtworks: "The Model Context Protocol's Impact on 2025" (Dec 2025)
- Zylos Research: A2A + MCP convergence (Mar 2026)
