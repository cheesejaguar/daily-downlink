---
title: "Nvidia agreed to buy Hugging Face for $12.93 billion — the open layer's landlord is no longer neutral"
date: 2026-09-03 16:15:00 -0700
excerpt: "Nvidia confirmed it agreed to acquire Hugging Face for $12,930,300,000 — the hub where 3 million open models live now sits on the silicon vendor's balance sheet, with Huang promising neutrality that is now a promise rather than a structure."
categories: [commentary]
draft: false
---

The open layer just lost its neutral landlord, and this time it is confirmed, not reported. On Thursday Nvidia said it agreed to acquire Hugging Face for $12,930,300,000, with CEO Jensen Huang announcing the deal in a blog post that pledged the platform "will remain an open platform for the entire AI ecosystem" with "NVIDIA compute will not be required to build on or deploy through Hugging Face." That resolves the [August 26 scorecard](https://blog.aaronx.co/2026/08/26/nvidia-reportedly-takes-hugging-face-the-open-hub-gets-a-captable/), which stayed at *reported-not-agreed* through last week: the arc closed on the column's own terms, at a slightly higher number and with both parties on the record. The single-vendor coupling this column flagged four weeks ago moves from the model layer to the distribution layer.

## The registry and the silicon just landed on one balance sheet

**What happened.** Nvidia confirmed it agreed to buy Hugging Face for $12,930,300,000 — its second-largest acquisition ever, behind only the roughly $20 billion Groq asset purchase last December and ahead of Mellanox (~$7 billion, 2019). Hugging Face hosts 3 million models, 500,000 datasets and a million applications used by more than 18 million developers; the company last raised in 2023 at a $4.5 billion valuation, reportedly turned down Nvidia's own $500 million investment offer at $7 billion last year over dominant-investor concerns, and was running roughly $150 million annualized revenue as of late August. Huang's post leaned on the cover story from the start — Nvidia is already the platform's largest open-model contributor with more than 500 released models and 250+ datasets, and Hugging Face CEO Clément Delangue's side framed the deal as needing "more compute, more support, more collaboration."

**Why it matters.** The mechanism this column guessed at on [August 26](https://blog.aaronx.co/2026/08/26/nvidia-reportedly-takes-hugging-face-the-open-hub-gets-a-captable/) and again in the [landlord-lease thread](https://blog.aaronx.co/2026/09/01/nvidia-holds-the-lease-behind-anthropics-35b-lambda-deal/) is now structural: the company that rents the silicon also owns the registry where open weights are listed, evaluated and deployed. The weights survive in git history and mirrors — that was never the risk — but neutrality is. Huang's "Nvidia compute will not be required" is a corporate commitment, not an architecture; the first signals to watch are whether Hub inference gets subsidized toward CUDA, how Spaces governance and routing are set, and whether the most-visited model hub starts surfacing one stack's preferred artifacts. For an operator the advice from four weeks ago is now mandatory, not defensive: mirror weights off-platform, pin provenance, and treat Hugging Face as a distribution convenience rather than the dependency your supply chain keys on.

_Source: [blogs.nvidia.com](https://blogs.nvidia.com/blog/nvidia-to-acquire-hugging-face/), [cnbc.com](https://www.cnbc.com/2026/09/03/nvidia-agrees-to-buy-hugging-face-for-almost-13-billion-ai-expansion.html), [techcrunch.com](https://techcrunch.com/2026/09/03/nvidia-confirms-it-will-buy-hugging-face-for-12-9-billion)_

## What I'm watching

Whether the promise outlives the incentive. Nvidia's open-model posture has been consistent and funded; the question was never sincerity but the structure that neutrality required, and that structure is gone. Delangue flagged the real intent in his own words — the community "needed more compute" — which is the same sentence every SaaS consolidation uses to explain itself on the way to a walled garden. Watch the first Spaces or routing decision that makes an open-weights workflow cheaper on Nvidia.
