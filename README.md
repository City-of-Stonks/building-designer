# Building Designer

A single self-contained HTML tool for painting City of Stonks building
sprites in the same "role, not color" vocabulary the live site's own
generator uses: every cell is an abstract part (a window, a trim line, a
rooftop object), never a literal color, so the same sprite can be recolored
per city context and stretched to any height without being redrawn.

No build step, no dependencies — open `index.html` in a browser.

## What it does

- A pixel-grid editor (pen, line, rectangle, fill, eyedropper, eraser,
  undo/redo, horizontal mirror, adjustable zoom) for painting a 14-role
  semantic palette across a resizable canvas (20–50 wide, 34–127 tall).
- A **repeating floors** band: rows above it render once as a roofline cap,
  rows inside it repeat to reach whatever height a building actually needs,
  rows below it render once as the ground floor. An optional max-height cap
  supports one-off landmark buildings that never stretch indefinitely.
- Six live preview contexts (Dawn District, Golden Hour, Neon Night,
  Necropolis, Gold Tier, Gas Storm) rendering the *same* role-map with
  different color mappings and different target heights side by side —
  proof that the role system actually produces the adaptive behavior it's
  meant to.
- Export to `.json` (the full role-grid + band + metadata) and `.png` (the
  authored sprite, upscaled) — this is a local design tool, not a
  submission form; exported files still need to go wherever City of Stonks
  actually collects community submissions.

## Status

Independent fan-made tool, not officially affiliated with cityofstonks.com.
The row-repetition math (the core "stretch to any height" mechanic) is
covered by direct unit tests confirming exact row counts for unstretched,
stretched, and max-height-capped cases.
