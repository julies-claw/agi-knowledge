---
tags: [infra, agents, commerce]
links: [./mcp.md, ./mcp-ecosystem.md, ../commerce/a2a.md, ../agents/multi-agent.md]
status: growing
updated: 2026-03-22
---

# Agent Communication Protocols — MCP vs A2A vs ANP vs ACP

Four protocols are competing to become the "HTTP of the agent internet." They solve different parts of the problem.

## The Four Protocols

```
MCP (Model Context Protocol)    Anthropic, Nov 2024
                                 Agent ↔ Tools
                                 Single agent connecting to external data/tools
                                 "USB-C for tools"
                                 Won: de facto standard, OpenAI adopted it

A2A (Agent-to-Agent Protocol)   Google, Apr 2025
                                 Agent ↔ Agent
                                 Agents discovering and calling other agents
                                 Built on HTTP + JSON-RPC
                                 Complementary to MCP, not competing

ANP (Agent Network Protocol)    Open source / community
                                 Agent ↔ Agent (decentralized)
                                 Based on DID (Decentralized Identifiers)
                                 Focus: trustless discovery, no central registry
                                 Still early

ACP (Agent Communication Protocol)  IBM + open governance
                                 Agent ↔ Agent (async messaging)
                                 Built on REST
                                 Focus: enterprise async patterns
                                 Less adoption
```

Source: Dev.to / Dr. Hernani Costa (Jul 2025); Zylos Research (Mar 5 and Feb 15, 2026)

## How They Fit Together

| Protocol | Connects | When to use |
|---|---|---|
| MCP | Agent ↔ Tool/Data | Agent needs to call a database, API, filesystem |
| A2A | Agent ↔ Agent (direct) | One agent needs to delegate to another |
| ANP | Agent ↔ Agent (decentralized) | Cross-org, trustless agent interaction |
| ACP | Agent ↔ Agent (async) | Enterprise, fire-and-forget messaging |

The vision: MCP handles "what tools does this agent have access to?" while A2A/ANP handle "how do agents find and talk to each other?"

## Why This Matters for Commerce

A2A + payment rails = the infrastructure for agent marketplaces:
- Agent A discovers Agent B via A2A
- Agent A pays Agent B via x402/stablecoin
- Agent B delivers service
- All without human intermediaries

The Agentic AI Foundation (open governance body) is working to converge these standards.

## Current State of Adoption (Mar 2026)

- **MCP**: dominant, thousands of servers, all major LLM providers support it
- **A2A**: growing, Google pushing it, gaining traction
- **ANP**: niche, decentralized purists
- **ACP**: limited outside IBM ecosystem

## Sources

- Dev.to: "AI Agent Protocols: MCP vs A2A vs ANP vs ACP" (Jul 6, 2025)
- Zylos Research: "Agent-to-Agent Communication Protocol Standards" (Feb 15, 2026)
- Zylos Research: "The Protocol Layer" (Mar 5, 2026)
