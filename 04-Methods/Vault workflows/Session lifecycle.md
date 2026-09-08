---
type: process
title: "Session lifecycle"
tags:
  - vault
  - workflow
---

# Session lifecycle

The full cycle of a working session in this vault. Works with or without Claude Code.

## Session start

Whether you use `/morning` (with Claude) or do this manually, the goal is the same: orient yourself and set priorities.

1. Open today's daily note (auto-created by the Journals plugin, or create from template)
2. Check yesterday's note for carryovers (`## Next Session`, incomplete `## Priorities`)
3. Glance at `VAULT-INDEX.md` for active project states
4. Scan your task board (TaskNotes plugin) for overdue or due-today tasks
5. Write 3-5 priorities in today's `## Priorities` section

**With Claude Code:** `/morning` automates all of this and presents a briefing for you to confirm.

### Weekly review cadence

- **Weekly notes** (e.g., `2026-W35.md`): look back on last week, set protected focus for this week
- **Monthly notes** (optional): rocks check, honest reflection
- **Quarterly notes**: full project assessment, set new rocks in `GOALS.md`
- **Annual notes**: year-level reflection and planning

Create these from the templates in `__templates/` when you're ready. Start with weekly notes; add monthly and quarterly once you have a few months of data.

## During session

- Do your work
- Update `STATUS.md` when a project's state changes
- Log decisions in the daily note's `## Decisions Made` (include reasoning)
- After meaningful work, create a task in `TaskNotes/Tasks/` if there's a clear next action

## Session end

When you're done for the day:

1. Fill in `## Decisions Made` if you haven't already
2. Write `## Next Session` notes (what to pick up, unresolved questions)
3. Update `STATUS.md` for any project whose state changed

**With Claude Code:** `/close` automates all of this and also creates a detailed session log in `10-Session-Logs/`.

## Key files

- `__templates/Daily Note template.md`
- `__templates/Weekly Note template.md`
- `VAULT-INDEX.md`
- Per-project `STATUS.md`
