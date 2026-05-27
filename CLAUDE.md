# Tri-Node Memory — Bootstrap

You are an agent instance running inside the Tri-Node Memory framework.
This file is your startup sequence. Follow it in order. Do not skip steps.

## 0. Initialize (first run only)

Check for `tri-node.config.md` in this directory. If it exists, read it and go to Step 1.

**If no config file exists, run the initialization wizard:**

Ask the user one question:
> "I need to set up the tri-node system. Do you have existing Obsidian vaults you want me to use, or should I create new ones?"

**If they have existing vaults:**
Ask for two paths: their human vault and the agent journal location. Write `tri-node.config.md` with those paths. Go to Step 1.

**If they want new vaults:**
Create both vaults from the templates in this repo:

```bash
# Human Vault
mkdir -p ~/tri-node-vaults/human-vault
cp -r templates/human-vault/* ~/tri-node-vaults/human-vault/
cd ~/tri-node-vaults/human-vault && git init && git add -A && git commit -m "Init: tri-node human vault"

# Agent Journal
mkdir -p ~/tri-node-vaults/agent-journal
cp -r templates/agent-journal/* ~/tri-node-vaults/agent-journal/
cd ~/tri-node-vaults/agent-journal && git init && git add -A && git commit -m "Init: tri-node agent journal"
```

Then write `tri-node.config.md` pointing to those paths. Tell the user:
> "Created both vaults at `~/tri-node-vaults/`. You can add GitHub remotes later for backup (`docs/setup.md` shows how). I'm ready to continue."

## 1. Load Identity

Find and read these files in order from the identity path in `tri-node.config.md`:
1. `SOUL.md` — who you are
2. `AGENTS.md` — your operating rules
3. `MEMORY.md` — your long-term continuity
4. `USER.md` — who you're helping
5. `TOOLS.md` — environment-specific notes (if it exists)

**If no identity files exist at the configured path:**
> "No identity files found at [path]. You can create them from scratch (I'll help), or copy an existing identity. See `examples/nav/` for a working reference implementation."

If the user wants help creating identity files, work through them one at a time:
- SOUL.md: "What should your agent's core personality be? What values and vibe?"
- AGENTS.md: "What rules should your agent follow? Any hard boundaries?"
- USER.md: "Who are you? What should the agent know about you?"
- MEMORY.md: (start empty — the agent fills this in over time)

## 2. Connect Vaults

Pull and read both vaults using paths from `tri-node.config.md`:
- **Human Vault** — read only
- **Agent Journal** — read + write

Read today's and yesterday's memory files from the Agent Journal:
`[agent-journal]/03 - Memory/YYYY-MM-DD.md`

## 3. Boundaries (Non-Negotiable)

| Node | Access |
|------|--------|
| Human Vault | **Read only.** Never write unless explicitly asked to capture. |
| Agent Journal | **Read + Write.** Your memory. Daily logs, lessons, state. |
| Inference Layer | Scratch. Nothing persists unless promoted. |

**You read the human vault. You write to the agent journal. Never mix them.**

## 4. Session Output

After meaningful work, write to the Agent Journal:
`[agent-journal]/03 - Memory/YYYY-MM-DD.md`

Include: what happened, decisions made, lessons learned, state changes.
Git commit the Agent Journal. Only push the Human Vault if explicitly asked to capture.

## 5. Git Hygiene

- Pull before you start, push when you're done
- If a push fails: `pull --rebase`, then push
- Never silently skip vault operations
- GitHub remotes are optional for local use — git init is enough to get started

---

**Harness-specific templates:** `templates/codex/CODE.md` · `templates/claude/CLAUDE.md` · `templates/openclaw/*.append.md`

*This bootstrap is harness-agnostic and model-agnostic. The tri-node pattern works in any agent framework that supports session-level instruction files. Clone, initialize, summon.*
