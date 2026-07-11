---
name: process-inbox
description: Process the tolaria-brain inbox/ — read each captured item and file it into projects/, areas/, ideas/, data/, or archive/ following the rules in AGENTS.md. Use when the user says "process the inbox", "clear my inbox", "sort my notes", "empty the inbox", or "file these".
---

# Process the inbox

Sort everything in `inbox/` into its correct home. `AGENTS.md` is the canonical filing rule — read it first if unsure.

## Steps

1. **List** every item in `inbox/` (files and folders). If it's empty, say so and stop.
2. **Read** each item enough to classify it.
3. **Classify** using the table in `AGENTS.md`:
   - Has a finish line ("done by when?") → `projects/`
   - Ongoing standard you maintain → `areas/`
   - Your own spark or hunch → `ideas/`
   - A file, export, or something you read elsewhere → `data/`
   - Already done or dead → `archive/`
4. **Move** it. Rename to lowercase kebab-case and descriptive (`q3-budget-notes.md`). Drop the capture-date prefix unless the date matters. Don't duplicate — move, don't copy.
   - New projects: apply the header template from `projects/README.md` (Goal, Deadline, Status, Next action).
   - Archived items: prefix with year-month (`archive/2026-07-slug/`).
5. **Flag, don't guess** — if an item is ambiguous, leave it in `inbox/` and list it for the user to decide.
6. **Delete only true junk** and state exactly what you deleted.

## Finish

- Summarize what moved where, what was flagged, and what was deleted.
- Confirm any destructive moves/deletes before doing them.
- Offer to commit with `git-save` (message listing what changed).
