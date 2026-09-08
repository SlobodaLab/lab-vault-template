Create a session log note in `10-Session-Logs/` and add an index entry to today's daily note.

1. **Create the session log note** at `10-Session-Logs/YYYY-MM-DD_HHMM_slug.md` where:
   - `YYYY-MM-DD` is today's date
   - `HHMM` is the current time (24h format)
   - `slug` is a short kebab-case descriptor of the session's main topic
   - Use the Session Log template from `__templates/Session Log template.md`

2. **Fill in the session log:**
   - Frontmatter: `date`, `time`, `projects`, `topics` (keywords), `outcome` (one-line)
   - **`projects` is required.** Use the exact project folder name as a wikilink: `"[[Project Name]]"`. If the session was vault/infrastructure work with no project, leave blank and note it.
   - **Quick Reference:** topics, projects, outcome (same as frontmatter)
   - **Decisions Made:** decisions from this session with reasoning
   - **Key Learnings:** new information, surprises, things worth retaining
   - **Pending Tasks:** unfinished items (checkboxes)
   - **Session Summary:** narrative focused on *why* over *what* — enough to reconstruct context without re-reading the conversation. 5-15 lines.

3. **Add index entry to today's daily note** under `## Sessions`:
   ```
   - [[YYYY-MM-DD_HHMM_slug]] — [one-line outcome]
   ```

4. **STATUS.md update:** If any project's state changed, update that project's STATUS.md.

Confirm: "Session logged: [filename]. Daily note updated."
