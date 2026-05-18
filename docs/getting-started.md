# Getting Started

## 10-Minute Bootstrap

### 1. Set Up Your Human Vault

Your human vault is where *you* think about your work. Use Obsidian, a git repo wiki, or plain markdown files.

```bash
mkdir ~/my-vault
cd ~/my-vault
git init
mkdir -p "00 - Inbox" "01 - Templates" "02 - Projects"
# Start writing your project notes, decisions, architecture docs
```

**Copy the template structure:** [`templates/human-vault/`](../templates/human-vault/)

### 2. Set Up the Agent Journal

The agent journal is the agent's own continuity. Separate git repo, agent-owned.

```bash
mkdir ~/agent-journal
cd ~/agent-journal
git init
mkdir -p "03 - Memory"

# Copy templates
cp ../Tri-Node-Memory/templates/agent-journal/SOUL.md .
cp ../Tri-Node-Memory/templates/agent-journal/USER.md .
cp ../Tri-Node-Memory/templates/agent-journal/AGENTS.md .
cp ../Tri-Node-Memory/templates/agent-journal/MEMORY.md .
cp ../Tri-Node-Memory/templates/agent-journal/TOOLS.md .
```

### 3. Customize

- **SOUL.md** — Define the agent's identity. Who is it? What's its vibe? What are its red lines?
- **USER.md** — Tell the agent about yourself. Work style, preferences, current projects, constraints.
- **AGENTS.md** — Set the agent's session startup protocol, behavior rules, memory management.
- **MEMORY.md** — Start empty or pre-populate with project context the agent should know.

### 4. Configure Your Agent Framework

Point your agent framework (OpenClaw, etc.) at both vaults:

- **Human vault path:** Read-only for the agent
- **Agent journal path:** Read-write for the agent
- **Ensure the agent's SOUL/USER/AGENTS files are loaded at session start**

### 5. First Session

Start a session and test:
1. Agent reads your vault and builds context
2. Agent writes its first session log to `03 - Memory/`
3. Verify your vault is untouched
4. Review the agent's journal entry — transparent and correctable

## The Weekly Rhythm

- **Daily:** Agent writes session logs
- **Weekly:** Agent distills logs into MEMORY.md
- **Monthly:** Human reviews agent's MEMORY.md, corrects misunderstandings

## Next Steps

- Read the [core concept](tri-node-concept.md) for the "why"
- Read the [architecture](architecture.md) for the deep dive
- Check `examples/` for reference implementations
