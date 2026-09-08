Scaffold a new paper note. Argument: $ARGUMENTS (DOI, title, or "AuthorYear" identifier).

1. Determine the citation key (AuthorYear-suffix format, e.g., Smith2025-ab). If a DOI is provided, fetch metadata to construct it.
2. Confirm the citation key before creating the file.
3. Create `03-Papers/[citation key].md` from `__templates/Paper notes template.md`.
4. Fill in frontmatter: title, authors, DOI, journal, year, set `status: to-read`.
5. Replace the placeholder header block with values from the frontmatter (title, first_author, journal, year, status, DOI, PMID).
6. If a DOI was provided, fetch and paste the abstract into the **Abstract / TL;DR** section.
7. Ask which project(s) to link in the `projects:` field.
8. Add the new paper to `WIKILINK-TARGETS.md` under Papers.
9. Add to the reading queue in `VAULT-INDEX.md`.
