# Chat History - ace-run (research.2a.cld)

- **TIMESTAMP:** 2026-10-23 12:30:18 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2a.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261023_115726.md`

## Prompt

%id(cld, clan=research.2a)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2a.cdx`, `research.2a.grk`, `research.2a.mus`, `research.2a.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about moving forward with the E3 epic described by the
pypi_release_reliability_design_and_work_split.md file in the research sidecar repo. Can
you do some research with the goal of making sure we are ready for this epic, describing
the work that has been done so far (e.g. E1 and E2) and what developer-facing behavior
has been changed by that work, and starting the design for the E3 epic? 
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

Status: I've read the E3 design doc (`pypi_release_reliability_design_and_work_split.md`). Next I'm going through the beads and git history to see what E1 and E2 actually shipped.

Status: evidence-gathering is nearly done. I'm checking the exact `FLAKY:` handoff contract E2 left in `ci.yml`, then I'll write the report.

Status: writing the report now.

Status: the report is written. Registering it as an artifact now.

I've written the report and registered it as an artifact (`file:explicit:932a80be8097445aa240d311`, label `research:202610/e3_trustworthy_signal_readiness_and_design__cld.md`). The research repo commit happens when this turn ends. Short answer: E3 is ready to plan, but its CI-workflow phases shouldn't start yet. My measurements also show the design's main assumption about E3 is mostly wrong.

**Work so far**
- **Track 0 and E1 are done.** sase 0.18.0 is on PyPI and the plugins resolve cleanly. E1 (`sase-1my`) closed on 10-19 with its live checks passing. You declined the 7-day soak and the TestPyPI drill.
- **What E1 changed for developers:**
  - Bare `uv tool install sase` now fails loudly instead of installing 0.1.0, because 0.1.0 is yanked.
  - A daily install check runs on Linux and macOS and reports failures as one issue, which becomes a task bead.
  - Plugin release PRs now fail if they require a sase version that isn't on PyPI yet.
  - sase-core retention refuses to delete any core version a supported sase release depends on.
- **E2 (`sase-1n6`) is about 60% landed but hasn't released anything.** The tag build, exact core pin, Linux/macOS install tests, qualification code, an observe-only steward and release metrics are all on master. Publish/confirm, the cutover and the first steward release are not.
- **What E2 changed for developers:**
  - `pyproject.toml` now pins `sase-core-rs==0.42.0` exactly.
  - `just ratchet-core-window` is now `just ratchet-core-pin`.
  - `tools/release_watch` was rewritten with new flags (`--once`, `--tick --live`, `--json`, `--until-released`). It needs a core binding that no published core has yet.
  - `ci.yml` takes new inputs (`ref`, `core-source`, `core-version`) and uploads per-job test evidence.
- **Releases still use the old path.** `ci_watch` merges the release PR and `publish.yml` publishes it. A new epic, `sase-1nn`, is pushing 0.18.1 that way right now.

**Readiness for E3**
1. **Full CI has been 100% red since 10-20.** It fails during `build-core` setup (`sase-1nn.3`), so E3 can't measure anything on it until that fix lands.
2. **E2's qualification check conflicts with E3's rerun design.** It treats any failed test as red, so a flake that passes on rerun would still block a release. E3's rerun phase has to change E2's evidence format and edit two E2-owned files, which needs an agreed handoff.
3. **E2 has a rerun bug.** The steward's rerun also reruns lint, which its own policy excludes. That fix belongs to E2, not E3.
4. **Two overlapping beads should be closed first.** `sase-1jz` (green gates with stable TUI goldens) is still in progress and overlaps E3's visual work; `sase-16p` is moot.

**What the data says**
I parsed the failure logs of every red Master Gate run from the last 7.5 days (200 runs):
- `master` was red 82% of the time.
- Only 9 of 162 red runs (about 6%) were flake-only, worth 3% of the red time. So a perfect bounded rerun would barely move red time. It's still worth building so releases don't burn a version on a one-off flake.
- Almost all reds are real breaks that stay unfixed: median 2.5 h, p90 9.3 h, longest streak 33 runs. About 12.6% of commits started one.
- The design's culprit rule ("first red commit with a green parent") fits only 10 of 63 breaks, because 53 landed while master was already red. Each Master Gate run tests exactly one commit, so the culprit can instead be found per failing test.

**Proposed E3 design (in the report)**
- **Order:** start with a read-only signal ledger, which can begin now. Then per-test culprit attribution with a dispatchable `culprit-check.yml`, then a fix so one red lint step doesn't hide the others, plus Python and core version parity. After that: the bounded rerun with the new evidence format, a small quarantine, a +30-day drift test under its own workflow name, and the visual study.
- **The drift test must not run as `master-gate.yml`.** Otherwise `ci_watch` and the steward would read a red drift run as that commit's gate result.
- **Let E4 start earlier.** E4 (revert-first) can begin in propose mode once attribution is live, without waiting for the rerun helper.
- **E3 alone won't make master green.** That needs reverts or refusing landings while master is red, and no epic owns that today.
- **Size L** rather than M–L, plus eight decisions to settle in the plan.

One naming catch: "E3" is already used by the instruction-migration epic (`sase-1ko`), so title the new bead "E3: Trustworthy signal (PyPI release reliability)".

Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202610/e3_trustworthy_signal_readiness_and_design__cld.md`
