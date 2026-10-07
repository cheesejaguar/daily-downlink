---
title: "RTX Spark got a real price this morning — and memory wrote it"
date: 2026-10-07 11:30:00 -0700
excerpt: "Microsoft and Nvidia put actual numbers on the personal-AI tier from the San Francisco stage — Surface Laptop Ultra from $2,599 with pre-orders open, Dev Box at $5,999, first laptops October 16 — the price this column dated through a summer of floats, landing the same way every other price in this market has: memory sets the floor, and the petaflop lives at the top of the ladder."
categories: [commentary]
draft: false
---

The local-AI tier stopped being a tease at 10:00 PT this morning, when
Microsoft and Nvidia put real numbers on RTX Spark from the San Francisco
stage: the Surface Laptop Ultra opens at $2,599 with pre-orders live, the
developer-focused RTX Spark Dev Box lists at $5,999, and the first laptops
land October 16. Six OEMs are in at launch, with Acer and GIGABYTE
following. It is the price [this
column dated](/2026/10/01/an-agent-that-hacks-gets-a-named-defendant/)
through a summer of floats and leaks, and it lands the way every other price
in this market has: the entry SKU is a laptop story, but the config that can
actually hold a 120-billion-parameter model is a workstation story. The same
morning the open agent layer [got a war chest](/2026/09/04/open-models-got-a-balance-sheet/),
and the Bay Area's buildout hit pause in two cities at once.

## RTX Spark priced, and the petaflop is at the top of the ladder

**What happened.** Microsoft opened pre-orders today for the Surface Laptop
Ultra at a $2,599 starting price — the 18-core RTX Spark with 5,120 Blackwell
GPU cores and 24GB of unified memory, scaling up to 128GB on the 20-core
(6,144-core) chip — with the Surface RTX Spark Dev Box (the 128GB desktop
for local development) listing at $5,999. NVIDIA says RTX Spark laptops will
be available from October 16 across the launch OEMs;
Microsoft positions the Ultra as its most powerful laptop ever, running
up-to-120B-parameter models on-device with ~1 petaflop of FP4. The NVIDIA
page still said "notify me" for part of the morning — the numbers came from
the stage and the pre-order links, which is the part that counts.

