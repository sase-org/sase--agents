# Chat History - ace-run

- **TIMESTAMP:** 2026-07-08 17:22:52 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260708_171446.md`

## Prompt

%name:research.@.cld %m:@research_assist %g:research #gh:gh_sase-org__sase sase uses VHS tapes to automatically generate demos of us walking through different steps of the TUI. The biggest gap in functionality from my perspective is the inability to add custom text to the GIF at certain points. Can you do some research to help me understand how I could implement something like this? End your analysis with a recommended solution. Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.


## Response

I'll research how VHS tapes are used in this repo and what options exist for adding custom text overlays to the generated GIFs. Let me start by exploring the codebase and gathering external knowledge in parallel.

The SDD tree in this ephemeral workspace lives under `.sase/sdd/` (git-untracked here; `sdd/` itself only holds `beads`). The real research files with a `202607/` dir are at `.sase/sdd/research/202607/`, so that's where this file belongs. Now let me ground the VHS research with authoritative, up-to-date sources.

Key finding: VHS has a native `Subtitle` command (PR #726). But the installed version is **v0.11.0** — I need to verify whether that command actually exists in the installed binary or only in a newer release. Let me check both the local binary and the upstream release history.

The `validate` output is ambiguous (it also mis-parsed the `Output` path), and the binary contains a `Subtitle` string yet rejects the command. This is the crux of the whole recommendation, so let me nail it down rigorously with a clean tape file, and cross-check the upstream release history.

Definitive confirmation:
- **v0.11.0 (the installed, latest release) has NO native caption command** — `vhs validate` rejects `Subtitle`. Issue #735 requesting it is open and unimplemented (the earlier "PR #726 implemented it" search snippet was wrong; the `Subtitle`/`subtitle` strings in the binary come from vendored deps, not the tape parser).
- Local **ffmpeg 7.1.5 has everything needed**: `drawtext` (libfreetype), `subtitles`+`ass` (libass), `overlay`, `palettegen`/`paletteuse`, fontconfig, librsvg. ImageMagick present; gifsicle absent. VHS emits both `.mp4` and `.gif` per tape.

Before writing the recommendation, let me prove the core post-processing pipeline actually works end-to-end on a real demo mp4 with this toolchain.

PoC succeeded — caption burned, gif (721 frames) and mp4 (28.84s preserved) regenerated. Let me visually confirm the caption actually rendered by extracting a frame at t=2s (inside the cue window).

The caption renders exactly as intended — a styled lower-third ("Recall prior prompts instantly") in Fira Code over the real demo frame at t=2s, and absent at t=5s. The pipeline is proven with the installed toolchain. One useful incidental finding: the tape sets `Framerate 30` but the rendered mp4 is **25fps** — reinforcing that cue timing must be measured from the *rendered artifact*, not assumed from tape settings.

Let me clean up the PoC artifacts and write the research document.

Done. I researched this end-to-end — verified the toolchain, checked upstream VHS, and proved the recommended pipeline works on a real demo artifact — and wrote it up to:

`.sase/sdd/research/202607/vhs_demo_text_overlay_captions.md`

(Note: in this ephemeral workspace the SDD tree lives under `.sase/sdd/`; the plain `sdd/` dir only holds `beads`. That's where the existing `202607/` research files are, so the file is there. Since it's a markdown file in `sdd/research/`, the `just check` rule doesn't apply.)

## Key findings

- **VHS has no native caption command.** I confirmed three ways: it's absent from the docs, `vhs validate` on the installed **v0.11.0** (latest release) rejects `Subtitle` as an invalid command, and upstream [issue #735](https://github.com/charmbracelet/vhs/issues/735) requesting it is **open/unimplemented**. So captions must come from a layer you own — practically, post-processing.
- **The enabling fact:** `just demos` already emits an `.mp4` per tape, and the host's **ffmpeg 7.1.5** is built with `libass`/`libfreetype`/`libfontconfig` plus `palettegen`/`paletteuse`. You can burn styled text into the mp4 and regenerate the gif — without ever re-recording the TUI.
- **The real hard part is timing, not text.** Your tapes are event-driven (`Wait+Screen`), so cue times aren't known from the tape and can drift. I also found the tapes declare `Framerate 30` but the mp4 renders at 25fps — so cue timing must be measured against the *rendered* file.

## Recommendation (proven, not theoretical)

An **ffmpeg + libass caption stage driven by a per-tape sidecar YAML**, producing separate `*.captioned.{gif,mp4}` outputs, wired into `just demos`:
- **Phase 1 (ship now):** sidecar with absolute timestamps → generate an `.ass` (styled lower-third in Fira Code) → burn + regenerate gif in one ffmpeg pass.
- **Phase 2 (if drift bites):** anchor cues to hidden `Screenshot` markers, resolved to timestamps by nearest-frame matching, so captions track *content* instead of wall-clock.

I validated the core pipeline by burning a faded "Recall prior prompts instantly" lower-third into the actual `sase_ace_prompt_input.mp4` and confirming (via an extracted frame) it renders correctly inside its cue window and disappears after — using only the installed toolchain. The doc includes the working ffmpeg commands, the ASS template, the sidecar schema, a comparison table of all five approaches, the Rust-core-boundary rationale for keeping it in this repo, and risks/open questions.

One decision worth your input for a follow-up: whether `*.captioned.*` artifacts should be committed alongside `demos/out/` (and participate in visual-diff gating) or regenerated on demand.
