# Exit Report — Adversarial Review of brief-the-bot
**Date:** 2026-04-27
**Agent:** adversarial reviewer subagent
**Project:** brief-the-bot (talk Wed Apr 29, Rollins AI Business Association)
**Tags:** ["project:brief-the-bot","type:exit-report","type:redteam","topic:talk-prep","date:2026-04-27"]

## Task Summary
Conducted three-part adversarial review of `C:/Users/Devon/Textstone/projects/brief-the-bot/` ahead of Wednesday Apr 29 talk to ~30 Rollins student-athletes. Read all 6 prompt files in 02-prompt-pack, both Skill recipes in 03-claude-skills, README, glossary, reading-list, 01-the-levers, sample syllabus, agent-sdk-stretch, cookbook. Mentally simulated student execution; verified citations against known facts; red-teamed strategy/QR-code first-click failure mode. Delivered prioritized findings (BLOCK/WARN/NIT) within 700-word cap with ship verdict.

## Key Decisions / Findings
1. **[BLOCK] .ics floating-time bug is load-bearing.** `02-prompt-pack/syllabus-to-calendar.md` lines 38-42 instructs DTSTART without TZID and without Z suffix. Per RFC 5545 this is "floating time" — Apple Cal and Google Cal handle it inconsistently; deadlines render at wrong hours. Same bug in Skill recipe `calendar-invite-maker.md` lines 62-65. This is the demo from the talk AND the first thing students will tap from the QR code. Must fix before push. Recommended fix: add `TZID=America/New_York` (or user TZ from CONTEXT) to DTSTART/DTEND, give DTEND a 30-min buffer over DTSTART.

2. **[BLOCK] Two unverified citations on a public repo aimed at academic audience.** Schluntz quote ("ask not what Claude can do for you...") in reading-list.md line 25 and 01-the-levers/README.md line 85 — exact wording and 2026 talk date need verification (Schluntz's known public talk was 2024 era). Kosmyna MIT EEG study reading-list.md line 35 — exists as pre-print but the "measurably less neural engagement" framing oversimplifies a small-N pre-print and is presented as "empirical teeth."

3. **[BLOCK] Strategic first-click risk.** QR on Slide 12 → README → Pick Your Path → syllabus-to-calendar.md (the demo). The first click off the QR delivers a broken artifact unless .ics bug is fixed.

4. **[WARN] Thesis vs execution mismatch.** Repo claims "workflow > prompt" but ships a folder of prompts and calls the framework "levers." Need explicit framing in 01-the-levers/README.md addressing the obvious skeptical read.

5. **[WARN] "ChatGPT (paid)" claim wrong** in syllabus-to-calendar.md line 106 — free tier reads PDFs.

6. **[WARN] Glossary "Trust and Glue" framing** — Clark & Chalmers use "trust" not "trustworthiness"; "Trust and Glue" itself is a teaching gloss not their phrase. Flag as Devon's gloss.

7. **[WARN] Practice-quiz overconfidence** — "AI knows which trap is most common because trained on millions of student errors" is unsupported.

## Lessons Learned
- **Public-repo QR distribution amplifies tiny correctness bugs.** A floating-time .ics bug that would be a footnote in private use becomes the load-bearing failure when 30 students all run the same demo on the same night. The cost of one wrong constraint × 30 first-time users = repo death in week one.
- **Citation verification is a different threshold for a public repo than a private note.** Schluntz quote was probably fine in a private deck; on a public GitHub repo with a live audience, exact wording + source URL is needed.
- **Adversarial review found bugs that prove-it-works style review would have missed.** Reading the prompts as text feels fine; *mentally simulating a student running them on a Tuesday night with a real syllabus* is what surfaced the timezone bug. Mode matters.
- **The "60-second version" claim in README is marketing inflation** — realistic first-time path is 3-5 minutes. Acceptable as marketing but flag.

## Dead Ends
- Could not directly verify Schluntz 2026 talk title without WebSearch — flagged for Devon to confirm.
- Could not verify exact Wiener "complete subservience and complete intelligence do not go together" wording without book in hand — flagged for verification.
- Echo MCP tools not available in this subagent's deferred-tool list, so falling back to filesystem exit-report instead of echo_exit_report.

## Open Questions for Devon
1. Does the .ics fix go in tonight (Mon) or Tue? It's a 2-hour fix but blocks the QR.
2. Do you want to pull the Schluntz quote entirely, or verify-and-keep? If keep, link the source video.
3. Should the sample-syllabus.md test path become the *first* recommended action in README, before the real-syllabus path?

## Files Touched
- Read-only: all repo files listed in task summary
- Created: this exit report

## Verdict Delivered
"Hold for substantial revision (24-hour fix sprint)." Load-bearing reason: .ics floating-time bug + first-click QR risk = repo credibility dies in week one if shipped as-is. Two-hour fix; non-negotiable.
