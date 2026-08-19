# The Daily Downlink — publishing contract

You are publishing to a live blog. Read this file before you touch anything.

- **Live at:** <https://blog.aaronx.co>
- **Repo:** `cheesejaguar/daily-downlink` (public), branch `main`
- **Built by:** GitHub Pages' native Jekyll. No GitHub Actions, no build step, no CI.
- **Author:** Aaron Cohen

Pages rebuilds automatically on every push to `main`. There is nothing to run,
nothing to compile, and nothing to deploy.

---

## The entire publish procedure

1. Create **exactly one** file: `_posts/YYYY-MM-DD-slug.md`
2. Commit it.
3. Push to `main`.

That's it. Do not touch any other file unless you are explicitly asked to.

---

## Filename rule

```
_posts/YYYY-MM-DD-slug.md
```

- Zero-padded date: `2026-08-19`, never `2026-8-19`.
- `slug` is lowercase, words separated by hyphens, ASCII only, no spaces, no
  punctuation. `-` only.
- Extension is `.md`.

**The filename becomes the URL.** `_config.yml` sets
`permalink: /:year/:month/:day/:title/`, so:

```
_posts/2026-08-19-welcome-to-the-daily-downlink.md
  ->  https://blog.aaronx.co/2026/08/19/welcome-to-the-daily-downlink/
```

That mapping is the whole URL validation scheme. Get the filename right and the
URL is right by construction. A malformed filename is not an error — Jekyll
simply **ignores the file** and your post silently never appears. This is the
single most likely way to fail. Check the filename twice.

---

## Front matter

Every post opens with exactly this block, between two `---` lines, as the very
first bytes of the file:

```yaml
---
title: "Sentence case, in double quotes"
date: 2026-08-19
excerpt: "One sentence. Used on the home page and for SEO/social description."
categories: [commentary]
draft: false
---
```

| Key | Required | Notes |
|---|---|---|
| `title` | yes | Always double-quoted. A colon in an unquoted title breaks the YAML. |
| `date` | yes | `YYYY-MM-DD`, must match the filename's date. |
| `excerpt` | yes | One sentence, quoted. Shown on the home page; don't skip it. |
| `categories` | no | `[commentary]` is the default. |
| `draft` | yes | Always `false` when publishing. See the note below before using `true`. |

`layout` is **not** needed — `_config.yml` applies `layout: post` to everything
in `_posts/` automatically. Don't add it.

**On `draft: true` — know exactly what it does.** It hides the post from the home
page, the archive, and the RSS feed. It does **not** unpublish it: the page is
still built at its real URL and still appears in `sitemap.xml`, so anyone with
the link (or a search crawler) can reach it. If you need a post to genuinely not
exist, either don't commit the file, or use Jekyll's native `published: false`,
which stops the page being generated at all.

Note: `future: true` is set in `_config.yml`, so a post dated today will never
be silently dropped for timezone reasons. Do not rely on this to post-date
things; use the real date.

---

## Post structure

Copy [`_posts/2026-08-19-welcome-to-the-daily-downlink.md`](_posts/2026-08-19-welcome-to-the-daily-downlink.md)
and replace its contents. That file is the canonical example — when this
document and that file disagree, the file wins.

The shape, in order:

### 1. Lede

5–6 lines of plain prose immediately after the front matter. No heading above
it. State the day's throughline. It renders larger than body text, so it carries
the post.

### 2. Two or three highlights

Each highlight is an `##` heading followed by exactly three parts:

```markdown
## A heading that states the take, not the topic

**What happened.** The factual account. Short. No adjectives doing argumentative
work.

**Why it matters.** The commentary. This is the reason the post exists.

_Source: [domain.com](https://full-url-here)_
```

- The `**What happened.**` and `**Why it matters.**` labels are literal. Keep
  the bold and the trailing period; the stylesheet targets them.
- The source line is *italic*, on its own line, and is the **only** thing in its
  paragraph — the CSS styles `p > em:only-child` as the quiet attribution line.
  Link text is the bare domain.
