# Chat History - ace-run (research.2v.cld)

- **TIMESTAMP:** 2026-09-28 05:57:53 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2v.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_052837.md`

## Prompt

%id(cld, clan=research.2v)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2v.cdx`, `research.2v.grk`, `research.2v.mus`, `research.2v.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It's been a while
since sase released a version to PyPI. This is because master is always red. I need to
fix these failing CI jobs and release the next version to PyPI.

Can you do some research with the goal of helping me figure out what needs to be done?
End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'm pulling CI logs now. The latest Master Gate has lint failing plus 6 of 8 test shards, and nearly every job in the last Full CI run failed.

Found release PR #299 (0.18.0), open since Aug 30, plus 17 stale core-pin ratchet PRs piling up. Now checking how releases are gated.

The release PR's only gate, `release-core-floor-smoke`, fails because the published `sase-core-rs` 0.35.1 lacks 10 bindings that sase now calls. Next I'm checking when Master Gate was last green.

Last green Master Gate was 2026-09-18 (f90c6b549f), and Full CI has passed exactly once, on 2026-08-29. Now I'm finding what merges the release PR (`ci_watch`).

`ci_watch` also requires the release PR's `mergeStateStatus` to be CLEAN (it's UNSTABLE now). Next I'm checking whether sase-core has the 10 missing bindings unreleased on its master.

sase-core's own CI is red on master too, which would block its release. Checking why, and how its release-plz cut is gated.

sase-core master has been red since 297bc1e3 (2026-09-27): clippy lints first, then test failures that change from run to run. Now reading its release-plz gating.

Pulling the Full CI failure details now. contention-test hung until the job timeout killed it, and visual-test has at least one timing-sensitive snapshot failure.

~30 deterministic-looking test failures show up identically on 3.12, 3.14, and the Master Gate shards. I'm checking whether they reproduce locally on the current tree.

26 of the failures reproduce locally in 36s, so they're deterministic regressions rather than CI flakes. Next I'm getting short tracebacks to find each one's root cause.

Each cluster traces to a specific recent feature (agent tabs, tool receipts, update gear, and so on). Next I'm running `git log -S` to attribute each one to its introducing commit.

I've found the core picture. Now checking a few remaining details: Full CI job timeouts, the perf-floors failures, and how the core-floor ratchet works.

The tool-runs smoke failure reproduces locally too. Re-running one case with the slow marker enabled to capture why.

Master has no branch protection, and the ratchet opens a new branch/PR for every sase-core SHA, never closing old ones. Checking how much runner time each of those PRs uses.

Plugin dependencies are all published. Last thing: checking whether the sase-core-rs PyPI project is near its 10 GB storage quota, since that could block the 0.36.0 upload.

PyPI storage for sase-core-rs is fine (2.68 GB of 10 GB), so that won't block the upload. Before writing, I'm confirming the root cause of the largest cluster, the 9 `test_agent_completion` failures.

The snapshot includes the final edit. Now the final declaration.

The report is written and registered as a durable snapshot (`file:explicit:66da0dbe0039131582092456`, label `research:202609/sase_red_master_ci_and_pypi_release_unblock__cld.md`).

**Why nothing has shipped:** the last PyPI release was 0.17.1 on 2026-08-29, and 1,676 commits have landed since. Release PR #299 (0.18.0) has been open since Aug 30. `ci_watch` only merges it when four things are true at once, and none of them are:

1. **Master Gate green at HEAD.** It hasn't passed since 09-18, 847 commits ago. HEAD has 29 failing tests plus a lint failure from two files over the 1,000-line limit (`tool_run.py`, `executor.py`). 26 of the 29 fail every time when I run them locally (36s). Each group traces to one recent commit whose tests or allowlists weren't updated: the `%tab` directive, agent-tab inheritance, the `sase tool receipt` CLI, the receipt policy in `sase.yml`, the update gear, and so on.
2. **Full CI green within the last 6 hours.** It has passed once since Aug 27 and can't pass as currently set up:
   - `test (3.13)`, which runs `test-cost`, has timed out at 90 minutes on every run since 08-29, getting about 56% through.
   - `coverage-contexts` times out at 60 minutes.
   - `contention-test` (26 workers on 2 CPUs, 3 full-suite repeats) loses its runner every run.
   - `perf-floors` and `visual-test` also have real, repeatable failures.

   This condition alone has blocked every automatic release for a month.
3. **The release PR's own check green.** `release-core-floor-smoke` fails because the published `sase-core-rs` 0.35.1 lacks 10 functions master now calls.
4. **A `sase-core-rs` 0.36.0 on PyPI with those functions.** Its release PR #315 is blocked because sase-core's CI is red on tests that pass on one run and fail on the next: two on macOS, one on Linux.

**Why master stays red:**
- About 85 commits a day land straight onto an unprotected master, and nothing stops landings when CI goes red.
- About 77% of the last 1,000 local `check` runs failed, and only about 8% passed.
- The cheap whole-repo guard tests aren't always run by local checks. Once one is red, new violations pile onto it unnoticed: the timezone guard picked up a second one today.
- 17 outdated automated core-pin PRs have each run full CI, roughly 85 runner-hours in total.

**Recommendation:**
1. Briefly pause feature landings and close the outdated core-pin PRs #302–#318.
2. Fix or quarantine the three unreliable sase-core tests, get PR #315 green, trigger the 0.36.0 release manually, then move sase's `sase-core-rs` requirement to `>=0.36.0,<0.37.0`.
3. Fix the roughly 13 Master Gate failure groups. They're all small; the report has a table with the cause, commit, and suggested fix for each.
4. Move `test-cost`, `contention`, and `coverage-contexts` out of `Full CI` into a separate non-gating workflow, and fix the real `perf-floors` and `visual-test` failures.
5. Cut 0.18.0. If step 4 will take days, a one-time manual merge of #299 is reasonable once steps 2–3 are green and #299's own check passes. The publish job still runs its install checks before uploading. Don't skip step 2, though: a wheel built against 0.35.1 would crash at runtime on the missing functions.

The report ends with prevention measures, including automatically stopping landings when master is red and running the guard tests in every local `just check`.

I didn't implement or test any of the suggested fixes. Two causes are inferred rather than observed: that the contention runner runs out of memory, and that the macOS failures are intermittent (the same code passed on sase-core master but failed on the release PR). The lint steps that come after the line-limit check haven't run on master for days, so more failures may appear once it passes.

Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202609/sase_red_master_ci_and_pypi_release_unblock__cld.md`
