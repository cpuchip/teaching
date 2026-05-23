# Episode 2 — The Four Disciplines

> *"Prompt craft has not become irrelevant. Don't hear that. It's just become table stakes."* — Nate B Jones, *'Prompting' Just Split Into 4 Skills*, Feb 2026

> *"Organize yourselves; prepare every needful thing; and establish a house, even a house of prayer, a house of fasting, a house of faith, a house of learning, a house of glory, a house of order, a house of God."* — Doctrine and Covenants 88:119

**Binding question:** Prompt craft, context engineering, intent engineering, spec engineering — what does each one cover, and what do they leave for the work itself?
**Target length:** ~14 minutes (≈2100 spoken words)
**Status:** draft 2, 2026-05-23 — Phase 1 voice sweep
**Scratch / provenance:** [`.scratch/the-four-disciplines/main.md`](../.scratch/the-four-disciplines/main.md)

---

## 1. The engineering problem (~2:30)

[VISUAL: Title card — *Episode 2: The Four Disciplines*]

Last episode I said the value moved from execution to judgment. That's where it went. This episode is where it lives.

In 2024 the word *prompting* meant one thing — sit at a chat window, type a request, evaluate the response, type again. Prompt engineering was the differentiator. Job postings asked for it. Courses sold it.

In 2026 the word *prompting* has split.

[VISUAL: Four-altitude diagram — street / aerial / orbital / architectural, with the four disciplines labelled]

Four disciplines, four altitudes. Prompt craft is street level. You and the model, right now, this task. Context engineering is aerial. You're designing the information environment the model operates in before any prompt arrives. Intent engineering is orbital. You're encoding the purpose and values the agent optimises for when nobody's watching. Spec engineering is architectural. You're writing a blueprint precise enough that an autonomous agent can build from it for days without checking in.

Nate B Jones laid this out in February. He framed the stakes plainly:

> *"When you as an individual sit down and you screw up a prompt, it might waste your morning at worst. When you as a human being sit down and screw up context engineering or intent engineering, you are screwing up for the entire team, your entire org, your entire company."*

The stakes scale with the altitude. The altitude scales with how much of the work happens without you in the loop. By the time you're at spec engineering, the agent is acting on its own for hours.

If you know one of the four, you can do the work of one person. If you know all four, the work changes shape — you're orchestrating, not typing.

---

## 2. What the industry says (~5:00)

[VISUAL: Subtle shift — quieter, conversational frame]

### Prompt craft

This is the one everyone teaches. Write a clear request. State what you want, not what you don't want. Give context before the task. Provide examples. Specify the output format.

[VISUAL: Nate B Jones quote card — "table stakes" line]

Nate again:

> *"Prompt craft has not become irrelevant. Don't hear that. It's just become table stakes. It's sort of the way knowing how to type with 10 fingers was once a professional differentiator and now it's just table stakes."*

Table stakes. Prerequisite. You can't build the other three on top of bad prompt craft, the same way you can't write a novel if you can't write a sentence. Anthropic's golden rule for prompt craft is the test — show your prompt to a colleague. If they would be confused about what to do, the model will be too. Most bad AI output is accurate AI execution of an ambiguous prompt.

Prompt craft is synchronous, session-based, individual. Your skill, your prompt, this conversation.

### Context engineering

The prompt is roughly 200 tokens. The model's context window is a million. The prompt is two hundredths of one percent of what the model sees. The other 99.98% is context: the system prompt, the agent definitions, the tool schemas, the retrieved documents, the conversation history, the memory.

[VISUAL: Pie chart — 0.02% prompt, 99.98% context]

Nate's definition:

> *"I define context engineering as the set of strategies for curating and maintaining the optimal set of tokens during an LLM task."*

Context engineering is the discipline of designing the information environment that shapes every interaction. It's the difference between handing an employee a task with no background and handing them the same task with a briefing packet, access to the right databases, knowledge of who to ask for help, and a record of past decisions.

Where prompt craft is one conversation, context engineering is the system that shapes every conversation. The skill goes from individual to system-level. The time horizon goes from minutes to days.

