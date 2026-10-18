# Chat History - ace-run (research.20.final)

- **TIMESTAMP:** 2026-10-18 10:45:42 EDT
- **MODEL:** claude/opus
- **AGENT:** research.20.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_095054.md`

## Prompt

%clan(research.20, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I've been thinking about making some big changes to sase's release process with the goal
of making them much more reliable. See the
merge_queue_fenced_master_and_exact_sha_releases.md and
merge_queue_fence_reassessment_and_epic_split.md files in the research sidecar repo for
context.

I used to work at Google where our release process was pretty good. How does our planned
release process compare to Google's release process? Is there any inspiration that sase
can take from this release process? End your analysis with a ranked list of changes that
you think I should consider making to this planned change in our release process. If your
report does not indicate that any changes need to be made, that is fine.]]) %id:research.20.final %m:@xlarge
%wait:research.20.cdx %wait:research.20.cld %wait:research.20.grk %wait:research.20.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I've been thinking about making some big changes to sase's release process with the goal
of making them much more reliable. See the
merge_queue_fenced_master_and_exact_sha_releases.md and
merge_queue_fence_reassessment_and_epic_split.md files in the research sidecar repo for
context.

I used to work at Google where our release process was pretty good. How does our planned
release process compare to Google's release process? Is there any inspiration that sase
can take from this release process? End your analysis with a ranked list of changes that
you think I should consider making to this planned change in our release process. If your
report does not indicate that any changes need to be made, that is fine.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.20.cdx`, `research.20.cld`, `research.20.grk`, `research.20.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.20.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.20.linker`, can find it:

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
├── <name>__gem.md
└── <name>__final.md
```

## Response

I've opened the research repo and found all four reports. Next I'll read them and the two context reports through `sase artifact read`.

Now the four input reports.

I have all four reports. Now checking the facts they disagree on or leave weak, starting with the publish workflow and packaging config.

The publish workflow runs on a schedule at master's tip. Next I'm checking cld's flaky-qualification evidence against current Full CI runs, and whether the sase wheel is pure Python.

Confirmed: one failing test out of about 56,277 per job. Next, checking the wheel type on PyPI and the toolchain pinning in sase-core.

Bare `pip install sase` still resolves to 0.1.0 today. Now the sase-core side: toolchain pinning and how it publishes.

sase-core pins the lock file but floats the Rust compiler (`channel = "stable"`). Next, checking release-please's draft and tag options to settle how a release candidate gets chosen.

No release-downgrade tests and no yank tooling exist. Next, a quick check of the earlier CV research for Bryan's Google team context, so the comparison matches the process he knew.

Files moved. One quick fact for the rollback section: why `sase==0.1.0` is still installable.

The report is written and registered (`file:explicit:fa0111974739a42e2b5aea94`). Submitting the final declaration.

The consolidated report is written and registered for the linker as `research:202610/google_release_engineering_vs_sase_release_plan/google_release_engineering_vs_sase_release_plan__final.md` (`file:explicit:fa0111974739a42e2b5aea94`). The four input reports (cdx, cld, grk, gem) were matched by their `research.20.*` wait names and moved into the same folder. The host commits the research repo after this turn ends.

## How the plan compares to Google

**Keep the architecture.** The plan shares Google's philosophy: it separates fast admission checks from heavy release checks, builds once and ships exactly what was tested, runs a release train, and automates releasing. On landing it is stricter than Google. Google's own CI book says it can't serialize submits at its scale and calls that the small-project approach. Every sase `master` commit would be a tested combination, which Google doesn't get.

**The gap is everything after the merge.** Google puts its heaviest machinery after submit and after release. It tests the release-gating targets continuously, finds the culprit and rolls it back, cuts releases at the last green revision, runs the shipped package before users do, and rolls back fast. The plan is thinnest exactly there, and the release lane after the merge is what stalled PyPI for 49 days.

**Your Ad Manager experience fits this.** Your records show separate beta, SB and GA launch changes, 100% shadow traffic, and 10% → 50% → 100% rollouts. Epic D's cutover already follows that pattern: a config default that keeps the queue off, an allowlist pilot, and the old push-triggered gate kept as an audit.

## New evidence from today

- **Qualification would be a coin flip.** Full CI ran six times on the unchanged commit `ae9f044bb3` and passed three. Each failing job had one or two failures out of about 56,277 tests. No workflow reruns failed tests.
- **Epic A would make PyPI's provenance false.** `publish.yml` runs on a schedule at `master`'s tip. Once the build checks out the release commit instead, PyPI's attestation would name a later commit that was never built.
- **Epic B breaks its own gate on a date.** An expired quarantine entry fails lint, and lint is required, so every merge fails on day 15. Epic B's own +30-day clock-shift test would also flag every quarantine entry.
- **Installs are still broken.** Plain `pip install sase` resolves to 0.1.0, the only release whose `sase-core-rs` dependency still exists on PyPI.
- **release-please needs the tag to exist** to find the previous release, so a version is claimed as soon as its bump lands. That settles the disagreement between the reports on how to pick a release candidate.
- **The sase wheel is pure Python**, so pinning the compiler mostly matters for sase-core's native wheels.
- **Neither `sase` nor `sase-core-rs` is on TestPyPI**, so a TestPyPI staging step (and the plan's own TestPyPI drill) needs setup first.

## Ranked changes

All eleven fit inside the existing epics, and none delays restoring installability.

1. **Make release qualification tolerant of flaky tests:** extend the gate's one bounded rerun to the release-blocking jobs.
2. **Give the release-blocking lane Google's post-submit discipline:** keep it on the 2-hour cadence, find the culprit automatically, revert it through the queue, and set a time-to-green target.
3. **Exercise the exact release files on Linux and macOS before PyPI**, with a real no-LLM workflow, not just an import check.
4. **Make quarantine expiry escalate** instead of failing the required gate.
5. **Claim a version only for a qualified candidate:** use draft releases plus `force-tag-creation` now; later, qualify inside the release PR's merge-queue run; design tag-on-green as the alternative.
6. **Add a way to undo a bad release:** a yank runbook, yanking uninstallable old releases so installs fail loudly, and a hotfix branch built by cherry-picking.
7. **Run the publish job at the tag** so PyPI's attestation names the qualified commit.
8. **Give release health a consequence:** a severity veto, and a hold on packaging changes while installs are broken.
9. **Test that release N's state still works with release N−1**, so rollback is real.
10. **Pin toolchains (mainly in sase-core)** and bake the build's identity into the wheel.
11. **Add instability metrics** (change-fail rate, recovery time, time to green) and a gate escape rate.

The report also lists what not to copy from Google (human review, percentage rollouts, affected-test selection, a monorepo, a branch per release, publishing every green build, stopping all landings on any red) and corrects smaller claims in the input reports.

Nothing outward-facing was done: no workflows, rulesets, releases, beads or memory files were changed, no CI was triggered, and nothing was yanked.
