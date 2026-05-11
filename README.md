# Leaf Cutters

A meditative generative art piece — a colony of leaf-cutter ants strips a tree bare over a 12-hour day arc, rendered in a single self-contained HTML file.

![canvas art of leaf-cutter ants on a rope bridge](https://img.shields.io/badge/single%20file-index.html-8a5e2c?style=flat-square)

## About

Inspired by nature documentary timelapses. The scene runs continuously: dawn breaks, ants emerge from their nest, cross a rope bridge, climb the tree, cut leaves and carry them home. By dusk the canopy is stripped bare and the colony retreats. Then it begins again.

No frameworks, no build step, no external assets. Just `index.html` and a Canvas 2D context.

## Scene

- **Sky** — cycles from indigo dawn through coral sunrise, pale-blue noon, amber dusk, and back to deep purple night. Stars fade in and out. The sun arcs left to right.
- **Tree** — a procedurally generated tree on the right bank with a full circular canopy of individually tracked leaves. Thick branches have a bark texture. Branching roots snake down into the soil below.
- **Nest** — a soil mound on the left bank with a dark arched entrance. Eggs become visible inside as the colony grows.
- **Rope bridge** — a catenary curve with wraps around the trunk. Ants use it to commute.
- **Ants** — 5 at dawn, peaking at ~40 at noon, tapering by dusk. Each ant has a state machine (`GROUND_OUT → CLIMB → OUT → FORAGE → CUT → BACK → ENTER`), a 3-segment body, a 6-leg tripod gait, and carries a leaf overhead on the return trip.
- **Lake** — a ravine between the banks reflects the sky with animated ripples and shimmer.

## Usage

Just open `index.html` in a browser. No server required.

```
open index.html
```

## Controls

| Key | Action |
|-----|--------|
| `D` | Toggle Demo / Art mode |
| `S` | Cycle speed (×1 → ×2 → ×4 → ×8 → ×16 → ×32) |
| `P` | Pause / unpause |

## Modes

| Mode | Duration |
|------|----------|
| **Demo** (default) | 10 real minutes = full 12-hour arc |
| **Art** | 12 real hours — meant to run on a screen all day |

## Technical notes

- Single `index.html`, ~1000 lines of vanilla JS
- Canvas 2D only — no WebGL
- Seeded PRNG (`mulberry32`, seed `0xDEADBEEF`) — scene layout is fully reproducible
- Film grain overlay refreshed every other frame
- Colour temperature tint at dawn and dusk
- Resizes and reinitialises on window resize

## Stretch goals

- Ambient Web Audio (crickets / cicadas peaking at noon)
- Second rope lane separating outbound and inbound ants
