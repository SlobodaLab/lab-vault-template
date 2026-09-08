---
type: process
title: "Lab notebook system"
tags:
  - vault
  - workflow
---

# Lab notebook

How wet-lab bench work and computational runs are recorded, so entries are consistent, searchable, and surface in both the daily note and the relevant project.

## Principle

The **daily note is the lab notebook surface** — open a day and you read that day's bench work inline. Each activity is also its own **atomic entry note**, which lets a single entry appear in two places at once: on the day it happened *and* rolled up under its project.

## Where entries live

`01-Daily Notes/Lab Notebook/` — nested in the time-based zone with daily/weekly/monthly notes.

Filename: `YYYY-MM-DD_<ProjectShort>_<slug>.md` (e.g. `2026-06-15_MyProject_BHI3-media-prep`). Multiple entries per day are fine.

## Two domains

- `domain: wet` — bench work (cultures, media, extractions, assays). Template: `__templates/Lab Notebook Entry template.md`
- `domain: dry` — computational work worth reproducing (HPC/SLURM runs, pipelines, analyses with parameters and outputs). Template: `__templates/Dry Lab Entry template.md`

**The test:** *would you need this to reproduce the result, or to write a methods section?* If yes, it's a lab notebook entry regardless of domain. If it's just a record of what you did in a session (debugging, drafting, reorganizing notes), it's a session log, not a lab entry.

## Frontmatter (drives all linking)

```yaml
date: 2026-06-15
projects: "[[My Project]]"
type: lab-notebook
domain: wet           # or dry
experiment: Pilot Run  # optional; groups entries across days
logged: "14:30"
time_start: "13:00"
time_end: "16:00"
tags: [lab-notebook]
```

- `date` — makes the entry surface on that day's note
- `projects` — makes it roll up under that project's STATUS
- `type: lab-notebook` — what indexes filter on

## How entries surface

1. **Daily note** — `## Lab Notebook` section: embed the entry as `![[YYYY-MM-DD_Project_slug]]` so the full content renders inline
2. **Project STATUS** — `## Lab Notebook` section: a Dataview query lists that project's entries, matched on the `projects` frontmatter field
3. **Manual browsing** — open `01-Daily Notes/Lab Notebook/` directly

## Creating an entry

**With Claude Code:** `/lab <short description>` handles metadata, creates the entry from the template, fills it from your description, and embeds it in today's daily note.

**Without Claude:**
1. Create a new file in `01-Daily Notes/Lab Notebook/` named `YYYY-MM-DD_<ProjectShort>_<slug>.md`
2. Apply the appropriate template (wet or dry lab)
3. Fill in the frontmatter and content
4. Embed it in today's daily note under `## Lab Notebook`: `![[YYYY-MM-DD_ProjectShort_slug]]`

## Tips

- Record reagents and lot numbers in wet entries (cross-reference the reagent registry in `04-Methods/`)
- For dry entries, record enough detail to reproduce: software versions, exact commands, key parameters
- Time-stamp bench actions where possible (e.g. `**13:00** — inoculated plates`)
- One entry per experiment/activity per day; update an existing entry if you return to the same work
