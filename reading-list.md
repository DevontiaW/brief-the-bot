# Reading List

The books, papers, and talks that built the discipline behind this repo. Roughly ordered: start at the top if you want the foundations; jump in anywhere if you want depth on a specific idea.

---

## On the Discipline (Start Here)

### *Building a Second Brain* — Tiago Forte (2022)
The book that named what most of us were doing badly. Forte's CODE pattern — Capture, Organize, Distill, Express — is the discipline behind every prompt in this repo. If you've been collecting notes, articles, and ideas across forty apps and never doing anything with them, this book fixes that. Read it first.

### *"What Is Strategy?"* — Michael Porter, HBR (1996)
The foundation. Still the best thing written on strategy, period. Why does it belong in an AI repo? Because **strategy is choosing what NOT to do** — and that's the same muscle as prompt design. Every CONSTRAINT you add to a prompt is a "what not to do" decision. You're already doing strategy when you're prompting well. Most people just don't know it.

---

## On AI as a Cognitive Partner

### *"The Extended Mind"* — Andy Clark & David Chalmers (1998)
The 30-year-old paper that quietly predicted the AI era. Clark and Chalmers argue that a tool becomes part of your mind when it meets three criteria: **Reliability, Trustworthiness, Accessibility.** That's the *Trust and Glue* framework. The whole talk threads through this paper. The original is short (~15 pages) and surprisingly readable. Free PDF easy to find.

### *God and Golem, Inc.* — Norbert Wiener (1964)
The book where Wiener — the inventor of cybernetics — saw all of this coming. The line that lives in slide 7 and slide 10: *"complete subservience and complete intelligence do not go together."* Translation: a system smart enough to do your work for you will start interpreting your goals in ways you didn't expect. You need the discipline to keep the kill switch. Short, dense, and 60 years ahead of its time.

### Erik Schluntz — *"Vibe Coding in Production"* (talk, 2026)
Schluntz is an Anthropic engineer who builds AI systems for a living. His core line: *"Ask not what Claude can do for you — ask what guidance or context a new employee on your team would need to succeed."* That's the team-lead framing this whole repo runs on. Worth the 40 minutes. Find it on YouTube — search "Schluntz vibe coding."

---

## On Cognition and the Fluency Trap

### *Thinking, Fast and Slow* — Daniel Kahneman (2011)
The reason fluent AI text feels true even when it's not. Kahneman's System 1 (fast, automatic, easily fooled by surface fluency) versus System 2 (slow, deliberate, exhausting). The Fluency Trap on slide 7 is System 1 betraying you in real time. Read at minimum the first six chapters.

### Nataliya Kosmyna et al. — MIT Media Lab EEG Study on AI use (2025)
The study that gives the talk its empirical teeth. Subjects writing essays with AI assistance showed measurably less neural engagement than subjects writing without. Cited in the Q&A back-pocket arsenal. Search "Kosmyna AI EEG essay" on Google Scholar. Pre-print is free.

---

## On Prompt Engineering (Tactical)

### Anthropic's *Build with Claude* — Prompt Engineering docs
[docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
The single best free resource. Same three muscles I teach in this repo, with deeper coverage of advanced techniques (chain-of-thought, prompt caching, tool use) when you're ready for them. Skim the overview, then go back when a specific prompt is misbehaving.

### Anthropic's *Skills* docs
[docs.anthropic.com/en/docs/build-with-claude/skills](https://docs.anthropic.com/en/docs/build-with-claude/skills)
What Skills are, how to build them, how to install. The two Skills shipped in [`03-claude-skills/`](./03-claude-skills/) of this repo follow this spec. If you build your own, this is the reference.

---

## On Building (For the Curious Builders)

### *The Mom Test* — Rob Fitzpatrick
How to talk to people about an idea without lying to yourself about whether they actually want it. If you're building "your first thing" from the talk's Slide 12 challenge #3, read this before the third week. Short, brutal, life-changing for first-time builders.

### *The Lean Startup* — Eric Ries
The book that named MVP, build-measure-learn, and pivot. Sometimes mocked because it became corporate cliché — but the underlying discipline is solid. Read it once, internalize the loop, ignore everything that's been written about it since.

### *Designing Data-Intensive Applications* — Martin Kleppmann
Stretch goal — only relevant once you're past v1 of an actual product. The reference text on how data systems actually work under the hood. If you're using Claude or v0 to build something that has any data complexity, this is what your engineering co-founder will quote at you in year two.

---

## On Strategy (For When You Stop Being a Student)

### *Good Strategy / Bad Strategy* — Richard Rumelt (2011)
The book Porter would write if he were still teaching today. Rumelt's "kernel" — diagnosis, guiding policy, coherent action — is the framework I use for AI strategy at Deloitte. The first three chapters alone are worth the price.

### McKinsey's *State of AI* annual survey
[mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)
Hard data on where AI is actually creating value across industries. Updated annually. Your shortcut to "what's actually happening in enterprise AI" without reading 100 individual case studies.

---

## How to Read This List

You don't need to read all of this. Pick your path:

- **You want to be a better student tonight:** Forte (BASB) + Anthropic prompting docs. Two weeks.
- **You want to understand WHY this works (the philosophical foundation):** Clark & Chalmers + Wiener + Kahneman. One semester.
- **You want to build a real product:** Forte + The Mom Test + Lean Startup. One summer.
- **You want a job in AI strategy:** Porter + Rumelt + McKinsey AI Survey + Anthropic docs. One internship cycle.

The discipline is the same. The depth is what scales.

---

> *"The best AI users don't have the best prompts. They have the best discipline."*
> Discipline comes from reading. Reading comes from you.
