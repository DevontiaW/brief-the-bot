# Syllabus → Calendar Invites

Turn any class syllabus into a set of calendar events you can import into Apple Calendar, Google Calendar, or Outlook in 60 seconds.

This is the cleanest worked example of the three levers in this repo — and probably the most useful one for any student juggling deadlines, travel, and a calendar that already has too much in it.

---

## What This Does

You upload a syllabus. The AI reads every graded assignment, exam, project, and major deadline, and outputs a single `.ics` file (the universal calendar format). You import that file once and your whole semester shows up on your phone — colored, dated, with the assignment weight in the description so you know what's worth grinding on.

**No copy-pasting individual due dates. No "I forgot the midterm was this week."**

---

## The Prompt (Copy This Exactly)

```
You are a study planner helping a student turn a class syllabus into machine-readable calendar events.

ASK
Extract every graded assignment, exam, project, presentation, paper, and major deadline from the syllabus I uploaded. For each one, generate an iCalendar (ICS) VEVENT entry that I can import into Apple Calendar, Google Calendar, or Outlook.

CONTEXT
I am a student. The syllabus is the document attached to this message. My timezone is [INSERT YOUR TIMEZONE — e.g., America/New_York, America/Chicago, America/Los_Angeles, Europe/London]. Treat the due date in the syllabus as the deadline. If a time isn't specified, default to 11:59 PM in my timezone on the due date. Use the course code from the syllabus (example: MKT501) in every event title.

CONSTRAINTS
1. Output a single, complete .ics file. Start with:
   BEGIN:VCALENDAR
   VERSION:2.0
   PRODID:-//brief-the-bot//Student Calendar//EN
   CALSCALE:GREGORIAN
   And end with:
   END:VCALENDAR

2. One VEVENT per graded item. Each VEVENT must include:
   - UID: unique string in the format [course-code]-[short-slug]-[YYYYMMDD]@brief-the-bot
   - DTSTAMP: today's date and time in UTC, formatted YYYYMMDDTHHMMSSZ
   - DTSTART and DTEND: the deadline date and time, formatted YYYYMMDDTHHMMSS, with TZID set to my timezone (example: DTSTART;TZID=America/New_York:20260507T235900)
   - SUMMARY: [course-code] — [assignment name]   (example: MKT501 — Mid-Term Exam)
   - DESCRIPTION: include the assignment's weight (% of grade), any page reference, and any prep notes from the syllabus. Use \n for line breaks inside the DESCRIPTION field.

3. Do NOT invent due dates. If the syllabus is ambiguous about a date for any item, skip the VEVENT and instead add a // NEEDS CLARIFICATION comment line in the file with the assignment name and what's unclear.

4. Wrap your entire output in a single fenced code block labeled ics so I can copy it cleanly.

5. After the code block, list every assignment for which you flagged ambiguity in a short markdown bullet list, so I can fix them manually before importing.

Verify before you finish: every VEVENT has a unique UID, every DTSTART has a valid date, and the file opens with BEGIN:VCALENDAR and closes with END:VCALENDAR.
```

---

## What You Get Back

A code block that looks like this (one VEVENT per assignment):

```ics
BEGIN:VCALENDAR
VERSION:2.0
PRODID:-//brief-the-bot//Student Calendar//EN
CALSCALE:GREGORIAN
BEGIN:VEVENT
UID:MKT501-midterm-20260507@brief-the-bot
DTSTAMP:20260427T180000Z
DTSTART;TZID=America/New_York:20260507T235900
DTEND;TZID=America/New_York:20260507T235900
SUMMARY:MKT501 — Mid-Term Exam
DESCRIPTION:Worth 25% of grade.\nCovers chapters 1–6.\nIn-class, closed book.
END:VEVENT
BEGIN:VEVENT
UID:MKT501-final-paper-20260615@brief-the-bot
DTSTAMP:20260427T180000Z
DTSTART;TZID=America/New_York:20260615T235900
DTEND;TZID=America/New_York:20260615T235900
SUMMARY:MKT501 — Final Paper Due
DESCRIPTION:Worth 30% of grade.\n8–10 pages, APA format.\nSubmit via Canvas.
END:VEVENT
END:VCALENDAR
```

Plus an ambiguity list below it like:

> **Needs your eyes:**
> - Group presentation week — date listed as "Week 14" but no specific calendar date. Pull the date from your section's schedule.

---

## How To Import It (Phone-First)

1. Copy everything inside the `ics` code block (just the code, no markdown fences).
2. Paste it into a plain-text file. Save it as `[course-code].ics` (example: `MKT501.ics`).
3. **iPhone / Apple Cal:** AirDrop the file to your phone, tap it, choose "Add All."
4. **Google Calendar:** [calendar.google.com](https://calendar.google.com) → Settings → Import & Export → Import → upload the `.ics`.
5. **Outlook:** Open the `.ics` directly. Outlook will offer to add it.

Done. Your semester is on your phone.

---

## When It Goes Wrong

| Symptom | Fix |
|---|---|
| AI says "I can't read PDFs" | Claude.ai (free + paid), ChatGPT (free + paid), and Gemini all read PDFs. If a specific account is stuck, paste the syllabus text directly instead of uploading the PDF. |
| Dates are wrong / made up | Your CONSTRAINTS need teeth. Add a line: *"If a date isn't explicitly written in the syllabus, do not invent one. Add // NEEDS CLARIFICATION instead."* |
| File saves as `.ics.txt` (Windows) | Windows often hides extensions and adds `.txt` when saving from Notepad. Open File Explorer → View → check "File name extensions" → rename to remove the `.txt`. Or save from VS Code / a real text editor. |
| Apple Cal won't import | Check the file extension is `.ics` (not `.ics.txt`). On Mac: right-click in Finder → "Get Info" → rename. |
| Events show at the wrong hour after import | Your TZID didn't make it into the file. Re-run the prompt and double-check that every DTSTART line includes `TZID=YourTimezone` (example: `DTSTART;TZID=America/New_York:...`). Without TZID, calendars guess and usually guess wrong. |
| Output is a markdown table, not ICS | The AI ignored the format constraint. Add at the top: *"Output ICS only. No tables. No prose. No explanations above the code block."* |

---

## Fallback (No ICS, Just a Table)

If the ICS path is too much friction, run this prompt instead and copy the output into a calendar manually:

```
Extract every graded assignment, exam, and major deadline from the syllabus I uploaded. Output a single markdown table with columns: Date | Course | Assignment | Weight (%) | Notes. Sort by date, earliest first. If a date is ambiguous, write "TBD" and add a one-line "needs clarification" note in the Notes column. Do not invent dates.
```

You'll lose the auto-import magic, but you'll still have your whole semester in one place inside two minutes.

---

## Why This Prompt Works (Read If You Want To Build Your Own)

This prompt is the three levers in their cleanest form:

- **ASK** is two sentences. *Extract X. Generate Y in this format.* No fluff.
- **CONTEXT** tells the AI what role to play (study planner), what document to use (the upload), and what default to apply (11:59 PM if no time given). Defaults are how you stop the AI from asking 12 clarifying questions.
- **CONSTRAINTS** are a numbered list, not a paragraph. Numbered constraints have *teeth* — the AI treats them as a checklist. Prose constraints get ignored.

The most important constraint is #3 — *do not invent due dates.* That single line is the difference between a calendar you trust and a calendar that's lying to you. **Ground rules beat smart models, every time.**

This is the orchestrator move: you don't just ask, you brief.

---

> Ship it: import your `.ics` and free your brain from due-date tracking. PR your wins to [`cookbook/`](../cookbook/).
