# HEARTBEAT.md Template

Defines what the agent does during periodic health checks. Copy to agent journal root.

---

# HEARTBEAT.md

[Customize this with your agent's periodic task list. Examples below.]

## Maintenance Checks

- **Vault sync:** git pull human vault, check for new notes
- **Inbox triage:** Process any new items in the human vault inbox
- **Memory hygiene:** Check if daily logs need distilling into MEMORY.md

## Proactive Work

[Things the agent can do without asking during quiet periods.]

- Read and organize memory files
- Review and update MEMORY.md
- Commit and push agent journal changes
- Check project statuses (git status, CI, etc.)

## When to Reach Out

- Important external event detected
- Calendar event coming up (< 2 hours)
- Pattern detected worth surfacing
- It's been > 8 hours since the last check-in

## When to Stay Silent

- Late night (23:00-08:00) unless urgent
- Human is clearly busy
- Nothing new since last check
