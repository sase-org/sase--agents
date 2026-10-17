# Chat History - ace-run (research.1w.cld)

- **TIMESTAMP:** 2026-10-16 22:22:16 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1w.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215155.md`

## Prompt

%id(cld, clan=research.1w)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.1w.cdx`, `research.1w.grk`, `research.1w.mus`, `research.1w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Reading the Gas Town lessons report now, then I'll survey sase's current CI/landing/release setup.

Gathering live CI/release evidence: workflows, gate history, PyPI cadence, and the commit finalizer.

Still collecting evidence — now pulling PyPI release history and Master Gate pass/fail tallies.

Classifying recent red gates as flaky vs. deterministic by sampling failed test names.

Checking the local `check` pass rate from the ToolRun ledger, then I'll research external practices.

Now researching external practices (GitHub merge queue limits, Uber SubmitQueue, flaky-test handling, release-from-green patterns).

Full CI has failed 99 of its last 100 runs — checking which jobs keep it red, since release depends on it.

Evidence gathering is done. Writing the report now.

Report written and fact-checked; registering it as an artifact now.

Registered. Now submitting the final declaration (the research sidecar has the new report to commit).

I wrote the report and registered it as an artifact. My short answer: yes, protect `master`, but only once the CI gate gives reliable results. More importantly, protecting `master` alone wouldn't get releases going again.

**Report:** `202610/merge_discipline_for_a_green_releasable_master__cld.md` in the research repo, registered as `research:202610/merge_discipline_for_a_green_releasable_master__cld.md` (artifact `explicit:c806944bfda56185974b9b1c`). The host commits the file after this turn ends.

**What the live data shows:**
- **Master Gate:** green on 62 of its last 1,000 runs. 44% of pushes land before the previous push's gate run finishes.
- **Full CI:** green on 1 of 271 runs since Aug 27. Its `visual-test` job failed in every run I sampled.
- **Local `check`:** passed 10 of 405 runs on this machine.
- **Releases:** PyPI has had nothing new since 0.17.1 on Aug 29. Release PR #299 has been open for 48 days, and the last attempt ended `CORE_FLOOR_BLOCKED`.
- **Two separate kinds of red:**
  - Real breaks that land unchecked.
  - Flaky TUI timing tests, which fail about 30–40% of gate runs even when nothing is broken.
- **Repair epics don't hold:** at least eight have been aimed at "green CI, then ship 0.18.0". Each green window lasted about 36 hours before a new break landed.

**Changes I made to your requirements (all labelled in the report):**
- **The goal should be a releasable commit, not a green `master`.** A perfectly green Master Gate still wouldn't have shipped anything since August. Releasing also needs Full CI green and a published `sase-core` version that meets the minimum. Those three are never all true at the latest commit at the same moment.
- **Release from the newest fully green commit, not the latest one.** This is the quickest way to publish more often, and it was already listed as deferred in the August `release_gate_liveness` plan.
- **Rule: any check that blocks a release must also block merges**, or have a named owner and a deadline. `visual-test` has stayed red for weeks because only the scheduled Full CI runs it.
- **"PR-only" should mean a GitHub merge queue that agents land through automatically, with no human approval required.** The host finalizer already does every landing, so this is a finalizer change, not a change in how anyone works.
- **Fix flaky tests first.** Rerun a failed test once, and quarantine chronic flakes with an expiry date. At today's flake rate, any gate would bounce about a third of good changes.

**Why I disagree with the earlier advice:**
- **The August rejection of a merge queue doesn't hold up against today's numbers.** About 45 commits a day arrive, and a one-at-a-time queue can handle about 93 a day. The decision's own condition for reopening has been met.
- **I'd keep the gate off the agent host,** unlike Gas Town R1 and the Oct 1 report. The host is the scarce resource, its results differ from CI, and a host-side check can't stop pushes from other paths. GitHub runners cost nothing for a public org repo and give a real block on bad merges.

**Recommended order:**
1. **This week:**
   - Add flake handling and pin Python 3.12 locally.
   - Get one commit fully green.
   - Switch to tagging and publishing the last green commit (a nightly job picks it, with hatch-vcs versioning).

   Releases resume as soon as that one green commit exists.
2. **Next week:**
   - Add a `master` ruleset with a merge queue: rebase merging, zero approvals, nobody allowed to bypass.
   - Require only the CI jobs that are green today, and add the rest as each turns green, so nothing has to be frozen.
   - Run the gate on merge-queue builds, and stop `ci.yml` running its heavy suite on every agent PR.
   - Pilot this with a "queue" landing mode for some agents.
3. **Weeks 2–4:**
   - Build a host-side watcher that closes beads only once a PR has actually merged, and repairs or escalates rejected PRs.
   - Move Full CI to nightly with an owner.
   - Upgrade the org to GitHub Team if queue waits get long during busy hours. It raises the concurrent-job limit from 20 to 60 for about $4 a month (check the current price).

**Not yet verified:**
- Whether a CI job skipped by a condition counts as passing a required check on a PR.
- Whether the commit that lands on `master` is exactly the one the merge queue tested.

I didn't change any repo settings, workflows or decision records. The three decision records I propose need your approval through the memory-write process.
