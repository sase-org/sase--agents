# Chat History - ace-run (research.1.cld)

- **TIMESTAMP:** 2026-09-12 16:20:57 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260912_160413.md`

## Prompt

%id(cld, clan=research.1) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

The test suite for this project is incredibly slow and consumes a large number of resources. Part of this is necessary complexity just because the codebase is so large but we still need to think of a way to speed up our feedback loop without making our architecture less reliable. Can you do some research with the goal of helping me decide on the best way to solve this? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

I wrote the research report and registered it as an artifact (`file:explicit:0d4135789f6576c6f14bf606`, label `research:202609/test_feedback_loop_speed_and_reliability__b.md`). The commit declaration was accepted, so the host will commit it.

**Report:** `sase/repos/research/202609/test_feedback_loop_speed_and_reliability__b.md`

## What I found

The suite's size isn't the main problem. Three separate issues are making each other worse:

1. **`check-full` runs about 5× slower than it needs to.**
   - It uses the test-cost lane, and since 2026-08-10 that lane loads the global-state leak detector. The detector scans the globals of every loaded `sase.*` module before and after each of the 38,700 tests.
   - A single scan takes about 0.24 s once `sase` is fully imported. A 112-test file went from 7.7 s to 27.3 s with the detector on.
   - In the last full run on apollo, about 87% of worker CPU was spent outside the tests. The run took 94.5 minutes; the tests themselves account for roughly 16–17 minutes at the same 7 workers.
   - This conclusion comes from the recorded data plus small benchmarks. I haven't run a whole-suite A/B yet.
2. **CI isn't catching anything right now.**
   - Master Gate has failed 380 of its last 399 runs (last green 2026-09-08). Full CI hasn't been green since 2026-08-29.
   - The Master Gate failures are deterministic. Some SDD tests run `git commit` without a git identity, which only works on dev machines that have a global one configured.
   - Full CI's coverage-contexts job fails on a missing sase-core binding, so no coverage baseline exists at all.
3. **The fast `just check` lane is often slower than the full suite.**
   - It had no coverage baseline in all 42 runs that looked for one, and 55% of scoped runs escalated to the full suite.
   - The median scoped run takes about 20 minutes. Its "is the full suite faster?" cutoff (232 s) was measured on athena's 64-core machine, not on apollo.
   - 19 tests that should have been selected were missed.

Inside the tests, 68.5% of the time goes to starting and settling Textual apps. Each AcePage startup takes about 2.25 s, and 128 call sites use fixed-delay pauses. There's also about 7 s of fixed startup cost per pytest process. An autouse fixture imports the TUI in every process (3.3 s), and inline-snapshot's end-of-session report adds 3.4 s.

## Recommendation

Fix the safety net and the waste before buying hardware or making test selection smarter, in this order:

1. **Restore CI (days).**
   - Set git identity and config once in the root conftest so tests don't depend on the machine.
   - Get the coverage-contexts job green.
   - Stop landing work while Master Gate is red.
2. **Make `check-full` cheap (days).**
   - After an A/B run confirms the detector's cost, have `check-full` run the fast lane.
   - Move the leak detector to scheduled Full CI, which still gates releases.
   - Remove the fixed startup costs.
   - Expected on apollo: about 95 minutes down to about 20. Every check still runs, just not always in the same place.
3. **Cut Textual startup cost (2–6 weeks, can be split across agents).**
   - Move more test modules onto the existing shared-page helper (`AcePageGroup`), keeping its isolation check in CI.
   - Replace fixed pauses with the existing settle wait.
   - Tighten the existing cost budgets after each batch.
4. **Then fix the scoped lane.**
   - Base its cutoff on each host's own measured full-suite time.
   - Keep coverage data fresh on each host.
   - Don't escalate when the sase-core wheel hasn't actually changed.
   - Work the missed-test count down to zero.

I'd hold off on more hardware, Pants/Bazel, and testmon. I'd also keep the leak detector and TUI tests; they should move, not be deleted. All of this fits within the existing two-speed decisions, so none of them need reopening.

My timings came from a busy shared apollo. The report lists what to re-measure first.
