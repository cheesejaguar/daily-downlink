---
name: The Daily Downlink
description: A phosphor-console receiving log for a daily AI commentary column.
colors:
  ground: "#080c0a"
  phos: "#9ccfb0"
  phos-bright: "#d6f5e2"
  phos-dim: "#6f9a81"
  amber: "#e0a95c"
  amber-bright: "#f6cd93"
  phos-hot: "#eafff2"
  ground-lit: "#121e19"
  rule: "#1b2723"
typography:
  display:
    fontFamily: "Sometype Mono, ui-monospace, SFMono-Regular, Menlo, Consolas, monospace"
    fontSize: "2.125rem"
    fontWeight: 700
    lineHeight: 1.25
    letterSpacing: "-0.015em"
  display-narrow:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "1.75rem"
    fontWeight: 700
    lineHeight: 1.25
    letterSpacing: "-0.015em"
  heading:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "1.25rem"
    fontWeight: 700
    lineHeight: 1.35
    letterSpacing: "-0.01em"
  body:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "1.0625rem"
    fontWeight: 400
    lineHeight: 1.7
    letterSpacing: "normal"
  item:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "1rem"
    fontWeight: 700
    lineHeight: 1.35
    letterSpacing: "normal"
  body-narrow:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "0.9375rem"
    fontWeight: 400
    lineHeight: 1.7
    letterSpacing: "normal"
  summary:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "0.875rem"
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: "normal"
  ui:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "0.8125rem"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "normal"
  label:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "0.75rem"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "0.14em"
  stamp:
    fontFamily: "{typography.display.fontFamily}"
    fontSize: "0.75rem"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "normal"
spacing:
  rail: "8.5rem"
  gutter: "2rem"
  measure: "42rem"
  pad: "1.5rem"
  pad-narrow: "0.9rem"
  entry-gap: "5rem"
  heading-lead: "3.5rem"
components:
  link:
    textColor: "{colors.phos}"
  link-hover:
    textColor: "{colors.phos-hot}"
  link-external:
    textColor: "{colors.amber}"
  link-external-hover:
    textColor: "{colors.amber-bright}"
  nav-link:
    textColor: "{colors.phos}"
  nav-link-hover:
    textColor: "{colors.phos-hot}"
  log-title:
    textColor: "{colors.phos-bright}"
    typography: "{typography.heading}"
  log-title-hover:
    textColor: "{colors.phos-hot}"
  field-label:
    textColor: "{colors.phos-dim}"
    typography: "{typography.label}"
  stamp:
    textColor: "{colors.phos-dim}"
    typography: "{typography.stamp}"
---

# The Daily Downlink — design system

Recorded from the shipped build, not from the plan. Every value here is present
in `assets/css/style.css`.

## Overview

**North star: the receiving station log.** The site is the record of a scheduled
pass — what came down, when, and what the operator made of it. It is not a blog
page with a dark theme applied.

Two consequences run through every rule below. First, **the page is a record, so
alignment does the work that boxes would do elsewhere**: there are no cards, no
panels, no shadows, and no rounded containers anywhere in the interface. Second,
**brightness is the only depth axis**. A phosphor screen has one plane; emphasis
is how hard the electron beam hit, which is why the palette is three greens
rather than a green plus a set of surfaces.

The world is committed dark. This is not a theme toggle that happens to default
to dark — there is no light mode, because a phosphor console in daylight colours
is not the same object. `color-scheme: dark` is declared and the light palette
does not exist.

Direction provenance: concept roll seed `fd37f511` (`--scope direction --mode
read`), assigned index 7, overridden by a user-pinned phosphor terminal — the
playbook permits a brief-pinned direction to beat the roll. The seed also
appears in the direction contract in `_layouts/default.html`.

Anti-reference, stated by the client: the previous build of this site — indigo
accent, system serif, centred single column, hairline rule under every section.
That arrangement is what this system exists to refuse.

## Colors

Strategy: **committed**. One saturated field (green phosphor) carries the whole
surface; a second phosphor (amber) is reserved for a single semantic job.

