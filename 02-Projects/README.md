# Projects

Each project gets its own subfolder here. Inside each folder, create at minimum:

1. **A main project note** — overview, collaborators, links to related papers and data
2. **A `STATUS.md`** — the single source of truth for "where is this project at?"

Use the templates in `__templates/` to create these:
- `Project template.md` for the main note
- `STATUS template.md` for the status file

## The STATUS.md Pattern

Every project has a STATUS file that tracks:
- **Current phase** (data collection, analysis, writing, revision, etc.)
- **What's done** so far
- **Active work** in progress
- **Blockers** stopping progress
- **Next steps** in priority order
- **Key decisions** with dates and rationale

This is the file you read when you come back to a project after time away. Keep it updated — your future self will thank you.

## Example structure

```
02-Projects/
├── My First Project/
│   ├── My First Project.md      ← overview
│   ├── STATUS.md                ← current state
│   ├── Manuscript draft.md      ← if writing
│   └── Analysis notes.md        ← working notes
├── Side Project/
│   ├── Side Project.md
│   └── STATUS.md
```

## Linking

- Tasks in `TaskNotes/Tasks/` link to projects via their `projects:` frontmatter field
- Papers in `03-Papers/` link to projects the same way
- Lab notebook entries in `01-Daily Notes/Lab Notebook/` link via `projects:` too
- Dataview queries in the project template and STATUS template automatically pull in all linked items
