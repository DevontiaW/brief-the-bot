# Syllabus → Study Plan

A week-by-week study plan from any class syllabus. Capped at the hours you actually have. Flags the weeks most likely to crush you.

---

## What This Does

You've imported the calendar (see [`syllabus-to-calendar.md`](./syllabus-to-calendar.md)). Now you need a *plan* — what to read when, how many hours per week, where the squeeze weeks are.

This prompt builds that plan from the same syllabus. It respects the time budget *you* set (not what the professor wishes you'd spend) and surfaces the three weeks most likely to wreck you so you can plan ahead.

---

## The Prompt

```
You are a study planner helping a student build a realistic week-by-week study plan from a class syllabus.

ASK
Build a week-by-week study plan from the syllabus I uploaded, covering every week from now through the end of the semester.

CONTEXT
- I am a student. The syllabus is the document attached.
- My total weekly study budget for THIS class is [INSERT YOUR HOURS — e.g., 4 hours per week]. Do not exceed this unless explicitly necessary, and flag any week that does.
- Today's date is [INSERT TODAY'S DATE].
- Treat any reading or assignment listed in the syllabus as work for the week it appears.

CONSTRAINTS
1. Output a single markdown table with columns:
   Week | Dates | Reading focus | Assignments due | Reading hours | Practice hours | Notes
2. One row per week. Reading + Practice hours must total within my weekly budget unless explicitly flagged.
3. After the table, list the THREE weeks most likely to be the hardest, and explain in one sentence why each is hard (overlapping deadlines, dense reading, exam prep, etc.).
4. After that, list any week where my budget is exceeded and what I would need to drop or front-load to make it fit.
5. Do not invent dates or assignments. If the syllabus is ambiguous about a week's content, write "TBD" and add a one-line clarification request below the table.
6. Use plain English. No filler ("here's your plan!"). Just the table and the three follow-on lists.

Verify before you finish: every row's hours sum to within budget OR is explicitly flagged.
```

---

## What You Get Back

A semester table that looks like this (truncated):

| Week | Dates | Reading focus | Assignments due | Reading hrs | Practice hrs | Notes |
|---|---|---|---|---|---|---|
| 1 | Aug 25–29 | Ch. 1: Intro to Marketing | — | 1.5 | 1.0 | Light week, build a habit |
| 2 | Sep 1–5 | Ch. 2: STP | Group formation | 2.0 | 1.5 | Form team early |
| 3 | Sep 8–12 | Ch. 3: 4 Ps | — | 2.0 | 2.0 | Push case prep |
| ... | | | | | | |

Then below:

> **Three hardest weeks:**
> - Week 6 — Mid-term + Quiz 1 review collide
> - Week 11 — Marketing Plan first draft + group case due
> - Week 14 — Final presentation + last reading week
>
> **Budget overruns:**
> - Week 6 — needs ~6 hrs (mid-term). Front-load Ch 5–7 to Week 5 to absorb.

---

## How To Use It

1. Open Claude, ChatGPT, or Gemini in the same Project as your syllabus (so it has the context).
2. Paste the prompt. **Replace `[INSERT YOUR HOURS]` with your real number.** Be honest — 6 hours/week if you have a road trip, not 12 hours/week aspirationally.
3. **Replace `[INSERT TODAY'S DATE]`** with today.
4. Run.
5. Eyeball the three hardest weeks. Block calendar time for them now (use the [calendar prompt](./syllabus-to-calendar.md) to add study sessions as separate events).

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| Plan ignores your hour budget | The constraint isn't tight enough. Re-run with: *"Hard cap: total hours per week must be ≤ N. Flag any week where this can't be met."* |
| AI invents readings not in the syllabus | Add to constraints: *"Use only the readings explicitly listed in the syllabus. If a week has no reading listed, leave the cell blank."* |
| Plan is too generic ("study chapter 1") | Add to ASK: *"Reading focus must reference specific chapter numbers, page ranges, or article titles from the syllabus — not generic descriptions."* |
| Doesn't flag overlapping deadlines | Add to constraints: *"In Notes, flag any week where two or more graded items are due."* |

---

## Why This Works

The most important constraint here is the **hours cap.** Most generic study plans assume infinite student time. This one doesn't. By naming the constraint up front and demanding the AI flag overruns, you get a plan that fits the life you actually have — not the one a syllabus designer assumed you have.

This is the team-lead move applied to school: a real plan accounts for the real constraints. Anything else is a fantasy.

---

> Pair this with [`practice-quiz.md`](./practice-quiz.md) — once the plan is set, generate a quiz for any week you flagged as hard.