### Intent engineering

Context tells the model what to *know*. Intent tells the model what to *want*.

[VISUAL: Klarna case card]

The reference case is Klarna. In 2024 their AI customer service handled 2.3 million conversations in its first month — the equivalent of 700 full-time agents they would have needed to hire to handle that growth. Resolution time dropped from eleven minutes to under two. The metrics were spectacular.

By 2025 they walked it back. They reintroduced human agents for complex cases. The system had been optimising for the loudest signal (resolution speed, ticket closure), not for the deeper value the company actually cared about, which was customer experience. The AI did exactly what the spec said. The spec didn't encode what Klarna actually valued.

[VISUAL: Paweł Huryn quote card]

Paweł Huryn writes about this in *Product Compass*:

> *"Intent is what determines how an agent acts when instructions run out."*

The prompt covers the happy path. The context covers the knowledge base. Intent covers the judgment calls — the moments where the agent has to choose between two valid options and needs to know which one matters more. Without intent named explicitly, the agent will pick the easiest-to-measure value, which is usually speed.

Encoding intent looks like a purpose statement, a values hierarchy, decision boundaries, escalation rules. Real artifacts you write down. Running instructions.

### Spec engineering

The first three disciplines all assume you're in the loop. Even intent engineering — the agent's optimising for what you said it should optimise for, and you're checking the output.

Spec engineering is what you do when you won't be in the loop.

[VISUAL: spec primitives list — problem statement, acceptance criteria, constraints, examples, decomposition]

An autonomous agent reads a spec and works for hours, reading files, writing code, running tests, making hundreds of micro-decisions, without checking in. When the agent finishes, you evaluate the result. If the spec was imprecise, every one of those decisions was a coin flip.

Nate's framing of the shift:

> *"Real time prompting rewards verbal fluency… Specification engineering rewards completeness of thinking, anticipation of edge cases, clear articulation of acceptance criteria, and the ability to decompose really complicated outcomes into independently executable components."*

These are different skills. A person who's great at live chat with a model might be terrible at writing a document so complete that an agent can execute against it unattended. The second one is the skill that scales.

That's the four. Prompt craft, context engineering, intent engineering, spec engineering. The framework. There are good books, good courses, good conference talks for each. The industry knows what it's teaching.

---

## 3. What actually happened (~3:30)

[VISUAL: Screen capture — workspace directory tree, slow pan over .mind/, .spec/, .claude/, .github/]

I've been practicing all four for about a year. Each one was a real promotion in what the work could do. Each one ran out somewhere.

**Prompt craft** was where I started. The win is direct: write a clear binding question, name the constraints, give the model what it needs to act. When the prompt is precise the model lands the work on the first attempt. The chat history shows it: *"Lets default to true for this, it's the point of the experiment, but I appreciate you asking. it's the kind of setting that costs money and I'll like the say on that."* That's prompt craft as a habit. Instruction plus constraint plus the reason.

The ceiling is what happens when the model has no context of your prior work. A perfect prompt against a clean session gets you fluent generic output. The prompt can't substitute for the model knowing what your project is.

**Context engineering** was the next altitude. The system that holds it: `.mind/` for identity and active state, `.spec/` for proposals and journal entries, `.claude/skills/` and `.github/skills/` for invokable workflows, a `CLAUDE.md` at the root, six MCP servers wired in, agent files for specialised modes. The model arrives knowing who I am, what the project values, what tools to reach for, what we've already done.

That's the win. The first prompt of every session is no longer me teaching the model what we're working on. It's me asking for the next step. The whole stack does the teaching.

The ceiling is when the model knows everything and still chooses the wrong tradeoff. Context tells it *what is*. It doesn't tell it *what matters more than what*.

**Intent engineering** is the one I've been working on most recently. We have an `intent.yaml` at the root and a `.spec/covenant.yaml` that names what I commit to and what the agent commits to. Bilateral. Purpose stated. Values hierarchy named — depth over breadth, honest exploration over safety posturing, trust the discernment. Studies that the framework would have shipped fast get slowed for source verification because intent says verification matters more than speed.

