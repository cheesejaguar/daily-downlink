---
title: "vLLM's Rubin inference preview claims the NVL72 stacks up 3.2x in profit per gigawatt"
date: 2026-10-09 16:05:00 -0700
excerpt: "The vLLM team and NVIDIA posted an InferenceX Preview benchmark claiming Vera Rubin NVL72 runs 3.2x more profit per gigawatt and up to 10x more performance per dollar than GB300 NVL72 on the widely-deployed vLLM engine — a self-submitted preview, not yet independently verified, but the first concrete numbers for what Rubin does to inference economics at the system level."
categories: [commentary]
draft: false
---

The vLLM team and NVIDIA posted the first concrete inference numbers for Rubin
this morning, and they are attention-grabbing on geometry alone: Vera Rubin
NVL72 claims **3.2x more profit per gigawatt** and **up to 10x better
performance per dollar** than GB300 NVL72, both running on vLLM, the production
engine most of the industry already serves on. SemiAnalysis' Agentic Inference
Profit Calculator puts the same machine at roughly **$39 billion in annual
profit** even on a slightly-below-frontier open model like MiniMax's M3 428B.
The caveat in the same breath: this is an **InferenceX Preview submission** —
the benchmarks are the vendor's own submission, not an independent, run-to-run
audited number, and the full public submission is still coming. Treat the
absolute figures as the team's claim, and the direction as the news.

## Inference economics just got a Rubin number, and it is a claim worth a discount

**What happened.** The announcement, posted under the vLLM project and
SemiAnalysis' calculator model, is an InferenceX Preview: Rubin NVL72 delivering
3.2x the profit per gigawatt and up to 10x the performance per dollar of GB300
NVL72 on vLLM, with credit across NVIDIA, vLLM, Inferact, the ex-CentML team now
at NVIDIA, and named individuals. A dashboard link accompanies it. Per the
SemiAnalysis calculator, a Vera Rubin NVL72 running a slightly-less-than-frontier
open model (MiniMax M3 428B) is projected at ~$39B in annual profit. Both a
vLLM public Rubin NVL72 InferenceX submission and an SGLang Rubin NVL72
submission are described as coming soon.

**Why it matters.** The posted numbers are a preview submission, so read them as
the vendor's own upper-bound self-report — but the *direction* is the signal.
Profit per gigawatt is the metric that makes a datacenter wallet open or close:
if Rubin holds even a fraction of a 3.2x margin advantage at the system level,
the economics of inference flip toward whoever can power it, and GB300 fleets —
which are only just reaching the field — start their depreciation clock looking
older than planned. That two independent serving teams are tearing down the same
rack to claim the headline also tells you the performance race has moved from
the chip to the whole system: model, engine, and power envelope priced as one
line. The discount to apply is honesty about the source, not dismissal of the
result.

_Source: [x.com](https://x.com/SemiAnalysis_/status/2108604229988319724)_

## The Rest

- **The metric mix matters more than the headline** — "profit per gigawatt" and
  "perf per dollar" are margin levers, not FLOPS; that framing is the tell that
  Rubin is being pitched to the datacenter P&L, not the kernel benchmark sheet.
- **A preview is not a regression** — until the full public vLLM InferenceX
  submission lands and is reproduced independently, the 10x / 3.2x figures are
  the vendor's claim with chips in the table, not an audited run-to-run result.
- **Two engines, same claim** — vLLM and SGLang both shipping Rubin NVL72
  submissions reinforces that the advantage is in the platform, not any single
  software stack.

## What I'm watching

Watch for the full public vLLM Rubin NVL72 InferenceX submission and an
independent third-party reproduction — that, not the preview headline, is the
number that earns a fleet decision. And keep an eye on what GB300 purchasers do
when the wafer arrives with a younger sibling claiming 10x: the smart ones price
depreciation on the rumor, not the retraction.
