# Résumé Tailor

Take your résumé and a job posting. Get back a tailored rewrite plus a ranked list of every gap you'd need to close — most fixable first.

---

## What This Does

Most "tailor my résumé" prompts produce a slightly reworded version that uses the job posting's keywords. Useful for ATS scanners. Useless for actually deciding whether to apply.

This prompt does both. You get the rewritten résumé *and* you get an honest gap analysis: which gaps are easy to close in 6 months (a certification, a side project), which are moderate (a relevant role on campus or in a club), and which are deal-breakers (5 years of industry experience you don't have). It tells you whether the job is realistic — not just whether you should hit "Submit."

---

## The Prompt

```
You are a senior recruiter who has reviewed thousands of MBA résumés. You are honest, kind, and direct. You don't sugarcoat fit problems, but you also don't dismiss candidates over fixable gaps.

ASK
Tailor my résumé to the job posting below, AND produce a ranked gap analysis showing every place my current experience falls short of the posting's requirements.

CONTEXT
My current résumé:
[PASTE OR UPLOAD YOUR FULL RÉSUMÉ HERE]

The job posting:
[PASTE THE FULL JOB POSTING HERE]

CONSTRAINTS
1. Output in this order:
   PART 1 — TAILORED RÉSUMÉ
   PART 2 — GAP ANALYSIS (table)
   PART 3 — VERDICT (1 paragraph)
   PART 4 — IF YOU APPLY, FOCUS ON THESE THREE THINGS

2. PART 1 — Tailored Résumé:
   - Same structure and length as my current résumé.
   - Reword bullet points to match the language and priorities of the posting (without inventing experience I don't have).
   - Reorder sections if needed to lead with what's most relevant.
   - Flag any bullet you reworded heavily so I can verify accuracy before submitting.

3. PART 2 — Gap Analysis Table:
   Columns: Posting Requirement | My Current Match (1–5) | Closability (Easy/Moderate/Hard/Dealbreaker) | What it would take to close
   Rank rows by Closability (Easy first, Dealbreaker last).

4. PART 3 — Verdict (1 paragraph):
   Should I apply? Honest assessment. "Apply now," "apply with a strong cover letter that addresses X," "build for 6 months and apply," or "this is not a fit, here's a closer one to look at."

5. PART 4 — If you apply, focus on these three things:
   The three highest-leverage moves I should make in the cover letter or interview to address the most critical gaps.

6. Do not invent experience, certifications, or skills I don't have. Where the gap is large, say so plainly. I would rather hear it now than waste a week.
```

---

## What You Get Back

A clean, ATS-friendly résumé tailored to the posting (Part 1), followed by a ruthlessly honest table like:

| Requirement | Match (1–5) | Closability | What it takes |
|---|---|---|---|
| Excel modeling | 4/5 | Easy | Add one bullet showing financial model from MKT500 case |
| 2+ yrs healthcare | 1/5 | Hard | Internship or capstone in healthcare (would need to delay 12+ months) |
| Python | 3/5 | Moderate | Coursera cert + portfolio project (~3 months) |
| Manager experience | 5/5 | — | Strong — Army squad lead translates well |

Then a verdict: *"Apply with a strong cover letter that addresses the healthcare-experience gap directly. Lean on your transferable analytics skills and your willingness to learn the domain fast."*

Then three things to lead with in the cover letter / interview.

---

## How To Use It

1. Open a fresh chat (don't reuse a chat where the AI has been editing other résumés — context bleeds).
2. Paste the prompt. Fill in the two blocks: your résumé, the job posting.
3. Run.
4. **Read Part 3 (the verdict) before you read Part 1 (the rewritten résumé).** If the verdict is "this isn't a fit," save yourself the time and find a closer match.
5. If you do apply, use Part 4 to write the first paragraph of your cover letter — that's where you address the biggest gap directly.

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| AI invents experience or skills | Tighten constraint #6: *"Do NOT add any bullet, certification, or skill that is not explicitly in my current résumé. Reword only."* |
| Verdict is mealy / "depends" | Add to ASK: *"Give me a binary: APPLY or DON'T APPLY. If borderline, default to APPLY only when the gaps are closable in 90 days."* |
| Tailored résumé sounds nothing like you | Add to constraints: *"Preserve my voice. If a bullet currently reads as confident and direct, the rewrite should be too — don't make it more corporate."* |
| Gap analysis is shallow | Add: *"For each gap, name the SPECIFIC certification, course, project, or experience that would close it. No vague advice like 'gain more experience.'"* |
| You want focus on a different role / level | Tell it: *"Treat the posting as a stretch role. Lean my résumé toward demonstrating potential, not just past performance."* |

---

## Why This Works

Most résumé tailoring tools optimize for *getting through the ATS scanner.* That's a low bar. This prompt optimizes for two harder questions: **(1) is this job actually the right one to apply to right now, and (2) if yes, where am I weakest and how do I address that head-on?**

The four-part structure forces the AI to give you both parts of the truth — the polished surface (the rewritten résumé) and the honest assessment (the gap analysis). Most students want only the first part. The second part is where the actual decision lives.

---

> Pair this with [`email-to-professor.md`](./email-to-professor.md) when you need a recommendation letter — same discipline applied to the ask.
