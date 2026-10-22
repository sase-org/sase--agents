# Chat History - ace-run (research.3g.gem)

- **TIMESTAMP:** 2026-10-03 13:43:28 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3g.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_132117.md`

## Prompt

%id(gem, clan=research.3g)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3g.cdx`, `research.3g.cld`, `research.3g.grk`, `research.3g.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
would like to add support to the Muse LLM provider for streaming its output.

- I'm pretty sure we used to support this but then fixed a related bug which caused Muse
  agent replies to be chunked poorly.
- Unfortunately, I don't think that reply streaming has worked for the Muse provider
  ever since.

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

# Research Report: Output Streaming Support in the Muse LLM Provider

**Author**: Researcher `gem` (`research.3g.gem`)  
**Report File**: [`sase/repos/research/202610/muse_provider_output_streaming_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202610/muse_provider_output_streaming_architecture__gem.md)  
**Registered Artifact**: `file:explicit:cc137ced85dfc18c6f775617` (Label: `research:202610/muse_provider_output_streaming_architecture__gem.md`)

---

## 1. Executive Summary & Core Verdict

The Muse Code (`muse`) LLM provider backend in SASE *does* receive real-time token fragments (`run.output.delta` events) from `muse exec --json`. However, output streaming is functionally broken across both user-facing surfaces (the CLI console and the TUI prompt panel). 

This breakdown is the unintended consequence of the bugfix landed in commit `a0244d7599` ("*fix(muse): coalesce output deltas into one live-reply chunk per run stream*") combined with Rich console line-buffering and Muse's execution lifecycle:

1. **CLI Console Streaming is Silenced by Rich `Live` Buffering**: When running via `sase run`, the subprocess is wrapped in `output.provider_timer("Waiting for Muse Code")`. Because commit `a0244d7599` switched to `print(text, end="", flush=True)` to stream partial words, Rich's underlying `Live` stdout redirection intercepts and line-buffers the partial writes without displaying them until a newline is printed. The user sees a frozen spinner for the entire duration of the stream, followed by an abrupt batch dump when the stream terminates.
2. **TUI Paragraph Progression is Destroyed**: By forcing all deltas of a stream into a single chunk starting at byte offset 0, the TUI loses the ability to render progressive paragraph dividers over time.
3. **The Tool Execution Silence Gap**: Muse executes tools (reading/editing files, running tests) *before* emitting any conversational reply deltas. During this tool phase (often 90%+ of the turn duration), zero `run.output.delta` events are emitted, leaving `live_reply.md` completely empty and showing `"Waiting for agent response..."` until the final seconds of the turn.

---

## 2. Historical Root Cause: From Poor Chunking to Broken Streaming

### Phase 1: The Initial Implementation (`44fa7eee24`)
In the initial Muse provider implementation, incoming `run.output.delta` events were passed directly to `append_stream_text()`:
```python
def _stream_output_delta(payload: Mapping[str, object], state: _MuseStreamState) -> None:
    text = payload.get("text")
    if not isinstance(text, str) or not text:
        return
    append_stream_text(text, state.streamed_texts, state.suppress_output, ...)
```
`append_stream_text()` was designed for Claude and Codex block-level messages: on every call, it wrote a timestamp entry to `live_reply_timestamps.jsonl`, prepended `\n\n`, and called `print(text, flush=True)`.

Because `muse exec --json` emits raw sub-word token fragments (e.g. `'trees '`, `' are'`, `' tow'`, `'ering'`), this caused the **poor chunking defect**: every syllable or word was wrapped in its own TUI timestamp divider (`─── 13:30:15 ──────`) separated by double newlines, and printed on its own line in the terminal.

### Phase 2: The Coalescing Fix (`a0244d7599`)
To eliminate the mid-word splitting bug, commit `a0244d7599` introduced `append_stream_delta()`:
```python
def _stream_output_delta(payload: Mapping[str, object], state: _MuseStreamState) -> None:
    ...
    stream_key = _run_stream_key(payload)
    new_chunk = state.open_stream_key != stream_key
    if new_chunk:
        _close_delta_chunk(state)
        state.open_stream_key = stream_key
    append_stream_delta(text, state.suppress_output, ..., new_chunk=new_chunk)
```
- Only the *first* delta of a stream was given `new_chunk=True`, writing a single timestamp at offset 0.
- All subsequent deltas appended bare text to `live_reply.md` and called `print(text, end="", flush=True)`.
- A terminal newline was printed only when the stream finished in `_close_delta_chunk()`.

