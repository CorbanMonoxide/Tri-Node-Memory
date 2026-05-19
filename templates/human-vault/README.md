# Your Vault

This is where you think about your work. The agent reads this — never writes to it.

## Structure

```
your-vault/
├── 00 - Inbox/      # Quick captures, ideas, voice notes
├── 01 - Templates/  # Your note templates
└── 02 - Projects/   # Project-specific notes and decisions
```

## What Goes Here

- Architecture decisions
- Design docs
- Project requirements
- Meeting notes
- Research and references
- Anything you want the agent to know

## Included Templates

- **Project Template** — For project tracking: objectives, action items, log updates
- **Conversation Template** — For capturing agent conversations: key points, decisions, links
- **Insights Template** — For deeper analysis: findings, impact, next steps
- **Quick Note** — Minimal template for fast captures

## What Doesn't

- Agent session logs (that's the agent's journal)
- Agent personality and rules (that's the agent's journal)
- Raw chat transcripts (inbox them, then process or delete)

## The Agent's Access

The agent pulls this repo at session start. It reads your notes to build context. It never writes — no auto-formatting, no "helpful" edits, no inserting suggestions. If the agent has an idea, it tells you in conversation and you decide.
