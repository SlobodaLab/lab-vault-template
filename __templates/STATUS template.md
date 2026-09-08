---
type: project-status
projects: ""
status: active
last-updated:
---

# [Project Name] — Status

## Current Phase
<!-- e.g., Data analysis | Writing | Revision | Waiting for data -->

## What's Done
-

## Active Work
<!-- What's currently in progress or running (e.g., HPC jobs, ongoing analyses) -->
-

## Blockers
<!-- What's stopping progress? -->
-

## Next Steps
<!-- Ordered. First item = next thing to do. -->
1.

## Lab Notebook
<!-- Lab entries for this project (auto-listed by Dataview; matched on project folder). -->
```dataviewjs
const here = dv.current().file.folder;
const inProject = (p) => {
  if (!p.projects) return false;
  const links = Array.isArray(p.projects) ? p.projects : [p.projects];
  return links.some(l => { const pg = l && l.path ? dv.page(l.path) : null; return pg && pg.file.folder === here; });
};
const entries = dv.pages('"01-Daily Notes/Lab Notebook"').where(inProject).sort(p => p.date, 'desc');
if (entries.length) {
  dv.table(["Date", "Entry", "Experiment"], entries.map(p => [p.date, p.file.link, p.experiment ?? ""]));
} else {
  dv.paragraph("_No lab notebook entries yet._");
}
```

## Key Decisions Log
<!-- Append decisions as they're made. Date each entry. -->

| Date | Decision | Rationale |
|------|----------|-----------|
|      |          |           |
