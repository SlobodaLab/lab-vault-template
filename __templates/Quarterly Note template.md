---
date: <% tp.file.title %>
type: quarterly
quarter-start: <%* const m = tp.file.title.match(/(\d{4})-Q(\d)/); const y = m?.[1] || "2026"; const q = parseInt(m?.[2] || "1"); tR += `${y}-${String((q-1)*3+1).padStart(2,"0")}-01`; %>
quarter-end: <%* const m = tp.file.title.match(/(\d{4})-Q(\d)/); const y = m?.[1] || "2026"; const q = parseInt(m?.[2] || "1"); tR += q < 4 ? `${y}-${String(q*3+1).padStart(2,"0")}-01` : `${parseInt(y)+1}-01-01`; %>
---

> If you missed last quarter's review, skip it. Don't reconstruct. Start from now.

# Review: Last Quarter

## Per-Project Assessment
<!-- For each active project: what moved, what stalled, key milestones hit -->

### 

## Publications & Submissions
<!-- Papers submitted, revised, accepted, published -->
-

## Honest Assessment
<!-- What did I avoid and why? What did I tell myself I'd do but didn't? What shifted and why? What does this tell me about how I work? -->

## Time & Attention
<!-- What did I actually spend time on vs. what I planned? Any patterns? -->

---

# Plan: Upcoming Quarter

> **Snapshot at the start of the quarter.** `GOALS.md` is the living version — update there, not here. This section is an archive of what the plan looked like when written.

## Rocks
<!-- 2-3 things that MUST see meaningful progress. Be specific. -->
1. **[Rock name]** — milestone: 
2. **[Rock name]** — milestone: 
3. **[Rock name]** — milestone: 

## Explicitly Deprioritized
<!-- What I am NOT doing this quarter. Name it. -->
-

## External Anchors
<!-- Fixed deadlines, meetings, travel, grant cycles, conferences -->
-

---

## Tasks Completed This Quarter
```dataview
TABLE WITHOUT ID
  file.link AS "Task",
  projects AS "Project",
  completedDate AS "Completed"
FROM "TaskNotes/Tasks"
WHERE status = "done" AND completedDate >= date(this.quarter-start) AND completedDate < date(this.quarter-end)
SORT completedDate ASC
```

## Monthly Notes This Quarter
```dataview
LIST
FROM "01-Daily Notes/01-Monthly Notes"
WHERE date >= date(this.quarter-start) AND date < date(this.quarter-end)
SORT file.name ASC
```
