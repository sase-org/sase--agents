# Chat History - ace-run (research.z.cld)

- **TIMESTAMP:** 2026-10-01 01:23:08 EDT
- **MODEL:** claude/opus
- **AGENT:** research.z.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_005538.md`

## Prompt

%id(cld, clan=research.z)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.z.cdx`, `research.z.grk`, `research.z.mus`, `research.z.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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

Surveying the research corpus (874 reports, median ~3,500 words, which is about 23 minutes of audio each) before looking at TTS options.

Found a strong precedent: `#research_swarm` already has an opt-in `image=true` stage that generates infographics beside reports. Next I'm checking the hook and Telegram plugin for delivery options.

Mapping how reports already flow to the user (Highlights PDF hook, Telegram), then checking whether athena has a GPU for local TTS.

Comparing TTS engines now: the Speech Arena puts Gemini 3.8 Flash TTS near the top at about 1/5 of ElevenLabs' price. I'm checking which open-weight models could run on athena's RTX 3080 Ti.

Kokoro on apollo's CPU (load avg ~14) ran at **1.68× realtime**: 94s of audio in 56s. Now trying athena (Threadripper + RTX 3080 Ti) for comparison.

`sase_gateway` is the service behind it. I'm checking whether it already has a mobile or web surface that could host audio.

There's also a paired SASE Android app (`sase-android`) behind this gateway, which is a third possible delivery surface. Next I'm checking how the Telegram outbound handles notification attachments.

Confirming per-request limits now: OpenAI caps TTS input at 4,096 characters, and older Gemini TTS drifted after about a minute. Both point to chunking by section.

The ASR check hit a PyAV version mismatch. Retrying by passing decoded audio arrays directly.

I have enough evidence. Writing the report now, after confirming the target filename is free.

Fixing a couple of arithmetic and consistency details before registering.

Report written. Registering it as a durable artifact and cleaning up the benchmark scratch directories (large venvs and models on both hosts).

Artifact registered (`file:explicit:eb3f35a0e80d1a59ad0a4073`). Running the final declaration.

I wrote the report and registered it as an artifact (`file:explicit:eb3f35a0e80d1a59ad0a4073`, labelled `research:202610/markdown_to_audio_listening_pipeline__cld.md`). The host commits it to the research repo after this turn.

**Report:** `sase/repos/research/202610/markdown_to_audio_listening_pipeline__cld.md`

## What I found

- **Reading the reports aloud as-is doesn't work.** They are full of tables, code blocks and `file.py:NNN` citations, about 133 inline code spans per report. In one paragraph, the citations alone added 54% to its spoken length (35.9s vs 23.3s). Whisper heard one citation back as *"Plugins browser agent clives actions. Pi, 87."* An LLM step that rewrites each report as a spoken script is required.
- **There's too much to listen to all of it.** The repo has 438 finished reports, 117 of them from September alone. Read in full, one month is about 37 hours of audio. So I recommend a short **daily digest** covering every new report, plus **full audio versions only when you ask** for one.
- **Speech engine: Gemini 3.8 Flash TTS by default, Kokoro as the free local fallback.**
  - Gemini ranks #3 in a public blind-listening leaderboard and costs about $0.014 per minute of audio. That is roughly $5 a month for the recommended mix, doubling to about $10 from January 2027.
  - Kokoro is free and open source. I measured it at 28.7× realtime on athena's GPU and 1.7× on apollo's CPU, and Whisper transcribed its output back with a 3.3% word error rate.
  - ElevenLabs sounds slightly better but costs 5–7× more. Not worth it for this.
- **Getting it onto your phone: Telegram first, then a private podcast feed.**
  - Telegram's built-in music player already gives you speed control, background play and saved position. Today the Telegram plugin sends `.mp3` files as plain documents, so it needs a small `send_audio` change, about 20 lines.
  - Later, an RSS feed served from apollo through Tailscale Funnel on port 8443 and subscribed in AntennaPod adds offline downloads, a queue and chapters. Port 443 is already used for `sase_gateway`. A tailnet-only feed won't work because your Pixel's Tailscale was last seen 11 days ago.
- **Keep the audio files out of git.** The research repo is public and already ~357 MB. Commit only the small spoken script (`<stem>_narration.md`) next to each report. Those scripts also need adding to the research plugin's exclusion list, or each one would trigger a Highlights PDF.

## Recommendation

Build a small **`sase-listen` plugin** that turns a spoken script into an MP3 with chapters. Drive it with SASE agents that write the scripts:
- `#research/audio` for on-demand versions, which you can launch from Telegram;
- an `audio=true` option in `#research_swarm`, built like the existing `image=true` option;
- `#research/digest` for the daily digest.

Build it in three phases:
1. On-demand versions delivered over Telegram.
2. The podcast feed and the swarm option.
3. The daily digest and an automatic speech-recognition quality check.

## Not yet verified

I didn't call any paid API, so all Gemini, OpenAI and ElevenLabs figures come from published pricing and leaderboards. The report lists the live checks still needed, including rendering one 12-minute episode with Gemini to confirm the ~$0.16 cost estimate.

On athena, the newest `onnxruntime-gpu` (the GPU library Kokoro runs on) needs CUDA 13, but the installed NVIDIA driver (550) only supports CUDA 12.4. Pinning version `1.22.0` worked; upgrading the driver is the alternative.

I removed the benchmark installs on both machines. The small sample WAVs are still in `/tmp/cld_tts_bench/` on apollo if you want to hear how Kokoro sounds.
