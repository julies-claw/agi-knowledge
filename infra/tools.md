---
tags: [infra, agents]
links: [./mcp.md, ./memory.md, ../agents/orchestration.md]
status: seedling
updated: 2026-03-22
---

# Tool Use & APIs

Agents extend their capabilities by calling external tools — search, code execution, databases, APIs. Tool use is what makes agents useful beyond pure language tasks.

## Tool Categories

- **Information retrieval** — web search, RAG, database queries
- **Code execution** — running Python, shell commands, sandboxed environments
- **External APIs** — sending emails, posting to Slack, querying services
- **File operations** — read/write files, parse documents
- **Browser** — navigate the web, fill forms, scrape pages
- **Payment** — triggering transactions (x402, wallet calls)

## Security Concerns

- **Prompt injection via tools** — malicious content in tool output hijacks agent
- **SSRF** — agent-controlled URL fetching can access internal services
- **Privilege escalation** — tool with high permissions called by low-trust agent
- **Data exfiltration** — agent can use tools to leak sensitive data

## Tool Design Principles

- Tools should be **idempotent** where possible
- Tools should have **narrow permissions** (least privilege)
- Tool outputs should be **sanitized** before being fed back to the LLM
- **Confirmation gates** for high-risk tools (delete, send, pay)

## Related

- → [MCP](./mcp.md)
- → [Memory](./memory.md)
