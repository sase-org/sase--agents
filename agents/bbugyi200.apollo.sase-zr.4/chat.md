# Chat History - ace-run (sase-zr.4)

- **TIMESTAMP:** 2026-09-14 09:42:59 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-zr.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-zr, bead=sase-zr.4)
%model:@medium
%auto
%w:sase-zr.2
%w(bead=sase-zr.2)
Can you complete the work for bead sase-zr.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zr.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zr.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zr.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead details for sase-zr.4.

Good, no epic-symbol entries to worry about. Now let me open the sase-telegram repo and check the durable-approval-publication phase (sase-zr.2) for context on the shared API that was built.

Now let's look at the executor.py to see how `execute_gate_selection` integrates this, and understand the "submission" API that's meant for interactive/detached callers (e.g. CLI `--no-detach` vs detached).

While that agent researches the shared submission API, let me look at the current Telegram repo structure to understand the existing code that needs to change.

Let me check on the research agent's findings before proceeding further.

Now let's look at the main loop function and the `main()` entry point plus the shared-handled cleanup logic near the end.

This gives a clear model for the "durable delivery record" pattern the plan calls for. Let me check on the research agent now.

I now have a complete picture. Here is the structured report.

## 1. CLI: `sase gate answer` (`src/sase/notification_gates/cli_answer.py`, parser in `src/sase/main/parser_gate.py`)

