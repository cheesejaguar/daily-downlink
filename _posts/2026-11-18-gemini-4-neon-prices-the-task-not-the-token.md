---
title: "Gemini 4 Neon prices the task, not the token"
date: 2026-11-18 14:20:00 -0800
excerpt: "Google launched Gemini 4 Neon today at $3/$15 per million tokens with a 1M-token context, claiming Carbon-class agentic work at 32% lower cost per task — a bet that fewer steps, not a lower sticker, is the saving."
categories: [commentary]
draft: false
---

Google shipped Gemini 4 Neon this afternoon: a 1M-token-context model at $3 per million input tokens and $15 per million output, with cached input at $0.15, live in the Gemini API and AI Studio, Gemini for business, Antigravity for paid AI Pro and Ultra subscribers, and the Gemini app. Google's scorecard puts it at #3 overall on the Artificial Analysis Intelligence Index at its xhigh thinking level (61), #2 on the Vals Index (70.9%), #2 on the new Agent Arena Index (1,336), and #1 on the AA Coding Agent Index (58.6), with 65.2% on Terminal-Bench 4.1 and 46.2% on FrontierCode 2.0. The price is the argument: Carbon and Argon are $2/$10 through November 30 but step to $4/$20 on December 1; Neon at $3/$15 is 50% above today's Carbon card and 25% below the card Carbon will carry in twelve days. Google says Neon is 32% cheaper per task than Carbon at its default high thinking level, and 50–80% cheaper per task than top competing frontier models. That is a per-task claim built on a per-token card, and the two are not the same number.

## The sticker is up; the claim is the step count

**What happened.** Neon carries text, image, audio, video and PDF input, a 1M-token context and four thinking levels, with batch and flex at $1.50/$7.50 and priority at $5.40/$27; every thinking token is billed, and explicit caching is not supported — only implicit caching at $0.15 per million. Google's launch post claims the model sits on the Pareto frontier on both the Vals and Agent Arena indexes at its high setting, with roughly 50% to 80% lower cost per task than top competing frontier models.

**Why it matters.** For an operator the per-token card is not the bill. A $3/$15 model that finishes a coding task in fewer steps and fewer tokens can beat a $2/$10 model that wanders — and a model that does not will quietly raise the cost of the default tier by half. The number to demand is tokens and steps per completed task on your own workload, not Google's index, plus the cache hit rate: a 95% cached-input discount pays nothing if your prompts miss. Google is pre-positioning Neon as the value tier before Carbon's price doubles; if the cost-per-task claim survives independent reproduction, the December step-up is a routing problem, not a price increase. If it does not, the "cheap" tier got 50% more expensive without a capability jump.

_Source: [blog.google](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [9to5google.com](https://9to5google.com/2026/11/18/gemini-4-neon-announcement/) · [ai.google.dev](https://ai.google.dev/gemini-api/docs/pricing)_
