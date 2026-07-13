---
name: writing-docs
description: Conventions for writing and editing the docs that ship with this brain — INSTALL.md, README.md, AGENTS.md, and folder READMEs. Use whenever creating or editing any of these, or when the user asks to refactor, clean up, or improve the docs.
---

# Writing docs

How to write the docs that ship with this brain so they stay clear and don't go stale. Applies to `INSTALL.md`, `README.md`, `AGENTS.md`, and the per-folder `README.md` files.

## Keep it evergreen — no counts that go stale

The biggest trap: baking a count into the prose that a later edit invalidates. It reads fine today and wrong next month.

- **Don't state how many** steps, parts, tasks, options, or items something has — "two steps", "there are three folders", "follow these 5 steps". Add or remove one and the number lies.
- **Don't number what you'll have to renumber.** Prefer descriptive headings (`## Create your repo`) over ordinal ones (`## Step 1`). If order genuinely matters, an ordered list or a numbered agent checklist is fine — but don't *announce* the count in the surrounding sentence.
- **Say what it is, not how many.** "It has a user part and an agent part" — not "It has two parts."
- Same for anything else that drifts: exact file counts, exact folder lists spelled out in prose (link or point instead), version numbers that aren't pinned.

## Write for two readers

These docs are read by both a human and an AI agent. Make the audience of each section obvious, and keep the human-facing parts short — push procedure and detail into the agent-facing parts.

## General

- Lead with what the reader does, not background.
- One canonical source per fact; other docs link to it rather than restating it (`AGENTS.md` is the canonical filing rule).
- Prefer editing an existing doc over adding a new one.
- Keep edits small and reviewable; say what changed.
