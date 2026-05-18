# Tri-Node Memory: Core Concept

## Stateless Agents Are Dumb

Every conversation, every session — agents start from zero. You mention a decision from last week, it's gone. They hallucinate about project scope. They rewrite your documentation without permission. They dump every observation into a single memory file until context becomes noise.

The core insight: **agent memory isn't one system. It's a graph of three nodes with different rules.**

## The Three Nodes

### Node 1: The Human Vault

This is where *you* think about your work. Project notes, design decisions, architecture docs, requirements — all under your control, in your git repo, in your format.

**Rule: Agent reads. Never writes.**

Why? Because you need to own your decisions. An agent that auto-refactors your docs or reorganizes your notes is violating your autonomy over your own work. The agent is a consultant reviewing your work, not a coauthor.

### Node 2: The Agent Journal

This is where the agent maintains its own continuity. Completely separate from your vault. Separate git repo. Contains:

- **SOUL.md** — Who is the agent? What are its boundaries? Identity persists across sessions.
- **USER.md** — What does the agent need to know about the human? Work style, preferences, constraints.
- **AGENTS.md** — Behavior rules, startup protocols, red lines.
- **MEMORY.md** — Distilled learnings. Not raw observations — refined understanding.
- **Daily logs** — Raw session observations. Temporary. Gets distilled into MEMORY.md over time.

**Rule: Agent owns. Human can read (transparency).**

Why separate? The agent's understanding of *how you work* is different from your notes about *what you're building*. Mixing them creates confusion.

### Node 3: The Inference Layer

Session scratch space. Where the agent processes context, surfaces insights, asks questions in real-time.

**Rule: Nothing persists here unless explicitly promoted.**

It's thinking out loud, not memory.

## The Boundary Matters

The tri-node model solves three problems simultaneously:

1. **Autonomy:** Agent can't trample your data. Clear ownership boundaries.
2. **Context:** Agent has persistent, refined understanding — not raw doc dumps every session. 10x cheaper, 10x faster.
3. **Learning:** Agent observes patterns, records them in its journal, gets corrected, evolves. Not just reacting — learning your patterns over time.

## Not Just Theory

This architecture is running in production. See [`examples/`](../examples/) for reference implementations.
