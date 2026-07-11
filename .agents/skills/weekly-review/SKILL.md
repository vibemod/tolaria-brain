---
name: weekly-review
description: Run a weekly review of the tolaria-brain — check that the inbox is clear, projects have a valid next action, stale items get archived, and surface what needs attention. Use when the user says "weekly review", "review my brain", "what needs attention", "tidy up", or "how are my projects".
---

# Weekly review

A regular sweep to keep the brain trustworthy. Report findings; make changes only with confirmation.

## Steps

1. **Inbox** — is `inbox/` empty? If not, offer to run `process-inbox`.
2. **Projects** — for each item in `projects/`, check the header (from `projects/README.md`):
   - Missing **Goal**, **Deadline**, **Status**, or **Next action**? List it.
   - **Status: stalled** or past deadline? Flag it and suggest either a next action, a new deadline, or archiving.
   - Finished? Propose moving to `archive/` prefixed `YYYY-MM-`.
3. **Areas** — any area with no recent notes or an unclear standard? Note it. Areas don't get "done", but they can go stale.
4. **Ideas** — surface 3–5 ideas worth revisiting or promoting to a project.
5. **Archive hygiene** — confirm archived items keep their `YYYY-MM-` prefix; nothing active left behind.

## Finish

- Produce a short report: inbox status, projects needing action, stale areas, ideas to revisit.
- Make moves/edits only after the user confirms.
- Offer to commit the result with `git-save`.
