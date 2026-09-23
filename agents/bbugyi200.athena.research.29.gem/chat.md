# Chat History - ace-run (research.29.gem)

- **TIMESTAMP:** 2026-09-22 12:37:15 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.29.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_122509.md`

## Prompt

%id(gem, clan=research.29)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.29.cld`, `research.29.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? Note that I had some agents do some research on this issue yesterday but I
don't think the research swarm finished (feel free to review those research files for
inspiration, but make sure to verify any claims you intend to use in your own research).
End your analysis with a recommended solution. 
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

# SASE Headless Agent Long Commands, Internal Monitors, and Early Exits: Root Cause Audit & Solution

**Researcher:** `research.29.gem` (Independent Investigation)  
**Report File:** [`headless_agent_monitor_and_long_command_early_exits__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/sase/repos/research/202609/headless_agent_monitor_and_long_command_early_exits__gem.md)  
**Durable Artifact Snapshot:** `research:202609/headless_agent_monitor_and_long_command_early_exits__gem.md` (`file:explicit:87b1d16e3e6c6642ed5ed3a4`)  
**Final Declaration:** Accepted for `commit` (`sdd:research`).

---

## 1. Executive Summary & Verdict

The user hypothesis was:
> *"sase agents are constantly running commands that take a long time to finish and then running some kind of internal monitor or something and dying. I think this is likely happening because these agents don't understand that they are running in headless mode and thus will not have another turn and cannot use certain skills / internal tools."*

### Key Finding: Three Distinct Behaviors Masquerading as the Same Symptom
The diagnosis confirms the user's intuition is **partially correct**, but what appears as a single issue ("running a long command, monitoring, and dying") is actually the convergence of **three separate mechanisms**:

```
                               ┌─────────────────────────────────────────────────────────────┐
                               │  User Observes: "Ran a long command, monitored, and died"   │
                               └──────────────────────────────┬──────────────────────────────┘
                                                              │
                       ┌──────────────────────────────────────┴──────────────────────────────────────┐
                       ▼                                                                             ▼
       ┌──────────────────────────────────────────────┐              ┌──────────────────────────────────────────────┐
       │   Failure Mode 1: Silent False Success       │              │   Failure Mode 2: Destructive Monitor Loops  │
       │   (The Headless Misunderstanding)            │              │   (Designed Termination + Cancel-and-Restart)│
       ├──────────────────────────────────────────────┤              ├──────────────────────────────────────────────┤
       │ • Harness backgrounds command (>10s in agy). │              │ • Agent starts verification inline.          │
       │ • Harness injects "stop calling tools & wait"│              │ • Command is slow (just check takes 15-45m). │
       │ • Agent obeys, writes "waiting...", and ends.│              │ • Agent aborts in-flight command (wasting 30m│
       │ • Headless runner kills task & exits 0.      │              │ • Agent runs `sase monitor start` to handoff.│
       │ • Host marks SUCCESS because git tree clean! │              │ • `sase monitor start` intentionally SIGTERMs│
       │ • Result: Work lost, bead stuck IN_PROGRESS. │              │   the agent runner to transfer execution.    │
       │ • Active in agy (e.g. research.24.gem,       │              │ • Monitor fails -> new agent restarts suite  │
       │   sase-14t.3); historical in Claude pre-Sep15│              │   from 0 -> chains of 5-15 hops (sase-m4).   │
       └──────────────────────────────────────────────┘              └──────────────────────────────────────────────┘
```

