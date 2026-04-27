# Practice Quiz Generator

A self-test from any chapter, lecture, or reading set. Multiple choice + short answer. Answer key. The "trap" question flagged so you know where you'll mess up.

---

## What This Does

You upload the chapters or readings (or paste them, or just name them if the AI has been briefed on the syllabus). The prompt builds a focused quiz with an answer key. It's not for memorization — it's for *application*. The short-answer questions force you to apply a framework, not just recite it.

The most useful feature: at the end, the AI flags the **one question students typically get wrong and why.** That's the highest-leverage minute of your study session.

---

## The Prompt

```
You are a study partner building a practice quiz for an MBA student preparing for an exam.

ASK
Build a quiz on the topics, chapters, or readings I name below. The quiz should test whether I can APPLY the concepts, not just recite them.

CONTEXT
- I am a student preparing for [INSERT EXAM TYPE — quiz, mid-term, final].
- The topics I want covered: [INSERT TOPICS, CHAPTERS, OR READING TITLES].
- I have access to the source material via [the syllabus uploaded to this Project / the chapters I've pasted / my notes I've shared] — use only what's in scope.

CONSTRAINTS
1. Five multiple-choice questions (A, B, C, D). Mix recall and application:
   - 2 recall (definition, who said what, what's the term for X)
   - 3 application (given this scenario, which framework applies / which decision is correct / what would you do)
2. Two short-answer questions that require applying a framework to a hypothetical scenario. Each scenario should be one paragraph, realistic, and have a defensible answer.
3. Answer key at the very end of the response, under a clear "---ANSWER KEY---" header. Each answer includes a one-sentence explanation of WHY it's correct.
4. Do NOT put the answer key inline next to each question — I want to take the quiz first.
5. After the answer key, identify the ONE question students most often get wrong, name the trap, and explain how to spot it next time.
6. If a question requires source material I haven't given you, do not invent it — say so and ask me to provide it.

Format: numbered list, plain markdown, no extra commentary.
```

---

## What You Get Back

```
1. Which of the following best describes "market positioning"?
   A. The price point relative to competitors
   B. The distinct mental position a brand occupies in customer minds
   C. The percentage of market share held
   D. The geographic distribution of stores

2. ...

---ANSWER KEY---
1. B — Positioning is about perception, not price or share. (Common trap: confusing with market share.)
2. ...

---MOST-MISSED QUESTION---
Question 4. Most students confuse "differentiation" with "positioning." Differentiation is what makes your product different (the "what"). Positioning is how customers PERCEIVE that difference (the "where in their minds"). Watch for the word "perceived" in the question stem — that's almost always positioning.
```

---

## How To Use It

1. **Take the quiz before scrolling to the key.** Honor system. The point is the practice, not the score.
2. Mark which ones you got wrong. Re-read the explanation.
3. **Pay extra attention to the "most-missed" callout.** That's where the exam is going to come for you.
4. Re-run the prompt with adjacent topics 24 hours later for spaced repetition.

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| Questions feel too easy / surface-level | Add to ASK: *"Make the application questions HARD — multi-step reasoning, ambiguous scenarios. Don't make them obvious."* |
| AI invents content not in the syllabus | Tighten CONTEXT: *"Use ONLY material from the chapters/readings listed. If you can't build a question from the listed material, say so."* |
| Answer key shows up inline | Re-run with constraint #4 emphasized: *"DO NOT show answers above the key. The key goes at the very end."* |
| Short-answer scenarios feel generic | Add: *"Each scenario must include specific numbers, named companies (real or fictional), or quantitative trade-offs. No generic 'a company is deciding...'."* |
| You want a longer quiz | Adjust the constraint: *"10 multiple choice + 4 short answer."* The structure scales. |

---

## Why This Works

Most "AI quiz" prompts produce flashcard-style recall questions. This prompt forces application. The reason: most exams *are* application. If your study tool only tests recall, you're under-preparing.

The "most-missed question" callout is the highest-leverage feature here. The AI knows which trap is most common because it's been trained on millions of student errors. Use that.

---

> Run this every Sunday for the week's chapters. Treat it like film study after practice — find the gap, fix the gap, move on.
