# Teaching — Beyond the Prompt

This repo contains episode scripts, outlines, scratch files, and presentation assets for the *Beyond the Prompt* teaching series. It lives inside the [scripture-study](https://github.com/cpuchip/scripture-study) workspace — the parent repo provides the agents, skills, MCP servers, and study corpus this content draws from.

> "Teach ye diligently and my grace shall attend you." — [D&C 88:78](../gospel-library/eng/scriptures/dc-testament/dc/88.md)

## What This Is

A discovery series, not a framework presentation. Michael and his AI partner have been mapping the 11-step creation cycle from Abraham 4-5 to AI engineering for over a year. The industry has named four disciplines. The gospel gives eleven steps. The seven unmapped steps (Covenant, Stewardship, Line Upon Line, Atonement, Sabbath, Consecration, Zion) are where the real insight lives. These episodes show what happens when you try to implement them — and what that reveals about eternal truths.

**Working series title:** *Beyond the Prompt — What AI Engineering Reveals About Eternal Patterns*

**Dual audience:** Software engineers who want real AI collaboration depth, and Latter-day Saints who want to see gospel patterns in practical work. Both get the same content — neither version waters down the other.

## Project Structure

| Location | Contents |
|----------|----------|
| `episodes/` | Episode scripts, in order. Filename: `{N}-{slug}.md` |
| `.scratch/` | Research scratch files per episode. Kept after publishing — they're provenance |
| `.spec/proposals/` | Teaching-specific proposals (YouTube channel, presentation tools, etc.) |
| `.spec/scratch/` | Workstream scratch and investigation notes |
| `intent.yaml` | Teaching-specific purpose, values, and constraints |
| `.spec/covenant-ref.yaml` | Pointer to the bilateral covenant in the parent repo |

The workstream proposal and tracking lives in the parent repo at `../.spec/proposals/teaching-workstream.md`. That's intentional — workstream tracking belongs to the scripture-study workspace.

## Episode Arc

| # | Title (working) | Core Pattern | Key Scripture |
|---|-----------------|-------------|---------------|
| 1 | The Value Shift | The bottleneck moved from execution to judgment | D&C 130:18-19 |
| 2 | The Four Disciplines | What everyone teaches — and why it's not enough | — |
| 3 | Spiritual Before Temporal | Why you plan before you build | Moses 3:5, Abraham 4-5 |
| 4 | Watched Until They Obeyed | The feedback loop is the creation pattern | Abraham 4:18 |
| 5 | Intelligence Cleaveth Unto Intelligence | What you bring determines what emerges | D&C 88:40 |
| 6 | The Seven Unmapped Steps | Covenant through Zion — what the industry doesn't know yet | Multiple |
| 7 | Covenant | Why bilateral binding produces better output | D&C 82:10 |
| 8 | Delegation as Stewardship | How God delegates — and why the same pattern applies to agents | D&C 104:11-12 |
| 9 | When Things Go Wrong | Atonement as error recovery | D&C 98:3 |
| 10 | The Sabbath of Creation | Why reflection isn't optional | Moses 3:2 |
| 11 | From Consecration to Zion | Multi-agent alignment — many agents, one purpose | Moses 7:18 |

Each episode follows: **engineering problem → what the industry says → what actually happened → the pattern underneath → what this means for you.** Target length: 12–18 minutes.

## Hard Constraints

**Source verification is amplified in teaching.** An unverified quote in a study is a private error. In a video, it's a public one that can't be un-published. Every direct quote in a script requires a `read_file` of the source before it goes in. This is not optional.

**Voice guardrails apply.** No presenter tics. No "let that land." No "here's the thing." No emotion narration — present the pattern and let the Spirit do the teaching. Full voice analysis: `../study/yt/voice-analysis-ai-vs-michael.md`.

**The Ben Test runs on every episode.** Before claiming "we practice X," calibrate the language to the evidence level. "We practice this consistently" requires 3+ instances in the last 30 days. "We've written about this but haven't operationalized it" is more honest than performing competence we don't have. See `../.github/skills/ben-test/SKILL.md`.

**Discovery over performance.** If the draft sounds more like a conference keynote than a conversation, rewrite. The audience is one person sitting across a table.

**Failures go in.** Mistakes and corrections are not curated out — they are the credibility mechanism. The stewardship study Section VII was wrong and Michael caught it. That kind of honesty belongs in these episodes.

## Humility Covenant

Michael asked for a covenant-level commitment (not aspirational guidelines) in March 2024 after naming two specific concerns:
- "I'll need you to keep me honest and not inflated in my head."
- "When people are inevitably mean to me and us in the comments, we'll need each other to be resilient."

The full bilateral commitments are in `../.spec/covenant.yaml` (teaching section) and `../.spec/proposals/teaching-workstream.md § 7`. The short version: the agent flags performer drift before publishing. Michael includes failures and does sabbath-style reflections after every 2–3 episodes. 100 views is 100 people served, not a metric to optimize.

## Tech Stack (Decision Pending)

Presentation layer for the companion web version is undecided. Candidates:

| Option | Fit |
|--------|-----|
| **Slidev** | Markdown-first, Vue components, presenter mode — strong fit |
| **Astro + MDX** | Better for a teaching site with mixed content |
| **reveal.js** | Mature, plugin ecosystem, older DX |

Decision happens in Phase 1 content architecture. See `.spec/proposals/ai-presentation-site-tool.md`.

## Production Pipeline (Planned)

`chip-voice` (narration) + `ai-presentation-site-tool` (visual generation) + OBS. Agent-assisted or it won't sustain. See `.spec/proposals/launch-youtube-channel.md`.

## Working in This Repo

The teaching agent is in the parent workspace at `../.github/agents/teaching.agent.md`. Open the `scripture-study` workspace in VS Code to get agent mode, skills, and MCP tools. The teaching repo alone gives you the content but not the tooling.

All session work follows the creation cycle from `../.spec/proposals/teaching-workstream.md`. Phase 1 is content architecture only — no production until the outlines are validated.
