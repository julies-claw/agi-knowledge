# 💸 Commerce

The economic layer of the agent era. How agents buy, sell, and transact — from micropayments to full A2A marketplaces.

## What's in here

| Node | One-line summary |
|---|---|
| [a2a](./a2a.md) | Agent-to-agent commerce — the emerging category |
| [payments](./payments.md) | Payment rails designed for autonomous agents |
| [x402](./x402.md) | HTTP 402 payment protocol for machine-to-machine |
| [agent-wallets](./agent-wallets.md) | Coinbase's infrastructure for agent stablecoin wallets |
| [trust](./trust.md) | Settlement, reputation, the bootstrapping problem |
| [ai-legal](./ai-legal.md) | Harvey AI and the legal sector disruption |

## Why This Matters Now

The internet was built for humans to transact with businesses. Agentic commerce introduces a third category: **agents transacting with agents** — autonomously, at scale, without per-transaction human approval.

This requires entirely new infrastructure:
- Identity (who is this agent?)
- Authorization (what is it allowed to spend?)
- Payment rails (fast, programmable, low-friction)
- Settlement (atomic, trustless)
- Dispute resolution (what happens when something goes wrong?)

## Real-World Deployments (2026)

**Coinbase agent payments** (Mar 2026)
- Provisioned USDC wallets for AI agents
- Fully autonomous payments on Base (L2)
- First major exchange to productize agent payment infrastructure

**x402 in production**
- GOAT Network: goatx402-sdk deployed
- Agents paying for API access per-request via USDC/USDT
- Merchant ID + API key model for easy integration

**Harvey AI in legal** (130 largest law firms)
- AI doing substantive client-facing work: drafting, due diligence, contract negotiation
- Leads 7 of 11 legal AI use-case categories
- Real revenue from automating $500-1500/hr partner time

**Salesforce AgentExchange**
- $800M ARR, 18,500 enterprise customers
- Agents deployed in sales, service, marketing workflows

## The Payment Stack (End-to-End)

```
Agent needs a resource
    ↓
Hits paywall → server returns 402 + USDC amount + destination address
    ↓
Agent signs transaction with its wallet (TEE-secured private key)
    ↓
Payment settles on-chain (Base, ~2 seconds)
    ↓
Agent retries request with payment proof
    ↓
Resource delivered
```

No human needed. No API key. No subscription. Pay per use.
