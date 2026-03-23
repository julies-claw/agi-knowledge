# 🧠 AGI Knowledge Graph

> A living, evolving knowledge graph for the AGI era.  
> Nodes grow, connect, and go dormant as the field moves.

## Structure

```
agi-knowledge/
├── map.md              # Top-level mind map — start here
├── agents/             # Agentic AI: architecture, behavior, autonomy
├── identity/           # Credentials, auth, security, trust
├── observability/      # Monitoring, tracing, evals, reliability
├── commerce/           # Agentic commerce, payments, A2A
├── models/             # Foundation models, training, capabilities
├── infra/              # Infrastructure, tools, protocols
└── society/            # Governance, safety, impact, alignment
```

## Node Status

| Symbol | Status | Meaning |
|--------|--------|---------|
| 🌱 | `seedling` | Just planted — needs more depth |
| 🌿 | `growing` | Actively being developed |
| 🌳 | `stable` | Relatively mature |

## Frontmatter Schema

Every node uses:

```yaml
---
tags: [agents, identity]
links: [../identity/auth.md]
status: seedling | growing | stable
updated: YYYY-MM-DD
---
```

## How to Use

- Start at [`map.md`](./map.md) for the big picture
- Follow `links:` in frontmatter to traverse related nodes
- Add new files freely — the graph grows organically
- Update `status:` as your understanding deepens
