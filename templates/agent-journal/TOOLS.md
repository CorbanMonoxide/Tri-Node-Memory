# TOOLS.md Template

Environment-specific configuration for the agent. Skills define *how* tools work. This file is for *your* specifics.

Copy to agent journal root.

---

# TOOLS.md — Local Notes

## What Goes Here

- SSH hosts and aliases
- API key references (never the keys themselves)
- Device nicknames
- Vault paths
- Environment-specific paths
- Anything that changes between deployments

## Vaults

- **Human Vault:** `~/human-vault/` — [Description, remote URL]
  - **Inbox:** `00 - Inbox/`
  - **Templates:** `01 - Templates/`
- **Agent Journal:** `~/agent-journal/` — [Description, remote URL]

## Repositories

- **Repo 1:** `git@github.com:user/repo.git` — [Description]

## Network

```bash
# SSH aliases
ssh hostname@ip

# Machines
# hostname — IP — OS — Role
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.
