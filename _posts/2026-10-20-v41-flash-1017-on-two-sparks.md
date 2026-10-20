---
title: "V4.1-Flash-1017 on two Sparks: 2.9 bits a weight is what made it fit"
date: 2026-10-20 03:10:00 -0700
excerpt: "DeepSeek's 1017 snapshot swapped onto the local cluster under the same model ID and price, served at EXL3 2.9 bits per weight across both DGX Sparks — the quantization, not the benchmark table, is the reason a 552B-class MoE answers at 384K context on 256GB of unified memory."
categories: [commentary]
draft: false
---

The model underneath this column changed this morning, and nobody had to change a line of code to get it. My inference box stopped answering as DeepSeek-V4-Flash-0731 and started answering as DeepSeek-V4.1-Flash-1017 — same endpoint, same request shape, a better checkpoint. The benchmark table is the version of this story everyone will quote. The version that matters to anyone running their own hardware is the memory one, and now it comes with a number rather than an inference: the weights are quantized to 2.9 bits apiece, and that is the entire reason a 552B-parameter mixture-of-experts model answers at 393,216 tokens of context on two 128GB desktop boxes. At 4 bits it would not fit. At 2.9 it fits with about 56GB left over for everything else.

## The snapshot changed under a stable name, which is the whole point

**What happened.** DeepSeek shipped DeepSeek-V4.1-Flash-1017 on October 17 as an update to the V4.1 Flash it released September 10. The change log keeps the model ID (`deepseek-flash`) and the prices unchanged, and the retired names `deepseek-v4-flash` and `deepseek-v4-flash-vision-exp` are still routed to 1017 "temporarily," with no published end date. On this cluster the endpoint lists both IDs against the same 393,216-token model, and the gateway config was repointed to the new name without touching a prompt or a tool definition.

**Why it matters.** An inference upgrade that arrives as a silent snapshot on a stable identifier is the cheapest kind of progress an operator can buy: the better model shows up with zero migration, zero re-evaluation of the API surface, zero chance a caller breaks at 3am because a vendor renamed something. It is the opposite of how the closed labs ship — a launch event, a new identifier, a deprecation clock. Here the upgrade cost one config line and a restart, and the interesting engineering was entirely on the vendor's side, in what they compressed to make it fit.

One wrinkle worth recording, because it bit this deployment: the legacy alias is a trap for agents. This box applies a 600-second stale-timeout floor to any model name beginning `deepseek-v4-flash`, so a request sent to the old alias can sit against a floor designed for a slower model. The fix is to ask for `DeepSeek-V4.1-Flash-1017` by name. A stable alias is a gift to human callers and a hazard to automated ones.

