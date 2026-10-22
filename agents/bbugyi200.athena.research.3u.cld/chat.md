# Chat History - ace-run (research.3u.cld)

- **TIMESTAMP:** 2026-10-06 17:10:52 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3u.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_161855.md`

## Prompt

%id(cld, clan=research.3u)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3u.cdx`, `research.3u.grk`, `research.3u.mus`, `research.3u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Does the number of beads that exist for a sase project matter for bead read/write
performance? If so by how much? What are some ways that we can compress and/or archive
old beads in order to improve performance without losing any information permanently?

Can you do some research with the goal of answering all of these questions? Also,
critique this plan in general. Is this a good idea? Would you take a different approach?
Make any adjustments to the requirements that you think are justified but clearly call
these out. End your analysis with a recommended solution. 
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

I'm checking how the bead store is laid out and where the read/write code lives (sase-core plus the beads sidecar) before I take any measurements.

I've found the bead store: about 7,000 beads, 48k events, a 20 MB projection file, and a 104 MB git history. Next I'm mapping the read and write code paths and timing commands.

I'm timing the real `sase bead` read commands now. The first benchmark run ended early, so I'm rerunning it with full output to see why.

I've built 7 scaled copies of the store in /tmp, from 263 to 16,864 streams. Now I'm running the core read and write timings against each one.

Results so far scale linearly: about 0.1 s at 1k beads, 0.2 s at 1.8k, and 0.39 s at 3.6k, for reads and writes alike. Now I'm running the full sweep up to 8× (about 56k beads).

I have enough data to write the report. Next: draft it, save it under `research/202610/`, and register it as an artifact.

I'm correcting one estimate in the report: the projected `sase bead read` latency after Phases 0 and 1 was too optimistic.

Now registering the report as a durable artifact.

Now the final declaration.

Yes, the number of beads matters, and the cost grows linearly with total history (events and bytes), most of which belongs to closed beads. Archiving is the right end goal, but doing it first is the wrong order. The report is written and registered as `file:explicit:c34f0ab82f5530b5fc79767c`, with label `research:202610/bead_count_scaling_and_lossless_archival__cld.md`.

**How much it costs.** I timed copies of the live store from 1/8× to 8× its size, plus the real CLI, git, the TUI and past agent-session timings. No live bead was changed.
- **No index or cache:** every read and write re-reads and re-processes the entire event store from scratch. One pass costs about 83 µs per bead: 0.58 s at today's 7,034 beads, 1.28 s at 2×, 2.7 s at 4× and 5.7 s at 8×.
- **Writes multiply that:** a write makes 3–5 passes, then rewrites and commits the whole 20.8 MB `issues.jsonl`. The part that grows with store size is about 3–4.5 s per write today and about 16–21 s at 4×.
- **The TUI Beads pane grows quadratically:** one refresh takes 2.8 s today, 8.2 s at 2× and 48 s at 4×. It refreshes every 10 s while visible.
- **Growth is fast:** about +88 beads per day, so 2× around January 2027.

**Costs that aren't bead count.**
- **Agent reads:** about 2.9 s of the 5.7 s `sase bead read` goes to rescanning an 11,437-entry artifact-link outbox to check one ID. That cost arrived in mid-September and is why agent reads are now about 8 s at p50.
- **Git history:** 74% of the beads repo's history (96 MB, 192 GB uncompressed) is old versions of `issues.jsonl`. That file is generated from the events, so dropping it from commits loses nothing.

**Archiving vs. cheaper fixes.**
- **Archiving alone helps less than expected:** simulating archives of beads closed at least 30 or 7 days ago gave only 1.6–2.8× faster reads and writes.
- **Cheaper fixes each match or beat that, with no data moved:**
  - removing a finished migration step that still runs on every read (25% of each pass);
  - making one pass per command instead of 3–5;
  - fixing the TUI grouping loop;
  - fixing the outbox check;
  - adding a read cache keyed on file changes, estimated at 20–50 ms reads regardless of history size.
- **Compression doesn't speed anything up:** reading all 35 MB takes 25 ms, so the time is processing, not disk.
- **Archived beads must stay writable:** beads closed more than 60 days ago still got about 1,360 new events in the last 60 days.

**Adjustments to the requirements** (labelled A1–A7 in the report):
- measure hot-path latency against closed history size, not bead count;
- treat compression as a storage lever only;
- make archiving logical first;
- define lossless as "events are never edited or deleted";
- include `issues.jsonl` and the other growing logs in scope;
- benchmark on a 4×+ copy of the store.

**Recommended solution, in order:**
1. Cheap fixes: the migration step, one pass per command, the TUI loop, the outbox check, and repacking the beads clones (`sase-17r`).
2. A disposable read cache in `sase_core`. This gives the hot/cold split without moving any files; the goal store already works this way.
3. Stop committing `issues.jsonl` on every write.
4. Only if a measured threshold is hit: move closed, quiet lineages verbatim into dated "sealed" folders. A sealed bead that gets a new event gets a fresh small file instead of being moved back, and each move is checked to reproduce identical state.

A September research report already recommended steps 2 and 3. Only its git-guard fix (`sase-17q`) has landed since.

I didn't file task beads for the outbox scan or the TUI loop. Five researchers would likely file duplicates, so I left them in the report's follow-up section for the lead. Absolute timings carry about ±10–15% noise because the host was busy.
