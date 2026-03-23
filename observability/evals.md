---
tags: [observability, models, agents]
links: [./tracing.md, ./reliability.md, ../models/foundation.md]
status: seedling
updated: 2026-03-22
---

# Evals & Benchmarks

How do you measure whether an agent is doing well? Evals are the testing framework for AI systems — but unlike unit tests, "correct" is often subjective or context-dependent.

## Types of Evals

- **Automated evals** — LLM-as-judge, rule-based checks, regex matching
- **Human evals** — human raters score outputs (slow, expensive, gold standard)
- **Task completion** — did the agent complete the goal? (binary or graded)
- **Behavioral evals** — does the agent behave safely, honestly, helpfully?

## For Agents Specifically

- **End-to-end task evals** — give agent a goal, measure success rate
- **Tool use accuracy** — did the agent call the right tools with right params?
- **Hallucination detection** — did the agent make up facts?
- **Instruction following** — did it do what it was asked to do?

## Known Benchmarks

- **MMLU, HumanEval, GSM8K** — model capability (not agent-specific)
- **WebArena, SWE-bench** — agentic task completion
- **AgentBench** — multi-task agent evaluation

## The Meta-Problem

Evals are themselves imperfect. LLM-as-judge can be biased. Human evals are noisy. The field is still figuring out how to eval agents at scale.

## Related

- → [Tracing](./tracing.md)
- → [Reliability](./reliability.md)
