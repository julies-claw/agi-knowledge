---
tags: [observability, agents, infra]
links: [./evals.md, ./reliability.md, ../agents/long-running.md]
status: seedling
updated: 2026-03-22
---

# Tracing & Logging for Agents

How do you understand what an agent did, why it did it, and where it went wrong? Traditional distributed tracing tools weren't built for LLM-based agents — the field is adapting fast.

## Why Agent Tracing is Hard

- Non-deterministic — same input, different output each time
- Multi-step reasoning isn't a function call stack
- Tools calls, LLM calls, and code execution are all mixed
- Long-running means traces can span hours or days

## What to Capture

- **LLM calls** — prompt, response, token count, latency, model version
- **Tool calls** — which tool, what input, what output, errors
- **State changes** — what changed in agent memory/context
- **Decision points** — why did the agent choose path A over path B?
- **Human handoffs** — when did the agent escalate, and why?

## Emerging Tools

- **LangSmith** (LangChain) — tracing for LLM apps
- **Arize Phoenix** — open-source LLM observability
- **Weights & Biases Weave** — traces + evals
- **OpenTelemetry** — becoming the standard, being extended for LLMs
- **Helicone** — LLM proxy with built-in logging

## Related

- → [Evals](./evals.md)
- → [Long-Running Agents](../agents/long-running.md)
