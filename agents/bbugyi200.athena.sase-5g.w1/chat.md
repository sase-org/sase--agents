# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 09:40:18 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-5g.w1
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260706_071546.md`

## Prompt

#gh:gh_sase-org__sase 
%w:sase-5g Can you do some research into the recently implemented "dynamic agent families" (see the sase-5f and sase-5g epic beads and related git commits) with the goal of helping me produce a user manual that describes their design and how to use them? Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.
 %m:claude/claude-fable-5

## Response

I'll research the dynamic agent families feature. Since I'll be working with beads, let me first load the beads reference.

Both epics are closed. Now let me read the epic plan files and gather the related git history.

I'll research the Dynamic Agent Families v1 implementation. Let me start by examining the commits and key files in parallel.

Let me read the directive parsing, plan_chain, and the xprompt/prompt helper files.

I'll research the Dynamic Agent Families v2 implementation. Let me start by examining the relevant commits and finding the key files.

Let me read the xprompt YAML files, plan_chain, and search for the relevant plan_chain functions.

Now let me read the current state of the key files. Let me explore the module layout and read the main files.

Let me read the relevant portions of plan_chain.py.

I'll research this systematically. Let me start by examining the two key commits and finding the relevant files.

Now let me read the standard plan chain modules and custom definitions.

Let me read the wait dependency resolution, runner cancel behavior, artifacts metadata, and test file.

Let me read the core files in parallel.

Now let me read the custom_definitions modules and the facade.

The design doc gives me the full architecture story. Let me check what user-facing documentation already exists (v1 Phase 5 required docs) while the agents finish.

Let me read the create_followup_artifacts function, the runner cancel logic, and the test file.

Now let me read the CLI parsers, launch handler, and approval actions.

Now let me read the loading module, example YAMLs, and prompt templates.

Now let me read the gating rule, notifications, skill file, and TUI/mobile pieces.

Let me read the runner cancellation logic and the wait/directives wiring.

Now let me read pending_actions.py, the TUI modal, mobile actions, and search for auto-approve env vars.

Now let me read the axe runner files, CLI parser, and modals.

There's existing documentation in `docs/xprompt.md`. Let me read those sections and search for v2 docs.

Let me examine the directives wiring, wait behavior, and the test file.

Now let me read the modals, config, and handlers.

Now let me search for auto-approve env vars and check the notification modal flow and priority.

Let me look at the directive extraction for name (colon form handling), docs, and the run_agent_directives family wiring.

Let me read the axe runner files, config, and plan approval actions.

The auto-approve references found are all for *plan* approval, not launch. Let me verify whether launch auto-approve exists anywhere and check the gating in `sase run`, the entry/parser wiring, and priority.

Let me read the docs sections and the directive collect/extract code for colon form handling.

Let me read the execution loop files and the role_completed emission.

Let me read the plan handler files, plan approval actions, and xprompt handler.

Let me read the directive collection and extraction code to confirm colon-form vs paren-form behavior.

Auto-approve for launch is not present; only plan auto-approve exists. Let me confirm by checking the tests and the entry/parser wiring, plus how `sase run` reaches the gate.

Let me read the remaining key files: questions handler, plan approval actions, plan utils, xprompt handler, config schema.

Let me read special_cases.py to understand the `sase run` path and %n family attach handling, and check the test files.

Let me read the xprompt handler, plan utils, config schema, and status label rendering.

Let me look at the config schema, status label rendering, notification senders, and docs.

Let me examine the c5f18ae90 edge-case fixes and search for terminal outcome handling.

Let me read the test files to confirm gating and %n family attach behavior.

Let me read the c5f18ae90 tale and search for terminal outcome mappings and the WAITING child row rendering.

Now let me read the main test file and check TUI notification modal flow, plus how the TUI @ launch and family attach differ from the gated path.

Let me examine the outcome mapping markers and the WAITING child row rendering in the runner wait.

Let me examine the TUI notification modal flow and the mobile notifications wiring.

Now let me read the status label rendering (5g.9), notification senders, and notification modals.

All background context gathered. Waiting for the three code-research agents to report back; I'll write the research doc once their findings arrive.

Let me check the mobile notification snapshot for launch wire fields, search for any Telegram/docs, and confirm the user-typed launch paths that stay ungated.

Let me find how custom_role_label renders into display_status in the Agent model.

Let me trace the PLAN DONE / TALE DONE / EPIC CREATED terminal-status mapping and the WAITING child-row TUI rendering.

Let me read the notification senders (remote/Telegram) and the notification modals for member handling.

Let me check the mobile snapshot wire fields, the Justfile skill-generation change, and confirm no user docs exist.

Let me read the done-loader outcome-to-status mapping and the family status rendering.

Let me read the golden harness README, the mobile bridge test, and check the run choice remote behavior.

The Justfile references `get_auto_launch_approval_action`. Let me search for it and confirm whether launch auto-approve is implemented.

Let me find how the "run" remote choice is wired and check the mobile bridge test.

Let me verify the "raw -- in plain names" rejection and check the launch_validation wiring.

Let me read the launch_validation.py section on the `--` rejection to capture exact messages.

Let me verify the embedded-workflow parent inference wiring and confirm the `::` shorthand and registration.

I have gathered all the necessary facts. Let me do a final verification of the `sase launch request` handling of `-f` and confirm the response_dir path helper.

Let me verify the "run" choice fix diff and check the TUI modal remote choices.

Let me check the a660d9227 changes to _embedded_workflows.py for the parent-inference wiring with fenced ranges.

Let me read the remaining notification modal sections that write member selections.

Let me check the loop-cap hard-stop notification and finalize behavior.

Let me read the remaining plan_chain suffix-parsing branch to confirm custom-role resolution.

Let me verify the pytest marker registration and confirm test locations.

I now have all verified facts. Here is the report.

# Agent-Initiated Launch Approval (Dynamic Agent Families v2, phases 7-8 / epic sase-5g)

Scope confirmed from commits `19a07856d` (5g.7, pending-action infrastructure) and `deaf571e0` (5g.8, approved launch requests), read against the current tree.

## 1. Launch request flow

**How an agent submits a request.** Two entry points, both landing in `create_launch_approval_request`:

- Generated skill workflow: the agent writes a JSON file and runs `sase launch request -f launch_request.json -o json` (CLI parser `src/sase/main/parser_launch.py:47-101`; handler `src/sase/main/launch_handler.py:55-89`).
- Implicit gating path: when a running agent invokes `sase run ...`, `launch_query` diverts it to `create_launch_approval_request_from_prompt(query, reason="Running agent requested a detached launch.", source_surface="agent_skill")` (`src/sase/main/query_handler/_launch.py:41-59`).

**`sase launch request` options** (`src/sase/main/parser_launch.py:47-101`): positional `payload` (inline JSON, or `@PATH`); `-a/--approval` (default `required`); `-f/--file` -> `payload_file`; `-m/--max-slots` (int, default `1`); `-o/--output` (`text|json`, default `text`); `-p/--prompt`; `-r/--reason`; `-s/--source`. Passing both `payload` and `--file` is rejected (`launch_handler.py:69-72`).

**Request JSON schema** (normalized in `src/sase/agent/launch_request.py:190-243`; `LAUNCH_REQUEST_SCHEMA_VERSION = 1` at line 19):
- `schema_version` — must equal `1`, else `LaunchRequestError("invalid_schema", "schema_version", "schema_version must be 1")`.
- `prompt` — required non-empty string (`"prompt is required"`).
- `reason` — optional; defaults to `"Detached launch requested."`; must be non-empty (`"reason is required"`).
- `approval` — defaults to `"required"`; only `"required"` is accepted, else `LaunchRequestError("unsupported_approval", "approval", "only approval='required' is supported")`.
- `max_slots` — defaults to `1`; must be an int `>= 1` (`"max_slots must be an integer"` / `"max_slots must be at least 1"`).
- `family_type` — optional string (`launch_request.py:236-242`).

If the planned fan-out expands to more slots than `max_slots`, creation fails with `LaunchRequestError("max_slots_exceeded", "max_slots", "launch request plans N slot(s), max_slots is M")` (`launch_request.py:85-90`).

**Files written** (`src/sase/agent/launch_preview.py:21-23, 108-135`), in directory `sase_subdir("launch_requests") / <request_id>` (`launch_preview.py:116-118`):
- `launch_request.json` — full request payload, pretty JSON, `sort_keys=True`.
- `launch_preview.md` — human-readable preview (`_render_launch_preview_markdown`, `launch_preview.py:138-179`: `# Launch Preview`, Request/Source/Slots/Policy header, per-slot Kind/Planned name/Project/Model/Prompt SHA-256/prompt snippet).
- `launch_response.json` — not created at request time; any pre-existing one is deleted (`launch_preview.py:128-129`).

