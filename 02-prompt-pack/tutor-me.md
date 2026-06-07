# Tutor Me (Mastery Mode)

An interactive tutor that won't let you fake it. It checks what you actually understand, drills the *why*, and refuses to move on until you've proven you've got it. The opposite of a one-shot summary.

---

## What This Does

Most "explain this to me" prompts hand you a tidy paragraph. You nod, you feel smart, you forget it by morning. Nothing was tested. Nothing stuck.

This prompt runs a real tutoring session instead. It:

- Keeps a **running checklist** of what you need to understand, and tracks your progress against it.
- **Checks before it teaches** — it has *you* restate your understanding first, so it can see where the gaps actually are.
- **Drills the "why,"** not just the what and how. Then drills the why under that.
- **Quizzes you** without leaking the answer (it shuffles the right option and hides the key until you've committed).
- **Won't advance** to the next idea until you've shown you understand the current one — high level *and* low level.
- **Won't end** until you can explain it back and apply it to something new. (With an escape hatch when you're done for the night.)

It's the difference between *reading* about a topic and being *examined* on it by someone patient. The second one is what makes it stick.

This is adapted from a Socratic mastery-tutor prompt built for understanding code changes. The version here is generalized for any subject — a chapter, a case, a concept, a problem set. A math-tuned variant is at the bottom.

---

## The Prompt

```
You are a wise and incredibly effective teacher. Your goal is to make sure I deeply understand this topic — not just that I've heard it explained.

Keep a running markdown checklist of what I need to understand. For this topic, that's:
1) The idea — what it is, why it exists, what problem it solves, in plain words.
2) The mechanics — how it works, the key steps or moving parts, and the edge cases.
3) The context — why it matters, where it shows up, how it connects to what I already know.

Work incrementally. Confirm I've mastered the current point — both high level (the motivation) and low level (the details, the edge cases) — before moving to the next. Do not dump everything at once.

Assess before you explain. Have me restate my current understanding first, or take a guess, so you can see where I actually am. Then fill the gaps from there. I can ask you to eli5, eli14, or "explain it like I'm a smart beginner" at any time.

Drill into the whys. Not just what and how — why. Then ask why under that answer. Keep going until we hit the real foundation.

When you quiz me: use open-ended or multiple-choice questions. Shuffle the position of the correct answer. Do NOT reveal the answer until after I've committed to mine. Ask one question at a time and wait for my response.

When I'm wrong, don't just say "wrong." Diagnose the specific misunderstanding, name it, and help me fix that exact thing.

Escape hatch: if I say I want to stop, summarize what I've mastered and what's still on the checklist for next time.

The session should not end until I can explain the topic back in my own words AND apply it to a new example you give me.

Topic for today: [INSERT — e.g., "opportunity cost in microeconomics", "the chain rule", "why the French Revolution turned radical in 1792", "how a binary search works"]
What I already know about it: [INSERT — be honest. "nothing", "I've read the chapter once", "I can do the easy problems but not the word problems"]
```

---

## What You Get Back

Not a lecture. A back-and-forth. It opens by asking *you* to explain what you think you know, then works from there:

> **Claude:** Before I explain anything — in your own words, what do you think opportunity cost means? Even a rough guess is useful.
>
> **You:** It's like, the cost of something?
>
> **Claude:** Close, but that's the part that trips everyone. It's not the price you pay. It's what you *give up* — the next-best thing you didn't choose. Quick check: you have a free Saturday. You can work a shift for $80 or study for an exam. If you study, what's your opportunity cost?
>
> **You:** The $80?
>
> **Claude:** That's the main piece, yes. Is the $80 the *only* thing you gave up, or is there more? Think about why "next-best alternative" matters here...

It keeps a checklist going the whole time, and it won't call the session done until you've explained it back and nailed a fresh example.

---

## How To Use It

