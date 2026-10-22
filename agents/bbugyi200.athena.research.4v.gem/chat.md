# Chat History - ace-run (research.4v.gem)

- **TIMESTAMP:** 2026-10-19 07:27:50 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4v.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071316.md`

## Prompt

%id(gem, clan=research.4v)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4v.cdx`, `research.4v.cld`, `research.4v.grk`, `research.4v.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add pi (see the https://github.com/earendil-works/pi GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to pi that you should review if you
can find it. End your analysis with a recommended solution. 
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

# Research Report: Implementing Pi as a First-Class SASE LLM Provider

**Author**: researcher `gem`  
**Report File**: [`pi_llm_provider_implementation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/pi_llm_provider_implementation__gem.md)  
**Artifact Ref**: `file:explicit:a91e5e54fc6c0da2ede615e5` (`research:202610/pi_llm_provider_implementation__gem.md`)  
**Prior Art Reviewed**: [`sase_for_pi_users__final.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/sase_for_pi_users/sase_for_pi_users__final.md)  
**Reference Repo**: `gh:earendil-works/pi` (v1.3.0)  

---

## 1. Executive Summary & Recommended Solution

Pi ([earendil-works/pi](https://github.com/earendil-works/pi)) is an ultra-fast, extensible single-agent coding harness, while SASE is a multi-agent git operating system (providing numbered workspace checkouts, admission gates, host-owned completion, and cross-model DAG coordination). They operate at complementary layers: **SASE hosts Pi, rather than competing with it.**

### Recommended Implementation Strategy (Phased Approach)

1. **Phase 1: Core JSON Stream Provider (`sase.llm_provider.pi:PiProvider`)**
   - Register under `[project.entry-points."sase_llm"]` in `pyproject.toml`.
   - Invoke Pi in JSON stream mode:
     ```bash
     pi --mode json \
        --session-dir <artifacts_dir>/pi_sessions \
        --session-id <agent_session_id> \
        --model <model_name> \
        [--thinking <level>] \
        [--append-system-prompt <bundle_file>] \
        [-nc] \
        "<prompt>"
     ```
   - Stream deltas to `live_reply.txt` via `stream_json_lines()`.
   - Normalize `tool_execution_start` and `tool_execution_end` events into `tool_calls.jsonl` using `base_stream_tool_call_record`.
   - Record token counts and dollar cost into `usage.json` from `message_update.usage`.
   - **Crucial Invariant**: In `--mode json`, an error or abort stop reason does not exit with a non-zero status code. The runner must inspect `message_end.message.stopReason` and strictly wait for **`agent_settled`** with `aborted == false`.

2. **Phase 2: Workspace Portability & Instruction Delivery**
   - **Session Mobility**: Pi defaults to hashing `cwd` to group sessions under `~/.pi/agent/sessions/`. In SASE's ephemeral numbered checkouts (`sase_17`, `sase_18`), this causes cross-workspace session isolation issues. Explicitly setting `--session-dir "$SASE_ARTIFACTS_DIR/pi_sessions"` co-locates sessions with agent artifacts and guarantees cross-workspace mobility.
   - **Instruction Delivery**: Use Pi's `--append-system-prompt <path>` combined with `-nc` (`--no-context-files`). This delivers SASE's memory-built instruction bundle while suppressing native uncoordinated reads of `AGENTS.md` and `CLAUDE.md`, maintaining parity with the `instructions-per-invocation` decision.

3. **Phase 3: Mechanical Invariant Enforcement (`sase-pi` Extension)**
   Package a bundled TypeScript extension loaded via `-e`:
   - Expose `sase_final` as a typed tool that returns `{ terminate: true }` to gracefully stop the agent loop.
   - Attach a `tool_call` interceptor to fail-safe block raw `git commit`, `git push`, and `gh pr create` calls, advising the agent to use host-managed completion.
   - Attach an `agent_before_settle` hook that verifies whether a final declaration was recorded, injecting a single continuation prompt if the agent forgot to declare.
   - Enforce `helpers-return-roots-declare` by checking a root environment token to deny finalization by native subagents.

4. **Phase 4: Tooling, Catalog & TUI Integration**
   - Add Pi to `src/sase/llm_provider/models.yml` (tier defaults: `large: claude-3-7-sonnet`, `small: claude-3-5-haiku`).
   - Implement `llm_install_metadata()` for `@earendil-works/pi-coding-agent` via `npm`, integrating with `sase agent-cli install pi` and `sase doctor`.
   - Map SASE's 7 canonical effort levels (`none` -> `off`, `minimal`..`max` 1:1) to `--thinking <level>`.
   - Assign TUI status color `#8B5CF6` and interactive menu shortcut key `p`.

---

## 2. Artifact and Turn Registration

The complete report has been written and durably registered in the SASE artifact store:
- **Absolute Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/pi_llm_provider_implementation__gem.md`
- **Artifact Label**: `research:202610/pi_llm_provider_implementation__gem.md`
- **Artifact Reference**: `file:explicit:a91e5e54fc6c0da2ede615e5`
- **Final Declaration**: Submitted and accepted via `sase final submit` for host-owned commit.
