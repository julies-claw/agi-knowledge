---
tags: [identity, agents, security, commerce]
links: [./credentials.md, ./authn.md, ../commerce/a2a.md, ../commerce/trust.md]
status: growing
updated: 2026-03-22
---

# Agent Identity (Non-Human Identity)

Every existing identity framework assumes a human is somewhere in the loop. When agents transact autonomously, that assumption breaks. Agent identity is the unsolved problem underneath agentic commerce.

## The Core Problem

Traditional identity answers: "Who is this person?"  
Agent identity must answer: "What is this process, who authorized it, and what can it do?"

## Key Dimensions

- **Who created this agent?** (provenance)
- **Who authorized it to act?** (delegation chain)
- **What is it allowed to do?** (scope / capability)
- **Can it be held accountable?** (auditability)

## Current Approaches

- **API keys** — simple but no delegation, no scope, revocation is blunt
- **OAuth tokens** — designed for human-delegated access, being stretched to agents
- **DIDs (Decentralized Identifiers)** — cryptographic, self-sovereign, agent-friendly
- **TEE attestation** — proves the code running is what it claims to be
- **ERC-8004 / on-chain agent identity** — blockchain-based agent registration

## Open Problems

- No standard for expressing what an agent is *authorized* to do on behalf of a human
- Revocation is hard — how do you un-authorize a running agent mid-task?
- Reputation — agents have no credit history, no track record

## Related

- → [Credentials](./credentials.md)
- → [Authentication](./authn.md)
- → [TEE](./tee.md)
- → [A2A Commerce](../commerce/a2a.md)
