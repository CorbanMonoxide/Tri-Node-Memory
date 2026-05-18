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

## Quick Start

Read [`docs/setup.md`](docs/setup.md) for the step-by-step. The short version:

1. Create two Obsidian vaults, each with its own git repo
2. Copy the vault structures from `templates/`
3. Append the tri-node rules to your agent's SOUL.md, AGENTS.md, USER.md, and IDENTITY.md
4. Install the vault-capture and silicon-memory skills
5. Point your agent at both vault URLs

## License

MIT
