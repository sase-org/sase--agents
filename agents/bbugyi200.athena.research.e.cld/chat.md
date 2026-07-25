# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 14:23:04 EDT
- **MODEL:** claude/opus
- **AGENT:** research.e.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_141316.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase I want to generalize the concept of plan / question /
launch notifications so all of them use the same structure and sase notification
constructor. We should use the existing `sase notify create` command for this,
which will need to be signifigantly enhanced I think. As a part of this change,
I intend to remove the (never used) dynamic `improve_plan` and `tester` family
member hooks (I'm not even sure how they work, but I'm pretty sure we will need
to do something about them to progress with this initiative).

Can you do some research to help me understand what this task entails? End your
analysis with a list of questions that, if answered correctly, would allow you
to confidently design and implement this functionality. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by exploring how notifications currently work in this repo, focusing on `sase notify create`, the plan/question/launch notification paths, and those `improve_plan`/`tester` hooks.

Let me dig into the notification system and the hook machinery in parallel.

Now let me read the core notification code and fan out research agents on the different notification paths.

I have the sender-side picture. Now let me fan out agents to trace each notification flow end-to-end, the hook machinery, and the Rust boundary.

I'll start by reading the senders file and then trace out from there.

Now let me find all call sites for the three senders.

I'll research this systematically, starting with the seed files and schema definitions.

Three distinct producers. Let me read each.

Now let me trace upstream callers and the TUI action handlers in parallel.

I'll research this systematically, starting with parallel searches across the key areas.

While those run, let me check the research directory conventions and the Rust core side.

The TUI side lives in `actions/agents/`. Let me read the modal handlers and the dispatcher.

Now let me read the parser and handler files.

Now the question and launch handlers plus the response writer.

Let me read the launch approval action executor and the TUI modal flow dispatcher.

Now the skill file, models, and store layer.

The research sidecar is open at the path the user specified. Let me check the conventions and skim the closely-related prior research.

Now the hook/CLI triggers upstream. Let me look at the exec paths and hook handlers.

Now let me find the tests and the Rust-side schema mirror.

The plan/question flows are event-driven. Let me trace where those events originate.

This prior research doc is directly relevant — `improve_plan`/`tester` appear to be the "v2 north star" stubs. Let me read the v2 section and the plan-approval protocol details.

Let me check the Rust core repo availability, since the notification wire likely crosses that boundary.

Now let me read the docs, the approve-options modal state, and the remaining tests.

Now the request producers: skill CLI handlers and launch preview paths.

I have the Rust core checkout. Let me dispatch an agent to map the wire-level constraints there while the others finish.

I'll start by exploring the Rust core repo structure to find notification-related code.

While the agents work, let me search prior research and beads for anything already covering this initiative.

Found the notifications module. Let me read all of its files.

Now the wire definitions and pending actions.

Now the mobile module, the largest piece.

Now let me check the PyO3 bindings, gateway usage, and grep for action strings.

Critical detail spotted in the PyO3 layer. Let me check the gateway bridge and Python side now.

Let me read the pending-actions module directly — it's the central piece I'll need first-hand knowledge of.

The `_externally_handled` logic reveals a very regular pattern across all four gates. Let me check the question-summary special-casing, which no agent is covering.

Notably, `notify create` doesn't call `register_notification`. Let me check whether the store does that internally — that's a key gap.

Let me quantify how widely the per-action special-casing is spread — that's the core of what "same structure" would fix.

The special-casing spans 17 files. Let me look at the biggest offender — the TUI notification modal flow.

I've mapped the sender side and the duplication surface myself. Four research agents are still tracing the flows end-to-end, the `improve_plan`/`tester` hooks, the CLI surface, and the Rust wire. Here's what's already clear:

**The pattern is remarkably regular.** All four actionable notification types (`PlanApproval`, `UserQuestion`, `LaunchApproval`, `HITL`) are the same shape: a `response_dir` holding `<kind>_request.json` and `<kind>_response.json`, with the producer blocking on a poll of the response file. `pending_actions.py:308-345` hard-codes that identical logic four times.

**`sase notify create` is already closer than it looks.** `append_notification` (`store.py:113`) already calls `register_notification` internally, so a notification created via the CLI with `action="PlanApproval"` would already land in the pending-action store. The gap isn't capability — it's that `senders.py` bypasses the CLI with eight bespoke in-process constructors.

**The duplication is spread across 17 files**, and `question_summary.py:60-71` re-implements the filesystem state rules that `pending_actions.py` already owns.

I'll report back once the agents land.

Trace complete. Here is the full report.

---

# Three notification flows in `src/sase/notifications/senders.py`

## Headline correction: there are no hooks

The task premise (and the senders' own docstrings) says "hook". That is stale. **No Claude Code hook handler is involved in any of the three flows.** Grep for `ExitPlanMode`/`AskUserQuestion` finds only:

- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/llm_provider/claude.py:89` — `"provider_native_ask_tool": "AskUserQuestion"`, a template var
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/xprompts/skills/sase_questions.md:8` — "This replaces {{ provider_name }}'s native {{ provider_native_ask_tool }}"

The native tools are *disabled and replaced by skills*. So these two docstrings are misleading:

- `senders.py:205` — `"""Send a notification when Claude Code asks a user question via hook."""`
- `senders.py:20` (`notify_user_question` in-code comment context) — same framing

The real trigger mechanism for plan/question is a **marker file + SIGTERM self-kill**, and for launch it's a **plain CLI/skill call**.

---

## 1. Call sites and triggers

### `notify_plan_approval` — exactly one producer

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/llm_provider/_plan_utils.py:280` inside `handle_plan_approval()` (defined at `_plan_utils.py:196`).

Trigger chain (skill → CLI → marker → SIGTERM → runner):

1. Skill `sase_plan` runs `sase plan propose <file>` → `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/plan_propose_handler.py:15` `handle_plan_propose_command()`
2. Validates tier, prettier-formats, `move_plan_to_sase()` (consumes scratch file), writes `.sase_plan_pending` marker at `plan_propose_handler.py:90` with `{"plan_file", "original_file", "timestamp"}`, fsyncs
3. Touches `.ace_refresh_pulse` (`plan_propose_handler.py:105`) — a deliberate hack because `ArtifactWatcher` is non-recursive and would otherwise miss the marker three levels down
4. `kill_agent_runner_group(artifacts_dir)` — SIGTERMs the runner's process group
5. Runner wakes at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/axe/run_agent_exec.py:154` `read_and_delete_marker(..., ".sase_plan_pending")`, builds `kind="plan_submitted"` event (`run_agent_exec.py:163`), dispatches via `_handle_handoff_event` → `handle_plan_marker`
6. `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/axe/run_agent_exec_plan.py:171` calls `handle_plan_approval(event.payload.get("plan_file"), str(uuid.uuid4()), killed_check=was_killed, ...)`

**TUI-side consumers of `handle_plan_approval` (the TUI one, `actions/agents/_notification_modals.py:47` — different function, same name):**

- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agents/_notification_modal_flow.py:189` — via NotificationModal dismiss
- `_notification_modal_flow.py:88` — via `_jump_to_agent_notification` (direct keybind, skips the modal list)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/artifacts_plans.py:100` — Plans pane `a`/`r` keys
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agent_workflow/_prompt_bar_submit.py:182` and `:211` — re-entry after prompt-bar coder-prompt edit / cancel, carrying `PendingApproveState`

### `notify_user_question` — exactly one producer

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/axe/run_agent_helpers_questions.py:89` inside `handle_questions_flow()` (defined at `:40`).

Same marker/SIGTERM shape:

1. Skill `sase_questions` runs `sase questions '<json>'` → `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/questions_command_handler.py:41`
2. `_validate_questions()` (`:15`) enforces the schema, writes `.sase_questions_pending` at `questions_command_handler.py:81` with `{"questions", "timestamp"}`, fsyncs
3. `kill_agent_runner_group(artifacts_dir)` — **note: no `.ace_refresh_pulse` touch here**, unlike the plan path
4. Runner: `run_agent_exec.py:159` reads marker → `kind="questions_submitted"` (`:171`) → `handle_questions_marker`
5. `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/axe/run_agent_exec_questions.py:204` calls `handle_questions_flow(event.payload.get("questions", []), state.current_artifacts_dir, reacquire_runner_slot=..., run_started_at=...)`

**TUI consumers:** `_notification_modal_flow.py:191` (modal) and `:91` (jump keybind); plus the marker fallback at `_notification_modal_flow.py:125` → `open_user_question_modal_from_marker`.

### `notify_launch_approval` — exactly one producer

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_request.py:109` inside `create_launch_approval_request()` (`:73`).

Two entry points, **no marker, no SIGTERM, no runner involvement**:

- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/query_handler/_launch.py:49` — `sase run <prompt>` (skill `sase_run`). Gated at `:47` by `running_agent_context_requires_launch_approval()`, which is just `bool(os.environ.get("SASE_AGENT"))` (`launch_request.py:187`). Outside an agent, `sase run` launches directly at `_launch.py:62` with **no approval at all**.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/launch_handler.py:59` — `sase launch request` CLI

**TUI consumer:** `_notification_modal_flow.py:193` → `handle_launch_approval` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agents/_notification_launch_approval.py:47`). **Not** reachable from the `_jump_to_agent_notification` keybind — `_notification_modal_flow.py:68` filters to `("PlanApproval", "UserQuestion")` only.

---

## 2. The response protocol

### `response_dir` — three different roots, three different naming schemes

| Flow | `response_dir` | Constructed at |
|---|---|---|
| Plan | `sharded_path("plan_approval", session_id)` → `~/.sase/plan_approval/YYYYMM/<uuid4>/` | `_plan_utils.py:242` |
| Question | `sase_subdir("user_question") / session_id` → `~/.sase/user_question/<uuid4>/` (**unsharded**) | `run_agent_helpers_questions.py:70` |
| Launch | `sase_subdir("launch_requests") / request_id` → `~/.sase/launch_requests/<request_id>/` | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_preview.py:122` |

The `session_id` is a fresh `uuid4` in all three, but generated in different places: plan's is passed *in* by the caller (`run_agent_exec_plan.py:173`, `str(uuid.uuid4())`), question's is generated *inside* the flow (`run_agent_helpers_questions.py:69`), launch's `request_id` comes from `build_launch_preview_request`.

### Files in `response_dir`

| Flow | Request (writer) | Response (writer) | Extra |
|---|---|---|---|
| Plan | `plan_request.json` — `_plan_utils.py:261` | `plan_response.json` | `plan_approved.marker` (3rd state signal) |
| Question | `question_request.json` — `run_agent_helpers_questions.py:79` | `question_response.json` | `pending_question.json` marker in **artifacts_dir**, not response_dir |
| Launch | `launch_request.json` — `launch_preview.py:124` | `launch_response.json` | `launch_preview.md` (`launch_preview.py:125`) |

Constants: `LAUNCH_REQUEST_FILE`/`LAUNCH_PREVIEW_FILE`/`LAUNCH_RESPONSE_FILE` at `launch_preview.py:22-24`. Plan and question use **bare string literals** everywhere — no constants.

### Request JSON shapes

**`plan_request.json`** (`_plan_utils.py:255`):
```json
{"plan_file": "...", "session_id": "...", "timestamp": 1234.5,
 "member_options": [...], "default_member_ids": [...]}
```
(last two spread in from `plan_approval_member_request_payload(project=...)`)

**`question_request.json`** (`run_agent_helpers_questions.py:73`):
```json
{"questions": [{"question": "...", "options": [{"label": "..."}], "multiSelect": bool}],
 "session_id": "...", "timestamp": 1234.5}
