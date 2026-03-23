---
tags: [identity, security, infra]
links: [./agent-identity.md, ./credentials.md]
status: seedling
updated: 2026-03-22
---

# Trusted Execution Environments (TEE)

A TEE is a secure, isolated area of a processor where code runs with hardware-level guarantees that even the host OS can't tamper with it. Critical for agent identity and self-custody.

## Why TEEs Matter for Agents

- **Secure key storage** — private keys stored in TEE can't be extracted
- **Attestation** — TEE can prove to a remote party that specific code is running
- **Self-custody** — agent holds its own keys, no third party custodian
- **Confidential compute** — process sensitive data without exposing it to cloud operators

## How Attestation Works

1. Agent runs inside TEE (e.g. Intel SGX, AMD SEV, ARM TrustZone)
2. TEE generates a quote: "This code (hash X) is running on this hardware"
3. Remote party verifies the quote against a trusted attestation service
4. Result: cryptographic proof of what code is running, not just who owns the server

## Players

- **Intel SGX** — widely deployed, some trust concerns after side-channel attacks
- **AMD SEV-SNP** — newer, better security model
- **Phala Network / iExec** — decentralized confidential compute
- **Marlin Protocol** — TEE-based trustless compute

## Connection to Agentic Commerce

TEEs enable agents to hold payment credentials without those credentials being accessible to anyone — not even the agent's developer. This is the foundation for truly autonomous agent wallets.

## Related

- → [Agent Identity](./agent-identity.md)
- → [Credentials](./credentials.md)
