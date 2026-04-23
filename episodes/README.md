# Episodes

Episode scripts for *Beyond the Prompt*. Each file is the working script for one episode — not the final polished transcript, but the living document that moves through outline → script → post-production notes.

## File Convention

```
episodes/
├── 01-the-value-shift.md
├── 02-the-four-disciplines.md
├── ...
└── 11-from-consecration-to-zion.md
```

Filename format: `{N:02d}-{slug}.md`

## Episode Structure

Every script follows this five-part shape:

1. **The engineering problem** (2–3 min) — what goes wrong without this step
2. **What the industry says** (2–3 min) — current best practices and their limits
3. **What actually happened** (3–5 min) — real story from our work, with source references
4. **The pattern underneath** (3–5 min) — the gospel principle, with scripture
5. **What this means for you** (1–2 min) — practical takeaway, professional and spiritual

Target length: 12–18 minutes per episode.

## Status

| # | Slug | Status |
|---|------|--------|
| 1 | the-value-shift | planned |
| 2 | the-four-disciplines | planned |
| 3 | spiritual-before-temporal | planned |
| 4 | watched-until-they-obeyed | planned |
| 5 | intelligence-cleaveth | planned |
| 6 | the-seven-unmapped-steps | planned |
| 7 | covenant | planned |
| 8 | delegation-as-stewardship | planned |
| 9 | when-things-go-wrong | planned |
| 10 | the-sabbath-of-creation | planned |
| 11 | from-consecration-to-zion | planned |

## Scratch Files

Per-episode research and provenance lives in `../.scratch/{slug}/`. These are kept after publishing — they're the provenance that makes the source verification claims verifiable.

## Before You Script

Run the teaching agent (`@teaching` in VS Code agent mode) from the parent workspace. It handles the full phase structure — outline, script, Ben Test, voice review — and has access to the study corpus, MCP servers, and source verification tools.

Source verification is amplified in teaching context. Read before quoting. Every direct quote in a script requires a verified `read_file` of the source. An unverified quote in a study is a private error; in a published video it can't be un-published.
