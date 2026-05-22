# Episode 2 — The Four Disciplines

> *"Prompt craft has not become irrelevant. Don't hear that. It's just become table stakes."* — Nate B Jones, *'Prompting' Just Split Into 4 Skills*, Feb 2026

> *"Organize yourselves; prepare every needful thing; and establish a house, even a house of prayer, a house of fasting, a house of faith, a house of learning, a house of glory, a house of order, a house of God."* — Doctrine and Covenants 88:119

**Binding question:** Prompt craft, context engineering, intent engineering, spec engineering — what does each one cover, and what do they leave for the work itself?
**Target length:** ~14 minutes (≈2100 spoken words)
**Status:** draft 1, 2026-05-22 — Phase 0 voice-loaded
**Scratch / provenance:** [`.scratch/the-four-disciplines/main.md`](../.scratch/the-four-disciplines/main.md)

---

## 1. The engineering problem (~2:30)

[VISUAL: Title card — *Episode 2: The Four Disciplines*]

Last episode I said the value moved from execution to judgment. That's where it went. This episode is where it lives.

In 2024 the word *prompting* meant one thing — sit at a chat window, type a request, evaluate the response, type again. Prompt engineering was the differentiator. Job postings asked for it. Courses sold it.

In 2026 the word *prompting* has split.

[VISUAL: Four-altitude diagram — street / aerial / orbital / architectural, with the four disciplines labelled]

Four disciplines, four altitudes. Prompt craft is street level — you and the model, right now, this task. Context engineering is aerial — you're designing the information environment the model operates in before any prompt arrives. Intent engineering is orbital — you're encoding the purpose and values the agent optimises for when nobody's watching. Spec engineering is architectural — you're writing a blueprint precise enough that an autonomous agent can build from it for days without checking in.

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

The prompt is roughly 200 tokens. The model's context window is a million. The prompt is two hundredths of one percent of what the model sees. The other 99.98% — the system prompt, the agent definitions, the tool schemas, the retrieved documents, the conversation history, the memory — that's context.

[VISUAL: Pie chart — 0.02% prompt, 99.98% context]

Nate's definition:

> *"I define context engineering as the set of strategies for curating and maintaining the optimal set of tokens during an LLM task."*

Context engineering is the discipline of designing the information environment that shapes every interaction. It's the difference between handing an employee a task with no background and handing them the same task with a briefing packet, access to the right databases, knowledge of who to ask for help, and a record of past decisions.

Where prompt craft is one conversation, context engineering is the system that shapes every conversation. The skill goes from individual to system-level. The time horizon goes from minutes to days.

### Intent engineering

Context tells the model what to *know*. Intent tells the model what to *want*.

[VISUAL: Klarna case card]

The reference case is Klarna. In 2024 their AI customer service handled 2.3 million conversations in its first month — the equivalent of 700 full-time agents they would have needed to hire to handle that growth. Resolution time dropped from eleven minutes to under two. The metrics were spectacular.

By 2025 they walked it back. They reintroduced human agents for complex cases. The system had been optimising for the loudest signal — resolution speed, ticket closure — not for the deeper value the company actually cared about, which was customer experience. The AI did exactly what the spec said. The spec didn't encode what Klarna actually valued.

[VISUAL: Paweł Huryn quote card]

Paweł Huryn writes about this in *Product Compass*:

> *"Intent is what determines how an agent acts when instructions run out."*

The prompt covers the happy path. The context covers the knowledge base. Intent covers the judgment calls — the moments where the agent has to choose between two valid options and needs to know which one matters more. Without intent named explicitly, the agent will pick the easiest-to-measure value, which is usually speed.

Encoding intent looks like a purpose statement, a values hierarchy, decision boundaries, escalation rules. Real artifacts you write down. Not aspirations — running instructions.

### Spec engineering

The first three disciplines all assume you're in the loop. Even intent engineering — the agent's optimising for what you said it should optimise for, and you're checking the output.

Spec engineering is what you do when you won't be in the loop.