**Why it matters.** Six months of analyst floats put this platform anywhere
from $1,799 (the low end of the channel's early estimates) to a $2,899
high-end guess to a $2,999.99 HP leak, and the real entry price landed
mid-stack at $2,599. That
is fine, but it is not the story. The story is that the machine you actually
buy to run a frontier-class model locally — the config with the memory for a
120B model — is the $5,999 Dev Box or the top of the laptop ladder, and that
is [the same ladder that inverted on the DGX Spark](/2026/10/02/the-64gb-dgx-spark-costs-more-than-the-128gb-did/)
last week when a 64GB SKU listed above what 128GB launched at. Nobody should
buy the $2,599 entry expecting to run a 120B model on it; the entry price is
the DRAM bill for a laptop, and the real compute is what the headlines
leave out. For an operator this is good news written in the old language:
the personal-AI tier finally has a rate card you can budget against, and the
rate card tells the truth about [what compute costs when memory prices](/2026/10/04/sunday-zeitgeist-the-frontier-became-a-rationing-decision/).
Yesterday's column flagged this event as ships-or-fails on official numbers — [it shipped](/2026/10/06/mistral-priced-the-open-frontier/).

_Source: [windowslatest.com](https://www.windowslatest.com/2026/10/07/microsofts-macbook-pro-killer-has-up-to-128gb-ram-starts-at-2599-and-its-called-surface-laptop-ultra/), [theverge.com](https://www.theverge.com/news/941271/microsoft-surface-rtx-spark-dev-box-specs-availability), [windowscentral.com](https://www.windowscentral.com/microsoft/windows-11/what-to-expect-at-microsofts-special-windows-and-surface-event-on-october-7-surface-laptop-ultra-and-rtx-spark-revealed-new-agentic-os-capabilities-and-more), [videocardz.com](https://videocardz.com/newz/nvidia-and-microsoft-tease-rtx-spark-announcements-for-october-7-windows-event)_

## The lab behind the open agent closed $90M on an enterprise pitch

**What happened.** Nous Research, the startup behind the open-source Hermes
agent, has closed a $90 million round at a $1.5 billion valuation, up from
the $75 million it was reported to be raising this summer, according to WSJ
Pro and Dealroom. The pitch is explicit: enterprises buy open-source
architecture for more control over their data and less dependence on a
specific vendor, and Nous is building commercial seats on top of the agent
whose open weights any self-hoster can already run.

**Why it matters.** This is the open-vs-closed fight arriving at the agent
layer with a real balance sheet attached. The closed labs raised tens of
billions on the promise of holding the frontier behind terms of service; the
open lane just raised $90M to sell the opposite — the same capability, run
under your own policy, on silicon you control. The David-and-Goliath framing
flatters neither side; the operator-relevant fact is that [open models got a
balance sheet](/2026/09/04/open-models-got-a-balance-sheet/) back in
September, and now the open *agent* framework got one. That is the layer
where the workforce actually touches the tools, and it changes what a
self-hosted deployment is: no longer a hobby hedge against a subscription,
but a supported commercial surface. The number to watch is not $90M — it is
what happens to the open license terms as the enterprise seats scale, [the
same tension this column has tracked since the open lanes started
pricing](/2026/08/20/open-weights-get-pricing-power/).

_Source: [wsj.com](https://www.wsj.com/pro/venture-capital/maker-of-open-source-ai-assistant-hermes-secures-90-million-a061c1d7), [dealroom.co](https://dealroom.co/news/160592-nous-research-raises-90m-at-1-5b-valuation-for-open-source-ai)_

## The buildout went from municipal drama to unanimous policy in 48 hours

**What happened.** The Oakland City Council voted 7-0 Tuesday night for a
45-day moratorium on new data-center development, joining San Francisco,
whose supervisors had earlier approved the same pause; Gilroy and Richmond
already had theirs, and Monterey Park has a permanent ban. The next gate in
the region is San Jose's uniform-standards session on October 15, ahead of a
December council vote on a pipeline the city puts at more than 30 projects.

**Why it matters.** Yesterday's column [flagged this exact vote as the
landing date](/2026/10/05/new-york-put-the-model-makers-under-oath/) and
called the buildout's binding constraint "the council chamber"; now the
evidence is unanimous and two cities deep. A moratorium is a 45-day clock,
not a ban — but the message to anyone planning regional GPU density is that
megawatts in the Bay Area are now a land-use matter decided in public
meetings, and [no rate card captures the zoning schedule](/2026/10/03/the-price-of-ai-is-no-longer-on-the-rate-card/).
When both of the Bay's largest cities pause on the same policy 48 hours
apart, the supply side of the buildout has been re-regulated while the
demand side kept bidding prices up [against the physics bill](/2026/09/18/physics-billed-the-frontier/).

_Source: [ktvu.com](https://www.ktvu.com/news/oakland-city-council-approves-45-day-moratorium-new-data-centers), [oaklandside.org](https://oaklandside.org/2026/10/07/oakland-data-center-moratorium-approved), [cbsnews.com](https://www.cbsnews.com/sanfrancisco/news/san-francisco-oakland-data-center-backlash-45-day-moratoriums-approved)_

## The Rest

- **DeepSeek's ≥$12B round is still not closed (14th episode)** — Dealroom now floats it swelling toward ~$15B at a ~$75B valuation ahead of a Shanghai IPO, but "close to securing" is still not "closed," and CITIC prepping the float is IPO-prep, not a round; the [September finalization](/2026/09/24/deepseek-crossed-1b-revenue-and-finalized-a-7-5b-round/) stayed the last closed number all week. [dealroom.co](https://www.dealroom.co)
- **Marvell lifted FY2028 revenue to ~$20B, up from $18B** on AI data-center connectivity silicon, with a path it frames to $70–90B by FY2031 — the cleanest local demand signal in a week where the model makers threw no new cards. [investing.com](https://www.investing.com/news/stock-market-news/marvell-raises-2028-revenue-forecast-on-strong-ai-data-center-demand-4934830)
- **Nvidia's market cap is sitting near a record $5.65 trillion** the day it shipped its first Windows chip — the silicon layer keeps printing while the layer above it raises and the layer below it pauses. [finance.yahoo.com](https://finance.yahoo.com)
- **A suit now says Nvidia's $20B Groq deal took most of the company** — a terms dispute over the December 2025 asset/licensing deal, off-lane legal noise but a marker that the neocloud consolidation lane is adversarial. [timesofisrael.com](https://www.timesofisrael.com)
- **Three years since October 7** — the anniversary's political weight landed heaviest on Israel's internal divisions ahead of an election, while Strait of Hormuz tanker attacks this week hit their highest in any week since the Iran war began. [apnews.com](https://apnews.com), [reuters.com](https://www.reuters.com)

## What I'm watching

- **October 9:** Gemini's free-tier downgrade lands (the consumer lane each tick has docketed) — the first real signal on whether consumer free access is a racket or a funnel.
- **October 15:** San Jose's uniform-standards session — the next and biggest gate on the Bay buildout's 30-plus-project pipeline.
- **October 16:** RTX Spark laptops on sale — whether $2,599 holds off the street, and the first independent shots at that ~120B-on-a-laptop claim.
- **October 27:** Mistral's Large 4 weight drop, license included — the open frontier's next re-arm, now that RTX Spark gives it hardware to run on.
- The money lane's close-watch set: DeepSeek's ≥$12B, OpenAI's $30B at $1.4T, and Moonshot's Hong Kong paperwork.
