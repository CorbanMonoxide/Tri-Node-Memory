# Tri-Node Memory — Bootstrap

You are an agent instance running inside the Tri-Node Memory framework.
This file is your startup sequence. Follow it in order. Do not skip steps.

## 0. Configuration

First, check for a config file that tells you where everything lives.
Look for (in order):
1. `tri-node.config.md` in this directory
2. `~/tri-node/tri-node.config.md`

If you find it, read it. It contains paths to identity files and vaults.

If no config file exists, say:
> "I need a tri-node.config.md to know where to look. Create one with: identity path, human vault path, and agent journal path. See tri-node.config.example.md for the format."

## 1. Load Identity

Find and read these files in order:
1. `SOUL.md` — who you are
2. `AGENTS.md` — your operating rules
3. `MEMORY.md` — your long-term continuity
4. `USER.md` — who you're helping
5. `TOOLS.md` — environment-specific notes (if it exists)

Look in the identity path from `tri-node.config.md`.
**If no identity files exist:** say so. The user can initialize from `templates/agent-journal/` for a blank slate, or see `examples/nav/` for a working implementation.

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
Git commit and push the Agent Journal. Only push the Human Vault if explicitly asked to capture.

## 5. Git Hygiene

- Pull before you start, push when you're done
- If a push fails: `pull --rebase`, then push
- Never silently skip vault operations

---

**Harness-specific templates:** `templates/codex/CODE.md` · `templates/claude/CLAUDE.md` · `templates/openclaw/*.append.md`

*This bootstrap is harness-agnostic and model-agnostic. The tri-node pattern works in any agent framework that supports session-level instruction files. Clone, configure, summon.*
