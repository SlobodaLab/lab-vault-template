---
type: process
title: "Manuscript review workflow"
tags:
  - vault
  - workflow
---

# Manuscript Review Workflow

A two-pass review and edit workflow for manuscripts. Works with any reviewer (AI or human), designed to stay within manageable scope and produce a clear audit trail.

## Prerequisites

1. **Get the manuscript into Markdown.** If it's in Word, convert with pandoc:
   ```bash
   pandoc "manuscript.docx" -t markdown --wrap=none -o "02-Projects/ProjectName/Manuscript draft.md"
   ```
2. **Back up the original.** Keep a copy of the pre-edit version before starting.

## Two-pass workflow

### Pass 1 — Review only

Read the manuscript and produce a numbered review note:

**Output file:** `02-Projects/ProjectName/Review — [manuscript name].md`

Each item includes:
- **Number** for reference
- **Location** (section, approximate line)
- **Category**: correction / structural addition / rewrite / flag
- **What to change** with specific proposed text where possible
- **Why**
- **Confidence**: certain / guess (with what needs verification)

No edits are made to the manuscript in this pass. Review the list and approve, modify, or reject each item before proceeding.

### Pass 2 — Edit

Apply approved items from the review note. For each edit:
1. Apply the change with a `[Edit]` or `[Edit: guess]` marker
2. Log a one-line entry to the changelog (see below)
3. Move to the next item

This pass is mechanical because the analysis was done in Pass 1.

## Incremental changelog

Maintained as changes are made, not reconstructed after the fact.

**Location:** Either `## Edit Log` at the bottom of the manuscript, or a companion `Edit changelog.md` in the same project folder.

**Format:** One line per change:
```
- [location] change description (category: correction/addition/guess)
```

## After editing

- Remove `[Edit]` markers once verified by the author
- Convert `[Edit: guess]` items to verified text or flag for co-authors
- Archive the review note once all items are resolved
