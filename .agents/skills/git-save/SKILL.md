---
name: git-save
description: Snapshot the tolaria-brain with git — stage changes, write a clear commit message listing what moved/changed/was deleted, commit, and push if a remote exists. Use when the user says "save", "commit", "snapshot", "back this up", "git save", or after processing the inbox or editing notes.
---

# git-save

Commit the current state of the brain. Git history is the audit log, so the message must say what actually changed.

## Steps

1. **Check state** — run `git status --short` and `git diff --stat` to see what changed. If nothing changed, say so and stop.
2. **Review** — glance at the changes so the message is accurate. Group them: moved, edited, added, deleted.
3. **Stage** — `git add -A` (include moves and deletions). Confirm before staging deletions of anything that isn't clearly junk.
4. **Commit** with a message that lists what changed, e.g.:

   ```
   Process inbox: file 3 notes, archive outbreak report

   - moved inbox/well-map.md → data/well-map.md
   - moved inbox/2026-07-10-10k-plan.md → projects/run-a-10k.md
   - archived projects/outbreak-report → archive/2026-07-outbreak-report/
   - deleted inbox/blank.md (empty)
   ```

   Use a concise imperative subject line; put the itemized changes in the body.
5. **Push** — if `git remote` shows a remote, push the current branch. If not, skip and mention there's no remote.

## Rules

- Never force-push. Never rewrite existing history.
- Don't commit secrets or anything identifying about individuals (see `AGENTS.md` → Don't).
- One logical change per commit where practical.
- Report the commit hash and subject when done.
