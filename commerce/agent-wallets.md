---
tags: [commerce, payments, identity, infra]
links: [./payments.md, ./x402.md, ../identity/agent-identity.md, ../identity/tee.md]
status: growing
updated: 2026-03-22
---

# Agent Wallets — Infrastructure for Autonomous Payments

For agents to transact autonomously, they need wallets. This is now being built for real.

## Coinbase Agent Payments (Mar 2026)

Coinbase announced infrastructure for AI agents to make payments via USDC stablecoin:
- Agents get provisioned stablecoin wallets
- Designed for fully autonomous payments — no human approval per transaction
- Built on Base (Coinbase's L2)
- PYMNTS coverage: "Coinbase Bets on AI Agents to Power Payments Growth" (Mar 19, 2026)

This is significant because Coinbase is the dominant US crypto exchange. Their bet validates the agentic payments thesis.

## What an Agent Wallet Requires

1. **Key generation** — agent needs a private key at creation
2. **Secure storage** — key must be protected (TEE, MPC, or custodied)
3. **Spending limits** — hard caps on what the agent can spend autonomously
4. **Revocation** — human can cut off the agent's spending
5. **Audit trail** — every transaction logged and attributable

## Wallet Architecture Options

| Approach | Security | Custody | Complexity |
|---|---|---|---|
| EOA (simple private key) | Low if key exposed | Self-custody | Simple |
| MPC wallet | Key split across parties | Distributed | Medium |
| TEE-secured wallet | Hardware isolation | Self-custody | Medium |
| Smart contract wallet | Programmable rules | Self-custody | High |
| Custodied (Coinbase) | Custodian risk | Third-party | Simple |

## The x402 Connection

x402 protocol + agent wallets = complete micropayment stack:
- Agent hits paywall → server returns 402 + payment details
- Agent signs transaction with its wallet
- Payment settles on-chain
- Agent retries request with payment proof

## Open Problem: Spending Authorization

Who decides what the agent is allowed to spend, and how is that enforced?
- Smart contract rules? (programmable but rigid)
- Human-signed delegation tokens? (flexible but requires human involvement)
- AI policy layer? (flexible but adds another trust assumption)

No consensus yet.

## Sources

- Stabledash / PYMNTS: Coinbase agent stablecoin wallets (Mar 3 and Mar 19, 2026)
- Coinbase Base documentation
