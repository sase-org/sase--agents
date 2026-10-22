# Chat History - ace-run (research.47.gem)

- **TIMESTAMP:** 2026-10-09 13:21:22 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.47.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_130507.md`

## Prompt

%id(gem, clan=research.47)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.47.cdx`, `research.47.cld`, `research.47.grk`, `research.47.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

A
number of sase agents just failed on this machine with the following error:
`ImportError: cannot import name 'auto_launch_prefix' from 'sase.monitor.continuation_delivery'`

- This error was clearly caused by updating sase while agents were running, which is
  something I would like to support.
- I would like to start automatically detecting errors like this and attempting to
  automatically resolve the issue by dismissing and re-launching the sase agent that
  failed.
- We should try to restart an agent exactly once when a detected error pattern matches.
  Think hard about which error patterns we should check for.
- This operation should be very similar to what happens when the user selects a failed
  agent on the "Agents" tab, uses the `,x` keymap to dismiss and edit it, and then
  submitting the prompt (e.g. via the `<ctrl+g><enter>` keymap) that loads in the prompt
  input widget without modifying it.
- We should send an excellent and thorough sase notification to the user when we restart
  a failed agent like this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

# Research Report: Resilient Agent Execution & Auto-Relaunch on Live SASE Updates

**Report Artifact:** [`live_update_agent_failure_autorestart__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/live_update_agent_failure_autorestart__gem.md)  
**Registered Artifact Reference:** `file:explicit:c21ce6ccdf30308f9694092c` (`research:202610/live_update_agent_failure_autorestart__gem.md`)  
**Researcher:** `research.47.gem`

---

## 1. Executive Summary & Root Cause Analysis

### 1.1 Root Cause of `ImportError: cannot import name 'auto_launch_prefix' from 'sase.monitor.continuation_delivery'`
In development environments, SASE runs via an editable install (`pip install -e`), where Python loads code directly from the working repository checkout (`src/sase/`). 

Python resolves imports lazily and caches loaded module objects in `sys.modules`:
1. When an agent runner or monitor boots, initial modules are loaded into memory. At that time (prior to commit `61febdcc6`), `sase.monitor.continuation_delivery` had already been loaded into `sys.modules` without `auto_launch_prefix`.
2. SASE was updated via `git pull` or `just install-dev`. Commit `61febdcc6` added `def auto_launch_prefix` to `continuation_delivery.py` and updated `src/sase/monitor/followup.py` with `from .continuation_delivery import auto_launch_prefix`.
3. When the in-flight agent completed its main turn and reached monitor settlement or follow-up launch (`launch_followup_agent`), it imported `followup.py`.
4. `followup.py` looked up `sase.monitor.continuation_delivery` in `sys.modules`. Python returned the **stale in-memory module object from before the commit**, which lacked `auto_launch_prefix`, raising the fatal `ImportError`.

---

## 2. Critique of the Proposed Plan

### 2.1 Strengths
* **Automates Proven Manual Remediation:** Automating the user's manual `,x` (kill-and-edit) followed by `<ctrl+g><enter>` (relaunch verbatim) directly mirrors established operator behavior.
* **Strictly Bounded Blast Radius:** Restricting auto-restarts to **exactly once** guarantees the system cannot enter an infinite restart loop if an update introduces a genuine syntax error or breaking change.
* **Frictionless Developer Experience:** Eliminates babysitting of the Agents tab when pulling or updating branches while agents run.

### 2.2 Critical Risks & Recommended Adjustments
1. **Work Loss & State Contamination:**
   * *Risk:* If an agent has already run for 30 minutes, modified 5 files, and drafted a plan before crashing on follow-up delivery, a blind restart from the initial prompt in a dirty workspace can cause merge conflicts or overwrite uncommitted work.
   * *Adjustment:* Distinguish between **Phase 1 failures** (bootstrap / pre-edit failures, where a clean workspace wipe and restart is 100% safe) and **Phase 2 failures** (mid-turn failures after file modifications, where `#fork:<agent_name>` or clean VCS checkout restoration should be preferred).
2. **The "Broken Build" Trap:**
   * *Risk:* If a git update has a syntax error, broken dependency, or uncompiled Rust extension (`sase_core_rs`), restarting will immediately fail again.
   * *Adjustment:* Ensure retry exhaustion is recorded in durable state (`agent_meta.json` with `auto_restart_attempt: 1`) so that a second failure remains in `FAILED` status with a clear diagnostic explanation.
3. **Thundering Herd / Restart Storms:**
   * *Risk:* If 15 agents fail simultaneously upon an update, restarting all 15 immediately causes workspace contention and LLM rate-limiting.
   * *Adjustment:* Stagger relaunches through the existing runner-slot queue (`wait_for_runner_slot`).

---

## 3. Error Pattern Catalog

To prevent false positives (such as an agent running a test suite in a client repository that fails with `ImportError`), pattern detection must enforce a **Dual-Witness Rule**:

### 3.1 Targeted Error Signatures
1. **Direct Import & Missing Symbols:**
   * `ImportError: cannot import name '<sym>' from 'sase\.<mod>'`
   * `ModuleNotFoundError: No module named 'sase\.<mod>'`
