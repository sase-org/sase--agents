# Chat History - ace-run (research.54.cld)

- **TIMESTAMP:** 2026-11-17 10:27:54 EST
- **MODEL:** claude/opus
- **AGENT:** research.54.cld
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261117_095645.md`

## Prompt

%id(cld, clan=research.54)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.54.cdx`, `research.54.grk`, `research.54.mus`, `research.54.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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

I'm reading the code for the tmux artifact viewer: videos play through `mpv --vo=kitty` in a split pane. Next I'll check the local tools and time each startup stage.

I'm checking the user's setup next: which machine runs the TUI, which terminal they use, and the tmux passthrough config, since these decide where the slowdown comes from.

I'm timing how long the viewer's Python process takes to start, and looking for sample video artifacts to use in tests.

I'm opening the mpv source to see exactly what its kitty video output sends for each frame.

Athena runs mpv 0.40.0, whose kitty output has no tmux passthrough wrapping. I'm checking the tmux source to see what tmux does with those raw frame sequences.

The source reading shows tmux 3.5a turns un-wrapped kitty APC sequences into pane-title updates. Next I'll search beads and earlier chats for reports about this slowness.

mpv on its own pushes about 5.2 MB per frame (roughly 130 MB per second of video) at a realistic Retina pane size. Next I'm running the same command against a throttled reader to mimic an SSH link.

I have all the measurements. One last detail: whether tmux's `allow-set-title` can be set per pane, which would be a defensive hotfix.

In tmux 3.5a the APC title path ignores `allow-set-title`, so tmux settings can't defend against it. The only fix is to stop emitting raw kitty APC inside tmux. I'm writing the report now.

The report is written. Next I'm registering it as a durable artifact snapshot.

The video pane isn't just slow inside tmux: it never shows any video. Speeding up mpv can't fix it, because it sends every frame uncompressed; I recommend replacing the default player with one built on kitty's own animation support. The report is written and registered as an artifact, and the research repo commit has been declared.

**Why it's broken (reproduced in an isolated tmux on athena):**
- Athena has mpv 0.40.0. Its kitty output doesn't wrap frames for tmux; that option only arrived in mpv 0.41 and is off by default.
- tmux 3.5a treats each unwrapped 4 KB chunk of video as a new pane title. SASE's artifact pane shows the pane title in its border, so tmux also redraws the border for every chunk.
- Result: a 6-second clip took 47 s, no image data reached the terminal, and the pane border filled with base64 junk.

**Why tuning mpv won't help:**
- mpv sends every frame as uncompressed RGB: about 5.2 MB per frame in a half-screen Retina pane, or roughly 130 MB/s at 25 fps.
- Even with wrapping fixed, tmux could pass only about 50 MB/s on localhost (about 9.6 fps). Over a 100 Mbps link I measured 2.4 fps; over 25 Mbps, 0.6 fps.
- mpv also positions frames relative to the whole kitty window, not the pane, so the picture would land over the wrong pane.

**Recommendation:**
1. **Hotfix now (1–2 hours).** Inside tmux, stop launching mpv. Show a poster frame and basic metadata through the existing image path (about 0.5 s). Add an automated tmux test that would have caught this.
2. **Build a SASE-owned streaming player.**
   - ffmpeg decodes at about 10 fps, and only the changed part of each frame is compressed and sent.
   - kitty plays the frames itself, starting before the upload finishes, and loops afterwards with no further traffic.
   - SASE handles pause, seek, frame-step and replay.
   - In my prototype through tmux, the first frame went out in about 0.3 s. A whole 22-second 1080p demo took 12–21 MB, versus about 2.8 GB with mpv.
3. **Keep mpv as an opt-in setting** for local, non-tmux viewing, where it works well and has audio.

**Requirement changes I'm proposing (they're marked as changes in the report):**
- Treat this as a silent, legible preview at 8–12 fps rather than full video playback.
- Set targets: first frame under 1 s over SSH, and real-time playback of a typical demo on a 10 Mbps link.
- Require that it never slows the rest of the tmux session.
- The mute key goes away in the default player.
- Only kitty gets the animated preview; other terminals get the poster frame.
- Make the player choice a normal config setting, not a feature flag.

**Caveats:**
- I measured bytes and timings but couldn't watch the result on a real screen, so do a short check in kitty 0.47 on the Mac before building on this.
- kitty versions before 0.49 have a bug with how frames are split into pieces; my prototype hits it, but copying `kitten icat`'s format avoids it. The report lists this and the other protocol pitfalls.

My test runs used an isolated tmux server on athena and temp files on athena and apollo; all of it has been removed.

Files:
- `sase/repos/research/202611/video_artifact_tmux_pane_speed__cld.md` (artifact ref `file:explicit:e2ad574ad0b60353dc120f5f`, label `research:202611/video_artifact_tmux_pane_speed__cld.md`)
