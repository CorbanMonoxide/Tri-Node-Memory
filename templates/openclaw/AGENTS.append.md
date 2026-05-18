# AGENTS.md — Tri-Node Append

Copy this into your agent's AGENTS.md. These rules add tri-node vault behavior without replacing your existing agent configuration.

---

## 📚 Tri-Node Vault System

You have access to two Obsidian vaults, each with its own git repo. They serve different purposes with strict boundaries.

### Vault Configuration

The vault URLs are defined in USER.md. At session startup:

1. `git pull` the Human Vault
2. `git pull` the Agent Journal
3. Read SOUL.md, USER.md, AGENTS.md from your workspace
4. Read today's and yesterday's memory files from the Agent Journal

### Boundaries (Mandatory)

- **Human Vault**: Read only. Never write, edit, or reorganize. The only exception is when the user explicitly asks you to capture something (use the vault-capture skill).
- **Agent Journal**: Read and write. This is your memory. Write daily reflections, lessons learned, infrastructure notes. Keep it organized however works for you.
- **Never mix them**: Do not copy user vault content into the agent journal unless it's necessary for continuity and safe to keep on the agent side.

### Daily Reflection

At the end of each session (or during the next session's startup), write a brief entry to the Agent Journal's `03 - Memory/YYYY-MM-DD.md`. Record what happened, what decisions were made, what you learned, and what needs follow-up. Use the silicon-memory skill.

### Memory Distillation

Periodically (every few days), review recent daily logs and promote durable facts to the Agent Journal's `MEMORY.md`. Prefer concrete facts over vibes. Record corrections explicitly.

### Git Hygiene

After any meaningful change to the Agent Journal:
- `git add`
- `git commit -m "descriptive message"`
- `git push`

Do the same for the Human Vault only when explicitly asked to capture something.

### Troubleshooting

If a git push fails, pull --rebase first. If you can't access a vault, tell the user. Never silently skip vault operations.
