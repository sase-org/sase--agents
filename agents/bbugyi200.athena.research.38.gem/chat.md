# Chat History - ace-run (research.38.gem)

- **TIMESTAMP:** 2026-10-01 15:03:15 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.38.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_145619.md`

## Prompt

%id(gem, clan=research.38)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.38.cdx`, `research.38.cld`, `research.38.grk`, `research.38.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you help me
understand what the new sase-listen repo will actually provide to users that install it?
See the sase-1e3 epic bead for context. Make sure the report you produce is useful,
concise, and beautiful. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Independent Research Report: What `sase-listen` Delivers to Users

**Researcher:** `research.38.gem`  
**Context:** SASE Epic Bead `sase-1e3` · Plan [`plan:202610/sase_listen.md`](file:///home/bryan/projects/github/sase-org/sase/sase/repos/plans/202610/sase_listen.md)  
**Artifact Snapshot:** [`research:202610/sase_listen_user_capabilities_and_deliverables__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/sase_listen_user_capabilities_and_deliverables__gem.md)  
**Registered Artifact Ref:** `file:explicit:1160f9bc896031ece6c9a61e`

---

## Executive Summary

The new **[`sase-org/sase-listen`](https://github.com/sase-org/sase-listen)** repository provides an open-source, studio-grade audio production engine and mobile delivery pipeline that converts Markdown documents into chaptered, loudness-normalized MP3 audio editions tailored for listening during commutes, walks, or workouts.

Crucially, **`sase-listen` is a standalone Python package (`uv tool install sase-listen`)**, completely decoupled from SASE's core Rust backend (`sase-core`). It functions independently for any developer who wants to turn Markdown into podcasts, while offering native, zero-friction integration for SASE swarms (`#research_swarm audio=true`), Telegram bots (`sendAudio`), and private AntennaPod feeds.

```
                              ┌─────────────────────────────────────────────────────────┐
                              │                   INPUT MARKDOWN                        │
                              │  (SASE Research Report, Technical Doc, or Notes)        │
                              └───────────────────────────┬─────────────────────────────┘
                                                          │
                                         ┌────────────────┴────────────────┐
                                         ▼                                 ▼
                              ┌────────────────────┐            ┌────────────────────┐
                              │   AGENT SCRIPT     │            │   DETERMINISTIC    │
                              │   (LLM Audio Ed.)  │            │   AST NORMALIZER   │
                              └──────────┬─────────┘            └──────────┬─────────┘
                                         │                                 │
                                         └────────────────┬────────────────┘
                                                          ▼
                                      ┌───────────────────────────────────────┐
                                      │      NARRATION SCRIPT CONTRACT v1     │
                                      │  (Clean prose, ## chapters, metadata) │
                                      └───────────────────┬───────────────────┘
                                                          ▼
                                      ┌───────────────────────────────────────┐
                                      │         TTS SYNTHESIS ENGINE          │
                                      │  Gemini 3.8 Flash (default) / OpenAI /│
                                      │  Kokoro-82M / Offline Tone (testing)  │
                                      │  [Content-Addressed Chunk Cache]      │
                                      └───────────────────┬───────────────────┘
                                                          ▼
                                      ┌───────────────────────────────────────┐
                                      │       STUDIO AUDIO MASTERING          │
                                      │  • Bundled static FFmpeg 7.0.2        │
                                      │  • Two-pass EBU R128 (-16 LUFS)       │
                                      │  • Dynamic silence compression        │
                                      │  • ID3v2.3 CHAP/CTOC chapter tagging  │
                                      │  • Generated 1400x1400 Cover Art      │
                                      └───────────────────┬───────────────────┘
                                                          ▼
                                      ┌───────────────────────────────────────┐
                                      │        OUTPUT: 64 kbps CBR MP3        │
                                      └───────────────────┬───────────────────┘
                                                          │
                                         ┌────────────────┴────────────────┐
                                         ▼                                 ▼
                              ┌────────────────────┐            ┌────────────────────┐
                              │  PRIVATE PODCAST   │            │  TELEGRAM AUDIO    │
                              │  (RSS 2.0 Feed /   │            │  (Native sendAudio │
                              │   AntennaPod)      │            │   player & speed)  │
                              └────────────────────┘            └────────────────────┘
```

---

## The 7 Primary Deliverables to Users

### 1. Listenability Engine (The Narration Script Contract)
Raw Markdown read aloud by standard TTS is unlistenable due to code blocks, pipe tables, raw URLs, hex commit SHAs, and citation links. `sase-listen` introduces **Narration Script Contract v1**:
- **Dual Script Producers:**
  - **Agent Producer (`producer: agent`):** For deep research reports, an LLM agent drafts an audio-first script. Complex data tables are translated into comparative narratives (winner, runner-up, decisive metrics), and critical numbers are preserved while syntax noise is eliminated.
  - **Deterministic AST Normalizer (`producer: deterministic`):** Mechanically processes generic Markdown via `markdown-it-py`, humanizes identifiers (e.g., `snake_case` → "snake case"), handles small tables row-by-row, drops code fences/URLs, and logs an `omissions.json`.
- **Built-In Authoring & Validation Tooling:**
  - `sase-listen guide`: Prints official authoring guidance and pacing budgets (e.g., max 180 words/paragraph, max 45 words/sentence).
  - `sase-listen lint`: Enforces structural rules, checks for residual Markdown, and verifies number fidelity against the source document.
- **Technical Lexicon (`lexicon.yml`):** Bundled phonetic mapping ensuring technical jargon (`TUI`, `chezmoi`, `LUFS`, `xprompt`, `PyPI`, `mypy`) is pronounced naturally.

### 2. Studio-Grade Media Production (Zero System Dependencies)
- **Hermetic Static FFmpeg:** Bundles static FFmpeg 7.0.2 via `imageio-ffmpeg` (with `libmp3lame`, `loudnorm`, `silenceremove`, and `ebur128`). Users do **not** need `sudo apt install ffmpeg`.
- **Two-Pass EBU R128 Mastering:** Normalizes all output to **−16 LUFS integrated loudness** and **−1.5 dBTP true peak**.
- **Micro-Timing Control:** Injects precise pauses (0.5s between chunks, 1.2s between chapters, 0.9s post-intro) and dynamically compresses pauses over 1.5s down to 0.7s to eliminate dead air.
- **Efficient Audio Profile:** Encodes to **24 kHz, 64 kb/s CBR mono MP3**, producing compact files (~7 MB for a 15-minute report) that stay well below Telegram's 50 MB upload limit.

### 3. Interactive Chapter Markers & Metadata
- Generates native **ID3v2.3 `CHAP` and `CTOC` frames** for every `##` section heading.
- Compatible with mobile podcast players (e.g., AntennaPod), enabling chapter jumping, scrub bars, and visual chapter titles on lock screens.

### 4. Automated 1400×1400 Cover Art System
- Generates beautiful 1400×1400 progressive JPEGs using Pillow.
- Features a **deterministic two-tone gradient palette** keyed to the title hash, bundled Inter typography, metadata badges (`SASE RESEARCH · AUDIO EDITION`), and a title-hash waveform bar motif.
- Supports user-provided images or infographics via intelligent letterboxing over a blurred, darkened background.

### 5. Flexible Multi-Engine TTS Backends & Resilient Caching
- **Gemini 3.8 Flash TTS (Default):** High naturalness and pace using voice `Charon` (or `Kore`, `Sadaltager`, `Iapetus`) at ~$0.0135/min (~$0.22 per 16-minute episode).
- **OpenAI-Compatible Engine:** Supports `gpt-4o-mini-tts-2025-12-15` or private, self-hosted local models like **Kokoro-82M** via Kokoro-FastAPI (`base_url`).
- **Offline Synthetic Tone Engine (`tone`):** Simulates speech-paced tone bursts for instant, cost-free testing, dry runs, and CI validation without network access or API keys.
- **Content-Addressed Chunk Cache:** Hashed by synthesis parameters and text. A interrupted render can be resumed seamlessly without re-synthesizing completed chunks.

### 6. Frictionless Mobile Delivery Channels
- **Private Podcast Feed (Podcasting 2.0 / RSS 2.0):**
  - Managed via `sase-listen feed init`, `publish`, and `status`.
  - Exposable over Tailscale Funnel on `:8443` at an unguessable secret path with `<itunes:block>yes</itunes:block>` to prevent search indexing.
  - `sase-listen feed --qr` prints an ANSI QR code in the terminal for instant subscription in AntennaPod with auto-download enabled.
- **Telegram Audio Player Integration:**
  - Routes MP3s through Telegram's `sendAudio` API, retaining track titles, performers, and cover art in Telegram's built-in background media player with lock-screen playback controls and 1.5×–2× speed options.

### 7. Modern Rich CLI Experience
- `sase-listen render SOURCE`: Renders Markdown or scripts with real-time chapter progress bars, dry-run estimates, and `--json` support for agent automation.
- `sase-listen audition`: Synthesizes ~45-second samples across multiple voices to help users pick preferred narrators before committing to full synthesis.
- `sase-listen doctor`: Diagnostic health checks validating config, FFmpeg capabilities, API credentials, writable paths, disk space, and feed integrity.
- `sase-listen ls`: Inspects the local episode library, durations, chapters, and publication statuses.

---

## Operating Economics

| Engine | Rate / Minute | 16-min Episode | 20 Episodes / Month |
| :--- | :--- | :--- | :--- |
| **Gemini 3.8 Flash TTS** | $0.0135 ($0.027 in 2027) | **$0.22** ($0.43) | **$4.40** ($8.60) |
| **Gemini Flash-Lite TTS**| $0.0090 ($0.018 in 2027) | **$0.14** ($0.29) | **$2.80** ($5.80) |
| **OpenAI Mini TTS** | $0.0150 | **$0.24** | **$4.80** |
| **Kokoro-82M (Local)** | $0.0000 | **$0.00** | **$0.00** |
| **Tone Engine (Offline)**| $0.0000 | **$0.00** | **$0.00** |

---

## Scope Boundaries (What It Intentionally Does NOT Provide)

1. **Not a Two-Host Banter Simulator:** Deliberately uses a single authoritative technical narrator; it is not a NotebookLM-style conversational banter generator.
2. **Not a SASE Rust Subsystem:** Runs as a pure, standalone Python application decoupled from `sase-core`.
3. **No Audio in Git:** Audio files are stored in user XDG data directories, never committed to git repositories.
4. **No Custom Mobile App:** Leverages AntennaPod and Telegram for playback, battery-friendly background streaming, and car head-unit controls.
5. **No Automated Whisper ASR Gate in v1:** Validates quality via heuristic duration, silence, and WPM bounds; speech-to-text verification is deferred.

---

## Artifact Verification

The complete report has been written and registered as a durable SASE artifact:
- **Local File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/sase_listen_user_capabilities_and_deliverables__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/sase_listen_user_capabilities_and_deliverables__gem.md)
- **Artifact Label:** `research:202610/sase_listen_user_capabilities_and_deliverables__gem.md`
- **Artifact ID:** `explicit:1160f9bc896031ece6c9a61e`
- **Turn Finalizer:** Final declaration submitted and accepted (`Accepted final declaration for: commit`).