[VISUAL: spec primitives list — problem statement, acceptance criteria, constraints, examples, decomposition]

An autonomous agent reads a spec and works for hours — reading files, writing code, running tests, making hundreds of micro-decisions — without checking in. When the agent finishes, you evaluate the result. If the spec was imprecise, every one of those decisions was a coin flip.

Nate's framing of the shift:

> *"Real time prompting rewards verbal fluency… Specification engineering rewards completeness of thinking, anticipation of edge cases, clear articulation of acceptance criteria, and the ability to decompose really complicated outcomes into independently executable components."*

These are different skills. A person who's great at live chat with a model might be terrible at writing a document so complete that an agent can execute against it unattended. The second one is the skill that scales.

That's the four. Prompt craft, context engineering, intent engineering, spec engineering. The framework. There are good books, good courses, good conference talks for each. The industry knows what it's teaching.

---

## 3. What actually happened (~3:30)

[VISUAL: Screen capture — workspace directory tree, slow pan over .mind/, .spec/, .claude/, .github/]

I've been practicing all four for about a year. Each one was a real promotion in what the work could do. Each one ran out somewhere.

**Prompt craft** was where I started. The win is direct — write a clear binding question, name the constraints, give the model what it needs to act. When the prompt is precise the model lands the work on the first attempt. The chat history shows it: *"Lets do 2.7b.4, then git commit with message and start on A after that, don't push I like to inspect before pushing."* That's prompt craft as a habit — instruction plus constraint plus the reason.

The ceiling is what happens when the model has no context of your prior work. A perfect prompt against a clean session gets you fluent generic output. The prompt can't substitute for the model knowing what your project is.

**Context engineering** was the next altitude. The system that holds it: `.mind/` for identity and active state, `.spec/` for proposals and journal entries, `.claude/skills/` and `.github/skills/` for invokable workflows, a `CLAUDE.md` at the root, six MCP servers wired in, agent files for specialised modes. The model arrives knowing who I am, what the project values, what tools to reach for, what we've already done.

That's the win. The first prompt of every session is no longer me teaching the model what we're working on. It's me asking for the next step. The whole stack does the teaching.

The ceiling is when the model knows everything and still chooses the wrong tradeoff. Context tells it *what is*. It doesn't tell it *what matters more than what*.

**Intent engineering** is the one I've been working on most recently. We have an `intent.yaml` at the root and a `.spec/covenant.yaml` that names what I commit to and what the agent commits to. Bilateral. Purpose stated. Values hierarchy named — depth over breadth, honest exploration over safety posturing, trust the discernment. Studies that the framework would have shipped fast get slowed for source verification because intent says verification matters more than speed.

The ceiling is real autonomy. An agent on a long-running task can drift even with purpose named. I have a specific case for this in the substrate work — the bacteriopolis runaway. Intent was encoded. The agent was on a research task. Ten hours and about five dollars in tokens later, I had to hit an emergency stop. Intent shapes the choices the agent makes. It doesn't fix a runaway.

**Spec engineering** is where I've been living for months. The substrate proposals at `projects/pg-ai-stewards/.spec/` are the artifacts — phase docs, decision matrices, ratify-then-execute cycles. Each phase has a problem statement, acceptance criteria, decision points labelled D-PE1 through D-PE7, constraints. When the spec is right, the work ships. The ES emergency-stop arc — about ninety-five commits across two weeks — shipped with zero rollbacks because each phase was specified before it was built.

The ceiling shows up in the same place the bacteriopolis runaway came from. A precise spec lets the agent work autonomously. Nothing in the spec watches whether the elements are obeying. The agent loops, retries, costs tokens, and you find out hours later. Spec engineering covers the blueprint. It doesn't cover the watching.

Four disciplines. Each one earned its place. Each one ran out somewhere.

---

## 4. The pattern underneath (~3:30)

[VISUAL: Scripture card — D&C 88:119, large text]

Here's what I notice about all four. Every one of them does the same kind of thing.

