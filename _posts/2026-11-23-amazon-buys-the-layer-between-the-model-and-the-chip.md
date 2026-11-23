---
title: "Amazon buys the layer between the model and the chip"
date: 2026-11-23 08:20:00 -0800
excerpt: "Amazon signed an agreement to buy Decart's Optimization Stack and its founding team — about $7.5 billion per Bloomberg — turning cross-chip optimization software into a sales argument for Trainium."
categories: [commentary]
draft: false
---

Amazon said today it has signed an agreement to buy the proprietary technology behind Decart's Optimization Stack — the software layer that sits between a model and an accelerator and decides how efficiently the two work together — and to bring Decart's three co-founders and their researchers and engineers into the company. Amazon did not disclose a price; Bloomberg reports about $7.5 billion, against the $4 billion valuation of Decart's May round. Globes reports the deal is being made through Annapurna Labs, Amazon's chip arm, and it still needs regulatory clearance. What Amazon is buying is not another model. It is the layer that makes its own silicon usable.

## The portability was the product

**What happened.** Decart's Optimization Stack sits between the model and the chip, adjusting how operations are compiled and executed rather than replacing the infrastructure underneath; Decart says it supports Nvidia GPUs, Google TPUs and AWS Trainium. The two companies have worked together since 2025, and Annapurna Labs has cited Decart's Lucy2 model exceeding 80% Model FLOPS Utilization on Trainium3. Decart raised $300 million at about a $4 billion valuation in May, with Nvidia participating, and has raised more than $450 million in total. Calcalist reports the consideration is cash and stock paid in installments, with the founders committed for five years.

**Why it matters.** Cross-chip portability was the product: the same stack could tune a workload for whatever accelerator a customer already owned, which is what made it useful to operators who did not want to be tied to one vendor. Inside Amazon's chip arm, that portability becomes a way to demonstrate Trainium's cost per token against Nvidia at the moment inference cost is the binding constraint. The tell after closing is whether DOS keeps supporting Nvidia and TPUs at parity, or becomes Trainium-first. The first is a cost lever for customers; the second is lock-in with better benchmarks.

_Source: [aboutamazon.com](https://www.aboutamazon.com/news/company-news/amazon-decart-ai-optimization) · [bloomberg.com](https://www.bloomberg.com/news/articles/2026-11-23/amazon-is-said-to-pay-7-5-billion-for-ai-startup-decart-s-tech)_
