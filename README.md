# Beyond the Prompt

> *"Teach ye diligently and my grace shall attend you."* — D&C 88:78

A YouTube series and companion web resource exploring what AI engineering reveals about eternal patterns. Not a framework presentation — a discovery story told in episodes, drawing from a year of lived work with the 11-step creation cycle from Abraham 4-5.

**Status: Phase 1 — Content Architecture (active)**

---

## The Series

The industry has named four disciplines of AI collaboration: prompt craft, context engineering, intent engineering, spec engineering. The gospel gives eleven steps. The seven unmapped steps — Covenant, Stewardship, Line Upon Line, Atonement, Sabbath, Consecration, Zion — are where the real insight lives. This series shows what happens when you try to implement them.

**Dual audience:** Software engineers who want real AI collaboration depth, and Latter-day Saints who want to see gospel patterns in practical work. Both get the same content — neither version waters down the other.

### Episode Arc

| # | Title | Core Pattern | Key Scripture | Status |
|---|-------|-------------|---------------|--------|
| 1 | **The Value Shift** | The bottleneck moved from execution to judgment | D&C 130:18-19 | planned |
| 2 | **The Four Disciplines** | What everyone teaches — and why it's not enough | — | planned |
| 3 | **Spiritual Before Temporal** | Why you plan before you build | Moses 3:5, Abraham 4-5 | planned |
| 4 | **Watched Until They Obeyed** | The feedback loop is the creation pattern | Abraham 4:18 | planned |
| 5 | **Intelligence Cleaveth Unto Intelligence** | What you bring determines what emerges | D&C 88:40 | planned |
| 6 | **The Seven Unmapped Steps** | Covenant through Zion — what the industry doesn't know yet | Multiple | planned |
| 7 | **Covenant** | Why bilateral binding produces better output | D&C 82:10 | planned |
| 8 | **Delegation as Stewardship** | How God delegates — and why the same pattern applies to agents | D&C 104:11-12 | planned |
| 9 | **When Things Go Wrong** | Atonement as error recovery | D&C 98:3 | planned |
| 10 | **The Sabbath of Creation** | Why reflection isn't optional | Moses 3:2 | planned |
| 11 | **From Consecration to Zion** | Multi-agent alignment — many agents, one purpose | Moses 7:18 | planned |

Each episode: **engineering problem → what the industry says → what actually happened → the pattern underneath → what this means for you.** Target length: 12–18 minutes.

---

## Workspace Setup

This repo is designed to live **inside** the [scripture-study](https://github.com/cpuchip/scripture-study) workspace. The teaching agent, skills, copilot-instructions, and MCP servers all live in the parent repo.

```bash
# 1. Clone the parent workspace
git clone https://github.com/cpuchip/scripture-study.git
cd scripture-study

# 2. Clone this repo into the workspace root
git clone https://github.com/cpuchip/teaching.git
```

The `.gitignore` in scripture-study already ignores the `teaching/` directory, so the two repos coexist without conflict.

### What Lives Where

| Location | What | Why |
|----------|------|-----|
| `scripture-study/.github/agents/teaching.agent.md` | Teaching agent | Agents need the full workspace — studies, skills, MCP servers |
| `scripture-study/.spec/proposals/teaching-workstream.md` | Workstream tracking | Workstream planning belongs to the scripture-study workspace |
| `teaching/intent.yaml` | Teaching intent | Purpose, values, and constraints specific to this work |
| `teaching/.spec/proposals/` | Teaching-specific proposals | YouTube channel, presentation tools, production pipeline |
| `teaching/.spec/scratch/` | Workstream scratch | Investigation and research notes |
| `teaching/episodes/` | Episode scripts | The actual content — created as episodes are developed |
| `teaching/.scratch/` | Episode provenance | Per-episode scratch files, kept after publishing |

---

## Hard Constraints

**Source verification is amplified in teaching.** An unverified quote in a study is a private error. In a video, it's a public one that can't be un-published. Every direct quote in a script requires a `read_file` of the source before it goes in.

**Voice guardrails.** No presenter tics. No "let that land." No emotion narration — present the pattern and let the Spirit do the teaching. Full analysis: `../study/yt/voice-analysis-ai-vs-michael.md`.

**The Ben Test runs on every episode.** Claims about our practice use calibrated language matching evidence levels. See `../.github/skills/ben-test/SKILL.md`.

**Failures go in.** Mistakes and corrections are not curated out — they are the credibility mechanism.

---

## Production Pipeline (Planned)

`chip-voice` (narration) + `ai-presentation-site-tool` (visual generation) + OBS. Agent-assisted or it won't sustain. See `.spec/proposals/launch-youtube-channel.md` and `.spec/proposals/ai-presentation-site-tool.md`.

---

## License

MIT
