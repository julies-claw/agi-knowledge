# 📡 Observability

How do you know if your agent is working? Tracing, evaluation, hallucination detection, and reliability for AI systems.

## What's in here

| Node | One-line summary |
|---|---|
| [agent-benchmarks](./agent-benchmarks.md) | GAIA, SWE-bench, WebArena — real 2026 scores |
| [evals](./evals.md) | How to measure agent performance |
| [hallucination](./hallucination.md) | Why models make things up and how to reduce it |
| [tracing](./tracing.md) | LangSmith, Arize, OpenTelemetry for agents |
| [reliability](./reliability.md) | SLOs, idempotency, graceful failure |

## The Problem with Agent Observability

Traditional software: deterministic, traceable, reproducible
AI agents: probabilistic, non-deterministic, long-horizon

A bug in traditional software has a stack trace. A bug in an agent might be:
- A subtle shift in model behavior after a fine-tune
- A hallucinated tool call that cascades through a workflow
- Context drift over a long session causing the agent to "forget" its instructions
- Prompt injection via a tool response

## Real-World Numbers (2026)

**What agents can do:**
- Claude Opus 4.6: 80.8% on SWE-bench Verified (real GitHub issues)
- Claude Sonnet 4.5: 74.6% on GAIA (general multi-step tasks)
- Claude Opus 4.6: 99.3% on Tau2-bench telecom (customer service with tools)

**What they still fail at:**
- GAIA Level 3 (complex multi-step): ~40-50% success rate
- Long-running tasks (>1 hour): reliability drops significantly
- Novel situations outside training distribution

## The Eval Paradox

Benchmarks saturate fast — GAIA Level 1 was nearly solved by mid-2025.
Labs respond by making harder benchmarks.
But harder benchmarks ≠ better real-world performance.

The gap between "what scores well on SWE-bench" and "what reliably ships features in production" is still significant.

## Tools Being Used in Production (2026)

- **LangSmith** (LangChain): most widely deployed LLM tracing
- **Arize Phoenix**: open-source, strong eval capabilities  
- **Helicone**: LLM proxy with logging — easy to add to any stack
- **Weights & Biases Weave**: traces + evals in one platform
- **OpenTelemetry**: the emerging standard being extended for LLMs
