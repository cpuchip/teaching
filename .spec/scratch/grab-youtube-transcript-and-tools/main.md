# Research: Grab YouTube Transcript and Tools

**Entry Category:** ideas
**Project:** YouTube / Content (teaching/)
**Captured:** 2026-04-23
**Tags:** hyperframes, video-processing, youtube

---

## What This Is About

[SYNTHESIS] An infrastructure idea for the *Beyond the Prompt* video pipeline: pull transcripts from YouTube videos (for inspiration / reference / re-cuts), then use **HyperFrames** (HTML→video) and/or **video-use** (Claude-Code-driven editor wrapping ffmpeg + ElevenLabs) to assemble episode visuals. Captured alongside an inspiration video at `https://youtu.be/Aw3BkmhYu4I` and a note that ffmpeg setup will be part of the work.

This sits inside the WS7 Teaching production-pipeline question: how does the "agent-assisted or it won't sustain" pipeline (`launch-youtube-channel.md`) actually get built?

---

## What Already Exists

### [WORKSPACE] Existing transcript tooling — `scripts/yt-mcp/`
A working Go MCP server already solves the "grab YouTube transcript" half of this idea. From `scripts/yt-mcp/README.md`:

- Wraps **yt-dlp** to download transcripts + metadata.
- Stores them as markdown under `{YT_DIR}/{channel}/{video_id}/`.
- Exposes `yt_download`, `yt_get`, `yt_list`, `yt_search` as MCP tools.
- Already registered as one of the project's MCP servers (per parent `README.md`: "yt-mcp").
- Has a `docs/01_TODO.md` (~22KB) with planned work (not read in this pass).

→ **The "grab YouTube transcript" tool is already built and in use.** The new value the entry adds is on the *render/edit* side, not the *fetch* side.

### [WORKSPACE] Pipeline proposals already on file (teaching/.spec/proposals/)
- **`launch-youtube-channel.md`** — explicitly names the production pipeline as `chip-voice + ai-presentation-site-tool + obs`, with the hard constraint "Production pipeline must be agent-assisted or it won't sustain." HyperFrames / video-use are candidate components for that pipeline.
- **`ai-presentation-site-tool.md`** — Phase 1 task is "Survey existing presentation generators (revealjs, slidev, etc.)". HyperFrames is HTML-native and could overlap with — or replace — part of that surface (presentation site vs. rendered video are adjacent surfaces).

### [WORKSPACE] Workstream context — `teaching/.spec/scratch/teaching-workstream/main.md`
30 source files in `docs/work-with-ai/` plus the 11-episode arc (in `teaching/README.md`). Whatever pipeline gets chosen has to render 12–18 minute episodes repeatably. The README's "Production Pipeline (Planned)" section names: `chip-voice (narration) + ai-presentation-site-tool (visual generation) + OBS`.

### [WORKSPACE] No existing references to the new tools
`grep -i "hyperframes|video-use|heygen|ffmpeg"` across the workspace returned no prior mentions outside `teaching/episodes/README.md`. This is a **new external reference** to the project — not a duplicate of prior research.

---

## External Context

### [WEB] HyperFrames — `github.com/heygen-com/hyperframes`
- **What it is:** Open-source video rendering framework. "Write HTML. Render video. Built for agents." Apache 2.0, npm package `hyperframes`.
- **Authors:** HeyGen (the AI avatar video company). Inspired by Remotion; the team used Remotion in production at HeyGen before building this.
- **Model:** Compositions are plain HTML files with data attributes (no React, no proprietary DSL). "Frame Adapter" pattern — bring your own animation runtime: GSAP, Lottie, CSS, Three.js.
- **Agent integration:** Ships a "skills" install (`npx skills add heygen-com/hyperframes`) that registers as `/hyperframes`, `/hyperframes-cli`, `/gsap` slash-commands in Claude Code, Cursor, Gemini CLI, Codex. Also exposes a Codex plugin manifest.
- **CLI:** `npx hyperframes init`, `preview` (live-reload browser preview), `render` (to MP4). Non-interactive by default — designed for agent-driven pipelines.
- **Requirements:** Node.js ≥ 22, **FFmpeg**.
- **Determinism claim:** "same input = identical output," targeted at automated pipelines.

### [WEB] video-use — `github.com/browser-use/video-use`
- **What it is:** A Claude-Code-driven video editor. "Drop raw footage in a folder, chat with Claude Code, get `final.mp4` back." Open source (from the browser-use team).
- **Model:** Skill that installs into `~/.claude/skills/video-use` (or `~/.codex/skills/`). Agent uses the skill + helper scripts to drive ffmpeg.
- **What it actually does:**
  - Cuts filler words (`umm`, `uh`, false starts) and dead space.
  - Auto color grades segments.
  - 30 ms audio fades on every cut.
  - Burns subtitles (default: 2-word UPPERCASE chunks).
  - Generates animation overlays via **Manim**, **Remotion**, or PIL — spawned as parallel sub-agents.
  - Self-evaluates rendered output at every cut boundary before showing it.
  - Persists session memory in `project.md`.
