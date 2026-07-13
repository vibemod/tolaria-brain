---
name: gtd
description: Run a Getting Things Done (GTD) clarify pass over the tolaria-brain — take each capture in 01-inbox/ and decide "is it actionable?", then define the next action, defer it to a project, delegate it, or drop it into reference/someday. Use when the user says "gtd", "clarify my inbox", "what's my next action", "process with gtd", or "what should I do next".
---

# GTD clarify pass

Apply David Allen's *Getting Things Done* workflow to the brain. Where `inbox` just files things, this pass forces the actionability question and pins down a concrete **next action** for anything that needs one. `AGENTS.md` is the canonical filing rule.

## The core question

For each item, ask: **is it actionable?**

**No** → route it, don't keep it in the inbox:
- Useful reference or a file → `50-data/`
- A spark or maybe-someday → `04-ideas/` (note it as "someday/maybe")
- Done or dead → `60-archive/`, or delete true junk (say what you deleted)

**Yes** → decide the next physical action:
- **< 2 minutes** → do it now if you can (or tell the user it's a quick win), then file/close it.
- **Multi-step outcome** → it's a project. Move to `02-projects/` using the header template in `02-projects/README.md`, and make sure the **Next action** field is a concrete verb-first step ("email Jane the map", not "outbreak stuff").
- **Belongs to someone else** → delegate. Note who and what you're waiting for, and link the person in `05-people/`.
- **Single deferred action** → keep it as a next action with, where relevant, a date (absolute, `2026-07-20`).

## Steps

1. **List** every item in `01-inbox/`. If empty, say the inbox is clear and offer a review instead.
2. **Clarify** each item with the question above — one at a time.
3. **Organize** — move it to its destination, renamed lowercase-kebab and descriptive. Every project must end this pass with a valid next action.
4. **Flag, don't guess** — if actionability is genuinely unclear, leave it in `01-inbox/` and list it for the user.
5. **Confirm** destructive moves or deletes before doing them.

## Finish

- Report: what became a project (with its next action), what was delegated/deferred, what went to reference or someday, what was deleted.
- Surface the **next actions** as a short list so the user knows what to actually do next.
- Offer to commit with the `git` skill.
