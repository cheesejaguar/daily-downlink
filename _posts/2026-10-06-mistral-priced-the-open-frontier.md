---
title: "Mistral gave the open frontier a price, and China's open labs got the war chest"
date: 2026-10-06 11:30:00 -0700
excerpt: "Mistral opened a public preview of Large 4 with a live price card and weights promised for October 27, DeepSeek is close to raising at least $12 billion with Tencent and CATL at the head, Moonshot closed a final round near $50 billion, and Oakland votes today on pausing new data centers — the open layer spent the day pricing itself and raising money while its physical base hit a permitting wall."
categories: [commentary]
draft: false
---

The open layer spent Tuesday behaving like an industry with a balance
sheet. Mistral opened a public preview of Large 4 — a trillion-parameter
MoE with a price on the card and weights promised for the end of the
month — the first real number on the open frontier since it settled into
named floats. The money moved in the same window: DeepSeek is close to
raising at least $12 billion with Tencent and CATL making the biggest
commitments, and Moonshot just closed its final private round at a $50
billion valuation on the way to a Hong Kong IPO. Underneath both races,
the Bay Area's cities are voting on whether the megawatts behind the next
buildout get a permit at all. Open weights, open wallets, and a permitting
wall.

## Mistral published the price before the weights — and left the license for later

**What happened.** Mistral launched a public preview of Mistral Large 4
("le Chonk") today: a natively multimodal MoE with roughly a trillion
total parameters and 49 billion active, plus a million-token
context window, trained from scratch in about two months on 3,800 Grace
Blackwell GPUs in Mistral's own European data centers at roughly 10
megawatts. The API is live in Mistral Studio at $0.68 per million input
tokens and $2.09 output, and the weights are promised for October 27. It
is the first model out of September's €3B round, and Mistral positions it
as stronger than any open-weight model built in the US or Europe, leaning
on the sovereign-defense pitch: open weights that a bank or a government
can run under its own policy, where Mistral quotes a top-five global
security score. The independent tracker that produced that number also
puts Large 4's preview at an Intelligence Index of 38 — 64th of 225 — on
general intelligence.

**Why it matters.** What shipped today is not the model; it's the price
card and the deadline. For an operator that distinction is the point. In a
week of named floats — Reflection's Beam [unveiled yesterday](/2026/10/05/the-open-weights-race-finally-has-a-name/)
with a spec, a waitlist, and a promised Apache license but no price —
Mistral committed the number you can actually plan against: at $0.68/$2.09
it lands below the closed pair's flagship cards — Claude Opus 5.5 at $4/$20
and GPT-6 Sol at $2/$10, both since the mid-September [duopoly cuts](/2026/09/27/sunday-zeitgeist-the-floor-and-the-ceiling-left-the-lab/) —
several times cheaper on input and five-to-ten times on output, wedging back
into the [open-weights pricing lane](/2026/08/20/open-weights-get-pricing-power/).
But it only gave two of the three things open delivery depends on: pricing
is a commitment, weights are a delivery, and the license is a contract.
Mistral's Large 3 and Small 4 shipped Apache; Medium 3.5 went modified MIT;
Large 4's terms are, so far, just described as "open." And on the numbers,
the sovereign-flagpole framing is already under pressure — the same index
that backs its cyber claim ranks it mid-table on intelligence, so read the
benchmarks the way you read any vendor's pressure-tested tape: as targets,
not results, until October 27 lets you run your own.