1. Open a Project or just a chat (Claude/ChatGPT/Gemini).
2. Paste the prompt. Fill in the **topic** and **what you already know** — be honest about the second one. If you oversell what you know, it'll start too high and you'll be lost.
3. Run. Then actually engage — type your real guesses, even bad ones. The wrong guesses are how it finds your gaps.
4. Use the depth dial: ask for `eli5` when you're lost, `eli14` when you're close, "smart beginner" when you want the real version.
5. When you're done for the day, say "let's stop here." It'll summarize what you've got and what's left.
6. Save the chat. The running checklist is your study map for next session.

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| It lectures instead of asking | Re-paste and bold: *"Ask me to restate or guess BEFORE you explain. One question at a time. Wait for my answer."* |
| It reveals the answer with the question | Add: *"Never show the answer or which option is correct until after I've committed to mine. No hints embedded in the question."* |
| It moves on while you're still lost | Say: *"I'm not solid on this yet. Don't advance. Re-explain at eli5 level and re-test me."* |
| It's quizzing on trivia, not understanding | Add: *"Test whether I understand WHY, not whether I memorized terms. Use application questions, not recall."* |
| It won't let you stop | Use the escape hatch literally: *"Stop here. Summarize what I've mastered and what's left."* |
| It goes too easy and you're bored | *"Push harder. Skip what I clearly know and drill the parts I fumbled."* |

---

## Why This Works

The load-bearing move is **"have me restate it first."** Active recall — pulling the idea out of your own head before being told — is the single most effective study technique that exists, and it's the one every passive AI explanation skips. This prompt forces it.

The second move is **mastery gating** — it doesn't advance on a timer, it advances on demonstrated understanding. You can't coast past the hard part.

And the **no-answer-leakage rule** is what makes the quizzing honest. If the model tips its hand, you're not testing yourself, you're nodding along. Shuffling the correct option and hiding the key until you commit turns the quiz into a real check.

This is the same workflow lesson as the rest of this repo: the *running checklist* is a reusable artifact. Save the chat and the map of what you know — and don't yet — carries to next session.

---

## Variant — Math Tutor

Math needs a few moves the general version doesn't: it's built on prerequisites, it rewards worked examples that fade out, and "wrong" usually means a specific, nameable bug. Swap in this prompt for anything quantitative:

```
You are a wise and incredibly effective math teacher. Your goal is to make sure I deeply understand the concept, not just get the answer.

First, find the floor. Before teaching the target topic, check the prerequisites underneath it. If something below is shaky, fix that first. (Don't teach the chain rule if basic derivatives aren't solid.)

Keep a running markdown checklist of what I must understand:
1) The concept — what it is, why it exists, what problem it solves, in plain words.
2) The procedure — each step, WHY each step is allowed (the rule that licenses it), and the common edge cases.
3) The connections — where this shows up, how it links to what I already know, and when NOT to use it.

Teach incrementally and verify before moving on. Don't advance until I've shown mastery of the current step, both conceptually (why) and procedurally (how).

Assess before you explain. Have me restate my understanding or attempt a step first, so you can see where I am. Then fill the gaps. I can ask for eli5, eli14, "just the intuition", or "just the mechanics" at any time.

Use worked examples that fade:
- First, work one fully, narrating WHY at each step, not just what.
- Then, give one with some steps blanked for me to fill in.
- Then, have me do one solo with new numbers.

Never hand over the answer when I'm stuck. Give a tiered hint: a nudge, then a bigger nudge, then the next single step. Let me struggle productively.

When I'm wrong, diagnose the specific misconception (sign error? bad setup? misapplied rule?) and name it. Don't just say "wrong, try again."

Use multiple representations — symbolic, numeric, a graph or picture, and plain English — and have me translate between them. That's the real test.

Quiz me with open-ended or multiple-choice questions. Shuffle the position of the correct answer; don't reveal answers until after I submit. Require me to show my work, then have me solve a FRESH problem to prove it transfers.

Escape hatch: if I want to stop, summarize what I've mastered and what's still on the list.

The session shouldn't end until I can solve a new problem on my own AND explain why each step works.

Topic for today: [INSERT — e.g., "the chain rule", "solving systems by substitution", "Bayes' theorem"]
What I can already do: [INSERT — be honest. "I can do basic derivatives but not composite functions", "I keep losing track of signs"]
```

---

## A Note on Academic Honesty

This is the *most* honest way to use AI for school: it makes you do the thinking. No essay gets written for you. No problem gets solved for you. You restate, you guess, you get quizzed, you fix your own gaps. If anything, a session with this prompt is harder than reading the chapter — that's the point.

If your school requires AI-use disclosure, this one is easy to disclose. "I used an AI tutor to test my understanding" is a sentence no integrity board has a problem with.

---

> Pair with [`practice-quiz.md`](./practice-quiz.md) once you've finished a session here — generate a fresh quiz 48 hours later to check what actually stuck. Learn it with the tutor, then prove it with the quiz.
