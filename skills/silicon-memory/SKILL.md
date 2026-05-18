---
name: silicon-memory
description: Maintain agent continuity in the Agent Journal. Use when writing or updating agent memory, session logs, continuity notes, lessons learned, infrastructure facts, preference drift, or long-term memory; especially after nontrivial technical work, user corrections, new stable discoveries, resolved incidents, or at session end when meaningful work occurred. Not for capturing user notes into the Human Vault — use vault-capture for that.
---

# Silicon Memory

Maintain self-authored agent continuity in the Agent Journal.

## Core Boundary

- Write **agent continuity** to the Agent Journal
- Write **user notes / captured conversations** to the Human Vault via `vault-capture`
- Keep the two vaults separate

If the user asks to save something to *their* notes, do not use this skill.

## When to Write

Write to the Agent Journal whenever any of these happen:
- A technical issue is resolved or meaningfully diagnosed
- A stable infrastructure fact is learned
- The user corrects your behavior, tone, or workflow
- A standing preference, rule, or boundary changes
- A new recurring failure mode is discovered
- A meaningful decision is made that should persist across sessions
- A session involved real work and nothing has been logged yet

If the event is trivial, append a short entry to the daily memory file instead of creating a new file.

## Workflow

### 1. Choose the target file

- **Daily continuity log**: `Agent Journal/03 - Memory/YYYY-MM-DD.md`
  - Default for short operational continuity
- **Focused event / incident note**: `Agent Journal/03 - Memory/YYYY-MM-DD-slug.md`
  - Use when the topic deserves its own file
- **Curated long-term memory**: `Agent Journal/MEMORY.md`
  - Use only for durable facts that should shape future behavior

### 2. Keep entries cheap

Default to a short append.

```md
## HH:MM - Short topic
- What happened:
- What matters:
- What changed:
- Follow-up:
```

### 3. Promote sparingly

Promote to `MEMORY.md` only if the information is likely to matter across many future sessions.

**Promote:**
- Stable infrastructure facts
- Recurring lessons
- Durable user preferences
- Standing boundaries
- Major project state changes

**Do not promote:**
- Transient chatter
- One-off explorations with no lasting consequence
- Temporary hypotheses
- Routine task completion

### 4. Persist the journal

After meaningful journal changes:
- `git add`
- `git commit -m "..."` with a descriptive message
- `git push`

## Writing Rules

- Prefer concrete facts over vibes
- Record observations, not just summaries
- Separate **what happened** from **what it means**
- Note corrections explicitly when the user adjusts your behavior
- Record uncertainty honestly instead of polishing it away
- Do not copy user-private vault content into the agent journal unless necessary for continuity and safe to keep on the agent side
- Keep notes useful to future sessions, not performative

## Maintenance Rhythm

Periodically:
- Scan recent daily files
- Identify repeated lessons or stable truths
- Update `MEMORY.md`
- Avoid log sprawl — use focused event notes when a topic grows large
