# Teaching

Interactive web-based teaching content for sharing what we're learning about human-AI collaboration through the lens of scripture. Not as experts — as practitioners showing their work.

## Workspace Requirement

This repo is designed to live **inside** the [scripture-study](https://github.com/cpuchip/scripture-study) workspace. The teaching agent, skills, copilot-instructions, and MCP servers all live in the parent repo. Without it, you get the content but not the tooling that produces it.

### Setup

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
| `scripture-study/.github/agents/teaching.agent.md` | Teaching agent | Agents need access to the full workspace — studies, skills, MCP servers |
| `scripture-study/.spec/covenant.yaml` (teaching section) | Teaching covenant | Bilateral commitments governing teaching work |
| `scripture-study/.spec/proposals/teaching-workstream.md` | Workstream proposal | Planning and architecture for the series |
| `teaching/intent.yaml` | Teaching intent | Purpose, values, and constraints specific to teaching |
| `teaching/.spec/` | Teaching-specific spec files | Covenant reference, scratch files, episode-level artifacts |
| `teaching/episodes/` | Episode scripts | The actual content (created as episodes are developed) |

## Intent

See [intent.yaml](intent.yaml) for the full document. The short version:

> Share what we're learning about human-AI collaboration through the lens of scripture — not as experts, but as practitioners showing their work.

### Core Values

- **Discovery over performance** — If we're not learning while we teach, we're performing
- **Audience over speaker** — Every script serves the viewer, not the presenter
- **Failures included** — Mistakes and corrections go in, not curated out
- **Calibrated claims** — We say what we practice, not what we've written about (the Ben Test)

## License

MIT
