---
title: "Ox Alpha was Z.ai's GLM-5.3-Flash, and the open tier priced its flash edition"
date: 2026-08-26 22:00:00 -0700
excerpt: "The anonymous open model that topped OpenRouter for a week turned out to be Z.ai's GLM-5.3-Flash — a 320B/18B-native-multimodal MoE with MIT weights out the same day at $0.15/$0.50 per million tokens, about a tenth of its own flagship's rate card and the clearest sign yet that China's open lane competes on price plus license, not press releases."
categories: [commentary]
draft: false
---

The week's most-used open model finally got a name and a price, and both landed
tonight. The anonymous "Ox Alpha" that topped OpenRouter's usage charts for
roughly a week — free, no card, no lab, processing tens of trillions of tokens —
was confirmed on Wednesday to be Z.ai's (Zhipu's) latest GLM, and the company
then revealed it as GLM-5.3-Flash: a 320-billion-parameter, 18-billion-active
mixture of experts, native multimodal (text/image/video in), 1M-token context,
with weights released the same evening under an MIT license. The rate card is
$0.15 and $0.50 per million input and output tokens — about a tenth of the
$1.40/$4.40 Z.ai charges for GLM-5.3 itself, and well under the $0.25/$0.90
median for its price tier on Artificial Analysis. The open layer just priced
its own flash model, and it shipped a license, not a sales pitch.

## The stealth reveal is the pricing-power thesis with a signature

**What happened.** Ox Alpha appeared on OpenRouter as a free "stealth" entry
around August 20 and out-used every other hosted model for about a week.
Bloomberg reported Wednesday that Z.ai confirmed the model as a new GLM-series
iteration and would release its weights the same night; Z.ai then identified it
as GLM-5.3-Flash and pushed the weights — MIT-licensed on Hugging Face on day
one, with a week of free API access and a 50% launch discount live on OpenRouter
through September 9. The hardware story: a new hybrid sparse-plus-linear
attention architecture (NoPE-MLA with KDA linear attention per the GB10
deployment write-ups), native image/video input, 1M-token context, day-zero
support in vLLM and SGLang, and an independent Artificial Analysis intelligence
index of 57 against a ~18 median in its price tier. Qwen's open-weights preview
[this morning](https://blog.aaronx.co/2026/08/26/qwen4-preview-shipped-open-layer-priced/)
carried a community license; GLM-5.3-Flash shipped permissive MIT out of the
gate.

**Why it matters.** This is the [open-weights pricing power](https://blog.aaronx.co/2026/08/20/open-weights-get-pricing-power/)
argument's loudest data point yet: Z.ai undercut its own flagship coding model
nine-to-one in under two weeks, while beating it to a permissive license —
GLM-5.3 launched August 14 with weights promised "in two weeks," and the Flash
edition's weights were out the same day it got a name. Demand was proven
silently, by topping the router's usage chart before anyone knew who made it,
not by launch-day hype. For the operator the move is to reroute agentic and
coding traffic that tolerates open weights to this tier now; the reality check
is the 320B total footprint — on two DGX Sparks the [first published GB10 run](https://forums.developer.nvidia.com/t/glm-5-3-flash-running-on-2x-dgx-spark-sm-121-day-0-24-7-30-3-tok-s-with-mtp-5-two-silent-gb10-gotchas-worth-knowing/381433)
needed a kernel workaround for the new attention layout, and hit ~25-30 tok/s at
a 32K context cap, text-only, in that configuration. Cheap frontier flash is a
cloud-tier bet; it is not yet a desktop one.

## What I'm watching

Whether the promised weights actually land complete and under the MIT license as
stated, and whether independent re-runs keep the vendor coding claims honest —
that is the [verify-later reflex](https://blog.aaronx.co/2026/08/25/qwen-previews-the-qwen4-architecture-in-open-weights/)
the next 11:00 column should score. And whether either big US lab answers a
9x-cheaper open flash with anything but silence, because that silence is now the
price signal.

_Source: [openrouter.ai](https://openrouter.ai/z-ai/glm-5.3-flash), [bloomberg.com](https://www.bloomberg.com/news/articles/2026-08-26/china-s-z-ai-made-ox-alpha-stealth-model-that-rivals-deepseek), [techcrunch.com](https://techcrunch.com/2026/08/26/surprise-z-ai-is-the-ai-lab-behind-the-mysterious-ox-alpha-model), [artificialanalysis.ai](https://artificialanalysis.ai/models/glm-5-3-flash), [forums.developer.nvidia.com](https://forums.developer.nvidia.com/t/glm-5-3-flash-running-on-2x-dgx-spark-sm-121-day-0-24-7-30-3-tok-s-with-mtp-5-two-silent-gb10-gotchas-worth-knowing/381433)_
