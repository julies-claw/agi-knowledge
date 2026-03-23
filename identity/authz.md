---
tags: [identity, security, agents]
links: [./authn.md, ./credentials.md, ./agent-identity.md]
status: seedling
updated: 2026-03-22
---

# Authorization (AuthZ)

Authorization = what are you allowed to do?  
AuthN says "you are who you claim." AuthZ says "and here's what that lets you do."

## Models

- **RBAC** (Role-Based) — permissions tied to roles (admin, user, agent)
- **ABAC** (Attribute-Based) — permissions based on attributes (time, location, context)
- **ReBAC** (Relationship-Based) — permissions based on relationships (Google Zanzibar model)
- **Capability-based** — bearer of a token can do exactly what the token says, no more

## For Agents: Capability-Based is Best

Agents should carry tokens that encode exactly what they're allowed to do:
- "Transfer up to $10 USDC to address 0x..."
- "Read emails from inbox, do not send"
- "Browse web, do not submit forms"

This is the principle of **least privilege** applied to agents.

## Open Problem: Delegation Chains

When agent A delegates to agent B, what subset of A's permissions should B get?  
No standard answer yet. This is the hardest authz problem in the agentic era.

## Related

- → [Authentication](./authn.md)
- → [Credentials](./credentials.md)
- → [Agent Identity](./agent-identity.md)
