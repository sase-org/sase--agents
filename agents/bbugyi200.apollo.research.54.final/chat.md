# Chat History - ace-run (research.54.final)

- **TIMESTAMP:** 2026-11-17 10:37:49 EST
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.54.final
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261117_095645.md`

## Prompt

%clan(research.54, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The way that we support viewing video artifacts in a separate tmux pane (when selecting
a video file after using the `a` keymap on the "Agents" tab, for example) is incredibly
slow. I would like to make this much faster somehow.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.54.final %m:claude-fable-5
%wait:research.54.cdx %wait:research.54.cld %wait:research.54.grk %wait:research.54.mus %wait:research.54.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The way that we support viewing video artifacts in a separate tmux pane (when selecting
a video file after using the `a` keymap on the "Agents" tab, for example) is incredibly
slow. I would like to make this much faster somehow.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

When you author or carry over Mermaid diagrams, load `/mermaid_diagrams` before
drafting, even when no image or diagrams companion runs. The skill has the shared
figure-selection, styling, and PDF-render review rules. If the provider skill is not
deployed, verify the edited plugin's guide with `sase macro show skill/mermaid_diagrams --format raw` (or
`sase macro show /mermaid_diagrams --format raw`) and use the form this host supports.
This guidance does not enable a companion diagrams agent.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.54.cdx`, `research.54.cld`, `research.54.grk`, `research.54.mus`, `research.54.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.54.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.54.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

I'll start by opening the research repo and reading the five researcher reports, then do my own investigation of the video-artifact tmux pane flow.

All five reports are present in my checkout. Now I'll read each through its canonical research reference.

Two reports read. The cld report found the current path is functionally broken under tmux (APC becomes pane titles). Now reading the remaining three.

grk has companion Mermaid sources and rendered figures. I'll move those along with the report, keeping their filenames so the relative image links keep resolving.

All files are in place under the `fast_video_artifact_pane` stem. Now writing the consolidated report.

Now registering the consolidated report as a durable artifact for the linker agent.

Registration succeeded (`file:explicit:cd354dab8cb138e3e976d660`). Quick final layout check, then the final declaration.

All steps complete. Now submitting the final declaration.

Done. All five reports are consolidated under `202611/fast_video_artifact_pane/` in the research repo, the final report is written and registered (`file:explicit:cd354dab8cb138e3e976d660`, label `research:202611/fast_video_artifact_pane/fast_video_artifact_pane__final.md`), and the final declaration is accepted — the host will commit the research repo after this turn.

**The headline finding, confirmed twice:** the video pane isn't slow — it's broken. mpv 0.40 emits raw kitty graphics escapes with no tmux passthrough wrapping, and tmux consumes every one of those APC strings as a *pane-title change*, so zero video pixels ever reach your terminal. Worse, SASE's pane border renders `#{pane_title}`, so every 4 KB chunk of invisible video forces a border redraw over SSH — cld measured a 6 s clip taking 47 s to "play" on athena with nothing displayed. I reproduced the APC→title mechanism independently on apollo's tmux 3.4. On apollo the path fails differently: mpv isn't installed at all, so you get a hard `missing_mpv` error. On top of that sits a ~1–1.2 s fixed launch tax (fresh-process merged-config reload, eager `markdown_pdf` import, ~13 synchronous tmux calls on the UI thread).

**Why tuning mpv can't fix it:** `vo_kitty` sends every frame as uncompressed base64 RGB — ~5 MB/frame at a half-screen Retina pane, a ~1,400× inflation over the source H.264, far beyond what tmux (+SSH) can carry. And in mpv ≥ 0.41's passthrough mode, frames are positioned in *window* coordinates, so in a split pane the video would draw over the wrong pane. Two researchers proposed an mpv "flag pack"; the consolidated report rejects that for tmux and keeps mpv only as a local/non-tmux backend.

**Consolidated recommendation (phased):**
- **Phase 0 (hotfix):** under tmux, never launch mpv — show a poster frame + metadata through the already-working `kitten icat` path (~0.5 s), and add a pty+tmux regression probe (the original design tale's step 1, which never ran, would have caught this).
- **Phase 1:** kill the launch tax — pass resolved config from the TUI parent, lazy imports, off-thread pane decoration. Benefits every artifact kind.
- **Phase 2 (the product):** make the pane inspect-first — frame 0 + keyframe storyboard, frame scrubbing (`h`/`l`, `0–9`), `z` zoom at native sharpness, `o` native-open escape hatch, motion on demand. Your artifacts are screencasts/TUI demos; this answers "what happened at 0:22" faster than playback ever could.
- **Phase 3 (gated):** a SASE-owned streaming kitty-animation player for real in-pane motion over SSH. Two researchers independently prototyped it at ~100–230× fewer bytes than mpv (12–21 MB vs ~2.8 GB for a 22 s demo, first frame ~0.3 s). Build it only after a one-hour rendering spike on your Mac's kitty 0.47 passes and the scrubber proves insufficient — it's the one piece with real maintenance weight (including a kitty <0.49 chunking gotcha that both prototypes currently trip over).

The report also calls out eleven explicit requirement adjustments (inspect-first reframing, testable SLOs, a "no collateral damage to the tmux session" rule, mpv demoted to optional, backend as a config field rather than a feature flag, and keeping everything in the Python TUI per the rust-core boundary), plus a section documenting exactly where the five researchers disagreed and how each conflict resolved.
