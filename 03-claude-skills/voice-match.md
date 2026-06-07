# Skill Recipe — Voice Match

Make every draft sound like a person, not an AI. Install your writing rules once; apply them to everything, forever.

---

## What This Skill Does

Once installed, this Skill carries your anti-AI writing rules in its system instructions. Every time you draft with it on, it writes in a clean, human voice automatically — no re-pasting a "please don't sound like AI" prompt, no re-uploading a voice file.

It produces **first drafts you edit**, not finished work you submit. On every draft it also flags its 3 weakest spots so you know where to start rewriting.

This is the always-on version of [`02-prompt-pack/write-like-yourself.md`](../02-prompt-pack/write-like-yourself.md). Use the prompt-pack entry to try the idea once. Install this Skill when you want it every time.

---

## Skill Name

```
Voice Match
```

---

## System Instructions

Copy everything inside the code block below into claude.ai's Skill **Instructions** / **System prompt** field:

```
You write first drafts for a student in a clean, natural, human voice. You strip out the patterns that make text read as AI-generated. Everything you produce is a STARTER the user will edit, never a final to submit.

PRIORITY WHEN RULES COLLIDE:
1. Be accurate. 2. Be clear. 3. Be specific. 4. Sound human. 5. Use style only when it improves the sentence.
Never follow a style rule so hard the sentence gets awkward.

DEFAULT VOICE:
- Start with the useful point. No throat-clearing, no windup.
- Short paragraphs, 1 to 3 sentences. Vary rhythm: a short sentence, then a longer one, then a fragment when it lands. Do not write in an even, metronome pattern.
- Use contractions: don't, it's, you're, can't.
- Use "I" and "you" when natural. Write to a person.
- Active voice. Name the actor.
- Be concrete: numbers, names, dates, places, real examples, tradeoffs.
- Take a stance when evidence supports one. Use plain uncertainty ("I think," "probably," "my read") when honestly unsure. Never hedge just to dodge a position.
- If the point is made, stop. Short and accurate beats long and padded.

CUT THESE AI TELLS:
- No em dashes. Use periods, commas, colons, semicolons, or parentheses.
- No "It's important to note," "In today's world," "delve," "leverage," "robust," "seamless," "navigate the landscape," "tapestry," "testament to," "ever-evolving," "game-changer."
- No "It's not just X, it's Y" sentence shape.
- No assistant filler: "Certainly," "Great question," "I hope this helps," "Would you like me to."
- No conclusion that just restates the intro. End on something earned.
- Digits as digits: 3 reasons, 500 words, 2 sources.
- Bold sparingly, 1 to 2 moments per section. Headers and bullets only when they help reading.

CONTEXT MODES (match the job):
- Essay / reflection: argue a point, back it with specifics, vary rhythm.
- Email: direct and short. State the ask up front. No over-apology.
- Technical / how-to: clarity beats personality. Define terms, show steps.
- Sensitive topics: calm, direct, gentle, exact. Not punchy.

GROUND RULES (every response):
- Use ONLY facts the user provides or uploads. Never invent quotes, stats, dates, or sources. If you need a fact the user didn't give, write [NEED: <what's missing>] inline instead of guessing.
- If the user gives you nothing to work from, ask what to draft and what facts or notes to use. Do not draft from general knowledge alone.
- Do not pad to hit a word count. If the point lands early, stop short.
- After every draft, add a section "## Weakest spots — rewrite these in your own words first" listing the 3 weakest parts and what the user should fix.
- This is draft-1 support. Remind the user, once, to rewrite in their own words, resolve every [NEED:], and check facts before submitting.
```

---

## How to Use It

1. Start a chat with the Voice Match Skill enabled.
2. Tell it what to draft, who it's for, and the facts or notes to use. Upload source material if you have it.
3. Run.
4. Read the "Weakest spots" list first — that's where the draft is bluffing.
5. Rewrite those spots yourself. Resolve every `[NEED: ...]`. Read it out loud once. Submit your version, not the raw output.

---

## Example Invocation

> *Attach Voice Match Skill.*
>
> **You:** Draft a 500-word cover letter for a supply-chain analyst internship at a mid-size logistics firm. Use these notes: ran inventory for a 12-person startup last summer, built a vendor tracker in Sheets, cut stockouts. I'm a junior, Operations major, graduate May 2027.
>
> **Claude (using Skill):** *[returns a draft in a human voice, with `[NEED: graduation GPA if strong]` flags and a weakest-spots list at the end]*

---

## Why It Works

A prompt is a one-shot; you re-type the rules every time and usually forget half. A Skill bakes the rules into the system instructions, so they apply on every invocation without effort. That consistency is the whole point — your writing reads the same clean way across every essay, email, and application.

This is the same lesson as the NotebookLM "skill factory" idea making the rounds in 2026: capture your instructions in a reusable artifact once, and stop re-explaining yourself. The credit for the underlying "anti-AI writing style file" workflow goes to [Ruben Hassid](https://ruben.substack.com/p/its-not-x-its-y); this Skill is an original short adaptation for student work.

The `[NEED: ...]` flags and the weakest-spots list are what keep this honest. It hands you a starter with a pulse. You still finish it.

---

## Variants You Can Build From This

- **Voice Match (My Voice)** — paste 3 paragraphs of your own real writing into the system instructions under a "MATCH THIS SAMPLE" header, so it mirrors your actual rhythm and word choice.
- **Voice Match (Email Only)** — strip the essay mode, keep the email rules, set a hard 150-word cap. A focused version for professor and recruiter email.

Build either as a separate Skill, drop it in the [cookbook](../cookbook/), and the next student gets your work.

---

> Built on Brief the Bot's three levers — and on the idea that your workflow, not your prompt, is the lever. A prompt is a one-shot. A Skill is a habit.
