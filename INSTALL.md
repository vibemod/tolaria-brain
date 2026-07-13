# INSTALL.md

Setup guide for a new **tolaria-brain** second brain. Written to be run by an AI agent (Claude, Codex, Cursor, Gemini, OpenCode) — hand it this file and it can walk the whole thing end to end. A human can follow it too.

> **Agent:** work through the steps in order. Stop and confirm with the user at each **checkpoint**. Never invent facts about the user — ask, or leave a blank and flag it.

---

## 1. Get the repo

### Option A: Start from template

[Create a new repo from this template](https://github.com/new?template_owner=vibemod&visibility=private&template_name=tolaria-brain&name=second-brain&description=My%20Personal%20Second%20Brain), then clone the repo it creates:

```bash
git clone git@github.com:<your-username>/second-brain.git
cd second-brain
```

### Option B: Start yourself

Clone the template repo directly, then point `origin` at your own repo so you're not tracking the template:

```bash
git clone git@github.com:vibemod/tolaria-brain.git
cd tolaria-brain
git remote set-url origin <your-repo-url>
```

HTTPS instead of SSH:

```bash
git clone https://github.com/vibemod/tolaria-brain.git
cd tolaria-brain
git remote set-url origin <your-repo-url>
```

**Checkpoint:** confirm you're in the repo root — `ls` should show `AGENTS.md`, `SOUL.md`, `README.md`, and the numbered folders (`01-inbox/` … `60-archive/`).

---

## 2. Read the rules, then set up `SOUL.md`

Read `AGENTS.md` (how the agent works) and `SOUL.md` (who the user is). The shipped `SOUL.md` is a **demo persona ("John Snow", epidemiologist)** — it must be replaced with the real user before the brain is useful.

Interview the user and rewrite `SOUL.md` in their own words. Keep the existing section headings; fill each from their answers:

- **Who I am** — role, field, where based, why they do it.
- **What I value** — the principles they actually hold.
- **How I think** — their reasoning style.
- **My voice** — how they write; used whenever the agent drafts as them.
- **Current goals** — concrete, with absolute dates (`2026-08-31`, never "next month").
- **Long-term direction** — where they're headed over years.
- **My daily rhythm** — when they capture and when they process.
- **Apps & services I use** — their real tools.
- **Don't** — hard lines the agent must never cross.

**Checkpoint:** read the rewritten `SOUL.md` back to the user and get a yes before moving on. This file steers everything downstream.

---

## 3. Clear the demo content

The template ships with example notes. Remove them so the brain starts clean, but **keep every folder's `README.md`** — those document each folder's purpose.

```bash
rm 02-projects/neighborhood-outbreak-mapping-report.md
rm 02-projects/case-line-list-template.md
```

If the user wants either as a starting template, keep it and rename instead.

**Checkpoint:** confirm with the user before deleting. List what will go; delete only after a yes.

---

## 4. First commit

```bash
git add -A
git commit -m "Set up brain: personalize SOUL.md, clear demo notes"
git push        # only if origin points at your own repo
```

---

## 5. First run

Open the folder in your agent and try:

- "Read `SOUL.md` and `AGENTS.md`, then tell me back who I am and how you'll work." — confirms context loaded.
- Drop a note in `01-inbox/` and say **"process the inbox"** — runs the `process-inbox` skill and files it per `AGENTS.md`.

**Done.** Day to day: capture into `01-inbox/`, process at your own rhythm, commit after each session. `AGENTS.md` is the canonical filing rule; `README.md` explains the structure.
