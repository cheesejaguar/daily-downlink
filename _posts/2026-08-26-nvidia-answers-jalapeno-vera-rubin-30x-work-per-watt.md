---
title: "NVIDIA answers Jalapeño: Vera Rubin posts 30x more work per watt on agentic loads"
date: 2026-08-26 11:15:00 -0700
excerpt: "A day after OpenAI's chip benchmark, NVIDIA measured Vera Rubin at up to 30x GB300's throughput per megawatt on agentic workloads — a reminder that everyone in this fight reports their own numbers, and the real contest is who ships at scale first."
categories: [commentary]
draft: false
---

Follow-up to yesterday's pass on [OpenAI's Jalapeño](https://blog.aaronx.co/2026/08/25/openai-jalapeno-beats-blackwell-on-tokens-per-watt/). Where that post said the frontier's custom-chip lane had posted its first credible measured win against the incumbent on the axis the whole buildout is stuck on, NVIDIA answered the next day with on-silicon numbers of its own — and together the two announcements are a masterclass in why you should read the units before you read the headline.

## Vera Rubin: up to 30x more work per megawatt than GB300 — NVIDIA-measured

**What happened.** NVIDIA published data showing Vera Rubin NVL72 systems deliver up to 30x higher throughput per megawatt than GB300 NVL72 on agentic workloads, with token costs up to 35x lower. The measurement used the SemiAnalysis AgentX workload — recorded real-world agentic-coding sessions with context growth, tool calls, and sub-agent spawning preserved — and was run on-silicon by NVIDIA.

**Why it matters.** Two things at once, and they cut opposite ways. First, it is a genuine reset: if a full-stack Vera+LPX system genuinely does 30x the agentic work per energy unit of last year's flagship, then the price floor under inference just moved dramatically — the same "megawatts, not sockets" axis Jalapeño won on, now re-contested by the incumbent. But second, note what this number is: NVIDIA-measured, on NVIDIA's benchmark, announced by NVIDIA one day after a competitor's chip was reported ahead. It is the AI-infrastructure version of both boxers claiming the round. Jalapeño's own numbers came from an in-lab run by SemiAnalysis, to which OpenAI opened its doors — not from an independent neutral lab either. There is not a single independent party in this fight publishing the arbitrated, apples-to-apples number. That is the operator's warning: everyone reports the workload where they look best, and the workload is doing more of the work than the chip is.

_Source: [blogs.nvidia.com](https://blogs.nvidia.com/blog/vera-rubin-nvl72-efficiency-ai-agents)_

## What it does to yesterday's Jalapeño take

**What happened.** Yesterday I wrote that Jalapeño is "ahead on output tokens per MW vs Vera Rubin" and head-to-head on perf-per-dollar before spec-decode. NVIDIA's posted 30x-work-per-MW figure for Vera is not directly comparable — different chip, different system, different era vs the GB300 baseline, different benchmark — but it is a strong disconfirming data point against that secondary claim.

**Why it matters.** This is the part worth keeping, because it's how a decision record is supposed to work. The headline call — Jalapeño beat GB300 on work-per-watt — still stands on the reported numbers; you don't retract a claim because a different party measured a different chip differently. But my secondary assertion that Jalapeño is ahead of Vera Rubin on output-tokens-per-MW was always a small, unverified extrapolation, and the honest amendment is: that comparison is now contested, and contested by a real measurement on the agentic workloads that actually matter for the people running inference at load. I said "treat the Rubin-ships-now-vs-Jalapeño-ramps-2027 gap as the real race." This week's news is exactly that race, and NVIDIA just showed its best foot on it. The take here is unchanged but better-qualified: Jalapeño's win is real against the previous generation; against what is shipping now, the crown is contested week to week, and the only score that settles it is who delivers frontier token economics at production scale first.

_Source: [prior pass](https://blog.aaronx.co/2026/08/25/openai-jalapeno-beats-blackwell-on-tokens-per-watt/)_

## What I'm watching

Richard Ho's Hot Chips talk, for one — his slides may carry the Vera comparison directly rather than only the GB300 one. And the honest thing to track after both announcements: whether anyone runs the two on a shared, neutral agentic benchmark in 2026, because until that exists, "30x" and "beats the flagship" are both vendor-selected slices of a workload, not ground truth. Both ships now; both have a story to tell; the cheapest, most useful number in AI right now is an independent head-to-head on real agent traffic.
