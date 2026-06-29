# digital-storytelling-26

This is a working studio, not a showcase. It holds experiments, half-finished mechanics, interaction tests, and the scaffolding for a larger autobiographical project. The code here is a thinking tool — organized for clarity and iterability, not production. Expect rough edges.

---

## The North Star Project — *Displacement: A Sunset Park Memoir*

The main deliverable the course is building toward. An interactive autobiographical narrative about:

- Growing up in Sunset Park, Brooklyn — inherited, invisible belonging; the kind you don't notice until it's gone
- Being uprooted to rural Maryland at age [Jeff will fill this in]
- The irreconcilable tension between two selves: the Brooklyn kid and the Maryland teenager
- How displacement forces you to actively construct belonging instead of inheriting it
- Reading and solitude as the through-line connecting both places

**Core design principle:** interactions should embody emotional logic, not illustrate it. Mechanics are meaning. If a mechanic could be swapped for a caption without losing anything, it's the wrong mechanic.

---

## Design Influences & References

**Games / interactive:**
- *Florence* — mundane mechanics that carry emotional weight
- *What Remains of Edith Finch* — room-as-character, voice layering, death of the unified narrator
- *Old Man's Journey* — environmental storytelling, no text needed

**Web / editorial:**
- The Pudding — data-driven scrollytelling as narrative form
- Scrollytelling generally — controlling pacing through scroll position instead of clicks

**Audio:**
- Radiolab's "Father K." — how audio craft handles untranslatable experience

**Visual language:**
- Flat minimalist; no photorealism
- Warm palette = Brooklyn, home, the inherited self
- Cool palette = displacement, Maryland, the constructed self
- Doorway thresholds as recurring motif — the literal and psychological crossing point

---

## What's in the Repo

```
digital-storytelling-26/
├── snail-story/                    # Full snail piece (main experiment)
│   ├── snail-story-full.html       # The complete three-phase film: HOME → CARRY → ARRIVAL
│   ├── snail-story.html            # Earlier draft / working version
│   ├── snail-story-beat2.html      # Isolated beat 2 test
│   └── assets/                     # Visual placeholders (PNG swap pattern)
│       ├── background.png
│       ├── leaf.png
│       └── snail.png
├── snail-displacement/
│   └── index.html                  # Field guide / lecture structure (four slides, interactive nav)
├── interaction-experiments/
│   └── head-parallax-demo_1.html   # MediaPipe head-tracking parallax test
├── snail-displacement-build-doc.md # Build notes for the snail piece
└── CLAUDE.md                       # This file
```

### snail-story — The Formal Test

A short autoplay film about a snail's accidental dispersal. It operates on three levels simultaneously:

1. Scientific explainer — phoresy, how snails colonize new habitats via host animals
2. Displaced individual — the snail as stand-in for anyone moved by forces outside their control
3. Boy daydreaming in a library — the reader/narrator discovering the concept as a child and recognizing himself in it

The mechanism is phoresy itself: natural force, nobody's fault, existential. This piece is a formal test for the memoir — if I can make the three levels coexist without one flattening the others, the approach works.

Uses MediaPipe hand-tracking in some variants. Visual assets are generated via Flux.1 (ComfyUI Cloud) and swapped into the HTML via a simple image registry pattern — placeholders in, finals out, no restructuring required.

### interaction-experiments — Loose Tests

One-off mechanic specimens. `head-parallax-demo_1.html` tests MediaPipe face landmark tracking driving a parallax depth effect. These exist to answer specific questions ("does this feel right?") and may or may not feed into the memoir directly.

---

## Notes on Process

- **Builds first, writes second.** Prototyping reveals what I actually want to say. I don't write the script before I understand how the mechanic feels.
- **PNG swap pattern.** Placeholder images live in `assets/`. The HTML references them by filename. Swapping in finals means replacing the file, not touching the code.
- **Willing to pivot.** Mechanics change as understanding deepens. Scope shifts. The repo reflects where I am, not where I planned to be.
- **Narrative framework:** Blake Snyder's Save the Cat 15-beat structure, adapted for interactive/non-linear form. It's a spine, not a straitjacket.

---

## What's Coming

- Completing and testing the snail piece with final Flux.1 assets
- Main memoir scenes: dressing sequence, school mockery, reading reclamation
- Refining the narrative arc beat by beat
- Testing mechanic-as-meaning principles across longer interactions
- [Jeff will fill in actual folder structure as it grows]

---

## How to Run Anything

Everything here is vanilla HTML/CSS/JS. Open the file in a browser. No build step, no package manager, no server required unless a piece uses MediaPipe (which loads from CDN) — in that case you may need to serve locally to avoid CORS issues:

```bash
# From the repo root
python -m http.server 8080
# then open localhost:8080
```
