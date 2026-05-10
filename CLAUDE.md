# Leaf Cutter Ant Simulation

A meditative visual art piece — leaf-cutter ants strip a tree bare over a 12-hour day arc.

## Concept
Nature documentary timelapse aesthetic. Serene, slightly hypnotic. Single `index.html`, no frameworks, Canvas 2D only, no external assets.

## Scene
- **Sky**: dawn (indigo→coral) → noon (pale blue) → dusk (amber→purple), sun arcs left to right
- **Tree** (right): full canopy of individually tracked leaves, stripped bare by dusk; branches reveal as leaves thin
- **Nest** (left): soil mound with hole, ants emerge/enter here
- **Rope bridge**: catenary curve connecting nest to tree, ants walk along it
- **Ants**: 5 at dawn → ~40 at noon → taper at dusk; state machine OUT→FORAGE→CUT→BACK→ENTER; 3-segment body, 6-leg tripod gait, carry leaf overhead when returning

## Modes
- **Demo** (default): 10 real minutes = full 12-hr arc
- **Art**: 12 real hours (meant to run all day on a screen)
- Toggle with `D` key

## Style
Warm, painterly, earthy palette. Seeded PRNG (`mulberry32`, seed `0xDEADBEEF`) for reproducible scene generation. Film grain overlay, colour temperature tint at dawn/dusk.

## Stretch goals (not yet done)
- Ambient Web Audio sound (crickets/cicadas peaking at noon)
- Second rope lane (outbound/inbound separation)
