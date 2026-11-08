# Design rules

Written down before the first line of CSS so the next pass does not invent a
different page. Every rule below is checkable.

## 1. Intent

One job: show how a capsule moves from one device to another, and let the
visitor do it once. Everything that does not serve that job is decoration and
gets removed.

## 2. Surface

- `--paper:#F2EEE4`, `--paper-2:#EAE5D8`, `--ink:#15140F`.
- One accent: `--accent:#C8351A`. Used only for active state, the playhead, and
  the transmitted trace. It is not a brand wash.
- Hairlines: `1px` in `--rule` or `--rule-strong`. No shadows, no blur, no
  glass, no gradients, no rounded cards.
- Geometry comes from the grid, not from padding tricks.

## 3. Type

- Display: Instrument Serif, 400, `line-height:.96`, `letter-spacing:-.015em`.
- Text: IBM Plex Sans, 400/500.
- Labels and data: IBM Plex Mono, 500, `11px`, `letter-spacing:.16em`,
  uppercase.
- Body copy never exceeds 52 characters per line in the table, 38 in the hero.

## 4. Copy

Removed on purpose, per `petergyang/no-ai-slop`:

- Binary contrasts ("not X. It's Y.").
- Colon reveals ("The best part: it learns.").
- Throat-clearing openers.
- Faux-insight setups ("What nobody tells you").
- Importance puffery ("a testament to").
- Weasel attribution ("experts agree").
- Fake-profound endings.

Kept: concrete numbers, active voice, the point first.

## 5. State

Every state is visible and named: `idle`, `on air`, `sent`, `listening`,
`hearing`, `caught`. Durations, byte counts, and the baud rate come from the
data, not from a random number.

## 6. Motion

Motion exists to show a transmission happening: the playhead crosses the
waveform over the true airtime, capped at 2.6 s and labelled with the preview
multiplier when capped. `prefers-reduced-motion` collapses the animation to a
single frame.

## 7. Interaction

- One primary action per panel.
- The transmit button is disabled until there is a payload.
- The receive panel announces its state with `aria-live="polite"`.
- Every control is reachable and operable by keyboard; focus rings use the
  accent at 2px with a 3px offset.

## 8. Forbidden

- Card grids with equal rounded rectangles.
- Emoji as icons.
- Purple or blue gradient meshes.
- Testimonials, logo walls, and invented metrics.
- "Seamless", "revolutionary", "effortless", "supercharge".

## 9. Breakpoints

- `900px`: single column, rail hidden, instrument panels stack.
- `620px`: top navigation collapses to the single call to action.
- No fixed pixel widths in the layout. Check 320, 390, 768, 1024, 1440.
