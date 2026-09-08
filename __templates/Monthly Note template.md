---
date: <% tp.file.title %>
type: monthly
---

> If you missed last month's review, skip it. Don't reconstruct. Start from now.
>
> Monthly notes are optional — if weekly and quarterly reviews are carrying the load, skip this one.

## Rocks Check
<!-- Are the quarterly rocks still moving? One line per rock. -->
- 
- 
- 

## What Moved This Month
<!-- Brief update per active project: what actually happened -->

### 

## Honest Reflection
<!-- What did I avoid? What shifted? What am I telling myself that isn't quite true? -->

## Adjustment for Next Month
<!-- One small thing to do differently -->

---

## Tasks Completed
```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  projects AS "Project",
  completedDate AS "Completed"
FROM "TaskNotes/Tasks"
WHERE status = "done" AND completedDate >= date("<% tp.file.title %>-01") AND completedDate < date("<% tp.file.title %>-01") + dur(1 month)
SORT completedDate ASC
```

## Weekly Notes This Month
```dataview
LIST
FROM "01-Daily Notes/01-Weekly Notes"
WHERE file.name >= "<% tp.file.title %>" AND file.name < "<% tp.file.title %>-32"
SORT file.name ASC
```
