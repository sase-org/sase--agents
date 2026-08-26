# Chat History - ace-run (research.18.final)

- **TIMESTAMP:** 2026-08-26 13:31:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.18.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260826_125054.md`

## Prompt

%id(final, clan=research.18) %m:@research_lead
%wait:research.18.cdx %wait:research.18.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

This project currently uses release-please to create release
PRs and the `ci_watch` chop (defined in my bbugyi200/bugyi-chops GitHub repo) to submit
those PRs automatically when all GitHub workflows/jobs are green. The problem is that
this project seems to move so fast that many hours often go by where every GitHub
workflow that's started gets canceled by a subsequent one. I'm not sure how to solve
this.

Can you do some research with the goal of helping me figure out how to approach this
problem? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.18.cdx` -> `__a`, `research.18.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both transcripts to identify which report each researcher wrote.

Two loose reports look like candidates. Let me read both transcripts to determine the correct `__a`/`__b` assignment.

Assignment confirmed: `cdx` → `release_automation_liveness.md` (`__a`), `cld` → `release_train_ci_starvation.md` (`__b`). Now let me read both reports.

Both reports are substantial and disagree on the central recommendation. Let me research the gaps myself — starting with the local repo evidence and the key disputed facts.

The decisive disagreement is whether merge queue is viable — which turns on whether commits reach master via PR or direct push. Let me check.

**Decisive finding:** 400/400 master commits are single-parent with zero PR-squash signatures. Let me verify how they land and check the disputed repo settings.

Report A's `allow_squash_merge: false` finding is **confirmed** — and all 200 recent commits were committed directly by Bryan, not by GitHub's merge machinery. Let me verify the `--squash` claim in the chop.

`ci_watch.py:869` uses `--squash` while the repo has `allow_squash_merge: false` — Report A's latent-blocker finding is confirmed. Let me see the full merge path.

Both reports describe the gate accurately. Now let me check the live state and verify the disputed capacity/API claims.

My independent count confirms Report B's figures (166 cancelled / 33 failed / **0 success**, Aug 24–26). Let me verify the runner-capacity claim and the disputed `queue:` concurrency option.

PR CI queue wait ≈ 0 min — Report B's "runners are free today" claim is **confirmed**. Now the disputed `queue:` option.

`queue: max` is **confirmed real** (shipped May 2026) — a genuine gap in Report B. Let me verify the remaining load-bearing claims.

`actstat` queries `?branch=<default>` with **no event filter** — Report B's R2 rationale is confirmed. Let me check one implication neither report drew out.

A finding neither report made: the **existing** daily cron shares the master CI lane and stamps `failure` on the tip SHA. Let me verify cadence and the current red.

My cadence numbers match Report B's within rounding (median 10.6 vs 10.7 min). One last check on the current red.

The red has **narrowed** — the latest run fails only `visual-test`, the one cluster present in 8/8 failures. I have what I need. Let me set up the directory.

Both reports are preserved with the correct `__a`/`__b` assignment. Now the consolidated report.

Layout verified and provenance is correct. Let me confirm the primary repo is untouched before finalizing.

Consolidated report written. Final layout:

```
sase/repos/research/202608/release_gate_liveness/
├── release_gate_liveness__a.md   (cdx — was release_automation_liveness.md)
├── release_gate_liveness__b.md   (cld — was release_train_ci_starvation.md)
└── release_gate_liveness.md      (consolidated)
```

## What the merge resolved

**The two reports disagreed on the central recommendation.** `__a` recommended a GitHub merge queue; `__b` rejected merge queues and recommended two-speed CI. I resolved this against evidence `__a` didn't gather: **400/400 recent master commits are single-parent, zero carry a PR-squash subject, all were committed directly by you, and the repo has 0 rulesets with master reporting `Branch not protected`.** Commits land by direct push. A merge queue is enabled through a ruleset that *requires PRs*, so adopting it means re-architecting SASE's landing model for ~76 commits/day — and `__a`'s own ratio argument (used to reject `queue: max`) applies to its own recommendation: each queue entry needs a ~107-min `merge_group` check, giving ~13 merges/day against ~76 commits/day. `__b` is right on the primary fix.

**But `__a` found a blocker `__b` missed entirely.** `ci_watch.py:869` hard-codes `gh pr merge --squash`, and the repo has `allow_squash_merge: false`. The first time the gate ever opens, the merge still fails. Confirmed both sides. That's now R3, ordered first because it's one setting.

**So the consolidated framing is three independently sufficient blockers**, not one: liveness (tip settled ~14% of wall-clock), correctness (0 green runs), and that latent merge failure. `__a` treated the red as a "separate correctness issue"; `__b` treated it as disease #1. Both matter.

## What I added

- **Re-measured the disputed numbers.** My independent count (166 cancelled / 33 failed / **0 success**) reproduces `__b` almost exactly; `__a`'s narrower figures came from a latest-500 query across all workflows that truncated master CI. Commit cadence matched `__b` within rounding. PR CI queue wait ≈ 0 min, confirming runners are genuinely free.
- **`queue: max` is real** — shipped May 2026, up to 100 pending runs. `__a` was right, `__b` never mentions it. It's the one-line answer to your literal complaint, and it's still the wrong fix: it converts cancellation into unbounded backlog.
- **Two findings neither pass made.** The existing `'17 6 * * *'` cron — commented as an *intentionally contended flake reproducer* — runs on master, shares the same concurrency group, occupies the lane for 74–152 min, and stamps `failure` on the tip SHA `ci_watch` reads. `__b` warned about this for a hypothetical future cron; it's already live. Separately, **the red has narrowed**: the latest run failed only `visual-test` where every prior run failed 4–6 jobs, and `visual-test` is in 8/8 — it's the one durable blocker, not the four-cluster set both reports describe.
- Verified `actstat` really does query `?branch=<default>` with no event filter (load-bearing for moving the heavy lane off master), and noted that a Team plan tripling concurrency wouldn't help — this is a latency problem, not a capacity one.

**Recommendation:** fast per-SHA master gate (≤8 min) as the only thing the release gate reads, heavy lane on a non-default `ci-full` branch, ordered R3 → R1 → R4 (fix the squash setting, then land the gate, then fix `visual-test` with per-commit signal).