**`launch_request.json` contents** = the preview payload (`build_launch_preview_request`, `launch_preview.py:83-105`: `schema_version`(=1, preview schema), `request_id`, `created_at_unix`, `source_surface`, `all_or_nothing: true`, `response_file: "launch_response.json"`, `submitted_prompt_snippet`, `submitted_prompt_sha256`, `launch_kind`, `slot_count`, `fanout_counts`, `plan`, `slots[]`) plus three keys added at `launch_request.py:99-104`: `launch_request` (the normalized request), `requester` (subset of env: `SASE_AGENT`, `SASE_AGENT_NAME`, `SASE_ARTIFACTS_DIR`, `SASE_AGENT_WORKFLOW_NAME`, `launch_request.py:326-333`), and `dispatch` (`{"cwd": <cwd>, "prompt": <prompt>}`).

**Request id format**: `f"launch-{uuid4()}"` (`launch_preview.py:26-28`), e.g. `launch-<uuid>`.

**CLI output** (`launch_handler.py:187-205`): text mode prints `Launch approval requested <request_id> <response_dir>`; json mode prints an object with `request_id`, `notification_id`, `response_dir`, `request_file`, `preview_file`, `response_file`. The agent-gated `sase run` path instead prints `Launch approval requested: <request_id>` and `Response: <response_path>` (`_launch.py:57-58`).

## 2. The LaunchApproval pending action

**Notification** (`src/sase/notifications/senders.py:292-325`, `notify_launch_approval`): `sender="launch"`, `action="LaunchApproval"`, `notes=["Launch approval requested: N slot(s)", "Source: <surface>"]`, `files=[preview_file, request_file]`, `action_data={"response_dir", "request_id", "source_surface", "slot_count"}`, `tags=["launch"]`. It is classified priority (red indicator) via `_PRIORITY_ACTIONS` in `src/sase/notifications/priority.py:11-13`. TUI toast text/labels added in `src/sase/ace/tui/actions/agents/_toasts.py` (`"Launch approval requested"`, labels `("launch approval","launch approvals")`).

**Pending-action store** (`src/sase/notifications/pending_actions.py`): `LaunchApproval` maps to action kind `"launch_approval"` (`:26-32`); `_required_target_missing` requires `response_dir` (`:348-353`); `_externally_handled` treats it done when `launch_response.json` exists or `launch_request.json` is gone (`:337-345`).

**TUI modal** (`src/sase/ace/tui/modals/launch_approval_modal.py`): `LaunchApprovalModal` renders `launch_preview.md` as syntax-highlighted markdown; bindings `a`=Approve, `r`=Reject, `q`/`escape`=Cancel, plus scroll keys `ctrl+d/ctrl+u/g/G` (`:30-39`). Returns `LaunchApprovalResult(action, feedback)`. Wired through `handle_launch_approval` (`src/sase/ace/tui/actions/agents/_notification_modals.py`, added in 5g.7): it checks `response_dir`/`launch_request.json` exist, writes `launch_response.json` via `write_workflow_action_response`, then calls `run_launch_side_effects`. LaunchApproval is kept unread until answered and its pending actions are refreshed (`_notification_modal_flow.py` changes).

Note: the TUI `handle_launch_approval` path writes the response and runs side effects, but does **not** itself dispatch the launch — only `execute_launch_approval_response` (CLI/mobile) performs the approve-time dispatch (see below).

**CLI approve/reject** (`parser_launch.py:22-45`, `launch_handler.py:29-40, 115-174`):
- `sase launch approve <selector>`
- `sase launch reject <selector> [-f/--feedback <text>]`
- `<selector>` = full launch request id, full notification id, or unique notification-id prefix (`_resolve_launch_notification`, `launch_handler.py:130-151`). Ambiguous prefix -> `LaunchApprovalActionError("ambiguous_prefix", ...)`; none -> `("not_found", selector, "pending launch approval not found")`. Availability is re-checked: `already_handled` -> `"action already handled"`, `stale` -> `"action is stale"` (`launch_handler.py:154-174`). CLI errors exit code 2 (`launch_handler.py:44-49`).

**What approve/reject does** (`src/sase/launch_approval_actions.py:45-157`, `execute_launch_approval_response`):
- Validates `response_dir` exists and still contains `launch_request.json` (missing dir -> `invalid_request`; missing request -> `conflict_already_handled` `"launch request was already consumed"`).
- Response JSON: approve -> `{"action":"approve"}`; reject -> `{"action":"reject"}` (+`feedback` if given); `feedback` choice -> `{"action":"reject","feedback":...}` (feedback required else `invalid_request`).
- Writes `launch_response.json` **write-once** with `open("x")`; a pre-existing file raises `LaunchApprovalActionError("conflict_already_handled", ..., "response already exists")` (`:160-172`). This is the concurrency guard against double-resolution.
- On approve it then dispatches (`:74-93`): success adds `dispatch_status:"launched"`, `launched_count:N`, and message `"Launch approved and dispatched N agent(s)"`; failure rewrites the response with `dispatch_status:"failed"` + `dispatch_error` and raises `LaunchApprovalActionError("dispatch_failed", ...)`.
- Side effects (`run_launch_side_effects`, `:105-121`): best-effort `mark_dismissed` and `mark_already_handled(source="launch_response", action=choice)`.

**Revalidation on approval** (`dispatch_approved_launch_request`, `launch_request.py:128-182`): re-reads `launch_request.json`, validates the `dispatch` block (`dispatch.prompt` non-empty, `dispatch.cwd` present and an existing directory — else `invalid_request`), `os.chdir` into `dispatch.cwd`, and calls `launch_agents_from_cwd(prompt)`. The prompt is re-parsed/re-planned fresh at dispatch time (not reusing the preview plan), then cwd is restored.

**All-or-nothing batch semantics**: the preview always records `all_or_nothing: true` (`launch_preview.py:88`); the slot-count vs `max_slots` gate is enforced at request creation (`launch_request.py:85-90`). At approval, multi-prompt fan-out is dispatched by `launch_agents_from_cwd`, whose partial-failure rollback (`MultiPromptPartialLaunchError`) is handled in the ungated path at `_launch.py:64-78`.

## 3. The gating rule

Single gate function: `running_agent_context_requires_launch_approval()` = `bool(os.environ.get("SASE_AGENT"))` (`src/sase/agent/launch_request.py:185-187`).

- It is consulted in exactly one place: `launch_query` (the `sase run` CLI path) at `src/sase/main/query_handler/_launch.py:47`. When `SASE_AGENT` is set, `sase run` creates a LaunchApproval request (`source_surface="agent_skill"`) and exits 0 instead of spawning; otherwise it calls `launch_agents_from_cwd(query)` directly (`_launch.py:61-88`).
- Source-surface labeling mirrors this: `_default_source_surface` returns `"agent_skill"` when in an agent context, else `"cli"` (`launch_request.py:336-337`).

**Ungated (user-typed) surfaces** call `launch_agents_from_cwd` directly and never touch the gate:
- TUI `@` launch / user CLI without `SASE_AGENT` set (`_launch.py:62`).
- Mobile/Telegram bridge: `src/sase/integrations/_mobile_agent_launch.py:84` calls `launch_agents_from_cwd(prompt)` directly (no `SASE_AGENT` check).

**User-typed `%n` family attach stays ungated**: family expansion happens inside `launch_agents_from_cwd` (family code in `src/sase/agent/family_attach.py`, `multi_prompt_launcher.py`, etc.), not in `launch_query`, and there is no separate `SASE_AGENT`/approval check on the family path. So a user typing `%n(parent, reviewer) ...` in `sase run` (or TUI/Telegram) with `SASE_AGENT` unset launches directly. Conversely, an agent (`SASE_AGENT` set) typing the same `%n(...)` prompt is gated — confirmed by `test_launch_query_from_agent_context_requests_approval` in `tests/test_special_cases.py:182-222`, which uses prompt `"%n(foo, reviewer)\nDo work"` with `SASE_AGENT=planner` and asserts it requests approval and does not launch.

## 4. Auto-approve

Launch auto-approve is **not implemented** in phases 7-8. Evidence:
- The request `approval` field only accepts `"required"`; any other value is rejected (`launch_request.py:209-215`). There is no path that skips the approval step for a launch.
- No launch-specific auto-approve env var or agent-meta field exists. Grep confirms every `auto_approve*` symbol in the tree is for **PlanApproval**, not launches (agent-meta `auto_approve_plan_action` / `approve`, `get_auto_plan_approval_action` in `src/sase/main/plan_approve_handler.py:57`). There is no `get_auto_launch_approval_action` in the source.
- A dangling pyvision marker `sase-5g(get_auto_launch_approval_action)` appeared transiently in `deaf571e0`'s Justfile edit, but the referenced function was never created and the marker is absent from the current Justfile (`_lint-pyvision`, `Justfile:150-151`) — i.e. auto-approve was scoped in the epic but not built in these phases.

So, for the manual: there is no env var / meta field / precedence order to document for launch auto-approve; every agent-initiated launch requires explicit user approval.

## 5. The `/sase_run` generated skill

Source: `src/sase/xprompts/skills/sase_run.md` (generated into agent skills; presence asserted by `tests/main/test_init_skills_sources.py`, which requires the strings `"sase launch request"`, `"launch_response.json"`, `"%n(parent, reviewer)"`, `"Do not run \`sase run\`"`). Front-matter: `name: sase_run`, `description: "Request a SASE agent launch through LaunchApproval instead of spawning directly."`, `skill: true`.

