---
title: "The cheapest Gemini 4 outscores its own frontier"
date: 2026-11-12 10:30:00 -0800
excerpt: "Google launched Gemini 4 Hydrogen today at $1.50/$7.50 per million tokens — a 1M-context agentic workhorse that Google says scores 51 on the Artificial Analysis Intelligence Index, one point above Gemini 4 Argon's 50."
categories: [commentary]
draft: false
---

Google launched Gemini 4 Hydrogen this morning: a 1M-token-context model priced at $1.50 per million input tokens and $7.50 per million output, flat across the entire window, in the slot where Gemini 3.8 Flash used to sit. It is available today across AI Studio, the Gemini API, Gemini for business, the Gemini app, Google Search and Google Antigravity. Google says Hydrogen scores 51 on the Artificial Analysis Intelligence Index at its default high thinking level — one point above Gemini 4 Argon's 50 — and 54 at its xhigh setting, while often finishing tasks faster than models in its class. Max output is 65K tokens by default, or up to 1M with long decode, across four thinking levels: low, medium, high and xhigh.

## The mid-tier became the default

**What happened.** Hydrogen lands in the "everyday help" slot of the Gemini app's model picker, with Google claiming it finishes tasks 2.5 times faster at the high default than 3.8 Flash and more than triples the Terminal-Bench 4.1 score (57% vs. 18.2%). In Antigravity, a new Orchestrator switches between Carbon and Hydrogen inside a session; Google reports near-Carbon task success on Terminal-Bench 4.0 while consuming 24% less quota and finishing 19% faster. The model card and API docs are live; the model code is `gemini-4-hydrogen`.

**Why it matters.** For an operator, the cost decision is now a routing decision. The agentic workhorse — the model that writes code, runs tests and verifies changes — is priced below the frontier and, on Google's reported index, scores above it. That makes Carbon and Argon the specialist SKUs for long-horizon reasoning, and Hydrogen the default for the loop. The frontier premium is now buying the tail of the workload, not the average. The number to watch is not Google's 51; it is the first independent Terminal-Bench 4.1 and AA reproduction, because Carbon's scheduled December 1 step-up to $4/$20 makes the default-to-frontier gap 2.7x on both input and output — a hard price to defend for anything but the hardest tasks.

_Source: [blog.google](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/) · [9to5google.com](https://9to5google.com/2026/11/12/gemini-4-hydrogen-launch/) · [ai.google.dev](https://ai.google.dev/gemini-api/docs/models/gemini-4-hydrogen)_