The ceiling is real autonomy. An agent on a long-running task can drift even with purpose named. The clearest example I have is from the stewards database — an experiment we've been building that tries to embody the eleven-step creation cycle as code. One night an agent there got stuck in a research loop on a topic called bacteriopolis. Intent was encoded. The agent's purpose was named. It ran for ten hours and burned about five dollars in tokens before I hit the emergency stop. Intent shapes the choices the agent makes. It doesn't fix a runaway.

**Spec engineering** is where I've been living for months. Same stewards database. The proposals at `projects/pg-ai-stewards/.spec/` are the artifacts: phase docs, decision matrices, ratify-then-execute cycles. Each phase has a problem statement, acceptance criteria, decision points labelled D-PE1 through D-PE7, constraints. When the spec is right, the work ships. The emergency-stop arc that fixed the bacteriopolis runaway shipped with zero rollbacks across about ninety-five commits and two weeks because each phase was specified before it was built.

The ceiling shows up in the same place the bacteriopolis runaway came from. A precise spec lets the agent work autonomously. Nothing in the spec watches whether the elements are obeying. The agent loops, retries, costs tokens, and you find out hours later. Spec engineering covers the blueprint. It doesn't cover the watching.

Four disciplines. Each one earned its place. Each one ran out somewhere.

---

## 4. The pattern underneath (~3:30)

[VISUAL: Scripture card — D&C 88:119, large text]

Something stands out about the four disciplines when I lay them next to scripture.

> *"Organize yourselves; prepare every needful thing; and establish a house, even a house of prayer, a house of fasting, a house of faith, a house of learning, a house of glory, a house of order, a house of God."* — Doctrine and Covenants 88:119

The first verb is *organize*. Each of the four disciplines is a different act of organizing. Intent organizes the *why*. Spec organizes the *blueprint*. Context organizes the *information environment*. Prompt organizes *this one interaction*. Four altitudes of the same verb.

A *house of order* is what you've built when all four are working. The scripture names that explicitly.

But D&C 88:119 doesn't stop at *organize*. It says *prepare every needful thing*. The needful things include verbs the framework hasn't named yet.

[VISUAL: 11-step cycle diagram — eleven steps arranged in a ring or row. Four highlighted in lavender (Intent, Spiritual Creation, Line upon Line, Physical Creation). Seven greyed but labelled (Covenant, Stewardship, Watching, Atonement, Sabbath, Consecration, Zion). Step names on each node.]

The creation pattern in Abraham 4 and 5 names eleven things the Gods did to bring the earth from chaos to a working world. Eleven steps. The four disciplines cover four of them. Intent engineering is the *Intent* step. Spec engineering is the *Spiritual Creation* step, the blueprint, before anything physical. Context engineering is the *Line Upon Line* step, building understanding in layers across many sessions. Prompt craft is the *Physical Creation* step, the actual interaction where the work happens.

Four down. Seven to go. And the seven aren't more organizing.

Covenant is *binding*. A mutual agreement between the agent and the person it works for, with commitments on both sides.

Stewardship is *entrusting*. Handing real authority to the agent and trusting its judgment within bounds.

Watching is *observing*. Abraham 4:18 — the Gods watched things until they obeyed.

Atonement is *recovering*. When something goes wrong, putting it back.

Sabbath is *resting*. Stopping, reflecting, naming what was good.

Consecration is *giving*. Sharing what was made.

Zion is *harmonizing*. Many agents working as one.

Seven verbs the framework doesn't have. Scripture has had all seven since Abraham.

The bacteriopolis runaway happened because the spec was right and nothing was watching. Watching is the seventh step in the cycle. The framework doesn't have it yet. Episode 4 walks it.

That's what I mean when I say the framework leaves things for the work itself. The work itself is seven verbs the four disciplines don't reach.

This series walks them.

---

## 5. What this means for you (~1:30)

[VISUAL: practical close, plain]

