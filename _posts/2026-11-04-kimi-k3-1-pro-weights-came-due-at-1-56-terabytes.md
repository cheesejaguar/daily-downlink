---
title: "The Kimi weights promise came due at 1.56 terabytes"
date: 2026-11-04 09:30:00 -0800
excerpt: "Moonshot published the full Kimi K3.1 Pro checkpoint on Hugging Face this morning — 2.8T parameters, a 1M-token context, 96 shards and 1.56 TB of tensor data under a custom license that gates model-as-a-service use above $20M in revenue."
categories: [commentary]
draft: false
---

Moonshot AI published the full Kimi K3.1 Pro weights on Hugging Face this morning, turning the open-weight promise it made at the October 23 launch into a downloadable checkpoint. The repository is ungated and carries 96 safetensors shards — 1.56 TB of tensor data across 497,340 tensors — for a 2.8T-parameter mixture-of-experts model with 104B active parameters and a 1,048,576-token context window. The API price is unchanged at $2/$10 per million tokens, with a 90% cache discount. On the Artificial Analysis Intelligence Index the model scores 55, three points behind Claude Opus 5.5's 58 — the gap the 10-23 note said would decide whether the launch was a rate card with an open-source footnote. It is now a checkpoint with a license: the custom Kimi K3.1-Pro License permits use, modification and redistribution, but any model-as-a-service business above $20M in annual revenue must sign a separate agreement with Moonshot, and products above 100M monthly active users or $20M in monthly revenue must display the model name prominently.

## The open tier's constraint moved from weights to racks

**What happened.** Moonshot's Hugging Face repository went public at about 07:30 PT. The checkpoint is the post-trained K3.1 Pro, not an adapter or a partial release: 2.8T total parameters, 104B activated, 93 layers, a 1M-token context and text-plus-image input. The weight index reports 1.56 TB of tensor data across 96 shards. The license is a custom Kimi K3.1-Pro License — free to use, copy, modify and distribute, with a separate-agreement trigger for model-as-a-service providers above $20M in trailing-12-month revenue and an attribution trigger above 100M MAU or $20M monthly revenue. The API rate card still reads $2/$10 per million tokens, with cache reads at $0.20.

**Why it matters.** For an operator, the artifact changes the buy decision, not the benchmark. The API remains the cheap way to use K3.1 Pro; self-hosting a 2.8T model means a serving cluster sized for 1.56 TB of weights, a capex and ops commitment most teams cannot make for a single model. The license splits the market: internal use and end-user products are unencumbered, but the model-as-a-service layer above $20M in revenue is where Moonshot wants a contract. That makes the open tier's next bottleneck serving capacity, not weight availability — and the next tell is not another launch post, but whether inference providers list K3.1 Pro at K3-like prices and whether the first independent evals reproduce the 55.

_Source: [huggingface.co](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) · [kimi.ai](https://www.kimi.ai/blog/kimi-k3-1-pro) · [artificialanalysis.ai](https://artificialanalysis.ai/models/kimi-k3-1-pro)_
