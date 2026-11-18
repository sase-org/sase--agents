# Chat History - ace-run (1e0--plan)

- **TIMESTAMP:** 2026-11-18 11:19:25 EST
- **MODEL:** claude/opus
- **AGENT:** 1e0--plan

**Plan:** /home/bryan/.sase/plans/202611/prompt_k_video_preview.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/prompt_k_video_preview.md`

> # Prompt `K` preview: first-class support for video files
> ## Problem
> In prompt NORMAL mode, `K` previews the macro, skill, or file under the cursor. Image
> files already open an inline image reader (`ImagePreviewPanelModal`), but a video path
> such as `~/tmp/screencasts/20261118_110822.mp4` falls through to the text reader. The
> binary sniff in `_read_text_file()` then rejects it with the toast
> `Cannot preview binary file: ~/tmp/screencasts/20261118_110822.mp4`.
> The rest of sase's TUI already understands videos. `sase.media_types` defines
> `SUPPORTED_VIDEO_EXTENSIONS` (`.mp4 .m4v .mov .webm`). The terminal artifact viewer has
> a full video stack under `src/sase/ace/tui/graphics/_viewer_video_*` and

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Can you help me add good support to the `K` keymap in the prompt input widget for
video files? See the ~/tmp/screenshots/20261118_111058.png screenshot for context.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

The key layout will mirror the artifact viewer's video inspect view (digit jumps to deciles, `h`/`l` stepping). Next I'm checking the native-open command and the jump path before writing the plan.

I have what I need. I'm now writing the plan: an inline video preview modal for `K` (metadata line, cached poster frame, decile stepping, `Z` handoff to the full viewer).

The plan passes validation. Submitting it now.

I wrote and validated a plan for proper video support in the prompt `K` preview, and it's staged for your review. I haven't changed any code yet. The plan is `sase_plan_prompt_k_video_preview.md`, a single-agent plan sized medium.

**Why it fails today:** `K` sends any non-image file to the text reader. That reader sees binary bytes and shows the "Cannot preview binary file" toast from your screenshot (`_prompt_preview_target.py:405`). The rest of the TUI already handles videos: the artifact viewer can read metadata, pull single frames, show a storyboard and play the file. Only `K` doesn't use any of it.

**What the plan does:**
- **Recognise videos:** `.mp4`, `.m4v`, `.mov` and `.webm` paths get their own video preview instead of the binary-file error. Spotting them reads nothing from disk, so it stays fast.
- **New video preview window**, modelled on the existing image preview:
  - a metadata line, e.g. `4:05 · 2858×1728 · 30 fps · h264 · 12.3 MB`
  - a still frame from the video, sized to the window
  - a position line, e.g. `frame 3/10 · 00:49.0 / 04:05.0 [====>---]`
- **Keys:**
  - `h`/`l` (or the arrow keys) step back or forward by a tenth of the video.
  - `0`–`9` jump to that tenth, the same as in the full viewer.
  - `Z` opens the full viewer for sharp frames, the storyboard and playback.
  - `Y` copies the path.
  - `/`, `y` and `o` show a short warning, as they do for images.
- **Responsiveness:** reading metadata and extracting frames happens off the UI thread, and only one frame is extracted at a time. Pressing `l` repeatedly can't stack up ffmpeg processes. Frames are cached, so revisiting a frame is instant.
- **Without ffmpeg/ffprobe:** the preview still opens and shows a placeholder plus a hint to press `Z`.
- **Tests and docs:** tests don't need ffmpeg installed, and the two reference pages describing `K` and the preview window get updated.

**One decision for you, `jump_video`:** should `Ctrl+]` on a video open it straight in the artifact viewer, as it already does for images? I set the default to yes, because today it offers to open the mp4 in your editor.

**Left out on purpose:** playing video inside the preview, a storyboard grid (unreadable at the terminal's resolution), opening the viewer at the frame you're on, and support for more file types. `Z` already covers playback and the high-resolution view.
