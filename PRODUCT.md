# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary: **practitioners building AI systems** — engineers and researchers shipping
production AI. They read a short daily brief to stay oriented on what actually
changed and whether it affects their stack. They are technical enough to want the
primary source rather than coverage of it, and they are reading briefly, not
settling in for an essay.

Not written for a general or non-technical audience.

## Product Purpose

*The Daily Downlink* is a daily AI commentary column by Aaron Cohen. Each edition
carries two or three highlight stories with one clear take on each, a "The Rest"
digest of four to six quick hits, and an optional "What I'm watching".

It exists to build a **public, dated track record of judgment** about AI. Success
is that the archive demonstrates how its author thinks — a body of on-the-record
calls worth citing. Success is explicitly *not* audience size; reach and
subscriber growth are not the metric and should not drive product decisions.

## Positioning

Commentary, not aggregation. A neighbouring newsletter can carry the same stories;
what it cannot truthfully copy is a systems engineer's accountable, dated take on
each one — evidence read before it is cited, demos separated from products, and
capability claims weighed against what it costs to run the thing in production, at
load, when it is wrong.

The editorial filter is the position: if there is nothing useful to say about why a
story matters, it is demoted to The Rest or dropped, never summarised to fill space.

## Operating Context

- Published **once daily by an autonomous agent** over SSH using a dedicated deploy
  key, managed outside this repository.
- **No human is in the publishing loop.** The agent researches, writes, and pushes
  without review; whatever it pushes is live immediately. There is no staging,
  draft, or approval surface, and none is planned.
- The entire publish action is: add one markdown file to `_posts/`, commit, push to
  `main`. GitHub Pages rebuilds automatically.
- Because nothing is reviewed before publication, **`CLAUDE.md` at the repo root is
  the only safeguard** on correctness, format, and voice. It is a load-bearing
  product artifact, not documentation, and it is read by a fresh agent with no
  memory of prior sessions.
- Readers arrive at the site directly or through RSS.

## Capabilities and Constraints

Currently live: home (latest column plus reverse-chronological archive), post pages,
About, RSS feed, sitemap, and a styled 404.

- Served at `https://blog.aaronx.co` by GitHub Pages' **native Jekyll build** from
  `cheesejaguar/daily-downlink`, branch `main`, root.
- **No build step and no GitHub Actions.** Only Pages-whitelisted plugins are
  available: `jekyll-feed`, `jekyll-seo-tag`, `jekyll-sitemap`, `jekyll-paginate`.
  Any other gem fails the build outright.
- Post URLs derive from the filename: `_posts/YYYY-MM-DD-slug.md` →
  `/YYYY/MM/DD/slug/`. A malformed filename is not an error — the post is silently
  ignored.
- `draft: true` hides a post from the home page, archive, and feed, but the page is
  still built at its URL and listed in `sitemap.xml`. `published: false` is the only
  true off switch.
- **Planned but not built: category / tag archive pages.** Blocking constraint to
  solve first — no whitelisted plugin generates per-category pages (`jekyll-archives`
  is not permitted). Achievable in Liquid without a plugin, either as one grouped
  "Topics" page or one hand-added page per category, but not automatically.
- **Explicitly not planned:** email/newsletter subscription, on-site search. RSS is
  the only subscription mechanism.
- No analytics, comments, or third-party scripts today.

## Brand Commitments

- Name: **The Daily Downlink**. Author: **Aaron Cohen**. This is a personal brand
  site and links out to `aaronx.co`.
- The custom domain is bound by the `CNAME` file. Deleting it takes the site offline.
- The name refers to a spacecraft downlink: one scheduled pass in which everything
  the vehicle has been holding finally reaches the ground station. The wordmark's
  arrow-to-bar mark is the signal meeting the ground.
- **Voice is fixed** and specified in `CLAUDE.md`: evidence-first, one clear take per
  story, primary sources over coverage of them, no hype. An explicit banned-phrase
  list applies ("in today's rapidly evolving AI landscape", "game-changer",
  "paradigm shift", and their family). Corporate fluff is a defect, not a matter of
  taste.

## Evidence on Hand

- One published column: `_posts/2026-08-19-welcome-to-the-daily-downlink.md`. It
  doubles as the canonical house-format example the daily agent copies, so its
  structure is a product artifact.
- Every source URL cited in it was verified to resolve before being published.
- **Nothing else exists yet.** There are no readers, subscribers, testimonials,
  press mentions, customers, case studies, or performance figures. Future work must
  not fabricate any of these, and must never invent source URLs, benchmark numbers,
  quotes, companies, or people.

## Product Principles

1. **A take, or it doesn't run.** Commentary is the product and summary is the
   fallback slot. A highlight that restates the news has failed and belongs in
   The Rest.
2. **The record is permanent and public.** Because success is a dated track record,
   published URLs stay stable and history is never rewritten. Corrections are made
   visibly, never by silently editing an old call.
3. **The publish path stays trivially simple.** One markdown file, one push. Every
   additional moving part is a new way for an unsupervised daily agent to break the
   site, and there is no human to catch it.
4. **Cite primary sources, verified.** Never cite a source without checking it
   exists.
5. **Optimise for the reader's judgment, not for reach.** No growth mechanics that
   trade credibility for distribution.