```

**`launch_request.json`** (`launch_request.py:99-104`): the preview request plus `launch_request` (normalized payload), `requester` (env snapshot: `SASE_AGENT`, `SASE_AGENT_NAME`, `SASE_ARTIFACTS_DIR`, `SASE_AGENT_WORKFLOW_NAME`), and `dispatch` = `{"cwd": ..., "prompt": ...}`.

### Writers of the response

**Plan** — four distinct writers:
1. TUI: `_notification_modals.py:177` and `:237` via `write_workflow_action_response`
2. TUI feedback path: `_prompt_bar_submit.py:123`
3. CLI `sase plan approve`/`reject`: `plan_approve_handler.py:135`, `plan_reject_handler.py:79` → `execute_plan_approval_response` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/plan_approval_actions.py:87`, writes at `:133`)
4. Mobile/Telegram bridge: `_mobile_notification_actions.py:96`

**Question** — two writers:
1. TUI: `_notification_question_modal.py:134`
2. Mobile: `_mobile_notification_actions.py:200`

**Launch** — one writer, shared by everyone: `execute_launch_approval_response` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/launch_approval_actions.py:72`. Called from TUI (`_notification_launch_approval.py:152`), CLI (`launch_handler.py:123`), mobile (`_mobile_notification_actions.py:234`). This is the cleanest of the three.

All response writes use exclusive-create (`open("x")`) so a double-resolve raises `FileExistsError` → `conflict_already_handled` (`launch_approval_actions.py:169`, `_mobile_notification_actions.py:435`, `_notification_modal_responses.py:19`).

### Readers / pollers — **the biggest asymmetry**

**Plan**: `_plan_utils.py:311-400`. A blocking `while True` loop, `_POLL_INTERVAL = 0.5` (`_plan_utils.py:21`). Checks `killed_check()` each iteration, unlinks both `plan_response.json` and `plan_request.json` on consume, and **re-checks `get_auto_plan_approval_action()` inside the loop** (`:392`) so `%auto` set mid-wait still resolves.

**Question**: `run_agent_helpers_questions.py:122-146`. Blocking loop, hardcoded `time.sleep(0.5)` (`:146`) — no shared constant. Checks `was_killed()`. **Never unlinks the response** — it injects `_question_request_path`, `_question_response_path`, `_question_session_id` back into the dict (`:131-133`) for downstream consumers, and clears `pending_question.json` in a `finally` (`:148`).

**Launch**: **nothing in the codebase polls `launch_response.json`.** Grep confirms the only reads are existence checks in `pending_actions.py:341`. `_launch.py:57-59` prints the path and `sys.exit(0)`s. The "poller" is *the LLM itself*, instructed in prose at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/xprompts/skills/sase_run.md:100`: "The JSON output includes `response_file`. Poll that path until `launch_response.json` appears." Followed by `sase_run.md:114`: "If rejected, do not spawn anyway" — an *honor-system* enforcement, not a mechanical one.

### Response JSON shapes

**`plan_response.json`** — built at `_notification_modals.py:277` (TUI) / `plan_approval_actions.py:303` (CLI/mobile):
```json
{"action": "approve" | "epic" | "commit" | "reject",
 "feedback": "...",           // optional
 "commit_plan": true, "run_coder": true,
 "coder_prompt": "...",       // optional
 "coder_model": "...",        // optional
 "selected_member_ids": [...],// optional
 "epic_launch_owner": "host", // only when action=="epic"
 "saved_plan_path": "..."}    // added AFTER the fast write, _notification_modals.py:477
```
Parsed at `_plan_utils.py:332-388`. `"commit"` is a back-compat alias → `approve` + `run_coder=False` (`_plan_utils.py:363`).

**`question_response.json`** (`_notification_question_modal.py:120`):
```json
{"answers": [{"question": "...", "selected": ["label"], "custom_feedback": null}],
 "global_note": ""}
```

**`launch_response.json`** (`launch_approval_actions.py:137`):
```json
{"action": "approve"|"reject", "feedback": "...",
 "dispatch_status": "launched"|"failed", "launched_count": 1, "dispatch_error": "..."}
```
The dispatch fields are added by a **second, non-exclusive `_write_json_replace`** (`launch_approval_actions.py:82`, `:89`) after `dispatch_approved_launch_request` runs.

---

## 3. TUI action handlers

| action | handler | modal | required `action_data` |
|---|---|---|---|
| `PlanApproval` | `_notification_modals.py:47` `handle_plan_approval` | `PlanApprovalModal` (`:264`) | `response_dir`; reads `llm_provider`, `model`, `project_dir` (archive only) |
| `UserQuestion` | `_notification_question_modal.py:19` `handle_user_question` | `UserQuestionModal` (`:148`) | `response_dir` only |
| `LaunchApproval` | `_notification_launch_approval.py:47` `handle_launch_approval` | `LaunchApprovalModal` (`:79`) | `response_dir`, `request_id` |

Dispatch: `_notification_modal_flow.py:188-193`.

Notable per-handler details:

- **Plan** takes a third param `pending_approve_state` (`_notification_modals.py:50`) — the other two take only `(app, notification)`. It reads the plan tier off disk (`read_plan_tier`, `:90`) to preset `default_choice`, and parses `plan_request.json` for `member_options` (`:78`). Its `on_dismiss` handles five distinct result actions: `edit` (suspends TUI, runs `$EDITOR`), `feedback_requested`, `approve_prompt_edit`, `reject` (kills the agent, `:191`), and approve. It also runs a **background worker** (`:423`) for dismiss/persist/archive so the response write stays on the fast path.
- **Question** is the only one with a **notification-less entry point**: `open_user_question_modal_from_marker` (`:61`), used when the notification was dismissed but `pending_question.json` still exists. It passes `notification_id or str(question_response_path)` as the id (`:138`) — a synthetic fallback.
- **Launch** is the only one routed through the **task queue** (`_submit_launch_approval_task`, `:85`, with `dedup_key=f"launch-approval:{request_id}"`). It never writes the response itself; it delegates entirely to `execute_launch_approval_response`.

**Unread semantics** (`_notification_modal_flow.py:152-160`): all three are excluded from `mark_read` on modal dismiss — they stay unread until a response lands. Comment at `:154` says *"PlanApproval/UserQuestion must stay unread until response"* but the code list includes `LaunchApproval` — stale comment.

---

## 4. `pending_actions.py` — the relevant structures

The registration table at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/notifications/pending_actions.py:26`:

```python
_ACTION_KIND_BY_NOTIFICATION_ACTION = {
    "PlanApproval": "plan_approval",
    "HITL": "hitl",
    "UserQuestion": "user_question",
    "LaunchApproval": "launch_approval",
    "memory_review": "memory_review",
}
```

The `_externally_handled` predicate (`:308`) — note the **shape divergence**:

```python
    if notification.action == "PlanApproval":
        response_dir = _action_path(notification, "response_dir")
        if response_dir is None:
            return False
        return (
            (response_dir / "plan_response.json").exists()
            or (response_dir / "plan_approved.marker").exists()      # <-- plan-only 3rd signal
            or (
                response_dir.is_dir()
                and not (response_dir / "plan_request.json").exists()
            )
        )
    ...
    if notification.action == "UserQuestion":
        response_dir = _action_path(notification, "response_dir")
        if response_dir is None:
            return False
        return (response_dir / "question_response.json").exists() or (
            response_dir.is_dir()
            and not (response_dir / "question_request.json").exists()
        )
    if notification.action == "LaunchApproval":
        response_dir = _action_path(notification, "response_dir")
        if response_dir is None:
            return False
        return (response_dir / "launch_response.json").exists() or (
            response_dir.is_dir()
            and not (response_dir / "launch_request.json").exists()
        )
```

Question/launch are structurally identical modulo filenames; plan adds `plan_approved.marker`.

And the uniform target check at `:348`:

```python
def _required_target_missing(notification: Notification) -> bool:
    if notification.action in {"PlanApproval", "UserQuestion", "LaunchApproval"}:
        return _action_path(notification, "response_dir") is None
    if notification.action == "HITL":
        return _action_path(notification, "artifacts_dir") is None
    return False
```

Entry schema (`_entry_from_notification`, `:249`): `schema_version=2`, `prefix` (first 8 chars of notification id, `PENDING_ACTION_PREFIX_LEN = 8`), `notification_id`, `action_kind`, `action`, `action_data`, `files`, `created_at_unix`, `updated_at_unix`, `stale_deadline_unix` (`STALE_THRESHOLD_SECONDS = 24h`, `:24`), `transports`, `state`.

**Plan-only API**: `mark_plan_approval_auto_handled` (`:186`) — no question/launch equivalent exists. Its identity-matching rule is deliberately strict (`_plan_identity_matches`, `:433`): *"Matching never falls back to plan file alone: with no identity field provided nothing is marked, avoiding clobbering unrelated approvals when a plan path is reused."* Called from `_plan_utils.py:144` on auto-approve.

---

## Distinct / asymmetric bits, consolidated

**What plan has that question doesn't:**
- Auto-approval (`get_auto_plan_approval_action()`), checked twice: before notifying (`_plan_utils.py:224`) and inside the poll loop (`:392`). Question has only a one-shot `is_auto_approve_active()` pre-check (`run_agent_helpers_questions.py:55`) that auto-picks the **first option of every question** and never notifies.
- `mark_plan_approval_auto_handled` + `plan_approved.marker` + `_auto_dismiss_external_plan_response` (`_notification_status_overrides.py:82`)
- 9 optional `action_data` fields (`agent_name`, `model`, `llm_provider`, `runtime`, `agent_vcs_tag`, `project_dir`, …) vs question's 4. Launch has 4 total and **zero agent-identity fields** — so a LaunchApproval can never be matched to an agent row.
- `files=[plan_file]`; question sends `files=[]` explicitly (`senders.py:223`)
- Sharded `response_dir`; question's is flat
- `.ace_refresh_pulse` touch
- `default_member_ids` → a second notes line "Also run: …" (`senders.py:280`)
- Epic launch ownership negotiation (`epic_launch_owner`) and tier validation

**What question has that plan doesn't:**
- `pending_question.json` marker in the **artifacts_dir** (`run_agent_helpers_questions.py:113`), enabling the dismissed-notification fallback path and runner-slot release/reacquire (`reacquire_runner_slot`, `:134`)
- Multi-row `ANSWERED` override semantics (`_mark_agents_answered`, `:200`) — one notification maps to both the asking child and the root row
- A dedicated summary module, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/notifications/question_summary.py`

**What launch has that neither does:**
- Returns the `notification_id` (`senders.py:328`); the other two return `None`
- Keyword-only signature (`senders.py:296`, `*`)
- Tags: `normalize_notification_tags(["launch"])` (`senders.py:324`) — plan and question set no tags
- The approver *performs the work* (`dispatch_approved_launch_request`, `launch_request.py:128`, which `os.chdir`s and calls `launch_agents_from_cwd`) rather than unblocking a waiting producer
- Two-phase response write (create-exclusive, then replace with dispatch status)
- Preview markdown artifact

**Latent gaps worth flagging:**

1. **`write_workflow_action_response` only marks plan handled.** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agents/_notification_modal_responses.py:36`: `if action_kind != "plan_approval": return`. So a TUI-answered **UserQuestion never gets `mark_already_handled`** — its pending-action entry stays `available` until `_externally_handled` re-derives it from the filesystem. Launch avoids this by calling `mark_already_handled` itself (`launch_approval_actions.py:119`).
2. **`sase run` outside an agent bypasses approval entirely** (`_launch.py:47`), and the in-agent path's rejection is enforced only by skill prose (`sase_run.md:114`), not by code.
3. **No code polls `launch_response.json`** — if the agent stops polling (context ends, crash), an approved launch still dispatches host-side, but the requesting agent never learns of it.
4. Stale comment at `_notification_modal_flow.py:154` and stale "via hook" docstrings at `senders.py:205`.

The first agent landed with a major correction to the premise. Let me verify two of its load-bearing claims before I rely on them.

I have everything I need. Here is the full report.

---

# `sase notify` CLI Surface — Research Report

## 1. Argparse definition

**Registration site:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser_commands.py:197-302` (`register_notify_parser`)

