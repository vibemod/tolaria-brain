# INSTALL.md

Setup guide for a new **tolaria-brain** second brain.

It has two parts:

- **[User part](#user-part)** — what you do by hand. Takes a minute.
- **[Agent part](#agent-part)** — instructions your AI agent reads and runs for you. You don't need to read it.

---

## User part

### Create your repo

[**Create your repo from the template**](https://github.com/new?template_owner=vibemod&visibility=private&template_name=tolaria-brain&name=second-brain&description=My%20Personal%20Second%20Brain) — click the link, then **Create repository**. This copies tolaria-brain into your own GitHub account (private by default).

### Hand it to your agent

Open your project folder in Claude Code, Codex, Cursor, Gemini, or OpenCode and paste this prompt. Swap in your repo's clone URL (from the green **Code** button on your new repo):

```
I've created my second brain from the Tolaria template.

Then read the INSTALL.md agent part and walk me through setup —
ask me the questions, give me choices, and don't invent anything about me.

Clone it from: <paste your clone URL here>
```

That's it. Your agent takes it from here — it will interview you, personalize the brain, and confirm each step with you before doing anything.

Clone it from: <paste your clone URL here>
---

## Agent part

> **Agent:** you are setting up this user's second brain. Work through the steps in order. Stop at each **checkpoint** and get an explicit yes before continuing. Never invent facts about the user — ask, or leave a blank and flag it. When a step has choices, present them and let the user pick.

### 1. Clone and enter the repo

Clone the URL the user gave you and `cd` into it:

```bash
git clone <the-clone-url-the-user-gave-you>
cd <repo-folder>
```

**Checkpoint:** confirm you're in the repo root — `ls` should show `AGENTS.md`, `SOUL.md`, `README.md`, and the numbered folders (`01-inbox/` … `60-archive/`). If not, stop and ask the user for the right URL.

### 2. Read the rules

Read `AGENTS.md` (how you operate in this brain) and `SOUL.md` (who the user is). The shipped `SOUL.md` is a **demo persona ("John Snow", epidemiologist)** — you'll replace it in the next step.

### 3. Interview the user, then rewrite `SOUL.md`

Interview the user and rewrite `SOUL.md` in their own words. Ask about each section rather than filling it in yourself. Keep the existing section headings; fill each from their answers:

- **Who I am** — role, field, where based, why they do it.
- **What I value** — the principles they actually hold.
- **How I think** — their reasoning style.
- **My voice** — how they write; used whenever you draft as them.
- **Current goals** — concrete, with absolute dates (`2026-08-31`, never "next month").
- **Long-term direction** — where they're headed over years.
- **My daily rhythm** — when they capture and when they process.
- **Apps & services I use** — their real tools.
- **Don't** — hard lines you must never cross.

Ask a few questions at a time, not all at once. If the user is unsure about a section, leave it short and note it can grow later.

**Checkpoint:** read the rewritten `SOUL.md` back to the user and get a yes before moving on. This file steers everything downstream.

### 4. Clear the demo content

The template ships with example notes. Remove them so the brain starts clean, but **keep every folder's `README.md`** — those document each folder's purpose.

The demo notes to remove:

```bash
rm 02-projects/neighborhood-outbreak-mapping-report.md
rm 02-projects/case-line-list-template.md
```

**Give the user a choice:** for each demo file, offer to (a) delete it, or (b) keep it as a starting template and rename it to something of theirs. List what will go before touching anything.

**Checkpoint:** confirm with the user before deleting. Delete only after a yes, then report what you removed.

### 5. First commit

```bash
git add -A
git commit -m "Set up brain: personalize SOUL.md, clear demo notes"
git push
```

**Checkpoint:** confirm the push succeeds and points at the user's own repo (not the template).

### 6. First run

Show the user how the brain works day to day:

- Ask them to say **"Read `SOUL.md` and `AGENTS.md`, then tell me back who I am and how you'll work."** — confirms context loaded correctly.
- Have them drop a note in `01-inbox/` and say **"process the inbox"** — runs the `inbox` skill and files it per `AGENTS.md`.

**Done.** Tell the user the rhythm: capture into `01-inbox/`, process at their own pace, commit after each session. `AGENTS.md` is the canonical filing rule; `README.md` explains the structure.
