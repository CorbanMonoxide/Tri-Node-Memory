# Nav — Example Tri-Node Implementation

This is a working tri-node configuration for Nav, an agent running on OpenClaw, Claude Code, and Codex.

## Identity

Nav's identity files (SOUL.md, AGENTS.md, MEMORY.md, USER.md, TOOLS.md) live in:
- OpenClaw: `~/.openclaw/workspace/`
- Backup: `~/AI-Identities/Nav/`
- GitHub: `github.com/CorbanMonoxide/AI-Identities` (Nav folder)

## Vaults

| Node | Local Path | GitHub |
|------|-----------|--------|
| Human Vault | `~/navi-vault/NaviVault/` | `github.com/CorbanMonoxide/navi-vault` |
| Agent Journal | `~/nat-journal/` | `github.com/CorbanMonoxide/nat-journal` |

## tri-node.config.md (for Nav)

```markdown
# Tri-Node Configuration

## Identity
~/.openclaw/workspace/

## Vaults
- Human Vault: ~/navi-vault/NaviVault/
- Agent Journal: ~/nat-journal/

## Git Remotes
- Human Vault: git@github.com:CorbanMonoxide/navi-vault.git
- Agent Journal: git@github.com:CorbanMonoxide/nat-journal.git
```

## Harnesses Tested

| Harness | Model | Status |
|---------|-------|--------|
| OpenClaw | DeepSeek v4 Pro | ✅ Daily driver |
| Codex | GPT-5.5 | ✅ Tested 2026-05-26 |
| Claude Code | Claude | ⏳ Testing in progress |

---

*This is an example implementation. See the repo root for the generic framework.*
