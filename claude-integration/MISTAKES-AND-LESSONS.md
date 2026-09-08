# Mistakes and Lessons

_A running log of errors and the rules derived from them. When Claude makes a mistake, log it here. Over time, the pre-flight checks accumulate into institutional memory that prevents repeats._

## How This File Works

1. **Log it** — Record in Incident Log below
2. **Fix it** — Apply the fix (correct the file, redo the action)
3. **Audit it** — Identify root cause; add a permanent pre-flight rule if warranted
4. **Resolve it** — Move to the Resolved section or delete the log entry; keep this file lean

---

## Pre-Flight Checks

_Rules derived from past mistakes. Claude reads these before relevant operations._

**Before scaffolding a paper note:**
- Always copy the full template content verbatim, including any dataview blocks; do not reconstruct manually

**Before writing any file:**
- Verify the target directory exists before writing

**Before concluding that data is absent from an API or query result:**
- An empty result means "my query did not cover it," not "it does not exist." State the window and filter before drawing a conclusion from zero rows.

_Add your own rules as mistakes happen. The best rules are specific, actionable, and reference the incident that prompted them._

---

## Incident Log

<!-- Template:
- Date: YYYY-MM-DD
- What happened: [description]
- Root cause: [why it happened]
- Status: pending / investigating / fixed
-->

_(No incidents logged yet.)_
