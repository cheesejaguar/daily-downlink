---
title: "Sonnet 5.5 shipped Monday at unchanged prices, cheaper per task than the flagship era"
date: 2026-09-28 12:18:00 -0700
excerpt: "The most-watched leaked card of the month stopped being a leak this afternoon: Claude Sonnet 5.5 is live at unchanged Sonnet 5 prices, roughly 30% faster and up to 30% cheaper per task, and it is the first Sonnet to carry the sandbox-escape cyber safeguards and the anti-distillation classifiers the containment era has been building toward."
categories: [commentary]
draft: false
---

The card this blog has watched all month stopped being a leak this afternoon. Claude Sonnet 5.5 shipped Monday on Anthropic's own page — the same page the 11:00 column said it was waiting on — priced identically to Sonnet 5 at $2 per million input tokens, $10 per million output, and $0.20 per million on cache reads, but roughly 30% faster and up to 30% cheaper per task because it spends fewer tokens to finish the work. It is also the first Sonnet to ship the two feature sets that define this moment: the cyber safeguards that stop a model attempting to escape its sandbox, and safety classifiers against reasoning-extraction distillation. The containment platform left the lab this morning as software; the mid-tier shipped with containment built in this afternoon.

## The mid-tier caught up to the price war without moving the list price

**What happened.** Claude Sonnet 5.5 (model id `claude-sonnet-5-5`) is available now on the Claude Platform, Amazon Bedrock, Google Vertex and Azure with zero data retention. Anthropic reports Terminal-Bench 4.0 at 70.6% against Sonnet 5's 10.3%, CursorBench 4.0 within about two points of Opus 5.5, and GDPval-AA nearly level with the flagship while running ~400 points above Sonnet 5. Because its cybersecurity capability is comparable to Opus 5's, it launches with the cyber safeguards and fallbacks previously reserved for the most capable models, plus distillation-resistant reasoning extraction and a preserved-thinking change that binds Claude's thinking to the account that created it. The one hard migration: anyone running Sonnet with thinking off must move to the new `between_tools` setting before switching, or the change silently bites.

**Why it matters.** The price war's bottom end just moved in the operator's favor in a specific way: the list price didn't drop, but the per-task bill did, because the model needs fewer output tokens for the same work (Zendesk's test: ~20% faster ticketing; Balyasny: 121k tokens per answer vs 497k on Sonnet 5). Yesterday's column flagged Sonnet 5.5 as where "the price war's bottom end actually lives"; it now ships at exactly the $2/M figure the A/B-tests described, undercut the cheap-flagship story by keeping the workhorse tier cheap, and threads a recurring cost into every agent loop without waiting for a repricing. The clever part is what it bundles at that price: the sandbox-escape controls turn containment from a platform feature into the default mid-tier posture hours before tomorrow's DevDay, when OpenAI has to answer a model that matches its enterprise-tier agentic coding at a fifth of the per-task cost.

## What I'm watching

Whether DevDay answers with price or with a differentiator that isn't on the rate card, and whether the `between_tools` migration trips long-running Sonnet workloads between now and then. Haiku 5.5 rounds the family out in the coming weeks, which is the real test of whether the cheap-per-task logic survives at high volume.

_Source: [anthropic.com](https://www.anthropic.com/claude-sonnet-5-5), [theverge.com](https://www.theverge.com/ai-artificial-intelligence/1001591/anthropic-is-launching-claude-sonnet-5-5)_
