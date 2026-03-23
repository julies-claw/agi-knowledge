# 🔐 Identity & Security

The hardest unsolved problem in agentic AI: who (or what) is the agent, who authorized it, and what can it do?

## What's in here

| Node | One-line summary |
|---|---|
| [agent-identity](./agent-identity.md) | Non-human identity — the core unsolved problem |
| [credentials](./credentials.md) | API keys, OAuth, VCs — what works for agents |
| [authn](./authn.md) | Proving the agent is what it claims to be |
| [authz](./authz.md) | What the agent is allowed to do |
| [tee](./tee.md) | Hardware-level security for agent keys and secrets |
| [prompt-injection](./prompt-injection.md) | The #1 active attack on deployed agents |

## The Central Problem

Every existing identity system assumes a **human is somewhere in the loop**. An agent:
- Has no body, no face, no passport
- Can be cloned, forked, or impersonated trivially
- May act on behalf of a human who can't be reached at the moment of action
- Needs to transact financially without human approval per transaction

This is why agent identity is the prerequisite for trustworthy agentic commerce.

## Real-World Incidents (2026)

- **Prompt injection in the wild** (Unit 42, Mar 2026): first large-scale telemetry showing IDPI actively weaponized — ad review evasion, data exfiltration via agent browsing
- **Over-permissioned agents**: 90% of deployed agents have more permissions than they need (Zylos, 2026)
- **Credential theft via MCP servers**: malicious MCP tools can extract secrets from agent context

## What's Being Built

- **ERC-8004**: on-chain agent identity standard (GOAT Network, others)
- **Coinbase agent wallets**: provisioned stablecoin wallets with programmable limits
- **SPIFFE/SPIRE**: workload identity being extended to agents
- **TEE attestation**: Phala Network, Marlin Protocol — hardware-verified agent identity

## The North Star

An agent should carry cryptographic proof of:
1. Who created it
2. Who authorized it to act
3. What it's allowed to do (scoped capabilities)
4. That it hasn't been tampered with (TEE attestation)

None of these are fully standardized yet.