Instructions to agents (`sase_run.md:7-63`):
- Use this skill to start another SASE agent from inside a running agent; agent-initiated launches must go through `LaunchApproval`. Do **not** run `sase run` / `sase run -d` directly (those are user-initiated paths).
- **Request**: write a JSON file (`schema_version:1`, `prompt`, `reason`, `approval:"required"`, `max_slots:1`), then submit with `sase launch request -f launch_request.json -o json`. This writes `launch_request.json` + `launch_preview.md` and registers a pending `LaunchApproval`; it does not spawn the agent.
- **Family members**: to attach the launch to an existing family, put the `%n` directive inside the requested prompt (e.g. `%n(parent, reviewer)\nReview ...`). Use `%n(parent, @)` for the next free feedback suffix; use a concrete suffix like `%n(parent, tester)` when the role matters.
- **Outcome polling**: the JSON output includes `response_file`; poll that path until `launch_response.json` appears. Approved: `{"action":"approve","dispatch_status":"launched","launched_count":1}`. Rejected: `{"action":"reject","feedback":"..."}`. If rejected, do not spawn anyway — use the feedback to revise or continue without launching.

## 6. Telegram / mobile rendering

In-repo mobile bridge support exists; Telegram-specific rendering is delegated to external plugins (not in this repo).

- Host-side mobile action executor: `execute_mobile_launch_action(prefix, choice, *, feedback=None)` in `src/sase/integrations/_mobile_notification_actions.py:211-251`, exported via `src/sase/integrations/mobile_notifications.py`. It resolves the notification by prefix, validates `response_dir`/`launch_request.json`, and delegates to the shared `execute_launch_approval_response`, mapping errors to `MobilePlanActionError` codes (`not_found`, `ambiguous_prefix`, `conflict_already_handled`, `gone_stale`, `invalid_request`, `unsupported_action`).
- Wire fields exposed to remote surfaces come from the mobile snapshot (`src/sase/integrations/_mobile_notification_snapshot.py:79-89`): `action` (`"LaunchApproval"`), `action_state` (from `action_state_for_notification`), `display_files`/`host_files` (the `launch_preview.md` / `launch_request.json` paths), and `display_action_data`/`host_action_data` carrying `response_dir`, `request_id`, `source_surface`, `slot_count`. The rendered human artifact is `launch_preview.md`.
- Legacy Telegram integration: `src/sase/notifications/pending_actions.py:363-395` merges a legacy Telegram pending-actions file, storing transport records under `transports:[{"transport":"telegram_legacy","record":{chat_id, message_id}}]`; `merge_transport_record` (`:131-161`) lets a transport attach `chat_id`/`message_id`. No Telegram message formatting or send logic for LaunchApproval lives in this repo — it is delegated to the `sase-telegram` / `sase-core` plugins (not opened).

## 7. User-facing docs

No dedicated user-facing documentation for this feature exists in this repo. `docs/cli.md` does not list a `sase launch` command; grepping `docs/` and `README.md` for `sase launch` / `LaunchApproval` / `sase_run` returns only unrelated hits (`docs/rust_backend.md` references a `launch_query` startup benchmark; `docs/xprompt.md` is about plan-approval coder handoff). The only shipped "documentation" of the workflow is the generated skill `src/sase/xprompts/skills/sase_run.md` (item 5). If a manual section is needed, it must be authored fresh from the facts above.

The LaunchApproval//sase_run research is in — key findings: `sase launch request/approve/reject` CLI, write-once `launch_response.json`, the `SASE_AGENT` gating rule, and no auto-approve implemented. Still waiting on the v1 attach and v2 evaluator agents before writing the doc.

I now have a comprehensive, verified picture of the implementation. Here is the factual report.

# Dynamic Agent Families v2 (epic sase-5g) — As-Implemented Reference

All paths are absolute under `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10`. Line references are to the current (post-refactor) code.

---

## 1. Plan-approval choice registry

Source of truth: `src/sase/plan_approval_choices.py`.

The registry is a tuple of frozen `_PlanApprovalChoiceRecord` dataclasses (`PLAN_APPROVAL_CHOICE_RECORDS`, lines 94-212). Record fields (lines 42-60): `id`, `display_label`, `response_message`, `protocol` (a `PlanApprovalProtocolFields(action, commit_plan, run_coder)` NamedTuple), `custom_modal_key`, `review_modal_key`, `consequence_text`, `cli_kind_name`, `archive_side_effect`, `auto_mode_eligible`, `persist_action`, `status_label`, `requires_feedback`, `allow_protocol_overrides`, `allow_coder_options`.

The eight registered choices (`PlanApprovalChoiceId`, lines 13-22):

| id | label | protocol (action/commit_plan/run_coder) | custom key | review key | consequence_text | cli_kind | archive | auto-eligible | status_label | persist_action |
|----|-------|------------------------------------------|-----------|-----------|-------------------|----------|---------|---------------|--------------|----------------|
| `approve` | Approve | approve / F / T | `a` | `a` | "No SDD commit; run coder" | `approve` | yes | **yes** | PLAN APPROVED | approve |
| `run` | Run | approve / F / T | — | — | "No SDD commit; run coder" | — | **yes** | no | PLAN APPROVED | approve |
| `tale` | Tale | approve / T / T | `t` | `t` | "Commit to sdd/tales; run coder" | `tale` | yes | **yes** | TALE APPROVED | tale |
| `epic` | Epic | epic / T / T | `e` | `E` | "Commit to sdd/epics; launch bd/new_epic" | `epic` | yes | **yes** | EPIC APPROVED | epic |
| `legend` | Legend | legend / T / T | `l` | `L` | "Commit to sdd/legends; launch bd/new_legend" | `legend` | yes | **no** | LEGEND APPROVED | legend |
| `commit` | Commit | approve / T / F | — | — | — | `commit` | yes | no | PLAN COMMITTED | commit |
| `reject` | Reject | — | — | — | — | — | no | no | — | — |
| `feedback` | Feedback | — (requires_feedback=True) | — | — | — | — | no | no | — | — |

Only `approve` sets `allow_protocol_overrides=True` (so the TUI/CLI can flip commit_plan/run_coder). `approve`, `run`, `tale`, `epic`, `legend` set `allow_coder_options=True` (accept coder_prompt/coder_model). Derived tuples (lines 218-244): `PLAN_APPROVAL_MODAL_CHOICES = (approve, tale, epic, legend)`; `PLAN_APPROVAL_CLI_KINDS = (approve, commit, epic, legend, tale)`; `PLAN_APPROVAL_AUTO_MODE_CHOICES` = choices with `auto_mode_eligible` = `(approve, tale, epic)`; `PLAN_APPROVAL_REMOTE_CHOICES = (approve, run, reject, epic, legend, feedback)`.

**The "run" choice fix (5f390345a, sase-5g.2):** The `run` record sets `archive_side_effect=True` (line 126). Previously `plan_approval_actions.py` archived only when `choice in PLAN_APPROVAL_KINDS = ("approve","tale","epic","legend","commit")` — `run` was absent, so remote (Telegram/mobile) "Run" approvals did **not** copy/archive the plan into `sdd/tales/YYYYMM/`. The fix replaced that check with `approval_choice_archives_plan(choice)` (`src/sase/plan_approval_actions.py:220`, function at lines 277-280), which returns True for `run`. Now a remote "Run" approval runs the coder AND archives the plan (writing `saved_plan_path` back into `plan_response.json`, lines 220-231), matching interactive "Approve". Confirmed by `tests/test_mobile_notifications_bridge.py:297` (`test_execute_mobile_run_plan_action_archives_plan`) which asserts `_archive_plan_for_approval` is called with persisted action `"approve"`.

---

## 2. Evaluator architecture

After refactor 0ea37bfa5, the standard chain is split into a facade `src/sase/agent_family/standard_plan_chain.py` re-exporting from three modules:
- `standard_plan_chain_definition.py` — built-in definition + hashing
- `standard_plan_chain_models.py` — runtime dataclasses
- `standard_plan_chain_evaluator.py` — pure evaluator functions

**Typed events** (`standard_plan_chain_definition.py:26-30`): `HandoffEventKind = Literal["plan_submitted", "questions_submitted", "role_completed"]`. `GateRendererId = Literal["plan_approval", "user_question"]`. `RoleCompletedOutcome = Literal["success", "failed", "stopped"]`.

`HandoffEvent` (`standard_plan_chain_models.py:41-53`): fields `kind`, `interrupted_role`, `artifacts_dir`, `payload` (dict).

