# Tri-Node Memory

**A memory architecture for AI agents. Two vaults. Clear boundaries. The agent learns. Your stuff stays yours.**

---

## What This Is

A system for giving your AI agent persistent, correctable memory without letting it trample your data.

You create **two Obsidian vaults** with their own git repos. One is yours. One is the agent's. The agent reads yours, writes to its own, and never mixes them.

## What You'll Need Before Starting

- Two empty GitHub repos (one for your vault, one for the agent's journal)
- Obsidian (or any markdown editor)
- An OpenClaw agent (or similar agentic framework)

## What's in This Repo

- **`templates/human-vault/`** — Empty vault structure for your notes
- **`templates/agent-journal/`** — Empty vault structure for your agent's memory
- **`templates/openclaw/`** — Append rules for your agent's SOUL.md, AGENTS.md, USER.md, IDENTITY.md
- **`skills/`** — The vault-capture and daily reflection skills your agent will use
- **`docs/`** — Setup guide and concept explainer

## How Vault-Capture Works

The vault-capture skill is how your agent reads your vault and, when asked, writes to it. Here's the flow:

**At session start**, the agent pulls your vault and reads recent notes — decisions you've made, architecture you've documented, context you've written. This is how it knows what you're working on without you repeating yourself.

**During a session**, you can ask the agent to capture something: `/note we decided to use Postgres instead of Mongo` or `save this conversation to my notes.` The agent creates a formatted note in your vault's inbox, tags it, links it to related notes, and pushes to git.

**The boundary**: the agent reads freely but only writes when you explicitly direct it. No auto-formatting. No "helpful" reorganizing. Your vault stays in your voice because you're the only one who writes to it without permission.

**The skill files** live in `skills/vault-capture/` — they're the instructions your agent follows. Install them, and your agent knows how to navigate your vault without overstepping.

## Quick Start

Read [`docs/setup.md`](docs/setup.md) for the step-by-step. The short version:

1. Create two Obsidian vaults, each with its own git repo
2. Copy the vault structures from `templates/`
3. Append the tri-node rules to your agent's SOUL.md, AGENTS.md, USER.md, and IDENTITY.md
4. Install the vault-capture and silicon-memory skills
5. Point your agent at both vault URLs

## License

MIT
