# Agent SDK Stretch (Coming Soon — May 2026)

For the curious builders. The next layer down: the same syllabus-to-calendar workflow, but built as a real **agent** using the Anthropic SDK — Python script, file-read tool, ICS-write tool.

---

## What This Will Cover

- A working Python script that takes a syllabus PDF as input and outputs a `.ics` file as output, end-to-end, no human in the loop
- Built with [Anthropic's Python SDK](https://docs.anthropic.com/en/api/getting-started)
- Uses tool-use to read the PDF and write the ICS file
- Documented end-to-end so you can fork it and extend it (résumé tailor agent, research outline agent, etc.)

---

## Why It's Not Here Yet

Two reasons:

1. **Most students reading this repo don't have an Anthropic API key** — and that's fine. The agent is a "look what's possible" artifact, not a "use this tonight" artifact. Shipping it on Day 1 of this repo would have crowded out things you can actually use this weekend.

2. **The repo's job is discipline. The SDK is the next layer.** This pack's primary job is to teach the workflow. The SDK is for the small subset of readers who want to *build* the agent themselves rather than run it manually in Claude. That's a different conversation.

---

## When It Drops

Target: **May 2026.** Watch this folder, or follow [@DevontiaW on GitHub](https://github.com/DevontiaW) — the script will land here as `syllabus-to-ics-agent.py` with a runbook.

If you can't wait, here's the path to build it yourself:

1. Sign up for an Anthropic API key: [console.anthropic.com](https://console.anthropic.com).
2. Read the [Python SDK quickstart](https://docs.anthropic.com/en/docs/get-started).
3. Look at the `syllabus-to-calendar.md` prompt in this repo — that's your system prompt.
4. Add tool definitions for `read_pdf(path)` and `write_ics(content, path)`.
5. Run the loop.

You'll have a working agent in an afternoon. If you build it before May, **ship it to the [cookbook](../cookbook/)** as a Skill recipe + Python script, and the canonical version will reflect your work.

---

> The first AI fluency was prompts. The second is workflows. The third is agents. You're ready for layer two if you've made it this far.