2. **Attribute Skew on Stale Modules:**
   * `AttributeError: module 'sase\.<mod>' has no attribute '<sym>'`
3. **Call Signature Drift:**
   * `TypeError: <func>() takes N positional arguments but M were given` (within `sase.*` call frames)
4. **Bytecode / Packaging Desynchronization:**
   * `ValueError: bad marshal data` or `EOFError` during import
5. **Rust Core Extension ABI Skew:**
   * `ImportError: cannot import name '...' from 'sase_core_rs'` or `AttributeError: module 'sase_core_rs' has no attribute '...'`

### 3.2 Dual-Witness Verification (Zero False Positives)
An error is classified as an **Auto-Restartable Update Skew** only if **all three** criteria are met:
1. **Exception Signature Match:** Matches one of the patterns above.
2. **Internal Framework Call Boundary:** Both the call frame and the raise frame originate inside the internal `sase/` package directory (excluding child tools and subprocesses).
3. **Source Skew Witness:** Concrete evidence that code on disk moved:
   * **Signal A:** `git rev-parse HEAD` of the SASE source checkout differs from the runner's boot-time SHA (leveraging `src/sase/axe/source_skew.py`).
   * **Signal B:** The file in the traceback has an `mtime` strictly greater than the agent's `run_start_time`.

---

## 4. System Design: Auto-Dismiss & Relaunch Pipeline

### 4.1 Hybrid Architecture: "Runner Self-Recovery + ACE Safety Net"
* **Primary Layer (In-Runner Self-Recovery):**
  When `src/sase/axe/run_agent_runner.py::main()` catches an unhandled exception, it runs `evaluate_auto_restart()`. If eligible:
  1. Writes `done.json` with `outcome: "failed"`, `status: "FAILED (RETRIED)"`, and `retry_error_category: "source_update_skew"`.
  2. Atomically transfers the workspace claim to prevent race conditions.
  3. Reconstructs the prompt using `prepare_kill_and_edit_prompt()` from `src/sase/agent/relaunch_prompt.py` (preserving `%id` name reuse, session linkages, and clan tags).
  4. Spawns a detached child process with a fresh Python interpreter (`spawn_detached_child()`).
  5. Emits an enriched notification (`notify_agent_auto_restarted()`) and cleanly exits.
* **Secondary Layer (ACE TUI Watcher):**
  If an agent crashes prior to runner bootstrap (e.g. top-level syntax error before `main()`), the ACE polling engine (`_loading_refresh_polling.py`) detects the dead agent with an update-skew signature and automates the `,x` dismissal and prompt re-launch.

---

## 5. Notification & UX Design: Intuitive, Reliable, and Beautiful

### 5.1 SASE Notification Model
* **Sender:** `agent.recovery`
* **Icon:** `🔄`
* **Color Accent:** `#38BDF8` (Sky Blue)
* **Tags:** `["recovery", "auto-restart", "agent", cl_name]`
* **Action:** `JumpToAgent` (pressing `<enter>` on the notification instantly selects the newly running agent in ACE)

```text
┌────────────────────────────────────────────────────────────────────────┐
│ 🔄 Auto-Restarted Agent @bbugyi200.athena.0lj on sase-org              │
│ Cause: Framework update skew (ImportError: auto_launch_prefix)         │
│ Source checkout updated (61febdc → 89a10ce) while agent was running.  │
│ Action: Dismissed failed runner (PID 48102) & relaunched with preserved│
│         prompt, session identity, and workspace claim.                 │
│ New Runner: PID 49201 in Workspace #19 • Attempt 1/1                   │
└────────────────────────────────────────────────────────────────────────┘
```

### 5.2 ACE TUI Visual Experience
* **Toast Notification:** Sky blue banner: `Auto-restarted @bbugyi200.athena.0lj (code update skew)`.
* **Agents Tab Roster:** Relaunched row displays an amber/cyan badge: `RUNNING [AUTO-RETRY 1/1]`. Old failed row is cleanly dismissed to keep the active view uncluttered.
* **Prompt Panel Header:** Restarted agent displays a recovery header acknowledging the prior crash and showing exact git commit provenance.

---

## 6. Recommended Prevention Enhancements

In addition to reactive recovery (the cure), proactive prevention should be added:
1. **Eager Preloading:** Expand `_PRELOAD_PACKAGES` in `src/sase/axe/source_skew.py` to include `sase.monitor` and `sase.turns` so lazy imports during follow-up delivery do not touch disk mid-run.
2. **Milestone Re-exec:** Extend `src/sase/axe/run_agent_runner_refresh.py` to allow clean `os.execv()` reloads at clean step boundaries (e.g. before follow-up turn launches) if a HEAD change is observed.

---

## Artifact Registration Confirmation
The full research report has been written and registered in durable SASE artifact storage:
* **Report File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/live_update_agent_failure_autorestart__gem.md`
* **Artifact Snapshot:** `file:explicit:c21ce6ccdf30308f9694092c`
* **Label:** `research:202610/live_update_agent_failure_autorestart__gem.md`

Final declaration successfully submitted and accepted for finalizer `commit` (`repo-9bf900ad4f21` / `sdd:research`). The host will commit the declared work upon completion of this turn.
