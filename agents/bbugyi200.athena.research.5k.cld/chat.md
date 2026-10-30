# Chat History - ace-run (research.5k.cld)

- **TIMESTAMP:** 2026-10-30 17:13:06 EDT
- **MODEL:** claude/opus
- **AGENT:** research.5k.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261030_164448.md`

## Prompt

%id(cld, clan=research.5k)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.5k.cdx`, `research.5k.grk`, `research.5k.mus`, `research.5k.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The TUI has slowed down again lately. Can you do some research with the goal of helping
me speed things up again? Make sure you prioritize good architecture choices and
reliability (don't break anything). End your analysis with a recommended solution. 
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

Reading prior TUI GC research and live telemetry; next I'll check current stall logs and recent TUI commits.

Analyzing the live TUI's GC-pause and memory-heartbeat telemetry (current instance is 14 GB RSS+swap after ~2h).

Comparing the Oct 23 baseline (RSS 2–5 GB, 3.6% hitches) to today's 4–15 GB swings and ~15% hitches; now reading GC policy code and the commit history in between.

Sampling the live TUI with py-spy (non-blocking) to see which threads hold the GIL and what they're doing.

Found a big signal: "full" agent loads run nearly back-to-back (68 auto_refresh full loads averaging 27 s in 2.4 h). Tracing what the "disk" stage does.

The "index" sub-stage of each full agent load takes ~24 s median (3,650 s total in 2.4 h). Digging into what that call does.

Measuring next: the per-load "index" sub-stage is a Rust artifact-index query serialized behind a process-wide lock. Checking whether the time goes to lock waits or to the query itself.

Running a standalone timing probe of the artifact-index query (read-only "cached" freshness) to see whether the Rust query itself is slow or the TUI's time goes to lock waits.

Standalone, the same query takes 0.3 s for ~500 records; inside the TUI it takes ~24 s. So the time goes to contention, not data volume. Sampling worker stacks to find which kind.

Strong lead: the "stranded work" feature (landed Oct 23–24, right after the last good baseline) is sitting inside a long artifact-index query in 17 of 25 samples. Reading that code.

The stranded-work report has a 15 s TTL and re-runs one full-history index query per bead assignee. Timing that path standalone.

The loader only waits 50 ms for the index lock, then falls back to a filesystem source scan; for full-history loads that scan covers the whole archive. Measuring what one full source scan costs.

A single tier-1 "bounded" fallback scan takes **24.3 s, returns 16.6k records and peaks at 1.5 GB**. That matches the TUI's 23.8 s median "index" stage. Waiting on the full-history scan.

The machine-capacity feed (added Oct 27) re-runs a filesystem capacity scan up to every 30 s whenever the runner-slot token changes. Timing that scan.

Roughly 84% of logged slow full loads (1,978 of 2,366) have an "index" stage of 15 s or more, the signature of the source-scan fallback. Checking how often the stranded warmup is triggered.

The stranded refresh is also force-run (bypassing its TTL) on every `beads_watcher` event, and beads change constantly with ~30 agents running. Checking why the sase project has 218 candidates.

`Any` of `Equals` is supported by the current core, so a batched query works today without core changes. Prototyping it read-only to measure the gain.

Evidence is complete. Loading the diagram conventions before writing the report, since a causal-chain figure will help.

Fit is 69% (below the 75% floor) because the figure is too tall. Tightening spacing and widening wrapping once.

Figure renders at 83.6% fit and reads cleanly. Before writing, a quick check of the feature-flag conventions, since the recommendation changes a fallback path.

Writing the report now.

Fixing two over-specific claims about the host's test workers.

Report written. Registering it as a durable artifact snapshot.

The artifact is registered as `file:explicit:2ee80e4d9df172a7e689a301`. Submitting the final declaration.

The TUI is slow again because of one background feature, the "stranded work" check that landed on 23–26 October. GC tuning is not the fix. My report is at `sase/repos/research/202610/tui_slowdown_stranded_lock_scan_fallback__cld.md` and is registered as `file:explicit:2ee80e4d9df172a7e689a301`.

**How bad it is.** Your running TUI spends 13.3% of its time frozen for 1.5 s or longer. Its memory swings between 4 and 16 GB, with up to 7.9 GB swapped out. On 23 October, before the stranded-work commits landed, the same measurement was 3.6% frozen and 2–5 GB.

**Why it happens:**
1. **The stranded-work check hogs a shared lock.** For every in-progress bead it runs one separate query on the artifact index; the sase project has 218 of them. Each query takes about 0.6 s, so one pass takes about 2 minutes. It is supposed to refresh every 15 s and is also forced on every bead change, so it runs back to back. All index access in the TUI shares one lock, and this check was holding it in 51 of 59 stack samples I took from the live TUI.
2. **The Agents list then does about 70× more work.** Its index read gives up after waiting 50 ms for the lock and walks the filesystem instead. Measured on this machine:
   - the normal index read takes 0.35 s, returns 497 records and uses 140 MB;
   - the fallback walk takes 24–30 s, returns 16–22k records and uses 1.5–2.5 GB.

   About 84% of the slow Agents loads logged since 29 October show this pattern. That works out to roughly 80 of these walks an hour, often two at once.
3. **Those big temporary allocations cause the freezes.** They make garbage-collection pauses of 2–10 s, push memory into swap, and keep worker threads holding Python's global lock.

A second, smaller load landed on 27 October: the machine-capacity view repeats a 17 s filesystem walk up to every 30 s.

**Recommended fix, in steps you can revert independently:**
1. **Python-only changes, low risk:**
   - Make the stranded check one query per project instead of one per bead. I tried this against the live data without changing anything: it took 1.78 s instead of about 127 s, and 15 of 15 spot-checked beads gave identical results.
   - When the lock is busy, have the Agents list show its last good data and retry later, never fall back to a filesystem walk. It must never mark that stale data as complete history.
   - Refresh stranded status at most about once a minute instead of every 15 s, and limit forced refreshes on bead changes to about one per 30–60 s.
2. **In sase-core and the TUI:**
   - Do the stranded lookup in the database with an index, instead of filtering every row in Rust; it currently scans all 22k index rows per query.
   - Make the capacity view reuse an existing scan or rescan much less often.
   - Fix two per-second costs in the TUI's main thread: the stranded-count path and the clan runtime totals.
3. **Measure before changing anything else.** Re-measure with the existing telemetry and rerun the GC soak test before touching GC settings again. The recent soak failures are measuring this extra load, not the GC policy. Removing or splitting the shared index lock should come last, only after someone documents what it protects.

All my measurements were read-only. I changed no code, did not run the TUI benchmarks, and have no fresh j/k latency numbers because perf logging was off in the running TUI. I didn't file task beads, to avoid five duplicate filings from the swarm. The report commit is declared and lands after this turn.
