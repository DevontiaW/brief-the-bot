# Claude Skills (Recipes)

A "Skill" in claude.ai is a reusable, named prompt with system instructions baked in. Once installed, you invoke it like a command — no re-typing the prompt every time.

This folder contains two **Skill recipes** — markdown files with the exact text you paste into claude.ai's Skill creator. They install in about 60 seconds each.

---

## Why Recipes Instead of JSON Files?

claude.ai's Skill format isn't a stable public JSON-export-and-share schema yet (as of 2026). Skills are created in the claude.ai UI. So instead of shipping JSON that might break next month, this repo ships the *recipe* — the components every Skill needs:

1. **Skill name** — what you'll call it
2. **System instructions** — what the Skill always does, no matter the user input
3. **Default behaviors** — formatting, tone, what to flag, what to refuse
4. **Example invocation** — how a student would call the Skill

Reading a recipe also teaches you what a Skill *is.* By the time you've installed two, you'll know enough to build your own.

---

## How to Install a Skill (Once)

1. Open [claude.ai](https://claude.ai) and sign in.
2. In the left sidebar, click **Skills** (or look for the "Build a Skill" / "Create new Skill" button — UI changes occasionally).
3. Click **Create new Skill** (or equivalent).
4. Give it a name — match the recipe's title (e.g., `Study Guide Builder`).
5. In the **Instructions** / **System prompt** field, paste everything from the recipe's "System Instructions" code block.
6. (Optional) Add a description if the UI asks.
7. Save.

The Skill now appears in your Skills list. To use it: open a chat, attach the Skill (look for a "Use Skill" button or @-mention pattern depending on UI version), and run as you normally would.

---

## What's Here

| Recipe | What it does |
|---|---|
| [`study-guide-builder.md`](./study-guide-builder.md) | Turn any chapter, lecture, or reading into a structured study guide with summary, key concepts, applications, common traps, and self-check questions. |
| [`calendar-invite-maker.md`](./calendar-invite-maker.md) | Turn any list of deadlines into a clean .ics calendar file you can import into Apple Cal, Google Cal, or Outlook. |

Both recipes pull all three levers of the discipline. Read them like prompts — they are.

---

## Building Your Own Skill

Once you've installed both of these, build one of your own. The shortest path:

1. Take a prompt from [`02-prompt-pack/`](../02-prompt-pack/) that you've used 3+ times.
2. Strip out the per-use parts (your specific syllabus, your specific résumé) — leave only the persistent rules.
3. Paste those rules into a new Skill's System Instructions.
4. Now whenever you start a chat with that Skill, the rules are already loaded — you just provide the per-use input.

When you've built one that works, **submit it to the [cookbook](../cookbook/)** as a Skill recipe so the next student can install it too.

---

> A prompt is a one-shot. A Skill is a habit.
