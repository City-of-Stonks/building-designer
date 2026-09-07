# Building Designer

A single self-contained HTML tool for painting City of Stonks building
sprites in the same "role, not color" vocabulary the live site's own
generator uses: every cell is an abstract part (a window, a trim line, a
rooftop antenna), never a literal color, so the same sprite can be recolored
per city context and stretched to any height without being redrawn.

No build step, no dependencies — open `index.html` in a browser, or use the
[live version](https://city-of-stonks.github.io/building-designer/).

## What it does

- A full-page, fixed-viewport editor shell — menu bar, icon toolbox, canvas
  viewport, and a tabbed properties dock (Roles / Canvas / Preview / Stats /
  Info) — rather than a scrolling page of stacked panels.
- Tools: pen, line, rectangle, ellipse, fill, eyedropper, eraser, and a
  rectangular select tool with real copy/cut/paste/delete and arrow-key
  nudging of the selected block. Brush sizes 1–8px in square or round shape.
  Undo/redo, adjustable zoom, canvas resize, and flip horizontal/vertical.
- **Symmetry** — off, horizontal, vertical, or 4-way point symmetry about
  the canvas center.
- A **36-role palette** across 8 categories (Structure, Glass, Detail,
  Signage, Greenery, Weathering, Rooftop, Special) — billboards, neon
  signs, flags, ivy, rust, graffiti, antennas, solar panels, water towers,
  and more, on top of the original walls/windows/trim/doors set.
- A **repeating floors** band: rows above it render once as a roofline cap,
  rows inside it repeat to reach whatever height a building actually needs,
  rows below it render once as the ground floor. An optional max-height cap
  supports one-off landmark buildings that never stretch indefinitely.
- **14 live preview contexts** (Dawn District, Golden Hour, Neon Night,
  Necropolis, Gold Tier, Gas Storm, Cyberpunk Sprawl, Blizzard, Wildfire
  Haze, Aurora Skyline, Blackout, Festival Night, Desert Heat, Corporate
  District) rendering the *same* role-map with different color mappings and
  different target heights side by side.
- A **Random Building** generator — every dimension, window mix, frame
  rhythm, rooftop hardware, signage, and weathering choice is rolled
  independently from the same role palette, so nothing it produces can fall
  outside the aesthetic.
- A live **Role Usage** stats panel, a recently-used-roles strip, and
  Import/Export to `.json` (round-trips the full role-grid + band +
  metadata) and `.png`.
- A link to the [Control Room](https://city-of-stonks.github.io/testing/)
  dashboard, which lists every City of Stonks repo and its live GitHub
  Pages site in one place.

Export is a local design tool, not a submission form — exported `.json`
files still need to go wherever City of Stonks actually collects community
submissions.

## Status

Independent fan-made tool, not officially affiliated with cityofstonks.com.
The row-repetition math (the "stretch to any height" mechanic), the
symmetry/ellipse/flip/selection math, and the random building generator
were all verified with direct tests before shipping.
