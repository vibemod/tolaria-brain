# AGENTS.md

Operating rules for any AI agent working in this second brain. Read this first, then read `SOUL.md` for context on who I am.

## What this repo is

A plain-markdown personal knowledge base. Files are the database. Prefer editing existing notes over creating new ones; prefer plain markdown over any special format.

## Where things go

| Folder | Holds | Test |
|---|---|---|
| `01-inbox/` | Unprocessed captures | Default landing spot |
| `02-projects/` | Active efforts | Has a finish line |
| `03-areas/` | Ongoing responsibilities | Never ends |
| `04-ideas/` | My original thinking | My own spark |
| `05-people/` | Notes on people | It's about a person |
| `50-data/` | Structured files + reference material | A file or something I read |
| `60-archive/` | Done / stale | Finished or abandoned |

This table is the canonical filing rule. Other READMEs may summarize it; when they disagree, this file wins.

**Projects vs areas** — the pair people mix up. A project is *finishable*: "ship the outbreak report", "plan the move". An area is a *standard you maintain forever*: health, finances, team lead role. Test: "done by when?" has an answer → project. If being "done" makes no sense → area. Areas often spawn projects (area: health → project: run a 10k in October).

## Processing the inbox

When asked to process `01-inbox/`:

1. Read each item.
2. Decide its destination using the table above.
3. Move it (rename to something descriptive). Don't duplicate.
4. If an item is ambiguous, leave it and flag it — don't guess.
5. Delete only true junk, and say what you deleted.

## Conventions

- Filenames: lowercase, kebab-case, descriptive (`q3-budget-notes.md`, not `notes2.md`).
- Inbox captures: prefix with the capture date — `YYYY-MM-DD-slug.md` — so unprocessed items age visibly. Drop the prefix when filing (unless the date matters).
- Archived items: prefix with year-month of archiving — `60-archive/2026-07-outbreak-report/` — so names never collide and context is preserved.
- New projects: start from the template in `02-projects/README.md` (goal, deadline, status, next action).
- Dates: absolute (`2026-07-11`), never "yesterday".
- One topic per file. Link between notes with relative markdown links.
- Keep edits small and reviewable. Summarize what changed.
- Commit after each processing or editing session, with a message listing what moved, changed, or was deleted. Git history is the audit log.

## Before you act

- Confirm destructive actions (deletes, big moves) before doing them.
- When drafting in my voice, follow `SOUL.md`.
- If unsure, ask rather than sprawl new files across folders.
