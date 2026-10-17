# Chat History - ace-run (research.1w.mus)

- **TIMESTAMP:** 2026-10-16 22:52:45 EDT
- **MODEL:** claude/sonnet
- **AGENT:** research.1w.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215155.md`

## Prompt

Your previous attempt hit a model context limit or transient provider failure. Any file edits, new tests, and other on-disk changes you made are preserved. Before making additional changes, run `git status` and `git diff` to see what is already in place, then continue implementing the plan from wherever you left off. Do not re-apply edits that are already present.

%id(mus, clan=research.1w)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.1w.cdx`, `research.1w.cld`, `research.1w.grk`, `research.1w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

After reading the gastown_vs_sase_lessons_to_borrow.md file in the research sidecar
repo, it seems like to me that sase needs better merge discipline.

- Namely, we need a way to ensure that master stays green so we can start publishing new
  versions of sase to PyPI more often.
- I'm not sure if we need to adopt a PR-only (i.e. protected master branch) workflow to
  achieve this (or if that's recommended anyway) or if there is some other way.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll check what's already on disk from the previous attempt.

I'm reading the landing-discipline sections of the Gas Town report and the earlier master-red report, before I check the live repo state.

I'm checking the release and publish plumbing now (`publish.yml` and the `ci_watch` release logic). That tells me what actually gates a PyPI release.

I'm moving to the outside research on GitHub merge queues, rulesets and submit-queue prior art. I'll also pull the local `check` stats that size a pre-push gate.

I'm classifying the 15 red onsets, to separate real breaks from flakes. That decides how much a merge gate could prevent versus how much flake handling is needed.

The local evidence is complete. I'm now running three quick searches on the load-bearing external facts: release-please's `target-branch`, Chromium's LKGR, and the Actions concurrency limits.

I have the evidence I need. Writing the report now.

Now I'll register the report as a durable snapshot.

I wrote the report and registered it as an artifact. The registration succeeded as `file:explicit:d8b1c3e547d37d881792f5a3`, labeled `research:202610/merge_discipline_green_master_and_pypi_release_cadence__mus.md`. The report is at `sase/repos/research/202610/merge_discipline_green_master_and_pypi_release_cadence__mus.md`.

The recommendation is to release from a proven SHA, make red trustworthy, stop landings piling onto a red master, and add fix-or-revert. A PR plus GitHub merge queue is the end-state, adopted only if measured triggers fire. PR-only branch protection is not recommended on its own. Required checks test the PR head against a stale base, and `ci.yml` runs the full Python 3.12–3.14 matrix on PRs, which takes over 100 minutes. What protects master is a merge queue that tests the merged result.

**What the data showed:**
- **No release for 49 days.** PyPI's last release was 0.17.1 on 2026-08-29. The 28 releases before it came about one per 2.8 days.
- **Full CI is the real release blocker.** It has passed once in its last 271 runs, on 2026-08-29. The release watcher needs a recent green Full CI. A landing queue that only runs the Master Gate would not have made 0.18.0 shippable.
- **The wheel is built from the tip.** `publish.yml` checks out the default branch with no `ref:`, so the published wheel is whatever master is when Publish runs, not a SHA that was verified.
- **Master Gate was red about half the time** (Oct 13–17, 145 runs). Of 16 red episodes, 5 lasted an hour or more and held 93% of the red minutes. The other 11 were short blips.
- **Most red onsets look like flakes.** About 12 of 15 were recurring timing tests in the TUI suite, and 3 looked like real regressions. I classified by test name and recurrence, not by rerunning, so treat that split as medium confidence.
- **A merge queue on this suite would reject good changes.** The org is on the Free plan with a 20-job concurrency cap. A merge queue is available for public org repos, so `sase-org/sase` should qualify. I did not enable it or measure runner queue waits.

**Requirement adjustments, flagged in the report:**
- **Goal changes.** The goal moves from "master stays green" to "a releasable SHA under 24 hours old always exists", with a red-minutes budget for the tip.
- **Two tiers of green.** Gate-green and release-green are separate; release-green means Master Gate, Full CI and the core-floor smoke all pass on one SHA.
- **PR-only dropped.** It is no longer a requirement.
- **Added requirements.** These are publishing the verified SHA, a flake budget, deferral (not blocking) when landings are refused, and a scheduled release cadence.

**Recommended order:**
1. **Release from a proven SHA.** Keep an `lkg` ref (last known good) and build the wheel from it. The release-please non-default-branch behavior needs a one-day spike.
2. **Make red trustworthy.** Quarantine the recurring flakes with an expiry, rerun failed test shards once, and fix Full CI's real failures.
3. **Stop the pile-on.** Defer non-repair landings while a confirmed red HEAD stands, and add a cheap combined-tree guard after rebase (`sase-1cb`).
4. **Fix-or-revert within 60 minutes.** My model puts red time at about 11%, down from 50%, and about 7% if the flake blips are also removed.
5. **Decision gate for the queue.** Adopt PR + merge queue + ruleset only if measured triggers fire; the report lists them.

The final declaration is submitted, so the host commits the report to the research repo after this turn.
