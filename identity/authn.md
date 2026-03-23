---
tags: [identity, security]
links: [./credentials.md, ./authz.md, ./agent-identity.md]
status: seedling
updated: 2026-03-22
---

# Authentication (AuthN)

Authentication = proving you are who you claim to be.  
For agents: proving the agent is what it claims to be, running the code it claims to run.

## Human vs. Agent AuthN

| | Human AuthN | Agent AuthN |
|---|---|---|
| Proof | Password, biometric, TOTP | API key, certificate, TEE attestation |
| Frequency | Once per session | Every request (often) |
| Delegation | Rare | Core use case |
| Revocation | Manual | Needs to be instant + remote |

## Agent AuthN Approaches

- **Shared secret (API key)** — works but doesn't prove identity, just possession
- **Public key cryptography** — agent signs requests with private key, verifiable
- **TEE attestation** — hardware proof that specific code is running
- **OAuth client credentials** — machine-to-machine OAuth flow

## Related

- → [Credentials](./credentials.md)
- → [Authorization](./authz.md)
- → [Agent Identity](./agent-identity.md)
