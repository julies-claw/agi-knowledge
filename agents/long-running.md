---
tags: [agents, infra, cloud]
links: [./context-engineering.md, ../observability/tracing.md, ../identity/agent-identity.md]
status: growing
updated: 2026-03-22
---

# Long-Running Agents

Agents that work across multiple context windows over hours or days — not single-session assistants.

## The Core Problem

> "The core challenge of long-running agents is that they must work in discrete sessions,
> and each new session begins with no memory of what came before. Imagine a software
> project staffed by engineers working in shifts, where each new engineer arrives with
> no memory of what happened on the previous shift."
> — Anthropic Engineering Blog

LLMs have finite context windows. Complex tasks exceed one window. The question is: how do you bridge sessions?

## Anthropic's Solution (Claude Agent SDK)

Two-agent approach:
1. **Initializer agent** — sets up environment on first run, creates structured artifacts
2. **Coding agent** — makes incremental progress each session, leaves clear handoff notes

Key failure modes they observed when *not* doing this:
- Agent tries to do too much at once
- No clear state handoff between sessions
- Compaction (summarizing old turns) alone isn't sufficient

Source: "Effective harnesses for long-running agents" (Anthropic, Nov 2025)
https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents

## Infrastructure Problem: Existing Cloud Wasn't Built for This

Standard cloud infra assumptions break for long-running agents:

| Platform | Limit | Problem |
|---|---|---|
| Temporal (durable execution) | 51,200 event history, 2MB payload | Agent making 1000s of LLM calls hits ceiling fast |
| AWS Step Functions | 256 KiB per state transition | Blocks structured LLM responses |
| Modal / E2B | 24h max invocation | Lose process state on interrupt |

**OpenComputer** (Mar 2026) — purpose-built cloud for agentic workloads:
- Persistent VMs that hibernate when idle, wake in seconds
- Designed for stateful, long-horizon agent processes
- Addresses the gap that serverless/containerized platforms can't fill
Source: agent-wars.com, March 16 2026

## Open Problems

- How does an agent know it's making progress vs. going in circles?
- What's the right granularity of checkpointing?
- Who is responsible when a long-running agent causes harm mid-task?
- How do you audit hours of autonomous action?
