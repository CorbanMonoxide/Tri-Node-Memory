# Human Vault Template

This directory structure is a starting point for your human vault — the notes, decisions, and documentation the agent reads but never writes to.

## Structure

```
human-vault/
├── 00 - Inbox/          # Capture zone — quick notes, voice memos, ideas
├── 01 - Templates/      # Your note templates
├── 02 - Projects/       # Project-specific notes
├── 03 - Decisions/      # Architecture decisions, design choices
└── README.md            # Vault overview (optional)
```

## Principles

1. **You own this.** The agent reads but never writes. No auto-refactoring, no "helpful" reorganization.
2. **Write in your voice.** The agent adapts to your style, not the other way around.
3. **Link freely.** Obsidian-style `[[wikilinks]]` work if your agent framework supports them.
4. **Version control.** Git-back this vault. The agent pulls at session start to stay current.

## What Goes Here

- Project architecture decisions
- Design docs and specs
- Meeting notes
- Research and references
- Task lists and priorities
- Anything you want the agent to know across sessions

## What Doesn't

- Agent session logs (that's the agent journal)
- Agent personality/rules (that's the agent journal)
- Raw chat transcripts (inbox them, then process or delete)