**Wired into the top-level parser at:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser.py:25` (import) and `:430` (`register_notify_parser(top_level_subparsers)`).

**Dispatched at:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/entry.py:252-256`:

```python
# --- notify ---
if args.command == "notify":
    from .notify_handler import handle_notify_command
    handle_notify_command(args)
```

### Group parser (`sase notify`) — parser_commands.py:199-218

```python
notify_parser = subparsers.add_parser(
    "notify",
    help="Create, list, or inspect notifications",
)
notify_parser.add_argument(
    "-s", "--sender", default=None,
    help="Notification sender name (overrides sender in JSON input)",
)
notify_parser.add_argument(
    "-t", "--tag", action="append", default=None,
    help="Tag for a created notification; repeat to add more tags",
)
notify_sub = notify_parser.add_subparsers(
    dest="notify_subcommand", help="Notification subcommands"
)
```

### `create` — parser_commands.py:220-236 (ALL flags)

```python
create_parser = notify_sub.add_parser(
    "create",
    help="Create a notification (reads JSON from stdin or uses flags)",
)
create_parser.add_argument(
    "-s", "--sender", default=None,
    help="Notification sender name (overrides sender in JSON input)",
)
create_parser.add_argument(
    "-t", "--tag", action="append", default=None,
    help="Tag for the created notification; repeat to add more tags",
)
```

**That is the complete `create` flag surface: only `-s/--sender` and `-t/--tag`.** Everything else (`notes`, `files`, `action`, `action_data`, `silent`) is stdin-JSON-only. There is no `--note`, `--file`, `--action`, `--action-data`, or `--silent` flag today.

### `list` — parser_commands.py:238-284
`-j/--json` (store_true), `-l/--limit` (int, default 20), `-q/--query`, `-t/--tag` (plain string — **not** append), `-s/--sender`, `-u/--unread`, `-a/--all`.

### `show` — parser_commands.py:286-302
`-i/--id` (**required**), `-f/--format` (`choices=("markdown","json")`, default `markdown`).

### Bare-`notify` defaulting quirk (important if you add flags)
`sase notify` with no subcommand resolves to `list` via `_default_list_subcommands()` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/parser.py:333-364`, which calls `_copy_parser_defaults(list_parser, parser)`. Consequence: the group-level `-t/--tag` is `action="append"` (list-of-str) while `list`'s `-t/--tag` is a plain string — the group and child disagree on the type of the same short flag. `handle_notify_command` dispatches `None` and `"list"` identically (`notify_handler.py:22`).

### Handler
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/main/notify_handler.py:37-72` — `_handle_notify_create`:

- Reads stdin JSON only when `not sys.stdin.isatty()` (`:42`); invalid JSON → exit 1 (`:48-49`).
- `--sender` overrides JSON `sender` (`:52-53`); missing sender → exit 1 (`:55-57`).
- Builds the `Notification` with a server-side `uuid4` id and `datetime.now(get_timezone()).isoformat()` timestamp — **id and timestamp are not caller-controllable** (`:60-61`).
- Passes through `notes`, `files`, `action`, `action_data` verbatim from JSON (`:63-67`). Note **`silent` is NOT read from JSON** — it silently defaults to `False`.
- Tags merged JSON-then-CLI via `_create_tags` (`:75-84`) → `normalize_notification_tags` (strip/lower/dedupe, order-preserving).
- Prints the new id to stdout, exits 0 (`:71-72`).

---

## 2. `sase_notify.md` skill

**File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/xprompts/skills/sase_notify.md` (69 lines).

**Key finding: the skill never mentions `sase notify create`.** It is explicitly and exclusively read-only. Lines 9-10:

> "Quick reference for inspecting SASE notifications. This skill is read-only: do not dismiss, mute, snooze, mark read, or otherwise mutate notifications unless the user explicitly asks and a SASE CLI command exists for that action."

What agents are told they *can* do: `sase notify list -j -l 20` (line 15) as the primary command; filter by `--sender`, `--unread`, `-q`, `--all` (lines 24-28); `sase notify show --id <id>` and `-f json` (lines 37, 44). Axe digest flow: check `files`, then `action_data.error_report_path`, then read the attached file (lines 53-56). Summarization rules: cite `id`/`sender`/`timestamp`, don't fabricate, report uncertainty (lines 63-69).

The skill also documents the JSON row shape (lines 18-20) — `id`, `timestamp`, `age`, `sender`, `priority`, `notes`, `files`, `action`, `action_data`, `read`, `dismissed`, `silent`, `muted`, `snooze_until`. **Note this list omits `tags`**, which the actual projection does emit (verified against `tests/main/test_notify_handler.py:269-285` and `catalog.py`). That's a pre-existing doc drift in the skill.

### Deployed/generated skills story
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/memory/generated_skills.md:11-16`:

> Chezmoi skill files (`SKILL.md`) are **generated**, not hand-edited. The source templates live in `src/sase/xprompts/skills/` and are rendered per-provider by `sase skill init`.
> - Run `sase skill init --force` after changing any skill source file in `src/sase/xprompts/skills/`
> - Then run `chezmoi apply` to deploy the generated files to their live locations
> - Do NOT edit the chezmoi skill files directly — changes will be overwritten on the next generation

And the **CLI/Skill Contract Synchronization** rule (`:18-24`) — written for `sase commit` but directly analogous:

> Any change to `sase commit` CLI arguments must include same-turn updates to: in-repo callers/wrappers that invoke the changed arguments; relevant skill `SKILL.md` files that document or demonstrate those arguments; tests validating both CLI parsing and skill invocation examples.

---

## 3. Tests touching `sase notify create` / `notify_handler`

**Only one file** references `notify_handler`, `notify create`, `handle_notify`, `register_notify_parser`, or `notify_subcommand`:

**`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/main/test_notify_handler.py`** (469 lines). Fixture `temp_notifications_dir` (`:25-34`) patches `store.NOTIFICATIONS_DIR`, `store.NOTIFICATIONS_FILE`, and clears `store._LOAD_CACHE`.

Parser tests:
- `:88` `test_parser_defaults_bare_notify_to_list` — asserts bare `notify` → `notify_subcommand == "list"` with all list defaults present on the namespace.
- `:102` `test_parser_registers_notify_list_options` — all list flags parse.
- `:132` `test_parser_registers_notify_show_options` — `--id`/`-f json`; `SystemExit` for missing `--id` and for `-f raw`.
- `:145` `test_parser_registers_explicit_create_alias` — `["notify","create","-s","worker","-t","Review"]` → `sender == "worker"`, `tag == ["Review"]`.

Create-behavior tests:
- `:153` `test_explicit_create_path_writes_notification` — stdin JSON `{"sender":"json","notes":["created"]}`, asserts exit 0, printed id == stored id, sender/notes round-trip.
- `:179` `test_create_sender_flag_overrides_stdin` — `--sender cli` beats JSON `"json"`.
- `:195` `test_create_combines_json_and_cli_tags` — JSON `[" Done ","Review"]` + CLI `["review","CLI"]` → `["done","review","cli"]` (normalize + dedupe + order).

Dispatch/list/show tests: `:223` dispatch to list; `:247` **asserts exact JSON key order** of list rows (`id, timestamp, age, sender, priority, notes, files, tags, action, action_data, read, dismissed, silent, muted, snooze_until`); `:288` `--all` includes dismissed; `:305` pretty empty output; `:314` show json+markdown; `:348` unknown id → exit 2; `:360`/`:372` store read failure → exit 1 with "cannot read notifications".

End-to-end skill-contract test: `:384` `test_notify_skill_recommended_flow_lists_shows_and_reads_axe_digest` — drives the exact command lines the skill documents through `create_parser()` + `handle_notify_command`, asserting the axe digest discovery flow works.

**Adjacent (do not test the CLI, but do construct `Notification`/`append_notification`):** `tests/test_notification_models.py`, `tests/test_notification_priority.py`, `tests/test_notification_catalog.py`, `tests/test_notifications_sort.py`, `tests/test_pending_actions.py`, `tests/test_core_notification_store.py`, `tests/test_mobile_notifications_bridge.py`, and the `tests/notification_store/` package (`test_storage.py`, `test_state_updates.py`, `test_models.py`, `test_mute_snooze.py`).

---

## 4. `memory/cli_rules.md` — constraints on new `notify create` subcommands/options

Full file is 27 lines. The binding rules (`:9-14`):

> When adding or changing CLI subcommands or options:
> - Make `-h|--help` output excellent: clear, complete, consistent, and easy to scan.
> - **Keep listed subcommands and options sorted alphabetically.**
> - **Give every public long option a short alias**; this does not apply to internal subprocess arguments.
> - Prefer beautiful, colored output over black-and-white output when color improves readability.

Concrete implications for `notify create`:
- Any new long option needs a short alias. `-s` and `-t` are taken. Within `notify`, `-j -l -q -u -a -i -f` are consumed by sibling subcommands (reuse across siblings is fine, but avoid confusing collisions).
- **The existing `create` parser already violates the alphabetical rule at the group level**: `create`, `list`, `show` are alphabetical (good), but if you add options you must keep them sorted — `-s/--sender` currently precedes `-t/--tag`, which is alphabetical, so insert new options in the right slot rather than appending.

The **Default `list` Subcommand Convention** (`:16-27`) also constrains you:
> - A command group that has an exact `list` child defaults to that child when invoked bare... wired centrally in `_default_list_subcommands()` in `src/sase/main/parser.py`; do not re-implement it per command.
> - **Flags owned by `list` still belong after the explicit `list` token** (e.g. `sase plan list --json`, not `sase plan --json`). Document the bare default in the group's help/description, matching `sase plan`.

Since `notify` has a `list` child, adding flags to the **group-level** `notify_parser` is exactly what the convention warns against — new `create` options belong on `create_parser` only. (The existing duplicated group-level `-s`/`-t` are legacy and already in tension with this rule; `docs/cli.md:49` and `docs/notifications.md:254-255` both reinforce "use the explicit `list` subcommand when passing list flags".)

---

## 5. The notification store

### Physical location
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/notifications/store.py:32-43`:

```python
def _notifications_dir() -> str:
    return NOTIFICATIONS_DIR or str(sase_subdir("notifications"))

def _notifications_file() -> str:
    return NOTIFICATIONS_FILE or os.path.join(_notifications_dir(), "notifications.jsonl")
```

`sase_subdir` → `sase_home()/subdir`, and `sase_home()` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/core/paths.py:47-54`):

```python
return Path(os.environ.get("SASE_HOME") or Path.home() / ".sase").expanduser()
```

**Path: `$SASE_HOME/notifications/notifications.jsonl`, defaulting to `~/.sase/notifications/notifications.jsonl`.** Module-level `NOTIFICATIONS_DIR`/`NOTIFICATIONS_FILE` globals (`store.py:16-17`) exist purely as test seams.

### Wire format
One JSON object per line (JSONL). All I/O goes through Rust — `store.py:1` is literally titled *"Rust-backed JSONL notification storage."* Python never writes the file directly; `append_notification` (`:113-123`) calls `notification_store_facade.append_notification_counts`, which calls `require_rust_binding("append_notification_counts")` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/core/notification_store_facade.py:67-76`). Rust owns locking, tempfile, and atomic rename (`facade.py:83`: "Rewrite the store through Rust's lock/tempfile/rename path").

Wire schema version: `NOTIFICATION_STORE_WIRE_SCHEMA_VERSION = 1` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/core/notification_store_wire.py:10`. Mismatches raise (`:124-128`).