**Built-in `standard_plan_chain` definition** (`standard_plan_chain_definition.py:131-217`): `STANDARD_PLAN_CHAIN_ID = "standard_plan_chain"`, `STANDARD_PLAN_CHAIN_VERSION = 1`, `entry_role = "root"`.
- Roles (id → suffix → prompt_template): `root` (no suffix); `plan` (`PLAN_CHAIN_PLAN_SUFFIX`, `initial_prompt`); `q` (`--@`, `standard_question_followup_prompt`); `feedback` (`--plan-@`, `standard_feedback_replan_prompt`); `code` (`PLAN_CHAIN_CODER_SUFFIX`, `standard_coder_prompt`); `epic` (`PLAN_CHAIN_EPIC_SUFFIX`, `bd/new_epic`); `legend` (`PLAN_CHAIN_LEGEND_SUFFIX`, `bd/new_legend`); `commit` (`PLAN_CHAIN_COMMIT_SUFFIX`, terminal).
- Gates: `plan_review` (renderer `plan_approval`, choices generated from `PLAN_APPROVAL_CHOICE_IDS`); `user_questions` (renderer `user_question`, `return_to_interrupted_role=True`).
- Events: `plan_submitted`→gate `plan_review`; `questions_submitted`→gate `user_questions`; `role_completed`→`terminal=True`, `composition_rule="after_followup_workflow_including_embedded_vcs_refs"`.
- Per-choice routing helpers: `_choice_target_role` (lines 103-114), `_choice_side_effects` (lines 117-128; e.g. tale→`("write_sdd","commit_sdd","set_sase_plan_env")`, epic/legend→`("write_sdd","commit_sdd","launch_<choice>_creator")`, feedback→`("record_feedback","replan")`).
- The compiled definition is hashed with SHA-256 into `STANDARD_PLAN_CHAIN_CONFIG_HASH` (lines 231-240).

**Family state persisted on artifacts** (`standard_plan_chain_models.py`): `FamilyRuntimeMetadata.as_meta_fields()` (lines 68-79) writes these `agent_meta.json` keys: `agent_family_config_id`, `agent_family_config_version`, `agent_family_config_hash`, `active_gate_id`, `active_gate_renderer`, `family_state`, and (for custom roles) `agent_family_custom_role` (a role snapshot). `as_followup_relationships()` (lines 81-87) drops `active_gate_id`/`active_gate_renderer` for follow-up artifacts. `family_state` is a `FamilyStateSnapshot.as_json()` (lines 30-38) with: `current_role`, `current_role_suffix`, `feedback_count`, `qa_round_count`, `saved_chat_suffixes` (list), `visit_counts` (dict). Persistence is done via `record_family_runtime_metadata` in `src/sase/axe/run_agent_family_metadata.py` (calls `update_meta_field` per key, preserving explicit `None` clears).

**Evaluator functions** (`standard_plan_chain_evaluator.py`): `build_handoff_event` (78-96) normalizes a legacy marker dict into a typed event; `evaluate_handoff_event` (181-219) routes an event to gate/renderer and computes custom-role transitions/terminality; `evaluate_plan_approval_transition` (285-340) picks the post-review role/suffix/side-effects and any custom role after `plan`; `evaluate_questions_transition` (343-386) picks the Q&A follow-up role/suffix; `family_state_snapshot` (50-75) and `family_runtime_metadata_for_role` (222-248).

**Wiring into markers** (`src/sase/axe/run_agent_exec.py`): the exec loop reads legacy marker files `.sase_plan_pending` / `.sase_questions_pending`, builds a typed event via `build_handoff_event`, and dispatches through `_handle_handoff_event` (lines 177-186) to `handle_plan_marker` / `handle_questions_marker`.
- `handle_plan_marker` (`run_agent_exec_plan.py:122-318`) coerces to a `plan_submitted` event, evaluates gate metadata, records family runtime metadata, calls `handle_plan_approval`, then for `feedback` uses `evaluate_plan_approval_transition`; otherwise delegates to `handle_accepted_plan`.
- `handle_accepted_plan` (`run_agent_exec_plan_accept.py:230-612`) calls `evaluate_plan_approval_transition` (with `custom_roles` filtered by selected members and `auto_mode`), records family metadata, and either spawns a custom-role follow-up, an epic/legend creator, or the coder.
- `handle_questions_marker` (`run_agent_exec_questions.py:108-296`) coerces to a `questions_submitted` event, records gate metadata, then `evaluate_questions_transition` picks the follow-up.

The legacy marker files still drive the loop; the evaluator is layered on top as the golden README pins ("preserving existing marker-file behavior").

---

## 3. `role_completed` event (5g.4)

Emitted in `src/sase/axe/run_agent_exec.py:_handle_completed_followup` (lines 204-263), called after a follow-up workflow returns normally (`run_execution_loop` line 334). It fires only when `state.agent_step > 1` and there is a current role suffix (line 207) — i.e. not for the first/planner step and not for killed follow-ups (kill path returns "killed" before this).

Payload (lines 214-219): `{"outcome": "success", "artifacts_ref": <current_artifacts_dir>}`. `outcome` is currently hard-coded `"success"`; `interrupted_role` is derived from the completed artifact's `agent_family_role` meta field (`_current_agent_family_role`, lines 189-201).

What the standard chain does with it: `evaluate_handoff_event` looks up the `role_completed` event definition (terminal, composition rule `after_followup_workflow_including_embedded_vcs_refs`). `_custom_role_for_handoff_event` (evaluator lines 157-178) selects an active custom role placed `after` the just-completed role (via `active_roles_after` filtered by `state.selected_member_ids`). If a non-terminal custom role is selected, `spawn_custom_role_followup` mutates state to run it next and the loop continues (returns `False`); if the role's visit cap is exhausted or a failure policy applies, it records `custom_role_terminal_reason` / `custom_role_terminal_role` meta fields and terminates. If no custom role matches, the event is terminal and the loop ends. A snapshot guard (`custom_role_snapshot`) prevents a custom role from chaining after itself (evaluator lines 164-172). Killed follow-ups never emit it (see kill handling in `run_execution_loop`).

---

## 4. `agent_family` YAML schema (5g.5)

Loader/validator: `src/sase/agent_family/custom_definitions/` (split by 179a0398a into `models.py`, `loading.py`, `validation.py`, `discovery.py`). A file is recognized only if the top-level mapping has `kind: agent_family` (`loading.py:54`).

**Top-level fields** (`validation.py:parse_agent_family_definition`, lines 61-113):
- `kind: agent_family` (required to be recognized).
- `schema_version` — must equal integer `1`, else error `"schema_version must be 1"`.
- `id` — required; must match `^[A-Za-z][A-Za-z0-9_]*$` (error `"id '<x>' must use letters, numbers, and underscores"`).
- `version` — required positive integer (error `"version must be a positive integer"`).
- `extends` — optional, defaults to `"standard_plan_chain"`; any other value errors `"extends must be 'standard_plan_chain', got '<x>'"`.
- `roles` — required non-empty mapping (error `"roles must be a non-empty mapping"`), keyed by role id.

**Per-role fields** (`_parse_role`, lines 155-234; allowed keys set `_ROLE_KEYS` lines 36-51). Unknown keys error `"role '<id>' has unknown keys: <keys>"`.
- `suffix` — optional; defaults to `--<role_id>`. Must start with `--` (canonical), match `^--[A-Za-z0-9_]+$`, and must NOT be a standard reserved suffix (`--plan`, the question/coder/epic/legend/commit suffixes). Errors: `"role '<id>' suffix must use canonical '--' spelling"`, `"... must start with '--'"`, `"... must use letters, numbers, and underscores"`, `"... suffix '<s>' is reserved by the standard chain"`.
- `prompt_template` — required non-empty string. When `validate_prompt_refs` is on, it must name a known xprompt (the name is the token before `:`/`(`/space; leading `#` stripped). Errors: `"role '<id>' prompt_template is required"`, `"... must name an xprompt reference"`, `"... references unknown xprompt '<name>'"`.
- `placement` — required mapping with required string `after` (`_parse_placement`, lines 317-327). Errors: `"role '<id>' placement must be a mapping"`, `"... placement.after is required"`. Stored as `placement_after`.
- `on_done` — required; one of `re_review | continue | terminate` (error `"role '<id>' on_done must be one of: continue | re_review | terminate"`).
- `on_failure` — required; one of `notify_and_continue | notify_and_stop`.
- `auto` — **required**; one of `run | skip` (no default; absent key errors `"role '<id>' auto must be one of: run | skip"`).
- `max_visits` — optional; **defaults to `3`**; must be a positive integer.
- `default` — optional boolean; defaults to `False` (stored as `default_enabled`); must be true/false.
- `label`, `done_label` — optional display labels (see §7 for constraints).
- `delegated_budget`, `delegated_budgets` — reserved (Phase 8); accepted and snapshotted into `reserved` but not interpreted (lines 47-52, 214-216).

Each role compiles into `AgentFamilyRoleDefinition` (`models.py:16-55`) which also records `config_id` (= definition id), `config_version`, `config_hash` (SHA-256 over schema_version/id/version/extends/roles, `validation.py:82-91`), and `source_path`. `as_snapshot()` serializes all fields (including `label`/`done_label`/`reserved`) for artifact persistence; `role_definition_from_snapshot` rebuilds it (lines 116-152).

