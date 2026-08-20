---
title: "Open weights are getting pricing power"
date: 2026-08-20 11:00:00 -0700
excerpt: "DeepSeek raised API prices more than fourfold and still owns the volume tier, Mojo finally shipped under Apache 2.0, and the sub-second micro-VM is becoming the cheap default for running untrusted agent code."
categories: [commentary]
draft: false
---

The week's news is less about who's smarter than who and more about who's
cheaper and who's safer to depend on. DeepSeek pushed its API prices up by more
than four times on the volume leader, and the case for why the budget tier
survives it has nothing to do with loyalty and everything to do with how far the
tiers are apart. Mojo — the language pitched as "Python, but fast on GPUs" —
finally went Apache-2.0,
which is the difference between a bet on a vendor and a dependency you can build
on. And the most practical agent-safety story of the week is a 50-millisecond
virtual machine that makes hardware isolation the default place to run code you
don't trust. Three stories, one throughline: the soft underbelly of AI is no
longer raw capability but operating economics and the security floor, and both
just got easier to think about properly.

## A fourfold price hike on the volume leader is the first real test of open-weight pricing power

**What happened.** DeepSeek raised its API output pricing effective August 16:
V4 Pro goes from $0.87 to $3.96 per million tokens at peak hours — more than
four times — and V4 Flash from $0.28 to $1.32, with both halving off-peak, in a
new peak/off-peak structure the company says is meant to "allocate resources
more reasonably." Weeks earlier, Vercel's August Production Index (data through
July) showed the same model family owning the budget tier outright: DeepSeek
became the second-largest lab by token volume, running more than twice Google's
share, and its cheapest model, V4 Flash, moved about a fifth of all gateway
tokens — more than any other single model. Open-weight models as a group grew
to 36% of gateway token volume in July while their share of spend, which had
languished under four cents of every dollar, doubled to around nine cents.