Python→Rust projection is a plain `dataclasses.asdict` (`notification_store_wire.py:83-84`):
```python
if isinstance(record, Notification):
    return asdict(record)
```
Rust→Python rehydration is explicit and coercive (`_notification_from_dict`, `:98-117`) — note `action_data` is force-cast to `{str: str}`:
```python
action_data={str(k): str(v) for k, v in (data.get("action_data") or {}).items()},
```

### Fields crossing the Rust boundary
All 13 `Notification` fields cross, in both directions: `id`, `timestamp`, `sender`, `notes`, `files`, `tags`, `action`, `action_data`, `read`, `dismissed`, `silent`, `muted`, `snooze_until`.

### Is `Notification` mirrored in Rust? **Yes — exactly.**
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_core/src/notifications/wire.rs:8-32`:

```rust
pub struct NotificationWire {
    pub id: String,
    pub timestamp: String,
    pub sender: String,
    #[serde(default)] pub notes: Vec<String>,
    #[serde(default)] pub files: Vec<String>,
    #[serde(default)] pub tags: Vec<String>,
    #[serde(default)] pub action: Option<String>,
    #[serde(default)] pub action_data: BTreeMap<String, String>,
    #[serde(default)] pub read: bool,
    #[serde(default)] pub dismissed: bool,
    #[serde(default)] pub silent: bool,
    #[serde(default)] pub muted: bool,
    #[serde(default)] pub snooze_until: Option<String>,
}
```

Field-for-field identical to `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/notifications/models.py:8-24`. **Critical constraint: `action_data` is `BTreeMap<String, String>` in Rust — flat, string-valued only. No nested objects, no lists, no ints.** Any new `action_data` payload must be string-encoded. `id`, `timestamp`, `sender` have no `#[serde(default)]` → they are required on every line.

There is a dedicated parity test: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_core/tests/notification_store_parity.rs`.

Other wires (`notification_store_wire.py:13-74`): `_NotificationCountsWire` (priority/errors/rest/muted), `_NotificationStoreStatsWire` (total/blank/invalid_json/invalid_record/loaded/dismissed_filtered lines), `NotificationStoreSnapshotWire`, `NotificationUpdateOutcomeWire`, `NotificationAgentKeyWire` (cl_name/raw_suffix), and the tagged `NotificationStateUpdateWire` whose `kind` values are: `mark_read`, `mark_dismissed`, `mark_many_dismissed`, `mark_muted`, `mark_snoozed`, `expire_snoozes`, `mark_all_read`, `dismiss_matching_agents`, `dismiss_agent_completions_matching_agents`.

### Caching side-effect of `create`
`append_notification` (`store.py:113-123`) also calls `pending_actions.register_notification(n)` inside a try/except that only warns on failure, then `_invalidate_load_cache()`. The `_LOAD_CACHE` (`:24`) is keyed by `(st_size, st_mtime_ns, st_ino, include_dismissed)` so cross-process writes invalidate via `stat()`.

---

## 6. Mobile notification integration

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/integrations/mobile_notifications.py` is a 41-line pure re-export facade over five `_mobile_notification_*.py` siblings.

### How a Notification becomes a mobile push
It is a **pull/snapshot bridge, not a direct push on create.** `sase notify create` does *not* itself send a push. The chain is:

1. **`_mobile_notification_snapshot.py:20-97`** — `read_mobile_notification_snapshot()` calls `load_notifications()` (store → Rust) and filters `silent` rows unless `include_silent` (`:36-37`):
   ```python
   if not include_silent:
       rows = [row for row in rows if not row.silent]
   ```
   `_bridge_row()` (`:70-97`) projects each `Notification` into a `MobileNotificationBridgeRow`, splitting `action_data` into **two** copies: `display_action_data` (home-path normalized, for UI) and `host_action_data` (raw, for filesystem access) — `:83-90`. It attaches `action_state=action_state_for_notification(notification)` from `pending_actions`.
2. **Rust card projection** — `sase/repos/linked/sase-core/crates/sase_core/src/notifications/mobile.rs:355-390`, `mobile_notification_card_from_wire()`.
3. **Gateway** — `crates/sase_gateway/src/host_bridge.rs:348-380` exposes `list_notifications`, `notification_file_metadata`, `action_state`, and *rejects* mutations in the default bridge (`:459`, `:469`: `"notification state mutations are not supported by this bridge"`). Notifications path is rebuilt independently at `host_bridge.rs:531-533` (`sase_home.join("notifications")`).
4. **Push** — `crates/sase_gateway/src/push.rs:124` derives a hint via `push_hint_from_event()` (`crates/sase_gateway/src/wire.rs:270+`) from an *event record*, then fans out to subscriptions. The push body carries only `notification_id` (`push.rs:490-491`) with a generic title/body (`"SASE notification update"` / `"Open SASE to view current notifications."`, `push.rs:654-655`). **The push is a wake-up ping; the client re-fetches the snapshot.**

### Which `action` values are special-cased
`mobile.rs:724-732` — `mobile_action_kind()`:
```rust
Some("PlanApproval") => MobileActionKindWire::PlanApproval,
Some("HITL")         => MobileActionKindWire::Hitl,
Some("UserQuestion") => MobileActionKindWire::UserQuestion,
Some("LaunchApproval") => MobileActionKindWire::LaunchApproval,
None                 => MobileActionKindWire::NonAction,
Some(_)              => MobileActionKindWire::Unsupported,
```
**Any unrecognized `action` string → `Unsupported`** (labeled `"Unsupported action"`, `mobile.rs:741`) and `actionable == false` (`mobile.rs:363-368`). `action == None` → `NonAction`, `action_summary: None`.

Python-side action executors (`mobile_notifications.py:5-10`): `execute_mobile_hitl_action`, `execute_mobile_launch_action`, `execute_mobile_plan_action`, `execute_mobile_question_action`. Each re-resolves by action name — e.g. `_mobile_notification_actions.py:127` `_resolve_action_notification(prefix, "HITL")`, `:218` `_resolve_action_notification(prefix, "LaunchApproval")`.

### Does it care about sender / action / action_data shape? **Yes, heavily.**

**Sender** — hardcoded allow-lists. `mobile.rs:392-397`:
```rust
pub fn mobile_notification_error_from_wire(notification: &NotificationWire) -> bool {
    notification.action.as_deref() == Some("ViewErrorReport")
        && matches!(notification.sender.as_str(), "axe" | "user-agent")
}
```
`mobile.rs:400-411` — priority requires action in `{PlanApproval, UserQuestion, JumpToMentorReview, LaunchApproval}` **or** sender in `{"axe","crs"}`. Mirrored in Python at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/notifications/priority.py:11-16`:
```python
_PRIORITY_ACTIONS = frozenset({"PlanApproval", "UserQuestion", "LaunchApproval", "JumpToMentorReview"})
_PRIORITY_SENDERS = frozenset({"axe", "crs"})
_ERROR_SENDERS = frozenset({"axe", "user-agent"})
```
**So an arbitrary `--sender foo` from `sase notify create` can never be priority or error-classified.**

**action_data shape** — each action kind requires specific keys (`mobile.rs:415-480`):
- `PlanApproval` → `action_data["response_dir"]`, plan file from `files.first()`, choices Approve/Run/Reject/Epic/Feedback.
- `HITL` → `action_data["artifacts_dir"]`, `action_data["workflow_name"]`, choices Accept/Reject/Feedback.
- `UserQuestion` → `action_data["response_dir"]`, `action_data["question_count"]` (**parsed as `u32`, defaults to 0 on parse failure**), choices Answer/Custom.
- `LaunchApproval` → `action_data["response_dir"]`, `request_id`, `source_surface`, `slot_count` (`u32`), choices Approve/Reject/Feedback.

**Attachment resolution** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/integrations/_mobile_notification_attachments.py:75-101` reads generic path keys from `host_action_data` (`project_file`, `agent_project_file`, `output_path`, `response_path`, `image_path`) then branches on action:
```python
if notification.action == "PlanApproval":
    if response_dir := notification.host_action_data.get("response_dir"):
        _append_unique_path(paths, str(Path(response_dir).expanduser() / "plan_request.json"))
elif notification.action == "HITL":
    if artifacts_dir := notification.host_action_data.get("artifacts_dir"):
        request_path = Path(artifacts_dir).expanduser() / "hitl_request.json"
        ...
elif notification.action == "UserQuestion":
    if response_dir := notification.host_action_data.get("response_dir"):
        _append_unique_path(paths, str(Path(response_dir).expanduser() / "question_request.json"))
```

**Pending-action registration** (fires on every `create`) — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/notifications/pending_actions.py:26-32`:
```python
_ACTION_KIND_BY_NOTIFICATION_ACTION = {
    "PlanApproval": "plan_approval",
    "HITL": "hitl",
    "UserQuestion": "user_question",
    "LaunchApproval": "launch_approval",
    "memory_review": "memory_review",
}
```
`_entry_from_notification` (`:249-256`) returns `None` for any other action — so an unknown action creates no pending-action entry. Note `memory_review` is registered here but is **not** in the mobile action-kind map — it's TUI/CLI-only.

---

## Summary of hard constraints on extending `sase notify create`

| Constraint | Source |
|---|---|
| New long options require short aliases; keep sorted alphabetically | `memory/cli_rules.md:12-13` |
| Put new flags on `create_parser`, not `notify_parser` (bare-notify defaults to `list`) | `memory/cli_rules.md:16-27`, `parser.py:333-364` |
| `action_data` values must be flat strings (Rust `BTreeMap<String,String>`) | `wire.rs:21`, `notification_store_wire.py:107-109` |
| New `Notification` fields require same-turn Rust `NotificationWire` change + schema version bump | `wire.rs:8-32`, `notification_store_wire.py:10` |
| New `action` values are inert on mobile (`Unsupported`, non-actionable) unless added to `mobile_action_kind()` **and** `_ACTION_KIND_BY_NOTIFICATION_ACTION` **and** `_PRIORITY_ACTIONS` | `mobile.rs:724-732`, `pending_actions.py:26-32`, `priority.py:11` |
| Skill source edits require `sase skill init --force` + `chezmoi apply`; never edit chezmoi output | `memory/generated_skills.md:11-16` |
| CLI arg changes require same-turn updates to callers, `SKILL.md`, and tests for both parsing and skill examples | `memory/generated_skills.md:18-24` |
| `tests/main/test_notify_handler.py:269-285` pins exact list JSON key order — adding a field breaks it | that test |
| `docs/notifications.md:231-237` and `docs/cli.md:32` document `create`; the skill deliberately does not | those files |

Two latent inconsistencies worth flagging to whoever acts on this: (a) `sase_notify.md:18-20` omits `tags` from the documented row shape even though it is emitted; (b) `notify_handler.py:59-68` never reads `silent` from stdin JSON, so `silent` is unreachable via the CLI despite being a first-class field that the mobile bridge filters on (`_mobile_notification_snapshot.py:36-37`).

Both claims verified independently: `_notification_modal_responses.py:36` early-returns for anything that isn't `plan_approval`, and the only "poller" of `launch_response.json` is prose in `sase_run.md:100` telling the LLM to poll it. The three remaining agents are still running.

I have a complete picture. Here is the report.

---

# Dynamic Agent Family Member Hooks — `improve_plan` & `tester`

## 1. What is an "agent family"?

**Concept** (`docs/agent_families.md:1-22`): a *plan-chain agent family* is the group of agents sharing a `--`-separated base name (`foo`, `foo--plan`, `foo--code`, `foo--plan-2`). "Dynamic agent families" adds two extension mechanisms on top of the historically hard-coded plan→coder transitions:

- **User-initiated**: `%n(parent, suffix)` in any prompt (→ §4).
- **Lifecycle-initiated**: declarative `kind: agent_family` YAML custom roles, toggled at the plan gate.

### Schema / model / parser

| Concern | File |
|---|---|
| Dataclass models | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent_family/custom_definitions/models.py` |
| Parser + validation | `.../src/sase/agent_family/custom_definitions/validation.py` |
| YAML/mapping loaders | `.../src/sase/agent_family/custom_definitions/loading.py` |
| Filesystem discovery | `.../src/sase/agent_family/custom_definitions/discovery.py` |
| Public re-exports | `.../src/sase/agent_family/__init__.py`, `.../custom_definitions/__init__.py` |

