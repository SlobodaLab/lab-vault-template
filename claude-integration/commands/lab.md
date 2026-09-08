Create **or update** a lab notebook entry. Argument: $ARGUMENTS (short description of the work, e.g. "BHI media prep", "streaked plates at 3pm", "MetaPhlAn profiling run").

Entries cover **two domains**:

- `domain: wet` — bench work (cultures, media, extractions, assays)
- `domain: dry` — computational work worth reproducing (HPC/SLURM runs, pipelines, analyses with parameters and outputs)

**The test:** *would you need this to reproduce the result, or to write a methods section?* If yes, it's a lab notebook entry. If it's a record of a conversation (debugging, drafting, reorganizing), it's a session log via `/log`.

If the domain is ambiguous from the argument, ask before writing.

## Step 1 — New entry, or update?

1. List today's existing entries: `01-Daily Notes/Lab Notebook/YYYY-MM-DD_*.md`
2. Decide:
   - If the user explicitly said new or update, follow that
   - Otherwise: same project/experiment as an existing entry today = **update**; different work = **new entry**
   - **State your recommendation and confirm before writing**

## Step 2 — Update an existing entry

- Append new information to the appropriate section
- Time-stamp bench actions where a time is given (e.g. `**13:00** — ...`)
- Do not re-embed in the daily note (the embed auto-updates)
- Confirm: "Updated [filename]."

## Step 3 — Create a new entry

1. **Metadata:**
   - `date`: today
   - `projects`: infer from context; if ambiguous, ask. Wikilink to the project note.
   - `domain`: `wet` or `dry`
   - `experiment`: optional grouping (e.g. `Pilot Run`)
   - `logged`: current time (HH:MM, 24h)
   - `time_start` / `time_end`: ask the user. Accept casual answers and normalize to HH:MM.
   - `slug`: short kebab-case descriptor

2. **Create** at `01-Daily Notes/Lab Notebook/YYYY-MM-DD_<ProjectShort>_<slug>.md` using:
   - wet → `__templates/Lab Notebook Entry template.md`
   - dry → `__templates/Dry Lab Entry template.md`

3. **Fill** from the conversation/args. Leave unknown fields as blank or `(to fill in)`.

4. **Embed** in today's daily note under `## Lab Notebook`:
   ```
   ![[YYYY-MM-DD_<ProjectShort>_<slug>]]
   ```

5. Confirm: "Lab notebook entry created: [filename]. Embedded in today's daily note."
