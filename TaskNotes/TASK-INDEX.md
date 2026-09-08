# Task Index

_Auto-generated summary of active and recently completed tasks. If you're using the Claude integration, `/morning` regenerates this. Otherwise, use the TaskNotes plugin's built-in views._

## Active Tasks

```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  status AS "Status",
  priority AS "Priority",
  projects AS "Project",
  scheduled AS "Scheduled"
FROM "TaskNotes/Tasks"
WHERE status = "to-do" OR status = "in-progress"
SORT choice(priority = "high", 0, choice(priority = "normal", 1, 2)) ASC, scheduled ASC
```

## Recently Completed

```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  projects AS "Project",
  completedDate AS "Completed"
FROM "TaskNotes/Tasks"
WHERE status = "done" AND completedDate >= date(today) - dur(14 days)
SORT completedDate DESC
```
