---
date: <% tp.file.title %>
type: weekly
---

> If you missed last week's review, skip it. Don't reconstruct. Start from now.

## Looking back: last week
<!-- How did it go? One line per quarterly rock: moving / stalled / done -->
- 
- 
- 

## Looking forward: this week

### Protected Focus
<!-- 1-2 sentences: what gets non-negotiable attention this coming week -->

### Flag
<!-- Anything I'm avoiding or worried about -->

## Someday Review
<!-- First weekly note of the month only — delete this section otherwise. For each: still parked / reactivate / archive -->
```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  projects AS "Project",
  wakeDate AS "Wake"
FROM "TaskNotes/Tasks"
WHERE status = "someday"
SORT wakeDate ASC
```

---

## Tasks Completed
```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  projects AS "Project",
  completedDate AS "Completed"
FROM "TaskNotes/Tasks"
WHERE status = "done" AND completedDate >= date("<% tp.date.weekday("YYYY-MM-DD", 0, tp.file.title, "gggg-[W]ww") %>") AND completedDate <= date("<% tp.date.weekday("YYYY-MM-DD", 6, tp.file.title, "gggg-[W]ww") %>")
SORT completedDate ASC
```

## Daily Notes This Week
```dataview
LIST
FROM "01-Daily Notes"
WHERE date >= date("<% tp.date.weekday("YYYY-MM-DD", 0, tp.file.title, "gggg-[W]ww") %>") AND date <= date("<% tp.date.weekday("YYYY-MM-DD", 6, tp.file.title, "gggg-[W]ww") %>")
SORT file.name ASC
```
