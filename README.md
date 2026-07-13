# Second Brain (Tolaria)

A plain-markdown second brain — a single git-tracked folder of notes that both you and an AI agent can read and edit. No app, no lock-in, just files.

## How it works

Everything you capture lands in `01-inbox/`. Later, you (or the agent) file each item into the right place. The active folders stay small; anything done or stale moves to `60-archive/`.

## Structure

At the root: `AGENTS.md` (how the agent should work) and `SOUL.md` (who I am). The notes live in numbered folders, each with its own `README.md`. The canonical filing rules are in `AGENTS.md` ("Where things go"); quick version:

| Folder | What goes in it | Test |
|---|---|---|
| `01-inbox/` | Unprocessed captures — notes, links, half-thoughts | Default landing spot; unsure → here |
| `02-projects/` | Active efforts with an end state | Has a finish line ("done by when?" has an answer) |
| `03-areas/` | Ongoing responsibilities, no end date | Never ends (health, finances, a role) |
| `04-ideas/` | My own original thinking | My own spark |
| `05-people/` | Notes on people — colleagues, contacts, one file each | It's about a person |
| `50-data/` | Structured files (csv/json) + reference material | A file, or something I read |
| `60-archive/` | Finished projects & stale ideas | Done or abandoned |

The classic confusion is projects vs areas: ask "done by when?" — if that question has an answer, it's a project; if being "done" makes no sense, it's an area.

## AI / Agent

Open this folder in Claude Desktop or Codex and ask it to process the inbox, find something, or draft from your notes. It reads `AGENTS.md` for the rules and `SOUL.md` for context on you.

### Skills (works with any agent)

Reusable workflows live once in `.agents/skills/<name>/SKILL.md` and are shared to every tool via symlink, so Claude Code, Codex, Cursor, and OpenCode all see the same skills:

- **inbox** — file everything in `01-inbox/` into the right folder per `AGENTS.md`.
- **gtd** — GTD clarify pass: is each capture actionable? Pin down the next action, defer, delegate, or drop it.
- **grilling** — get interviewed one question at a time to stress-test a plan before you build it ([source](https://github.com/mattpocock/skills)).
- **grill-me** — user-invoked version of the grilling interview; type it when you want to be grilled on a plan or design.
- **research** — spin up a background agent to investigate a question against primary sources and save cited findings as markdown.
- **weekly-review** — sweep projects, areas, and ideas; flag stale items, keep the archive tidy.
- **git** — commit a snapshot with an itemized message; push if there's a remote.

To add a skill, create `.agents/skills/<name>/SKILL.md` (lowercase-kebab name matching the folder) — every tool picks it up automatically. OpenCode and Cursor read `.agents/skills/` natively; the symlinks cover Claude (`.claude/skills`) and Codex (`.codex/skills`).

## References

Second-brain method and templates that shaped this structure:

- [Building a Second Brain (PARA method)](https://fortelabs.com/blog/para/) — Tiago Forte's Projects / Areas / Resources / Archive system, the backbone of these folders.
- [obsidian-ai-second-brain](https://github.com/jamesmcroft/obsidian-ai-second-brain) — a starter template for an AI-augmented second brain using CODE/PARA and AI skills.
- [second-brain-template](https://github.com/mcallaway/second-brain-template) — a minimal markdown-file second-brain template.
- [Second Brain Setup with Claude (Karpathy's method)](https://dreamsaicanbuy.com/learn/second-brain-setup) — using a plain-markdown repo as a knowledge base an LLM operates.
- [Markdown files as the digital workplace](https://luhr.co/blog/2024/09/02/markdown-files-as-the-digital-workplace/) — the case for plain markdown over apps.
