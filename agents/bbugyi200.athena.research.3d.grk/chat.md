# Chat History - ace-run (research.3d.grk)

- **TIMESTAMP:** 2026-10-02 13:05:21 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.3d.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124445.md`

## Prompt

%id(grk, clan=research.3d)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.3d.cdx`, `research.3d.cld`, `research.3d.mus`, `research.3d.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research the prompt-input keymap latency independently and write a `__grk.md` report. First I'll load the research/project skills and locate the keymap code.

The TUI performance notes and prompt-input keymap code look like the right place to start. I'll load those next and map how `<ctrl+n/p>` and `<space>` currently work.

TUI perf rules are loaded. Next I’ll find the prompt-input keymap handlers and any existing latency traces.

The blog post already names `Ctrl+N`/`Ctrl+P` as MRU workspace cycling. I’ll trace those handlers and the space-to-focus path next.

`ctrl+n/p` loads the VCS MRU on every keypress, and `space` is `start_agent_from_patch`. I’ll inspect those loaders and the activation path for blocking work.

The MRU loader already admits it runs on every `<ctrl+p>`. I’ll follow the space-activation action and the per-keystroke helpers next.

The per-keystroke MRU path looks like the bottleneck. I’ll inspect PromptInputBar mount work, caches, and any existing beads or benches.

Space remounts the bar and `on_mount` warms several catalogs. I’ll check whether those warmups and the cycle-key completion refresh still run on the UI thread.

I’ll time the live MRU and launchability path, and read the remaining keystroke helpers that still look synchronous.

I'll locate the real replace helper via inspect and time the live MRU/launchability path.

415ms on a 7-entry MRU load is the smoking gun. I’ll profile that path in a fresh process and walk the TextArea replace MRO.

I'll write the research report from the completed evidence, then register it as a durable snapshot. First I'll confirm the path is still free and refresh the required SASE skills.

The chosen report name is still free. I'll record skill use, open the research repo, and pull a few source citations so the write-up stays exact.

Research sidecar is open and the filename is unused. Next I’ll pull AGENTS.md and the key source paths so the report can cite them accurately.

I have the memory rules and the MRU load path. Next I’ll read the cycle handler, prompt-bar mount, and launchable-record fields so the report can pin the latency to specific calls.

I have the call graph. I'll remeasure the live MRU and mount paths so the report cites numbers from this run.

Measurements are in. I’ll write the report to the unused `__grk` path, then register it.

The report is registered. Next I’ll pull the finalizer context and submit the commit for the research sidecar.

Both keymaps are slow because every press rebuilds the launchable VCS xprompt MRU on the UI thread, and `<space>` then throws the prompt bar away and mounts a new one.

Live numbers on this host (7 MRU entries, 37 project dirs, 3 launchable):

| Path | Cold | Warm |
| --- | ---: | ---: |
| `load_launchable_vcs_xprompt_mru_pairs()` | **446 ms** | **20–26 ms** |
| JSON load of the MRU file | — | 0.05 ms |
| `list_project_records` of all 37 dirs | — | 4.4 ms |

A warm `<ctrl+n/p>` already misses the 16 ms keystroke budget on data fetch alone. cProfile of that warm path is 6 `git config --get remote.origin.url` subprocesses and 9 full `list_project_records` walks per key. Rust already stores `launchable` and `vcs_kind` on `ProjectRecordWire` without git. Completions and the current-project chip already peek mtime and resolve on a worker; these two keymaps do not.

`<space>` pays that same load, then unmounts/remounts `PromptInputBar` (markdown `PromptTextArea`, ~29 mixins) because a second `#prompt-input-bar` would hit `DuplicateIds`. That is why it feels intermittent: first press after start is the 446 ms cliff, later presses are still ~40 ms of fetch plus remount.

**Recommended fix** (full write-up in the report):

1. One in-process launchable-MRU snapshot, keyed by `(mru mtime, size, projects token)`, built from a single `list_project_records` using `record.launchable` / `record.vcs_kind`. Key handlers only peek. Prune and git detection move off the key.
2. `<ctrl+n/p>` stashes that ring on the widget and does index math plus a short tag replace. If the token moved, keep cycling the last ring and refresh one coalesced worker.
3. `<space>` reuses a keep-alive / in-place `PromptInputBar` instead of remounting.

Do not wrap the key handler in `to_thread`, call `resolve_ref`, or keep spawning git on a keystroke.

Report: `sase/repos/research/202610/prompt_input_current_project_keymap_latency__grk.md`  
Snapshot: `research:202610/prompt_input_current_project_keymap_latency__grk.md` (`file:explicit:7c05c5ed46a841b7d6c6c206`)
