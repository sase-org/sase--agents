# Chat History - ace-run (research.54.gem)

- **TIMESTAMP:** 2026-11-17 10:16:47 EST
- **MODEL:** agy/gemini-4-hydrogen-xhigh
- **AGENT:** research.54.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261117_095645.md`

## Prompt

%id(gem, clan=research.54)
%m:agy/gemini-4-hydrogen-xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.54.cdx`, `research.54.cld`, `research.54.grk`, `research.54.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The way that we support viewing video artifacts in a separate tmux pane (when selecting
a video file after using the `a` keymap on the "Agents" tab, for example) is incredibly
slow. I would like to make this much faster somehow.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

I have completed the independent research and registered the report as a durable artifact snapshot.

- **Report file:** [tmux_video_artifact_viewer_perf__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202611/tmux_video_artifact_viewer_perf__gem.md)
- **Artifact ID / Ref:** `explicit:a991e7522d2a1bdef066fce5` (`file:explicit:a991e7522d2a1bdef066fce5`)
- **Stored Snapshot:** [tmux_video_artifact_viewer_perf__gem-b3057d2e6c23.md](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261117095650/tmux_video_artifact_viewer_perf__gem-b3057d2e6c23.md)

### Key Findings

1. **Why video viewing in a tmux pane is slow:**
   - **Launch tax (~1.2 s before playback starts):** [decorate_artifact_file_tmux_panes](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/graphics/_viewer_tmux_decoration.py#L86) and [_sync_artifact_file_viewer_layout](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/actions/agents/_panel_artifact_pane.py#L158) run ~13 synchronous `tmux` subprocesses on the UI thread (~`89.1 ms` measured), [viewer.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/graphics/viewer.py#L13) eagerly imports `sase.attachments.markdown_pdf` (`273.7 ms`), and [`load_artifact_video_playback_config`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/graphics/_viewer_loop_media.py#L73-L100) re-runs `load_merged_config()` (`824.5–895.7 ms`) inside the child pane.
   - **`mpv --vo=kitty` pixel/transport explosion:** As verified in upstream [vo_kitty.c](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/external/gh/mpv-player/mpv/video/out/vo_kitty.c#L44-L55), `vo_kitty` emits **uncompressed raw RGB24 (`f=24`, zero `o=z` compression)** across the full pane pixel canvas (because [`artifact_video_player_command`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/graphics/_viewer_loop_media.py#L37-L70) omits `--vo-kitty-width`/`height` and `vo_kitty.c` omits `c=/r=` GPU upscaling), omits `--profile=sw-fast`, `--vo-kitty-use-shm=yes` (local only; impossible over SSH), and `--vo-kitty-auto-multiplexer-passthrough=yes`, and wraps thousands of 4096-byte chunks per frame in `\ePtmux;...\e\\` passthrough sequences. On real `2560x1548` screencasts, `1280x774 @ 30fps` raw RGB24 base64 is **`118.89 MB/s`** (`891.65 MB` for a 7.5 s, `644 KB` `.mp4` — **1,384×** larger than the source H.264 stream).

2. **Plan Critique & Adjusted Requirements:**
   - Streaming full-motion 30 fps pixels through a tmux pane over SSH fights terminal, multiplexer, and codec physics; downscaled frames blur `2560x1548` UI text, and linear playback without a visual scrubber is cumbersome for quick inspection.
   - **Recommended adjustments:** (a) separate quick in-pane inspection from native full-motion playback; (b) drop `mpv` as the mandatory remote backend (use `ffmpeg` + `kitten`, keeping `mpv` for local `--vo-kitty-use-shm=yes` or native GUI open); (c) distinguish local vs. remote SSH attached `tmux` clients dynamically; (d) pass resolved config from the TUI parent to eliminate the ~1.2 s launch overhead.

3. **Recommended Solution:**
   - **Phase 1 (Immediate):** Remove the ~1.2 s launch tax (pass config from TUI, lazy-import `markdown_pdf`, drop `clear` subprocess, move tmux decoration off the UI thread) and enable `--profile=sw-fast` + `--vo-kitty-use-shm=yes` for local same-host `mpv`.
   - **Phase 2 (Three-Tier Hybrid):**
     1. **Default in-pane landing (`<0.5 s`):** Frame 0 + cached `5x2` timestamped keyframe contact sheet (`~86–90 KB` via `kitten icat`) with interactive frame/decile scrubbing (`h/l`, `0-9`, `z` zoom for native `2560x1548` clarity).
     2. **On-demand in-pane playback (`space` / `p`):** `ffmpeg` -> capped scale/FPS + dirty-rect diff + `zlib` (`o=z`) + single reused Kitty image ID with `c=/r=` upscaling (measured at **`0.73–1.88 MB/s`** vs. `118.9 MB/s` — **63–162× reduction**), or local SHM `mpv` when same-host.
     3. **One-key native Retina playback (`o`):** Open the compressed `.mp4` (`0.09–0.20 MB/s`) directly on the display host (local `open`/`xdg-open`/`mpv`, or Tailscale/SSH handoff reusing client `~/tmp/screencasts/` copies when present).