**Where files live / discovery precedence** (`discovery.py:get_all_agent_family_definitions`, lines 27-73) — same search order as xprompts, later entries override earlier by `id`:
1. `get_sase_package_xprompts_dir()` (bundled package xprompts).
2. Plugin `sase_xprompts` resources (`_load_definitions_from_plugins`, lines 168-222; source path `plugin:<module>/<file>`).
3. Project config dir `~/.config/sase/xprompts/<project>/` (lines 135-145).
4. Project workspace `<workspace>/.xprompts/` and `<workspace>/xprompts/` (lines 148-165).
5. `get_xprompt_search_paths()` dirs (reversed, lines 118-132).

Each dir is scanned for `*.yml` and `*.yaml` (lines 104-105). Invalid definitions are skipped and recorded via `record_load_issue(..., kind="agent_family")` (`loading.py:64-66`) — surfaced as `skipped: <source>: <error>` on stderr by `sase xprompt list`.

**Bundled examples are intentionally inactive** — they live under `xprompts/examples/agent_families/` which is NOT in the search path (docstring `discovery.py:33-35`). The two flagship examples:

`src/sase/xprompts/examples/agent_families/improve_plan.yml`:
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

`src/sase/xprompts/examples/agent_families/tester.yml`:
```yaml
kind: agent_family
schema_version: 1
id: tester
version: 1
extends: standard_plan_chain
roles:
  tester:
    suffix: "--tester"
    label: "TESTING"
    done_label: "TESTED"
    prompt_template: "agent_family_tester:{source_artifacts}"
    placement:
      after: code
    on_done: terminate
    max_visits: 1
    on_failure: notify_and_continue
    auto: run
```

Their referenced prompt templates ship in `src/sase/xprompts/agent_family_improve_plan.md` (input `plan_file: path`) and `src/sase/xprompts/agent_family_tester.md` (input `source_artifacts: line`). Prompt placeholders are filled by `_render_custom_role_prompt` (`run_agent_exec_custom_roles.py:45-65`): available format keys are `plan_file`, `source_artifacts`, `artifacts_ref`, `outcome`, `source_role`, `role`; unknown keys render empty; a rendered value not starting with `#`/`@`/`%` is prefixed with `#`.

**How a user lists/inspects definitions:** via `sase xprompt list` (JSON). `src/sase/main/xprompt_handler.py:_handle_list` (lines 167-195) appends each active family definition with `"type": "agent_family"`, `"kind": "agent_family"`, `source` = the definition source path, and a `preview` = JSON of `{"roles": [...]}` where each role dict exposes `id, suffix, placement_after, prompt_template, on_done, max_visits, on_failure, auto` (label/done_label are NOT in the list preview). Note: `sase xprompt explain` operates only on regular prompts (`get_all_prompts`), so it does not explain family definitions.

---

## 5. Approval-gate member options (5g.6)

**TUI (`ApproveOptionsModal`, `src/sase/ace/tui/modals/approve_options_modal.py`):** Custom members render under an "Also run:" section (line 221). Each member row (`_member_row_markup`, lines 257-272) shows `<index> [x]/[ ] <display_label>  after <placement_after>`, where `display_label` is the role id with underscores replaced by spaces (`plan_approval_choices.py:342`). Keys `1`-`9` toggle members (`_toggle_member_by_key`, lines 351-360; digit handling at 328-331); footer hint reads `[cyan]1-9[/cyan]=Members` (line 234). Default-checked state comes from `default_enabled` (constructor lines 183-192). The result (`ApproveOptionsResult`, lines 109-119) carries `selected_member_ids: tuple[str,...] | None`.

**CLI flags on `sase plan approve`** (`src/sase/main/parser_plan.py:86-103`): `-w/--with ROLE` (dest `with_members`, `action="append"`, repeatable, help "Run a custom family member for this approval (repeatable)") and `-W/--without ROLE` (dest `without_members`, `action="append"`, repeatable, help "Skip a default custom family member for this approval (repeatable)"). Example in epilog: `sase plan approve abcdef12 --with tester`. Resolution: `plan_approve_handler.py:_selected_member_ids_for_cli` (lines 132-171) reads `plan_request.json`, parses `member_options_from_request_data`, then `resolve_member_selection_for_overrides` (`plan_approval_choices.py:459-480`). Specifying the same role in both `--with` and `--without` raises `"member option specified with both --with and --without: <ids>"`; an unknown role raises `"unknown plan-approval member option: <ids>"` (both surface as CLI `Error:` and exit 2).

**How `plan_request.json` / `plan_response.json` carry options:** the request payload is built by `plan_approval_member_request_payload` (`plan_approval_choices.py:354-370`) and merged into `plan_request.json` (`llm_provider/_plan_utils.py:232-240`). It contains `member_options` (list; each option `as_request_payload` includes `id, label, placement_after, suffix, auto, default, definition_default, source_path, config_id, config_hash`, lines 78-91) and `default_member_ids`. The response writes `selected_member_ids` (`plan_approval_actions.py:_add_selected_member_ids`, lines 245-255; TUI `_build_plan_approval_response`, `_notification_modals.py:307-308`). Reading back: `selected_member_ids_from_response_data` (lines 434-456) prefers explicit response ids, else falls back to `default_member_ids_from_request_data` (lines 407-431).

**Sticky per-project defaults config key:** `agent_family.plan_approval.default_members` in `sase.yml` — an object mapping role id → boolean (`src/sase/default_config.yml:6-11`; schema `src/sase/config/sase.schema.json:113-133`, `additionalProperties: false`, values boolean). Read by `_configured_plan_approval_member_defaults` (`plan_approval_choices.py:500-528`), which also tolerates a list form (each listed id → true). **Precedence:** the configured override, if present for a role id, replaces the role definition's own `default` (`plan_approval_choices.py:336`: `default_overrides.get(role.id, role.default_enabled)`).

**Remote (Telegram/mobile) behavior:** `notify_plan_approval` (`src/sase/notifications/senders.py:231-289`) receives `default_member_ids` and, when non-empty, appends a preview note `"Also run: <comma-joined ids>"` (lines 270-277). The mobile bridge `execute_mobile_plan_action` (`src/sase/integrations/_mobile_notification_actions.py:32-117`) does not send explicit `selected_member_ids`, so the response omits them and the runner applies the request's `default_member_ids` (sticky defaults) via the fallback path — i.e. sticky project defaults are honored remotely.

The selection is threaded into execution via `LoopState.selected_member_ids` and used to filter custom roles after the plan/code gates with `filter_roles_by_selected_member_ids` (`plan_approval_choices.py:483-497`; used in `run_agent_exec.py:221` and `run_agent_exec_plan_accept.py:253`). `None` preserves definition-driven defaults; an empty tuple means "run no custom members".

---

## 6. Auto-mode behavior

Each custom role must declare `auto: run | skip` (required; §4). Under `%auto`/`%a` plan flows, `handle_plan_approval` short-circuits via `get_auto_plan_approval_action` and builds `_auto_approval_result` (`llm_provider/_plan_utils.py:38-56`). The auto path only enables members whose `auto == "run"`: `_auto_default_member_ids` calls `default_member_ids_from_request_data(payload, auto_mode=True)`, which intersects the default ids with `{option.id for option in options if option.auto == "run"}` (`plan_approval_choices.py:427-429`). `evaluate_plan_approval_transition` and `_select_custom_role_after` also skip non-`run` roles when `auto_mode=True` (`standard_plan_chain_evaluator.py:125-126`, 294-327; `auto_mode` derived from `plan_result.auto_approved` at `run_agent_exec_plan_accept.py:266`). Bare `%auto` resolves to `action="approve"` (runs coder, no SDD commit); tale/epic auto modes commit (`_plan_utils.py:38-51`). Auto plan approval itself remains limited to `approve`/`tale`/`epic` (`PLAN_APPROVAL_AUTO_MODE_CHOICES`; golden README invariant).

---

## 7. Display labels (5g.9)

Role `label` / `done_label` are optional display-only strings persisted in the role snapshot (`models.py` `as_snapshot`) and copied to `Agent.custom_role_label` / `Agent.custom_role_done_label` (`_meta_enrichment_common.py:apply_custom_role_display_labels`, lines 183-195; wire/filesystem enrichment paths both call it). They are surfaced through a **display-only** property `Agent.display_status` (`src/sase/ace/tui/models/agent.py:413-420`): when semantic `status == "RUNNING"` and `custom_role_label` is set, it returns the label; when `status == "DONE"` and `done_label` is set, it returns `done_label`; otherwise it returns the raw status.

**Bucket/label independence:** the row renderer (`src/sase/ace/tui/widgets/_agent_list_render_agent.py:186`) prints `display_status` for the text but switches color/style on the semantic `agent.status` (lines 188-268). So buckets, colors, and actions stay keyed to the unchanged semantic status while only the visible text changes. `_agent_status_apply.py:292-293` propagates the labels to the parent row.

**Constraints on label values** (`_optional_display_label`, `validation.py:275-291`, `_DISPLAY_LABEL_RE = ^[A-Za-z0-9][A-Za-z0-9 _/-]*$`, `_DISPLAY_LABEL_MAX_LEN = 24`): must be a non-empty string ≤ 24 chars using letters/numbers/spaces/`_`/`-`/`/`. Errors: `"... must be a string"`, `"... must not be empty"`, `"... must be 24 characters or fewer"`, `"... must use letters, numbers, spaces, _, -, or /"`.

