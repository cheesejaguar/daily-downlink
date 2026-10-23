---
title: "Kimi K3.1 Pro is fourth on the board, and the open weights are still a promise"
date: 2026-10-23 12:18:00 -0700
excerpt: "Moonshot's K3.1 Pro scores 55 on the Artificial Analysis Intelligence Index — fourth of 215, three points behind Claude Opus 5.5 — at $2/$10 per million tokens, a third below K3, with the weights promised by November 4."
categories: [commentary]
draft: false
---

Moonshot AI shipped Kimi K3.1 Pro today: the first model in its K3.1 series, a post-train of Kimi K3 with substantially larger reinforcement-learning compute, a 1,048,576-token context, and a score of 55 on the Artificial Analysis Intelligence Index — fourth of 215 models, three points behind Claude Opus 5.5. Moonshot reports 65.7% on Terminal-Bench 4.0, ahead of GPT-6 Astra's 58.2% and just behind Opus 5.5's 66.4%. The API price is $2/$10 per million tokens, a third below the $3/$15 list price Artificial Analysis records for K3. The weights are not out: Moonshot calls K3.1 Pro its most capable 3T-class open-weight model and says the full weights will be released by November 4.

## A price cut today, an open-weights date in twelve days

**What happened.** K3.1 Pro and a faster K3.1 Pro Highspeed variant ($4/$20, two to three times the speed with identical capabilities) are live today on Kimi.com, Kimi Work, Kimi Code and the Kimi API, under model IDs `kimi-k3.1-pro` and `kimi-k3.1-pro-highspeed`. Artificial Analysis ranks K3.1 Pro fourth of 215 on its Intelligence Index at 55, behind Claude Opus 5.5 (58), Claude Sonnet 5.5 (56) and Muse Wonder Full (56); its board still classes the model as proprietary, because the weights are not on Hugging Face. K3 scores 44 on the same index, so K3.1 Pro is 11 points higher and, at $2/$10, a third cheaper than K3's $3/$15 list. Moonshot says the full weights will be released by Nov 4.

**Why it matters.** The launch is a price cut first and an open-weights event second. For an operator, a 3T-class model with a 1M-token window and near-Opus coding scores at $2/$10 changes the unit economics of long-horizon agent work today; but at 73.5 output tokens per second it is slower than the board's 81-token median, and Artificial Analysis calls it very verbose, so the rate card is not the bill — cost per task is. What it does not change yet is the open-weights race: until the artifact lands, this is an API-only model with an open-weights promise, the same structure as Mistral's Large 4 preview. If the weights land by Nov 4 at the score Moonshot claims, the open frontier moves within three points of the top closed model in one step. If they slip, today's launch was a rate card with an open-source footnote.

_Source: [kimi.com](https://www.kimi.com/en/blog/kimi-k3-1-pro) · [artificialanalysis.ai](https://artificialanalysis.ai/models/kimi-k3-1-pro)_
