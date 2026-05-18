# Setup Guide

## Before You Start

You need:
- [Obsidian](https://obsidian.md) installed (or any markdown editor)
- Two empty GitHub repos created
- An OpenClaw agent already running

---

## Step 1: Create Your Two Vaults

### Your Vault (Human)

This is where *you* think about your work. Create an Obsidian vault, init git, and link it to one of your GitHub repos.

```bash
mkdir ~/my-vault
cd ~/my-vault
git init
git remote add origin git@github.com:you/your-vault.git

# Copy the human vault structure from this repo
cp -r Tri-Node-Memory/templates/human-vault/* .
git add -A && git commit -m "Init: tri-node human vault" && git push -u origin main
```

### The Agent's Journal

This is the agent's own memory. Separate vault, separate repo.

```bash
mkdir ~/agent-journal
cd ~/agent-journal
git init
git remote add origin git@github.com:you/agent-journal.git

# Copy the agent journal structure
cp -r Tri-Node-Memory/templates/agent-journal/* .
git add -A && git commit -m "Init: tri-node agent journal" && git push -u origin main
```

---

## Step 2: Append Tri-Node Rules to Your Agent

Your OpenClaw agent already has SOUL.md, AGENTS.md, USER.md, and IDENTITY.md. Don't replace them — append the tri-node rules.

Open each append template from `templates/openclaw/` and copy its contents into the matching file in your agent's workspace:

- `SOUL.append.md` → Append to your agent's `SOUL.md`
- `AGENTS.append.md` → Append to your agent's `AGENTS.md`  
- `USER.append.md` → Append to your agent's `USER.md`
- `IDENTITY.append.md` → Append to your agent's `IDENTITY.md`

**Important:** Update the vault URLs in `USER.append.md` to point to your actual repos.

---

## Step 3: Install the Skills

Copy the two skills into your agent's skills directory:

```bash
cp -r Tri-Node-Memory/skills/vault-capture ~/.openclaw/workspace/skills/vault-capture
cp -r Tri-Node-Memory/skills/silicon-memory ~/.openclaw/workspace/skills/silicon-memory
```

These skills handle:
- **vault-capture** — Reading your vault, capturing notes, committing changes
- **silicon-memory** — Writing to the agent journal, daily reflections, memory distillation

---

## Step 4: Tell Your Agent About the Vaults

In your agent's `USER.md` (with the tri-node append rules), fill in:

```markdown
## Vault Configuration
- **Human Vault**: git@github.com:you/your-vault.git (local: ~/my-vault/)
- **Agent Journal**: git@github.com:you/agent-journal.git (local: ~/agent-journal/)
```

Your agent will now:
- Pull both vaults at session start
- Read your vault to build context (never write to it)
- Write its daily reflections and memory to the agent journal

---

## Step 5: Test

Start a new agent session. Watch the logs — you should see it pull both repos. Ask it to capture a note. Check that the note lands in your vault, not the agent's journal. Check that the agent writes its own reflection to its journal.

If the boundary holds, it's working.

---

## The Weekly Rhythm

- **Daily**: Agent writes session logs to `agent-journal/03 - Memory/`
- **Weekly**: Agent distills logs into `agent-journal/MEMORY.md`
- **Monthly**: You review the agent's MEMORY.md, correct misunderstandings

---

## Troubleshooting

- **Agent can't push to vaults**: Make sure the git remotes use SSH and the agent has key access
- **Agent is writing to your vault**: Check AGENTS.md — the "read human vault, write to agent journal" rule must be clear
- **Skills not loading**: Verify skill directories are in the agent's configured skills path