---

## 8. `max_visits` / loop-cap behavior

`max_visits` defaults to `3` (`validation.py:205-208`) and must be a positive integer. Visit accounting lives in `FamilyStateSnapshot.visit_counts` and `LoopState.custom_role_visit_counts`. In `_select_custom_role_after` (`standard_plan_chain_evaluator.py:114-154`): if `prior_visits >= role.max_visits`, it returns a `CustomRoleTransition(cap_exhausted=True)`; otherwise it increments the count and proceeds.

**Hard stop:** when the cap is exhausted at the plan gate, `handle_accepted_plan` records meta field `custom_role_cap_exhausted: <role_id>` and returns loop outcome `"custom_role_cap_exhausted"` (`run_agent_exec_plan_accept.py:385-392`). At the `role_completed` gate, `_handle_completed_followup` records `custom_role_terminal_reason` (value `"custom_role_cap_exhausted"` or the `on_failure` policy) plus `custom_role_terminal_role`, and terminates (`run_agent_exec.py:242-263`). There is no separate desktop/Telegram notification for the cap; the stop is recorded as the terminal loop outcome and the terminal-reason meta fields (surfaced through the normal done-marker/finalize path in `run_agent_exec_finalize.py`).

---

## 9. Existing user-facing docs

There is **no dedicated user-manual documentation** for Dynamic Agent Families v2 in `docs/`. The `docs/` directory (ace.md, xprompt.md, configuration.md, etc.) only mentions the concept incidentally:
- `docs/xprompt.md:1097-1098` notes that custom family-role suffixes such as `reviewer`/`tester` "are allowed as custom roles and use ordinary running/done status labels while preserving the custom role in `agent_family_role` metadata for future family evaluators."
- `docs/ace.md:1439` references "agent-family roots" only for name validation display.

No docs page documents the `kind: agent_family` YAML schema, the `improve_plan`/`tester` examples, `agent_family.plan_approval.default_members`, or the `sase plan approve --with/--without` flags. The only "generated help" is `sase plan approve`'s argparse help (parser_plan.py) and the JSON emitted by `sase xprompt list`. Internal/spec docs referencing the epic exist under `sdd/` (bead stream `sdd/beads/events/streams/sase-5g.jsonl`) and the test harness README `tests/plan_chain_golden/README.md`, but these are developer-facing, not a user manual.

### Test/harness locations (for verification)
- Golden harness: `tests/plan_chain_golden/` (`test_marker_and_loop_golden.py`, `test_plan_approval_response_golden.py`), marker `plan_chain_golden` registered in `pyproject.toml:214` and `tests/conftest.py:40-54` (`pytest -m plan_chain_golden`).
- Unit coverage: `tests/test_plan_approval_choices.py`, `tests/test_standard_plan_chain_evaluator.py`, `tests/test_agent_family_custom_definitions.py`, `tests/test_dynamic_agent_family_attach.py`, `tests/test_approve_options_modal_state.py`, `tests/test_plan_approve_cli.py`, `tests/test_plan_utils.py`, `tests/test_config_schema.py`, `tests/test_mobile_notifications_bridge.py`, `tests/test_agent_loader_status_custom_role_labels.py`, and a PNG snapshot `tests/tui/visual/.../agents_custom_role_labels_120x40.png`.

The v2 evaluator/YAML/approval-gate research is in — the choice registry, `agent_family` YAML schema with flagship `improve_plan`/`tester` examples, `--with/--without` CLI flags, sticky defaults config key, and display-label mechanics are all captured. One agent remains (v1 attach machinery); I'll write the research doc when it reports.

I have all the verified facts. Here is the report.

# Dynamic Agent Families v1 — As-Implemented Behavior

Scope note: all `%n`/`%name` family-attach parsing lives in `src/sase/agent/family_attach.py`; the `{source}` token in every parser error is `%<name-as-typed>` (i.e. `%n` if the user wrote `%n`, `%name` if they wrote `%name`), built at `family_attach.py:113-116` and `src/sase/xprompt/_directive_collect.py:164`.

## 1. Accepted grammar of `%n` / `%name` today

Family attach is **paren-form only**. The colon form (`%n:name`) never attaches — it only assigns a plain name (the colon value is a single string, never comma-split). Attach dispatch happens only in `_collect_name_paren_args` (`_directive_collect.py:150-183`), which is reached solely for the `(` form. `parse_name_directive_args` (`family_attach.py:54-82`) classifies the args.

Accepted forms:
- `%n(name)` / `%name(name)` — one positional → **plain name** (`family_attach.py:80-82`). Same as `%n:name`.
- `%n(parent, suffix)` — two positionals → **family attach** (`family_attach.py:74-79`).
- `%n(parent, @)` — `@` allocates the next free suffix (`family_attach.py:327-328`, resolution at `342-354`).
- No colon attach form. `%name:reviewer` / `%n:reviewer` are documented as plain-name assignment (`docs/xprompt.md:1026-1031`).

Strict rejections (each raised as `ValueError`, re-wrapped as `DirectiveError` at `_directive_collect.py:166-167`):

| Case | Exact message | Location |
|---|---|---|
| Keyword args (e.g. `%n(foo, run_status=DONE)`) | `Unsupported keyword on %n: run_status=. Use %n(parent, suffix) for family attach; keyword arguments are not supported.` | `family_attach.py:62-68` |
| 3+ positionals (e.g. `%n(foo, reviewer, extra)`) | `%n accepts at most two positional arguments. Use %n(parent, suffix) for family attach.` | `family_attach.py:69-73` |
| Empty parent or suffix | `%n(parent, suffix) requires both parent and suffix.` | `family_attach.py:76-77` |
| Legacy `.`/`-` spelling or a `--` inside the suffix (e.g. `%n(foo, .reviewer)`, `%n(foo, -reviewer)`, `%n(foo, --reviewer)`) | `Invalid %n family suffix '.reviewer'. Pass the bare suffix without a family separator, e.g. %n(parent, reviewer).` | `family_attach.py:329-333` |
| Other invalid chars in a suffix | `Invalid %n family suffix '<x>'. Use letters, numbers, and underscores only, or @ to allocate the next free suffix.` | `family_attach.py:334-338` |
| Raw `--` in a **plain** name (e.g. `%name:foo--bar`) | `Agent name 'foo--bar' cannot contain '--'; double dash is reserved for agent-family phases.` | `AgentNameSyntaxError`, `launch_validation.py:72-77`, via `validate_user_agent_name` `launch_validation.py:84-91` |

Note: the suffix-message error literally says `Invalid %n family suffix` regardless of whether the user typed `%name` (it is hard-coded to `%n`, unlike the source-interpolated messages). The suffix token regex is `^[A-Za-z0-9_]+$` (`family_attach.py:51`). Prelaunch name helpers ignore the attach form (`extract_static_name_directive` returns None, `validate_launch_name_requests` passes — test `test_prelaunch_name_helpers_ignore_family_attach_form`).

## 2. Parent resolution

Resolution is delegated to the Rust binding **`resolve_agent_family_parent`** (`require_rust_binding("resolve_agent_family_parent")`, `family_attach.py:575-581`), with a pure-Python compatibility fallback `_resolve_agent_family_parent_fallback` (`family_attach.py:584-626`) for stale checkouts. Both are driven from `_resolve_family_attach_plan` (`family_attach.py:260-323`).

- Candidate set: `_agent_family_snapshot` scans only the current project's `ace-run` artifacts, including active + full history + hidden (`family_attach.py:387-424`).
- Matching (fallback mirrors Rust): a candidate matches if `name == parent`, `workflow_name == parent`, or `name` starts with `"<parent>--"` (`_candidate_matches_parent`, `family_attach.py:629-637`); filtered to the same project.
- Selection: **newest timestamp wins**; among the newest-timestamp ties, dismissed identities are dropped; then classified. Terminal parent → `resolved`; still-running parent → `running` (`family_attach.py:599-626`). Newest-match + project-scope confirmed by `test_family_attach_resolution_uses_newest_match_with_project_scope` (picks `20260701010202` over an older same-name and a same-name in project `other`).

Error messages (`_resolution_error_message`, `family_attach.py:541-566`):
- Absent: `Cannot attach family member with %n(<parent>, <suffix>): parent agent '<parent>' was not found in project '<project>'.`
- Dismissed: `Cannot attach family member to dismissed parent '<parent>'. Revive the parent from the Agents tab before using %n(parent, suffix).`
- Ambiguous: `Cannot attach family member to '<parent>': multiple newest parent candidates matched (<name@ts>, ... up to 5). Use the exact parent after dismissing or reviving duplicates.` (label form is `name@timestamp`, `_candidate_label` `family_attach.py:569-572`).
- Resolved but metadata vanished: `Cannot attach family member to '<parent>': resolved parent metadata is no longer available.` (`family_attach.py:283-295`).

All are `_FamilyAttachError`, which aborts the launch before any agent is spawned (`test_family_attach_prep_failure_prevents_spawn`, tests 614-638).

