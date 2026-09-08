# Research Vault Template

A structured [Obsidian](https://obsidian.md) vault for managing research projects, lab notebooks, paper libraries, tasks, and career planning. Designed for graduate students and postdocs in wet-lab and computational research, but adaptable to any research workflow.

Everything stays on your computer as plain Markdown files. No cloud lock-in, no proprietary formats.

## Getting Started

1. **Download [Obsidian](https://obsidian.md/download)** (free for personal use)
2. **Get this vault** — click the green **Code** button above → **Download ZIP**, or click **Use this template** if you have a GitHub account
3. **Open in Obsidian** — Open folder as vault → select the extracted folder → Trust and enable plugins
4. **Install plugins** — see the [detailed setup guide](SETUP.md) for the plugin list and configuration

For complete step-by-step instructions, see **[SETUP.md](SETUP.md)**.

## If You're New to Obsidian

Obsidian is a note-taking app where your notes are plain Markdown files in a folder on your computer. A few things to know:

- **Notes are files.** Every note is a `.md` file. You can open them in any text editor, back them up normally, and they'll outlast any app.
- **Links connect notes.** Type `[[` to link to another note. This is how projects, papers, tasks, and daily notes connect to each other.
- **Search is powerful.** `Ctrl/Cmd + O` opens the quick switcher (find any note by name). `Ctrl/Cmd + Shift + F` searches content across all notes.
- **Templates save time.** When creating a new note, use `Ctrl/Cmd + P` → "Templater: Insert template" to apply a template.
- **The command palette does everything.** `Ctrl/Cmd + P` opens it. Search for any action.

For more: [Obsidian's official docs](https://help.obsidian.md/) and the [community hub](https://obsidian.md/community).

## Vault Structure

```
00-Inbox/          Capture anything quickly; sort later
01-Daily Notes/    Daily journal, weekly/monthly/quarterly reviews, lab notebook
02-Projects/       One subfolder per research project, each with a STATUS.md
03-Papers/         Literature notes (one file per paper)
04-Methods/        Protocols, workflows, and how-to docs
05-Data Analysis/  Analysis notes and results
06-Meetings/       Meeting notes
07-Knowledge/      Reference material, concepts, evergreen notes
08-Career/         Applications, CVs, career planning
09-Contacts/       People you work with
10-Session-Logs/   Work session records (used with Claude Code integration)
99-Archive/        Completed or inactive items (never delete, archive here)
TaskNotes/         Individual task files managed by the TaskNotes plugin
__templates/       Templates for all note types
__assets/          Attachments and embedded files
__media/           Images and media
```

## Core Workflows

### Daily Notes

Your daily note is your home base. It auto-creates when you open the vault and includes:
- **Priorities** — today's task list (3-5 items)
- **Meetings** — auto-populated from meeting notes dated today
- **Work Log** — tasks completed today
- **Lab Notebook** — bench work and computational runs embedded inline
- **Decisions Made** — what you decided and why
- **Next Session** — what to pick up tomorrow

### Projects + STATUS.md

Every project gets a subfolder in `02-Projects/` with:
- A **main project note** (overview, links to papers/tasks/meetings)
- A **STATUS.md** (the single source of truth for project state)

STATUS.md tracks: current phase, what's done, active work, blockers, next steps, and a key decisions log. Read it when you come back to a project after time away. See `02-Projects/README.md` for details.

### Lab Notebook

Lab entries live in `01-Daily Notes/Lab Notebook/` as atomic notes. Each entry:
- Is embedded in the daily note (you see it inline when you open the day)
- Rolls up under its project's STATUS.md (you see all entries for a project in one place)
- Covers either **wet lab** (bench work) or **dry lab** (computational work worth reproducing)

See `04-Methods/Vault workflows/Lab notebook system.md`.

### Paper Library

Papers live in `03-Papers/` with structured metadata. Each paper note has sections for key findings, methods, relevance to your work, critiques, and a "cite-as" sentence you can grab when writing.

See `04-Methods/Vault workflows/Paper scaffold and processing.md`.

### Task Management

Individual tasks are Markdown files in `TaskNotes/Tasks/`, managed by the TaskNotes plugin. Each task has structured frontmatter (status, priority, project, scheduled date) and appears on the task board. Tasks link to projects and surface in daily notes and project views via Dataview queries.

See `04-Methods/Vault workflows/Task management.md`.

### Review Cadence

The vault supports a layered review cycle. Start with daily and weekly; add monthly and quarterly once you have enough history.

| Review | Frequency | What it covers |
|--------|-----------|---------------|
| Daily note | Every day | Priorities, decisions, next steps |
| Weekly note | Weekly | What moved, protected focus for next week |
| Monthly note | Monthly (optional) | Rocks check, honest reflection |
| Quarterly note | Quarterly | Full project assessment, set new rocks |
| Annual note | Yearly | Year-level review and planning |

### Reagent & Materials Registry

A cross-project record of physical reagents, primers, stocks, and kits in `04-Methods/Reagent and materials registry.md`. One row per item for lot traceability. Batch records link to lab notebook entries.

### Manuscript Review

A two-pass workflow (review, then edit) for manuscript revisions, with an incremental changelog for audit trails. See `04-Methods/Vault workflows/Manuscript review workflow.md`.

## Optional Add-ons

### Time Tracking with ActivityWatch

Passive time tracking using the free, open-source [ActivityWatch](https://activitywatch.net/). It runs in the background and records which apps you use; you review the data at end of day. No manual timers.

See `04-Methods/Vault workflows/Time tracking (optional).md`.

### Claude Code Integration

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) is an AI coding assistant that can work directly with your vault. The integration adds slash commands that automate common workflows:

| Command | What it does |
|---------|-------------|
| `/morning` | Morning briefing + priority setting |
| `/close` | Session wrap-up + log creation |
| `/lab` | Lab notebook entry from a description |
| `/paper` | Paper note scaffold from a DOI |
| `/status` | Project status check |
| `/priorities` | Priority drafting from tasks + project state |

The vault works completely without Claude Code. The AI layer accelerates existing workflows but doesn't replace them; every action Claude automates has a manual equivalent.

See `claude-integration/README.md` for setup.

## Key Design Principles

- **Archive, don't delete.** Move to `99-Archive/` instead of deleting. You'll thank yourself later.
- **STATUS.md is the single source of truth** for every project's state.
- **Daily note is the hub.** Everything surfaces there: priorities, meetings, lab work, decisions.
- **Templates enforce consistency.** Use them. Every note type has one.
- **Links create value.** Connect papers to projects, tasks to projects, entries to projects. The cross-references compound over time.
- **Future you is the audience.** Write decisions with reasoning. Record enough in lab entries to reproduce the work. Your future self is the primary reader.

## Acknowledgments

Developed in the [Sloboda Lab](https://www.slobodalab.com/) at McMaster University. Built iteratively through daily use over months of graduate research.

## License

This template is shared freely. Use it, adapt it, share it with your lab. No attribution required, but if it helps you, consider sharing your improvements back.
