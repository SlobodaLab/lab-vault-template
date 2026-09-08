---
date: <% tp.file.title %>
type: annual
---

> If you missed last year's review, skip it. Don't reconstruct. Start from now.

# Review: Last Year

## Per-Project Assessment
<!-- For each active/completed project: what moved, what stalled, what finished -->

### 

## Publications & Submissions
<!-- Full list: submitted, revised, accepted, published -->
-

## Skills & Development
<!-- Methods learned, courses, collaborations, presentations -->
-

## Honest Assessment
<!-- What did I systematically avoid? What projects are secretly dead? What am I proud of? What would I do differently? -->

## Career & Positioning
<!-- How did the year move me toward where I want to be? What didn't move? -->

---

# Plan: Upcoming Year

## Outcomes I Want
<!-- 3-5 concrete outcomes for the year. Framed as results, not tasks. -->
1. 
2. 
3. 

## Career Anchors
<!-- Job market, postdoc applications, conferences, grants, committee milestones, thesis -->
-

## Explicitly Not Doing
<!-- Projects, commitments, or directions I'm parking for the year -->
-

## What I Need to Protect
<!-- Time, attention, energy. What gets ring-fenced? -->
-

---

## Quarterly Notes This Year
```dataview
LIST
FROM "01-Daily Notes/01-Quarterly Notes"
WHERE date >= date("<% tp.file.title %>-01-01") AND date < date("<% parseInt(tp.file.title) + 1 %>-01-01")
SORT file.name ASC
```