| Token | Value | Role |
|---|---|---|
| `ground` | `#080c0a` | The screen. A green-black, never pure `#000`. |
| `phos` | `#9ccfb0` | Body text. The resting brightness of the record. |
| `phos-bright` | `#d6f5e2` | Headings, titles, the lede, `<strong>` inside lists. |
| `phos-dim` | `#6f9a81` | Stamps, field labels, summaries, footer. |
| `amber` | `#e0a95c` | **Outbound references only** (`a[href^="http"]`). |
| `amber-bright` | `#f6cd93` | Outbound link excitation. |
| `phos-hot` | `#eafff2` | Internal link excitation — the beam hitting harder. |
| `rule` | `#1b2723` | Hairlines. Structural only. |
| `ground-lit` | `#121e19` | The only non-ground surface: a log row under the cursor. |

**Amber means "this leaves the record."** It is the second phosphor and it is
scoped to `a[href^="http"]`, source attributions, the date stamp, and the
wordmark's mark. Internal links stay green at body brightness and carry their
underline as the affordance, exciting to `phos-hot` on hover; only outbound
links are amber. Never use amber for emphasis — emphasis is `phos-bright` — and
never colour an internal link amber.

Measured contrast on `ground`: body 11.2:1, titles 16.9:1, outbound links 9.4:1,
internal links 11.2:1, and the
dimmest role (`phos-dim`) 6.2:1. The floor for any text token in this system is
4.5:1, and `phos-dim` is the darkest value permitted.

## Typography

**One face: Sometype Mono**, self-hosted from `assets/fonts/` (SIL OFL, variable
400–700, latin subset, roman + italic, ~34KB total). Chosen because it is a
monospace drawn for *reading* rather than for code — the world requires mono,
and a coding face would have made the long-form unreadable.

Monospace here is world-native, not a technical costume: the surface is a
console, and the rail alignment, tabular date stamps, and log columns all depend
on a fixed advance width.

Hierarchy comes from weight, brightness and case more than from size — the whole
ramp spans 0.75rem to 2.125rem, and everything below `heading` sits inside one
rem. These are the only sizes the build uses:

| Role | Size | Weight | Notes |
|---|---|---|---|
| display | 2.125rem | 700 | entry and record titles ≥46rem |
| display-narrow | 1.75rem | 700 | same titles below 46rem |
| heading | 1.25rem | 700 | `h2` inside a record |
| body | 1.0625rem | 400 | line-height 1.7 |
| item | 1rem | 700 | log entry titles |
| body-narrow / wordmark | 0.9375rem | 400 / 700 | body below 46rem; the wordmark |
| summary | 0.875rem | 400 | log entry summaries |
| ui | 0.8125rem | 400 | nav, read-on, record footer, source line, skip link |
| label / stamp | 0.75rem | 400 | field labels (uppercase, `0.14em`), stamps (`tabular-nums`), site footer |

Inline `code` is `0.9em` — relative on purpose, so it tracks whatever role it
sits inside.

Measure is **68.2ch** on desktop. Below 46rem the body drops to **0.9375rem**
and padding to `0.9rem`, giving **39.8ch**. That is under the 65–75ch band and
is a deliberate floor, not an oversight: at 375px a 45ch measure in this face
requires a ~13.3px size, and trading legible type for a nominal measure buys the
metric at the cost of the thing it proxies for. Do not chase it.

## Layout

A two-column grid shared by header, main and footer, so the left edge never
moves down the page.

```
grid-template-columns: 8.5rem (rail) | 2rem (gutter) | 42rem (record)
```

- **Column 1 is the stamp rail** — dates, categories, status. Nothing else.
- **Column 2 is the record** — all prose and headings.
- The log spans `1 / -1` so each entry keeps its own stamp in the rail.
- Single breakpoint at **46rem**, where the grid collapses to one column and the
  stamp goes inline above its title.
- Page fills the viewport (`body` flex column, `main` flex `1 0 auto`) so the
  footer never floats mid-page on a short archive.

Rhythm: more space above a heading than below it (`3.5rem` / `1.25rem`).
Stamps are baseline-matched to the heading they label, not eyeballed.

## Elevation & Depth

**There is none, and adding any is a violation.** No shadows, no blur, no
layering, no z-index above the skip link. The surface is a single plane.

The single exception is `ground-lit`, the log row under the cursor. It is a
brightness change in the ground itself, not a lift: no shadow, no border, no
transform.

