---
title: "OpenAI's Jalapeño is beating the current NVIDIA flagship on tokens per watt"
date: 2026-08-25 18:30:00 -0700
excerpt: "Bloomberg-reported results plus an in-lab SemiAnalysis run say OpenAI's in-house Jalapeño inference chip beats NVIDIA's GB300 on work-per-watt and latency — the first time a frontier lab's custom silicon has publicly beaten the incumbent on the axis the whole datacenter buildout is stuck on."
categories: [commentary]
draft: false
---

OpenAI's first in-house chip went from rumor to benchmark today. Bloomberg reports
that on a public benchmarking system, its Jalapeño inference processor — an ASIC
built with Broadcom, running at 700 watts — outperformed NVIDIA's current flagship
GB300 on both work per unit of power and speed of response. SemiAnalysis
published the same day after an in-lab run of its InferenceX suite, writing that
Jalapeño beats every NVIDIA, AMD, and Google chip it has tested on output tokens
per all-in utility megawatt. The frontier's custom-chip lane just posted its
first credible measured win against the incumbent, a day before NVIDIA reports.

## The first number that matters to an operator is tokens per watt

**What happened.** Bloomberg reports OpenAI's Jalapeño led NVIDIA's GB300 — the
leading option on the public benchmarking system used — on AI work per unit of
power and response speed, at 700 watts, per OpenAI hardware chief Richard Ho.
SemiAnalysis was invited into the labs and ran its InferenceX suite in person:
Jalapeño beats Blackwell on perf-per-watt across almost every scenario without
speculative decoding or prefill-decode disaggregation, serving roughly 700
tokens/sec/user at concurrency 1 on DeepSeek R1 and about 1,400 on
Kimi-K2.5/GPT-OSS. Against the HBM4 Vera Rubin that is now shipping, it is
head-to-head on perf-per-dollar and ahead on output tokens per MW even before
speculative decoding lands. It is not designed for training; initial deployment
is slated for later this year with production ramping through 2027; Ho presents
at Hot Chips at Stanford tomorrow.

**Why it matters.** You cannot buy this chip. Jalapeño is OpenAI's own inference
economics, so its direct effect on you is the future price of GPT API tokens,
not your hardware shelf — the benchmark is a forecast, and the rate card is the
receipt. But the axis it wins on is the axis everything in this buildout is
blocked on: megawatts, not sockets or flops. When a model lab shows a 700-watt
ASIC beating the current flagship on work-per-watt on a public benchmark, with
the run independently replicated in a lab, "build the chip" stops being a hedge
for labs that can afford it, and the price floor under all of inference moves a
rung down. Read the token price, run tomorrow's Hot Chips numbers, and treat the
Vera Rubin shipping-now-vs-Jalapeño-ramping-2027 gap as the real race.

_Source: [finance.yahoo.com](https://finance.yahoo.com/technology/ai/articles/openai-claims-chips-outperform-nvidia-140001612.html), [newsletter.semianalysis.com](https://newsletter.semianalysis.com/p/openai-jalapeno-better-than-nvidia), [openai.com](https://openai.com/index/openai-broadcom-jalapeno-inference-chip)_

## What I'm watching

Two things: what Richard Ho actually shows at Hot Chips tomorrow, and whether
Jalapeño's measured advantage survives contact with Vera Rubin once both are in
production — Rubin ships now, Jalapeño ramps through 2027. The scoring to do
next: what the second generation (already far along, taping out in the coming
months) does to GPT token pricing once OpenAI's own silicon starts carrying
frontier flagship inference.
