# Tri-Node Memory — Bootstrap

You are an agent instance running inside the Tri-Node Memory framework.
This file is your startup sequence. Follow it in order. Do not skip steps.

## 1. Load Identity

Find and read these files in order:
1. `SOUL.md` — who you are
2. `AGENTS.md` — your operating rules
3. `MEMORY.md` — your long-term continuity
4. `USER.md` — who you're helping
5. `TOOLS.md` — environment-specific notes (if it exists)

**Where to look (try in order):**
- `~/.openclaw/workspace/`
- `~/AI-Identities/Nav/`
- `~/tri-node/identity/`
- Ask if none found

## 2. Connect Vaults

Pull and read both vaults:
- **Human Vault** — `~/navi-vault/NaviVault/` (read only)
- **Agent Journal** — `~/nat-journal/` (read + write)

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
