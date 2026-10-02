---
title: "The 64GB DGX Spark costs more than the 128GB one did"
date: 2026-10-02 08:05:00 -0700
excerpt: "Nvidia's new 64GB DGX Spark lists at $4,999 on October 23 — above where the 128GB system launched, because DRAM, not silicon, is setting the local-AI price."
categories: [commentary]
draft: false
---

DRAM has done what GPU yields never managed: it inverted the price ladder of
the personal-AI tier. Nvidia this morning introduced a 64GB version of the DGX
Spark — half the memory of the original GB10 box — starting at $4,999 from
Acer, ASUS, Dell, Gigabyte, HP and MSI on October 23. The 128GB system launched
at $3,999 and had its MSRP raised to $4,699 in February. The new "budget" SKU
undercuts nothing: less memory now lists for more than the full-fat machine
ever did.

## DRAM reset the floor under local inference

**What happened.** Nvidia's blog runs the 64GB config today, dated October 2:
same GB10 Grace Blackwell Superchip, DGX OS and full NVIDIA AI software stack
as the 128GB model, up to 100-billion-parameter models on device, from $4,999
starting Friday October 23 from Acer, ASUS, Dell, Gigabyte, HP and MSI. Every
unit keeps the built-in ConnectX-7 NIC; two can pool to 128GB via the new Sync
Cluster Assistant, and Nvidia's Qwen 3.8 27B test shows 1.7x throughput over a
single unit. Street pricing on what 128GB inventory remains is running
$7,000–$9,000, well past even the raised Founders MSRP.

**Why it matters.** This is the price ladder collapsing under memory supply,
not a product refresh. Half the RAM, yet the SKU lists $300 above today's
128GB Founders MSRP ($4,699) and $1,000 above the $3,999 launch price — the
cheaper local box now costs more than the flagship did. For an operator the
"thin local tier" assumption is gone: buying less memory barely bends the
bill, so the rational move is one box clustered against a second rather than
sizing up, and anything that won't fit 100B resident leans back to the cloud.
Local AI is not getting cheaper; its cost floor just moved up on DRAM's
account.

_Source: [blogs.nvidia.com](https://blogs.nvidia.com/blog/local-ai-dgx-spark-64gb-sync)_

## What I'm watching

Watch whether the 64GB SKU holds at $4,999 through October 23 or drifts up
between announcement and availability the way the rest of the line just did —
memory quotes, not Nvidia, have been writing these price tags for two
quarters. And Sync Cluster Assistant is the quieter tell: Nvidia is selling
the cluster as the upgrade path instead of more RAM, which is how a hardware
vendor signals it can't source the LPDDR5X either.