**Why it matters.** The interesting number isn't the 4x — it's the distance
between tiers. New DeepSeek ceiling versus what the market charges up-market:
$1.32 for V4 Flash at peak, $15 for Kimi K3 output, $30 for GPT-5.6 Sol. Four
times more expensive is nothing next to an order-of-magnitude gap, so the
budget tier keeps its pricing power — the volume column and the spend column
have decoupled, and repricing one tier doesn't move the other. That matches what
Vercel's routing data showed all along: buyers pick a tier by the task, then the
cheapest model inside that tier. Read naively, "DeepSeek raised prices 4x"
sounds like the cheap era ending; read as an operator, it's a signal to re-run
the model-mix math on the low end, not to abandon it — the same routing decision
I flagged when the 27B tied the flagship [yesterday](https://blog.aaronx.co/2026/08/19/small-weights-lost-keys-and-the-last-clean-text/),
now with a price event attached. One honest caveat: this is gateway telemetry —
a large, real sample of proxied production traffic, but not the whole market,
and DeepSeek's share is still small in absolute compute terms. Under that
caveat, the shape of the split is clear.

_Source: [finance.yahoo.com](https://finance.yahoo.com/technology/ai/articles/deepseeks-ai-models-cost-four-105824671.html) · [vercel.com](https://vercel.com/blog/deepseek-overtakes-google-on-volume-cost-per-token-falls)_

## Releasing the compiler is how a language bet becomes infrastructure you can build on

**What happened.** Modular shipped Mojo 1.0 late last week and, on August 18,
released the Mojo compiler and toolchain under Apache 2.0, following through on
its 2023 open-source promise. Mojo is positioned as making GPU programming "as
painless as possible" with Python-inspired syntax. The quieter change is that
Modular has dropped the original plan to make Mojo a full superset of Python —
as the company put it last year, "Mojo may or may not evolve into a full
superset of Python, and it's okay if it doesn't" — betting instead that
AI-assisted coding tools will smooth the migration.

**Why it matters.** A systems engineer choosing whether to put a new language in
the build path weighs the license as heavily as the syntax. Apache 2.0 means
shipping Mojo in a commercial toolchain costs nothing in legal review and the
compiler can be forked if the vendor's roadmap goes sideways — that converts a
bet on a single company into a dependency the community owns, which is the
precondition for a language aimed at infrastructure to be taken seriously. The
honest part is the superset retreat: Mojo is no longer "Python that's fast," it
is a Python-flavored language you migrate into, and the migration path runs
through coding agents rather than drop-in compatibility. That is a narrower,
more candid pitch — and open sourcing is what makes even the narrow version
worth the risk, because the gaps (debugger maturity, ecosystem breadth,
C-extension interop) become problems you can hire into instead of promises from
a vendor.

_Source: [modular.com](https://www.modular.com/blog/mojo-open-source) · [simonwillison.net](https://simonwillison.net/2026/Aug/18/mojo-is-now-open-source/)_

## The cheap default for running untrusted code is now a 50-millisecond micro-VM

**What happened.** Simon Willison tested smolvm as a sandbox for untrusted Python
and JavaScript: Firecracker-based micro-VMs with offline local images,
no-network execution, CPU and RAM limits, guest-enforced timeouts, storage
quotas, and read-only input mounts. The mechanics worked as specified — cold
starts around 0.6–1.5 seconds, warm runs around 50 ms. There is one environment
gotcha worth repeating: the agent's own container is itself a Firecracker guest
without /dev/kvm, so it could not run a VM inside a VM, and the test battery
fell back to GitHub Actions runners.

**Why it matters.** Whenever an agent executes code it didn't write — model
output, or a user-supplied script for a data transformation — the trust boundary
should be the hypervisor, not a process sandbox or the model's good behavior.
Micro-VMs have always been the right shape for this; what changed is latency and
price, and a warm start measured in milliseconds makes hardware isolation the
default rather than an expensive special case. Plan for the nested-virtualization
gotcha, though: if the container hosting an agent can't reach /dev/kvm, your
sandbox silently can't start inside it. This is the same "control the agent run
layer" thesis that just drew nine figures of venture money (see The Rest) — the
runtime security floor is becoming a funded category, and the cheap version of
it is a sub-second VM.

_Source: [simonwillison.net](https://simonwillison.net/2026/Aug/19/smolmachines-untrusted-sandbox/)_

## The Rest

- **Lattice, an 8 MB static retriever** — one 30K×1024 lookup table with no transformer, trained on ~660M curated pairs, now leads the static-retriever class on decontaminated BEIR while embedding all of English Wikipedia in seven minutes on a laptop. It is the cheapest possible realization of the "fix retrieval, not the parameters" call from [yesterday](https://blog.aaronx.co/2026/08/19/small-weights-lost-keys-and-the-last-clean-text/): the more context you can fetch by lookup, the fewer times the model has to recall from its own weights. [huggingface.co](https://huggingface.co/blog/erikkaum/lattice-blog)
- **Onyx Security raises $113M** — the Israeli startup building technology to govern and control autonomous agents banked nine figures, a direct bet on the agent-runtime security category. The money is flowing to the layer that decides what an agent is allowed to do, not just the models it runs on. [timesofisrael.com](https://www.timesofisrael.com/israeli-cyber-startup-raises-113m-to-secure-and-control-autonomous-ai-agents)
- **San Jose opens its data-center standards process** — the first community listening session this week drew residents pushing for a moratorium against 11 projects working through the pipeline, with final standards due in December. "What it costs to run at load" now includes water, power, and land-use politics in my own backyard. [sanjosespotlight.com](https://sanjosespotlight.com/san-jose-residents-push-for-data-center-moratorium)
- **hermes-skill-factory (community, ★523)** — a meta-skill that watches an agent's own workflows and auto-converts them into reusable skills, alongside siblings that tighten skill lookup with multi-layer retrieval. Unverified and community-maintained — the pattern of agents productizing their own habits is worth a look before you install. [hermesatlas.com](https://hermesatlas.com/projects/Romanescu11/hermes-skill-factory)

## What I'm watching

Whether DeepSeek's repricing is a one-off or the start of a ladder, because the
endgame of a rising budget tier isn't a more expensive API — it's teams deciding
the cheapest inference is the open-weight rack they already control. Every step
up the API floor de-risks the self-hosting decision, which is exactly where
Mojo's open-source compiler and the 8 MB Lattice retriever both point: the cost
of running a useful AI system yourself keeps dropping on every axis but
electricity.
