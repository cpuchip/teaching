# Scratch — Episode 2: The Four Disciplines

**Position in arc:** 2 of 11 (the industry-frame episode — walk the four disciplines the industry has named, show what each covers, name what the framework leaves for the work itself).

**Binding question:** *Prompt craft, context engineering, intent engineering, spec engineering — what does each one cover, and what do they leave for the work itself?*

**Target length:** 13–16 minutes (≈2000–2300 spoken words at 150 wpm).
**Date:** 2026-05-22

---

## Episode's job in the series arc

Episode 1 named the bottleneck shift and ended with *"Living inside the new work showed me something the disciplines don't quite reach."* Episode 2 walks all four disciplines so the listener has the vocabulary and understands what each one actually does. The close points at the gap — what the framework leaves for the work itself — without filling it. Episodes 3–11 each take one piece of that gap and walk it. Episode 6 names the seven unmapped steps explicitly.

The episode's job:
1. Teach the four disciplines well enough that the listener could explain them to someone else
2. Show the lived ceiling of each — when Michael was practicing it well and still hit a wall
3. End with the unstated assumption all four share — that something *organizes* the work — and point at what comes next

---

## Outline (5-part structure per `episodes/README.md`)

1. **The engineering problem** (~2:30) — Prompting alone isn't enough. The industry has split prompting into four altitudes. Why each one matters and where they sit relative to each other.
2. **What the industry says** (~5:00) — Walk each discipline: prompt craft, context engineering, intent engineering, spec engineering. What each one is, what it covers, who teaches it. Nate B Jones quotes throughout. The Klarna case for intent.
3. **What actually happened** (~3:30) — Michael's stack as evidence: directing study agents (prompt), the .mind/.spec/.claude system (context), `intent.yaml` + `covenant.yaml` (intent), pg-ai-stewards substrate proposals (spec). For each, the ceiling moment — where the discipline was the right answer until it ran out.
4. **The pattern underneath** (~3:30) — All four disciplines do one thing: they *organize*. D&C 88:119 — *"Organize yourselves; prepare every needful thing; and establish a house..."* — names what the disciplines do. The framework runs out because organizing isn't the whole work. The work also needs bilateral covenant, watching, atonement, sabbath, consecration, zion. Brief gospel pivot — the seven unmapped steps wait for Episode 6.
5. **What this means for you** (~1:30) — Build the four disciplines. They're real, they're necessary, they raise the floor of everything else. Then notice what the framework hands back to you — the work that remains your job. The rest of the series walks that work.

---

## Verified external quotes — verbatim from local transcript cache

### Nate B Jones — "'Prompting' Just Split Into 4 Skills..."

