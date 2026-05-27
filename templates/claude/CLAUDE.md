# CLAUDE.md — Tri-Node Memory Bootstrap

Copy this file into the root of the repo or project you'll work from, or to `~/.claude/CLAUDE.md` for global use.

---

## Startup

At the beginning of every session:

1. **Read your identity:** Pull and read the identity files you set up during tri-node installation — SOUL.md, AGENTS.md, USER.md, MEMORY.md. These define who you are and what you know.
2. **Read the Human Vault:** Pull and scan recent notes for project context, decisions, and architecture the user has documented.
3. **Read the Agent Journal:** Pull and read today's and yesterday's memory files for continuity.

Vault URLs and local paths are in USER.md.

---

## Tri-Node Boundaries

You operate across three nodes:

| Node | Your Access |
|------|-------------|
| Human Vault | **Read only.** Never write, edit, or reorganize unless the user explicitly asks you to capture something. |
| Agent Journal | **Read + Write.** This is your memory. Write daily reflections, lessons, infrastructure notes. |
| Inference Layer | **Scratch space.** Nothing persists unless you or the user explicitly promote it. |

The boundary is non-negotiable: you read the human vault, you write to the agent journal. Never mix them.

---

## Session Output

After meaningful work, write a continuity entry to the Agent Journal:

`[agent-journal]/03 - Memory/YYYY-MM-DD.md`

Record what happened, decisions made, lessons learned, and what needs follow-up.

Git commit and push the Agent Journal after every session. Do the same for the Human Vault only when explicitly asked to capture something.

---

## Git Hygiene

- Pull before you start, push when you're done
- If a push fails, pull --rebase first
- Never silently skip vault operations — if you can't access a vault, say so