`models.py:11-13` defines the enums, `models.py:16-35` `AgentFamilyRoleDefinition`, `models.py:58-67` `AgentFamilyDefinition`:

```python
type RoleOnDone = Literal["re_review", "continue", "terminate"]
type RoleOnFailure = Literal["notify_and_continue", "notify_and_stop"]
type RoleAuto = Literal["run", "skip"]
STANDARD_EXTENDS_ID = "standard_plan_chain"
```

`loading.py:52-56` is the `kind` gate — the *only* thing that makes a YAML file a family definition:

```python
if not isinstance(data, Mapping):
    return None
if data.get("kind") != "agent_family":
    return None
```

`validation.py:59-111` `parse_agent_family_definition` enforces `schema_version == 1`, `extends == "standard_plan_chain"`, non-empty `roles` mapping, and computes a sha256 `config_hash` over `{schema_version, id, version, extends, roles}` (`validation.py:80-89`). `validation.py:153-215` `_parse_role` handles per-role keys; `_ROLE_KEYS` (`validation.py:34-49`) is a closed set (unknown keys are load errors) and includes two explicitly reserved, uninterpreted keys:

```python
    # Reserved for the Phase 8 delegated-budget design. These are accepted
    # and snapshotted but intentionally not interpreted in Phase 5.
    "delegated_budget",
    "delegated_budgets",
```

`_RESERVED_SUFFIXES` (`validation.py:27-33`) blocks `--plan/--q/--code/--epic/--commit`. Display labels are capped at 24 chars by `_DISPLAY_LABEL_RE` / `_DISPLAY_LABEL_MAX_LEN` (`validation.py:51-52`).

**Discovery order** (`discovery.py:100-146`, documented at `docs/agent_families.md:118-127`): package xprompts → plugins (`sase_xprompts`) → `~/.config/sase/xprompts/<project>/` → workspace `.xprompts/`/`xprompts/` → general search paths; later wins by `id`. Note the docstring at `discovery.py:35-37`:

> Priority mirrors xprompt/workflow discovery. Bundled example definitions live under ``xprompts/examples`` and are intentionally not active.

`_load_definitions_from_dir` (`discovery.py:168-188`) uses a **non-recursive** `directory.glob("*.yml")`, which is the actual mechanism that keeps `src/sase/xprompts/examples/agent_families/*.yml` inactive — there is no name-based exclusion.

`active_roles_after(after_role, ...)` (`discovery.py:149-165`) is the query the runner uses; it sorts by `(source_path, id)`.

---

## 2. What `improve_plan` and `tester` actually are

**Both are inactive, bundled *example* YAML templates** — `tester` is indeed also an example family file, symmetric to `improve_plan`.

### `improve_plan`
`.../src/sase/xprompts/examples/agent_families/improve_plan.yml` (14 lines, verbatim):
```yaml
kind: agent_family
schema_version: 1
id: improve_plan
version: 1
extends: standard_plan_chain
roles:
  improve_plan:
    suffix: "--improve_plan"
    label: "IMPROVING PLAN"
    done_label: "PLAN IMPROVED"
    prompt_template: "agent_family_improve_plan:{plan_file}"
    placement:
      after: plan
    on_done: re_review
    max_visits: 3
    on_failure: notify_and_stop
    auto: skip
```
Its prompt body `.../src/sase/xprompts/agent_family_improve_plan.md` (an **active** xprompt, directly in the package xprompts dir) tells the agent to improve the approved plan and re-submit via `/sase_plan` — that resubmission is what creates the re-review loop (`docs/agent_families.md:218-224`).

### `tester`
`.../src/sase/xprompts/examples/agent_families/tester.yml`: `placement.after: code`, `on_done: terminate`, `max_visits: 1`, `on_failure: notify_and_continue`, `auto: run`. Body: `.../src/sase/xprompts/agent_family_tester.md` — "Run the most relevant focused tests, inspect failures, and report any issues clearly."

### Every reference (excluding `.git`, `node_modules`)

**`improve_plan`** — 11 files, **zero non-test/non-doc source code**:
- `src/sase/xprompts/examples/agent_families/improve_plan.yml` (definition)
- `src/sase/xprompts/agent_family_improve_plan.md` (prompt body)
- `docs/agent_families.md:16,131,135-153,191,221`
- Tests: `tests/test_plan_approval_choices.py:122-206`, `tests/test_plan_approval_responses.py:297-353`, `tests/test_plan_approve_cli.py:45-368`, `tests/test_approve_options_modal_state.py:196-218`, `tests/test_agent_family_custom_definitions.py:79-96,186-217,296,364`, `tests/test_config_schema.py:214`, `tests/test_dynamic_agent_family_attach_resolution.py:278`, `tests/ace/tui/visual/test_ace_png_snapshots_agents.py:252-285`

**`tester`** — same set plus four **incidental string** hits in source:
- `src/sase/main/parser_plan.py:56` — CLI epilog example text only: `"  sase plan approve abcdef12 --with tester\n"`
- `src/sase/xprompts/skills/sase_run.md:96` — doc example: `` `%n(parent, tester)` when the role matters. ``
- `tools/validate_sase_core_rs:163` — Rust-binding probe fixture `{"id": "tester", "label": "TESTING", "done_label": "TESTED"}` (mirrored in `tests/test_validate_sase_core_rs_tool.py:12`)
- `docs/ace.md:1566,1738`, `docs/xprompt.md:1115`
- **False positives**: `smoke/pypi/Dockerfile:14-43` and `smoke/pypi/docker-compose.yml:15` — a Linux user named `tester`, unrelated.

**Nothing in `src/sase/**/*.py` branches on either id.** They are pure data.

---

## 3. How a family member becomes a plan-approval *choice*

The registry is `.../src/sase/plan_approval_choices.py`. Its docstring (lines 1-5) states it is "the approval-gate vocabulary source of truth."

Members are a **separate axis from choices**: `PLAN_APPROVAL_CHOICE_RECORDS` (`:92-193`) is the closed set (`approve/run/tale/epic/commit/reject/feedback`); custom members are `PlanApprovalMemberOption` (`:61-89`) rendered as an *additive* "Also run:" multi-select.

### Producer side (runner writes `plan_request.json`)

1. `_plan_approval_member_options()` (`:293-329`) walks `get_all_agent_family_definitions()`, **flattens all roles across all definitions into one id-keyed dict**, applies config overrides, and sorts by role id:
```python
default_overrides = _configured_plan_approval_member_defaults()
...
for role_id in sorted(roles_by_id):
    role = roles_by_id[role_id]
    default_enabled = default_overrides.get(role.id, role.default_enabled)
```
   Note `display_label=role.id.replace("_", " ")` (`:317`) — so `improve_plan` renders as `improve plan`.
2. `_configured_plan_approval_member_defaults()` (`:478-506`) reads `agent_family.plan_approval.default_members` from merged config (mapping *or* list form). Schema: `src/sase/config/sase.schema.json:168-188`; default `{}` at `src/sase/default_config.yml:24-29`.
3. `plan_approval_member_request_payload()` (`:332-348`) emits `{"member_options": [...], "default_member_ids": [ids where default_enabled]}`.
4. `src/sase/llm_provider/_plan_utils.py:252-294` merges that payload into `plan_request.json` and passes ids to the notifier:
```python
member_payload = plan_approval_member_request_payload(
    project=_plan_approval_project_name(project_dir)
)
request_data = {"plan_file": ..., "session_id": ..., "timestamp": ..., **member_payload}
```
5. `notify_plan_approval` (`src/sase/notifications/senders.py:231-289`) — `default_member_ids` is **display-only**, appended as a note:
```python
notes = [f"Plan ready for review: {plan_name}"]
default_members = [m for m in default_member_ids if isinstance(m, str) and m.strip()]
if default_members:
    notes.append(f"Also run: {', '.join(default_members)}")
```
   This is what remote (Telegram/mobile) approvers see, since they have no toggles (`docs/agent_families.md:207-210`).

### Consumer side (surfaces)

- **ACE TUI**: `src/sase/ace/tui/actions/agents/_notification_modals.py:78` parses options → `PlanApprovalModal(member_options=...)` (`:116`, `:269`) → forwarded to `ApproveOptionsModal` (`src/sase/ace/tui/modals/plan_approval_modal.py:292-293`).
- **Approve-options modal state** — `.../src/sase/ace/tui/modals/approve_options_modal.py`:
  - `__init__:143-160` seeds `self._selected_member_ids` from `default_enabled` when no explicit selection.
  - `compose:189-196` renders the `"Also run:"` section, one `Static` per option with `id=f"approval-member-{option.id}"`.
  - `_member_row_markup:225-241` renders `1 [x] tester after code`.
  - `_toggle_member` / index handler at `:322-328`; result tuple at `:330-335`; dismissal at `:404,415`.
  - Result dataclasses `ApproveOptionsResult` / `ApproveOptionsEditPrompt` carry `selected_member_ids` (`:89`, `:107`).
- **CLI**: `src/sase/main/plan_approve_handler.py:130-184`. `_selected_member_ids_for_cli` returns `None` when neither flag is given (preserving defaults), else reads `plan_request.json` and calls `resolve_member_selection_for_overrides` (`plan_approval_choices.py:437-458`), which raises on `--with`/`--without` overlap or unknown ids.
- **Auto mode**: `_plan_utils.py:66-68` → `default_member_ids_from_request_data(payload, auto_mode=True)`; `plan_approval_choices.py:405-407` intersects defaults with `auto == "run"`:
```python
if auto_mode:
    auto_ids = {option.id for option in options if option.auto == "run"}
    default_ids = [member_id for member_id in default_ids if member_id in auto_ids]
```
  (This is exactly why `tester` has `auto: run` and `improve_plan` has `auto: skip`.)

### Response → execution

`selected_member_ids_from_response_data` (`:412-434`) → `PlanApprovalResult` (`_plan_utils.py:353-373`) → `run_agent_exec_plan_accept.py:312-322` stores `state.selected_member_ids` and filters:
```python
active_after_plan = filter_roles_by_selected_member_ids(
    active_roles_after("plan", project=ctx.project_name),
    selected_member_ids,
)
```
Same pattern for `after: code` at `run_agent_exec.py:227-229` (keyed on `event.interrupted_role`). `filter_roles_by_selected_member_ids` (`:461-475`) treats `None` as "no filtering" (legacy) vs `()` as "run nothing".

Selection precedence, per `docs/agent_families.md:205`: **explicit gate selection > project config > role's own `default`**.

The evaluator then inserts the member: `standard_plan_chain_evaluator.py:112-152` `_select_custom_role_after` — note it returns on the **first** matching role, enforces `auto`, checks `prior_visits >= role.max_visits` → `cap_exhausted=True`, and increments `visit_counts[role.id]`. Spawning/prompt rendering is `src/sase/axe/run_agent_exec_custom_roles.py:45-134`:
```python
rendered = role.prompt_template.format_map(values).strip()
if rendered.startswith(("#", "@", "%")):
    return rendered
return f"#{rendered}"
```
with placeholders `plan_file`, `source_artifacts`, `artifacts_ref`, `outcome`, `source_role`, `role` (`:53-61`); missing keys degrade to `""` via `_MissingFormatValue` (`:23-25`).

---

## 4. Dynamic attach resolution

