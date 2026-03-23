---
tags: [agents, infra, tools, commerce]
links: [./orchestration.md, ../commerce/a2a.md, ../infra/mcp.md]
status: growing
updated: 2026-03-22
---

# Workflow Automation → Agentic AI — Evolution

How the "make software do things automatically" stack has evolved.

## Timeline

```
~2015–2022     Workflow Automation (rule-based)
               → Zapier, Make (Integromat), n8n
               → "If X happens, do Y" — trigger + action
               → No reasoning, deterministic, brittle on edge cases
               → n8n: open-source, self-hosted, 400+ integrations

2022–2023      LLM-augmented workflows
               → Add LLM as a step inside a workflow
               → Zapier AI, n8n AI nodes
               → Still fundamentally rule-based, LLM is one box in the diagram

2023–2024      Agent frameworks (code-first)
               → LangChain: chains + tools + memory — flexible but verbose
               → LangGraph: graph-based state machines for agents
               → CrewAI: role-based multi-agent teams ("hire a crew")
               → AutoGen (Microsoft): conversational multi-agent framework
               → Mental model: developer builds the agent architecture in code

2024–2025      No-code/low-code agent builders
               → n8n adds full agentic mode (agents inside workflows)
               → Flowise, Dify: visual agent builders
               → "Vibe coding" + agent builders: non-engineers can deploy agents

2025–2026      Agent-native platforms
               → LangGraph dominates complex stateful agents (80% of top workflows
                 projected to use LangGraph or CrewAI by end of 2026)
               → Salesforce AgentExchange: $800M ARR, 18,500 enterprise customers
               → Anthropic Claude Marketplace: launched Mar 7, 2026
                 — zero commission, enterprise procurement model (like AWS Marketplace)
                 — launch partners: Snowflake, GitLab, Harvey AI, Rogo, Replit, Lovable Labs
               → OpenAI GPT Store: 3M GPTs created, but ~$0.03/conversation payouts
                 — scale without meaningful creator economics
               Sources: Zylos Research (Mar 9, 2026), multiple
```

## The Five Agent Marketplace Models (2026)

Per Zylos Research (Mar 2026):
1. **Enterprise procurement** — Claude Marketplace (zero commission, enterprise budget redirect)
2. **Creator economy** — GPT Store (scale but poor payouts)
3. **Enterprise CRM-native** — Salesforce AgentExchange ($800M ARR)
4. **Open protocol** — MCP marketplace (AgentPatch), A2A, Agent Skills
5. **Vertical-specific** — domain marketplaces (legal, finance, healthcare)

## Key Tension Right Now

**Centralized marketplaces** (OpenAI, Anthropic, Salesforce):
- Trust + discoverability
- But: platform lock-in, commission extraction

**Open protocols** (MCP, A2A, Agent Skills):
- Interoperability + freedom
- But: fragmented, harder discovery

**Security gap**: 88% of orgs report AI agent security incidents; 90% of deployed agents are over-permissioned (Zylos, 2026)

## Sources

- Zylos Research: "AI Agent Marketplaces and Distribution Channels" (Mar 9, 2026)
- AIAgentBase blog: "LangGraph vs CrewAI vs AutoGen vs n8n" (Feb 24, 2026)
- Anthropic Claude Marketplace launch (Mar 7, 2026)