**Build the four disciplines.** They're real. They're necessary. Prompt craft is table stakes. You can't work without it. Context engineering is the second altitude. Design the information environment around your work. Intent engineering is the third. Name the purpose and the values so the agent has something to optimise for when you're not watching. Spec engineering is the fourth. Write blueprints precise enough that autonomous agents can execute against them.

**Notice where the framework hands the work back to you.** The agent has been organised by your disciplines. Now it has to act. The agent acts well when something is watching, when there's a covenant between you about what each side will do, when there's a way to recover from drift, when there's a rhythm of rest and reflection. The framework doesn't supply those. The work itself needs them anyway.

**Don't wait for the industry to name what scripture already has.** The seven steps the framework doesn't reach are the rest of this series. Episode 3 takes the first one.

[VISUAL: closing card — Episode 3 teaser]

That's Episode 2. Next: spiritual before temporal — what changes when you plan something completely before you build a single piece of it. After that: the watching pattern from Abraham 4 — the one that would have stopped the bacteriopolis runaway.

The written version with all the sources is at cpuchip.net.

Thanks for watching.

---

## Production notes

- **Voice:** conversational, slow enough to think. Not influencer pace. ~150 wpm.
- **Cuts:** Section 4 needs the slowest pace — the D&C 88:119 quote should land, and the eleven-step diagram should be on screen long enough to read every label even when greyed.
- **B-roll suggestions:** terminal scrolling through pg-ai-stewards phase docs, the workspace directory tree, the stewards database dashboard with a long-running task, the LCARS interface.
- **Captions / lower thirds:** every external quote and every scripture reference needs a citation card on screen.
- **Length check:** ~2100 words at 150 wpm ≈ 14:00. Tightest cut if it lands long: Section 2's spec engineering subsection can compress one paragraph; the Nate "verbal fluency vs completeness of thinking" quote is the keeper, the bridge text around it is the candidate for trim.

## Source verification — every claim in this script