**Source:** `yt/ai-news-strategy-daily-nate-b-jones/BpibZSMGtdY/transcript.md`
**Video:** [YouTube](https://www.youtube.com/watch?v=BpibZSMGtdY) · published 2026-02-27 · 41:11 runtime
**Channel:** AI News & Strategy Daily | Nate B Jones

**[10:12 → 10:20] Prompt craft as individual skill:**
> "This is the skill I have taught and many others have taught for the last year or two. It's synchronous. It's sessionbased and it's an individual skill."

**[11:01 → 11:07] Prompt craft is table stakes:**
> "Prompt craft has not become irrelevant. Don't hear that. It's just become table stakes. It's sort of the way knowing how to type with 10 fingers was once a professional differentiator and now it's just table stakes."

**[12:10] Context engineering defined:**
> "I define context engineering as the set of strategies for curating and maintaining the optimal set of tokens during an LLM task."

**[16:01 → 16:17] Stakes scale with altitude:**
> "When you as an individual sit down and you screw up a prompt, it might waste your morning at worst. When you as a human being sit down and screw up context engineering or intent engineering, you are screwing up for the entire team, your entire org, your entire company."

**[26:20 → 26:29] Spec engineering rewards different thinking** (script renders as compressed pair with ellipsis):
> "Real time prompting rewards verbal fluency... Specification engineering rewards completeness of thinking, anticipation of edge cases, clear articulation of acceptance criteria, and the ability to decompose really complicated outcomes into independently executable components."

(The ellipsis in the rendered version omits intermediate sentences — *"It rewards quick iteration. It rewards a good eye for output quality."* — that don't add to the contrast point.)

### Paweł Huryn — "Intent Engineering Framework for AI Agents" (Product Compass, 2026-01-13)

**Source:** [productcompass.pm](https://www.productcompass.pm/p/intent-engineering-framework-for-ai-agents) (verified via WebFetch 2026-05-22)

> "Intent is what determines how an agent acts when instructions run out."

### Klarna case (intent engineering failure pattern)

**Source:** WebSearch 2026-05-22, multiple corroborating sources including [OpenAI case study](https://openai.com/index/klarna/) and [Klarna press](https://www.klarna.com/international/press/klarna-ai-assistant-handles-two-thirds-of-customer-service-chats-in-its-first-month/).

**Verified facts:**
- 2.3 million conversations in the first month (early 2024)
- "Equivalent of 700 full-time agents" — *but* this was agents Klarna would have needed to hire during a growth phase, not 700 displaced.
- Reduced resolution time from 11 minutes to under 2 minutes.
- By 2025, Klarna publicly walked back some AI-only claims and reintroduced human agents for complex cases.

**The framing the script must respect:** Klarna succeeded at speed and resolution-count metrics, then had to walk back when customer satisfaction issues emerged. That's the intent-engineering failure pattern — the agent optimized for the loudest signal (resolution speed) rather than the deeper value (customer experience). The walk-back is the proof that the optimization was misaligned, not a refutation of AI customer service.

### D&C 88:119

**Source:** `gospel-library/eng/scriptures/dc-testament/dc/88.md:247` — verified verbatim.

> "Organize yourselves; prepare every needful thing; and establish a house, even a house of prayer, a house of fasting, a house of faith, a house of learning, a house of glory, a house of order, a house of God"

---

## Source document audit (Phase 0 critical pass)

The script will pull substantively from the workspace guide at `docs/work-with-ai/guide/00_foundation.md` through `04_spec-engineering.md`. Audit notes:

- **Voice:** the guide docs are textbook prose, not Michael's chat voice. They're correct for reference material; they're wrong for spoken script. Re-voice everything pulled — no sentence-lifting.
- **Quote handling:** the guide docs cite Nate accurately (timestamps match the transcript). Trust the citations but verify against the cached transcript before quoting in the script.
- **Klarna framing in the guide:** the guide treats Klarna as an unqualified "intent engineering failure pattern." The 2026 walk-back is what makes the case load-bearing — note it in the script so the example is honest rather than tabloid.
- **Compressed-quote handling:** the guide renders the Nate 26:20/26:29 quote as a compressed pair without ellipsis. The script should use the ellipsis honestly to signal compression, OR use the longer verbatim version.

The `intent/03_beyond-intent.md` doc is the structural backbone for Section 4's pivot — it names the seven unmapped patterns. Section 4 SHOULD NOT walk through all seven (that's Episode 6's job). It should name the SHAPE of what the framework leaves out and point at the rest of the series.

---

## Section 3 — Michael's lived examples (the four ceilings)

For each discipline, one moment where it was the right answer + one moment where it ran out. These are claims about practice — every one calibrated against chat-history evidence (per the `voice-michael` skill).

| Discipline | When it was the right answer | When it ran out (the ceiling) |
|---|---|---|
| **Prompt craft** | Directing a study agent with binding question + scratch file + constraints — the study lands on the first attempt because the prompt was precise. | A perfect prompt against a model that has no context of your prior work produces fluent generic output. Prompt craft can't substitute for the model knowing your codebase. |
| **Context engineering** | The full stack of `.mind/`, `.spec/`, `.claude/skills/`, `.github/skills/`, CLAUDE.md, agent files, six MCP servers. The model arrives knowing who Michael is, what the project values, what tools to reach for. | Context can load and the agent still picks the wrong tradeoff when no purpose tells it what matters more than what. The model knows everything and still goes the wrong direction. |
| **Intent engineering** | `intent.yaml` and `.spec/covenant.yaml` — encoded purpose, values hierarchy, bilateral commitments. Studies that the framework would have shipped fast got slowed for source verification because intent says depth > breadth. | Even with purpose named, an autonomous agent loop can still drift in a long-running task. Intent shapes choice; it doesn't fix the runaway. (The bacteriopolis substrate runaway is a concrete instance — intent was named, the agent still went for ten hours and $5+ before the emergency stop.) |
| **Spec engineering** | The pg-ai-stewards substrate proposals — phase docs, decision matrices (D-PE1, D-PE2...), ratify-then-execute cycle. Specs precise enough that ~95 commits across the ES arc shipped with zero rollbacks. | Even with a precise spec, the agent works autonomously for hours and you come back to a 20-minute task that took three hours because nothing was *watching* the elements obey. Spec without watching = bacteriopolis. |

The last row is where Section 4's pivot lives. The watching pattern (Abraham 4:18) is what the four disciplines don't provide. Episode 4 walks it specifically — *"watched until they obeyed."*

---

## Section 4 — The pattern underneath (draft logic)

The line Episode 1 ended on: *"Living inside the new work showed me something the disciplines don't quite reach."* Episode 2's section 4 starts naming what.

The shared assumption all four disciplines make: **the work is to organize**. Prompt craft organizes a single interaction. Context engineering organizes the model's information environment. Intent engineering organizes purpose and values. Spec engineering organizes the blueprint an agent will execute against.

D&C 88:119 names what they all do:

> "Organize yourselves; prepare every needful thing; and establish a house..."

The list that follows in v119 — *"a house of prayer, a house of fasting, a house of faith, a house of learning, a house of glory, a house of order, a house of God"* — is what gets built. The disciplines, all four of them, *are organizing*. They're the *organize yourselves* step.

But D&C 88:119 doesn't stop at *organize*. It says "prepare every needful thing" — and the "needful things" the framework leaves for the work itself are the bilateral covenant (Step 2 in the eleven-step cycle), the stewardship (Step 3), the line-upon-line learning (Step 5), the watching until they obey (Step 7 — Abraham 4:18), the atonement / error recovery (Step 8), the sabbath (Step 9), the consecration (Step 10), the zion alignment (Step 11). Seven needful things the four disciplines don't have language for yet.

This is the pivot. Episode 2 names the shape (organize → seven other things needed). Episodes 3–11 walk each thing.

**Important:** Section 4 should NOT list all seven. It should name that they exist and point forward. The full enumeration is Episode 6's job. Section 4's last line should make the listener want Episode 3.

---

## Ben Test pre-check — claim calibration

Every claim about practice calibrated per the Ben Test skill.

| Claim | Calibration | How it lands in the script |
|---|---|---|
| "I work prompt craft well" | Practiced | Concrete example — directing study agents — proves it |
| "I have context engineering infrastructure" | Practiced | Visible in `.mind/`, `.spec/`, `.claude/`, `.github/`, MCP servers — point to it |
| "I have intent engineering" | Practiced | `intent.yaml` and `.spec/covenant.yaml` exist; cite by name |
| "I have spec engineering" | Practiced | pg-ai-stewards substrate phase docs are the evidence |
| "The four disciplines together don't solve the watching problem" | Practiced — bacteriopolis runaway is the proof | Name the incident honestly (cost, scope, what failed) — it's the failure beat |
| "The seven unmapped steps fill what the four disciplines leave" | Aspirational at scale, practiced in this project | Frame as "this is what's emerged here" not "this is the answer for everyone" |

**Things to NOT claim:**
- That the four disciplines are insufficient *in general*. They might be sufficient for many use cases. The claim is they don't reach as far as the *work itself* requires for what *we're trying to do*.
- That we've solved the seven unmapped steps. We've named them. We're walking them. That's all.
- That bacteriopolis was an indictment of any specific discipline. It was a runaway. The lesson is that organize-without-watch is incomplete.

---

## Voice — what to keep out (per `voice-michael` skill + `voice-analysis-ai-vs-michael.md`)

Cut list — presenter tics that would make the script sound like a YouTube hustle video:
- "Let that land"
- "Sit with that"
- "Here's the thing"
- "This matters because"
- "Read that again"
- "That's not nothing"
- "stops me cold"

"It's not X — it's Y" pivots: hunt them ruthlessly. Episode 1 took three passes to clear; aim for zero on draft 1.

**Em-dash budget:** one per spoken paragraph max.

**Therefore/but causation**, not "and then" sequence.

**Don't narrate the script's own structure.** No "in this episode I'm going to" or "the next thing I want to tell you" or "what's coming next." Just say the thing.

**Partnership voicing (when AI is the subject):** no anger, no "fighting the model," collaborative pronouns where collaboration is described. Failure modes are real (tools breaking, session limits, the bacteriopolis runaway) but they're not framed as Michael yelling at the model. Reference: `feedback_michael_voice_kindness.md` + `.claude/skills/voice-michael/SKILL.md`.

---

## Failure to include (per teaching covenant — `failures-included`)

Two real failure beats:

1. **The prompt-craft ceiling moment** — a great prompt that produced fluent generic output because the model had no project context. Not a flaw of the prompt; a sign that context was the next altitude.
2. **The bacteriopolis substrate runaway** — intent was named, spec was written, ten hours and ~$5 spent before the emergency stop. Not because any single discipline failed; because the four don't include *watching*. The proof that the four disciplines, however well practiced, leave the watching for the work itself.

If the script reads as four-disciplines-are-sufficient or as four-disciplines-are-broken, both are wrong. The truth is they're necessary, well-defined, and finite — they cover what they cover, and beyond that it's the work itself.

---

## Discovery check (per `discovery_not_performance`)

Am I still learning while preparing this? Yes — the D&C 88:119 "organize yourselves / prepare every needful thing" reading clicked while writing this scratch. The disciplines aren't just teaching one part of a larger cycle — they're explicitly the "organize" half of D&C 88:119, and the "needful things" verse goes on to list are what come after. The phrase "house of order" reads differently after this — the four disciplines are how you become a house of order. The other "houses" (prayer, fasting, faith, learning, glory, God) are different work.

---

## Visual plan

Per the dual-audience constraint, visuals work for engineers AND for LDS viewers without watering down either.

| Beat | Visual |
|---|---|
| Title card | "Episode 2: The Four Disciplines" — LCARS typography |
| Section 1 — altitude diagram | Four horizontal bands: street (prompt) / aerial (context) / orbital (intent) / architectural (spec). Animate the stakes-scaling line |
| Section 2 prompt craft | Quote card — Nate "table stakes / typing with 10 fingers" |
| Section 2 context engineering | The 99.98% / 0.02% visual — your prompt as a tiny slice |
| Section 2 intent engineering | Quote card — Paweł "instructions run out" + Klarna walk-back graphic |
| Section 2 spec engineering | Quote card — Nate "verbal fluency vs completeness of thinking" |
| Section 3 — Michael's stack | Screen capture: `.mind/`, `.spec/`, `.claude/skills/`, `.github/skills/` directory tree |
| Section 3 — bacteriopolis runaway | Brief terminal/log shot with cost ticker; don't dwell |
| Section 4 — D&C 88:119 | Scripture card |
| Section 4 — the seven unmapped | Eight-step diagram: organize highlighted; seven others greyed out as forward placeholders |
| Closing | Episode 3 teaser card |

B-roll candidates: scrolling agent files, the substrate dashboard, a long-running task in flight, the workspace tree.

---

## Companion page on cpuchip.net (not part of this script — separate next step)

After draft 6 ships: `projects/cpuchip.net/content/presentations/02-the-four-disciplines.md`. The Episode 1 page used one bespoke component (`ValueShiftScarcity`); Episode 2 could use a companion: maybe `FourAltitudes` (animated altitude diagram) or `OrganizeAndBeyond` (D&C 88:119 organize + seven greyed forward steps). TBD when the script is ratified.