- **How it gives the LLM the video without watching it:**
  1. **Audio transcript** via ElevenLabs Scribe (word-level timestamps + speaker diarization + audio events). Packed into a ~12 KB `takes_packed.md`.
  2. **Visual composite (`timeline_view`)** — filmstrip + waveform + word labels PNG, called only at decision points.
  - Pitch: 30k frames × 1.5k tokens = 45M tokens of noise vs. 12 KB text + a few PNGs.
- **Deps:** `ffmpeg` (required), `yt-dlp` (optional, for online sources), **ElevenLabs API key** (paid — required for Scribe transcription).
- **Pipeline:** Transcribe → Pack → LLM reasons → EDL → Render → Self-Eval (max 3 fix-and-rerender iterations).

### [WEB] YouTube inspiration link
`https://youtu.be/Aw3BkmhYu4I` — couldn't extract a clean title from raw HTML in this pass. Worth a manual watch by Michael; that's the "why this caught my eye" artifact.

### [SYNTHESIS] How these two relate
- **HyperFrames** = render-from-scratch. You author a composition (HTML + animations) and render to MP4. Strong fit for *generated* visuals — title cards, scripture quotes with art, animated diagrams of the 11-step cycle.
- **video-use** = edit-existing-footage. You give it raw takes (e.g., Michael talking) and it produces a tightened cut with subtitles. Strong fit for *talking-head* episodes — which the WS7 pipeline currently hand-waves with "OBS."
- They are complementary, not competing. A possible pipeline shape: record talking head → video-use to tighten + subtitle → HyperFrames-rendered B-roll/overlays → final assembly.
- Both depend on FFmpeg. Both are designed for agent-driven workflows, which matches the hard constraint in `launch-youtube-channel.md`.

### [SYNTHESIS] Overlap with `ai-presentation-site-tool` proposal
That proposal scoped to revealjs/slidev/etc. — *web* presentations. HyperFrames produces *video*. If the teaching site and the YouTube episode share visual content (likely — same scripture quotes, same diagrams), there's a question about whether to:
- Author once in HTML and render to both web (via slidev/revealjs/Astro) and video (via HyperFrames), or
- Maintain two parallel artifacts.

This is a real architectural decision that touches both proposals.

---

## Open Questions

1. **Is `scripts/yt-mcp/` sufficient for the "grab transcript" need, or does this entry envision something more (e.g., bulk channel scraping, transcript-driven re-cuts)?** The fetch half looks already-solved.
2. **Talking-head vs. fully-generated episodes — which model does *Beyond the Prompt* use?** The README mentions OBS (talking head implied). If yes, video-use is more relevant than HyperFrames for the primary pipeline; HyperFrames becomes a B-roll/overlay tool.
3. **ElevenLabs API key — acceptable cost / dependency?** video-use requires it for Scribe transcription. yt-mcp already uses yt-dlp's auto-captions (free) — the project may not need ElevenLabs at all if transcription is the only blocker.
4. **Does HyperFrames replace, complement, or compete with the planned `ai-presentation-site-tool`?** Both want HTML-as-source-of-truth. Authoring once and rendering to both web + video is a different proposal than what's currently on file.
5. **FFmpeg install on Windows — already done, or part of this work?** Both tools require it. The entry mentions "get ffmpeg installed" as part of the play.
6. **License + provenance:** HyperFrames is Apache 2.0 (clean). video-use license not confirmed in this pass — should be checked before committing it to the pipeline.
7. **Determinism vs. liveness:** HyperFrames promises deterministic renders (good for re-builds). video-use has a self-eval loop with up to 3 retries (good for quality, less deterministic). What does *Beyond the Prompt* need on that axis?
8. **What did the YouTube inspiration video actually show?** Couldn't extract its title/content in this pass — Michael should confirm what specifically caught his eye so the right tool gets weighted.

---

## Raw Sources

### [WORKSPACE]
- `scripts/yt-mcp/README.md`
- `scripts/yt-mcp/docs/01_TODO.md` (not read in this pass; large)
- `teaching/.spec/proposals/launch-youtube-channel.md`
- `teaching/.spec/proposals/ai-presentation-site-tool.md`
- `teaching/.spec/scratch/teaching-workstream/main.md`
- `teaching/README.md` (Production Pipeline section)

### [WEB]
- HyperFrames repo: https://github.com/heygen-com/hyperframes
- HyperFrames prompting guide: https://hyperframes.heygen.com/guides/prompting (referenced from repo README)
- Remotion (the prior art HyperFrames is inspired by): https://www.remotion.dev
- video-use repo: https://github.com/browser-use/video-use
- ElevenLabs API keys (video-use dep): https://elevenlabs.io/app/settings/api-keys
- Manim (animation lib used by video-use): https://www.manim.community/
- yt-dlp (used by yt-mcp; optional dep of video-use): https://github.com/yt-dlp/yt-dlp

### [CAPTURED]
- YouTube inspiration: https://youtu.be/Aw3BkmhYu4I?si=7tJKUhe3tuLWct6D (title not extracted in this pass)
