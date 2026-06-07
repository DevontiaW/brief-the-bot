# Write Like Yourself (Draft-1 Voice)

Get a first draft that sounds like a person, not a press release. This is the starter you edit — not the final you submit. Break the blank page, in your own register.

---

## What This Does

Most "write my essay" prompts hand you AI prose: smooth, padded, hedged, and instantly recognizable. Your professor has read a thousand of those. So has every hiring manager. The tell isn't one word — it's the whole register. Even sentence lengths. Hedge on every claim. "It's important to note that..." A conclusion that restates the intro and says nothing new.

This prompt does the opposite. You feed it a short **voice file** — a set of writing rules that strip out the AI tells — and ask it to draft in *that* voice. You get back a first draft that reads like a sharp human wrote it fast. Short paragraphs. Varied rhythm. Real specifics. A stance, not a shrug.

It is a **starter, not a ghostwriter.** You still rewrite it in your own words, check every fact, and own what you submit. The job here is to kill the blank page and give you something with a pulse to edit.

This idea comes from [Ruben Hassid's "anti-AI writing style" file](https://ruben.substack.com/p/its-not-x-its-y) — save your writing rules once, upload the file, and tell the AI to apply them to everything. The starter ruleset below is an original short version built for student work. Ruben's full file is worth a look if you want the long form.

---

## The Prompt

Two parts. First, save the **voice file** as its own `.md` and upload it to your Project. Second, paste the **draft request** whenever you want a draft in that voice.

### Part 1 — The voice file (save as `my-voice.md`, upload once)

```
# MY WRITING VOICE
Read this before writing anything for me. Apply with judgment. Spirit over letter. A clean, natural sentence always wins over a rule.

## Priority when rules collide
1. Be accurate.
2. Be clear.
3. Be specific.
4. Sound human.
5. Use style only when it makes the sentence better.

## Default voice
- Start with the useful point. No throat-clearing.
- Short paragraphs. 1 to 3 sentences. Vary the rhythm: a short sentence, then a longer one, then a fragment when it lands.
- Use contractions: don't, it's, you're, can't.
- Use "I" and "you" when natural. Write to a person.
- Active voice. Name the actor.
- Be concrete: numbers, names, dates, places, real examples, tradeoffs.
- Take a stance when the evidence supports one. Say "I think" or "probably" when honestly unsure. Never hedge just to dodge a position.
- If the point is made, stop. Short and accurate beats long and padded.

## Cut these AI tells
- No em dashes. Use periods, commas, colons, semicolons, or parentheses.
- No "It's important to note," "In today's world," "delve," "leverage," "robust," "seamless," "navigate the landscape," "tapestry," "testament to."
- No "It's not just X, it's Y" sentence shape.
- No assistant filler: "Certainly," "Great question," "I hope this helps," "Would you like me to."
- No conclusion that just restates the intro. End on something earned.
- Spell digits as digits: 3 reasons, 500 words, 2 sources.
- Bold sparingly. Headers and bullets only when they actually help reading.
```

### Part 2 — The draft request (paste when you want a draft)

```
Using the voice rules in my-voice.md, write a FIRST DRAFT of the following. This is a starter I will edit, not a final.

ASK
[INSERT — e.g., "a 600-word reflection arguing that remote internships taught me more than my classroom courses"]

CONTEXT
- What it's for: [INSERT — e.g., class reflection for MGT-310, application essay, blog post]
- Audience: [INSERT — e.g., my professor, an admissions reader, general]
- Source material I've uploaded / key facts to use: [INSERT — or "none, this is from my own experience below:"]
- My own raw notes / experience to draw from: [INSERT — bullet points are fine]

CONSTRAINTS
1. Apply every rule in my-voice.md.
2. Length: [INSERT — e.g., ~600 words]. Do not pad to hit the count. If the point is made early, stop short.
3. Use only the facts I gave you. Do not invent quotes, stats, or sources. If you need a fact I didn't provide, write [NEED: ...] inline instead of making one up.
4. Open with the actual point, not a windup.
5. At the end, list 3 spots where the draft is weakest and what I should rewrite in my own words first.
```

---

## What You Get Back

A draft that reads like this (excerpt) instead of AI mush:

> Remote internships get a bad rap. People assume you learn less because you're not in the room. My summer at a 12-person logistics startup says otherwise.
>
> In class, the stakes are a grade. On a remote team, I shipped a vendor tracker that three people used the next morning. When it broke, I heard about it in nine minutes. That feedback loop taught me more about clean data than a semester of lectures did.
>
> [NEED: the specific metric on how much time the tracker saved]

Then, below the draft:

> **Weakest spots — rewrite these in your own words first:**
> 1. The opening claim is strong but unproven. Add one concrete detail from your actual summer.
> 2. Paragraph 3 drifts toward generic "I grew as a person." Cut it or make it specific.
> 3. The ending is a placeholder. You need a real closing thought, not a summary.

---

## How To Use It

1. Save Part 1 as `my-voice.md`. Open a Project (Claude/ChatGPT) and upload it once — it persists across the whole conversation.
2. Tweak the voice file to actually sound like *you*. Add words you'd never use. Add a line about your real habits ("I write in second person," "I like one-sentence paragraphs for emphasis").
3. Paste Part 2. Fill in the four CONTEXT blocks honestly. Drop in your raw notes — even messy bullets help a lot.
4. Run.
5. **Start with the "weakest spots" list, not the draft.** That tells you where the AI is bluffing.
6. Rewrite those spots in your own words. Resolve every `[NEED: ...]` with a real fact. Read the whole thing out loud once. If a line sounds like a robot, it is — fix it.
7. The draft is now a scaffold you've made yours. Submit *that*, not the raw output.

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| Still full of em dashes | The model ignored the voice file. Re-paste and bold it: *"ZERO em dashes. This is a hard rule. Replace every one with a period or comma."* |
| Sounds choppy — all short fragments | Over-corrected. Add: *"Vary length for real. Mix in a 25-word sentence that earns its length. Don't write in a staccato pattern either."* |
| Padded to hit the word count | Add: *"Cut 20%. Remove any sentence that doesn't add a fact or move the argument. Shorter is fine."* |
| Invented a stat or quote | Re-run and bold constraint #3. Anything not in your notes must be a `[NEED: ...]` flag, never a guess. |
| Reads generic, could be anyone's essay | Your voice file is too thin. Add 5 specific words you actually use, a sentence on your habits, and a 2-line sample of your real writing for it to match. |
| Conclusion just restates the intro | Add: *"End on a new thought, a stakes-raise, or a concrete image. Never summarize what you just said."* |

---

## Why This Works

The load-bearing move is the **voice file**, not the draft request. Once your rules live in a file you upload, you stop re-typing "please don't sound like AI" into every chat — and you stop getting the watered-down version that produces. The file is the workflow. The request is just the trigger. (Same lesson as the NotebookLM skill-factory idea in [`03-claude-skills/`](../03-claude-skills/): capture the instructions once, reuse forever.)

The second move is the **weakest-spots list**. It forces the AI to mark where it's bluffing instead of hiding it in confident prose. That's where you start editing — and it's what keeps this a draft-1 tool instead of a cheating tool.

Because the honest framing matters: this gets you a *starter*. It does not get you something to submit. A draft in a human voice is still a draft you have to finish.

---

## A Note on Academic Honesty

Using AI to break the blank page and rough out a first draft is a tool, like an outline or a writing-center session. Submitting AI output as your own finished work is not — it violates most academic integrity policies, and "but it sounded human" makes it worse, not better.

This prompt is built for the first use case. The `[NEED: ...]` flags, the weakest-spots list, and the "rewrite in your own words" step all exist to keep you doing the actual thinking. If your school requires AI-use disclosure, disclose it. More schools require it every semester.

---

## Credit

The "save your anti-AI writing rules as a file and apply them to everything" workflow is **Ruben Hassid's** ("How to AI"). The starter ruleset here is an original short version written for this repo. For the long-form file and his full method, see [ruben.substack.com](https://ruben.substack.com/p/its-not-x-its-y).

---

> Pair with [`research-outline.md`](./research-outline.md) — outline your sources first, then draft from the outline in your own voice. Outline, then draft. Never draft blind.
