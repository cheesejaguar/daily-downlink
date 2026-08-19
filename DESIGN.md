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
  rule: "#1b2723"
typography:
  display:
    fontFamily: "Sometype Mono, ui-monospace, SFMono-Regular, Menlo, Consolas, monospace"
    fontSize: "2.125rem"
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
  pad-narrow: "1.15rem"
  entry-gap: "5rem"
  heading-lead: "3.5rem"
components:
  link:
    textColor: "{colors.amber}"
  link-hover:
    textColor: "{colors.amber-bright}"
  nav-link:
    textColor: "{colors.phos}"
  nav-link-hover:
    textColor: "{colors.amber-bright}"
  log-title:
    textColor: "{colors.phos-bright}"
    typography: "{typography.heading}"
  log-title-hover:
    textColor: "{colors.amber-bright}"
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
| `amber` | `#e0a95c` | **Links and sources only.** |
| `amber-bright` | `#f6cd93` | Link excitation (hover/focus). |
| `rule` | `#1b2723` | Hairlines. Structural only. |

**Amber means "this points somewhere else."** It is the second phosphor, and it
carries exactly one meaning: links, source attributions, the date stamp, and the
wordmark's mark. Never use amber for emphasis — emphasis is `phos-bright`.
Never use green for a link.

Measured contrast on `ground`: body 11.2:1, titles 16.9:1, links 9.4:1, and the
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

The ramp is short on purpose — five roles, hierarchy from weight, brightness and
case rather than from many sizes:

| Role | Size | Weight | Notes |
|---|---|---|---|
| display | 2.125rem (1.75rem ≤46rem) | 700 | entry and record titles |
| heading | 1.25rem | 700 | `h2` inside a record |
| body | 1.0625rem (1rem ≤46rem) | 400 | line-height 1.7 |
| label | 0.75rem | 400 | uppercase, `0.14em` tracking |
| stamp | 0.75rem | 400 | `tabular-nums` |

Measure is **65–75ch** (68.2ch as built). Body drops to 1rem below 46rem to buy
back characters per line, because mono is wide and a narrow viewport otherwise
falls under ~32ch.

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

- **Link** — amber, 1px underline at `0.2em` offset. Hover/focus goes
  `amber-bright`. Nav links are the exception: they sit at `phos` so they read
  as interactive against dim status text, and go amber on hover.
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

---

**Not canonized.** The uppercase field-label rule is recorded as a system rule
but flagged as content-coupled: it works only because the post format guarantees
`**Label.**` as a paragraph's first child, so it is a convention shared with
CLAUDE.md rather than a free-standing style. Nothing else in the build was
withheld — the mechanical detector returned zero findings, and no craft-floor
refusal is present to be mistaken for house style.
