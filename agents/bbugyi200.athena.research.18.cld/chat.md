# Chat History - ace-run (research.18.cld)

- **TIMESTAMP:** 2026-08-26 13:08:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.18.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260826_125054.md`

## Prompt

%id(cld, clan=research.18) %m:@research_b  #gh:gh_sase-org__sase This project currently uses release-please to create release
PRs and the `ci_watch` chop (defined in my bbugyi200/bugyi-chops GitHub repo) to submit
those PRs automatically when all GitHub workflows/jobs are green. The problem is that
this project seems to move so fast that many hours often go by where every GitHub
workflow that's started gets canceled by a subsequent one. I'm not sure how to solve
this.

Can you do some research with the goal of helping me figure out how to approach this
problem? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by mapping the actual setup — workflows, release-please config, push cadence, and the `ci_watch` chop.

Confirmed: commits land on `master` every few minutes. Now the workflows.

`gh` works — let me get empirical data on what's actually being cancelled.

Zero `CI / push` successes in 19 hours — 31 cancelled, 9 failed. Let me widen the window and read the `ci_watch` chop.

The release train has been stuck for **19 days** — PR #284 open since Aug 7, last tag v0.16.0 same day. Let me confirm the exact blocker.

Three independent blockers are emerging. Let me quantify the failure side and confirm GitHub's documented concurrency semantics.

Let me verify two facts that materially change the recommendation: repo visibility (runner cost) and whether `actstat` filters by event.

Let me get real job-minute costs rather than estimating, and confirm the exact concurrency limit.

Let me measure queue-wait directly — the cleanest evidence of whether the org is runner-saturated.

One decisive question remains for the design: whether `actstat` counts non-push runs against a commit.

One last computation — the settle-probability model that drives the recommendation.

Now I'll write the research report.

The report is written. Now the finalizer declaration.

Written to `sase/repos/research/202608/release_train_ci_starvation.md`.

## What I found

Your diagnosis was half right, and the other half is the part that's actually killing you.

**The cancellations are real but they aren't the blocker.** `ci_watch`'s first gate is "is the default branch green," and master CI has produced **165 cancelled, 33 failed, 0 successful** runs over three days. Every one of the 33 that completed failed on real, repeatable assertions (`OptionDoesNotExist: 'small'`, `NoMatches: '#confirm-btn'`, an `artifacts_subtab` visual timeout, `phase7-perf-check`). Master is genuinely red. Release PR #284 has been sitting `MERGEABLE`/`CLEAN` since **Aug 7 — 19 days, 1,589 commits**.

**The cancellations are why it's red and stays red.** `cancel-in-progress: false` doesn't give you a deep queue — GitHub allows one running plus *one pending* run per group, and each new push cancels the pending one. Master CI takes ~107 min; commits land every ~11 min. So only **13% of master commits ever get a completed run**, and only **2% get one that finishes before the next push**. Regressions land unobserved, then surface hours later in a run spanning ~7 commits with no attributable author.

**Runners are not your constraint.** PR CI runs start in 0.1 minutes — the 26–74 minute master waits are entirely self-inflicted concurrency-group pending time. But you also can't just delete the block: full verification is 234 job-minutes × 82 commits/day = **66% of your account's 20-slot ceiling**, and PR CI needs another ~59%. That's the starvation your `ci.yml` comment already records.

Also worth knowing: the release PR side is nearly innocent. Its CI is a single job that finishes in **73 seconds** — the empty-rollup window is ~11% of ticks, not a 19-day stall.

## Recommendation

Apply the project's own two-speed verification decision to CI itself:

- **R1** — a fast `master-gate.yml` (lint + scoped 3.12 tests + PyPI core wheel, **≤ 8 min / ~12 job-min**, per-SHA concurrency so nothing is ever cancelled). Takes attributable coverage 13% → 58%, settled-tip 14% → 68%, for 3.4% of budget.
- **R2** — heavy lane onto a non-default `ci-full` branch fast-forwarded every 2h. This detail matters: `actstat` groups *all* default-branch runs by SHA with **no event filter**, so a cron on master would re-poison the tip for 90 minutes at a time.
- **R4** — throttle release-please to a schedule; that closes the `empty_rollup` and `generator_busy` conditions.
- **R0/R5** — fix the four red clusters, and pin `sase-core` (currently checked out at unpinned HEAD, so a core push can redden `sase` with no `sase` commit).

I recommend landing R1 *before* fixing the red, so the repair work gets per-commit signal instead of the 1-in-8 signal that let it accumulate.

Two open decisions I'd want your call on are in §11 — the `ci-full` branch vs. adding a `gating_workflows` allowlist to `ci_watch` (faster vs. more principled), and whether the last-known-good release train is worth building now.

Sources: [GitHub concurrency docs](https://docs.github.com/actions/writing-workflows/choosing-what-your-workflow-does/control-the-concurrency-of-workflows-and-jobs), [Actions limits](https://docs.github.com/en/actions/reference/limits), [Mergify](https://mergify.com/blog/github-merge-queue-was-step-one-real-ci-orchestration-comes-next), [TianPan](https://tianpan.co/blog/2026-07-02-the-merge-queue-is-the-new-bottleneck), [Aviator](https://www.aviator.co/blog/merge-queues-for-large-monorepos/), [release-please](https://github.com/googleapis/release-please).
