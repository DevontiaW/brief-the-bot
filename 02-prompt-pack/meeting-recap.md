# Meeting Recap

Turn any meeting transcript (class, team practice, group project, study session) into a clean recap with action items, decisions, and open questions — each tagged with an owner and a deadline.

Pairs with **Granola** (granola.ai), **Otter** (otter.ai), or any voice-to-text tool. Athletes who travel and miss class — this is your single highest-leverage prompt.

---

## What This Does

You record a meeting (Granola does this automatically; Otter has a free tier; Apple Voice Memos + a quick paste also works). You feed the transcript to this prompt. The AI returns a structured recap:

- **Action Items** — who agreed to do what, by when, with a confidence flag if the deadline is unclear
- **Decisions** — what got decided (and what *didn't*, but should have)
- **Open Questions** — what still needs answering, by whom

It also flags anywhere the transcript is fuzzy on ownership ("we should…" with no name) or on timeline ("soon" with no date) — because those are the items that fall through the cracks.

---

## The Prompt

```
You are a meeting recap assistant. You produce structured recaps from raw transcripts. You are precise about ownership and deadlines. You flag ambiguity instead of papering over it.

ASK
Extract action items, decisions, and open questions from the transcript I'm providing.

CONTEXT
- Meeting type: [INSERT — e.g., "MKT501 group project sync", "team practice debrief", "class lecture", "advisor 1:1"]
- Meeting date: [INSERT TODAY'S DATE OR THE MEETING DATE]
- People in the meeting (if known): [INSERT NAMES OR ROLES — e.g., "Devon, Sarah, Mike", or "me + my advisor", or "professor + 30 students"]
- The transcript:
[PASTE TRANSCRIPT HERE — or attach the file Granola/Otter exported]

CONSTRAINTS
1. Output in this exact order:
   PART 1 — TL;DR (3-line summary of what the meeting was actually about)
   PART 2 — DECISIONS
   PART 3 — ACTION ITEMS (table)
   PART 4 — OPEN QUESTIONS
   PART 5 — FLAGS (anything ambiguous I should fix)

2. PART 1 — TL;DR: Three sentences. Plain language. What was the meeting actually about, what got decided, what's the next step.

3. PART 2 — DECISIONS: Bulleted list. Each decision in one sentence. If a decision was discussed but NOT made, write "DEFERRED — [topic]" instead.

4. PART 3 — ACTION ITEMS: Markdown table with columns:
   Owner | Action | Deadline | Confidence (HIGH/MEDIUM/LOW)
   - HIGH = transcript explicitly named who and when
   - MEDIUM = owner clear, deadline implied or unclear
   - LOW = ambiguous owner or deadline (the transcript said "we should" or "soon")

5. PART 4 — OPEN QUESTIONS: Bulleted list. Anything raised in the meeting but not resolved. If a question has an implied owner, name them in parentheses.

6. PART 5 — FLAGS: Bulleted list of anything I should hand-fix:
   - Action items where confidence is LOW
   - Open questions with no owner
   - Decisions deferred without a follow-up trigger
   - Anywhere the transcript was unclear or cut off

7. Do NOT invent action items, decisions, or attendees not in the transcript. If the transcript is silent on something, that's the FLAGS list, not the action list.

8. Use plain English. No filler ("here's your recap!"). Just the structure above.
```

---

## What You Get Back

```
## PART 1 — TL;DR
The MKT501 team met to align on the Acme case analysis. We split the four-segment market analysis across team members and agreed to reconvene Thursday. Mike is still pulling sources for the competitive landscape section.

## PART 2 — DECISIONS
- Use Porter's Five Forces as the analytical frame (not SWOT).
- Final paper length: 8 pages, due Friday.
- Mike will lead the executive summary; Sarah leads the recommendation.
- DEFERRED — pricing analysis depth (need professor's clarification on whether quantitative is required).

## PART 3 — ACTION ITEMS
| Owner  | Action                                  | Deadline       | Confidence |
|--------|-----------------------------------------|----------------|------------|
| Sarah  | Draft segments 1-2 of market analysis   | Wed Apr 30     | HIGH       |
| Mike   | Draft segments 3-4 + executive summary  | Wed Apr 30     | HIGH       |
| Devon  | Source pull from HBR + McKinsey         | Tue Apr 28     | HIGH       |
| All    | Review + sync                           | Thu May 1, 7pm | MEDIUM     |

## PART 4 — OPEN QUESTIONS
- Is quantitative pricing analysis required? (→ Devon: email Dr. Smith)
- Are we citing in APA or Chicago? (no owner)
- Should we include competitor financial deep-dive? (raised by Sarah, no answer)

## PART 5 — FLAGS
- "All — Review + sync" is MEDIUM confidence: Mike said "I'll be at practice that night" but didn't confirm a backup plan
- "Are we citing in APA or Chicago?" has no owner — assign someone before next sync
- Pricing analysis was deferred without a follow-up trigger — set a hard deadline for the email-to-Dr-Smith
```

That's everything you need to leave the meeting and go.

---

## How to Use It

1. Record the meeting:
   - **Granola** (granola.ai) — auto-records every meeting on your laptop, free tier good enough for students
   - **Otter** (otter.ai) — free tier covers ~600 minutes/month
   - **Apple Voice Memos** + paste-as-text — free, manual but works
2. Export the transcript (every tool has an "Export" or "Copy Transcript" button).
3. Open Claude / ChatGPT in a Project (so context persists across multiple meetings if you want a series).
4. Paste the prompt. Fill in the four CONTEXT blocks (meeting type, date, attendees, transcript).
5. Run.
6. **Read PART 5 (Flags) first.** That's your real to-do list — the ambiguity that will bite if not handled.
7. Drop the action items into your task tracker (or use the [`syllabus-to-calendar`](./syllabus-to-calendar.md) prompt to convert them into calendar events).

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| Action items have no owners | Tighten constraint #4: *"Every action item MUST have a named owner from the attendee list. If the transcript says 'we should X', name the most likely owner based on context AND flag confidence as LOW."* |
| Decisions section is empty even though things got decided | Often a transcript-quality issue (the recording missed key audio). Re-run with: *"Re-read the transcript. Decisions can be implicit — if the team agreed to a path forward, that's a decision. List ALL decisions, even small ones."* |
| Output is one giant paragraph | The model ignored structure. Re-run with: *"Output MUST follow the 5-part structure exactly. Use markdown headers. Use a table for action items, not prose."* |
| Recap reads as if AI was AT the meeting | Remind it: *"You weren't there. You only know what's in the transcript. Don't add color or interpretation — just structure."* |
| Confidence flags missing | Add: *"EVERY action item must have a confidence flag. If you skip one, the recap is incomplete."* |

---

## Why This Works

The reason most "meeting summary" prompts fail is the **ambiguity tax.** Real meetings are messy — half the action items have unclear owners, deadlines like "soon," and decisions that get deferred without a trigger. Generic AI summaries paper over this messiness, which is exactly what you DON'T want — you want the messiness surfaced so you can fix it before it becomes a missed deadline.

The two load-bearing constraints are:
1. **Confidence flags** — make uncertainty visible
2. **The FLAGS section** — surface the items most likely to fall through the cracks

Run this after every meeting and you'll never lose a "wait, who was supposed to do X?" again.

---

## Pair It With

- [`syllabus-to-calendar.md`](./syllabus-to-calendar.md) — convert the action item deadlines into calendar events
- [`email-to-professor.md`](./email-to-professor.md) — when an action item is "email Dr. Smith for clarification," that's the next prompt to run

---

> Built by Devontae Williams — the prompt that finally made me OK with missing class for an away game.
