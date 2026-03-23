---
tags: [commerce, agents, infra]
links: [./a2a.md, ./x402.md, ./trust.md]
status: growing
updated: 2026-03-22
---

# Agentic Payments

Payments made by AI agents on behalf of humans or other agents — autonomously, programmatically, at scale.

## What's New

Traditional payments assume a human authorizes each transaction. Agentic payments flip this: humans set policies, agents execute within those policies.

## Payment Rails for Agents

| Rail | Speed | Cost | Agent-Friendly? |
|------|-------|------|-----------------|
| Credit card | Seconds (auth) | 2-3% | ⚠️ Requires human setup |
| ACH/bank transfer | 1-3 days | Low | ❌ Too slow |
| Stablecoins (USDC/USDT) | Seconds | Low | ✅ Programmable |
| Lightning (Bitcoin) | Instant | Near-zero | ✅ But adoption limited |
| x402 + stablecoin | Instant | Low | ✅ Purpose-built |

## Key Design Questions

- **Spending limits** — how does a human cap what an agent can spend?
- **Approval flows** — above threshold X, ask human; below X, proceed
- **Audit trail** — every agent payment should be logged and attributable
- **Refunds** — how does an agent handle a failed purchase?

## Wallet Architecture for Agents

- Agent needs a wallet (private key)
- Key must be stored securely (TEE or MPC)
- Key rotation without downtime is hard
- Multi-sig possible for higher-value transactions

## Related

- → [A2A Commerce](./a2a.md)
- → [x402](./x402.md)
- → [Trust & Settlement](./trust.md)
