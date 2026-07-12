---
name: process-inbox
description: Process the tolaria-brain 01-inbox/ — read each captured item and file it into 02-projects/, 03-areas/, 04-ideas/, 50-data/, or 60-archive/ following the rules in AGENTS.md. Use when the user says "process the inbox", "clear my inbox", "sort my notes", "empty the inbox", or "file these".
---

# Process the inbox

Sort everything in `01-inbox/` into its correct home. `AGENTS.md` is the canonical filing rule — read it first if unsure.

## Steps

1. **List** every item in `01-inbox/` (files and folders). If it's empty, say so and stop.
2. **Read** each item enough to classify it.
3. **Classify** using the table in `AGENTS.md`:
   - Has a finish line ("done by when?") → `02-projects/`
   - Ongoing standard you maintain → `03-areas/`
   - Your own spark or hunch → `04-ideas/`
   - A file, export, or something you read elsewhere → `50-data/`
   - Already done or dead → `60-archive/`
4. **Move** it. Rename to lowercase kebab-case and descriptive (`q3-budget-notes.md`). Drop the capture-date prefix unless the date matters. Don't duplicate — move, don't copy.
   - New projects: apply the header template from `02-projects/README.md` (Goal, Deadline, Status, Next action).
   - Archived items: prefix with year-month (`60-archive/2026-07-slug/`).
5. **Flag, don't guess** — if an item is ambiguous, leave it in `01-inbox/` and list it for the user to decide.
6. **Delete only true junk** and state exactly what you deleted.

## Finish

- Summarize what moved where, what was flagged, and what was deleted.
- Confirm any destructive moves/deletes before doing them.
- Offer to commit with `git` (message listing what changed).
