Generate a morning briefing and set today's priorities. Run this at the start of each work session.

---

## 1. Read context

Do these in parallel:
- Read `VAULT-INDEX.md`
- Read `GOALS.md` (if it exists)
- Read the most recent daily note **dated strictly before today** — glob `01-Daily Notes/**/*.md` (recursive), keep only filenames matching `YYYY-MM-DD`, discard any >= today, take the highest remaining. Read specifically `## Priorities`, `## Next Session`
- Read today's daily note (`01-Daily Notes/YYYY-MM-DD.md`); create from template if missing
- Read `TaskNotes/TASK-INDEX.md` if it exists
- Read the current week's weekly note (`01-Daily Notes/01-Weekly Notes/YYYY-WNN.md`) if it exists; collect unchecked `- [ ]` items as a priority source

## 2. Planning window checks (check existence only, do not read)

If any of these are missing and within the window, surface a prompt at the end of the briefing (step 5):

- **Weekly note** for upcoming week: check Saturday/Sunday/Monday. Prompt: *"No weekly note for W[NN] yet — want to draft it now?"*
- **Monthly note**: last 3 days of month or first 2 of next. Prompt: *"No monthly review yet — want to draft it now?"*
- **Quarterly note**: last 14 days of quarter or first 7 of next. Prompt: *"No quarterly plan yet — want to draft it now?"*

## 3. Task scan

- Collect tasks with `status: to-do` or `status: in-progress` from `TaskNotes/Tasks/`
- Focus on: scheduled this week, overdue, and `priority: high`
- Any task with `status: someday` and `wakeDate` today or earlier surfaces as **waking** — ask: reactivate or re-park with a new `wakeDate`

## 4. Build priorities (max 5)

Sources: yesterday's incomplete priorities (carryovers), unchecked items from the weekly note, tasks scheduled/due today, overdue tasks, high-priority tasks, VAULT-INDEX project priorities.

- Be specific and actionable
- Where a priority maps to a single TaskNote, use a wikilink: `- [ ] [[Exact Task File Name]]`

## 5. Present briefing

Output before writing to the daily note:
- **Yesterday:** what got done, what's carrying over
- **Scheduled tasks remaining:** count
- **Today's priorities:** numbered list (max 5)
- Any planning window prompts from step 2

Ask: *"Does this look right, or any changes before I set it?"*

## 6. Write to daily note

Once confirmed, replace `## Priorities` section with the ranked checklist. Confirm: *"Priorities set for [date]."*