## 3. Reserved suffixes, custom suffixes, `@`, composition, collisions

`AGENT_FAMILY_SEPARATOR = "--"` (`plan_chain.py:9`). Reserved suffixes and roles (`plan_chain.py:10-15, 25-56`):

| Suffix arg | Role suffix | `agent_family_role` |
|---|---|---|
| `plan` | `--plan` | `plan` |
| `q` | `--q` | `q` |
| `code` | `--code` | `code` |
| `epic` | `--epic` | `epic` |
| `legend` | `--legend` | `legend` |
| `commit` | `--commit` | `commit` |

- Custom suffix (any `[A-Za-z0-9_]+` not reserved): the role is **the token itself** — e.g. `reviewer`→`reviewer`, `improve_plan`→`improve_plan` (`_family_role` `family_attach.py:358-367`; `agent_family_role_for_suffix` returns None for the token, so it falls through to the token; `plan_chain.py:234`). Verified by `test_family_attach_role_mapping_through_attach_path`.
- Numeric suffix or `@` → role `feedback` (`family_attach.py:365-366`).
- `@` allocation: normalized to `--@` (`family_attach.py:327-328`), then `allocate_agent_family_child_suffix(parent_base, "--@", extra_reserved=<known family suffixes>)` fills `@` with the lowest free numeric slot (`family_attach.py:347-354`; `plan_chain.py:443-457`). The reserved set always includes `base`, `base--plan`, and `base--0` (`plan_chain.py:413-414`), so `@` never collides with the planner/root-question rows.
- Name composition: `agent_name = f"{parent_base}{role_suffix}"` (`family_attach.py:300`), where `parent_base` = the parent's `agent_family` meta, else `agent_family_base(parent_name)` (`_family_base`, `family_attach.py:477-483`).
- Collision (`_ensure_family_name_available`, `family_attach.py:370-384`): if the composed name already exists in reserved or known family names → `Agent family member '<name>' already exists. Use %n(<parent>, @) to allocate the next free suffix.` Verified by `test_family_attach_collision_message_suggests_auto_suffix`.

## 4. Metadata written on an attached member

Written directly in `extract_directives_and_write_meta` (`run_agent_directives.py:283-305`) when a family-attach plan is present:
- `name` = composed child name; `workflow_name` = `parent_base`; `role_suffix` = the `--<suffix>`; `agent_family` (`AGENT_FAMILY_FIELD`) = `parent_base`; `agent_family_role` (`AGENT_FAMILY_ROLE_FIELD`) = role.
- `parent_timestamp` = parent artifact timestamp; `plan_chain_parent_timestamp` (`PLAN_CHAIN_PARENT_TIMESTAMP_FIELD`) = same.
- Inherited from parent: `workspace_dir`, `workspace_num`, `changespec_name`, `cl_name` (`run_agent_directives.py:299-305`).
- If queued behind a running parent, `wait_for_artifacts` = the identity dep list (`run_agent_directives.py:245-246`).

This is intentionally **field-indistinguishable from a runner follow-up** (`create_followup_artifacts`, `run_agent_helpers_artifacts.py:97-195`). That helper inherits `model, llm_provider, reasoning_effort, vcs_provider, workspace_dir, name, approve, changespec_name, cl_name, bead_id, epic_bead_id, phase_bead_id, legend_bead_id, agent_family_config_id/version/hash, family_state` (`:118-139`), then sets canonical `role_suffix`, `agent_family`, `agent_family_role`, `parent_timestamp`, and `plan_chain_parent_timestamp` when the meta is a plan-chain phase (`:146-163`). The parity test `test_family_attach_metadata_matches_runner_followup_and_tui_family_child` asserts member meta == follow-up meta across `name, workflow_name, role_suffix, parent_timestamp, plan_chain_parent_timestamp, agent_family, agent_family_role, workspace_dir, workspace_num, changespec_name, cl_name`, that `find_agent_family("foo")` includes it, and that the TUI `Agent.is_family_member_child is True`.

SASE_PLAN rule for code-role members: `sase_plan` is set **only when `role == "code"`** and the parent's family has a plan path (`_resolve_family_attach_plan` `family_attach.py:320-322`; `_family_sase_plan` reads newest family record's `sdd_plan_path`/`plan_path`/done plan path, `:515-538`). `prepare_family_attach_launch` exports `env["SASE_PLAN"]` only if `plan.sase_plan` is truthy (`family_attach.py:192-193`). Verified by `test_family_attach_sase_plan_env_only_for_code_with_parent_plan` (`code`+plan→set; `q`+plan→unset; `code`+no plan→unset).

## 5. Running-parent queueing

When the parent resolves as `running`, `plan.parent_is_running = True` (`family_attach.py:316`). The child is launched **immediately** rather than rejected.

- Implicit wait (`run_agent_directives.py:110-124`): the parent name is appended to `wait_names`, and an **identity dep** is appended to `wait_identity_deps` carrying `project_name`, `timestamp`, `artifact_dir`, and `name`. It is persisted as `wait_for_artifacts` in the child's `agent_meta.json` (`:245-246`).
- Identity-keyed by timestamp/dir: `_identity_candidate` matches first on `artifact_dir`, else on `(project_name, timestamp)` (`wait_dependency_resolution.py:470-484`) — so the child waits on that **exact** parent artifact, not the newest same-named run.
- Success/failure (`identity_status`, `wait_dependency_resolution.py:442-468`):
  - `_IDENTITY_SUCCESS_OUTCOMES = {"completed", "plan_rejected"}` (`:23`); `_FAILURE_OUTCOMES = {"failed", "killed", "stopped"}` (`:24`); `repeat_stopped` also counts as failure (`:547-553`).
  - If the parent is a family root, `family_candidate_for_root` aggregates the whole generation: `is_failed` if **any** member failed; resolves only if **all** are resolved and **any** succeeded (`:328-357, 450-459`).
  - Terminal-status mapping: `DONE`, `PLAN DONE`, `TALE DONE` all write `done.json` `outcome:"completed"` → **success** (child proceeds). `PLAN REJECTED` writes `outcome:"plan_rejected"` → **also counts as success** for the identity wait (child still proceeds; `_done_loaders.py:191-192`). `EPIC CREATED` is a TUI-derived status for an active approved-plan epic child (`_agent_status_family.py:128-137`, `_agent_status_apply.py:255`); the underlying epic root that finishes writes `completed`. A parent that ends `FAILED`/`STOPPED`/killed → failure, cancelling the child.
- Child rendering: launched right away and shown as a **WAITING family-member child row folded under the running parent** (`docs/xprompt.md:1100-1104`). The TUI child-row normalization that makes WAITING family children share the parent-fold behavior while keeping their own status/details is commit `9caeb0d37` (`_agent_status_family.py`, `agent.py` `is_family_member_child`).
- Cancel-to-STOPPED + notification (`run_agent_runner.py`): when the wait returns cancelled because the dependency failed (`:352-382`), `_finalize_cancelled_wait` (`:98-158`) writes a `done.json` with `outcome:"stopped"`, `queue_cancelled: True`, `failed_dependencies: [...]`, and `error: "Queued launch cancelled because dependency failed: <detail>"` where `<detail>` is the comma-joined `name@timestamp` list. It then calls `notify_workflow_complete(sender="user-agent", cl_name=..., success=True, notes=["Queued agent @<name> stopped", "Parent dependency failed: <detail>"], action="JumpToAgent", action_data={cl_name, raw_suffix, agent_name?, prompt}, tags=["done"])`. Because the outcome is `"stopped"`, the row renders as **STOPPED** and does **not** satisfy any downstream `%wait` (`_done_loaders.py:179-190`, comment explicitly noting queue-cancel uses `stopped` to avoid the wait cascade).

## 6. `#with_feedback` and `#with_q_and_a`

Both are packaged embeddable prompt-assembly xprompts (`src/sase/xprompts/with_feedback.yml`, `with_q_and_a.yml`); they only build prompt text — `%n(parent, suffix)` is the directive that actually attaches the launched agent (`docs/xprompt.md:876-878`).

`#with_feedback` (`with_feedback.yml`):
- Inputs: `feedback` (type `text`, required — first positional, so the `::` shorthand fills it: `#with_feedback:: text` → `feedback="text"`), `parent` (type `line`, `default: ""`).
- Body: resolves the parent via `resolve_resume_agent_name(parent)`, reads its prompt artifact, and appends the feedback as an `### Additional Requirements` bullet using the same replan renderer as the runner (`assemble_feedback_replan_prompt`, `feedback_prompt.py:20-30`; `_assemble_feedback_replan_prompt_from_parent`, `:39-57`). Prompt candidate order: `followup_prompt.md`, else newest `*_prompt.md` (excluding commit-finalizer), else `raw_xprompt.md` (`:81-102`). Prior Q&A rounds are merged in front when present (`:26-29`).
- Errors (`_FeedbackPromptError`, a `ValueError`): `parent is required` (empty parent, `:43`); `unknown parent agent: <parent>` (unresolvable, `:49`); `no prompt artifact found for parent agent '<parent>' at <dir>` (`:53-56`).

