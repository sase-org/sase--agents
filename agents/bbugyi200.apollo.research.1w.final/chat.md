# Chat History - ace-run (research.1w.final)

- **TIMESTAMP:** 2026-10-16 23:25:39 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1w.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215155.md`

## Prompt

%clan(research.1w, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] After reading the gastown_vs_sase_lessons_to_borrow.md file in the research sidecar
repo, it seems like to me that sase needs better merge discipline.

- Namely, we need a way to ensure that master stays green so we can start publishing new
  versions of sase to PyPI more often.
- I'm not sure if we need to adopt a PR-only (i.e. protected master branch) workflow to
  achieve this (or if that's recommended anyway) or if there is some other way.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.1w.final %m:@xlarge
%wait:research.1w.cdx %wait:research.1w.cld %wait:research.1w.grk %wait:research.1w.mus %wait:research.1w.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.1w.cdx`, `research.1w.cld`, `research.1w.grk`, `research.1w.mus`, `research.1w.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.1w.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1w.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

I've read the cdx and cld reports and now I'm reading the remaining three (grk, mus, gem) before doing my own research.

Five reports read; now checking the repo's release and CI workflows myself to settle the points where they disagree.

Confirmed the April 2026 GitHub merge-queue incident (squash-method groups) and the docs' build model. Now simulating queue latency using real push arrival times and gate durations.

Bots already land via PRs, so they'd work under a protected master. Checking how the release watcher merges the release PR, then I'll write up.

Verified the sase-github merge-success bug. Two quick fact checks before writing: release-please's `sha` output, and whether the merge queue lands exactly the tested commit.

Fact checks done (`sha` output exists). Now I'll move the five reports into the consolidated folder and write the final report.

Registration succeeded. Now the final declaration.

I've written the consolidated report and registered it as `research:202610/merge_queue_fenced_master_and_exact_sha_releases/merge_queue_fenced_master_and_exact_sha_releases__final.md` (ref `file:explicit:2275ecc4b9284da3e2884d94`). The five reports, one per suffix, now sit in that folder under their new names; the host commits the move after this turn.

## Short answer

Yes, sase needs better merge discipline, and yes, protect `master`. But "PR-only" isn't the mechanism that keeps it green. Required PRs alone test each change against an out-of-date `master`. What keeps it green is **GitHub's native merge queue**: it tests each change on top of `master` plus everything queued ahead of it, and only that tested result lands. The queue needs PRs, so here they are plumbing the host creates, with zero required approvals. Required reviews would deadlock anyway, because agents push as you and GitHub won't let you approve your own PR.

## Requirement changes I'm making (called out in the report)

- **Releasable, not always green.** The real goal is "a fully tested SHA exists and gets published on a cadence". A green `master` is the means. Even a perfectly green Master Gate would have shipped nothing since Aug 29: Full CI has passed 1 of 271 runs.
- **Publish exactly what you tested.** `publish.yml` builds whatever `master` is when it runs, not the release commit. Nothing requires the full CI suite on that exact commit. This is a small fix and the fastest route back to PyPI.
- **Fix the flaky tests before enforcing anything.** Most green→red flips are TUI timing flakes; today's newest red is one of them.
- **Anything that blocks a release must also block merges,** or have an owner and a deadline.
- **Merged is its own state,** separate from "agent finished".

## The five researchers split, and I sided with cdx and cld

- **For:** cdx and cld recommended the merge queue now, and mus recommended it later.
- **Against:** grk and gem wanted the agent host to run the checks before pushing ("host landing lane"). My own measurements rule that out:
  - **The local check is a poor gate.** Over 14 days on apollo it passed 6 of 168 runs, with a 12 min median and 59 min at p90.
  - **One host's lock can't order everything.** Landings come from both athena (649) and apollo (73), so a single-host lock doesn't serialize them.
- **Capacity fits.** GitHub's runners are mostly idle when a gate needs them: the slowest test shard waits 4 s at the median and 2.5 min at p90. I replayed this week's real pushes through a model of the queue. Running two builds at once, changes land in about 13 min at the median and 27–34 min at p95, as long as flaky failures stay under 10%.
- **Reopen the August decision.** That decision (`ci-two-speed-split`) rejected a merge queue, but its own reopen trigger has been met.
- **Use merge commits, not squash or rebase.** GitHub's April 2026 merge-queue incident hit squash groups (and possibly rebase), and merge commits keep the agent's commit SHA.

## Recommended sequence

1. **This week:**
   - Block force pushes and deletion on `master`.
   - Make Publish build release-please's `sha` output, run the full CI suite on that SHA, and publish only those files.
   - Ship 0.18.0 from PR #299; its core-floor check turned green this morning.
2. **Weeks 1–2:** make the gate trustworthy.
   - Rerun a failed test once, and quarantine known flakes on a list where entries expire.
   - Commit `.python-version`.
   - Move the visual tests into the gate.
   - Run Full CI nightly instead of every 2 h.
3. **In parallel:** pilot the queue.
   - Add `merge_group` to the workflows, plus one combined required check.
   - Add a host-side "queue" landing mode behind a feature flag.
   - Add a watcher that closes beads only once a change has provably merged.
4. **Then enforce:** require the queue with nobody allowed to bypass it, and run a nightly release train (a release every 1–3 days).

## Gaps the switch would expose

- **sase-github treats "queued" as "merged".** `_submit_via_pr_merge` counts any exit 0 from `gh pr merge` as a merge, but against a queue that only means the PR was queued.
- **The release watcher would stop finding results.** It looks up Master Gate runs by branch `master`, and queue runs happen on other branches, so it must switch to looking up by SHA.

No settings, workflows or memory files were changed, and nothing was piloted. Four behaviours aren't confirmed by GitHub's docs and need checking in the pilot:
- whether `master` ends up at exactly the commit the queue tested;
- whether requiring the queue alone blocks direct pushes;
- how PRs made with your credentials trigger workflows;
- whether release-please's draft option fits the publish flow.

Sources: [GitHub status: April 23 incident](https://www.githubstatus.com/incidents/zsg1lk7w13cf) · [GitHub blog: availability update](https://github.blog/2026-04-28-an-update-on-github-availability/) · [The Stack](https://thestack.technology/github-bug-messed-up-customer-code-coo-plays-down-incident/) · [GitHub merge queue GA changelog](https://github.blog/changelog/2023-07-12-pull-request-merge-queue-is-now-generally-available/) · [GitHub Docs: managing a merge queue](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue)
