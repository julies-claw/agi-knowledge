---
tags: [identity, security, agents]
links: [./authn.md, ./authz.md, ./agent-identity.md, ../commerce/x402.md]
status: growing
updated: 2026-03-22
---

# Credentials

Credentials are the proof an agent (or human) presents to demonstrate identity and authorization. In the agentic era, credential management becomes dramatically more complex.

## Types

| Type | Description | Agent-friendly? |
|------|-------------|-----------------|
| API keys | Static secret, passed in headers | ⚠️ Simple but no scope/expiry |
| OAuth 2.0 tokens | Time-limited, scoped access tokens | ⚠️ Designed for humans |
| JWT | Self-contained, signed claims | ✅ Good for delegation chains |
| Verifiable Credentials (VCs) | W3C standard, cryptographic, self-sovereign | ✅ Best for agent identity |
| mTLS certificates | Mutual TLS, strong but operationally heavy | ✅ Good for service-to-service |

## Agent-Specific Challenges

- **Rotation** — agents running for days need credential rotation without interruption
- **Delegation** — human → agent → sub-agent: each hop needs scoped credentials
- **Storage** — where does an agent securely store secrets? (TEE is the answer)
- **Least privilege** — agents should only have credentials for what they need right now

## Emerging Standards

- **SPIFFE/SPIRE** — workload identity for cloud-native services, increasingly used for agents
- **Verifiable Credentials (W3C)** — standardized format for machine-readable claims
- **OpenID for Verifiable Presentations** — presenting VCs in OAuth flows

## Related

- → [Authentication](./authn.md)
- → [Authorization](./authz.md)
- → [Agent Identity](./agent-identity.md)
- → [TEE](./tee.md)
- → [x402](../commerce/x402.md)
