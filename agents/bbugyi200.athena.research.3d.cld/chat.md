# Chat History - ace-run (research.3d.cld)

- **TIMESTAMP:** 2026-10-02 13:26:07 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3d.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124445.md`

## Prompt

%id(cld, clan=research.3d)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3d.cdx`, `research.3d.grk`, `research.3d.mus`, `research.3d.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Traversing through
the "current project" stack using the `<ctrl+n/p>` keymaps can be painfully slow in the
prompt input widget. Also, activating the prompt input widget using the `<space>` keymap
can be pretty slow sometimes too. It is very important that both of these operations are
very fast.

Can you do some research with the goal of helping me decide the best way to make these
keymaps work much faster? End your analysis with a recommended solution. 
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

I'm locating the prompt input widget's `Ctrl+N`/`Ctrl+P` handler and the `<space>` activation path.

Early finding: the first `Ctrl+N`/`Ctrl+P` MRU load took **9.9 s cold** and about 20 ms warm. I'm profiling where that time goes.

I'm building a headless harness that times `<space>` and `Ctrl+N`/`Ctrl+P` in the real app against a copy of your `~/.sase` data, so the run doesn't touch the real state.

Still building the sandbox. I'm checking which large state files (prompt history and similar) the prompt bar reads, so the copy includes them.

I'm reading the prompt bar's text-changed handler to see what each `Ctrl+N`/`Ctrl+P` edit triggers after the MRU load.

The host is under load (load average 35 on 64 cores), which is close to your normal conditions. I'm creating the sandboxed `SASE_HOME` copy now.

The profile script hit a profiler-already-running bug in my harness. I'm fixing it and re-running.

I can't see from reading what schedules the detail refresh during prompt typing. I'm instrumenting the debouncer to record the caller stack instead.

I have everything I need for the report, so I'm writing it now.

Report written and registered. I'm removing the 540 MB sandbox copy of your state that I created for the measurements.

I measured both keys in the real TUI and found a few specific bugs behind the slowness. Each can be fixed on its own, and fixing them makes both keys roughly instant. The report is written and registered as `research:202610/prompt_bar_space_and_project_cycle_latency__cld.md`.

I ran the real TUI headless against a temporary copy of your `~/.sase` data (deleted afterwards), on a busy host (load average about 35). These numbers are a best case: the run had no auto-refresh and no live agent activity.

| Key | Typical time to screen | First press / bad cases |
| --- | --- | --- |
| `<space>` | ~142–154 ms | 0.36–0.75 s on first press; +0.45–0.6 s when Python's garbage collector runs |
| `Ctrl+N`/`Ctrl+P` | ~42–44 ms | 0.31–0.47 s the first time you land on each project; fast repeated presses lag up to 1.3 s |

**Root causes:**
1. **Every keypress re-checks your recent-projects list from disk.** `load_launchable_vcs_xprompt_mru_pairs` runs on every `<space>` and every `Ctrl+N`/`Ctrl+P`. It starts six `git config` processes and re-reads project data each time: 20–75 ms normally, 1.2–2.1 s the first time.
2. **A file watcher restarts on the keypress the first time a prompt names a new project.** Stopping it waits on a thread for up to 0.5 s (`ArtifactWatcher.stop()`). The watcher already has a non-blocking way to add folders (`ensure_watches()`), but this path doesn't use it.
3. **`<space>` builds the whole prompt bar from scratch every time.** On top of that, a setup-handler bug runs 146 `on_mount` calls instead of 17. Each mixin calls the next one up, and Textual also calls every one of them itself.
4. **Background warm-ups that finish after the bar opens redraw the Agents detail panel**: 60–100 ms normally, 371 ms the first time. This lands just as you start typing or cycling.
5. **Garbage-collection pauses of 445–600 ms**, because the TUI holds about 960k tracked objects. One `gc.freeze()` after startup cut them to about 56 ms.

**Recommendation:**
- **Phase 1 (small, independent fixes that remove the spikes):**
  - keep the recent-projects list in memory, refreshed in the background, and have both keys read it;
  - add folders to the watcher instead of restarting it;
  - make each `on_mount` handler run once;
  - stop prompt warm-ups from redrawing the Agents panel while the prompt is open;
  - call `gc.freeze()` after startup.

  A quick prototype of three of these measured `Ctrl+N/P` at 24 ms and `<space>` at 109 ms.
- **Phase 2 (the structural fix for `<space>`):** build the next prompt bar ahead of time while the TUI is idle. Then `<space>` only fills in the text, shows it, and focuses it. Also rebuild text highlighting once per edit instead of 2–3 times. Expected: `<space>` around 50–60 ms and `Ctrl+N/P` at or under 16 ms (one frame).

I'd also add a benchmark and tests to keep these paths free of subprocesses and blocking calls, and extend the `SASE_TUI_PERF` timing log to these keys so you can confirm the gains in your live TUI.

One limit: your stall log shows 3.2–4.7 s freezes today from unrelated Agents-tab work. A keypress that arrives during one of those still waits, and those need separate fixes.
