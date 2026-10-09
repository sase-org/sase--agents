# Chat History - ace-run (research.0r.gem)

- **TIMESTAMP:** 2026-10-09 18:00:25 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0r.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_173435.md`

## Prompt

%id(gem, clan=research.0r)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.0r.cdx`, `research.0r.grk`, `research.0r.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Muse reply streaming is still not working correctly. I never see any text in a Muse sase
agent's "Reply" card until that agent completes. Can you do some research with the goal
of helping me figure out how to fix this? 
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

# Research Report Summary: Muse Agent Reply Streaming Latency & Blank Reply Card

**Researcher Identity:** `gem` (Swarm Report `__gem.md`)  
**Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/muse_reply_streaming_investigation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/muse_reply_streaming_investigation__gem.md)  
**Artifact Registration:**
- **Artifact ID:** `explicit:6ce810efc2aebd0748d44acb`
- **Stored Snapshot Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261009173443/muse_reply_streaming_investigation__gem-fa653be4d586.md`
- **Reference:** `file:explicit:6ce810efc2aebd0748d44acb`
- **Label:** `research:202610/muse_reply_streaming_investigation__gem.md`

---

## 1. Key Finding & Root Cause Diagnosis

The observed issue—*never seeing any text in a Muse agent's "Reply" card until completion*—is **not** caused by a broken pipe, blocked socket, or I/O buffering defect in SASE's event loop. Instead, it is an **architectural mismatch between Muse's event lifecycle model and SASE's Reply card presentation pipeline**:

1. **Tool-Phase Delta Starvation:**
   - In headless mode (`muse exec --json`), Muse treats tool execution as batch task executions rather than conversational turns.
   - During tool calling (which accounts for **95% to 99%** of an agent's running time), Muse emits `task.lifecycle.*` and `tool.result` events.
   - Muse emits **zero `run.output.delta` events** while executing tools.

2. **Strict SASE Parser Segregation:**
   - In [`_subprocess_muse.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/llm_provider/_subprocess_muse.py), `_process_muse_json_line()` only writes `run.output.delta` to [`live_reply.md`](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261009173443/live_reply.md) (via `append_stream_delta()`).
   - Tool events are routed exclusively to [`tool_calls.jsonl`](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261009173443/tool_calls.jsonl) (for the TUI "Tools" card) and contribute **nothing** to `live_reply.md`.

3. **Empty Reply Buffer in TUI:**
   - The ACE TUI's Reply card follower ([`_live_reply_follow.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/prompt_panel/_live_reply_follow.py)) monitors `live_reply.md`.
   - While `live_reply.md` remains 0 bytes throughout the multi-minute tool execution phase, the Reply card continuously renders:
     ```text
     Waiting for agent response...
     ```

4. **Completion Burst Illusion:**
   - Only *after* all tools have completed does Muse generate its final answer.
   - Muse emits `run.output.delta` in a rapid 1–2 second burst immediately followed by `run.terminal.completed`.
   - The process exits, SASE marks the agent `DONE`, and the reply text suddenly renders.
   - To the user, it appears as though reply streaming was completely buffered until termination.

5. **Contrast with Claude Code & Codex:**
   - Claude models natively generate conversational assistant text blocks explaining their reasoning before and between tool calls (`{"type": "assistant", "message": {"content": [{"type": "text", ...}]}}`). These stream continuously to `live_reply.md`.
   - Muse suppresses all conversational text deltas in `exec --json` until the final terminal response. Prompting Muse to "explain before calling tools" does not override this behavior in headless mode.

---

## 2. Proposed Solutions

### Solution 1: Provider-Side Live Reply Progress Projection (Recommended)
- **Concept:** In [`_subprocess_muse.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/llm_provider/_subprocess_muse.py), intercept `task.lifecycle.proposed` and `tool.result` events and write compact progress indicators (e.g., `*⚡ Running tool: `Bash`...*` and `*↳ ✓ `Bash` success*`) directly to `live_reply.md`.
- **Why it is safe:** SASE defines `live_reply.md` as an ephemeral draft buffer for in-flight display. Turn completion returns `state.terminal_texts`, ensuring the final saved response ([`response.md`](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261009173443/response.md) / chat history) remains 100% clean markdown without tool progress artifacts.
- **Result:** Provides instant, continuous visual activity in the Reply card from the moment the agent starts until it finishes.

### Solution 2: TUI-Level Fallback Projection
- **Concept:** In [`_live_reply_follow.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/prompt_panel/_live_reply_follow.py), if `live_reply.md` is empty for an active agent, inspect [`tool_calls.jsonl`](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261009173443/tool_calls.jsonl) and display an active tool summary (e.g. `[Executing: Bash - "find ..."]`) in place of `Waiting for agent response...`.
- **Result:** Provider-agnostic; benefits any provider that starves text deltas during tool phases.

---

The full research report with empirical probe logs, architectural traces, and concrete code snippets has been saved and registered as durable artifact `research:202610/muse_reply_streaming_investigation__gem.md`.

The finalizer declaration for the `commit` payload was published and successfully submitted:

- **Repository**: `sdd:research` (`repo-8caa19a02d02`)
- **Action**: `commit`
- **Commit Message**: `docs(research): investigate muse reply streaming and propose live progress projection`
- **Status**: Declaration accepted by the host.
