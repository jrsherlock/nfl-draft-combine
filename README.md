# DRO — Behavioral Simulation for Player Personnel

> *"Your data tells you what a player **is**. DRO tells you how the room is going to behave when he slides."*

A concept site for **DRO** (Decision Rehearsal Operations) — a behavioral load-testing sandbox for front offices. DRO's multi-agent persona engine runs your draft board through ten thousand parallel realities — rival GMs, beat writers, agent reps, fan bases — before a single pick is on the clock.

**Live site:** [jrsherlock.github.io/nfl-draft-combine](https://jrsherlock.github.io/nfl-draft-combine/)

---

## What this repo is

A two-page static site presenting the DRO product concept and a working engine-demo mockup. Everything is plain HTML — no build step, no framework, no dependencies.

| File | Purpose |
| --- | --- |
| `index.html` | Landing page. Hero, command deck, persona library, sentiment rollups, cross-sport extensibility, data-ingestion pitch. ~3.7k lines, single-file with embedded CSS. |
| `demo.html` | Interactive engine demo. War-room dialogue stream, trade wire, pick-distribution chart. |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll processing). |

## The pitch, in one paragraph

Static models score the player. DRO scores the *room*. Seeded by your proprietary scouting reports, Combine biometrics, transfer-market profiles, and historical board tendencies, DRO instantiates a curated cast of 1,184 fitted personas — each carrying its own tone, posting cadence, source network, bias dials, and platform-native voice. Inject a behavioral shock (an eleventh-hour medical flag, a leak from a rival war room, a surprise bid) and the engine re-resolves all downstream agent decisions in roughly 4.2 seconds per branch. 312 posts roll up to three numbers the room actually uses.

Same engine works for the NFL Draft, R2–R3, MLS Summer Window, UEFA January Window, Combine re-pricing, free-agency 72hr, and a generic trade-deadline sandbox.

## Design

- **Aesthetic:** ink-and-ember tactical terminal × editorial sports.
- **Type:** Fraunces (display), Instrument Serif (italics), Geist (UI), JetBrains Mono (data).
- **Palette:** deep ink blacks, ember orange, gold, mint, azure — color-coded by persona platform (X, Reddit, Sports Radio, Discord, Cable TV).
- **Layout:** engineering-grid background, three-column command deck with live war-room center panel.

## Local preview

```bash
# any static server works — pick one:
python3 -m http.server 8000
# or
npx serve .
```

Then open <http://localhost:8000>.

## Deploying

Pushes to `main` deploy automatically via GitHub Pages (source: `main` / root). To trigger a rebuild:

```bash
git push origin main
```

Build status:

```bash
gh api repos/jrsherlock/nfl-draft-combine/pages/builds/latest \
  --jq '{status, error: .error.message, commit, updated_at}'
```

## Status

Internal preview — agency confidential mockup. Copy, scenarios, and metrics are illustrative, not a shipped product.
