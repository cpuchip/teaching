# Video tooling and image sourcing — research notes

*Compiled 2026-05-21 in response to Michael's ask: "find images in the
creative commons" and "I've seen hyperframes... would be awesome if we could
really bring this to life."*

The teaching workstream produces YouTube episodes. Each episode needs (a)
a video to publish and (b) a companion page on cpuchip.net (Episode 1's
page shipped same day at `/presentations/01-the-value-shift`). This doc
covers the tooling we could adopt to make the video production loop
tractable, plus a sourced image plan for Episode 1.

---

## Part 1 — Programmatic video tooling

### The lead: HyperFrames (HeyGen)

[github.com/heygen-com/hyperframes](https://github.com/heygen-com/hyperframes) ·
[hyperframes.app](https://hyperframes.app/) · Apache-2.0 · open-sourced 2026

**What it is:** A video rendering framework that takes plain HTML
compositions and renders them to MP4. AI-agent-native by design — the CLI is
non-interactive by default, "designed for agent-driven workflows." Animations
ride GSAP, **AnimeJS** (we already use it), Lottie, Three.js, or CSS. Ships
with 50+ pre-built component blocks (transitions, overlays, charts).

**Why this is the lead for our workflow:**
- We already author cpuchip.net presentations in HTML + AnimeJS. The
  `ValueShiftScarcity` component that scroll-reveals on the web page is the
  same shape as what a HyperFrames composition would need. The skill we
  built for the web companion transfers directly to the video.
- AI-first means I (the agent) can author compositions reliably. LLMs are
  strong at HTML/CSS; HyperFrames was designed around that fact.
- Deterministic rendering — identical inputs produce identical outputs. We
  get reproducible builds, version-controlled videos.
- No per-render fees, no commercial restrictions, no proprietary format.
- The same compositions can output multiple aspect ratios (16:9 for
  YouTube, 9:16 for Shorts) without re-authoring.

**Workflow:**
```bash
npx hyperframes init episode-01
npx hyperframes preview     # live-reload browser preview
npx hyperframes render      # output MP4
```

**Honest caveats:**
- New project (open-sourced 2026); ecosystem and docs less mature than
  Remotion. We'd be early adopters.
- Render uses FFmpeg + Puppeteer — Chrome footprint, ~~5–10× real-time
  render speed depending on composition complexity. A 13-minute episode
  would take 1–2 hours to render. Fine for batch, not for iteration.
- Voiceover and captions need to be authored externally and fed in
  (text-to-speech sync is supported via overlays, not auto-generated).

### The alternatives

- **[Remotion](https://www.remotion.dev/)** — React-based, the mature
  incumbent. **Licensing gotcha:** free for companies under 4 devs;
  otherwise commercial license required. Best ecosystem and docs. If
  HyperFrames feels too early, Remotion is the safe fallback.
- **[Motion Canvas](https://motioncanvas.io/)** — TypeScript generator
  functions, scene graphs, real-time editor. Designed for explainer videos
  and visualizations specifically. Hand-crafted animation, not template
  filling. Closest analog to writing the LCARS diagrams we've already built.
- **[Revideo](https://midrender.com/revideo)** — open-source fork of Motion
  Canvas. MIT-licensed, adds headless rendering API, audio support, designed
  for automated/batch pipelines. The picks for "I want Motion Canvas's
  hand-crafted feel but with batch rendering."

### Recommendation

**Start with HyperFrames.** Same animation library we already use, same
HTML/CSS skill set, designed for the exact workflow we're already running
(LLM-authored compositions). The composition for `ValueShiftScarcity` on
the cpuchip.net page would port to a HyperFrames scene with maybe an hour
of work — and the cpuchip.net page becomes both the web companion AND the
proof-of-concept for the video scene.

**Fallback to Remotion** if HyperFrames docs prove too thin for a specific
need (it's new; we may hit gaps).

**Skip Motion Canvas / Revideo for now** — different mental model from
the AnimeJS work we already have. Worth revisiting if we need
keyframe-perfect explainers later.

### Next step (when you're ready)

Stand up a `teaching/composition/` directory parallel to `episodes/` and
`videos/`. Each episode gets its own composition folder. Start by porting
`ValueShiftScarcity` (the working cpuchip.net component) to a HyperFrames
scene and rendering a 30-second test clip. If that pipeline holds, scale
to a full episode shell with title card, scene transitions, captions, and
the voiceover track.

---

## Part 2 — Creative Commons image sourcing

### Sources, ranked for our needs

1. **[Unsplash](https://unsplash.com)** — Unsplash License (free for
   commercial use, no attribution required, no model release). Largest
   library, highest-quality photos. **First stop.**
2. **[Pexels](https://www.pexels.com)** — Pexels License (similar to
   Unsplash). Strong on workspace, laptop, code-screen shots. **Second
   stop.**
3. **[Pixabay](https://pixabay.com)** — Pixabay License (free for
   commercial use, no attribution required). Mix of stock photos and
   vector illustrations. Useful for abstract concepts.
4. **[StockSnap.io](https://stocksnap.io)** — Explicitly CC0. Smaller
   library but every image is unambiguously public domain.
5. **[Wikimedia Commons](https://commons.wikimedia.org)** — Mixed
   licensing; check each image. Good for historical photos, scriptural
   art, public-domain paintings.
6. **[Creative Commons Search Portal](https://search.creativecommons.org/)** —
   meta-search across Flickr CC, Wikimedia, museum collections. Best for
   "I need a specific named thing under explicit CC license."

### LDS-specific imagery

The Church of Jesus Christ of Latter-day Saints owns most published gospel
art. **Media usage terms:** non-commercial use is generally permitted with
attribution per the
[Church's terms of use](https://www.churchofjesuschrist.org/legal/terms-of-use).
A YouTube video that's free-to-watch but ad-supported may or may not
qualify — worth a careful read before using any Church-owned artwork in
a monetized channel.

**Safer alternatives for LDS-themed imagery:**
- Public-domain Bible art on Wikimedia (Tissot, Doré, classical
  paintings of biblical scenes).
- Original photography — open scripture, hands, candles, etc. (Unsplash /
  Pexels have plenty).
- Original LCARS-style graphics generated by the cpuchip.net components
  we've already built. Screen-capture our own diagrams = no licensing
  concern.

### Image plan for Episode 1 specifically

| Beat | Image type | Source candidates |
|---|---|---|
| Title card | Original LCARS — already built | Screenshot the cpuchip.net presentation header |
| 2008 → 2026 split (old IDE vs AI chat) | Two screenshots — original | Just shoot them — your own editor, your own AI session |
| "I feel insignificant sometimes" | Hold on text card — no image needed | LCARS text-on-black |
| Reddit dev quote | Stylized text card | LCARS or screenshot of Thompson's article |
| Trejo / Turkovic / Jovanović quotes | Quote cards with attribution | Generate; or pull author headshots from their public profiles (use only with permission for monetized video) |
| "Staying Relevant" study scroll | Screen recording — original | Record the cpuchip.net study page scrolling |
| Database schema config failure beat | Generic terminal / code abstract | Unsplash "terminal," "code," "database" — many candidates |
| Scripture cards (D&C 130, Matt 25, Abraham 4) | Text + subtle background | Public-domain illuminated manuscript imagery (Wikimedia); or open Bible photo (Unsplash) |
| Parable of the Talents | Public-domain painting | Search Wikimedia for "Parable Talents" — multiple Old Master paintings in public domain |
| Abraham 4-5 (organized and watched) | Abstract creation imagery — stars, light | Unsplash "cosmos," "starfield," "creation" |
| Closing / Episode 2 teaser | LCARS pill — already built | Screenshot |

**Most of Episode 1 needs minimal external imagery.** The visual identity
is LCARS (we own it), the talking-head is you, and the major beats are
text cards. The CC0 stock is for:
- Section 1 b-roll (workstation, typing, code editor close-ups)
- Section 4 scriptural background imagery (open scripture, creation
  imagery, classical paintings of the parable)

### Specific Unsplash search queries that should yield good first-page results

- `software engineer late night` — for the reviewer-not-creator beat
- `terminal black screen` — for the failure beat
- `open scripture book` — for section 4
- `cosmos starfield abstract` — for Abraham creation imagery
- `monastery library old book` — for the durable-layer / talents close

---

## Part 3 — Integration with the existing workflow

The cpuchip.net presentation page IS the visual storyboard for the video.
Each `<ValueShiftScarcity />`-style component on the web page is a scene
that can port to HyperFrames. The web page comes first (one repo, one
component, one design system); the video composition reuses the same code.

Recommended order for Episode 1 production:
1. ✅ Script finalized in `teaching/episodes/01-the-value-shift.md` (draft 6).
2. ✅ Web companion shipped at `/presentations/01-the-value-shift`.
3. (next) Record voiceover from the script. ~13 minutes.
4. (next) Capture b-roll: workstation shots, the cpuchip.net study scrolling,
   the editor open, the AI chat interface.
5. (next) Stand up `teaching/composition/01-the-value-shift/` as a
   HyperFrames project. Port `ValueShiftScarcity` as the first scene.
   Build out title card, scene transitions, scripture cards, closing.
6. (next) Render. Iterate. Cut.
7. (next) Publish to YouTube. Add the video embed link to the
   presentation page.

The whole loop is reproducible, version-controlled, agent-authorable.

---

*Last updated: 2026-05-21*
