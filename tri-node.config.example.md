# tri-node.config.md — Configuration Template

Copy this to `tri-node.config.md` in the root of the tri-node repo (or `~/tri-node/`) and fill in your paths.

```markdown
# Tri-Node Configuration

## Identity
Path to your agent's identity files (SOUL.md, AGENTS.md, MEMORY.md, USER.md, TOOLS.md):
`~/path/to/identity/`

## Vaults
- **Human Vault** (your notes, agent reads only): `~/human-vault/`
- **Agent Journal** (agent's memory, agent writes): `~/agent-journal/`

## Git Remotes (optional)
- Human Vault: `git@github.com:you/your-vault.git`
- Agent Journal: `git@github.com:you/agent-journal.git`
```

**Where to put this file:**
- In the tri-node repo root (recommended — travels with the framework)
- Or at `~/tri-node/tri-node.config.md` (global, shared across projects)

The bootstrap will find it automatically.
