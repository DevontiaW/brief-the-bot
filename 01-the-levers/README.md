# The Three Levers

## The Idea

Every framework you've seen for "prompt engineering" — CRAFT, RACE, CO-STAR, PEEL, PRISM, the next one launching next Tuesday — is repackaging the same three muscles. You don't need to memorize acronyms. You need to run the levers.

**ASK** — Be specific.
**CONTEXT** — Set the scene.
**CONSTRAINTS** — Shape the output.

That's the whole framework. Three levers. The discipline is in pulling all three every time.

## In Practice

Two worked examples. Same student, same hour, very different results.

### Example 1 — The Same Question, Asked Two Ways

**Weak ASK:**
> "Can you help me with my marketing paper?"

**What you get back:** A bulleted list of generic advice — "consider your audience, use data, make sure your conclusion ties back to your thesis." Nothing wrong. Nothing useful.

**Strong ASK + CONTEXT + CONSTRAINTS:**
> **ASK:** Outline a five-paragraph argument defending the thesis below, using the three sources I uploaded.
> **CONTEXT:** Thesis: *"Direct-to-consumer brands win on speed of feedback, not on price."* Sources: HBR article on Warby Parker, Dollar Shave Club case study, McKinsey D2C report (all attached).
> **CONSTRAINTS:** Five paragraphs, one core argument per paragraph, each tied to a specific quote or stat from the sources. Flag any paragraph where the sources don't fully support the claim.

**What you get back:** A real outline you can actually write from. Each paragraph has a claim, evidence from a specific source, and a flag where the evidence is thin so you know what to dig into.

The prompt didn't change in spirit — *"help me with my paper"* is still the underlying ask. The discipline changed.

### Example 2 — The Constraint That Saves the Hour

You ask: *"Compare these three companies' marketing strategies and tell me which one is best."*

You get back: three confident-sounding paragraphs that all say "it depends on context" and never actually pick one. You're back where you started.

Add one constraint: *"Output a markdown table — Company | Core Strategy | Strongest Evidence | Weakness | Verdict (rank 1–3 with reasoning)."*

Now you get a table. Each company has a rank. Each rank has a reason. You can disagree with the AI's verdict — but at least there *is* a verdict.

**Constraints have teeth. Prose doesn't.**

## Framework

```
┌─────────────────────────────────────────────────────────┐
│  ASK         What is the deliverable, exactly?          │
├─────────────────────────────────────────────────────────┤
│  CONTEXT     What does the AI need to know?             │
│              (your situation, your data, your audience) │
├─────────────────────────────────────────────────────────┤
│  CONSTRAINTS What shape should the output take?         │
│              (format, length, format, what to flag)     │
└─────────────────────────────────────────────────────────┘
```

Read it top-down. **If you don't have a clear ASK, the rest is decoration.** Most bad prompts are bad asks. Fix the ASK first.

## How To Pull All Three (60-Second Practice)

Every time you open a chat, ask yourself three questions before you type:

1. **What's the actual deliverable?** Not "help me," but "draft a 3-paragraph email." Not "study this," but "build me a 5-question quiz with answer key."
2. **What does the AI not already know?** Upload it. Paste it. Name the class, the professor, the rubric, the constraint.
3. **What format do I want back?** Table? Bulleted list? Markdown? Three columns? One paragraph? *"What flag if uncertain?"*

If you can answer all three before you press Enter, you're 80% of the way to a useful response.

## Your Move

Open Claude, ChatGPT, or Gemini right now. Take the most generic question you've asked an AI in the last week. Re-write it using all three levers. Run both versions side-by-side. **Compare the outputs.**

You'll see the difference inside one prompt. That's all this discipline is — applied repeatedly, every time you open a chat.

## Go Deeper

- [`02-prompt-pack/`](../02-prompt-pack/) — six prompts that already pull all three levers. Steal them.
- [`reading-list.md`](../reading-list.md) — the books and papers that built the discipline.
- [Anthropic's prompting guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) — same muscles, more depth.

---

> **One more thing.** A famous Anthropic engineer named Erik Schluntz once said the right test for a prompt is: *"What guidance or context would a new employee on your team need to succeed at this task?"* Everything in this repo is just that question, applied to school instead of work.
