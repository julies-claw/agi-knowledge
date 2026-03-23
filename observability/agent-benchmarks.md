---
tags: [observability, agents, models]
links: [./evals.md, ../agents/coding-agents.md, ../models/foundation.md]
status: growing
updated: 2026-03-22
---

# Agent Benchmarks — What Actually Measures Agent Performance (2026)

"Best agent" claims are everywhere. The benchmarks that actually have signal in 2026:

## The Four Main Agentic Benchmarks

### GAIA (General AI Assistants)
- Created by Meta + HuggingFace
- 466 questions, 3 difficulty levels
- Level 1: single web search; Level 3: chain web browsing + file parsing + calculations + reasoning
- **Measures**: real-world multi-step task completion
- **2026 leader**: Claude Sonnet 4.5 at **74.6%**, Anthropic sweeps top 6 positions
- Human baseline: ~92% (agents still below human performance)

### WebArena
- Autonomous web navigation in realistic environments
- Agent must accomplish tasks on real websites (shopping, Reddit, GitLab, etc.)
- **Measures**: browser automation, planning, error recovery
- **2026 leader**: OpAgent (Qwen3-VL + RL) at **71.6%** — surpasses GPT-5 and Claude-backed agents

### SWE-bench (Coding)
- Real GitHub issues, agent must write a PR that passes tests
- SWE-bench Verified and SWE-bench Pro variants
- **Measures**: end-to-end software engineering
- **2026 leader**: Claude Opus 4.6 at **80.8%** (SWE-bench Verified), **59%** (SWE-bench Pro)

### Tau2-bench (Customer Service with Tools)
- Multi-turn customer service, agent uses tools to resolve real scenarios
- Retail and telecom domains
- **Measures**: tool use accuracy + multi-turn consistency under pressure
- **2026 leader**: Claude Opus 4.6 — **99.3%** telecom, **91.9%** retail (highest recorded)

### BFCL V4 (Function Calling)
- Tests accuracy of tool/function calling across many scenarios
- **2026**: Claude Opus 4.1 at 70.4%, but open-source GLM-4.5 tops both at **70.9%**

Source: Awesome Agents leaderboard (Feb 28, 2026); Morph LLM SWE-bench Pro (Mar 2026)

## Key Insight: Benchmarks Are Saturating Fast

GAIA Level 1 was ~90% solvable by mid-2025. Labs are moving to harder versions.
SWE-bench Verified will likely be "solved" (>90%) within 12 months at current rate.
The benchmark-capability gap: what a model scores ≠ what it reliably does in production.

## What Benchmarks Don't Measure

- Long-running reliability (>1 hour)
- Cost per successful task completion
- Behavior under adversarial conditions (prompt injection)
- Graceful failure and human escalation

## Sources

- Awesome Agents: "Agentic AI Benchmarks Leaderboard" (Feb 28, 2026)
- Morph LLM: SWE-bench Pro Leaderboard (Mar 2026)
- Steel.dev: AI Agent Benchmark Results Index (Mar 2026)