1. **Silent False Success (The True Headless Misunderstanding):**
   - Active today in **Antigravity (`agy`)**.
   - `run_command` in `agy` has a hardcoded 10-second blocking timeout (`WaitMsBeforeAsync` limit 10,000 ms). Any command taking >10s is forced into the background.
   - agy's harness injects a system prompt instruction: *"YOU MUST TAKE ONE OF THE FOLLOWING TWO ACTIONS: A) proceed to other work or B) update the user and end the turn. DO NOTHING ELSE."*
   - In interactive mode, this relies on a reactive event loop to resume. In SASE's headless print mode (`agy run --print`), the runner sees the agent idle, waits a 5-second grace period, **SIGKILLs all background child tasks**, and exits with code 0!
   - Because `declaration_store.py` only requires declarations when uncommitted git changes exist (`submission_required = bool(repository_obligations)`), an agent that stopped halfway on a clean tree is marked by SASE as **`SUCCESS` / `completed`**. The command was terminated, the report was never written, and the phase bead was abandoned.
   - **Live Confirmation:** We encountered this exact trap twice in this session (`task-36` and `task-107`) and only survived by actively defying the harness instruction to continuously poll `manage_task(Action='status')`.

2. **Designed Monitor Handoffs Killing the Agent by Design (Cancel-and-Restart Waste):**
   - Agents are not using internal LLM tools to monitor; they are invoking SASE's own CLI command: `sase monitor start`.
   - `sase monitor start` drops `.sase_monitor_pending` and executes [`kill_agent_runner_group()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/main/utils.py#L60-L91), sending `SIGTERM` to the agent runner's process group. The agent is supposed to "die" to yield to a detached supervisor.
   - The tragedy is **Cancel-and-Restart**: `lint_and_test.md` tells agents: *"just check may be run inline, but hand it to a monitor the same way whenever it is taking a long time."* Because `sase monitor` cannot adopt an in-flight command, an agent running `just check` inline for 20 minutes aborts the process and restarts it from second 0 under a monitor. If the check fails, the next agent fixes 1 line and re-monitors, creating chains of 5 to 15 monitor hops (e.g. `sase-m4.land` had **9 consecutive failed monitors**).

3. **Output Concealment via Block Buffering (`| tail -n N`):**
   - Agents run `sase tool run check 2>&1 | tail -n 6`. Standard Unix pipes buffer in 4 KiB blocks on non-TTYs, and `tail` does not output until stream termination.
   - Audited live during this turn: agent `sase-165.6.f0--code` (Muse) has been running `sase tool run check 2>&1 | tail -n 6` for **over 80 minutes** without emitting a single byte of stdout. The agent and user perceive the process as completely frozen.

---

## 2. Telemetry & Live Case Evidence

Across 499 runs audited between September 20 and 22:
- **`research.24.gem` (Sep 21):** Ran `time ./scripts/check.sh clippy`. Backgrounded at 10s. agy logged: `root agent idle; waiting up to 5s for 1 background task(s) ... terminating 1 background task(s) on exit`. SASE recorded `Agent completed with status: SUCCESS` in 6m37s. The report was never written and the entire research swarm stalled.
- **`sase-14t.3` (Sep 20):** Ran `sase doctor`. Backgrounded at 10s. Replied *"Waiting for sase doctor to complete"*. agy exited 0. `finalizer_result.json` recorded `commit: success` with 0 attempts and 0 evidence. The phase bead was left abandoned in `IN_PROGRESS`.
- **`sase-m4.land` (Codex):** A single family produced a cascade of 9 failed monitors (`mon` through `mon-8`), re-running the entire test suite on every hop.
- **Claude:** Suffered from native backgrounding prior to Sep 15 (`bdda3bdf1`). Completely cured by setting `CLAUDE_CODE_DISABLE_BACKGROUND_TASKS=1`, `--disallowedTools ScheduleWakeup`, `BASH_MAX_TIMEOUT_MS=14400000` (4 hours), and stream-level wait-state classifiers.

---

## 3. Detailed Root Causes

1. **Harness Asynchrony Schema:**
   `agy` 1.2.8 exposes no CLI flag or environment variable to disable backgrounding or allow synchronous command execution past 10 seconds.
2. **SASE agy Classifier Failure:**
   In [`src/sase/llm_provider/agy.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/llm_provider/agy.py#L213-L238), `_looks_like_no_progress()` requires `dominated_by_intentions AND (has_wait_signal or low_substance)`. If an agent writes a detailed paragraph explaining what command it is waiting for (>70 words, <2 future mentions), `dominated_by_intentions` evaluates to `False`, so the wait signal is ignored and the output is accepted as valid progress. Furthermore, structural trajectory extraction is completely bypassed on 1.2.8 because [`_SUPPORTED_AGY_TRAJECTORY_VERSIONS`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/llm_provider/_subprocess_agy.py#L24) is hardcoded to `{"1.0.10"}`.
3. **Host-Side Completion Loophole:**
   In [`src/sase/finalizers/declaration_store.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/finalizers/declaration_store.py#L217), `submission_required = bool(repository_obligations)`. A clean working tree requires no declaration. If an agent exits mid-task on a clean tree, SASE assumes success.
4. **Lack of In-Flight Adoption:**
   Neither `sase tool run` nor `sase monitor start` can adopt an existing process group. Shifting from inline execution to a monitor requires SIGKILLing the running command and starting over.

---

## 4. Recommended Solution

### Phase 0: Immediate Backstops (Zero Architectural Risk)
1. **Enforce Completion Obligations on Clean Trees:**
   Modify [`src/sase/finalizers/declaration_store.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/finalizers/declaration_store.py) so that any run with an assigned bead or registered research obligation requires a declaration. If it exits without a declaration or handoff marker, fail loudly as `incomplete` rather than recording `success`.
2. **Repair the `agy` Provider Layer:**
   - Rewrite `_AGY_PRINT_MODE_DIRECTIVE`: Instruct the agent that commands >10s are backgrounded and it **must** remain in the turn polling `manage_task(Action='status')` until completion.
   - Fix `_looks_like_no_progress`: If `has_wait_signal` is detected in the tail without completion tokens, classify as no-progress regardless of word count.
   - Update `_SUPPORTED_AGY_TRAJECTORY_VERSIONS` to support `1.2.*`.
3. **Prohibit `| tail -n N` on Long Commands:**
   Enforce via `lint_and_test.md` and CLI rules that verification commands must never be piped into `tail`.
4. **Up-Front Provider Guidance:**
   - **Claude:** Run `sase tool run check` inline (4-hour timeout allows it to complete reliably).
   - **Non-Claude (`agy`, `muse`, `grok`):** Start verification directly under `sase monitor start --profile verify -f <prepared-ref>` rather than starting inline and aborting.

### Phase 1: Mechanical, Lossless ToolRun Handoff (The Permanent Fix)
1. **Detached Supervisor ToolRuns (`sase-core`):**
   Move tool execution to the supervisor daemon. The ToolRun record in SQLite is the durable handle.
2. **In-Flight Monitor Adoption (`--adopt`):**
   Enable `sase monitor start` to adopt an existing, in-flight ToolRun matching the workspace and command digest without restarting it.
3. **Automated `--handoff-after <duration>`:**
   Add `--handoff-after` to `sase tool run`. If a command exceeds the provider threshold (e.g. 10m for Grok/Muse), it automatically creates a monitor, binds the in-flight process, and terminates the agent turn mechanically. The model never has to guess or make handoff decisions.

### Phase 2: Loop Governors & Verification Speedup
1. **Monitor Loop Governor:** Cap monitor chains at 3 consecutive failed verification attempts per family before requiring a gate or human escalation.
2. **Targeted Re-Verification:** Instruct monitor follow-up agents to execute only failing test slices before triggering the full suite.
3. **Prebuilt Rust Wheels:** Distribute prebuilt `sase_core_rs` wheels across workspaces via `SASE_CORE_WHEEL` to eliminate 15–20 minutes of per-workspace cargo rebuild overhead.

---
*The full independent research report has been saved to [`headless_agent_monitor_and_long_command_early_exits__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/sase/repos/research/202609/headless_agent_monitor_and_long_command_early_exits__gem.md) and registered under durable artifact reference `file:explicit:87b1d16e3e6c6642ed5ed3a4`.*