### Why This Broke Streaming
- **On the CLI**: Rich's `provider_timer` (`rich.live.Live`) intercepts `sys.stdout`. Rich's stdout wrapper buffers writes until it sees `\n`. Because `print(text, end="", flush=True)` provides no newline, all deltas remain trapped in Rich's memory buffer while the spinner continues to spin. Only when `run.terminal.completed` arrives 5–10 seconds later does `_close_delta_chunk()` emit `\n`, dumping the entire accumulated text at once.
- **In the TUI**: While `live_reply.md` updates on disk, the entire reply is forced into one monolithic chunk. The prompt panel never shows chronological paragraph progression, and because Muse outputs deltas in a rapid burst at the end of the turn (e.g., 106 deltas over 1.89s in our live benchmarks), the burst completes within a single 1–2 second TUI polling interval.

---

## 3. Evaluation of Implementation Options

1. **Reverting to PTY Plain Output (Abandoning `--json`)**: **Rejected**. Running `muse exec` without `--json` in a pseudo-terminal would sacrifice structured tool tracking (`_tool_call_muse.py`), model metadata configuration, usage parsing from `--session-id`, and machine-readable error classification.
2. **Direct Unbuffered Writes (`sys.__stdout__`)**: **Rejected**. Writing directly to unbuffered stdout bypasses Rich's line buffer but collides violently with Rich's `Live` cursor repainting, causing the spinner thread (updating at 2 Hz) to erase or overwrite printed text.
3. **Paragraph-Boundary Delta Chunking**: **Recommended for TUI**. Detect `\n\n` boundaries across incoming deltas. When a delta completes a paragraph and begins a new one, trigger `new_chunk=True`. This matches Gemini/Antigravity's ergonomic paragraph chunking without splitting words.
4. **Timer-Dismissal Streaming Handoff**: **Recommended for CLI**. When the first `run.output.delta` arrives, fire a callback that cleanly stops `provider_timer`. Once the spinner exits, subsequent token fragments stream directly to the terminal with zero line-buffering.

---

## 4. Recommended Solution

The recommended solution combines **paragraph-boundary delta chunking** in `_subprocess_muse.py` with an **early timer handoff** in `muse_provider.py` and `output.py`:

### Step 1: Add Paragraph-Boundary Detection in `_subprocess_muse.py`
Upgrade `_MuseStreamState` to track consecutive newlines across streamed deltas:
- When `state.consecutive_newlines >= 2` and a delta begins with non-whitespace content, set `new_chunk = True`.
- `append_stream_delta()` records a new timestamp entry at `live_reply_file.tell()` for the new paragraph.
- Intra-paragraph deltas continue to concatenate seamlessly (`new_chunk = False`), preventing word-splitting.

### Step 2: Implement Stoppable `provider_timer` for the CLI
In `src/sase/output.py`:
- Add a `.stop()` method to `provider_timer` to finalize the `Live` spinner early.
In `src/sase/llm_provider/muse_provider.py`:
- Wire an `on_stream_start` callback from `_subprocess_muse.py` to `timer_context.stop()`.
- While Muse executes tools or waits on the network, the spinner `⏱️ Waiting for Muse Code [MM:SS]` displays normally.
- The instant delta 1 arrives, the spinner completes (`✅ Waiting for Muse Code completed in ...`), and all subsequent tokens stream directly to stdout in real-time.

### Step 3: Update Test Assertions
Update `tests/ace/tui/widgets/test_agent_reply_muse_chunks.py` and `tests/llm_provider/test_muse_provider_stream.py`:
- Preserve assertions that intra-sentence deltas (mid-word, mid-inline-code) coalesce into 1 chunk.
- Add test cases verifying that multi-paragraph deltas separated by `\n\n` create distinct timestamped chunks.

---

## 5. Artifact & Turn Finalization

- **Research Report**: Written to [`sase/repos/research/202610/muse_provider_output_streaming_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202610/muse_provider_output_streaming_architecture__gem.md).
- **Artifact Registration**: Successfully registered via `sase artifact create` as snapshot `file:explicit:cc137ced85dfc18c6f775617`.
- **Finalizer Declaration**: Verified and submitted host declaration via `sase final submit -` (commit obligation accepted for repo `repo-29a3edc5b48c`).
