# Chat History - ace-run (research.34.cld)

- **TIMESTAMP:** 2026-10-01 11:00:08 EDT
- **MODEL:** claude/opus
- **AGENT:** research.34.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_102713.md`

## Prompt

%id(cld, clan=research.34)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.34.cdx`, `research.34.grk`, `research.34.mus`, `research.34.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Why is master failing in CI for
this project? What can I do to fix this an prevent this from happening again in the
future? Can you do some research with the goal of answering these questions? Make sure
your report is excellent, concise, and beautiful. End your analysis with a recommended
solution. 
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

Status: master's "Master Gate" has failed on every push for 100+ commits. I'm now finding when it started and pulling the failure logs.

Status: latest run has 3 symvision lint errors plus ~14 failing tests spread across 7 shards. Now checking the import error, reproducing locally, and tracing why agent-side checks miss these.

Status: the import error reproduces locally, so it's a real code break and not CI-environment drift. Now running the remaining failing tests locally and finding which commit broke each one.

Status: the sampled history shows a rotating set of failures. Individual breaks get fixed, new ones land, and the count never reaches zero. Now measuring how long each break survives.

Status: I have a candidate culprit commit for each current failure. Next I'm checking each one against the diff to confirm the commit actually explains the failure.

Status: `just check` does run symvision, so I'm working out how a symvision break still reached master. My lead is that epic-symbol whitelists depend on bead state, which changes outside git.

Status: pulling stats from the local ToolRun ledger to see how often agents' own `just check` runs fail, and how those failures get triaged.

Status: a 9/28 research swarm already diagnosed this and recommended a "stop the line" plus wave repairs. I'm now checking what got adopted since then and why master is still red.

Status: the 9/29 repair cut failures from 61 to 4. It still landed red, and the count was back up to 9 within about 20 minutes. Next I'm checking which of the 9/28 prevention items actually shipped.

Status: evidence gathering is done. Pulling exact failure details for the fix table, then writing the report.

Status: analysis is complete. Writing the report now.

Status: the report is written and formatted. Proofreading it once, then registering it as an artifact.

Status: the report is final. Registering it as a durable artifact now.

I've written the report and registered it as an artifact (`file:explicit:5f996bf8c16e23a4b5e19162`). The host will commit it to the research repo after this turn.

**Report:** `sase/repos/research/202610/sase_master_ci_red_why_and_how_to_keep_green__cld.md`

**Why master is failing**

- **How long:** Master Gate hasn't passed since 2026-09-18 02:24Z, which is about 1,100 red runs in a row. Since September 1 it has passed 60 times out of 1,907 runs (3.1%).
- **What fails at HEAD:** 3 unused-symbol lint errors (symvision), 11 failing tests and 1 test-collection error. All of them come from 8 feature commits landed in the last ~40 hours. I confirmed each commit's diff explains its failure, and each fix is a few lines. Beads already exist for most of them (sase-1dh, sase-1dn, sase-1de, sase-1cm).
- **The underlying cause is how changes land, not those 8 commits:**
  - **No gate before master.** About 90 commits a day go straight to an unprotected master. Landing records `unverified` rather than refusing, and the CI verdict usually arrives after the next commit has already landed.
  - **Local checks have stopped meaning anything.** Only 26 of the last 1,000 `just check` runs passed; 20% were killed by a signal, most at a ~9-minute inline limit. The agents behind these breaks got red or killed checks and landed anyway.
  - **Test selection was not the problem.** I replayed it for six of the culprit commits, and every one escalated to the full suite, so the broken test was in scope each time.
  - **Local and CI environments differ.**
    - **Python:** agents run Python 3.14 while CI runs 3.12. One failing test passes locally for exactly that reason; I reproduced it.
    - **Rust core:** local installs build it from the linked checkout instead of CI's pinned revision.
  - **Failures hide other failures.** Lint stops at the first red check, so three later CI steps (validation, plans, package build) have been skipped on most runs. Symvision shows one error class at a time, which made one break look like it came from the commit that was fixing symvision.
  - **Repairs get overtaken.** The 09-29 repair cut failing tests from 61 to 4, but it landed already red and the count was back to 9 within 18 minutes. Four repairs since 09-23 have gone the same way.
  - **Nobody owns the backlog.** 68 open CI beads and 91 open flake beads. Agents keep `+1`ing the current ones instead of fixing them.
- **Cost:** PyPI is still on 0.17.1 from 08-29, and release PR #299 is blocked.

**Recommended solution**

1. **Today, stop the line once.**
   - Hold feature landings.
   - Have one build-cop agent, explicitly allowed to run `just check-full`, land the 8 fixes as a single commit.
   - Verify that commit on the actual Master Gate, because a local 3.14 run can't see the 3.12 failure.
   - Release the hold only when the gate is green.
2. **This week, adopt a green-or-revert landing contract:**
   - **A. Refuse unverified landings.** The commit finalizer should require a passing `check` receipt (or "no new failures"). The receipt machinery already exists; only the default needs flipping.
   - **B. Fix or revert on red.** When a commit turns master red, `ci_watch` holds landings and launches a fix agent; if master isn't green within 60 minutes, it reverts the commit.
   - **C. Make local match CI.** Run the same Python version and the pinned Rust core in both.
3. **Later:**
   - Make lint run every check and report all failures instead of stopping at the first.
   - Quarantine stale CI failures with an expiry instead of leaving master red.

A and B would change two existing decisions (host-owned completion and `ci_watch`'s notify-only role), so they need new decision records and should ship behind a feature flag.

**Less certain:** two of the 8 culprit commits were made by agents on apollo, whose check history I didn't inspect. The risk that a bead closing can turn lint red comes from reading the code; I didn't see it happen.