- **Why it matters** must contain an actual argument. If it restates What
  happened in different words, the highlight has failed and belongs in The Rest.

### 3. The Rest

4–6 quick hits under a `## The Rest` heading:

```markdown
## The Rest

- **Thing** — one line on why it's here. [domain.com](https://url)
```

### 4. What I'm watching (optional)

A short forward-looking paragraph under `## What I'm watching`.

---

## Voice

A systems engineer's eye on AI. Someone who builds things that have to work
beyond the lab, writing for a technical reader.

- **Evidence first.** Link the primary source — the paper, the filing, the
  changelog. Not a news article about the primary source.
- **One clear take per story.** Commit to it. Hedging every direction is the
  same as saying nothing.
- **Separate the demo from the product.** Ask what it costs to run, at load,
  when it's wrong.
- **Never cite a source you have not verified exists.** No invented URLs, no
  invented benchmark numbers, quotes, companies, or people. If you cannot verify
  it, leave it out.
- Second person and contractions are fine. Jokes are fine if they're dry.

**Banned outright.** Do not write these, or anything in their family:

- "In today's rapidly evolving AI landscape…"
- "game-changer", "revolutionary", "paradigm shift", "seismic", "unprecedented"
- "It's important to note that…", "Only time will tell.", "The future of X is here."
- Opening a post by announcing that AI is moving quickly.
- Ending a section with a rhetorical question standing in for an argument.

---

## Hard constraints — breaking these breaks the site

1. **Never delete or edit `CNAME`.** It contains `blog.aaronx.co` and is what
   binds the custom domain. Deleting it takes the site offline.
2. **Never add a Jekyll plugin** beyond those already in `_config.yml`. GitHub
   Pages' native build only permits a whitelist; the usable ones are
   `jekyll-feed`, `jekyll-seo-tag`, `jekyll-sitemap`, and `jekyll-paginate`
   (the first three are enabled; pagination is deliberately not used). Any other
   gem causes the build to fail outright.
3. **Never add `.github/workflows/`.** This site uses Pages' native build. An
   Actions workflow will take over deployment and change the failure modes.
4. **Never change `url` or `baseurl`** in `_config.yml`. They are
   `https://blog.aaronx.co` and `""` respectively.
5. **Keep `_config.yml` minimal.** Every key in it is load-bearing. Don't add
   settings speculatively.
6. **One post per push.** Don't batch several days into one commit.
7. **Never rewrite history** on `main` (no force-push, no rebase of pushed
   commits). Published URLs must stay stable.

---

## Verifying a push worked

Pages builds in roughly a minute. To confirm:

```bash
gh api /repos/cheesejaguar/daily-downlink/pages/builds/latest \
  --jq '{status, error: .error.message, commit: .commit}'
```

`status` should be `built`. If it's `errored`, `error.message` says why — fix it
and push again. Then confirm the post is actually live at its URL.

If the build says `built` but your post isn't on the home page, the cause is
almost always one of:

- the filename doesn't match `YYYY-MM-DD-slug.md`, or
- `draft:` is `true`.

---

## Local preview (optional, for a human)

Not needed to publish. Requires Ruby 3.3.x:

```bash
brew install ruby@3.3
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve
```

`Gemfile` pins `github-pages` 232, which is exactly what Pages runs
(Jekyll 3.10.0 / Ruby 3.3.x — see <https://pages.github.com/versions.json>).
A clean local build means a clean deploy.

---

## Layout of this repo

```
CNAME                     custom domain — do not touch
_config.yml               site config — do not touch
CLAUDE.md                 this file
PRODUCT.md                durable product context — internal, never published
Gemfile                   local preview only; Pages ignores it
index.html                home: newest column + archive
about.md                  about page
404.html                  not-found page
_layouts/                 default, post, page
_includes/                head, header, footer
assets/css/style.css      all styling, vanilla CSS
assets/favicon.svg
_posts/                   >>> the only directory you add files to <<<
```
