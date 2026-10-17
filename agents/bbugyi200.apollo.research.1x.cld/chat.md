# Chat History - ace-run (research.1x.cld)

- **TIMESTAMP:** 2026-10-17 00:31:42 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1x.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215631.md`

## Prompt

%id(cld, clan=research.1x)
%m:claude/opus@xhigh %wait:research.1w.linker %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.1x.cdx`, `research.1x.grk`, `research.1x.mus`, `research.1x.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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

Opened the research sidecar and found the prior Gas City and Gas Town reports. Next I'll read them, then study the gascity source and sase itself.

Now reading Gas City's own docs (AGENTS.md, how it works, formulas, packs) at `45c804d59e`, then I'll compare against SASE's current source.

Gas City docs and code are verified (two subagent sweeps found several features its docs advertise that are unwired). Now checking SASE's current state since the Oct 16 Gas Town report.

Key data point found: Gas City's `main` CI was green on 99 of its last 100 runs, against SASE's Master Gate at 8 of 60. Checking commit cadence on both repos for a fair comparison.

Verified SASE's side too (workflow preview and tag-overridable epic role macros exist, so those aren't gaps). One last look at Gas City's examples, then I'll write the report.

Evidence gathering is done. Writing the report now.

Now registering the report as a durable artifact.

Report written and registered. Now submitting the final declaration.

I've written the report and registered it as an artifact (`research:202610/sase_vs_gascity_where_gascity_leads__cld.md`). It compares Gas City at commit `45c804d59e` with SASE at `5ea5fa5452`.

**Biggest finding:** the Gas City project (how its repo is run, not the `gc` product) keeps `main` green, and SASE doesn't.
- **Gas City:** 99 of the last 100 CI runs on `main` passed. GitHub enforces this: changes land only through PRs, `bazel test` and CodeQL checks must pass, and a merge queue tests up to 5 changes at a time. Tests are cached, so a run takes about 5 minutes. It lands 20–114 commits a day, many from bots.
- **SASE:** only 8 of the last 60 Master Gate runs passed. `master` has no branch rules, and changes are pushed before they are tested.
- **Why it matters:** SASE's CI decision record rejected a merge queue as too costly. Gas City runs one at about SASE's commit rate, though it pays for faster runners and caching to do it.

**Ways Gas City is superior** (the report ranks 13):
- **Workflows survive crashes.** Each step is stored as a durable work record, so a crashed run picks up where it stopped. SASE workflows restart from step 0, and a failed epic phase waits for a human.
- **The host decides when work is done.** A script run by the orchestrator, not the agent, checks each step. It can re-run a whole review→fix loop a set number of times, and a failing optional step can be marked as non-blocking.
- **Automation reacts to events.** Jobs fire on cron, on events or on webhooks, and can launch whole workflows. Supervision rules ship as editable config, for example handing work held by a dead agent back to the queue.
- **Wider integration surface:**
  - a typed, numbered, followable event log;
  - a generated HTTP API with a web dashboard;
  - shareable bundles of agents and workflows with version pins, a lockfile and a registry;
  - 18 agent CLIs supported versus SASE's 7.

**Treat Gas City's docs with caution.** Checking the code turned up about 12 advertised features that are removed, never called, or only partly working. For example, its voting step was removed but is still recommended in the docs, and its crash-loop protection never triggers. SASE stays ahead on verified completion, admission control, human gates, memory and docs that match the code.

**Ranked recommendations** (13 in total):
1. Test before landing: add `master` branch rules now, then trial Gas City's merge-queue setup with Master Gate as the required check. This needs a new decision record.
2. Make workflow and epic runs durable and resumable, in the Rust core.
3. Have the host run acceptance checks, with bounded loops over several steps and typed failure handling.
4. Add a typed, durable event log with `--follow`.
5. Add cron and event triggers that can launch workflows.
6. Let each epic phase be a full workflow, and add real parallel fan-out inside workflows.
7. Ship a review macro with reviewers on different models and a synthesizer.
8. Add shareable bundles of macros and workflows with version pins.
9. Let projects contribute their own `sase doctor` checks and fixes.
10. Route ready beads to roles automatically, within a launch budget.
11. Add one generic adapter for agents that speak the Agent Client Protocol (ACP).
12. Add dollar cost estimates.
13. Small process borrowings, such as running the quick-start docs as tests.

The host will commit the new file in the research repo after this turn ends. I didn't install or run Gas City, so its throughput figures are its maintainers' own.
