---
tags: [agents, infra, observability]
links: [./orchestration.md, ../observability/tracing.md, ../identity/agent-identity.md]
status: growing
updated: 2026-03-22
---

# Long-Running Agents

Agents that persist across sessions, maintain state over time, and execute multi-step tasks autonomously — often without a human in the loop for hours or days.

## Why It's Hard

- **State management** — where does memory live between steps?
- **Failure recovery** — what happens when a step fails mid-task?
- **Observability** — how do you debug something that ran for 6 hours?
- **Authorization drift** — credentials expire, permissions change mid-run

## Key Concepts

- **Checkpointing** — saving intermediate state so tasks can resume
- **Event loops** — the agent's internal tick cycle
- **Interrupt handling** — human-in-the-loop escalation when the agent is stuck
- **Idempotency** — safe to retry steps without side effects

## Open Questions

- Who is responsible when a long-running agent causes harm?
- How do you audit what a long-running agent did?
- What's the right granularity for human oversight?

## Related

- → [Orchestration](./orchestration.md)
- → [Observability / Tracing](../observability/tracing.md)
- → [Agent Identity](../identity/agent-identity.md)
