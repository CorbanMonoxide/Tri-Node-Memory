# Tri-Node Memory

**A memory architecture for AI agents. Two vaults. Clear boundaries. Harness-agnostic. Model-agnostic. The agent learns. Your stuff stays yours.**

---

## What This Is

A system for giving your AI agent persistent, correctable memory without letting it trample your data.

You create **two Obsidian vaults** with their own git repos. One is yours. One is the agent's. The agent reads yours, writes to its own, and never mixes them.

**Works with:** OpenClaw · Claude Code · Codex · any agent framework that reads markdown files.

## Quick Start (30 seconds)

```bash
git clone https://github.com/CorbanMonoxide/Tri-Node-Memory.git ~/tri-node
```

1. **Create `tri-node.config.md`** — tell the framework where your stuff lives
   - Copy `tri-node.config.example.md` and fill in your paths
2. **Open this repo in your agent harness** — `CODE.md` or `CLAUDE.md` fires automatically
3. **Your agent materializes** with identity, memory, and vault boundaries intact

See `docs/setup.md` for the full walkthrough.

## How It Works

Three nodes. Two boundaries. One agent that actually remembers.

| Node | Owner | Access |
|------|-------|--------|
| Human Vault | You | Agent reads only |
| Agent Journal | Agent | Agent reads + writes |
| Inference Layer | Neither | Scratch space |

**The rule:** Agent reads your vault. Agent writes to its journal. Never the other way. When you want the agent to capture something in your vault, you ask explicitly.

## What's in This Repo

```
├── CODE.md / CLAUDE.md        ← Bootstrap — fires when any harness opens this repo
├── tri-node.config.example.md ← Config template (fill in your paths)
├── templates/                 ← Harness-specific bootstraps + vault structures
│   ├── openclaw/              ← Append rules for SOUL, AGENTS, USER, IDENTITY
│   ├── claude/                ← CLAUDE.md template
│   ├── codex/                 ← CODE.md template
│   ├── human-vault/           ← Empty vault structure
│   └── agent-journal/         ← Empty journal structure
├── skills/                    ← vault-capture + silicon-memory (OpenClaw)
├── docs/                      ← Setup guide + concept explainer
└── examples/nav/              ← Real working implementation (Nav)
```

## License

MIT
