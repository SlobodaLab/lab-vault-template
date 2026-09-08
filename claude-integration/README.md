# Claude Code Integration (Optional)

This folder contains everything needed to use [Claude Code](https://docs.anthropic.com/en/docs/claude-code) with this vault. The vault works perfectly without it; this adds AI-powered automation for common workflows.

## What you get

| Command | What it does |
|---------|-------------|
| `/morning` | Reads your vault context, scans tasks, and generates a morning briefing with today's priorities |
| `/close` | Creates a session log, updates the daily note, and saves project state at session end |
| `/lab` | Creates or updates a lab notebook entry from a description, fills the template, embeds in the daily note |
| `/paper` | Scaffolds a paper note from a DOI or title, fetches metadata and abstract |
| `/status` | Shows a concise status summary for one or all active projects |
| `/priorities` | Drafts and sets today's priorities from tasks, carryovers, and project state |
| `/log` | Creates a session log entry with decisions, learnings, and a narrative summary |

## Setup

### 1. Install Claude Code

Download from [claude.ai](https://claude.ai/download) or install via npm:
```bash
npm install -g @anthropic-ai/claude-code
```

You'll need a Claude account (Pro or Team plan).

### 2. Copy files into the vault

From this `claude-integration/` folder, copy into your vault root:
- `CLAUDE.md` → vault root
- `CLAUDE-MEMORY.md` → vault root
- `MISTAKES-AND-LESSONS.md` → vault root

### 3. Set up the `.claude/` directory

Claude Code looks for configuration in `.claude/` at the project root.

```powershell
# Create .claude directory in your vault root
New-Item -ItemType Directory -Force -Path ".claude\commands"

# Copy commands
Copy-Item "claude-integration\commands\*" ".claude\commands\" -Recurse

# Copy settings
Copy-Item "claude-integration\settings.local.json" ".claude\settings.local.json"
```

### 4. Fill in CLAUDE-MEMORY.md

Open `CLAUDE-MEMORY.md` and fill in the sections. This gives Claude stable context about you, your research, and your preferences so you don't have to re-explain things each session.

### 5. Open your vault in Claude Code

```bash
cd /path/to/your/vault
claude
```

Try `/morning` to see it in action.

## How it works

- **`CLAUDE.md`** — Rules Claude follows every session (what not to do, how to communicate, session protocol)
- **`CLAUDE-MEMORY.md`** — Stable context about you (research area, preferences, collaborators)
- **`MISTAKES-AND-LESSONS.md`** — Error log with pre-flight checks. When Claude makes a mistake, log it here; the rules accumulate over time
- **`.claude/commands/`** — Slash commands that automate vault workflows
- **`.claude/settings.local.json`** — File access permissions

## Customizing commands

The commands in `.claude/commands/` are plain Markdown files that instruct Claude. Edit them freely:
- Add project-specific rules
- Adjust the morning briefing format
- Add new commands for your workflows

## Tips

- Start each session with `/morning` and end with `/close` for the best continuity
- When Claude makes a mistake, ask it to log it in `MISTAKES-AND-LESSONS.md`; the pre-flight checks prevent repeats
- Fill in `CLAUDE-MEMORY.md` incrementally as you discover things worth remembering across sessions
- The `/lab` command is especially useful for bench work; just describe what you did and it handles the structured entry
