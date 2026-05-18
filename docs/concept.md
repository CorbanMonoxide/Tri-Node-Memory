# Tri-Node Memory: Core Concept

## The Problem

AI agents forget between sessions. Even "agentic" frameworks — ones that keep context alive — fall into three traps:

1. **Stateless**: Each session starts from zero. No learning over time.
2. **One bucket**: Everything dumped together — session notes, project context, random observations. Signal lost.
3. **No boundaries**: Agent treats your notes and its observations as the same thing. Rewrites your docs. Inserts suggestions inline. You lose track of what's yours.

The real issue isn't memory. It's *whose* memory.

---

## The Model: Three Nodes

### Node 1: Human Vault
Your project notes, design decisions, architecture docs. Your Obsidian vault, your git repo, your voice. **Agent reads. Never writes** (unless you explicitly direct it).

### Node 2: Agent Journal
The agent's own memory. Separate vault, separate git repo. Contains SOUL.md (identity), USER.md (what it knows about you), MEMORY.md (distilled learnings), and daily session logs. **Agent writes. You can read.** Transparent and correctable.

### Node 3: Inference Layer
Session scratch space. Where the agent processes context and thinks out loud. **Nothing persists** unless explicitly promoted by you or the agent. It's a whiteboard, not a filing cabinet.

---

## The Feedback Loop

1. You document a decision in your vault
2. Agent reads it at next session start, builds context
3. Agent processes in its journal, records its understanding
4. Agent surfaces insights in conversation
5. You correct or confirm
6. Agent updates its journal. Your vault stays untouched.

The agent learns your patterns without ever touching your data.

---

## Why It Works

- **Autonomy**: Hard boundary — your vault is yours. Agent can't rewrite it.
- **Context efficiency**: Agent has refined, persistent understanding instead of raw doc dumps every session.
- **Learning**: Agent observes patterns over time, records them, gets corrected, evolves.
