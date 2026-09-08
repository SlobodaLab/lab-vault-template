---
type: project
status: active
collaborators: []
---
# <% tp.file.title %>

## Overview
-

## Tasks

```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  priority AS "Priority",
  choice(status = "in-progress", "🔵 Doing", choice(status = "to-do", "⬜ To Do", "✅ Done")) AS "Status",
  completedDate AS "Completed"
FROM "TaskNotes/Tasks"
WHERE contains(projects, this.file.link) OR contains(string(projects), this.file.name)
SORT choice(status = "in-progress", 0, choice(status = "to-do", 1, 2)) ASC, choice(priority = "high", 0, choice(priority = "normal", 1, 2)) ASC
```

## Meeting Notes

```dataview
TABLE WITHOUT ID
  file.link AS "Meeting",
  date AS "Date",
  attendees AS "Attendees"
FROM "06-Meetings"
WHERE contains(projects, this.file.link) OR contains(string(projects), this.file.name)
SORT date DESC
```

## Papers

```dataview
LIST
FROM "03-Papers"
WHERE contains(projects, this.file.link) OR contains(string(projects), this.file.name)
SORT file.name ASC
```

## Notes
-
