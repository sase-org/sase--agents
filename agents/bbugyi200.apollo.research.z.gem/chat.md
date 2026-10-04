# Chat History - ace-run (research.z.gem)

- **TIMESTAMP:** 2026-10-01 01:07:44 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.z.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_005538.md`

## Prompt

%id(gem, clan=research.z)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.z.cdx`, `research.z.cld`, `research.z.grk`, `research.z.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
need a way to generate audio content from markdown files (like the research produced by
agents that is stored in the research sidecar repo, for example). I would like to listen
to this content while commuting / walking.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. 
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

# Research Report: Generating Commuter Audio from Research Markdown

I have completed the independent research investigation on converting technical markdown documents (such as SASE research artifacts) into audio optimized for listening while walking or commuting.

The full report has been written to:
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/markdown_to_audio_pipeline__gem.md`

Durable snapshot registration succeeded:
- **Artifact ID**: `explicit:83f8ecc3e34df4f36ca4c33c`
- **Artifact Ref**: `file:explicit:83f8ecc3e34df4f36ca4c33c`
- **Label**: `research:202610/markdown_to_audio_pipeline__gem.md`
- **Snapshot Path**: `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261001005543/markdown_to_audio_pipeline__gem-90c89f68399a.md`

---

## Executive Summary & Key Findings

### 1. The Core Obstacle: Verbatim TTS Fails on Technical Markdown
Technical research markdown is filled with visual scaffolding: multi-column benchmark tables, code blocks, diffs, footnotes, and URLs. 
- Feeding this text directly into a text-to-speech engine results in an exhausting, monotone 45+ minute audio stream where tables become meaningless lists of numbers and code fences turn into alphabet soup.
- While walking or driving, hands and eyes are occupied and ambient noise is high. Audio comprehension requires **audible signposts**, **conversational explanations of visual structures**, and **pacing tailored to a 10–18 minute walk**.

### 2. The Recommended Architecture: Two-Tier Audio Pipeline

| Pipeline Layer | Primary Technology | Fallback / Alternative | Key Advantages |
| :--- | :--- | :--- | :--- |
| **Script Adaptation** | **LLM Audio Scriptwriter** (Dual-Host Dialogue or Solo Executive Memo) | AST-Sanitized Verbatim Narration (via regex/parser) | Translates tables, benchmarks, and code into conversational explanations optimized for walking comprehension. |
| **TTS Engine** | **Kokoro-82M** (Local open-weight via ONNX/PyTorch or `Kokoro-FastAPI`) | **Microsoft Edge TTS** (`edge-tts`, free cloud) or **OpenAI Audio** (`tts-1`) | Kokoro-82M delivers commercial-grade prosody at 3x–5x real-time on CPU, requires zero per-use API fees, and includes distinct male/female voices for dual-host dialogue. `edge-tts` provides an instant zero-dependency cloud fallback. |
| **Packaging & Mastering** | **128 kbps MP3 with EBU R128 Normalization** (-16 LUFS) & ID3v2 Chapters | Chaptered M4B (AAC) | MP3 with ID3v2 chapters is 100% universally compatible across mobile podcast apps, car dashboards, and Telegram. Loudness normalization prevents traffic noise from masking speech. |
| **Mobile Delivery** | **Private Podcast RSS Feed** (served over Tailscale or Cloudflare R2) + **Telegram Audio Push** | Audiobookshelf / Syncthing | Podcast apps (Pocket Casts, Overcast, Apple Podcasts, AntennaPod) auto-download episodes in the background over Wi-Fi with lock-screen, Bluetooth, and variable-speed controls. Telegram push (via existing `sase-telegram`) provides instant notifications. |
| **Dependency Isolation** | `uv run --with static-ffmpeg` | System package install (`apt install ffmpeg`) | Bryan's machine does not have system `ffmpeg` installed. `static-ffmpeg` via `uv` provides fully isolated, root-free FFmpeg capabilities. |

---

## Synthesis Engine Evaluation Summary

| Engine | Quality / Naturalness | Speed (Real-time Factor) | Hardware Footprint | Cost per 1M Chars | Cost per 15-min Episode |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Kokoro-82M** | **Excellent** | **3x–5x (CPU)** / **25x–50x (GPU)** | Tiny (<400MB RAM/VRAM) | **$0.00** | **$0.00** |
| **Microsoft Edge TTS** (`edge-tts`) | **Very Good** | **10x–20x (Cloud stream)** | Negligible | **$0.00** | **$0.00** |
| **OpenAI Audio API** (`tts-1`) | **Very Good** | **8x–15x (Cloud REST)** | None | **$15.00** | **~$0.22** |
| **ElevenLabs** | **Outstanding** | **3x–8x (Cloud REST)** | None | **$150.00–$300.00** | **$2.25–$4.50** |
| **Piper TTS** | **Good** (Slightly robotic) | **10x–20x (CPU)** | Very low (<100MB RAM) | **$0.00** | **$0.00** |

---

## Actionable Next Steps to Implement

1. **Script Adaptation Prompt**: Use a structured prompt template (provided in Section 8.1 of the report) with Claude 3.5 Haiku, Gemini 1.5/2.0 Flash, or GPT-4o-mini to transform markdown reports into a 12–15 minute dual-host JSON dialogue (`alex` and `sam`).
2. **Synthesis & Mastering**:
   - Synthesize using `uvx edge-tts` or `kokoro` with `alex` (`en-US-ChristopherNeural` / `am_adam`) and `sam` (`en-US-JennyNeural` / `af_heart`).
   - Concatenate chunks and normalize loudness to -16 LUFS using `uv run --with static-ffmpeg`.
3. **Private Feed over Tailscale**:
   - Serve a local podcast directory (`~/.sase/podcast/`) using a background HTTP server bound to the Tailscale IP (`http://<tailnet-host>:8080/feed.xml`).
   - Subscribe once in Pocket Casts, Overcast, or AntennaPod. Episodes will auto-download over Wi-Fi before you walk.
4. **Telegram Dispatch**: Leverage the already-running SASE Telegram daemon to push audio files directly to a private channel for on-demand playback.
