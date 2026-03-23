---
tags: [identity, security, agents]
links: [../infra/tools.md, ./agent-identity.md, ./authz.md]
status: growing
updated: 2026-03-22
---

# Prompt Injection — The #1 Agent Security Threat

Prompt injection is the attack class where malicious content in the agent's environment hijacks its behavior. It's no longer theoretical — it's being observed in the wild.

## Two Types

**Direct prompt injection**: attacker directly sends malicious instructions to the LLM
(e.g., jailbreak in the user message)

**Indirect prompt injection (IDPI)**: attacker embeds malicious instructions in *content the agent reads*
- Hidden text in a webpage the agent browses
- Instructions in a PDF the agent processes
- Malicious content in a code file the agent reviews
- Instructions in an email subject line an agent processes

The agent unknowingly follows the attacker's instructions, not the user's.

## Observed in the Wild (2026)

Unit 42 (Palo Alto Networks) published first large-scale real-world telemetry:
- IDPI is **actively weaponized**, not just theoretical
- First observed case: **AI-based ad review evasion** — attackers embed hidden instructions in ad content so AI reviewers approve malicious ads
- Impact scales with agent permissions: a high-privilege agent executing IDPI = much worse than a low-privilege one

Source: Unit 42, "Fooling AI Agents: Web-Based Indirect Prompt Injection Observed in the Wild" (Mar 3, 2026)

## Why Agents Make This Worse

Traditional prompt injection affects chatbots. Agents are worse because:
1. **Agents take actions** — a hijacked agent can send emails, make payments, delete files
2. **Agents browse the web** — every webpage is a potential attack surface
3. **Agents are over-permissioned** — 90% of deployed agents have more permissions than they need (Zylos, 2026)
4. **No standard defenses** — the field doesn't have equivalent of SQL injection parameterization

## Defense Approaches (Incomplete)

- **Sanitize tool outputs** before feeding back to LLM
- **Least privilege** — agents should only have permissions for current task
- **Separate trust boundaries** — user instructions vs. retrieved content vs. tool outputs
- **Confirmation gates** for high-risk actions
- **Input validation** on agent inputs

None of these fully solve the problem. It's an open research area.

## Sources

- Unit 42 / Palo Alto Networks (Mar 3, 2026): first in-wild IDPI telemetry
- Zylos Research (Mar 2026): 90% of agents over-permissioned
- Medium: "The Lethal Trifecta: How Indirect Prompt Injection Is Breaking Agentic AI" (Mar 2026)
