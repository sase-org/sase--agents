# Chat History - ace-run (research.5g.cld)

- **TIMESTAMP:** 2026-10-29 01:03:23 EDT
- **MODEL:** claude/opus
- **AGENT:** research.5g.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261029_002947.md`

## Prompt

%id(cld, clan=research.5g)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.5g.cdx`, `research.5g.grk`, `research.5g.mus`, `research.5g.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The sase-core repo keeps failing CI. I'm wondering if there is a way we can fix this
with a post-commit hook or something like that to prevent these same types of failures
from continuing to recur. Can you do some research to help me understand the nature of
these failures? End your analysis with a recommended solution. 
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

I'm going through sase-core's CI run history (many recent master pushes are red) to sort the failures into categories before recommending a fix.

Downloading the failed-job logs (the first try was blocked by an escape-sequence guard) so I can pull out exactly which tests failed.

Now classifying the clippy and test-compile failures, which don't show up as named test failures.

Clear categories are emerging. Next I'm checking the specific root causes: when each regression was introduced and fixed, the macOS-only failures, and the recurring flakes.

Status: I confirmed the ledger's file hashes are plain SHA-256, so I can check exactly whether each landed commit's tree was ever checked locally. Running that match now.

Status: found existing flake beads, but none for the top CI flake (`concurrent_readers_see_consistent_snapshots`). I'm checking that test and the macOS-only failures, then I'll write the report.

Status: data collection is done. Master's tip was red about 29% of the time in October. I'm sorting the ~75 failure episodes into root-cause classes and then drafting the report.

Status: analysis is complete. Checking one implementation detail before writing: whether the commit workflow re-stages files the before-hook changes (this decides whether an auto-format hook works).

Report written. Registering it as a durable artifact.

The report is written and registered (`file:explicit:b4342bf7d4353ece0025cb69`, label `research:202610/sase_core_ci_failure_taxonomy_and_landing_gate__cld.md`). The host will commit it to the research repo when this turn ends.

**Report:** `sase/repos/research/202610/sase_core_ci_failure_taxonomy_and_landing_gate__cld.md`

**How bad it is.** sase-core's master was red 29% of the time in October, and 40% of October's master pushes failed CI. That red master also failed all 121 failed release-plz PR runs that month. I sorted all 467 failed CI jobs since Sep 16 into 74 separate failure episodes, in five classes:

| Class | Episodes | Red hours | Would a local gate catch it? |
|---|--:|--:|---|
| Formatting, clippy, hakari features, compile errors | 19 | ~90 | Yes, in seconds to about 2 minutes |
| Tests that fail every run, on Linux too | 9 | ~48 | Yes, with a full `just check` |
| macOS-only failures | 8 | ~87, including the longest (27 h) | No, except the compile errors |
| Flaky tests | 34 | ~46 | No |
| CI config | 4 | ~7 | No |

(Red hours overlap when two failures are open at once.)

**Key findings:**
- **Commits that passed a local check never caused the first two classes.** I matched each landed commit against the local record of `check` runs (athena only). The 150 of 231 commits whose exact content had passed `check` introduced none of these failures. Every one I could trace either never ran a sase-core check, was edited after its last check, or landed after its check failed. 39 commits landed on a failed check.
- **Most of the unchecked commits came from agents working in the sase repo that also edited sase-core** (9 of 11 traceable causes). Those agents ran sase's `check`, which doesn't format, lint or test sase-core.
- **sase-core's existing pre-commit hook does nothing.** Its before-commit hook resolves to `sase_git_fix`. That script looks for a capital-J `Justfile` and a `fix` recipe, and sase-core has neither. All 40 recent runs exited 0 in about 0.05 s.
- **One test failure can hide another.** `cargo test` stops at the first failing test binary, so a second regression from the same change only showed up after the first was fixed. One change kept master red for about 27 hours this way.
- **macOS compile errors can be caught on Linux.** A `cargo check --target aarch64-apple-darwin` with a stub C compiler reproduced CI's exact `mode_t` error on the breaking commit `916d5e3a`, in about 2 minutes.
- **The biggest flake has no owner.** `concurrent_readers_see_consistent_snapshots` failed 37 CI jobs, is failing on the current tip, and has no flake bead.

**Recommendation.** A literal git post-commit hook can't help: it runs after the commit exists and can't block it. The hook that matters is sase-core's before-commit hook. Turn it into a landing gate that:
- runs `cargo fmt`;
- lets the commit through if a passing `check` already covers this exact tree (that needs a receipt policy added to sase-core's `check` tool);
- otherwise runs `sase tool run check` itself, and sends a failure to repair instead of landing it red.

That addresses about 47% of red time and costs roughly 15 minutes of host time a day. Then:
1. Add the macOS cross-target check to `just check`.
2. Fix the top flake, and run CI tests with one retry and `--no-fail-fast`.
3. Pin the exact Rust version, and alert someone or launch a repair agent when master goes red.
4. Only if that isn't enough, require CI to pass before landing (protected master with PRs or a merge queue).

**Limitations:**
- The check records are per machine, so the 59 commits from agents on apollo couldn't be traced.
- The gate design is a sketch. Three things need confirming when it's built: that files reformatted by the hook get re-staged, that checks run by sase-rooted agents resolve to the sase-core project, and that the commit step's time budget fits an 11-minute `check`.

I didn't file any beads, to avoid five researchers filing duplicates. The report ends with a list of proposed follow-ups for the lead to file.
