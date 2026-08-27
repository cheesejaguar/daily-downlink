---
title: "Nvidia reportedly takes Hugging Face, and the open layer loses its neutral landlord"
date: 2026-08-26 20:30:00 -0700
excerpt: "Hours after its record earnings, Nvidia is reported to be buying Hugging Face for roughly $13 billion — The Information says a deal is agreed at $12.9 billion, Business Insider and Bloomberg describe serious talks above $13 billion that could still fall apart — putting the neutral hub of the open-weights ecosystem on a closed-vendor cap table, unconfirmed by either party."
categories: [commentary]
draft: false
---

Hours after NVIDIA printed its record quarter, the open layer absorbed a cap-table shock. The Information reports the chipmaker has agreed to buy Hugging Face for $12.9 billion; Bloomberg and Business Insider report serious talks in recent weeks over a deal valuing the platform at more than $13 billion, with no agreement reached. Neither NVIDIA nor Hugging Face has confirmed. If the number survives even as a negotiation, it is the largest consolidation of the open-weights ecosystem's infrastructure into the hands of the company whose revenue runs on renting the silicon those weights execute against — and it lands the same evening today's earnings re-answered the [custom-silicon fight](https://blog.aaronx.co/2026/08/26/nvidia-printed-96b-vera-rubin-in-full-production/).

## The open hub's landlord changes — reported, not confirmed

**What happened.** The Information, citing a person with knowledge of the deal, reports Nvidia has agreed to buy Hugging Face for $12.9 billion. Business Insider, citing a person familiar with the matter, frames the same arc as serious acquisition conversations over a deal valuing the platform "more than $13 billion," adding that the companies have not reached a deal and the talks could still fall apart. It dropped hours after NVIDIA guided Q3 to $108 billion and said it has $18 billion committed to equity investments for the rest of the fiscal year. Context: Hugging Face last raised in 2023 at a $4.5 billion valuation, and reportedly turned down a $500 million NVIDIA investment at a $7 billion valuation last year, citing the risk of a single dominant investor.

**Why it matters.** Hugging Face is where open weights live for most operators — the registry, Spaces, datasets, the model IDs a supply chain already keys on. A closed-vendor owner moves single-vendor coupling from the model layer to the distribution layer: the GPUs and the hub that hosts what runs on them end up on one balance sheet. The weights themselves survive in git history and mirrors, so this is not a hunting license on open models; it is a neutrality problem. Plan for a platform whose routing, Spaces, and export choices are made to optimize one stack, and keep weight provenance and object-storage redundancy independent of the hub no matter which report is right.

## What I'm watching

Whether the deal is real and at which number: The Information says agreed at $12.9 billion; Bloomberg and Business Insider say talks above $13 billion that could still collapse; neither party has commented. If it closes, the first signals are hub neutrality, Spaces governance, and whether NVIDIA subsidizes Hub inference in a way that pulls the open layer's gravity toward CUDA.

_Source: [theinformation.com](https://www.theinformation.com/articles/nvidia-agrees-buy-open-source-model-repository-hugging-face-12-9-billion), [businessinsider.com](https://www.businessinsider.com/nvidia-in-talks-to-buy-hugging-face-13-billion-dollars-2026-8), [bloomberg.com](https://www.bloomberg.com/news/articles/2026-08-27/nvidia-discussed-buying-ai-startup-hugging-face-insider-says), [techcrunch.com](https://techcrunch.com/2026/08/24/hugging-face-reportedly-in-talks-to-be-acquired-for-13b)_