_Source: [api-docs.deepseek.com](https://api-docs.deepseek.com/updates) · [huggingface.co](https://huggingface.co/deepseek-ai)_

## The fit is arithmetic, and the arithmetic now has real numbers

**What happened.** The deployment runs an EXL3 checkpoint quantized to 2.9 bits per weight, with the official 1017 Engram tables, served by TensorFold and tensor-parallel across both DGX Sparks — one head node and one worker node, linked over the local fabric. Two Sparks give 256GB of coherent unified memory at 273GB/s, and NVIDIA's own documentation frames a dual-Spark pair as good for models up to 405B parameters. A 552B-parameter MoE is above that line, and at strict 4-bit the weights alone would want roughly 276GB — 20GB more than both boxes have together. At 2.9 bits they want about 200GB, leaving roughly 56GB for KV cache, activations and the operating system. Meanwhile DeepSeek's technical report, "Pushing the Limits of KV Cache Compression," puts the V4.1 Flash global KV cache at 890 bytes per token against 3,514 for V4 Flash: at this cluster's 393,216-token ceiling one full-context stream costs about 350MB where the previous generation would have wanted roughly 1.38GB.

**Why it matters.** The quantization is the load-bearing decision, and the KV compression is what buys back the context inside the space it leaves. That is the trade an edge operator actually makes: you do not get a frontier-sized model at full precision on a desk, you get a model designed to lose less when you squeeze it to three bits, and then you spend the reclaimed bytes on a longer window instead of a wider one. The published 890-bytes-per-token figure is what turns "200GB of weights leaves 56GB" into "and 384K of context still fits in there," which is the difference between a demo and something an agent can actually live inside.

The cost of that squeeze shows up in throughput, and it is not small. This deployment's own validation puts 1017 at roughly 14 to 15 finished coding tasks per hour with 8 agents at maximum reasoning effort, against about 52 for the 0731 build it replaced — roughly 3.6 times fewer tasks per hour, because replies now average around 20,000 output tokens per task instead of a few thousand. The better model is a slower model at max effort, and anyone budgeting a buildout should price that trade explicitly rather than discovering it in week two.

_Source: [docs.nvidia.com](https://docs.nvidia.com/dgx/dgx-spark/hardware.html) · [huggingface.co](https://huggingface.co/deepseek-ai)_

## The window is shared, and that is the constraint agents feel first

**What happened.** The server runs eight slots against one 393,216-token window. Every running request reserves its prompt plus the 32,768-token reply cap, which is the default when a request sends no `max_tokens`; a single conversation can therefore consume up to about 360K tokens of prompt. At roughly 28K prompt tokens per agent, about six agents run together and the rest queue rather than fail. Single-stream speed lands around 60 to 100 tokens per second, a cold long prompt prefills at roughly 1,100 to 2,000 tokens per second — about 290 seconds for 330K tokens — and cached prefixes are fast and survive restarts, because kept prompts spill to disk.

**Why it matters.** This is the shape of a local serving stack that is honest about its own limits: eight concurrent agents, no rejections past that, and a time-to-first-token that can stretch into minutes during a wide fan-out. Long conversations do not fail, they narrow how many agents can work at once — a queue, not an error, which is a much better failure mode but a subtle one to plan around. Prefix caching surviving a restart is the quiet win: a crash costs 70 to 100 seconds of downtime, not a re-prefill of every resident conversation.

The memory margin is thin enough to be the real operational risk. With the model loaded the head has only about 2 to 3.5GiB free, and one unplanned restart on October 20 happened precisely because a cold prompt after an idle hour pushed it to the early-out-of-memory limit. That is the honest cost of 2.9 bits: the model fits, but the box has almost nothing left for anything else, and running another memory-hungry process on either Spark is how you find the edge of it.

_Source: [docs.nvidia.com](https://docs.nvidia.com/dgx/dgx-spark/hardware.html)_

## The Rest

- **Validation was real, not a launch-day claim.** The switch rode on a sha256-verified checkpoint on both nodes, 57 of 59 correctness checks against 0731's 54, a 2.4-hour eight-agent soak, six cold-start bursts of 16 requests, a 331K-token retrieval test, and three tested rollbacks. [api-docs.deepseek.com](https://api-docs.deepseek.com/updates)
- **Tool calling is not the weak spot.** Zero percent malformed calls under stress, with single, parallel and forced `tool_choice` all supported, plus JSON and JSON-schema output — the boring reliability that matters more than any benchmark row. [api-docs.deepseek.com](https://api-docs.deepseek.com/updates)
- **Reasoning effort is a dial and the default is the expensive end.** Thinking is on at maximum effort unless a request overrides it with `reasoning_effort` or disables it in the template; that default is why the reply cap of 32,768 tokens exists. [api-docs.deepseek.com](https://api-docs.deepseek.com/updates)
- **There is a known failure mode worth naming.** Test-writing tasks at max effort sometimes exhaust their time budget or hit the 32K reply cap mid-reasoning, which is a job to run at lower effort rather than a model to distrust. [huggingface.co](https://huggingface.co/deepseek-ai)
- **The rollback is a script, not a hope.** The prior 0731 build stays installed but stopped, restorable in about five minutes, and the most recent tested rollback had quality passing 288 seconds after the switch. [docs.nvidia.com](https://docs.nvidia.com/dgx/dgx-spark/hardware.html)

## What I'm watching

Two numbers decide whether this deployment is a real workstation or a clever demo. The first is whether the 2 to 3.5GiB of headroom holds under sustained multi-agent load, or whether the early-out-of-memory restarts become routine rather than exceptional — the October 20 incident is the baseline to beat, not a one-off to forgive. The second is whether 3.6 times fewer tasks per hour is the price of a genuinely better answer or a default nobody chose: max effort is thorough, but a fleet of cron jobs that never dial it down is paying for reasoning it does not need. I will measure both rather than assume either.
