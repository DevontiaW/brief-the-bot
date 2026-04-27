# Brief the Bot
### Workflow Discipline for AI

Most people open ChatGPT and start typing. That's where the trouble starts.

This is the repo from the talk *"Stop Prompting. Start Orchestrating."* — built for students who don't have time to read a 200-page book on prompt engineering, but who do have a paper due Sunday and a flight Friday morning. It's the same workflow I use as a Deloitte consultant and an MBA student. The only difference is now it fits on your phone.

**The whole bet of this repo:** your prompt isn't the lever. Your *workflow* is. Get the workflow right and a free AI account will out-perform a $200/month plan run badly.

---

## Pick Your Path

| If you have… | Start with |
|---|---|
| **10 minutes** | [The Levers](./01-the-levers/) → [Syllabus → Calendar](./02-prompt-pack/syllabus-to-calendar.md). One prompt, your week is on your phone. |
| **1 hour** | All of the above + [the rest of the prompt pack](./02-prompt-pack/) (study plan, practice quiz, résumé tailor, email-to-professor, research outline). |
| **1 weekend** | All of the above + [install both Skill recipes](./03-claude-skills/) and submit your first prompt to the [cookbook](./cookbook/). |

If you're the kind of person who reads every footnote — start with the [reading list](./reading-list.md). It's where the discipline came from.

---

## The Only Framework You Need

You don't need to memorize CRAFT, RACE, CO-STAR, or the next acronym someone's going to launch a course on. You need three muscles.

**ASK** — Be specific. Action verbs. Specific scope.
- *Weak:* "help me with my paper."
- *Strong:* "outline a five-paragraph argument for my thesis using the three sources I uploaded."

**CONTEXT** — Set the scene. Brief the AI like a friend who skipped the lecture. Upload the syllabus. Paste the rubric. Name the class. AI doesn't know what you're working on until you tell it.

**CONSTRAINTS** — Shape the output. Table format. Three columns. Under 500 words. Ranked by effort vs impact. Without constraints, you're King Midas — you get exactly what you asked for, which is never what you wanted.

That's it. Every "framework" you've seen is repackaging these three. Run the levers, change the world.

---

## What's in This Repo

```
brief-the-bot/
├── 01-the-levers/              ← The framework, with worked examples
├── 02-prompt-pack/             ← Copy-paste prompts for real student work
│   ├── syllabus-to-calendar.md   ← Live demo from the talk
│   ├── study-plan.md
│   ├── practice-quiz.md
│   ├── resume-tailor.md
│   ├── email-to-professor.md
│   └── research-outline.md
├── 03-claude-skills/           ← Installable Skill recipes for claude.ai
├── 04-agent-sdk-stretch/       ← For the curious builders (drops May 2026)
├── cookbook/                   ← Your wins. PR your best prompt.
├── examples/                   ← Sample outputs so you know it works
├── glossary.md                 ← Friction curve, fluency trap, orchestrator
└── reading-list.md             ← The books that built the discipline
```

---

## How To Use It (The 60-Second Version)

1. Open [claude.ai](https://claude.ai) (free account is fine), [chatgpt.com](https://chatgpt.com), or [gemini.google.com](https://gemini.google.com). The levers work in any of them.
2. Open a **Project** (Claude/ChatGPT) or a **Gem** (Gemini). Projects let you upload context once and reuse it.
3. Pick a prompt from [`02-prompt-pack`](./02-prompt-pack/). Copy it. Paste it. Upload your file (syllabus, résumé, whatever the prompt asks for).
4. Read the output. Spot-check three things — a date, a number, a name. If those are right, the rest usually is. If they're not, run the prompt again with sharper context.
5. Save what works. PR your wins to [`cookbook/`](./cookbook/) so the next student doesn't start from scratch.

---

## When You're Ready for More

This repo is the entry point. If it clicks, here's where to go next:

- **[`30-days-of-ai-strategy`](https://github.com/DevontiaW/30-days-of-ai-strategy)** — A 30-day learning series for the same discipline applied to business decisions. Where the levers meet the C-suite.
- **[`ai-strategy-field-guide`](https://github.com/DevontiaW/ai-strategy-field-guide)** — The full vendor-neutral playbook. Governance, ROI, evaluation, deployment. For when you stop being a student and start running the program.

---

## A Note on the Tools

The prompts in this repo work in Claude, ChatGPT, and Gemini. I built and tested them in Claude because that's where I work day-to-day. The discipline is portable; the tool is not the point.

If a prompt doesn't work for you on the first try, that's the discipline working. Sharpen the ASK. Add the CONTEXT. Tighten the CONSTRAINTS. Run it again.

---

## Credits + Connect

Built by **Devontae Williams** — Senior Strategy Consultant at Deloitte, MBA candidate at Rollins College's Crummer Graduate School of Business, U.S. Army veteran (combat engineer / Sapper), founder of [Textstone Labs](https://textstonelabs.com).

Find me on [LinkedIn](https://www.linkedin.com/in/devontaewilliams/) if you build something with this. Especially if it works.

---

> *"The best AI users don't have the best prompts. They have the best discipline."*

**Stop prompting. Start orchestrating.** You're a team lead now. Go build something.