`#with_q_and_a` (`with_q_and_a.yml`):
- Inputs: `prompt` (type `text`, required — first positional / `::` shorthand), `qa_file` (type `path`, required).
- Body: reads the JSON at `qa_file`, normalizes it via `qa_rounds_from_payload`, and appends rendered Q&A with `assemble_question_followup_prompt` = `base_prompt + "\n\n" + merge_qa_for_prompt(rounds)`; the merged Q&A block is wrapped in `%xprompts_enabled:false ... %xprompts_enabled:true` so literal `#xprompt` text inside answers does not expand (`qa_prompt.py:34-45`).
- Accepted `qa_file` shape: a single `{questions, response}` object, an object with a `rounds` list, or a top-level list of such objects (`_raw_rounds_from_payload`, `qa_prompt.py:61-73`). `response` may be omitted and reconstructed from `answers`/`global_note` (`:92-97`).
- Errors: `qa_file not found: <path>` (`FileNotFoundError`, yml `:24-25`); `qa_file is not valid JSON: <path>: <exc>` (yml `:26-27`); plus payload validators in `qa_prompt.py`: `qa_file must contain a JSON object or list` (`:73`), `qa_file field 'rounds' must be a list` (`:66`), `qa_file <label> item <n> must be an object` (`:80`), `qa_file round <n> must contain a 'questions' list` (`:87`), `qa_file round <n> questions must be objects` (`:90`), `qa_file round <n> response must be an object` (`:99`), `qa_file must contain at least one Q&A round` (`:57`).

Composition sugar from `a660d9227`: `#with_feedback` **defaults its `parent` from a co-occurring `%n(parent, suffix)`** in the same prompt segment. `default_with_feedback_parent_from_family_attach` (`family_attach.py:128-148`) runs only for `with_feedback`, only when `args["parent"]` is empty; it finds the first top-level `%n(parent, suffix)` in the `---` segment containing the workflow reference (fenced- and offset-aware, `_prompt_segment_at_offset` `:150-171`) and sets `parent`. Wired at both embedded-expansion sites: `workflow_executor_steps_embedded_expand.py:167-176` and `_embedded_workflows.py:117-129` (which passes `fenced_ranges` and `segment_source_query`). So `%n(planner, @) #with_feedback:: text` infers `parent=planner` (`test_with_feedback_parent_default_uses_family_attach_directive`), while an explicit `#with_feedback(parent=planner)` is left untouched. `#with_q_and_a` gets **no** such inference (guarded by `workflow_name != "with_feedback"`, `:137`).

## 7. Edge cases fixed in `c5f18ae90`

This commit is primarily coverage + a dead-branch removal; the tale (`sdd/tales/202607/close_out_sase_5f_epic.md`) states "No behavior changes to the family-attach, wait, or notification implementations beyond the dead-branch removal." Worth noting for a manual:
- Removed the now-unreachable `kind == "running"` error branch of `_resolution_error_message` (`family_attach.py`, old message told users to wait and rerun). Since Phase 4, running parents queue instead of erroring, so that message can no longer appear.
- PID ≤ 1 is now treated as not-alive (`names/_common.py:82-83`) — a parent/agent whose recorded PID is 1 no longer looks live (affects liveness → resolution as terminal vs running).
- macOS/zombie handling on `axe stop` (`_process_stop.py`): new `_pid_is_zombie` (via `ps -o stat=`) so `_wait_for_all_exited`/`_wait_for_exit` treat zombies as exited instead of hanging.
- Unquoted LSP command path containing spaces is now recovered (`xprompt_lsp.py` `_recover_unquoted_command_path_with_spaces`).
- Explicit `$XDG_STATE_HOME` now wins on **all** platforms, including macOS (`workspace_provider/store.py` `_default_state_root`) — previously macOS ignored it. Relevant because family resolution scopes to the project artifacts under the state root.

## 8. Existing user-facing docs

- `docs/xprompt.md` is the main manual surface:
  - "Bundled Follow-Up XPrompts" (`:868-900`): the `#with_feedback`/`#with_q_and_a` table, the "%n is the launch directive" note, the two feedback-parent examples (`%n(planner, @) #with_feedback:: ...` and explicit `parent=`), the Q&A file example and shape description, and the plan-chain `--` glossary note.
  - `%name`/`%n` reference: table row (`:1002`), examples block (`:1026-1031`, including `%n(parent, reviewer)` and `%n(parent, @)`), the full two-argument description (`:1090-1093`), reserved-vs-custom suffixes and `@` (`:1095-1098`), running-parent WAITING queue + cancel-to-STOPPED notification (`:1100-1104`), collision suggestion, and the submitted-plan `%wait` exception on the `<base>--plan` row (`:1115-1119`).
- TUI completion hints (`directive_completion.py`, updated in `a660d9227`): `%name` argument hint is now `:agent or (parent, suffix)` and its description `assign an agent name or attach a member to an existing family`.
- `sase xprompt explain with_feedback` / `sase xprompt catalog` surface the YAML `description` lines ("Append plan feedback to a parent agent prompt using the replan renderer." / "Append answered SASE user questions to a prompt using the follow-up renderer.") — see `docs/xprompt.md:864-866` for the explain/catalog commands.
- Planning docs (not end-user, but authoritative): epic `sdd/epics/202607/dynamic_agent_families_v1.md` and closeout tale `sdd/tales/202607/close_out_sase_5f_epic.md`.

No dedicated README section beyond `docs/xprompt.md`; a `grep` of the repo shows the family-attach user documentation is concentrated there.

All three research agents have reported. I now have the full picture — design lineage, v1 attach machinery, v2 evaluator/YAML/approval-gate, and LaunchApproval//sase_run. Writing the research doc now.

The research doc is written. Let me spot-check two facts I stated (the launch-requests directory path and the config key shape) before wrapping up.

Both spot-checks pass — `~/.sase/launch_requests/` (via `sase_subdir`, overridable with `SASE_HOME`) and the `agent_family.plan_approval.default_members` config key match the doc exactly. Since the only change is a new markdown file under `sdd/research/`, the `just check` requirement is waived per the project instructions.

## Done

I wrote the research to **`sdd/research/202607/dynamic_agent_families_user_manual_research.md`** (~430 lines). It consolidates the `sase-5f`/`sase-5g` epics, the July design docs, the 202606 memos, and — via three parallel code-research agents — the as-implemented behavior verified against the current tree, with exact syntax, error messages, schemas, and file/test anchors throughout.

How the doc is organized:

- **Concept overview** — what a `--` family is, the v1 (user-initiated) vs v2 (lifecycle-initiated) split, the four locked design invariants (no custom status strings, no `%!`, v1 metadata as the v2 compatibility contract, user-launches ungated), and the glossary caveat about `--` families vs dot-separated hoods.
- **v1 reference** — full `%n(parent, suffix)` grammar with every strict-rejection error message verbatim, parent resolution rules (newest undismissed match, Rust `resolve_agent_family_parent`), suffix→role table, the metadata/inheritance contract incl. the `SASE_PLAN` rule, identity-keyed queueing under running parents (including the subtle bits: `plan_rejected` counts as wait success, cancel-to-STOPPED doesn't cascade into downstream `%wait`s), and the `#with_feedback`/`#with_q_and_a` input contracts plus the `%n`→`parent` inference sugar.
- **v2 reference** — the 8-entry plan-approval choice registry (including the deliberate `run`-choice fix: remote Approve now archives the plan), the typed-event/evaluator architecture and family-state artifact fields, the `role_completed` after-code seam, the complete `agent_family` YAML field table with both flagship examples (`improve_plan`, `tester` — which ship *inactive* under `examples/agent_families/`), approval-gate toggles (`ApproveOptionsModal` digits, `sase plan approve --with/--without`, `agent_family.plan_approval.default_members` sticky config, remote fallback), auto-mode/`max_visits` semantics, display labels, and the full `LaunchApproval`//sase_run flow (`sase launch request/approve/reject`, `SASE_AGENT` gating, write-once responses, and the fact that launch auto-approve was scoped but never built).
- **8 manual-ready usage recipes**, a **documentation-gap analysis** (v1 is documented in `docs/xprompt.md`; everything in v2 is currently undocumented — the YAML schema, `sase plan approve --with`, the config key, `sase launch`, labels), and a **suggested manual outline**.

One finding worth highlighting for the manual work: `docs/cli.md` and `docs/configuration.md` have no trace of the v2 surfaces, so the doc's §5 lists exactly what the manual must author from scratch versus what it can adapt from `docs/xprompt.md`.

The uncommitted file is the research doc I created this session, so I'll commit it with the commit skill.

Committed. The uncommitted file was the research doc I created this session, so per the finalizer I committed it via the `/sase_git_commit` skill:

- **Commit**: `docs: add dynamic agent families user manual research`, staging only `sdd/research/202607/dynamic_agent_families_user_manual_research.md` with `--type create_commit`.
- **Verified**: `git status --short --branch` shows the working tree clean and `master` in sync with `origin/master` (the wrapper pushed as part of its workflow).
