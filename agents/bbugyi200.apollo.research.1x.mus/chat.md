# Chat History - ace-run (research.1x.mus)

- **TIMESTAMP:** 2026-10-17 00:48:34 EDT
- **MODEL:** claude/sonnet
- **AGENT:** research.1x.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215631.md`

## Prompt

Your previous attempt hit a model context limit or transient provider failure. Any file edits, new tests, and other on-disk changes you made are preserved. Before making additional changes, run `git status` and `git diff` to see what is already in place, then continue implementing the plan from wherever you left off. Do not re-apply edits that are already present.

%id(mus, clan=research.1x)
%m:muse/muse-spark-1.3-contributor@xhigh %wait:research.1w.linker %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.1x.cdx`, `research.1x.cld`, `research.1x.grk`, `research.1x.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with gascity (see recent
research in the research sidecar repo related to gascity and gastown for context)? In
particular, in what ways is gascity superior to sase? End your analysis with a ranked
list of recommended improvements you think I should consider making to sase based on
your report's findings. 
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

I'll check what's already on disk from the previous attempt, starting with the research repo.

Prior gascity and gastown research exists. I'll read the consolidated reports (not the per-researcher files) for context.

Reading Gas City's source to find what it does that SASE doesn't. I'm starting with its convergence, review-quorum, resilience and usage packages.

Now the SASE side. I'll survey its docs and source to check each candidate gap.

Status: I've confirmed the workflow executor persists state but has no resume entry point. I'll grep to be sure, then check SASE's failure handling for epic phases.

Status: evidence gathered on both sides. Before writing, I'll read the SASE decision records my recommendations touch, so I can say exactly which ones they would reopen.

I have the evidence I need. I'll confirm the target path is free and then write the report without overwriting anything.

Writing the report now, as a new file under the topic subdirectory.

Before registering, I'll fact-check the nightly-run claim, which I phrased loosely.

Status: fixing a last wording issue in the report, then I'll register it.

Registration succeeded. The last step is the final declaration, as the instructions for this turn require.

I wrote the Gas City vs. SASE report and registered it as a durable snapshot. Registration returned `explicit:0d1e56bf7db2463ba6635bc8`.

- **Report:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202610/gascity_vs_sase_where_gascity_is_ahead/gascity_vs_sase_where_gascity_is_ahead__mus.md`
- **Label:** `research:202610/gascity_vs_sase_where_gascity_is_ahead/gascity_vs_sase_where_gascity_is_ahead__mus.md`

I did not install or run Gas City. The CI numbers come from short `gh run list` windows, so they show current state, not long-run rates.

## Where Gas City is ahead, in rank order

1. **It keeps `main` green at high throughput.**
   - Gas City uses a merge queue, rulesets, a fail-closed PR evidence watchdog and a hermetic Bazel gate with remote execution.
   - All 300 of its last 300 push-to-`main` Bazel runs were green (Oct 11–17), with a median wall time of 288 s.
   - SASE's Master Gate was green on 49 of 300 pushes, with a median of 747 s.
   - A queue makes green push runs close to guaranteed. The informative figures are the queue's one rejection in 24 and 49 of 54 PR runs green the first time.
2. **It runs verification and retry as data, not prose.** A deterministic dispatcher runs `check`, `retry`, `drain`, scope and finalize steps, with typed failure classes. An exit code of 75 means "I couldn't reach what I verify", so it does not use up an attempt. SASE parks a failed phase for a human instead. In SASE's 2026-10-01 `just check` sample, 211 of 1,000 runs were killed or lost, which are exactly the "no verdict" cases that exit 75 protects.
3. **A controller with no LLM owns convergence.** SASE's scheduler already emits launch proposals with dedupe, so most of this is new detection logic, not new machinery.
4. **Smaller advantages.**
   - An endpoint ("upstream") axis for the model provider, plus container and Kubernetes runtimes.
   - Event-triggered automation.
   - Usage facts and a price table.
   - Reason-coded decision tracing.
   - Declarative packs with a registry.
   - Docs conventions such as an "Accepted But Inert" section.

The report also covers where Gas City is not ahead, and cautions about its maturity (1,561 open issues, reconciler v2 still opt-in, and a nightly acceptance run that failed 52 of its last 60 times).

## Recommended improvements, ranked

1. Set an SLO for the pre-land gate, measure critical path against elapsed time, add rulesets and a fail-closed "no CI evidence" check, and reopen the merge-queue rejection once the gate's p50 fits the commit cadence.
2. Add verification-aware attempts to bead phases and workflows, with a third "no verdict" outcome that does not use up the retry budget, plus workflow resume.
3. Add a deterministic epic-convergence job to the scheduler, depending on 2.
4. Add usage facts and a price table, to give budgets a unit.
5. Add a conformance suite for LLM provider adapters.
6. Add event-triggered scheduler jobs.
7. Add an upstream endpoint axis, then systemd sandbox properties.
8. Adopt the "last verified" and "inert" docs conventions.
9. Add decision traces.
10. Defer the declarative bundle format and registry until a second external consumer asks for it.

## Process notes

- I first read the two prior research reports with the file reader. The repo rules say sidecar reads should go through `sase artifact read`, so I re-read them that way to record the audit, and used only the audited command afterwards. The report says this too.
- The final declaration is submitted, so the host will commit the report to the research repo after this turn ends. I haven't checked that it landed.
