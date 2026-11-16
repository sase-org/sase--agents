# Chat History - ace-run (research.62.cld)

- **TIMESTAMP:** 2026-11-16 06:34:32 EST
- **MODEL:** claude/opus
- **AGENT:** research.62.cld
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261116_061336.md`

## Prompt

%id(cld, clan=research.62)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.62.cdx`, `research.62.grk`, `research.62.mus`, `research.62.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The TUI has slowed down quite a bit lately (including startup). I would like to dig into
this and speed up sase's TUI significantly.

Can you do some research with the goal of helping me decide the best/safest way to
optimize sase's TUI? Feel free to recommend extra instrumentation but only if truly
necessary to diagnose the TUI's performance. End your analysis with a recommended
solution. 
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

Reading startup telemetry: process start → on_mount has gone from ~0.6s in August to ~6.5s now, and `app_construct_seconds` alone is ~5.5s. Next I'm charting the trend by date and source revision.

Found a step regression: app construction jumped from ~1.0s to ~5.5s on Nov 12, coinciding with the local-command trust enforcement commits. Now profiling app construction to confirm the cause.

Building a cProfile harness that constructs `AceApp()` without running it (side-effectful session registration stubbed out) so I can see exactly where the ~5s goes.

Aggregating the stall-watchdog log (hitches, GC pauses) by culprit frame to see what's blocking the UI at runtime.

The live TUI (pid 2180945) is at **23 GB RSS + 24 GB swap only 17 minutes after start**, with 50 s GC pauses. That's the dominant runtime problem right now. Next I'm checking what is ballooning.

Cross-referencing UI hitches against GC pauses: the recovery records carry a `gc_overlap_s` field, which shows how much of each freeze was garbage collection.

Checking why the incremental "prep" stage costs ~2.5 s even when only 2 agents changed (looks like a fixed O(roster) cost).

I have the full picture. Before writing, confirming the research sidecar path through `sase repo`, as project rules require.

Writing the report now.

Report written. Registering it as an artifact.

Artifact registered. Finishing the turn through `/sase_final`.

I wrote the report and registered it as an artifact (`file:explicit:6f1daa1c597371e6bacf245f`). The host will commit it to the research repo when this turn ends.

**Report:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_26/sase/repos/research/202611/tui_performance_regressions_root_causes__cld.md`

**Urgent:** your running TUI (pid 2180945) was using 23 GB of RAM plus 24 GB of swap only 17 minutes after it started. It is pushing the whole host into swap. Restarting it won't help, because any TUI on a build at or after `d26b581253` (today's hijack commit) does the same thing. Until a fix lands, either quit it when you're not using it, or temporarily pin the installed checkout back to `082f2bc705`.

The slowdown has three separate causes, each measured:

1. **Runaway hijack checks (since this morning, `d26b581253`).**
   - **What happens:** every time the Agents footer refreshes, the TUI starts a background check of whether the selected agent can be hijacked.
   - **Why it's expensive:** each check scans every agent artifact and then reads 65,875 dismissed-agent files (591 MB). One check costs 32–38 s and about 2.2 GB of memory.
   - **Why they pile up:** the cached answer is thrown away on every roster refresh, so checks never get reused. They also run on the shared background thread pool. I found 31 of its 32 slots stuck on these checks, so ordinary agent loads queue behind them.
   - **Effect:** the UI was frozen about 26% of the time, with garbage-collection pauses up to 50 s.

2. **Slower startup (since Nov 12, `021cd73021`).**
   - **What happens:** building the TUI app now takes 5–6 s instead of about 1 s.
   - **Why:** the new local-command trust check works out a project's root as `<repo>/sase` instead of `<repo>` for configs at `sase/sase.yml`. That forces a fallback that re-merges every project's config, about 121 merges and 100 `git remote` calls.
   - **Fix tested:** correcting the root in-process cut app construction from 6.9 s to 1.9 s.
   - **Side issue for the trust owners:** with the wrong root, the identity the trust check uses doesn't match the one `sase config trust allow` records when run with no path argument. That is likely why the "skipped (no-acknowledgment)" warning appears on every command.

3. **Chronic costs that predate both.**
   - **GC pauses:** before today, 95% of UI freezes overlapped a full garbage collection, each about 3 s because the TUI holds a very large heap.
   - **Uncached lookup:** loading the agent list repeats the same project-alias lookup 303 times per load. That one lookup is 44% of the decode step.

**Recommended order:**
1. **Hotfix the hijack checks now.** Skip rows that obviously can't be hijacked and allow only one check per agent at a time. Cache on that agent's own status instead of a counter that changes every refresh. Give the checks a single worker of their own. Have the TUI use the agent row it already has instead of the full archive scan.
2. **Remove the extra startup work without changing trust identities.** Cache the per-project result instead of moving the root yet, because correcting the root changes the keys existing trust approvals are stored under. The root fix itself should go to the trust owners with a compatibility lookup for old keys.
3. **Cache the project-alias lookup** in the agent loader.
4. **Shrink the heap,** using the existing GC census tool, as part of the in-progress `sase-1sl.4` phase.

Steps 1–3 should bring time to a usable Agents list from about 14 s back to roughly 6–7 s, and remove today's memory blowup.

The existing telemetry was enough to find all of this. The only new instrumentation I'd add is a gauge for how busy the shared thread pool is, logged in the existing memory heartbeat; it would have flagged cause 1 within minutes.

I didn't file task beads so the five researchers don't create duplicates; the synthesis can file them once.
