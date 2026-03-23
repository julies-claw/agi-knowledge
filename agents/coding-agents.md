---
tags: [agents, tools, coding]
links: [./context-engineering.md, ./long-running.md]
status: growing
updated: 2026-03-22
---

# Coding Agents — Evolution

From autocomplete to autonomous coding. This has gone through distinct generations in ~3 years.

## Timeline

```
2021–2022      GitHub Copilot (inline autocomplete)
               → IDE plugin, watches what you type, suggests next line
               → Mental model: "faster typist"
               → Dominated the market, millions of users

2023–2024      Cursor (AI-native IDE)
               → Built from scratch around LLM assistance
               → Multi-file context, chat with your codebase
               → "Tab" feature: predicts your next edit, not just completion
               → Reached ~$100M ARR in 2024, fastest-growing dev tool
               → Mental model: "smarter pair programmer"

2024           Cline / Aider / open-source agents
               → Terminal-based, full file edit + bash execution
               → Human-in-the-loop but agent does multi-step work
               → Popular with power users who want control

2024–2025      Claude Code (Anthropic)
               → Terminal-native autonomous agent — not an IDE plugin
               → Point at a codebase, give a task, it plans + executes
               → Works across dozens/hundreds of files without staying in loop
               → SWE-bench Verified: Claude Opus 4.6 = 80.8% (highest recorded, 2026)
               → 46% developer satisfaction vs. Cursor 19%, GitHub Copilot 9%
               → #1 in VS Code agentic AI marketplace in under 8 months
               Source: DEV.to / dev.to, March 2026

2025–2026      "Co-working" era / collaborative agents
               → JetBrains sunsets Code With Me (real-time collab):
                 "When an AI agent handles multi-file tasks autonomously,
                  synchronous real-time collaboration becomes a niche edge case"
               → Shift: human reviews, agent executes
               → OpenAI Codex (GPT-5.1-based, 2026): cloud coding agent
               → Paradigm: async human-agent collaboration vs. real-time human-human
```

## The Key Distinction (Builder.io framing, 2026)

> "Cursor makes you faster at what you already know how to do.
>  Claude Code does things **for** you."

This captures the generational shift: from acceleration tools to delegation tools.

## What's Converging

- All major coding agents now target SWE-bench as the benchmark
- Terminal-native > IDE plugin for agentic workflows (more control, less UI dependency)
- The question shifts from "does it suggest good code?" to "can it ship a feature end-to-end?"

## Sources

- DEV Community: "Claude Code vs GitHub Copilot vs Cursor in 2026" (Mar 16, 2026)
- dev.to/lizechengnet — benchmark data, satisfaction survey data
- JetBrains Code With Me sunset announcement (2026.1 final release)
