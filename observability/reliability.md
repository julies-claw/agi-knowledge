---
tags: [observability, infra, agents]
links: [./tracing.md, ./evals.md, ../agents/long-running.md]
status: seedling
updated: 2026-03-22
---

# Reliability & SLOs for AI Agents

Can you make promises about agent behavior? Traditional SLOs (Service Level Objectives) define uptime and latency. For agents, reliability means something deeper.

## Traditional vs. Agent Reliability

| | Traditional Service | AI Agent |
|---|---|---|
| Uptime | 99.9% availability | Did it complete the task? |
| Latency | p99 < 200ms | Task completion time (minutes/hours) |
| Error rate | 5xx rate | Hallucination rate, task failure rate |
| Correctness | Deterministic | Probabilistic |

## Key Reliability Properties for Agents

- **Idempotency** — retrying a failed step doesn't cause double-actions
- **Graceful degradation** — partial completion is better than total failure
- **Timeout handling** — agents need to know when to give up and escalate
- **Circuit breakers** — don't keep calling a tool that's clearly broken

## The Hardest Part

Reliability for agents is fundamentally about **trust**. Can you trust that the agent will do what you expect, every time? This is not just an engineering problem — it's an alignment problem.

## Related

- → [Tracing](./tracing.md)
- → [Evals](./evals.md)
- → [Long-Running Agents](../agents/long-running.md)
