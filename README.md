# Tolaria - Second Brain

A plain-markdown second brain — a single git-tracked folder of notes that both you and an AI agent can read and edit. No app, no lock-in, just files.

## How it works

Everything you capture lands in `inbox/`. Later, you (or the agent) file each item into the right place. The active folders stay small; anything done or stale moves to `archive/`.

## Structure

```text
README.md    → this file
AGENTS.md    → operating rules for any AI agent working in here
CLAUDE.md    → points to AGENTS.md (so Claude picks up the same rules)
SOUL.md      → who I am: values, voice, goals, how I think

inbox/       → capture everything here first, organize later
projects/    → active efforts with an end state
areas/       → ongoing responsibilities, no end date
ideas/       → my own original thinking
data/        → structured files (csv/json) + reference material
archive/     → finished projects & stale ideas

.agents/skills/  → canonical agent skills (one source of truth)
.claude/skills   → symlink → .agents/skills
.codex/skills    → symlink → .agents/skills
.cursor/skills   → symlink → .agents/skills
.opencode/skills → symlink → .agents/skills
```

Each folder has its own `README.md` explaining what belongs in it.

## Skills (works with any agent)

Reusable workflows live once in `.agents/skills/<name>/SKILL.md` and are shared to every tool via symlink, so Claude Code, Codex, Cursor, and OpenCode all see the same skills:

- **process-inbox** — file everything in `inbox/` into the right folder per `AGENTS.md`.
- **weekly-review** — sweep projects/areas/ideas, flag stale items, keep the archive tidy.
- **git-save** — commit a snapshot with an itemized message; push if there's a remote.

To add a skill, create `.agents/skills/<name>/SKILL.md` (lowercase-kebab name matching the folder) — every tool picks it up automatically. OpenCode and Cursor read `.agents/skills/` natively; the symlinks cover Claude (`.claude/skills`) and Codex (`.codex/skills`).

## Filing

The canonical filing rules live in `AGENTS.md` ("Where things go"). Quick version: finishable → `projects/`, maintained forever (health, finances, a role) → `areas/`, your own thinking → `ideas/`, files & things you read → `data/`, unsure → `inbox/`, done → `archive/`.

The classic confusion is projects vs areas: ask "done by when?" — if that question has an answer, it's a project; if being "done" makes no sense, it's an area.

## Using it with an agent

Open this folder in Claude and ask it to process the inbox, find something, or draft from your notes. It reads `AGENTS.md` for the rules and `SOUL.md` for context on you.

## References & further reading

Second-brain method and templates that shaped this structure:

- [Building a Second Brain (PARA method)](https://fortelabs.com/blog/para/) — Tiago Forte's Projects / Areas / Resources / Archive system, the backbone of these folders.
- [obsidian-ai-second-brain](https://github.com/jamesmcroft/obsidian-ai-second-brain) — a starter template for an AI-augmented second brain using CODE/PARA and AI skills.
- [second-brain-template](https://github.com/mcallaway/second-brain-template) — a minimal markdown-file second-brain template.
- [Second Brain Setup with Claude (Karpathy's method)](https://dreamsaicanbuy.com/learn/second-brain-setup) — using a plain-markdown repo as a knowledge base an LLM operates.
- [Markdown files as the digital workplace](https://luhr.co/blog/2024/09/02/markdown-files-as-the-digital-workplace/) — the case for plain markdown over apps.