Depth is expressed only as brightness: `phos-dim` recedes, `phos` rests,
`phos-bright` advances. If something needs to come forward, raise its
brightness token; do not lift it.

## Shapes

No border radius anywhere in the interface. No fills, no chips, no pills, no
containers. The only radius in the project is `4px` on the favicon tile, which
is an app-icon affordance and not a page token.

Rules are 1px `rule` and appear in exactly three places: under the status bar,
between log entries, and above the record footer. A rule anywhere else is
decoration and does not belong.

Icons are authored SVG on a 24px grid at `stroke-width: 2`, `round` caps and
joins, `currentColor`. The arrow-to-bar mark (signal meeting the ground) is the
only mark; it is a brand commitment recorded in PRODUCT.md and the About prose
refers to it.

## Components

- **Link** — internal links sit at `phos` with a 1px underline at `0.2em`
  offset and excite to `phos-hot`. Outbound links (`a[href^="http"]`) are
  `amber`, exciting to `amber-bright`. Do not give an internal link
  `phos-bright`: that is the heading value, and the collision removes the only
  colour channel distinguishing the two.
- **Phosphor persistence** is the system's single motion: colour excites in
  **40ms** and decays over **620ms** on
  `cubic-bezier(0.16, 1, 0.3, 1)`. Fast in, slow out — what phosphor does.
  It is the only animation in the system; adding a second is a violation.
  Fully disabled under `prefers-reduced-motion`.
- **Field label** — `.body p > strong:first-child` renders as a block, uppercase,
  tracked, `phos-dim`. This turns the post format's `**What happened.**` /
  `**Why it matters.**` convention into record fields **without editing the
  markdown**. It is coupled to the authoring contract in CLAUDE.md; changing one
  requires changing the other.
- **Source line** — `.body p > em:only-child` renders as a de-italicised
  `0.8125rem` `phos-dim` block, pulled up `0.75rem` to sit with its paragraph.
- **Stamp** — dim, tabular, with its date in amber.
- **Share control** — a real `<button>` in the record footer, carrying the
  record's link language: no background, no border, no radius, underlined,
  `phos` exciting to `phos-hot`. It ships `hidden` and is revealed by script
  only when the browser can act on it, so a no-JS reader sees nothing broken.
  Where `navigator.share` exists it opens the native sheet; otherwise it
  relabels itself "Copy link" and writes the canonical URL to the clipboard,
  confirming in an `aria-live="polite"` status set in `amber`. Dismissing the
  share sheet is a choice, not an error, and is never reported as one.
- **Focus** — 2px `amber` outline at `3px` offset. Never removed.

## Do's and Don'ts

**Do**
- Reach for a brightness token before reaching for any other device.
- Keep every new surface on the rail/record grid.
- Keep amber semantic: it points somewhere else.
- Set new UI text in one of the five type roles.

**Don't**
- Add cards, panels, boxes, shadows, gradients, or radii.
- Introduce a second typeface, or fall back to a system stack.
- Add a light theme or a theme toggle.
- Use green for links or amber for emphasis.
- Add a second animation.
- Add a rule that isn't separating the status bar, log entries, or the record
  footer.

## Script

The site carries exactly one script: ~30 lines of vanilla JS inlined on post
pages only, wiring the share control. There is no framework, no bundler, no
build step, and no third-party script. Every other surface is static HTML and
CSS, and any new behaviour must clear the same bar: progressive enhancement,
inline, no dependency, and nothing that breaks with JS off.

## Out of system

Print styles (`@media print`) deliberately leave the system: the page inverts to
black on white at `10.5pt`, links print black with their URL appended at
`8.5pt`, and `#444` carries the URL. Phosphor is a screen material and has no
meaning on paper. These literals are the only ones in the stylesheet and they
are intentional; do not tokenize them.

---

**Not canonized.** The uppercase field-label rule is recorded as a system rule
but flagged as content-coupled: it works only because the post format guarantees
`**Label.**` as a paragraph's first child, so it is a convention shared with
CLAUDE.md rather than a free-standing style. Nothing else in the build was
withheld — the mechanical detector returned zero findings, and no craft-floor
refusal is present to be mistaken for house style.
