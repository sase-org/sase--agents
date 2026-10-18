# Chat History - ace-run (research.22.cld)

- **TIMESTAMP:** 2026-10-18 11:56:44 EDT
- **MODEL:** claude/opus
- **AGENT:** research.22.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_111719.md`

## Prompt

%id(cld, clan=research.22)
%m:claude/opus@xhigh %wait:8y %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.22.cdx`, `research.22.grk`, `research.22.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you help me review all of the files that the previous agent just tagged in the
research sidecar repo, which are related to our efforts to make sase's PyPI releases
much more reliable? Once you've done that, you should think hard about what the best
possible solution is and how the work should be split up. It's fine if your
recommendation steals a lot from those other research files (i.e. no need to be
original). Converging on the best design/architecture is our main priority. 
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

Reading the 12 reports the previous agent tagged `pypi-release-reliability` in the research sidecar. I'll go through them with audited `sase artifact read` calls.

Now reading the core proposal first.

Still reading — I'm through 9 of the 12 tagged reports; now on the Gas City and docs-redesign ones (only their release-related sections).

Now the docs-redesign report's install/release-alignment sections.

I've read all 12 tagged reports. Next I'll check the live state (PyPI, rulesets, CI, publish workflow, beads) so my recommendation rests on current facts, not just the Oct 17–18 snapshots.

Step 0 is done (`master-integrity` ruleset active since Oct 17 22:54Z); PyPI is still 0.17.1 and #299 is still open. Checking CI health next.

Master Gate has been green for the last 5 runs, and Full CI passed 3 of 6 on `ae9f044bb3`. So why hasn't #299 merged? Checking its checks and the core pin.

#299's `release-core-floor-smoke` is failing. Checking whether the pinned sase-core commit is in any published core release.

The pinned core commit `72bf9203` is 8 commits past `v0.41.0`, so it isn't in any published core. Confirming that's what fails the floor smoke, and checking for a pending sase-core release PR.

Retention exists because of PyPI's 10 GiB per-project limit. I'll measure release size and current usage to get the real shelf life of a sase release.

Found it: `ci_watch` auto-merges release PRs for sase, sase-github and sase-telegram, but sase-core isn't in its `release_repositories`. Checking whether anything else merges sase-core's release PRs.

Today's sase-core daily cut (scheduled 07:41Z, actually ran 12:10Z) failed at "Merge release PR". Checking why.

An active epic, `sase-1mk`, now owns Track 0 ("ship v0.18.0"), and its phase `.8` watches sase-core 0.42.0 and then sase 0.18.0. Reading it so I don't duplicate it.

sase-core `master` CI is red on 14 of its last 30 pushes, so the core cut also inherits an unfenced, often-red `master`. I have enough evidence; writing the report next.

Writing the report now. It reframes the program around three promises (installable, releasable, landable), adds the core-lockstep and family-install evidence, and lays out a six-epic split.

Report written. Registering it as a durable snapshot now.

Registration succeeded (`file:explicit:0e3988efaa04bbb8524bd271`). Checking working-tree state across the repos I touched before the final declaration.

Only the new report file is dirty, in the research repo. Submitting the final declaration.

I read all 12 tagged reports, checked them against today's live state, and wrote my recommendation. It's registered as `file:explicit:0e3988efaa04bbb8524bd271`, and the host will commit it to the research repo when the turn ends.

**Report:** `202610/pypi_release_reliability_architecture_and_epic_split__cld.md` (label `research:202610/pypi_release_reliability_architecture_and_epic_split__cld.md`)

**What I keep from the tagged reports:** GitHub's native merge queue with zero approvals and rebase landing; publishing exactly the commit that was tested, built once; the three classes of checks (block merges, block releases only, advisory); one bounded rerun for flaky tests; handling for `master` going red with no landing ("drift"); and the Google report's 11 ranked changes.

**What I measured today that the earlier reports didn't have:**
- **Nothing blocking the release right now is a landing problem.** Master Gate has passed its last 5 runs. Release PR #299 fails only one check: `sase-core-rs` 0.41.0 lacks the `mobile_pairing_issue` binding.
- **The sase-core 0.42.0 release is ready but uncut.** Its release PR #331 is green, but today's once-a-day cut failed on a macOS-only test. `ci_watch` auto-merges releases for sase and its plugins, but not for sase-core.
- **Core lag is the normal state.** sase moved its core pin 137 times in 29 days. About 85% of that time the pin pointed at a core commit no published release contained.
- **What ships isn't what was tested.** CI tests sase against a core built from the pinned source; users get the PyPI wheel, usually built from a later commit.
- **Installs are broken for the whole family.** A clean install resolves `sase` 0.1.0 with `sase-github` 0.1.0 and `sase-telegram` 0.4.9. The newest `sase-github` requires a sase version that doesn't exist yet.
- **Retention deleted the core versions 0.17.1 needs**, even though `sase-core-rs` uses only 3.88 of its 10 GiB on PyPI.
- **Two items are already handled.** The Step 0 ruleset is live, and the new epic `sase-1mk` owns shipping 0.18.0.

**Recommended design.** Plan around three separate promises: installable, releasable and landable. The changes from the existing plan:
- **Release train first, not last.** Make the release train one automated, deterministic owner with a typed status for each blocker and an action for it.
- **Release sase and sase-core together.** Each sase release pins the exact core version it was tested against, and testing uses that published wheel.
- **Guard installs for the whole family.** Retain core versions by what releases actually need, refuse any release whose dependency floor isn't published, and run a daily install check on Linux and macOS.
- **Revert first, queue later.** Automatically revert a confirmed bad commit, starting with a human approving each revert, before building the merge queue.
- **Keep the queue as the end state,** behind the release work and a measured go/no-go review.

**Work split:** Track 0 (`sase-1mk`) plus six epics, each with its own verification steps:
- **E1** Installability and dependency lockstep (medium)
- **E2** Release train and steward (large)
- **E3** Trustworthy test signal (medium to large)
- **E4** Revert-first (medium)
- **E5** Queue-aware landing as a product feature (extra-large)
- **E6** Cut `master` over to the queue (medium)

E1–E3 start now in parallel, E4 follows E3's first phases, E5 is off the PyPI critical path, and E6 comes last.

**What you need to do next** (I didn't do any of this, since each step publishes or changes shared settings):
1. Cut sase-core 0.42.0: `gh workflow run release-plz.yml --repo sase-org/sase-core -f dry_run=false`, unless `sase-1mk`'s watcher does it first.
2. Once #299 merges, dispatch Publish right away, then check the PyPI wheel against the tag.
3. File PyPI's project-size increase request for `sase-core-rs`.
