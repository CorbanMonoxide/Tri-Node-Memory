# Tri-Node Memory

**A memory architecture for AI agents that actually remember — without trampling your data.**

---

## The Problem

AI agents forget. They hallucinate about project scope. They rewrite your documentation without asking. They dump everything into one memory file until context becomes noise.

Even "agentic" frameworks struggle with this. They either stay stateless (no learning), dump everything into one bucket (no signal separation), or auto-overwrite your data (no autonomy).

The real issue isn't memory — it's *whose* memory.

## The Model: Three Nodes, One System

```
┌─────────────────┐     ┌─────────────────┐
│   HUMAN VAULT   │     │  AGENT JOURNAL  │
│   (Your Brain)  │◄───►│ (Agent's Brain) │
│                 │     │                 │
│  • Project docs │     │  • SOUL.md      │
│  • Decisions    │     │  • MEMORY.md    │
│  • Architecture │     │  • Daily logs   │
│                 │     │                 │
│  AGENT READS    │     │  AGENT OWNS     │
│  NEVER WRITES   │     │  HUMAN CAN READ │
└────────┬────────┘     └────────┬────────┘
         │                       │
         │    ┌──────────────┐   │
         └───►│  INFERENCE   │◄──┘
              │  (Scratch)   │
              │              │
              │  TRANSIENT   │
              │  NO PERSIST  │
              └──────────────┘
```

**Node 1 — Human Vault:** Your project docs, decisions, architecture. Agent reads, never writes. You stay in control.

**Node 2 — Agent Journal:** The agent's own continuity. SOUL.md, MEMORY.md, daily logs. Agent owns this. Humans can read it (transparency).

**Node 3 — Inference Layer:** Session scratch space. Where thinking happens. Nothing persists unless promoted.

## The Feedback Loop

1. You document in your vault → "Moving from REST to gRPC, 6-month backward compat window."
2. Agent reads this at session start. Builds context.
3. Agent processes in its journal: "Project requires dual-stack. User prefers gradual migration over rewrites."
4. Agent surfaces insights in conversation → "Should we use a facade layer?"
5. You correct → "No, client-side adapter, different problem."
6. Agent updates its understanding. Your vault stays untouched. Agent still learned.

## What's in This Repo

- **`templates/`** — Ready-to-use vault and journal structures
- **`docs/`** — Concept explainer, getting started guide, architecture deep-dive
- **`examples/`** — Reference implementations (coming soon)

## Getting Started

See [`docs/getting-started.md`](docs/getting-started.md).

## License

MIT