> *"Organize yourselves; prepare every needful thing; and establish a house, even a house of prayer, a house of fasting, a house of faith, a house of learning, a house of glory, a house of order, a house of God."* — Doctrine and Covenants 88:119

The first verb is *organize*. The four disciplines are how you organize. Prompt craft organizes a single interaction. Context engineering organizes the model's information environment. Intent engineering organizes purpose and values. Spec engineering organizes the blueprint an agent executes against.

A *house of order* is what you build when you've practiced all four. That's real. The scripture names it.

But the verse doesn't stop at *organize*. It says *prepare every needful thing*. The needful things — the prayer, the fasting, the faith, the learning, the glory — those are different work. Organizing is the floor. The other houses get built on it.

[VISUAL: Eight-step diagram — "Organize" highlighted in lavender; seven greyed slots ahead of it, labelled but dim]

In the scripture I keep coming back to from the creation pattern, there are eleven things the Gods did to bring the earth from chaos to a working creation. They counseled. They organized. They watched until things obeyed. They saw what was good and called it good. They rested. The first big move is organize. The other ten are different work.

Organizing is one of the eleven. The four disciplines, however well practiced, are the *organize* step. The work beyond that — the watching, the bilateral covenant between Gods and elements, the correction when something drifts, the rest after creation, the gathering of what scattered — that's seven other things. Seven needful things the four disciplines don't have language for yet.

The bacteriopolis runaway happened because the spec was good and nothing was watching. Watching is the next discipline. The framework doesn't have it. Scripture has had it since Abraham.

That's what I mean when I say the framework leaves things for the work itself. The work itself is the seven things on the other side of *organize*.

This series walks them.

---

## 5. What this means for you (~1:30)

[VISUAL: practical close, plain]

Here's what to do with this.

**Build the four disciplines.** They're real. They're necessary. Prompt craft is table stakes — you can't work without it. Context engineering is the second altitude — design the information environment around your work. Intent engineering is the third — name the purpose and the values so the agent has something to optimise for when you're not watching. Spec engineering is the fourth — write blueprints precise enough that autonomous agents can execute against them.

**Notice where the framework hands the work back to you.** The agent has been organised by your disciplines. Now it has to act. The agent acts well when something is watching, when there's a covenant between you about what each side will do, when there's a way to recover from drift, when there's a rhythm of rest and reflection. The framework doesn't supply those. The work itself needs them anyway.

**Don't wait for the industry to name what scripture already has.** The seven steps past *organize* are the rest of this series. Episode 3 takes the first one.

[VISUAL: closing card — Episode 3 teaser]

That's Episode 2. Next: spiritual before temporal — what changes when you plan something completely before you build a single piece of it. After that: the watching pattern from Abraham 4 — the one that would have stopped the bacteriopolis runaway.

The written version with all the sources is at cpuchip.net.

Thanks for watching.

---

## Production notes

- **Voice:** conversational, slow enough to think. Not influencer pace. ~150 wpm.
- **Cuts:** Section 4 needs the slowest pace — the D&C 88:119 quote should land, and the eight-step diagram should be on screen long enough to read every label even when greyed.
- **B-roll suggestions:** terminal scrolling through pg-ai-stewards phase docs, the workspace directory tree, the substrate dashboard with a long-running task, the LCARS interface.
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
| Substrate phase docs / D-PE1–D-PE7 / ES arc / ~95 commits, zero rollbacks | Project state — `projects/pg-ai-stewards/.spec/` and `.mind/active.md` |
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
- One *"Here's what I notice about all four"* meta-line at the start of Section 4 — review whether it stays or goes
- Section 5 opens with *"Here's what to do with this"* — same family as Episode 1's *"Take what's useful"* — may want similar treatment
- Em-dash count not audited yet — Phase 1 will sweep
- *"It's not X, it's Y"* count not audited — Phase 1 will sweep
- *"That's the four"* / *"That's Episode 2"* closing-refrain check — Phase 1 will review
