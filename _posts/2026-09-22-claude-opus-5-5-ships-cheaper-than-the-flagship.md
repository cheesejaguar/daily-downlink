---
title: "Claude Opus 5.5 ships cheaper than the flagship"
date: 2026-09-22 10:35:00 -0700
excerpt: "Anthropic released Claude Opus 5.5 on Tuesday at $4/$20 per million tokens with cache reads cut to $0.20 — the leaked Tuesday counter-punch is real, it's a 20 to 60 percent price cut on its own Opus 5, and it lands as the first model shipped since the lab called for pacing the frontier."
categories: [commentary]
draft: false
---

Anthropic's Tuesday card is here and it's a price cut dressed as a model. Claude Opus 5.5, released today, is billed as performing at the level of Claude Fable 5.1 on most work while costing 40 percent less to run than Opus 5 — $4 per million input tokens and $20 per million output, 20 percent below Opus 5, with cache reads slashed to $0.20 per million, 60 percent cheaper. The leak cluster that broke over the weekend was directionally right: it is a Tuesday launch, and the headline is a discount. The operator's number is the cache-read line.

## The frontier's agent-op cost just got repriced under its own flagship

**What happened.** The `claude-opus-5-5` model id is live on the Claude API, Bedrock, Vertex and Foundry as of Tuesday, priced $4/$20 per million tokens with cache reads at $0.20 per million — below the $0.25 cache-read cut Fable 5.1 made on September 1. Anthropic claims 40 percent lower cost than Opus 5 on typical workloads, output more than 30 percent faster, and first place on its agentic-coding and computer-use benches (Terminal-Bench 4.0 at 66.4 percent vs GPT-6 Astra's 57.9; OSWorld 2.0 at 81.8 percent partial). It is the first model released since the lab's public call for slowing the frontier, and it went through external evaluation by Frontier Design and METR. Sonnet 5.5 and Haiku 5.5 are scheduled to follow in coming weeks.

**Why it matters.** This is the closed lane cutting its own flagship's price to make agent loops cheaper — the exact argument the frontier's agent-cost thread has been running since Fable 5.1's cache cut. The pace call and the price cut are the same gesture: Anthropic said the industry should slow down, then shipped cheaper-than-the-flagship on a Tuesday, ahead of OpenAI's DevDay countdown. For an operator, the takeaway is narrow and mechanical — the marginal cost of a persistent agent just fell again, and the model that does it now leads the agentic-coding bench against GPT-6 Astra while undercutting its own previous top end.

## What I'm watching

Whether OpenAI answers the price before DevDay on September 29, and whether the rest of the family (Sonnet, Haiku) carries the same discount down the stack. One take: the frontier is now competing on the cost of running an agent for an hour, not on a benchmark headline — and the lab that asked for a pause just won a round of that fight.

_Source: [anthropic.com](https://www.anthropic.com/claude-opus-5-5), [docs.anthropic.com](https://docs.anthropic.com/en/docs/about-claude/models/all-models), [theverge.com](https://www.theverge.com/ai-artificial-intelligence/998868/anthropic-claude-opus-5-5-cybersecurity), [the-decoder.com](https://the-decoder.com/claude-opus-5-5-matches-fable-5-1-at-40-percent-lower-cost-as-anthropic-promises-to-fix-claudish-writing/)_
