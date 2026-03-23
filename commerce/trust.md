---
tags: [commerce, identity, agents]
links: [./a2a.md, ./payments.md, ../identity/agent-identity.md]
status: seedling
updated: 2026-03-22
---

# Trust & Settlement in Agentic Commerce

How do agents establish trust with each other, and how do transactions settle when neither party is human?

## Trust Layers

1. **Identity trust** — is this agent who it claims to be?
2. **Authorization trust** — is this agent allowed to commit to this transaction?
3. **Execution trust** — will this agent actually deliver what it promised?
4. **Settlement trust** — will payment clear, and is it final?

## Settlement Approaches

- **Atomic swaps** — payment and delivery happen simultaneously (trustless)
- **Escrow** — third-party holds funds until delivery confirmed
- **Reputation-based credit** — agents with track records can transact on credit
- **Smart contracts** — code enforces the terms, no counterparty trust needed

## The Bootstrapping Problem

New agents have no reputation. Reputation systems need transactions to function. How does a new agent earn trust before it has a history?

Possible solutions:
- Human guarantors (vouching for an agent)
- Staking / collateral
- Attestation from a known issuer

## Related

- → [A2A Commerce](./a2a.md)
- → [Payments](./payments.md)
- → [Agent Identity](../identity/agent-identity.md)
