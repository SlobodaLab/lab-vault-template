---
type: process
title: "Task management"
tags:
  - vault
  - workflow
---

# Task management

How tasks are tracked in the vault using the TaskNotes Obsidian plugin.

## Overview

Tasks are individual markdown files in `TaskNotes/Tasks/`. Each file has YAML frontmatter with structured fields, and a body for notes. The TaskNotes plugin renders these as a task board in Obsidian.

## Task file format

```yaml
---
status: to-do          # to-do | doing | done | someday
priority: normal       # low | normal | high
projects:
  - "[[Project Name]]"
contexts:              # @lab, @desk, @computer, etc.
scheduled: YYYY-MM-DD
dateCreated: YYYY-MM-DDTHH:MM:SS
dateModified: YYYY-MM-DDTHH:MM:SS
completedDate: YYYY-MM-DD
timeEstimate: 30       # minutes
tags:
  - task
---

Brief note about the task.
```

## Creating tasks

- **In Obsidian:** Use the TaskNotes plugin's "New task" command
- **With Claude Code:** Claude can create tasks when actionable items emerge (it will always confirm first)
- **Manually:** Create a new `.md` file in `TaskNotes/Tasks/` with the frontmatter above

## Task statuses

| Status | Meaning |
|--------|---------|
| `to-do` | Ready to work on |
| `doing` / `in-progress` | Currently active |
| `done` | Completed (set `completedDate`) |
| `someday` | Parked; not on the active list. Optionally set `wakeDate` to resurface it later |

## Relationship to STATUS.md

- `STATUS.md` tracks **project-level state**: phase, blockers, decisions
- TaskNotes tracks **individual actionable work items**
- They complement each other: a STATUS.md "next step" might map to one or more tasks

## Contexts

Use the `contexts` field to tag where/how a task can be done:
- `@lab` — needs to be in the lab
- `@desk` — desk work (reading, writing)
- `@computer` — analysis, coding
- `@radar` — not actionable yet, just watching

## Stale task triage

Periodically (weekly recommended), review tasks that haven't been updated in 7+ days:
- **Resolve** — do it now
- **Defer** — set a new `scheduled` date
- **Drop** — archive to `99-Archive/TaskNotes/`
- **Keep** — update `dateModified` to reset the clock
- **Park** — set `status: someday` for indefinite deferral

**With Claude Code:** Friday `/morning` sessions automate this triage interactively.

## Key files

- `TaskNotes/Tasks/` — individual task files
- `TaskNotes/TASK-INDEX.md` — summary view (Dataview queries)
