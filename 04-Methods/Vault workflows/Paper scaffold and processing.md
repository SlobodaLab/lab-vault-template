---
type: process
title: "Paper scaffold and processing"
tags:
  - vault
  - workflow
---

# Paper scaffold and processing

Workflow for adding new papers to the vault and maintaining the paper library.

## Quick start

**With Claude Code:** Run `/paper` with a DOI, title, or "AuthorYear" identifier. The skill handles everything below automatically.

**Without Claude:** Follow the manual steps below.

## Adding a paper manually

1. Create a new file in `03-Papers/` named with a citation key: `AuthorYear-xx.md` (e.g., `Smith2025-ab.md`)
2. Apply the `Paper notes template` from `__templates/`
3. Fill in frontmatter: title, authors, DOI, journal, year
4. Set `status: to-read`
5. Paste the abstract into **Abstract / TL;DR**
6. Set the `projects:` field to link to relevant project(s)
7. Add the paper to `WIKILINK-TARGETS.md` under Papers
8. Add to the reading queue in `VAULT-INDEX.md`

## Citation key format

`AuthorYear-XX` where Author is the first author's surname, Year is the publication year, and XX is a short suffix to distinguish papers. Use whatever citation manager key format you prefer, or just pick two letters.

## Paper template sections

| Section | When to fill |
|---------|-------------|
| Frontmatter (metadata, tags, projects) | At scaffold time |
| Abstract / TL;DR | At scaffold time |
| Key Findings | After reading |
| Methods | After reading |
| Relevance to My Work | After reading |
| Questions / Critiques | After reading |
| Cite-as | After reading |
| Related Papers | After reading |

The **Cite-as** section is particularly useful: write the one-sentence claim you'd actually use in a manuscript, with this paper as the citation. When writing, you can search your `03-Papers/` folder for cite-as statements.

## Key files

- `__templates/Paper notes template.md`
- `03-Papers/` — all paper notes
- `WIKILINK-TARGETS.md` — paper link targets