- Flags registered at `src/sase/main/parser_gate.py:140-156`: a mutually-exclusive group with `-d/--detach` and `-D/--no-detach`.
- Effective-detach logic: `_effective_detach()` at `cli_answer.py:253-265`. Explicit `--detach`/`--no-detach` always win; if neither is given, **gate-shell-backed** gates default to detached, ordinary gates default to synchronous (today's behavior).
- Detached path: `_submit_detached_answer()` at `cli_answer.py:268-328`. It does **not** call `execute_gate_selection` itself — it re-invokes the **same CLI command** with `--no-detach --json` as `argv` via `submit_proc_request(ProcSubmitRequest(argv=["sase","gate","answer","--id",...,"--kind",...,"--no-detach","--json"], origin=GATE_ANSWER_DETACH_ORIGIN, operation=GATE_ANSWER, operation_payload=payload, ...))` (`cli_answer.py:295-314`). Resolved args (option ids, input_data, option_inputs, feedback, retry) travel through the **operation-request sidecar**, not argv, so the child re-parses the request payload rather than the flags.
- It returns immediately with `{"detached": True, "proc_id": proc.proc_id, "status": "submitted", ...}` (`cli_answer.py:315-328`) — the parent CLI invocation never blocks on `execute_gate_selection`.
- The synchronous path (`--no-detach`, or default for non-shell gates) calls `execute_gate_selection` directly at `cli_answer.py:178-187` and blocks until it returns.
- Supervision terminology: `submit_proc_request` (`src/sase/procs/service.py:72`) reserves a "proc-shell" row (`ProcReserve`, `src/sase/procs/store.py`) then calls `spawn_detached_supervisor()` (`src/sase/procs/spawn.py`) which forks a **detached supervisor process** that owns the child's lifecycle even after the submitting client exits. The supervisor sets `env["SASE_PROC_ID"] = proc.proc_id` on the child it launches (`src/sase/procs/supervisor.py:384`, also `legacy_supervisor.py:98`; the env var name is `PROC_ID_ENV = "SASE_PROC_ID"` in `src/sase/ops/models.py:15`).
- That env var is read back by `accept_gate_decision` (`src/sase/notification_gates/decision.py:179`: `execution_owner = os.environ.get("SASE_PROC_ID", "").strip()`), which records which proc row is executing the gate in the durable decision receipt.

## 2. ACE (`src/sase/ace/tui/actions/agents/_notification_gate_execution.py` and `_notification_plan_gate.py`)

- **Generic/neutral gates** (`_notification_gate_execution.py:41-114`, `submit_gate_execution_task`): builds a `GateSubmission` dataclass (id, feedback, input_data, retry, option_inputs) and calls `app._submit_durable_proc(sase_argv("gate","answer","--id",request_id,"--kind",request_kind,"--json"), operation=GATE_ANSWER, request=durable_request_payload(...), ...)`. Notably it does **not** pass `--detach`/`--no-detach`; it relies entirely on ACE's own durable-proc submission layer rather than on the CLI's own detach flag.
  - `app._submit_durable_proc` is implemented at `src/sase/ace/tui/actions/_proc_action_submission.py:35` and, via `src/sase/ace/tui/durable_submit.py:66-105` (`submit_durable_proc_request`), builds a `ProcSubmitRequest` and calls the **same** `submit_proc_request` from `src/sase/procs/service.py`. So ACE spawns a genuine detached `sase gate answer ... --json` **subprocess** as a supervised proc-shell, gets back a `DurableSubmitHandle(proc_id, operation, result_path)` (`durable_submit.py:19-24`), and returns to the TUI event loop immediately; completion is observed asynchronously via `ObservedProc`/`on_complete` callbacks, not by blocking.
- **Plan/generic-plan gates** (`_notification_plan_gate.py:66-144`, `submit_neutral_plan_response`): different mechanism — it uses `app._submit_session_worker("plan-gate", work, ...)` where `work()` calls `execute_plan_approval_response(...)` (from `src/sase/plan_approval_actions.py`, which itself calls `execute_gate_selection`) **in-process**, inside a Textual background worker/thread, not a separate OS process. Blocking happens off the UI thread but still inside the ACE process.

So ACE has two distinct patterns: neutral/custom gates → detached OS subprocess via the durable proc queue; plan gates → in-process async worker thread. Both return control to the TUI immediately, but only the former is a truly separate, detached process that survives ACE exiting.

## 3. Generic Python-level "submit + supervised background proc" API

Yes: `submit_proc_request(request: ProcSubmitRequest, *, after_spawn=None, after_ack=None) -> Proc` in `src/sase/procs/service.py:72-159`. This is the one, generic, non-CLI-subprocess-only API: it reserves a proc row (`reserve_proc`/`ProcReserve`, `src/sase/procs/store.py`), writes an optional operation-request sidecar (`_write_operation_request`, `service.py:428-439`, via `sase.ops.write_operation_request`), then `spawn_detached_supervisor()` (`src/sase/procs/spawn.py`) and returns the settled `Proc` (with `.proc_id`) as soon as the supervisor acknowledges startup — it does **not** wait for the child command to finish.

`ProcSubmitRequest` (`src/sase/procs/request.py:15-54`) is the typed request: `argv`, `label`, `cwd`, `origin`, optional `operation`/`operation_payload`, `result_path`, `concurrency_keys`, `workspace_claim`, etc.

However, this API is **argv-based**: both CLI (`cli_answer.py:295-314`) and ACE (`ace/tui/durable_submit.py:66-105`) use it by constructing `argv=["sase","gate","answer",...]` — i.e. they still spawn a `sase` **subprocess** that re-enters `cli_answer.py`, which in turn calls `execute_gate_selection` synchronously inside that child process. There is **no** gate-answer-specific Python wrapper (e.g. `submit_gate_answer_detached(...)`) that skips the CLI re-entry and directly hands `execute_gate_selection`'s arguments to a background proc without going through argv/CLI parsing. A caller like Telegram wanting this today would have to build its own `ProcSubmitRequest(argv=["sase","gate","answer",...])` and call `submit_proc_request` directly (same pattern CLI/ACE use), or a new thin Python wrapper would need to be added — none currently exists in `src/sase/procs/`, `src/sase/core/`, or `src/sase/gate_shell/`.

**Important existing gap found**: Telegram's actual current implementation does **not** use `submit_proc_request` at all. `resolve_gate_response()` in the linked `sase-telegram` repo (`src/sase_telegram/inbound.py:348-426`) calls `execute_gate_selection` **directly and synchronously** (`inbound.py:402` / `:412`, `source="telegram"`), exactly like the "mobile" bridge (`src/sase/integrations/_mobile_notification_actions.py:47-125`, `execute_mobile_gate_action`, which also calls `execute_gate_selection` directly at line 93). This function is called from the single-process Telegram poll loop at `sase-telegram/src/sase_telegram/scripts/sase_tg_inbound.py:889`, so **today Telegram fully blocks its inbound poll loop** on slow gate execution — it has not yet adopted the detach pattern CLI/ACE use.

## 4. `%auto` short-circuit

`%auto` does **not** call `execute_gate_selection` through any detached/background path — it calls it directly and synchronously, deliberately, in `_resolve_auto_gate()` at `src/sase/notification_gates/service.py:213-250`:
```python
execution = execute_gate_selection(
    paths.root, selected_option_ids, adapter.automatic_input(spec),
    source="auto_resolution", **execution_kwargs,
)
```
The comment right after (`service.py:~247-254`) is explicit about why this is safe: *"creation-time auto-resolution always runs inline in the creating agent's own process/turn, which already owns the lane and workspace (and ... the family's runner-slot claim) — never a separate answering process. No follow-up may launch and no claim may be disposed of here."* — followed by `settle_gate_shell(..., creator_live=True)`.

The question-gate variant of this is in `src/sase/axe/run_agent_exec_questions.py:107-226` (`handle_questions_marker`): it passes `auto=is_auto_approve_active()` (from `src/sase/main/plan_approve_handler.py:195`) into `create_question_gate_shell(...)`; when the gate auto-resolves, `creation.should_handoff` is `False` and the runner continues in-process via `_continue_after_auto_answered_question()` (`run_agent_exec_questions.py:229-…`) rather than doing a gate-marker handoff/wait.

So: yes — `%auto` accepts that `execute_gate_selection` blocks, on the premise that the call is already happening inside a background/supervised agent process (an axe-run agent turn), so there's nothing further to detach from.

## 5. Submission-result type distinct from `GateExecutionResult`

`GateExecutionResult` is defined at `src/sase/notification_gates/model_results.py:77-83`:
```python
@dataclass(frozen=True)
class GateExecutionResult:
    """Result of resolving a terminal gate choice."""
    response: dict[str, Any]
    already_completed: bool = False
```
That's the only completed-response type. **No dedicated "submission result" dataclass exists yet.** The closest things today:
- CLI's `_submit_detached_answer` returns a bare, untyped `dict[str, Any]` (`cli_answer.py:315-328`) with ad hoc keys `detached`, `proc_id`, `status: "submitted"`, etc. — not a shared/reusable type.
- ACE's `DurableSubmitHandle(proc_id, operation, result_path)` in `src/sase/ace/tui/durable_submit.py:19-24` is a generic durable-proc handle (used for any durable operation, not gate-answer-specific).

So the plan's stated intent — "expose a separate submission result for interactive callers" — is **not yet implemented**; there is currently no `GateSubmissionResult` (or similarly named) type anywhere under `src/sase/notification_gates/` or `src/sase/procs/`.

Now let's check `edit_message_reply_markup`'s signature and existing tests around `_dismiss_gate_callback` / `_answer_resolved_callback` for keyboard cleanup, to design the fix consistently.

Now I have a clear design. Let me implement the source changes, starting with `inbound.py`.

Now let's replace the `resolve_gate_response` function with the new submission-based implementation.

Now let's add the keyboard-cleanup-retry constants and helpers, and update `_dismiss_gate_callback`. Let's view the exact current code around it first (already have it from before but let me re-fetch fresh context).

Now let's view and rewrite `_dismiss_gate_callback` and add the retry helpers.

Now let's add the gate-completion delivery scan. Let's look at the `_send_ready_update_completions` area again to insert the parallel gate-completion functions nearby.

Now let me insert the gate-completion delivery functions right after `_shorten_home`.

Now let's add the top-level imports for `get_proc` and `TERMINAL_PROC_STATUSES`.

Now let's wire these into `main()`.

Let me update `submit_gate_response` to restore the fast already-answered/cancelled pre-check.

Let's run linting to catch syntax/type issues early.

Good, syntax is valid. Now let's run the test suite to see what breaks so I can fix tests systematically.

Good, plenty of disk space now. Let's run `just install`.

Now let's rewrite `test_gate_shell_settlement.py` to reflect the new submission-based behavior.

Good, it's actively building the Rust core in release mode — this will take a while. Let's continue with other work while it runs. Let's check the many `_handle_callback` end-to-end tests to see if the autouse fixture I added will make them pass, or if there are edge cases (e.g., tests that check keyboard removal calls).

Still building (release mode compile of the Rust core takes a while). Let's continue reviewing other parts of the test suite while waiting — particularly checking `test_inbound.py` for anything related to gate flows I may have missed, and double-checking my `sase_tg_inbound.py` edits compile cleanly with a quick static check via pyflakes-style grep for undefined names.

Good. Let's check on the background build progress.

Good, `main()` looks structurally intact. Let's view the top of `main()` where I added the new calls, to confirm formatting/correctness.

Good. Now let's wait for the background install to finish before running tests.

This all looks correct. Now let's wait for the background install/build to complete.

`just install` finished successfully. Let's run the relevant test files.

Now let's verify the other failure is truly pre-existing and unrelated to my changes, by checking it on a clean checkout of sase-telegram (stash my diff) or checking if `sase.monitor.store_lane` is broken independent of my edits.

Now let's run the new completion/keyboard-cleanup tests and the full test_inbound.py file.

All 10 new tests pass. Now let's run the full `test_inbound.py` suite to make sure nothing else broke.

Confirmed pre-existing and environment-specific. Now let's run the full test suite.

All pre-existing failures confirmed unrelated. Now let's run lint checks.

All lint checks pass. Let's run `just check` (lint + test combined, the canonical gate) as the final verification.

This is a substantial, complete change. Let's do a final review of the full diff to ensure everything is clean and coherent before closing.

This all looks clean and consistent. Let's do a final check of the epic-symbols requirement before closing.

Now let's close the bead with a verification note.

Bead closed successfully. Now let me invoke the SASE final declaration to properly end this turn.

The final declaration was accepted, committing the sase-telegram changes.

## Summary

Completed bead **sase-zr.4** (Decouple Telegram acknowledgements and cleanup from gate execution) in the sase-telegram repository:

- Replaced the synchronous `execute_gate_selection` call in `inbound.resolve_gate_response` with a durable submission through the shared supervised-proc API, mirroring `sase gate answer --detach` — so slow option commands, archive publication, and successor launch no longer block Telegram's inbound poll loop or delay later updates in the same batch.
- Gate-shell settlement is now handled entirely by the reinvoked CLI process (already tested in `sase`), simplifying Telegram's own code.
- Added durable completion/error delivery (`_send_ready_gate_completions`) so the real outcome reaches the user even after a callback popup has expired.
- Fixed the keyboard-cleanup durability bug the plan called out: a failed Telegram edit no longer silently drops track of a stale keyboard — it's now retried across ticks via a tombstone file.
- Verified with `just lint` (clean) and `just check` (594 passed; 4 pre-existing failures confirmed unrelated via `git stash` on a clean checkout, recorded as PROPOSED FOLLOW-UP notes on the bead).

The bead is closed, and the sase-telegram repository changes were committed via the SASE finalizer.