`tests/test_dynamic_agent_family_attach_resolution.py` (330 lines) covers the **user-initiated** `%n(parent, suffix)` path — a *different* mechanism from custom lifecycle roles.

**Mechanism** (`src/sase/agent/_family_attach_resolution.py:19-70`, facade `src/sase/agent/family_attach.py`):

1. Snapshot every artifact record for the project (`agent_family_snapshot`) plus in-batch pending siblings from earlier `%n:foo` segments of the same multi-agent prompt.
2. Build a request `{"schema_version": 1, "parent_name", "project_name", "candidates": [...], "dismissed": [...]}` (`:36-45`).
3. Delegate matching to the **Rust core binding** — `_candidates.resolve_binding()` → `sase.core.rust.require_rust_binding` (`_family_attach_candidates.py:249-250`). Hence the test name `test_family_attach_absent_parent_error_uses_rust_resolution`.
4. Accept only `kind in {"resolved", "running"}`; anything else raises `FamilyAttachError` with a message from `_candidates.resolution_error_message` (`:46-52`).
5. Map the resolved `artifact_dir` back to a record/sibling to build a `FamilyAttachLaunchPlan` (`role_suffix`, `agent_family_role`, env).

Tested failure modes: absent parent (`"parent agent 'missing' was not found in project 'sase'"`), dismissed parent (`"Revive the parent from the Agents tab"`), ambiguous parent (lists `foo--plan` / `foo--code` candidates), numeric `@` allocation (`--1`, `--2`, with `%n(foo, @)` guidance on collision), role mapping, and `SASE_PLAN` env only for `code` with a parent plan path.

**Key decoupling fact** — `docs/agent_families.md:71-75`:

> A manual attach does not run the custom lifecycle machinery, though: even when the suffix matches a defined custom role (`%n(foo, tester)`), the member runs your prompt with generic RUNNING/DONE labels.

`improve_plan` appears in this test file exactly once, at `:278`, as an arbitrary parametrize value proving underscore-bearing suffixes map through (`("improve_plan", "improve_plan")`). **Zero real coupling.**

---

## 5. Coupling assessment

**Coupling to the notification machinery: effectively zero.** The notification path (`senders.py:274-280`) only string-joins whatever ids `default_member_ids` contains. `notify_plan_approval` never imports `agent_family` and never mentions either id. The entire pipeline — discovery → options → payload → modal → CLI → evaluator → spawn — is **generic over role ids**. `improve_plan`/`tester` are configuration data plus test/doc fixtures.

### What would break if removed

Deleting **only the two `.yml` example files** breaks **nothing** — they are inactive (non-recursive glob), unreferenced by any test, and not enumerated in packaging (`pyproject.toml:159,165` includes `src/sase` wholesale).

Deleting the **`.md` prompt bodies** breaks one real test. `tests/test_agent_family_custom_definitions.py:148-181` calls `get_all_agent_family_definitions()` with the default `validate_prompt_refs=True` and asserts `issues == []`, while its inline YAML references `prompt_template: "agent_family_tester:{source_artifacts}"`. Since `validation.py:176-182` calls `_validate_prompt_template_ref` against the xprompt catalog, removing `src/sase/xprompts/agent_family_tester.md` makes that assertion fail. Every other test passes `validate_prompt_refs=False`, so they'd survive.

**Files needing change for a full removal:**

*Source (4):*
1. `src/sase/xprompts/examples/agent_families/improve_plan.yml` — delete
2. `src/sase/xprompts/examples/agent_families/tester.yml` — delete (dir becomes empty)
3. `src/sase/xprompts/agent_family_improve_plan.md` — delete
4. `src/sase/xprompts/agent_family_tester.md` — delete

*Incidental source strings (2, cosmetic):*
5. `src/sase/main/parser_plan.py:56` — CLI epilog example
6. `src/sase/xprompts/skills/sase_run.md:96` — skill doc example

*Tooling (2 — only if you also rename the Rust probe fixture; not required):*
7. `tools/validate_sase_core_rs:159-165`
8. `tests/test_validate_sase_core_rs_tool.py:12`

*Docs (3):*
9. `docs/agent_families.md` — §Bundled Examples (`:129-178`) plus `:16`, `:33`, `:73`, `:185`, `:191`, `:203`, `:221`
10. `docs/ace.md:1738` (and `:1566`)
11. `docs/xprompt.md:1115`

