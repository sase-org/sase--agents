# Chat History - ace-run (research.y.cld)

- **TIMESTAMP:** 2026-08-05 18:22:32 EDT
- **MODEL:** claude/opus
- **AGENT:** research.y.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260805_173621.md`

## Prompt

%id(cld, clan=research.y) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase This project's test suite is getting to be very large and very slow, especially when parallel agents are run. Can you do some research with the goal of helping me mitigate this problem somehow? Don't be afraid to explore/recommend large architectural changes if that's genuinely the right approach, like splitting up the repo for example. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by getting oriented in the repo — test suite size, structure, and how parallel agents interact with it.

I have the measurements I need. Writing the report.

Research written to `sase/repos/research/202608/test_suite_scaling_and_parallel_agent_contention.md`.

## What I measured

I ran the full suite twice with `--durations=0` under realistic conditions (4–5 sibling agent workspaces running their own suites concurrently), plus targeted serial runs and micro-benchmarks.

**The suite is not slow because tests are slow — it's slow because every agent runs all 25,900, every time, against a fixed host-wide worker pool.**

- One `just test` = **3,648.7 CPU-seconds (60.8 CPU-min)** of measured execution
- Median test: **0 ms**. p75 = 30 ms, p90 = 250 ms. Slowest 1,000 tests (3.9%) = 63% of runtime
- 16 workspaces × one `just check` each ≈ 973 CPU-min against a **16–32 worker/min host ceiling** (the gate's budget is memory-bound and collapses from 32 to 15 under load — self-reinforcingly)

## Three findings worth acting on immediately

1. **CI is running on one worker.** `_suite_gate.py` subtracts a flat `_RESERVED_CPUS = 4`; on a 4-vCPU GitHub runner that gives a budget of **1**. I verified the arithmetic and it matches measured CI: `test (3.13)` 44 min, `test (3.12)` 66 min, against a 41.3 CPU-min non-visual suite. Also, most recent `master` CI runs are `cancelled` — pushes outpace a 66-minute leg.
2. **The visual lane is 27% of runtime for 1.6% of tests** (902.9 s / 420 tests). CI already runs it as a separate job and excludes it from the matrix; `just test` doesn't. Agents can get this today with `SASE_PYTEST_EXCLUDE_VISUAL=true`.
3. **Three tests in `test_dismissed_bundle_persistence.py` are 4.4% of the whole suite** (160.3 s) — they're scale tests that belong behind `slow`.

## Recommendation

**Not a repo split.** The seam is real (`ace/tui` = 42% of source, only 34 reverse imports), but it delivers a fixed ~2× for single-sided changes, adds permanent cross-repo version pinning, and leaves aggregate host demand unchanged.

Instead: **diff-scoped test selection as the default for `just check`**, full suite in CI. I measured this — matching test files against three real commits' changed modules ran in **18.3 s / 147.0 s / 166.5 s serially**, versus ~61 CPU-min, using a deliberately over-inclusive one-hop import heuristic. Median commit touches 9.3% of test files. That's a 20–200× cut, and scoped runs are fast enough serially to skip the worker pool entirely — which is what actually fixes the parallel-agent case.

Sequenced as: Step 1 (hours) = −36% suite CPU, CI 44 → ~15 min. Step 2 (1–2 weeks) = ~10–30× reduction in aggregate host demand. Step 3 (ongoing) = gate fair-share, a per-PR test-runtime budget to bend the growth curve, TUI harness cost.

One caveat on the growth data: test LOC grew **21× in six months** (30k → 641k), with the test:source ratio steady at 1.06:1. Both sides are growing at agent speed, so any fix that only trims today's suite is a one-time win against a curve that doubles every ~6 weeks — hence the governance item in Step 3.

I made that file this session, so I'll commit it.

Committed and pushed.

**`docs(research): add test suite scaling and parallel-agent contention report`** (`bf889a0`) in the research repo — `202608/test_suite_scaling_and_parallel_agent_contention.md`, 352 lines. `git status --short --branch` shows `main...origin/main` with no dirty files and no ahead marker, so it's clean and in sync.

The two finalizer entries (linked repo `research` and SDD sidecar `research`) resolve to the same checkout, so one commit covered both. The main workspace was already clean (just 2 commits behind `origin/master`, unrelated to this session).

One note: `sase commit` reported that prompt-archive/agent-hood publication was deferred because the agents sync lock was busy. The primary commit succeeded and the publication is queued to retry automatically — no action needed from me, but flagging it in case it doesn't clear.
