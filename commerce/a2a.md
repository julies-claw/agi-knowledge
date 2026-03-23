---
tags: [commerce, agents, identity]
links: [./payments.md, ./trust.md, ./x402.md, ../identity/agent-identity.md, ../agents/multi-agent.md]
status: growing
updated: 2026-03-22
---

# A2A — Agent-to-Agent Commerce

When AI agents transact with each other autonomously — buying, selling, negotiating, settling — without a human approving each transaction.

## Why A2A is Different

Human commerce has millennia of infrastructure: legal contracts, banks, escrow, reputation systems. A2A commerce starts from scratch, with processes not people as the transacting entities.

## The Core Trust Problem

> "My agent needs to negotiate with your agent and neither side has a reason to trust the other. There is no shared state, no reputation system, no way to verify that the agent on the other side is authorized to commit capital on behalf of its principal."

This is the fundamental unsolved problem.

## Required Primitives

1. **Agent identity** — verifiable, non-repudiable identity for each agent
2. **Authorization proof** — cryptographic proof of what the agent is allowed to spend
3. **Reputation** — track record of past transactions (doesn't exist yet)
4. **Settlement** — atomic, trustless payment finalization
5. **Dispute resolution** — what happens when something goes wrong?

## Emerging Approaches

- **x402** — HTTP payment protocol for agent micropayments
- **On-chain agent identity** (ERC-8004) — blockchain-native agent registration
- **Payment channels** — pre-authorized spending limits for agents
- **Stablecoin rails** — USDC/USDT for programmable, fast settlement

## Use Cases

- Agent buying compute/API access from another agent
- Procurement agents negotiating prices on behalf of businesses
- Content agents paying royalties to data sources
- Service marketplace: agents hiring agents for subtasks

## Related

- → [Payments](./payments.md)
- → [Trust & Settlement](./trust.md)
- → [x402](./x402.md)
- → [Agent Identity](../identity/agent-identity.md)