| Claim / quote | Verified against |
|---|---|
| Nate B Jones — "table stakes" / "10 fingers" line | **Verified verbatim** at `yt/ai-news-strategy-daily-nate-b-jones/BpibZSMGtdY/transcript.md` lines [11:01–11:07]. Video [BpibZSMGtdY](https://www.youtube.com/watch?v=BpibZSMGtdY) published 2026-02-27, 41:11 runtime. |
| Nate B Jones — "screw up a prompt / waste your morning" stakes line | **Verified verbatim** same transcript [16:01–16:17] |
| Nate B Jones — context engineering definition | **Verified verbatim** same transcript [12:10] |
| Nate B Jones — "verbal fluency / completeness of thinking" | **Verified verbatim** same transcript [26:20] and [26:29]. Rendered with ellipsis in script — intermediate "It rewards quick iteration. It rewards a good eye for output quality." omitted between the two halves. |
| Paweł Huryn — "instructions run out" | **Verified verbatim** at [productcompass.pm](https://www.productcompass.pm/p/intent-engineering-framework-for-ai-agents) via WebFetch 2026-05-22. Article: *"The Intent Engineering Framework for AI Agents,"* 2026-01-13. |
| Klarna 2.3M conversations / 700 FT agent equivalent | **Verified** via WebSearch 2026-05-22 across [OpenAI case study](https://openai.com/index/klarna/) + [Klarna press](https://www.klarna.com/international/press/klarna-ai-assistant-handles-two-thirds-of-customer-service-chats-in-its-first-month/). First month, early 2024. 700 = agents avoided-hiring, not displaced. |
| Klarna walk-back in 2025 | **Verified** same sources. Reintroduced human agents for complex cases. |
| D&C 88:119 | **Verified verbatim** `gospel-library/eng/scriptures/dc-testament/dc/88.md:247` |
| Abraham creation pattern (counsel, organize, watch until they obeyed) | Workspace reference — Abraham 4-5 (will read in full for Phase 5 fact-check). Episode 1 already verified Abraham 4:18 verbatim. |
| Anthropic "show your prompt to a colleague" golden rule | Cited from `docs/work-with-ai/guide/01_prompt-craft.md` which sources [Anthropic's Claude Prompting Best Practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) — verify verbatim in Phase 5. |
| Michael's stack — .mind/, .spec/, .claude/, .github/, MCP servers, agent files | Project state — visible in workspace |
| Stewards database phase docs / D-PE1–D-PE7 / emergency-stop arc / ~95 commits, zero rollbacks | Project state — `projects/pg-ai-stewards/.spec/` and `.mind/active.md` |
| Four disciplines mapping to steps 1, 4, 5, 6 of the eleven-step creation cycle | Derived 2026-05-22 from `teaching-workstream.md` §5 episode map + `docs/work-with-ai/intent/03_beyond-intent.md` (the seven unmapped) + `docs/work-with-ai/guide/00_foundation.md` (the four altitudes). Intent ↔ Step 1; Spec ↔ Step 4 (Spiritual Creation); Context ↔ Step 5 (Line Upon Line); Prompt ↔ Step 6 (Physical Creation). |
| Bacteriopolis runaway — ten hours, ~$5 | Project state — referenced in `.mind/active.md` and pg-ai-stewards memory files. Numbers approximate; will verify exact figures in Phase 5. |

## Ben Test calibration applied

Every claim about practice in this script is at the **practiced** evidence level, anchored to artifacts in the project (the `.mind/` tree, the substrate proposals, the chat history). The bacteriopolis runaway is included as the honest failure beat that earns the rest of the argument — that the four disciplines, however well practiced, leave watching for the work itself.

The "this series walks the seven other things" framing is **aspirational at scale** but **practiced in this project** — we're walking them one episode at a time. The script doesn't claim the seven are the universal answer; it says they're what's emerged here, and the rest of the series shows the walk.

## Voice audit (draft 1 — what was loaded before drafting)

Loaded before writing:
- [`voice-michael` skill](../../.claude/skills/voice-michael/SKILL.md) — partnership pronouns, no anger, no adversarial framing
- [`feedback_michael_voice_kindness.md`](../../memory/feedback_michael_voice_kindness.md) — auto-memory pointer
- [`study/yt/voice-analysis-ai-vs-michael.md`](../../study/yt/voice-analysis-ai-vs-michael.md) — cut list
- [`script-refinement` skill](../../.claude/skills/script-refinement/SKILL.md) Phase 0 — source curation, voice-loaded first draft, verified quotes before drafting

Watch list for Phase 1 (voice rewrite) and Phase 2 (meta-narration sweep):
- Section 5 opens with *"Here's what to do with this"* — same family as Episode 1's *"Take what's useful"* — may want similar treatment
- Section 1 line 26 — the four-altitudes paragraph has four em-dashes in one paragraph; needs Phase 1 sweep (parallelism preserved by sentence reshape, not by dash removal alone)
- Section 5 first bullet — the *"Build the four disciplines"* bullet has four em-dashes in one paragraph for the same reason
- Section 4 has the *"Something stands out…"* opener — softer than Episode 1's caught-meta-narration patterns, but Phase 2 should look at it
- *"It's not X, it's Y"* count not audited — Phase 1 will sweep
- *"That's the four"* / *"That's Episode 2"* closing-refrain check — Phase 1 will review

Phase 0 drift sweep (2026-05-22, after the mapping + stewards rename):
- Section 5 closing bullet changed *"seven steps past organize"* → *"seven steps the framework doesn't reach"*. The 11-step order has Covenant (2) and Stewardship (3) BETWEEN Intent (1) and Spiritual Creation (4), so "past" was sequentially wrong; "doesn't reach" is precise.
- Production notes: *"eight-step diagram"* → *"eleven-step diagram"*, *"substrate dashboard"* → *"stewards database dashboard"*.
- Flagged for Michael's decision (not auto-fixed): Section 3 prompt-craft paragraph quotes Michael's actual chat phrase *"Lets do 2.7b.4, then git commit…"* — the verbatim chat history is great voice evidence, but *"2.7b.4"* is internal jargon a general audience won't decode. Options: keep as-is for authenticity (engineer audience will read it as project numbering), add a brief contextualizing aside, or replace with a different verbatim that's less jargon-dense. **RESOLVED 2026-05-23 (Phase 1): Michael picked option 3.** Substituted with the *"Lets default to true for this..."* verbatim — same instruction-plus-reason shape, no project numbering.

## Voice audit (draft 2 — Phase 1 voice rewrite, 2026-05-23)

Single-pass read of the whole script with only the voice cut-list, em-dash budget, and "It's not X, it's Y" pivot pattern in mind. Found and fixed:

**Em-dash budget — five paragraphs over budget, all rewritten:**

1. **§1 four-altitudes paragraph** — 4 em-dashes ("Prompt craft is street level — ... Context engineering is aerial — ... Intent engineering is orbital — ... Spec engineering is architectural — ..."). Reshaped to short declaratives: *"[discipline] is [altitude]. [explanation]."* Same rhythm, zero em-dashes.
2. **§2 context engineering 99.98% sentence** — 2 em-dashes used as parenthetical brackets around the layer list. Rewritten with colon + comma list: *"The other 99.98% is context: the system prompt, the agent definitions, ..."*
3. **§2 Klarna "loudest signal" sentence** — 2 em-dashes used as parenthetical brackets around *"resolution speed, ticket closure"*. Rewritten with parens.
4. **§2 spec engineering "reads a spec" sentence** — 2 em-dashes used as parenthetical brackets around the autonomous-work list. Rewritten with commas only.
5. **§5 "Build the four disciplines" bullet** — 4 em-dashes (one per discipline, same pattern as §1). Reshaped the same way: short declaratives.

**§3 prompt-craft em-dash cleanup** (folded into the 2.7b.4 substitution edit) — 2 em-dashes in the same paragraph as the substitution (*"The win is direct — write a clear..."* and *"That's prompt craft as a habit — instruction plus constraint plus the reason"*). Both converted: first to colon, second broken into its own sentence.

**Audit correction:** initial Phase 1 audit also listed a §5 "Stop measuring yourself by execution speed" bullet as needing parens — that's an Episode 1 bullet, not Episode 2. Confused the two scripts mid-audit. Episode 2's §5 has three bullets (*Build the four disciplines*, *Notice where the framework hands the work back*, *Don't wait for the industry to name what scripture already has*) and only the first had an em-dash issue. Corrected here for honesty; the false claim should not get to Phase 2 as a "fixed" item.

**"It's not X, it's Y" pivot — one caught:**

- **§2 intent engineering close**: *"Real artifacts you write down. Not aspirations — running instructions."* The *"Not aspirations — running instructions"* fragment is the pithy single-line pivot the voice analysis flags. Simplified to *"Running instructions."* as the punctuating fragment. The negation was redundant once the positive was direct.

**Cut list — one caught:**

- **§5 opener** *"Here's what to do with this."* — presenter-tic family. Cut entirely. The section header (*"What this means for you"*) already does the work; the first bullet's bold opener carries the section start.

**2.7b.4 jargon substitution — resolved:**

- Per Michael's option-3 pick, the *"Lets do 2.7b.4, then git commit with message..."* verbatim swapped for *"Lets default to true for this, it's the point of the experiment, but I appreciate you asking. it's the kind of setting that costs money and I'll like the say on that."* Same authenticity, no project numbering. (Em-dash cleanup in the same paragraph noted above.)

**Closing refrain check — none triggered:**

- *"Four disciplines. Each one earned its place. Each one ran out somewhere."* (§3 close) — bookend to §3's opener, not a series-wide refrain. Keep.
- *"This series walks them."* (§4 close) — declarative section close. Keep.
- *"That's Episode 2. Next: ..."* (§5 close) — direct teaser, same shape as Episode 1. Keep.

**Therefore/but / "and then" — none caught.** Transitions already flow on causation or contrast.

**Flagged for Phase 2 (meta-narration sweep):**
- §4 opener *"Something stands out about the four disciplines when I lay them next to scripture."* — softer than Episode 1's caught patterns but worth a look.
