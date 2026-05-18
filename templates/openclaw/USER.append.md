# USER.md — Tri-Node Append

Copy this into your agent's USER.md. Fill in the vault URLs with your actual repos.

---

## Tri-Node Vault Configuration

### Vault URLs

Replace these with your actual git remote URLs:

```
Human Vault (read-only):  git@github.com:you/your-vault.git
Agent Journal (read-write): git@github.com:you/agent-journal.git
```

### Local Paths

```
Human Vault: ~/my-vault/
Agent Journal: ~/agent-journal/
```

### Preferences

- **Vault format**: Obsidian (markdown with [[wikilinks]])
- **Templates**: Stored in the Human Vault's `01 - Templates/` directory
- **Capture protocol**: The agent uses the vault-capture skill for any writes to the Human Vault