_Source: [mistral.ai](https://mistral.ai/news/mistral-large-4/), [thenextweb.com](https://thenextweb.com/news/mistral-releases-large-4-a-1-trillion-parameter-open-weight-ai-model), [cellcog.ai](https://cellcog.ai/blog/mistral-large-4), [artificialanalysis.ai](https://artificialanalysis.ai/models/mistral-large-4)_

## The war chest is following the volume tier

**What happened.** Bloomberg reports DeepSeek is close to securing at
least ¥80 billion (~$12 billion) in its next round — Tencent and CATL have
committed among the largest amounts, the final tally on signed term sheets
could approach ¥100 billion, and the financing "closes soon." It is still
in talks, not closed, and it sets up an early-2027 IPO. The figure
upsizes [the $7.5B that finalized last month](/2026/09/24/deepseek-crossed-1b-revenue-and-finalized-a-7-5b-round/).
Separately, Moonshot — the Kimi K3 lab — has closed its final private
round at roughly $50 billion, up from about $31.5 billion this summer, and
is preparing a Hong Kong IPO in Q1 2027, mulling a raise of up to $5
billion; by its own numbers ARR ran from about $300 million in June toward
$1 billion now.

**Why it matters.** The money is following the volume tier, and the volume
tier is Chinese open weights. These are the labs whose cheap tokens
operators actually route to — DeepSeek moved more than twice Google's
gateway traffic at a fraction of the price on Vercel's [August production
index](/2026/08/30/the-advisory-is-the-attack/), and Kimi K3 sits at the
top of the open-artifact pile. A war chest of this size makes the open
lane's price discipline structural rather than charitable: the distribution
that [got a balance sheet](/2026/09/04/open-models-got-a-balance-sheet/)
just got a bigger one, and the labs that set the price floor can now afford
to undercut for years. The operator-relevant number is not the headline
valuation; it's what a funded DeepSeek and a funded Moonshot do to the
price of the bucket you currently run on. The West's entry in the same
round is [Mistral's €3B](/2026/09/08/mistral-europes-biggest-private-round/)
paying for a trillion-parameter flagship — the same race, and the checkbook
sizes are not close.

_Source: [thenextweb.com](https://thenextweb.com/news/deepseek-12bn-funding-round-tencent-catl), [ca.finance.yahoo.com](https://ca.finance.yahoo.com/news/moonshot-ai-eyes-hong-kong-085637655.html), [businesstimes.com.sg](https://www.businesstimes.com.sg/companies-markets/moonshot-said-eye-hong-kong-ipo-early-2027-after-value-hits-us50-billion)_

## The buildout's binding constraint has moved from silicon to the council chamber

**What happened.** Oakland's full council votes today on a 45-day
moratorium on new data centers — a pause on land-use agreements and
entitlements while the city writes rules, prompted in part by a planned
20,000-square-foot conversion downtown. It is one vote of two in the same
window: San Jose's final uniform-standards community session follows
October 15, ahead of a December council vote, with a project pipeline the
city puts at more than 30. Gilroy and Richmond have already passed their
own 45-day moratoriums, and San Francisco supervisors floated one — the
pattern [this column tracked into ordinance language](/2026/09/18/physics-billed-the-frontier/)
in September is becoming the region's default.

**Why it matters.** The constraint that used to be silicon is now a
permitting agenda, and the megawatt allocation in the power-strained Bay
Area has become a municipal decision. Oakland's stated concerns — noise,
grid strain, water — are all line items in what it costs to run compute at
load, and a pause caps the buildout's supply side no less than a chip
shortage does. Yesterday's column [flagged these two votes as the
landing dates](/2026/10/05/new-york-put-the-model-makers-under-oath/)
and flagged the deeper point: the zoning clock is [one of the only inputs
to AI pricing no rate card captures](/2026/10/03/the-price-of-ai-is-no-longer-on-the-rate-card/).
If you are planning regional inference density anywhere near here, the
city council is now a supply-side counterparty — read its agenda the way
you used to read lead times.

_Source: [nbcbayarea.com](https://www.nbcbayarea.com/news/local/oakland-city-council-data-center-vote/4153917), [oaklandside.org](https://oaklandside.org/2026/09/23/oakland-data-center-moratorium-committee-appoval), [sanjoseinside.com](https://www.sanjoseinside.com/news/city-of-san-jose-invites-residents-to-help-regulate-data-center-development)_

## The Rest

- **Lambda is raising up to $4 billion at a $14.5 billion pre-money before a planned IPO** — the neocloud that rents frontier capacity, including to Anthropic [on the 09-01 deal](/2026/09/01/nvidia-holds-the-lease-behind-anthropics-35b-lambda-deal/), gets a Blackstone- and Coatue-led war chest; the compute-finance layer now raises like a frontier lab. [wsj.com](https://www.wsj.com/tech/ai/ai-neocloud-lambda-is-raising-4-billion-in-final-round-before-planned-ipo-568182f9)
- **Anthropic's IPO prospectus is real enough to pay its executives — Amodei pulled roughly $18M last year** — Reuters has the S-1 and the pay is middle of the tech-CEO pack, with co-founders pledging 80% of equity to charity; the [$2T November-IPO arc](/2026/09/19/the-frontier-priced-its-future-decisions-priced-at-zero/) finally has a dollar figure on its principals. [nypost.com](https://nypost.com/2026/10/06/business/anthropic-ipo-filing-reveals-pay-of-ceo-dario-amodei-daniela)
- **A state judge dismissed the lawsuit over San Jose's ~500-camera Flock network** — the ALPR system survives the challenge the city's critics [pushed back against in early October](/2026/10/01/an-agent-that-hacks-gets-a-named-defendant/); the fight over who holds location data and under what warrant keeps running on the same track as the agent-accountability one. [kqed.org](https://ww2.kqed.org/news/2026/10/05/south-bay-judge-rules-san-joses-flock-cameras-dont-invade-privacy)
- **Nvidia's market cap hit a record intraday high near $5.8 trillion** — the day's money theme in one ticker: the silicon layer keeps printing while the labs above it price and raise. [finance.yahoo.com](https://finance.yahoo.com/technology/article/nvidia-stock-hits-all-time-high-as-market-cap-closes-in-on-6-trillion-141332917.html)
- **Britain reportedly moves to expel Israeli diplomats if the East Jerusalem consulate closes** — the sharpest bilateral rupture in the framework yet, and a reminder that the region the morning brief watches each day stays structurally volatile into next week. [jpost.com](https://www.jpost.com/israel-news/article-910687)

## What I'm watching

Tomorrow at 10:00 PT is the Microsoft/Nvidia RTX-Spark Windows/Surface
event — the tease [this column dated](/2026/10/01/an-agent-that-hacks-gets-a-named-defendant/)
now ships or fails on official pricing and availability, and nothing else
counts. Later this month the two open-weights re-arms land on the same
track: Mistral's October 27 weight drop — license terms included — and
Reflection's promised Beam weights, the moment anyone can test Beam's
3-4x efficiency claim or Large 4's sovereign-flagpole claims with their
own evals. And the money lane has a close-watch set: a confirmed DeepSeek
round, a closed OpenAI $30B, and Moonshot's Hong Kong paperwork reaching
the F-1 stage.
