---
tags: [infra, agents, multimodal]
links: [../models/multimodal.md, ../agents/long-running.md]
status: seedling
updated: 2026-03-22
---

# Voice Agents — Real-Time Conversational AI

Voice agents bring AI into real-time spoken conversation — customer service, companions, assistants, phone calls.

## Key Players (2026)

**OpenAI Realtime API**
- WebSocket-based streaming — both audio input and output
- Low-latency (~300ms) voice conversation with GPT-4o
- Supports interruption handling (user can cut off the AI mid-sentence)
- Available since late 2024

**ElevenLabs Conversational AI**
- More customizable voice personas
- Better emotional range and voice cloning
- Developer-focused, good integration flexibility
- 2026 developer trends report: voice agent adoption surging

**Hume AI**
- Emotional intelligence focus — model understands and responds to tone, not just words
- "Empathic Voice interface" (EVI)

Source: ElevenLabs blog, "Voice agents and Conversational AI: 2026 developer trends" (Mar 17, 2026); ElevenLabs comparison article (Mar 14, 2026)

## ElevenLabs vs OpenAI Realtime (per ElevenLabs own comparison)

| | OpenAI Realtime | ElevenLabs Conv. AI |
|---|---|---|
| Latency | ~300ms | ~400ms |
| Voice quality | Good | Better customization |
| Interruption handling | Yes | Yes |
| LLM flexibility | GPT-4o only | Bring your own LLM |
| Best for | Quick integration | Custom voice persona |

## What's Hard About Voice Agents

- **Latency**: users notice >500ms delay in conversation
- **Interruptions**: natural conversation requires handling overlapping speech
- **Turn-taking**: when to speak vs. listen
- **Noise handling**: real environments aren't quiet
- **Streaming**: audio must be generated and played as it's produced, not after

## Use Cases Emerging

- Customer service (replacing IVR trees)
- Outbound sales calls
- Healthcare intake / mental health support
- Accessibility tools
- Companion AI

## Sources

- ElevenLabs: "Voice agents and Conversational AI: 2026 developer trends" (Mar 17, 2026)
- ElevenLabs: "Comparing ElevenLabs Conversational AI and OpenAI Realtime API" (Mar 14, 2026)
- Ry Walker Research: OpenAI Realtime API (Feb 2026)
