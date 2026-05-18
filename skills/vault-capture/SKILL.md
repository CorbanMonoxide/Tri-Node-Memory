---
name: vault-capture
description: Capture notes, ideas, and conversations into the Human Vault. Use when the user starts a message with /note, sends a voice message intended as a note, or asks to record a conversation. This skill handles multi-step ingestion, template enrichment, and final commit to the git-backed human vault while maintaining a strict boundary between user and agent data.
---

# Vault Capture

Manage the capture of information into the Human Vault.

## Security & Boundaries

- **Human Vault**: Private user data. Read only except when explicitly capturing.
- **Agent Journal**: Your continuity data. Never mix with user data.
- **Protocol**: Only write to the Human Vault when explicitly requested (via `/note`, "capture this", "save this to my notes", etc.).

## Ingestion Workflow

### 1. Quick Notes & Voice Captures
When a message starts with `/note` or a voice transcript indicates a note:
- Create a clear, descriptive filename: `YYYY-MM-DD - [Topic].md`
- Place in the Human Vault's inbox directory
- Tag appropriately based on the vault's conventions

### 2. Conversation Recording
When asked to record or save a conversation:
1. Summarize key decisions and action items
2. Include verbatim quotes for critical context
3. Format: `YYYY-MM-DD - Conversation - [Topic].md`
4. Place in the Human Vault

## Enrichment

1. **Draft**: Create the file in the target directory
2. **Enrich**: Tag the content with 3-5 relevant tags. Link to existing notes if the vault uses wikilinks
3. **Git**: Immediately `git add`, `git commit -m "Capture: [Topic]"`, and `git push`
4. **Confirm**: Notify the user that the note has been captured and pushed

## Multi-step Capture Protocol
1. **Ingest**: Read the raw input/transcript
2. **Enrich**: Match to a template if available, add tags and links
3. **Finalize**: Write, commit, and push
