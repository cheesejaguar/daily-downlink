---
title: "Qwen4-Max ships closed, and the price floor moves again"
date: 2026-11-15 20:10:00 -0800
excerpt: "Alibaba launched Qwen4-Max tonight at $1.50/$4.50 per million tokens — 25% below Qwen3.8-Max — a closed-weight flagship that claims coding wins over Claude Fable 5.1 and Kimi K3.1 Pro."
categories: [commentary]
draft: false
---

Alibaba launched Qwen4-Max this evening: the general-availability flagship of its Qwen4 family, and the first Qwen4 model you can call on a metered API. It is closed-weight, priced at $1.50 per million input tokens and $4.50 per million output — 25% below what Qwen3.8-Max charged on both legs, with implicit cache reads at $0.075. Bloomberg reports Alibaba claims the model scores near the top of coding benchmarks, ahead of Anthropic's Claude Fable 5.1 and Moonshot's Kimi K3.1 Pro. The Token Plan preview that was due to retire on November 25 was a demand probe; this is the rate card. The most-downloaded open-weight model family in the world has now put its frontier behind an API.

## The flagship is the closed tier now

**What happened.** Qwen4-Max is callable through Alibaba Cloud International with a 1M-token context, text, image and video input, reasoning on by default, and up to 393,216 output tokens. Alibaba did not release weights; it says smaller versions of the series will follow soon, and the September Apsara roadmap named an open-weight 27B tier. The release also adds stronger security measures, following the open-weight cyber-risk incidents that include the Qwen3.8-Flash-Next sandbox failure [covered in today's column](https://blog.aaronx.co/2026/11/15/the-account-is-not-the-control/).

**Why it matters.** Qwen3.8-Max was $2/$6; Qwen4-Max is $1.50/$4.50 — a fifth of Claude Fable 5.2's input rate and a ninth of its output. That is the new price anchor for frontier-class work, and the model setting it is one you cannot download. For an operator the routing table is now the deliverable: Qwen4-Max is a credible default for coding and agent loops on price, but it is a single-provider SKU on Alibaba Cloud International, so the cheap row is also a concentration risk. Watch the 27B. If it ships open under the same family, the closed flagship is a rental; if it does not, Qwen's open-weights reputation stops one tier below its own frontier.

_Source: [bloomberg.com](https://www.bloomberg.com/news/articles/2026-11-16/alibaba-unveils-new-flagship-ai-model-in-riposte-to-us-rivals) · [thedefiant.io](https://thedefiant.io/frontier/ai/alibaba-launches-qwen4-max-with-lower-api-prices) · [openrouter.ai](https://openrouter.ai/qwen/qwen4-max)_
