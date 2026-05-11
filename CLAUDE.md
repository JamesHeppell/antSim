# Leaf Cutter Ant Simulation

A meditative visual art piece — leaf-cutter ants strip a tree bare over a 12-hour day arc.

## Concept
Nature documentary timelapse aesthetic. Serene, slightly hypnotic. Single `index.html`, no frameworks, Canvas 2D only, no external assets.

## Scene
- **Sky**: dawn (indigo→coral) → noon (pale blue) → dusk (amber→purple), sun arcs left to right
- **Tree** (right): full canopy of individually tracked leaves, stripped bare by dusk; branches reveal as leaves thin
  - Trunk: `H * 0.26` initial length, width multiplier `0.105`; thick branches (w > 7) have bark texture (lit highlight, shadow edge, longitudinal furrow lines)
  - Extra lateral arms always spawn at the first fork (depth 7, both sides) and at depths 6 and 5 with high probability, giving a near-circular full crown
  - Leaves generated on branches up to depth 7 (4–8 per branch)
  - **Roots**: 5 branching root toes (`genRoots`) grow downward from the tree base into the soil, drawn as surface roots over the earth bank
- **Nest** (left): soil mound with hole, ants emerge/enter here
- **Rope bridge**: catenary curve connecting nest to tree, ants walk along it; rope lineWidth `3.5` (thicker) with scaled trunk-wrap radius
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
