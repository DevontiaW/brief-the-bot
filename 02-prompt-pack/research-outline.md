# Research Outline (Source-Grounded)

Build a research paper outline where every claim is anchored to the sources you uploaded. The AI is forbidden from inventing studies. When the evidence is thin, it tells you — instead of guessing.

This is the prompt that earns the orchestrator title.

---

## What This Does

The most common AI failure mode in academic work isn't bad writing — it's confident hallucination. The AI cites a study that doesn't exist. It misattributes a quote. It invents a statistic that's plausible enough to slip past a tired student.

This prompt is built to stop that. Three moves:

1. **Sources are loaded explicitly.** You upload them. The AI only reasons from what you've uploaded.
2. **Every claim must be tied to a specific source** — with a quote or page number when possible.
3. **Where evidence is thin or missing, the AI flags it** instead of papering over it.

The result is an outline you can actually defend in a discussion section — and a list of holes you need to fill before you start drafting.

---

## The Prompt

```
You are a research assistant helping a graduate student build a defensible outline for a research paper. You are rigorous about sourcing. You never invent citations. You flag weakness instead of papering over it.

ASK
Build a research outline for a paper with the thesis below, using ONLY the sources I have uploaded to this session.

CONTEXT
- Thesis (1–2 sentences): [INSERT YOUR THESIS]
- Length target: [INSERT — e.g., 8 pages, 12 pages, 15 pages]
- Discipline / citation style: [INSERT — e.g., APA 7th, MLA, Chicago]
- The sources I've uploaded: [list them by author + short title so we're aligned on what's in scope]
- Anything else I want included or NOT included: [INSERT — e.g., "include a counterargument section", "do not use Marxist frame"]

CONSTRAINTS
1. Output a structured markdown outline with the following sections:
   - Introduction (with thesis restated)
   - 3–5 body sections, each with 2–4 sub-points
   - Counterargument section
   - Conclusion
2. EVERY sub-point must include:
   - The claim (one sentence)
   - The supporting source (author + short title, with page or section reference if available)
   - A confidence flag: STRONG (direct quote/data), MODERATE (interpretive but defensible), or WEAK (thin evidence — needs more sourcing)
3. Where you cannot find sufficient support in the uploaded sources for a claim the thesis requires, do NOT make up a citation. Instead, write:
   `[GAP — needs source on: <specific topic>]`
4. After the outline, list ALL items flagged WEAK or GAP in a final "Sourcing Punch List" — these are what I need to fill before drafting.
5. Use the citation style I specified (constraint format only — full bibliography is a separate task).
6. Do not invent quotes, page numbers, or studies. If you can't pin a claim to a specific upload, flag it as GAP.

Verify before you finish: every claim is either tagged STRONG, MODERATE, WEAK, or GAP. None are unflagged.
```

---

## What You Get Back

A structured outline like this (excerpt):

> ## II. Direct-to-Consumer brands win on speed of feedback
>
> **A. D2C feedback loops are measurably tighter than retail.**
> Source: McKinsey D2C Report 2024, p.12. Confidence: **STRONG** — direct stat: "D2C brands iterate 3.4× faster than retail-distributed brands on average."
>
> **B. Speed of feedback enables product-market fit faster.**
> Source: Warby Parker case study (HBR), p.8. Confidence: **MODERATE** — case discusses iteration speed but does not directly link to PMF metrics.
>
> **C. The price advantage often cited is largely myth.**
> `[GAP — needs source on: D2C pricing parity vs retail. Suggested search: NRF 2024 pricing benchmarks.]`

Then below:

> ## Sourcing Punch List
>
> - Section II.B — needs a stronger PMF-to-feedback-speed source
> - Section II.C — needs pricing parity data (no upload covers this)
> - Section IV.A — counterargument WEAK; needs a specific D2C failure case study (suggested: Casper post-IPO)

---

## How To Use It

1. **Upload your sources first.** This is the load-bearing step. The outline is only as good as what's loaded.
2. Open a fresh Project (Claude/ChatGPT) so the sources persist across the conversation.
3. Paste the prompt. Fill in the four CONTEXT blocks.
4. Run.
5. **Start with the Sourcing Punch List, not the outline.** That tells you where the paper is weak before you fall in love with the structure.
6. Hunt for the missing sources (Google Scholar, your school library, the syllabus reading list). Upload them and re-run.
7. Iterate until every claim is STRONG or MODERATE — no unresolved GAPs.
8. *Then* start drafting from the outline.

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| AI cites a source you didn't upload | The sandbox broke. Re-run and bold constraint #6: *"USE ONLY THE SOURCES I UPLOADED. If you reference any source not in the upload list, that is a critical error — flag it as `[GAP]` instead."* |
| Confidence flags missing on most sub-points | Re-run with: *"EVERY sub-point must have a confidence flag. No exceptions. If you skip one, the outline is incomplete."* |
| Quotes look invented | Add: *"Use ONLY direct quotes from the uploaded text. Format quotes with quotation marks AND a page reference. If you can't pin a quote to a page, paraphrase and flag MODERATE."* |
| Outline is too generic to be useful | Add to ASK: *"Sub-points should be specific claims, not section topics. 'D2C brands iterate 3.4× faster' (specific) — not 'D2C brands iterate fast' (generic)."* |
| Counterargument is weak / strawmanned | Add: *"The counterargument section must use the SAME confidence rules. Find the strongest case AGAINST my thesis in the uploaded sources. If no source contradicts the thesis, flag GAP and tell me which kind of source to find."* |

---

## Why This Works

The single most important constraint is **#3** — *do NOT make up a citation. Flag GAP instead.* That single rule is the difference between an outline you can defend and an outline that will get you flagged for academic dishonesty if a professor checks any of the citations.

The confidence flags do something subtler. They force the AI to make its uncertainty *visible.* In normal AI prose, uncertainty hides — everything sounds confident. Here, uncertainty is structural. You can see exactly which claims rest on shaky ground.

This is the orchestrator move applied to research. **You're not asking the AI to write the paper. You're asking it to map the territory so you can decide where to dig.**

---

## A Note on Academic Honesty

Using AI to *map* sources you've uploaded is not the same as using AI to *write* the paper. The first is a tool — like an annotated bibliography software. The second is a violation of most academic integrity policies.

This prompt is designed for the first use case. It tells you what your sources support. **You still have to read them. You still have to write the paper. The AI is your research assistant, not your ghostwriter.**

If your school requires AI-use disclosure (more do every semester), disclose it. The disclosure won't hurt you. The non-disclosure will.

---

> Pair with [`practice-quiz.md`](./practice-quiz.md) — once the paper is drafted, generate a quiz on your own arguments to make sure you can defend them in a class discussion.
