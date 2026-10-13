# Chat History - ace-run (research.4c.cld)

- **TIMESTAMP:** 2026-10-13 10:01:45 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4c.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_090356.md`

## Prompt

%id(cld, clan=research.4c)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4c.cdx`, `research.4c.grk`, `research.4c.mus`, `research.4c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It
is taking a very long time to startup sase's TUI on my apollo machine. Can you do help
me profile that machine and sase's startup? End your analysis with a ranked list of
changes you think I should consider making in order to improve the TUI's startup on that
machine (or in general). 
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

I'm reading the perf runbook's startup sections and have confirmed SSH access to apollo, which is sitting at load average ~16 on 16 cores. Next I'll pull apollo's startup telemetry.

Telemetry is copied and the hosts compared. Now I'm checking the TUI's CLI flags so I can run a profiled, traced startup on apollo.

Two `sase tool` processes (`_join` and probably `wait`) are each writing about 2.2 MB/s and burning about 50% CPU, which looks like a hot poll loop. Checking them now.

I'm looking at the `sase tool wait` poll loop, which runs a ledger reconcile on every poll. After that I'll launch a traced, py-spy-profiled TUI startup on apollo.

Next I'll launch a traced, py-spy-sampled TUI startup on apollo inside a separate detached tmux session, so your session isn't touched.

I reproduced it: the profiled startup took **63 s** for `agents_ready` (Services/axe ready took 15 s). I got a 100 Hz py-spy capture plus the TUI trace spans. Pulling them back to analyze.

The DDL has an index on the summaries side but probably none on `archive_visibility_projection` for the 3-column join. Next I'll time the query read-only on apollo's real index.

Next I'm breaking down the agent-decode path and then the competing CPU-bound threads.

Now the driver for the A/B runs, with no py-spy so overhead doesn't distort the timings:

Round 1 came in at 20–25 s for every variant, with no clear winner from one run each. I'm comparing the per-span traces to see where the time went in each.

Even in a "fast" 20 s run, the provider stage runs about 8 s past the end of decode. Next I'm checking what the provider span covers.

In this run the loader thread spends **5.9 s in `os.path.realpath`** (`_joinrealpath`) and 2.3 s in `stat`. Next I'm finding who calls `realpath` so heavily.

No stray processes are left; only my own `pgrep` matched itself. Before writing the report I'll verify the exact file:line references I plan to cite.

All references check out. Next I'll confirm the report directory exists and that my chosen filename is free.

The filename is free. Before writing, I'll gather the app-instance IDs of my 18 profiling startups, so the report can tell you which records in apollo's `tui_startup.jsonl` to filter out.

I have everything I need. Writing the report now.

I'm double-checking two claims in the report before registering it: the Tier-2 statement, and the late-September comparison.

The report is written. Next I'll register it as a durable artifact snapshot.

Registered as `explicit:1fc38fa36f08fac215a82f22`. Submitting the final declaration.

I profiled apollo and its TUI startup, wrote the report, and registered it as artifact `explicit:1fc38fa36f08fac215a82f22`. Your last startup (13:02) took about 85 s wall-clock before the Agents rows appeared. The slow startups have three causes that stack.

1. **Apollo is a slow, overloaded host.**
   - It's a DigitalOcean droplet: 16 vCPUs on a 2017 Xeon 8168 at 2.7 GHz.
   - While I measured, load average was 13–31. Pytest runs launched by agents alone used 8–10 of the 16 cores, and processes were regularly waiting on disk syncs.
   - With the same Python, single-threaded code runs 2.2–2.9× slower than on athena. Importing the TUI takes 5.6 s on apollo vs 1.85 s on athena.

2. **The Patches relation index rebuilds over and over during startup, even though the Artifacts tab isn't open.**
   - Any artifact file change triggers an immediate Patches reload. A code comment in `_watcher.py` says "Patch refreshes are cheap enough to keep immediate".
   - They aren't cheap here. Each reload walks all ~44,000 artifact-link rows, which takes 2.4 s on apollo with nothing cached.
   - With 10–17 agents writing files, I saw 7–11 rebuilds before the Agents tab was ready. That's about 30% of the startup's Python CPU time (GIL).
   - The first rebuild also runs directly on the UI event loop.

3. **Python's global interpreter lock (GIL) multiplies small operations on the Agents loading path.**
   - Each file check or database row step briefly releases the GIL. Getting it back waits about 5 ms whenever another thread is busy computing.
   - I reproduced this on apollo's real dismissed-agents database. The query takes 59 ms alone, 36 s with one busy thread alongside, and 72 s with three.
   - The same effect turned a one-time path-resolution step (`AgentIdentitySnapshot.current()`, 0.5 s on its own) into 7.6 s inside the TUI.

**A/B test on apollo:** 17 normal startups, alternating variants, with only the profiling runs modified.

| Variant | Agents ready (mean) | Spread |
| --- | --- | --- |
| Unmodified | 34.0 s | 19.7–65.6 s |
| Relation index disabled | 26.3 s | 25.4–27.0 s, at load ~30 |
| Relation index disabled + shorter GIL switch interval | 21.0 s | 20.5–21.7 s |

The shorter switch interval alone didn't help. The disabled-index arm only has 3 runs, but it removed both the long startups and the run-to-run variance.

**Ranked changes to consider:**
1. Don't reload Patches or rebuild the relation index while Artifacts isn't visible, rate-limit reloads, and move the startup build off the event loop.
2. Take load off apollo while you're using it: cap the agents' pytest workers (`-n`), run fewer agents at once, or `nice` them, or `%dispatch` heavy agents to athena, which sits at load 5–7 on 64 threads.
3. Cache the relation index between identical builds, and move the link-to-edge matching into sase-core as one batched call.
4. Defer startup work that isn't needed for the first Agents paint: the first auto-refresh service scan (768 file opens), the plugin/macro catalog scans, the update check, the cache warmups, and a debug-only import of 293 modules that happens on the event loop.
5. Cut the many tiny file and database operations on the Agents loading path: cache the identity snapshot, avoid reconcile-wide path resolution, fetch dismissed identities in Rust, and open the dismissed index read-only (today every read commits a write transaction).
6. Reinstall apollo's sase environment on Python 3.14 (`just install-dev --python 3.14`, which you'd run yourself). It currently uses system Python 3.12.3. Expect a modest 15–20% CPU gain; it doesn't fix the GIL problem.
7. Slow down the `sase tool wait` / `_join` polling loop. Each waiter currently costs about half a core and ~490 writes per second.
8. Consider a faster droplet type for apollo.
9. Keep trimming what the TUI imports at startup. On Python 3.12, creating about 2,000 dataclasses is roughly half the import time.
10. Add host load and the relation-index build count to the startup telemetry, so future slow starts can be explained without py-spy.
11. Longer term, run the startup Agents load somewhere the GIL can't starve it: one Rust call, a helper process, or free-threaded Python.

**Things to know:**
- My profiling runs added about 20 records to apollo's `~/.sase/logs/tui_startup.jsonl` between 13:11 and 13:55 UTC; the report lists their instance IDs so you can filter them out.
- Raw profiling captures are in `/tmp/cld_prof` on apollo (about 18 MB, safe to delete).
- I didn't change sase code, config, or apollo's installed environment.
- I didn't file task beads, so the lead can consolidate recommendations across the five reports first.
- Apollo's load moved from 13 to 31 during the hour, so absolute numbers are noisy.

Files are in `sase/repos/research/202610/`:
- apollo_tui_startup_profile__cld.md