*Tests (10 — all mechanical rename to placeholder ids, except #1 which is a real dependency):*
12. `tests/test_agent_family_custom_definitions.py` ← **the only functional breakage**
13. `tests/test_plan_approval_choices.py`
14. `tests/test_plan_approval_responses.py`
15. `tests/test_plan_approve_cli.py`
16. `tests/test_approve_options_modal_state.py`
17. `tests/test_config_schema.py:214-215`
18. `tests/test_dynamic_agent_family_attach_resolution.py:278`
19. `tests/ace/tui/visual/test_ace_png_snapshots_agents.py:252-285` (**PNG snapshot regeneration** — labels `IMPROVING PLAN`/`TESTING` are baked into committed images)
20. `tests/plan_chain_golden/test_plan_approval_response_golden.py:163-239` (golden JSON files)
21. `tests/test_agent_loader_status_custom_role_labels.py`, `tests/test_core_agent_scan_records_running.py:298-309`

**Bottom line:** the feature is well-factored — the ids are data, not code. The only non-cosmetic removal cost is (a) the prompt-ref validation test at `tests/test_agent_family_custom_definitions.py:148-181`, and (b) regenerating visual/golden fixtures. Removing them would, however, leave the feature with **no shipped examples**, which `docs/agent_families.md:129-131` positions as the intended onboarding path ("Copy the `.yml` file into an active xprompts directory to enable it").

Two agents down, two running. The picture is sharpening considerably:

**The Rust wire is the hard constraint.** `NotificationWire` (`wire.rs:8-32`) mirrors the Python dataclass field-for-field, and `action_data` is a `BTreeMap<String, String>` — flat, string-valued only. So a generalized constructor can't stuff nested payloads (question options, member choices) into `action_data`; those must stay in the `<kind>_request.json` file. The existing design already respects this, which is good news for generalizing it.

**Unknown actions degrade silently, in three places independently.** `mobile.rs:724-732` maps unrecognized actions to `Unsupported`/non-actionable; `pending_actions.py:26-32` returns `None` (no pending entry); `priority.py:11` won't classify it as priority. So a notification minted through today's `sase notify create` with a novel action is inert everywhere — any generalization must add registration in all three, or make them data-driven together.

**`sase notify create` is missing more than it has**: no `--action`, `--action-data`, `--note`, `--file`, and `silent` isn't even readable from stdin JSON despite being a first-class field the mobile bridge filters on.

I'll wait for the `improve_plan`/`tester` and Rust-wire agents before drafting.

The `improve_plan`/`tester` finding contradicts the older design doc — the feature appears to have been *built* since. Let me verify the load-bearing claims myself.

Verified. This is the most important finding so far, and it reframes the task.

**`improve_plan` and `tester` aren't hooks, and they aren't unfinished.** They're two inactive *example* YAML files (`src/sase/xprompts/examples/agent_families/`), kept inactive because discovery uses a non-recursive `directory.glob()` (`discovery.py:106`) and the docstring at `:36` says examples "live under `xprompts/examples` and are intentionally not active." No Python code branches on either id — they're pure data.

The machinery they exemplify **has been built**: `plan_approval_choices.py:1-4` calls itself "the approval-gate vocabulary source of truth," and the custom-role evaluator, `--with`/`--without` CLI flags, and the `ApproveOptionsModal` "Also run:" toggles all exist. So deleting the two files is nearly free — but it also **doesn't unblock anything**, because what actually entangles with the notification refactor is the *member-options feature* built on top of them: `member_options`/`default_member_ids` in `plan_request.json`, and the "Also run: …" note that `senders.py:274-280` injects into the plan notification.

That distinction — delete two example files vs. remove the custom-roles feature — is the central question I'll need answered, and I'll frame it that way in the doc. Waiting on the Rust-wire agent before writing.

I have a complete picture. Here is the report.

# Rust notification system in sase-core — refactor constraints

**Bottom line for your refactor:** the `action` value is an **open `Option<String>`**, not a Rust enum — a generic `sase notify create` can already emit any action string without touching Rust. But Rust holds four hardcoded `match` sites on those strings that silently downgrade unknown actions to non-actionable, and `action_data` is a hard `BTreeMap<String, String>` (string→string only, no nesting). That map is the real constraint on expressing plan/question/launch payloads.

---

## 1. The Notification struct/model

**`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/linked/sase-core/crates/sase_core/src/notifications/wire.rs:7-32`** — the single source of truth:

```rust
#[derive(Debug, Clone, Default, PartialEq, Eq, Serialize, Deserialize)]
pub struct NotificationWire {
    pub id: String,          // no #[serde(default)] — but String::default() = "" applies via Default
    pub timestamp: String,
    pub sender: String,
    #[serde(default)] pub notes: Vec<String>,
    #[serde(default)] pub files: Vec<String>,
    #[serde(default)] pub tags: Vec<String>,
    #[serde(default)] pub action: Option<String>,
    #[serde(default)] pub action_data: BTreeMap<String, String>,
    #[serde(default)] pub read: bool,
    #[serde(default)] pub dismissed: bool,
    #[serde(default)] pub silent: bool,
    #[serde(default)] pub muted: bool,
    #[serde(default)] pub snooze_until: Option<String>,
}
```

Notes on the serde contract:
- **No `#[serde(rename_all)]`** — Rust field names *are* the JSON keys. Locked by test `notification_json_shape_uses_expected_wire_keys` (`crates/sase_core/tests/notification_store_parity.rs:913-937`), which asserts the exact 13-key object including `"snooze_until": null`.
- **No `#[serde(skip_serializing_if)]`** — every field is always written, even empty vecs and nulls.
- **No `deny_unknown_fields` anywhere** (verified by grep across `notifications/` and `sase_core_py/`). Unknown keys deserialize fine — **and are then silently dropped on the next rewrite**. This is a real hazard: see §4.
- `id`, `timestamp`, `sender` lack `#[serde(default)]`, so they are **required on deserialize**; a row missing them is counted as `invalid_record_lines` and skipped, not an error.

**Serialization format: JSONL** (one compact JSON object per line, no pretty-printing).

**File path:** `<sase_home>/notifications/notifications.jsonl`. Constructed in `crates/sase_gateway/src/host_bridge.rs:531-534`:
```rust
notifications_path: sase_home.as_ref().join("notifications").join("notifications.jsonl"),
```
Core itself takes `path: &Path` from the caller and never derives it. Sidecar files: `<path>.lock` (`store.rs:799-805`) and `.{filename}.{pid}.{nanos}.tmp` (`store.rs:807-817`).

### The store implementation — `crates/sase_core/src/notifications/store.rs`

| Function | Line | Behavior |
|---|---|---|
| `append_notification` | `94` | Delegates with `include_notifications=true` |
| `append_notification_counts` | `101` | Same but returns metadata only (no rows) |
| `append_notification_with_options` | `108` | Takes exclusive flock, appends, unlocks |
| `append_notification_unlocked` | `141` | `serde_json::to_writer` + `\n` in `O_APPEND` mode |
| `read_notifications_snapshot` | `18` | Shared flock |
| `read_notifications_snapshot_with_options` | `26` | `expire_due_snoozes` flag takes an *exclusive* lock instead |
| `rewrite_notifications` / `_counts` | `159` / `166` | |
| `apply_notification_state_update` / `_counts` | `206` / `213` | |

The `_counts` variants exist purely to skip re-reading rows for the return value. Test `notification_append_counts_produces_byte_identical_jsonl` (`notification_store_parity.rs:985`) locks the two paths to byte-identical output.

**Rewrite is a merge, not a replace** — an explicit design decision documented at `store.rs:502-506`:
```rust
// Rewrite is a _merge_: caller's rows win on id collision; rows present on
// disk but absent from the input are preserved (they may be concurrent appends
// from another thread). Callers cannot use this to delete rows by passing a
// shorter list — if replacement semantics are ever needed, add a separate API.
```

Row-level error tolerance (`read_rows_unlocked`, `store.rs:448-500`): bad lines are **counted and skipped**, never fatal. Stats tracked in `NotificationStoreStatsWire` (`wire.rs:43-51`): `total_lines`, `blank_lines`, `invalid_json_lines`, `invalid_record_lines`, `loaded_rows`, `dismissed_filtered`.

**PyO3 bridge:** `crates/sase_core_py/src/lib.rs:2859-2868`:
```rust
fn notification_from_pydict(dict: &Bound<'_, PyDict>) -> PyResult<NotificationWire> {
    let value = py_to_json_value(dict.as_any())?;
    serde_json::from_value(value).map_err(|e| {
        PyValueError::new_err(format!("notification is not a valid NotificationWire dict: {e}"))
    })
}
```
**This is the chokepoint for `notify create`.** Every Python notification must round-trip through `NotificationWire`. A non-string `action_data` value (int, bool, nested dict) raises `PyValueError` here.

Python mirror is field-for-field identical — `src/sase/notifications/models.py:8-24`, `action_data: dict[str, str]`, passed via `asdict()` at `src/sase/core/notification_store_wire.py:83-84`.

---

## 2. Pending actions — the action values are **open strings**

**There is no closed Rust enum for `action`.** `NotificationWire.action` is `Option<String>`. The nearest thing to an enum is `MobileActionKindWire`, but it is a *projection*, not the storage type:

`crates/sase_core/src/notifications/mobile.rs:85-94`:
```rust
#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum MobileActionKindWire {
    PlanApproval, Hitl, UserQuestion, LaunchApproval, NonAction, Unsupported,
}
```

**Unknown action → fallback variant, never an error.** Two independent `match` ladders both end in a catch-all:

`mobile.rs:724-733`:
```rust
fn mobile_action_kind(action: Option<&str>) -> MobileActionKindWire {
    match action {
        Some("PlanApproval") => MobileActionKindWire::PlanApproval,
        Some("HITL") => MobileActionKindWire::Hitl,
        Some("UserQuestion") => MobileActionKindWire::UserQuestion,
        Some("LaunchApproval") => MobileActionKindWire::LaunchApproval,
        None => MobileActionKindWire::NonAction,
        Some(_) => MobileActionKindWire::Unsupported,   // <-- fallback
    }
}
```
`pending_actions.rs:438-446` duplicates this logic as `action_kind_from_str` with `_ => MobileActionKindWire::Unsupported`. **These two functions are near-duplicates and must stay in sync** — a refactor should collapse them.

Deserialize never errors on an unknown action. But `Unsupported` means: `actionable: false` on the card (`mobile.rs:361-368`), `pending_action_from_notification` returns `None` (`pending_actions.rs:70-78`), and state is forced to `Unsupported` (`mobile.rs:486-491`). **So an unknown action is silently non-actionable, not rejected.** For a generic `notify create` this is the key risk: a typo'd action string produces a notification that appears fine and quietly does nothing.

### Where each string is hardcoded in Rust

| String | Rust sites |
|---|---|
| `PlanApproval` | `mobile.rs:419, 726`; `pending_actions.rs:362, 406, 440`; `store.rs:677`; `host_bridge.rs:651` |
| `UserQuestion` | `mobile.rs:449, 728`; `pending_actions.rs:382, 407, 442`; `store.rs:677`; `host_bridge.rs:741` |
| `LaunchApproval` | `mobile.rs:463, 729`; `pending_actions.rs:391, 408, 443`; `host_bridge.rs:789` |
| `HITL` | `mobile.rs:432, 727`; `pending_actions.rs:372, 411, 441`; `host_bridge.rs:700` |
| `ViewErrorReport` | `mobile.rs:396`; `store.rs:660, 713` |
| `JumpToAgent` | `store.rs:646, 713` (dismissal matching only) |
| `JumpToMentorReview` | `mobile.rs:408` (priority only) |
| `JumpToChangeSpec` | **Not in sase_core.** Only `crates/sase_gateway/src/wire.rs:765, 832` as an error `target` string, plus test fixtures |
| `memory_review` | **Zero occurrences in Rust.** Python-only: `src/sase/ace/tui/modals/notification_modal_constants.py:16`, `_notification_modal_flow.py:196` |

Note the asymmetry: `PlanApproval`/`UserQuestion` are matched in `store.rs:677` for agent dismissal but **`LaunchApproval` is absent from that list** — launch notifications are not dismissed when their agent is killed. Possibly a latent bug worth confirming during the refactor.

---

## 3. Mobile action details — typed per-action structs projected from a string map

`MobileActionDetailWire` is an **internally-tagged closed enum** (`mobile.rs:107-148`), `#[serde(tag = "kind", rename_all = "snake_case")]`, with a **different typed shape per variant**:

```rust
pub enum MobileActionDetailWire {
    PlanApproval  { identity, state, response_dir: Option<String>, plan_file: Option<String>, choices: Vec<PlanActionChoiceWire> },
    Hitl          { identity, state, artifacts_dir: Option<String>, workflow_name: Option<String>, choices: Vec<HitlActionChoiceWire> },
    UserQuestion  { identity, state, response_dir: Option<String>, question_count: u32, choices: Vec<QuestionActionChoiceWire> },
    LaunchApproval{ identity, state, response_dir: Option<String>, request_id: Option<String>,
                    source_surface: Option<String>, slot_count: u32, choices: Vec<LaunchActionChoiceWire> },
    NonAction     { state },
    Unsupported   { identity, state, action: Option<String> },
}
```

**`action_data` is a generic string map at rest, projected into typed fields at read time.** `mobile_action_detail_from_notification` (`mobile.rs:413-492`) is the projection. The critical part — **numeric fields are parsed out of strings with a silent `unwrap_or(0)` fallback**:

```rust
question_count: notification.action_data.get("question_count")
    .and_then(|value| value.parse::<u32>().ok())
    .unwrap_or(0),
```
```rust
slot_count: notification.action_data.get("slot_count")
    .and_then(|value| value.parse::<u32>().ok())
    .unwrap_or(0),
```

**This directly answers your question.** A generic `notify create` **can** express all three payloads — every field is projected from `action_data: BTreeMap<String, String>` plus `files[0]` — but with these caveats:
- Everything must be a **flat string→string map**. No nesting, no ints, no bools. `slot_count: 3` must be sent as `"3"`.
- A malformed numeric string degrades to `0` silently, no error.
- `plan_file` is **not** in `action_data` — it comes from `notification.files.first()` (`mobile.rs:423`). Plan approval also *requires* non-empty `files` at execution time (`host_bridge.rs:661-663`, `MissingTarget("plan_file")`).

The `action_data` keys Rust reads: `response_dir`, `plan_file`(via files), `artifacts_dir`, `workflow_name`, `question_count`, `request_id`, `source_surface`, `slot_count`, `cl_name`, `raw_suffix`, `agent_cl_name`, `agent_timestamp`, `agent_root_timestamp`.

Choice enums are all **closed** and snake_case-serialized (`mobile.rs:178-263`): `PlanActionChoiceWire{Approve,Run,Reject,Epic,Feedback}`, `HitlActionChoiceWire{Accept,Reject,Feedback}`, `QuestionActionChoiceWire{Answer,Custom}`, `LaunchActionChoiceWire{Approve,Reject,Feedback}`. These are **hardcoded, not derived from the notification** — `mobile.rs:424-430` always emits all five plan choices regardless of payload.

Response-file names are also hardcoded per kind (`mobile.rs:573, 612, 668, 718`): `plan_response.json`, `hitl_response.json`, `question_response.json`, `launch_response.json`.

---

## 4. Wire versioning / schema_version

Three **independent, unsynchronized** constants:

| Constant | Value | File:line |
|---|---|---|
| `NOTIFICATION_STORE_WIRE_SCHEMA_VERSION` | `1` | `wire.rs:5` |
| `PENDING_ACTION_STORE_WIRE_SCHEMA_VERSION` | `2` | `pending_actions.rs:17` |
| `MOBILE_NOTIFICATION_WIRE_SCHEMA_VERSION` | `2` | `mobile.rs:8` |

**Crucially: `NotificationWire` itself has NO `schema_version` field.** The version only appears on the *envelope* types (`NotificationStoreSnapshotWire`, `NotificationUpdateOutcomeWire`, `wire.rs:54-73`) — it is stamped on output and **never validated on input**. Every JSONL row on disk is unversioned.

The only place a version is actually *checked* is `validate_schema` (`mobile.rs:925-938`), and only for inbound mobile action requests:
```rust
fn validate_schema(schema_version: u32) -> Result<(), MobileActionPlanErrorWire> {
    if (1..=MOBILE_NOTIFICATION_WIRE_SCHEMA_VERSION).contains(&schema_version) {
        return Ok(());
    }
    Err(plan_error(MobileActionPlanErrorCodeWire::InvalidRequest, ...))
}
```
This accepts a **range** `1..=2` — a deliberate backward-compat window.

**How compat is actually handled today (all implicit, no versioning):**
1. `#[serde(default)]` on all optional fields → old rows load. Fixture `store_contract.jsonl` line 2 is literally `{"id": "legacy-minimal", "sender": "legacy", "timestamp": "..."}` and loads fine.
2. Unknown action → `Unsupported` fallback, never an error.
3. Bad rows counted and skipped, never fatal.
4. Legacy migration is a **one-off bespoke shim**, not a version mechanism: `merge_legacy_telegram_pending_actions` (`pending_actions.rs:272-358`) parses a completely different Telegram JSON shape into `PendingActionWire`, tagging it `transport: "telegram_legacy"`.

**Forward compat is where this breaks — and it's a live refactor hazard.** Because there is no `deny_unknown_fields` *and* no `#[serde(flatten)] extra` catch-all, an unknown field:
- deserializes without error (looks safe), then
- is **permanently dropped** the next time any code path calls `rewrite_notifications` or `apply_notification_state_update` — since `merge_and_rewrite_notifications_unlocked` (`store.rs:506-520`) reads rows into `NotificationWire` and writes them back.

So if a generic `notify create` were to add a field (say `schema_version` or a `payload` blob) on the Python side only, marking a notification read from the ACE TUI would silently destroy it. **Any new field must be added to `NotificationWire` in Rust first.**

---

## 5. Tags, priority, senders, is_error

**Tags:** `tags: Vec<String>` (`wire.rs:16-17`), free-form. Rust **never inspects tag contents** — it only round-trips them (`store.rs`) and copies to the card (`mobile.rs:375`). All tag semantics are Python: `normalize_notification_tags` (`src/sase/notifications/models.py:27-42`) lowercases, strips, dedupes. Test: `notification_tags_round_trip_through_append_load_and_rewrite` (`notification_store_parity.rs:149`).

**Priority — computed, not stored.** There is no `priority` field on `NotificationWire`. It is derived (`mobile.rs:400-411`):
```rust
pub fn mobile_notification_priority_from_wire(notification: &NotificationWire) -> bool {
    if mobile_notification_error_from_wire(notification) {
        return false;
    }
    matches!(
        notification.action.as_deref(),
        Some("PlanApproval" | "UserQuestion" | "JumpToMentorReview") | Some("LaunchApproval")
    ) || matches!(notification.sender.as_str(), "axe" | "crs")
}
```
`priority` *does* appear on `MobileNotificationCardWire` (`mobile.rs:49`) as a computed projection.

**is_error — also computed** (`mobile.rs:393-398`):
```rust
pub fn mobile_notification_error_from_wire(notification: &NotificationWire) -> bool {
    notification.action.as_deref() == Some("ViewErrorReport")
        && matches!(notification.sender.as_str(), "axe" | "user-agent")
}
```
Error and priority are **deliberately disjoint** — errors early-return `false` from priority. Locked by test `priority_and_error_classifiers_are_disjoint` (`mobile.rs:1357-1389`).

**Senders known to Rust** (all bare string comparisons, no enum): `"axe"`, `"crs"`, `"user-agent"`. Used in `mobile.rs:397, 410` and `store.rs:660, 709`.

**Counting** (`store.rs:611-628`) — this is what drives the unread badge, and the ordering is significant:
```rust
for n in notifications {
    if n.read || n.silent { continue; }
    if n.muted { counts.muted += 1; }
    else if is_error(n) { counts.errors += 1; }
    else if is_priority(n) { counts.priority += 1; }
    else { counts.rest += 1; }
}
```
`NotificationCountsWire` (`wire.rs:34-41`) has `priority`, `errors` (`#[serde(default)]` — added later), `rest`, `muted`.

**This is a hard constraint on your refactor.** Priority and error classification are **hardcoded functions of `(action, sender)` in Rust**. A generic `notify create` cannot make a notification priority or error except by choosing one of those exact action strings or sender names. If the refactor introduces a new action name for plans/questions/launches, **priority classification silently breaks** and those notifications drop into `rest`. If you want data-driven priority, `NotificationWire` needs a real field (and see §4 about adding fields).

---

## 6. Tests covering notifications / pending actions

**`crates/sase_core/tests/notification_store_parity.rs`** — 28 integration tests, 1154 lines. Named "parity" because they lock Rust behavior against the prior Python implementation. Notable:
- `notification_json_shape_uses_expected_wire_keys` (`:913`) — **the exact JSON contract**; any field addition/rename breaks this
- `notification_counts_match_python_priority_rules` (`:169`)
- `notification_phase1_contract_fixture_loads_with_expected_counts` (`:84`) — against `tests/fixtures/notifications/store_contract.jsonl`
- `notification_loads_legacy_defaults_and_skips_bad_rows` (`:52`)
- `notification_append_counts_produces_byte_identical_jsonl` (`:985`), `notification_rewrite_counts_produces_byte_identical_jsonl` (`:1008`)
- `notification_dismiss_matching_agents_covers_notification_action_shapes` (`:408`), `..._matches_question_root_identity` (`:469`), `..._matches_question_child_identity` (`:586`), `..._covers_user_agent_view_error_report` (`:620`)
- `notification_append_plus_rewrite_concurrency_preserves_valid_rows` (`:870`), `..._counts_concurrency_...` (`:1114`) — threaded
- `notification_rewrite_preserves_unseen_rows` (`:1032`), `..._counts_...` (`:1057`), `notification_rewrite_all_preserves_unseen_rows` (`:1083`) — lock the merge semantics
- `notification_expire_snoozes_handles_aware_and_naive_timestamps` (`:358`)

**Unit tests in `mobile.rs:960-1390`** (9 tests):
- `mobile_notification_contract_snapshot_is_stable` (`:986`) — golden JSON vs `tests/fixtures/mobile/mobile_notification_contract.json`
- `action_result_contract_snapshot_is_stable` (`:1068`) — golden vs `tests/fixtures/mobile/mobile_action_result_contract.json`, covers plan+hitl+question+launch
- `launch_approval_detail_exposes_preview_identity` (`:1017`) — **inline exact-JSON assertion**, will break on any `LaunchApproval` shape change
- `plan_response_planner_covers_all_choices` (`:1134`), `launch_response_planner_covers_all_choices` (`:1281`), `hitl_response_planner_matches_existing_shapes` (`:1174`), `question_planner_supports_index_label_id_and_custom_answers` (`:1201`)
- `priority_and_error_classifiers_are_disjoint` (`:1357`), `prefix_resolution_makes_collisions_explicit` (`:1315`), `planner_errors_are_deterministic` (`:1336`)

**Unit tests in `pending_actions.rs:481-642`** (5 tests): `pending_store_registers_and_resolves_prefixes`, `pending_state_detects_stale_and_external_plan_response`, `launch_approval_is_a_pending_action_kind`, `pending_store_merges_legacy_telegram_shape`, `cleanup_stale_pending_actions_removes_only_expired_entries`.

**Also:** `crates/sase_core_py/src/lib.rs:4428-4700` (PyO3 binding tests), `crates/sase_gateway/src/routes.rs:3705-6047` (gateway route tests). Python side: `tests/test_core_notification_store.py`, `tests/test_notification_catalog.py`, `tests/test_launch_approval.py`, `tests/test_plan_approve_cli.py`, `tests/test_plan_reject_cli.py`.

---

## Synthesis: what constrains a generic `notify create`

`sase notify create` **already exists** (`src/sase/main/notify_handler.py:37-70`) and already accepts a generic payload from stdin JSON — `sender`, `notes`, `files`, `tags`, `action`, `action_data` — plus `--sender`/`--tag` flags. The three senders you want to unify are `notify_plan_approval` (`src/sase/notifications/senders.py:231`), `notify_user_question` (`:196`), and launch approval, all of which build `action_data: dict[str, str]` and call `append_notification`.

**Can a generic constructor express plan/question/launch payloads? Yes — with these five constraints:**

1. **`action_data` is `BTreeMap<String, String>`.** Flat, string-valued. `slot_count`/`question_count` must be stringified; bad values degrade to `0` silently rather than erroring. A non-string value raises `PyValueError` at `sase_core_py/src/lib.rs:2863`.
2. **`plan_file` rides in `files[0]`, not `action_data`** (`mobile.rs:423`), and is mandatory for plan execution (`host_bridge.rs:661`). A generic constructor must preserve `files` ordering.
3. **`action` must remain one of the exact literals** `PlanApproval` / `UserQuestion` / `LaunchApproval` / `HITL`. They are hardcoded at ~15 Rust sites across 4 files. Renaming requires a coordinated Rust change; a typo silently produces a non-actionable notification.
4. **Priority/error classification is a hardcoded `(action, sender)` function in Rust** (`mobile.rs:393-411`). Not expressible via `tags` or any generic field. New action names break badge counts silently.
5. **No field may be added Python-side only.** No `deny_unknown_fields` *and* no flatten-catch-all means extra fields survive a read but are destroyed on the next rewrite (`store.rs:506-520`).

**Lowest-risk path:** keep `NotificationWire` byte-identical, route the three senders through one Python constructor that emits the same `action` + `action_data` + `files` shape. Zero Rust change, all 28 parity tests + 2 golden fixtures stay green.

**If the refactor must change the wire** (new field, or a `schema_version` on the row), the required Rust edits are: `wire.rs:8-32` (struct), `notification_store_parity.rs:913` (exact-keys test), `tests/fixtures/notifications/store_contract.jsonl`, `tests/fixtures/mobile/mobile_notification_contract.json`, and Python's `models.py:9-24` — in that order, Rust first.

**Two cleanups worth folding in:** `mobile_action_kind` (`mobile.rs:724`) and `action_kind_from_str` (`pending_actions.rs:438`) are duplicate string→enum ladders that must stay in sync; and `LaunchApproval` is missing from the agent-dismissal match at `store.rs:677` where `PlanApproval`/`UserQuestion` are handled — likely a bug, worth confirming separately rather than assuming.

All four agents are in. Let me verify the two most surprising Rust claims before I put them in writing.

Both verified: `store.rs:677` matches only `Some("PlanApproval" | "UserQuestion")` — `LaunchApproval` is genuinely absent from agent-dismissal — and priority is a hardcoded `(action, sender)` function in Rust. Now I'll write the report.

Research written to `sase/repos/research/202607/unified_notification_constructor.md`. No `just check` needed — the only change is a markdown file in the research sidecar, which is both a different repo and covered by the research-docs exception.

**The headline: three of your premises need correcting before design starts.**

**There are no hooks.** Plan and question both work by writing a marker file and then SIGTERM-ing the runner's own process group (`plan_propose_handler.py:90` → `run_agent_exec.py:154`). Launch doesn't even do that — it's a plain CLI call. The "via hook" docstring at `senders.py:205` is just stale.

**`improve_plan` and `tester` aren't unfinished machinery — they're inactive example files for a feature that shipped.** They're two YAML files under `xprompts/examples/`, kept inactive by a non-recursive glob (`discovery.py:106`), and no Python code branches on either id. The evaluator, `--with`/`--without` flags, and modal toggles all exist and work. Deleting the two files costs almost nothing — but it also unblocks nothing. What actually entangles with your refactor is the *member-options* layer built on top: `member_options`/`default_member_ids` in `plan_request.json` and the `"Also run: …"` note at `senders.py:274-280`. That's the plan-specific bulge that stops the three gates from being the same shape. I've broken this into three separable layers in the doc, because "remove improve_plan/tester" could mean any of them.

**`sase notify create` is already closer than it looks** — `append_notification` already registers pending actions internally, so the CLI can already mint an actionable PlanApproval today.

**The genuinely useful finding:** the unifying abstraction isn't "a notification," it's a **request/response gate** — a `response_dir` holding `<kind>_request.json` and `<kind>_response.json`, with the notification as just the doorbell. `pending_actions.py:308-345` hard-codes that identical predicate four times, varying only filenames. "Significantly enhanced" most likely means `notify create` grows from *append a row* to *open a gate*.

**The constraint that would bite hardest:** priority is a hardcoded `(action, sender)` match in Rust (`mobile.rs:400-411`, verified directly). Collapsing to one generic action string would **silently** drop plan/question/launch out of the badge counts and make them non-actionable on mobile. So: generalize the plumbing, keep the four action literals as the type tag.

I also found three latent bugs sitting in the refactor's path, two verified first-hand: TUI-answered questions never get marked handled (`_notification_modal_responses.py:36` early-returns for non-plan), `LaunchApproval` is missing from Rust's agent-dismissal match (`store.rs:677`), and **nothing actually polls `launch_response.json`** — the "poller" is one line of prose in `sase_run.md:100` telling the LLM to do it.

The doc ends with 17 questions grouped into intent/scope, the removal, gate design, and rollout. The three I'd most want answered first: does "use `sase notify create`" mean subprocess or shared constructor; which of the three removal layers you actually want gone; and whether launch's inversion (approver does the work, rather than unblocking a waiter) is part of the abstraction or an acknowledged exception.

One caveat worth flagging: the existing `dynamic_agent_families_v1_v2_design.md` describes much of this as unbuilt "v2 direction," and it's now out of date — I've noted it as superseded so it doesn't mislead whoever picks this up.

I made that file this session, so I'll commit it.

Single untracked file, and both finalizer entries point at the same path, so one commit covers both.

History uses `docs(research):` for these. Writing the commit message now.

Committed and clean — working tree has nothing outstanding and `main` is level with `origin/main`, so the push went through.

**What I did:** committed the research doc I wrote this session to the research sidecar as `aee0ef6 docs(research): analyze unifying plan/question/launch notifications`, following the `docs(research):` tag the repo's history already uses. The two entries the finalizer listed (linked repo `research` and sidecar `sase-org/sase--research`) resolve to the same path, so the single commit covered both. No `just check` was needed — the change is one markdown file in the research sidecar, a different repo from the sase workspace and covered by the research-docs exception anyway.

The doc itself (`202607/unified_notification_constructor.md`, 389 lines) is unchanged from what I described earlier: it corrects the three starting premises (there are no hooks; `improve_plan`/`tester` are inactive examples of a shipped feature rather than unfinished machinery; `notify create` already registers pending actions), identifies the request/response gate as the real unifying abstraction, records the Rust wire constraints that would bite a naive generalization, flags three latent bugs, and ends with the 17 questions.
