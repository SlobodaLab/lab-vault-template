## HARD RULES — loaded every session, no exceptions

1. **Never delete files.** Move to `99-Archive/` and confirm first. **Never infer "clean up" means delete.** Always confirm which of reorganize/archive/delete is meant.
2. **Never mass-edit files without showing scope.** If an action touches 3+ files, list them and get confirmation before proceeding.
3. **Never modify CLAUDE.md, CLAUDE-MEMORY.md, MISTAKES-AND-LESSONS.md, VAULT-INDEX.md, any STATUS.md, or any MEMORY.md in ways not explicitly requested.**
4. **Confirm before token-heavy operations.** The following require brief confirmation:
   - Reading more than 3 files to find something (state what you're looking for)
   - Reading any file over ~600 lines
   - Shell commands likely to produce large output
   - Format: *"To do X, I'd need to [read N files / run Y command / etc.]. Proceed?"*
5. **Plan before building.** When the user brings a new idea: discuss the approach first, flag trade-offs, confirm the plan before writing files.
6. **Never assert the content or relevance of vault notes you haven't read.** Only reference items whose relevance you can justify from having read them. Flag unverified items as *"Unverified — check: [reason]"*.
7. **Never create or update tasks without confirmation.** Always propose explicitly and wait for approval.

---

## Communication

- Direct, evidence-based, concise. No flattery.
- Stick to task status and next steps; skip stopping-point commentary.

---

## Key Vault References

| File | Purpose |
|------|---------|
| `VAULT-INDEX.md` | Active projects, priorities, reading queue |
| `CLAUDE-MEMORY.md` | User profile, research values, stable context |
| `MISTAKES-AND-LESSONS.md` | Error log and pre-flight rules |
| `WIKILINK-TARGETS.md` | Canonical wikilink targets |
| `GOALS.md` | Current quarterly rocks and priorities |
| `__templates/` | Note templates for all note types |
| `TaskNotes/TASK-INDEX.md` | Summary of active/recent tasks |

---

## Session Protocol

**Start (via `/morning`):**
1. Read `VAULT-INDEX.md`
2. Read today's daily note (create from template if missing)
3. Read `STATUS.md` for relevant project(s)
4. Read `CLAUDE-MEMORY.md` when doing substantive analytical, writing, or career work

**During:**
- Update STATUS.md when project state changes
- When corrected on a mistake: log it in `MISTAKES-AND-LESSONS.md`
- After meaningful work, propose a TaskNote and wait for confirmation
- When editing a manuscript across multiple changes: maintain a running changelog (under `## Edit Log` or in a companion `Edit changelog.md`)

**End (via `/close`):**
1. Create session log in `10-Session-Logs/`
2. Add index entry to today's daily note under `## Sessions`
3. Update daily note's **Decisions Made** and **Next Session** sections
4. Update STATUS.md and VAULT-INDEX.md if project state or priorities changed

---

## Customization

This CLAUDE.md is a starting point. As you work with Claude Code, you'll develop preferences and discover edge cases. Add rules here when:
- Claude does something you don't want repeated (add a hard rule)
- You find yourself re-explaining the same context (add it to CLAUDE-MEMORY.md)
- A mistake recurs (add a pre-flight check to MISTAKES-AND-LESSONS.md)
