---
type: daily-note
date: <% tp.file.title %>
projects:
interactions:
---

[[TaskNotes/Views/calendar-default.base|📅 My Week]]

## Priorities
- [ ]
- [ ]
- [ ]

## Meetings Today

```dataview
LIST WITHOUT ID file.link
FROM "06-Meetings" OR #meeting
WHERE dateformat(date, "yyyy-MM-dd") = this.file.name
```

## Work Log

```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  projects AS "Project"
FROM "TaskNotes/Tasks"
WHERE status = "done" AND date(completedDate) = date(this.file.name)
SORT file.mtime DESC
```

<!-- Free text: context, failed attempts, decisions not captured in tasks -->



## Lab Notebook
<!-- Bench work (domain: wet) and computational runs worth reproducing (domain: dry). Add entries manually from templates or with /lab if using Claude. They embed here as ![[entry]]. -->



## On My Radar
```dataview
LIST FROM "TaskNotes/Tasks"
WHERE contains(contexts, "@radar") AND status != "done"
```

## Decisions Made
<!-- Things you settled today that you'd otherwise second-guess later. Include the reasoning. -->
-

## Next Session
<!-- Tasks to pick up. Unresolved questions. Things to check. -->
-

## Sessions
<!-- If using Claude Code: /close adds session log links here. Otherwise use for links to any work notes. -->

