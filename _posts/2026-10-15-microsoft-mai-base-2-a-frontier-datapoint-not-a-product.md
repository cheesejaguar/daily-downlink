---
title: "Microsoft claims a 2.8T frontier base train at DeepSeek-beating efficiency — nobody can run it yet"
date: 2026-10-15 18:20:00 -0700
excerpt: "Microsoft AI says it finished pre-training MAI-Base-2, a 2.8T-parameter MoE base model trained in 38 days on 16,000 Nvidia GB200 GPUs, claiming an estimated 4.2–12.3x compute-efficiency advantage over DeepSeek-V4-Pro-Base. There are no weights, no API, no price, and post-training is unfinished — a claim about frontier training economics, not a product."
categories: [commentary]
draft: false
---

Microsoft AI says it finished pre-training MAI-Base-2, a 2.8-trillion-parameter
mixture-of-experts base model with 80 billion active parameters, trained in 38
days on 16,000 Nvidia GB200 GPUs. The lab claims it reaches a lower training
loss than every open-weight model it tested against, and an estimated 4.2–12.3x
compute-efficiency edge over DeepSeek-V4-Pro-Base. None of it is usable today:
there are no weights, no API, no price, and post-training has not finished.
This is a claim about the cost of frontier training dressed up as a model
release — the operator-relevant part is what Microsoft now asserts about scale,
not a product to adopt.

## The efficiency claim is the story; the product does not exist yet

**What happened.** Microsoft AI announced on Oct 15 that MAI-Base-2 completed
pre-training: a MoE with 2.8T total and 80B active parameters, 102 layers,
native vision in the mix (about 18% image in a ~50-trillion-token corpus), and
a Muon optimizer — trained on 16,000 Nvidia GB200 GPUs over 38 days in
August–September, at a reported 21% average MFU and 89% goodput. Microsoft
claims a lower bits-per-byte than every open-weight model it compared against
(DeepSeek-V4-Pro-Base, Kimi K3, Qwen3.8, Xiaomi MiMo-V2.6-Pro-RL) and an
estimated 4.2–12.3x FLOP-efficiency gain over DeepSeek-V4-Pro-Base, or
6.3–12.7x over its own MAI-Base-1. No weights, no API, no availability date,
no pricing; post-training is under way and MAI-Base-3 is already in
preparation. It runs on Nvidia silicon — Microsoft's own Maia 300 does not
reach production until 2027.

**Why it matters.** The number every downstream operator pays is what a trained
base model costs, and Microsoft is now publicly bidding on that number: it
frames MAI-Base-2 as lower-loss than the strongest open base it tested, at a
fraction of the FLOP. Hold two caveats. First, the efficiency figure is a
fitted-scaling-law estimate, not a matched-budget run — the lab itself pencils
in an asterisk because DeepSeek trained on far fewer FLOP overall, and no
independent reproduction exists yet. Second, scale and availability sit at the
opposite end of the spectrum from this morning's 24GB Nemotron Bolt / RTX-Spark
local tier: 2.8T parameters means roughly 2.8 TB of weights at 8-bit, 5.6 TB at
16-bit — server-cluster memory, not a desk. Read it as Microsoft buying
optionality against its OpenAI dependency (it stresses original data over
distillation and plans weight-licensing through Azure AI Foundry), not as
frontier supply arriving today.

_Source: [microsoft.ai](https://microsoft.ai/news/frontier-pre-training-at-microsoft-ai/) · [investing.com](https://www.investing.com/news/stock-market-news/microsoft-ai-unveils-28-trillionparameter-model-claims-efficiency-gains-4952355) · [pasqualepillitteri.it](https://pasqualepillitteri.it/en/news/24354/microsoft-mai-base-2-trillion-parameters)_

## What I'm watching

Whether an independent run reproduces the 4.2–12.3x efficiency claim, whether
the tuned successor reaches Azure AI Foundry the way MAI-Base-1's lineage did
with MAI-Thinking-1, and — the question this beat keeps circling back to —
whether any of it ever becomes obtainable under a license you can actually
build on.
