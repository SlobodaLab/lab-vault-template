End the session. Run the batches in order; within each batch, run tool calls in parallel.

## Batch 1 — Gather timestamp

- **Timestamp:** `Get-Date -Format "yyyy-MM-dd_HHmm"` (needed for the log filename).

## Batch 2 — Read what you'll edit, in parallel

Read only the slices you need (use offset/limit). In one message:
- Today's daily note (`01-Daily Notes/YYYY-MM-DD.md`) — the `## Decisions Made` / `## Next Session` / `## Sessions` region
- `STATUS.md` for any project whose state changed (skip if none)
- `VAULT-INDEX.md` if active projects/priorities changed (skip if not)

Skip any file you already edited this session.

## Batch 3 — Write everything in parallel

- **Create session log:** `10-Session-Logs/YYYY-MM-DD_HHMM_slug.md` with full session details (using `/log` format)
- **Update daily note:** fill `## Decisions Made`, `## Next Session`, and add `## Sessions` index entry
- **Update STATUS.md** for any changed project
- **Update VAULT-INDEX.md** if anything changed

## Batch 4 — Text only (no tool calls)

- **Lab entry check:** If the session included computational work worth reproducing (HPC run, pipeline, analysis with parameters), flag it: *"This session included [X] — worth a lab entry via `/lab`?"* Do NOT write the entry; just prompt. Skip if nothing qualifies.
- **Confirm:** "Session closed. Log written to [filename], daily note updated."
