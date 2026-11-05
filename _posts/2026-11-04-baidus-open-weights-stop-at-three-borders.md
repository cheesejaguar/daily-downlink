---
title: "Baidu's open weights stop at three borders"
date: 2026-11-04 23:30:00 -0800
excerpt: "Baidu published ERNIE 5.5 Flash Base — a 280B-parameter base checkpoint, 14B active per token, 128 shards, ungated on Hugging Face — under a license that excludes the EU, UK and South Korea and requires written authorization above $50M in related revenue."
categories: [commentary]
draft: false
---

Baidu announced ERNIE 5.5 Flash Base tonight and published the weights ungated on Hugging Face: a 280B-parameter sparse mixture-of-experts with 14B active per token, pre-trained from scratch on 33.5T tokens at a 128K training context, and fine-tunable out to a 1M-token context. The checkpoint ships in FP8 and BF16 across 128 safetensors shards. This is the base model — the end of pre-training, before any mid- or post-training — and Baidu says the instruction-tuned ERNIE 5.5 Flash will follow. Baidu's own evaluation puts it ahead of DeepSeek-V4-Flash-Base, Hy3-preview-Base and MiMo-V2.5-Base on a unified pipeline; no independent benchmark has reproduced that yet.

## The license is the product decision

**What happened.** The custom ERNIE 5.5 Flash Base Model License v1.0 grants use, modification, continued training and redistribution only within a Territory that excludes the European Union, the United Kingdom and South Korea. Commercial use is free up to $50M in annual revenue related to products using the model, with a one-time notice and a "Powered by ERNIE" attribution; above $50M it requires Baidu's separate written authorization, with fees set by separate agreement.

**Why it matters.** For an operator, the download is not the decision — the license is. A 280B base checkpoint is a fine-tuning project, not a chat product: you pay the post-training bill and the serving bill for 288GB of FP8 weights, with 14B active per token keeping the per-token compute manageable. In the EU, UK or South Korea the license grants you nothing, so the "open" release is closed in three of the markets most likely to fine-tune it. The $50M line turns open weights into a procurement threshold — below it you file a notice, above it you negotiate. The territorial carve-out is the tell: the open-weight layer is being priced by jurisdiction, not just parameter count, and the first question for any "open" release is now which markets the license actually covers.

_Source: [ernie.baidu.com](https://ernie.baidu.com/release/ernie-5-5-flash-base/) · [huggingface.co](https://huggingface.co/baidu/ERNIE-5.5-Flash-Base) · [leiphone.com](https://www.leiphone.com/category/industrynews/XOv7MDFAP99kUMEW.html)_
