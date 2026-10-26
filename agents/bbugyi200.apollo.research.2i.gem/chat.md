# Chat History - ace-run (research.2i.gem)

- **TIMESTAMP:** 2026-10-26 14:16:21 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2i.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261026_134815.md`

## Prompt

%id(gem, clan=research.2i)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2i.cdx`, `research.2i.cld`, `research.2i.grk`, `research.2i.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The Muse LLM provider still shows no output streamed to the reply card in the main deck
while running (it arrives after the agent completes). See the
~/tmp/screenshots/20261026_134521.png screenshot for an example of an agent (the
`bob-cli-cn.1` sase agent running on my athena machine) that has this problem.

Can you do some research with the goal of helping me figure out exactly what is causing
this issue (it only seems to effect Muse)? End your analysis with a recommended
solution. 
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

# Independent Research Report: Muse Reply Card Streaming Root Cause & Solution

**Researcher:** `research.2i.gem`  
**Report File:** [`muse_live_reply_card_streaming__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/muse_live_reply_card_streaming__gem.md)  
**Registered Artifact:** `research:202610/muse_live_reply_card_streaming__gem.md` (`file:explicit:1c62dd3e6ff66e7b55af6b07`)

---

### 1. Executive Summary & Observed Problem

In the SASE TUI Main Deck, when agents run under the **Muse** LLM provider (such as `bob-cli-cn.1` on `athena`, seen in screenshot `~/tmp/screenshots/20261026_134521.png`), the **Reply Card** displays only:
```text
Waiting for agent response...
```
for the entire duration of the run (21+ minutes across 131 tool executions), only populating all at once after the agent completes. In contrast, Claude Code, Codex, Antigravity CLI, and Grok stream progress and thoughts progressively to the Reply Card while running.

---

### 2. Root Cause Analysis

Tracing the full pipeline across the TUI rendering engine, provider subprocess adapters, and the Muse Code CLI protocol revealed the exact mechanism:

1. **How the TUI Populates the Reply Card:**
   - In [`_agent_display_render_main.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/prompt_panel/_agent_display_render_main.py), while `agent.status == "RUNNING"`, the TUI calls `agent.get_timestamped_reply_chunks()` and `agent.get_live_reply_content()`, which read directly from `live_reply.md` (and `live_reply_timestamps.jsonl`).
   - If `live_reply.md` is empty or missing, the TUI falls back to rendering:
     ```python
     Text("Waiting for agent response...\n", style="dim italic")
     ```
   - When the agent transitions to `DONE`, the TUI switches to `get_response_content(agent)`, which loads the finalized `response.md`.

2. **The Subprocess Stream Filter in `_subprocess_muse.py`:**
   - In [`_subprocess_muse.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/_subprocess_muse.py#L32-L46), `append_stream_text(live_reply_path, delta)` is triggered **strictly** when:
     ```python
     if envelope.get("payload_type") != "run.output.delta":
         return
     ```
   - No other event types write to `live_reply.md`.

3. **The Muse Code Protocol Behavior:**
   - Analysis of test fixtures (`muse_exec_shell_tool_R3401.1.jsonl`) and live multi-turn executions (`muse exec --json`) revealed that during intermediate tool-execution turns, Muse **never emits `run.output.delta`**.
   - Instead, Muse treats tool calling as pure function invocations, outputting only `task.lifecycle.*` and `tool.result` envelopes without conversational narration.
   - Muse emits `run.output.delta` **only on the final turn of the run** when generating the terminal conversational summary, immediately followed by `run.terminal.completed` and process exit.
   - For a 21-minute agent running 131 tools, `live_reply.md` remains **0 bytes for 21 minutes and 35.9 seconds**. The TUI faithfully displays `"Waiting for agent response..."`.

4. **Secondary Defect in Terminal Event Capture:**
   - In `_capture_run_terminal()` ([`_subprocess_muse.py#L48-L62`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/_subprocess_muse.py#L48-L62)), `run.terminal.completed` captures `payload.text` into in-memory state, but never appends to `live_reply.md`. If delta chunks are ever batched or missed, `live_reply.md` is never populated prior to exit.

---

### 3. Recommended Solution

A two-layer solution resolves this issue cleanly:

1. **Provider Adapter Activity Streaming (Primary Fix in [`_subprocess_muse.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/_subprocess_muse.py)):**
   - When `task.lifecycle.started` arrives, extract the tool name and command summary and append an italicized progress breadcrumb to `live_reply.md` (e.g. `*▶ Executing tool: shell (git status)...*`).
   - When the first `run.output.delta` arrives, insert a separator before the final conversational reply begins.
   - In `_capture_run_terminal()`, append `payload["text"]` to `live_reply.md` if `state.seen_output_delta` was false as a fallback.
   - *Impact:* Immediate visual parity with Claude/Codex without requiring frontend changes.

2. **TUI Reply Card Tool Activity Fallback (Complementary UX Polish in [`_agent_display_render_main.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/prompt_panel/_agent_display_render_main.py)):**
   - If `live_reply.md` is empty for a running agent but `agent.tool_call_count > 0`, display the active tool execution status (e.g. `Executing tool #131...`) instead of the static `"Waiting for agent response..."` placeholder.
