# Chat History - ace-run (research.20.cld)

- **TIMESTAMP:** 2026-10-18 10:20:25 EDT
- **MODEL:** claude/opus
- **AGENT:** research.20.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_095054.md`

## Prompt

%id(cld, clan=research.20)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.20.cdx`, `research.20.grk`, `research.20.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

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

Reading the two merge-queue research reports from the research sidecar now. After that I'll research Google's release process.

Now researching Google's release process (SRE book, *Software Engineering at Google*, testing blog, Chromium docs) while I check sase's current workflow files.

Google sources are mostly gathered. Now checking sase's current publish and CI workflows so the comparison is accurate.

Checking whether the fleet runs released sase or a source build, then I'll draft the report.

Live data shows something useful: Full CI ran 6 times on the unchanged SHA `ae9f044bb3` and passed 3 of them. Checking which jobs flipped.

I have enough evidence. Writing the report now.

Checking one claim before registering: whether the install breakage really went unnoticed, or was already tracked in a bead.

The outage *was* noticed: an agent filed `sase-16p` on Sep 22 and it sat in the ready queue for about 26 days. Fixing the two places that said nobody noticed.

Report written and anchors check out. Registering it as a durable artifact.

Registered. Now submitting the turn's final declaration.

I wrote the report. It is registered as an artifact (`file:explicit:f89418ea0e7bcd4a29395542`, label `research:202610/google_release_process_vs_merge_queue_release_plan__cld.md`), and the research repo commit is declared.

## How the plan compares to Google

**The philosophy matches; the mechanics differ, and that shows where the plan is thin.** Both rest on one trunk, small changes, a release train that leaves on time, building once and shipping the exact tested bits, signed provenance, flake hygiene, and an owner for a red build.

- **Google can't serialize landings.** It handles more than one change a second, so changes land after a fast presubmit. The heavy work comes after the merge: continuous testing, automatic culprit finding, automatic rollback, and release candidates cut from green head, not the latest commit.
- **sase can serialize, so the plan puts its effort before the merge.** *Software Engineering at Google* names serialized submits as what small projects do, so keeping the merge queue (and zero approvals) is the right call.
- **The gap is the lane the queue doesn't cover.** The checks that block a release but not a merge (3.13/3.14 tests, install smokes, core floor) are in Google's post-submit situation. The plan backs them with only a bead, one repair turn and a 48-hour escalation, and may cut them to nightly. The SRE book says the opposite: continuously run the tests that gate the release, and release from the last revision that passed all of them.

## New evidence from today

- **The release lane is now flaky, not broken.** Full CI ran 6 times on the unchanged commit `ae9f044bb3` and passed 3. Each failing job lost 1–2 of ~56k tests, and the failing tests passed in the green runs on that same commit. The planned rerun covers only the Master Gate, not the jobs release qualification uses. As written, Epic A would refuse about half of good release candidates.
- **The PyPI attestations will name the wrong commit.** 0.17.1 has them, but they record the commit that triggered the workflow run. Once Epic A builds the release commit from a scheduled run, that will usually be a later commit than the one built.
- **The fleet runs source, not releases.** apollo runs sase as an editable install of the main checkout. The "latest PyPI sase is uninstallable" bug (`sase-16p`) has sat ready since Sep 22, while a bare install resolves to 0.1.0.

## Ranked changes

1. **Make release qualification tolerate flakes:** rerun failing tests once in the release jobs, the same way as the planned gate rerun.
2. **Keep the release-blocking checks on the 2-hour cadence**, and add automatic culprit finding, revert-first, and a time-to-green target.
3. **Never claim a version before its exact commit has passed the release checks.** Run them inside the release PR's merge-queue run; also try Google's model of tagging the newest green commit with the version stamped at build time.
4. **Run the upload at the release commit and check its attestation after publishing.**
5. **Add a rollback and hotfix path:** a runbook to yank a bad release from PyPI, and a cherry-pick hotfix branch.
6. **Test the installed package, not just the source:** run the install canary as a real workflow against each candidate's wheel.
7. **Add DORA's failure and recovery metrics, plus a gate escape rate.**
8. **Pin the build tools so wheels are reproducible.**

None of these changes the architecture or the four-epic split. I couldn't retrieve the body of Google's 2016 flaky-tests post, so those figures come from secondary sources and are flagged. I make no claims about Chromium's commit queue internals because its docs returned errors. Practices vary by Google team, so if your Ads experience differs from the public sources, trust it and re-rank.
