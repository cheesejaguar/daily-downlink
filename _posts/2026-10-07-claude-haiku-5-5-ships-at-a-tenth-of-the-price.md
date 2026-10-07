---
title: "Claude Haiku 5.5 ships — the entry tier just matched Luna at a tenth of the price"
date: 2026-10-07 12:12:00 -0700
excerpt: "Anthropic shipped Claude Haiku 5.5 this morning at $0.10/$0.50 per million tokens — ten times below Haiku 4.5's listed rates, matching GPT-6 Luna and cutting the cost of running it by about 75% per task — the budget tier just became the price war's latest front."
categories: [commentary]
draft: false
---

Anthropic ended the budget tier's waiting game this morning: Claude Haiku
5.5 is live on all platforms under `claude-haiku-5-5`, priced at $0.10 per
million input tokens and $0.50 per million output (prompts below 100k
tokens), versus Haiku 4.5's $1.00/$5.00. That is a ten-fold cut on both
axes — a 90% drop on listed rates — and Anthropic says the effective cost of
running it lands about 75% lower per task once token consumption is counted.
The rates put it at exact parity with OpenAI's GPT-6 Luna, and the 5.5 family
closes out the way it opened: every tier in the lineup has now shipped cheaper
or faster (or both) than the one it replaced.

## The budget tier just became the price war's newest front

**What happened.** Haiku 5.5 — which Anthropic positions as its cheapest,
fastest, and most capable small model yet — is available now across AWS,
Google Cloud, Azure, and the Claude Platform. Cache reads fall to $0.01 per
million (from $0.10), and Anthropic is also halving Sonnet 5.5's cache-read
price, which it says makes Sonnet about 20% cheaper on most agentic work,
plus adding a monthly API credit for Max and Team subscribers. The model
id is `claude-haiku-5-5`.

**Why it matters.** This is the price war going vertical. The frontier
headlines have been about flagships and open weights, but the whole Claude
5.5 family has now shipped as a pricing story — Opus 5.5 below its
predecessor, Sonnet 5.5 at flat rates with better cost-per-task, and now the
high-volume tier at a tenth of the price and locked to Luna parity. For an
operator the signal is concrete: the budget-call and agent-subagent lane now
has a rate card you can budget against, and the agentic-economics detail is
the cache read at one cent — when the cost of a repeated system prompt
approaches zero, the unit economics of a swarm of subagents change. The
forward take is that Anthropic has stopped competing on the headline model
and started competing on the bill, at the exact tier most usable AI workloads
actually live.

_Source: [anthropic.com](https://www.anthropic.com/claude-haiku-5-5), [venturebeat.com](https://venturebeat.com/technology/anthropic-launches-claude-haiku-5-5-with-90-api-price-reduction-matching-gpt-6-luna)_
