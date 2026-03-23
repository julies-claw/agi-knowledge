---
tags: [agents, tools, infra]
links: [./long-running.md, ./coding-agents.md, ../infra/tools.md]
status: growing
updated: 2026-03-22
---

# Computer Use Agents — AI Controlling the Desktop/Browser

Agents that can see a screen and control mouse/keyboard. Bypasses APIs entirely — if a human can do it in a GUI, the agent can too.

## The Three Main Players (Mar 2026)

Per Shareuhack guide (Mar 21, 2026):

**Claude Cowork** (Anthropic)
- Best for: local file operations — organizing folders, editing documents, reading/writing PDFs
- Runs locally, accesses your filesystem
- More privacy-preserving than cloud-based options

**OpenAI Operator**
- Best for: cross-site web operations — booking tickets, filling forms, comparison shopping
- Browser-native, handles web-based tasks well
- Can navigate multi-step web flows

**Manus Desktop** (launched Mar 16, 2026)
- Best for: long-running research, multi-step tasks — competitor research, data collection into reports
- Most autonomous of the three
- Still new, reliability being established

## Task-Tool Selection Matrix

| Task type | Best tool |
|---|---|
| Local file organization, PDF editing | Claude Cowork |
| Web forms, booking, cross-site ops | OpenAI Operator |
| Long research, multi-site data collection | Manus Desktop |
| One-off simple tasks | Don't bother with agents |
| High-risk financial decisions | Never delegate |
| CAPTCHA-heavy workflows | Not worth it yet |

## Security Baseline

> "Never grant any agent access to password managers, banking windows, or confidential business folders"

Computer use agents have read/write access to your screen. This is maximum privilege. The attack surface is enormous — prompt injection via anything displayed on screen.

## Claude Computer Use vs. Claude Cowork

Claude Computer Use (Oct 2024): research preview, raw API
Claude Cowork (2025): productized, more polished, consumer-facing
The underlying capability is similar; the UX and safety layers differ significantly.

## What's Still Hard

- **CAPTCHAs**: most anti-bot measures still work against agents
- **Multi-factor auth**: agents can't easily handle MFA flows
- **Precision tasks**: pixel-perfect design work, image editing
- **Reliability**: computer use agents fail more than API-based agents

## Sources

- Shareuhack: "Manus Desktop vs Claude Cowork vs OpenAI Operator" (Mar 21, 2026)
- Anthropic Claude computer use announcement (Oct 2024)
- O-mega.ai: "Agentic Computer Use: Ultimate Deep Guide 2026"
