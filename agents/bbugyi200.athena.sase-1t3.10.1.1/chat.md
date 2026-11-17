# Chat History - ace-run (sase-1t3.10.1.1)

- **TIMESTAMP:** 2026-11-17 13:51:08 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1t3.10.1.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1t3.10.1.1, bead=sase-1t3.10.1.1)
%clan(sase-1t3.10.1, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-1t3.10.1.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1t3.10.1.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1t3.10.1.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1t3.10.1.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1t3.10.1.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1t3.10.1.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1t3.10.1.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1t3.10.1.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

I'll start by reading the bead, its design file, and the skills this phase needs so I can see what already landed.

Next I’ll read the bead, its design file, and the memory notes that govern this phase.

The bead is in progress; I’ll pull the rest of its description, design, notes, and parent epic next.

This phase lives in sase-core. I’ll open that repo, read its agents file, and inventory the list-field consumers.

Compact types are not in the tree yet. I’ll inventory the existing wire, query, and Python list consumers next.

I’ll inventory Python list-field consumers in parallel and keep reading the Rust query, scan, and binding seams.

I'll inventory the Python list-row field consumers from the TUI loaders, projection, filters, grouping, and row-local actions. Starting with the listed files and wire types.

I'll read the wire dataclasses and the listed loader/projection files next so the field map stays grounded in actual reads.

Next I’ll read the loader modules and conversion helpers to see which wire fields they actually copy into list rows.

I’ll keep going through enrichment, Agent fields, live-query, grouping, status, and actions to see which of those copied fields are actually consumed.

I’ll inspect list-projection tests, Agent fields, and the remaining list consumers next.

I’ll now read AgentState fields, status/time modules, action availability, and the list-shape projection so KEEP vs DEFER is based on real reads.

I'll verify remaining field consumers against the listed loaders and list surfaces so the KEEP/DEFER map is sourced from actual reads.

I'll read the wire dataclasses and the list-paint/query consumers next so field paths stay exact.

I'll read the render-cache key, projection, live-query pushdown, and loader enrichment next.

TUI list load uses `AgentArtifactIndexQueryWire(record_shape="list", agents_list_projection=True)` in `src/sase/ace/tui/models/_agent_loader_artifact_index.py` with `TUI_SCAN_OPTIONS` (`include_prompt_step_markers=True`, `include_raw_prompt_snippets=False`) from `src/sase/ace/tui/models/_agent_loader_artifact_config.py`. Python conversion in `src/sase/core/agent_scan_wire_conversion.py` only forwards `record_shape`; it does not strip payload fields. Compact list JSON is assembled by the index. Python still skips `agent_meta.linked_repos` when `record_shape=="list"` (`src/sase/ace/tui/models/_loaders/_meta_enrichment_wire.py`). Selected-detail hydration in `src/sase/ace/tui/models/_projected_record.py` currently restores only full `step_output` and `linked_repos`.

Authoritative visible-row field set: `agent_render_key` / `_runtime_signature` in `src/sase/ace/tui/widgets/_agent_list_render_cache.py`.

---

## 1. KEEP (field path → consumers)

### `AgentArtifactRecordWire`

- `record.project_file` → grouping (`agent_groups/_keys.py`), live `project:`, identity of the project row.
- `record.project_name` / `record.project_dir` → path identity for loaders; live `project:` via `Path(project_file).parent.name`.
- `record.workflow_dir_name` → done/workflow dir gates (`DONE_WORKFLOW_DIR_*`, `WORKFLOW_STATE_DIR_*`); done-row `Agent.workflow`.
- `record.artifact_dir` → `Agent.artifacts_dir` / `index_record_dir`; hydration key; file/tmux/archive actions.
- `record.timestamp` → `raw_suffix`, `start_time`, `identity`, fold key, parent-fold key, retry/dedup keys.
- `record.record_shape` → list vs full; `projected_agent_needs_hydration`.
- `record.has_done_marker` → done-row gate; pending-review window (`_meta_enrichment_status.py`).
- `record.agent_meta` presence → enrich vs no-op; clan/session identity.
- `record.done` presence → done-row parse; vestigial workflow skip when `done.outcome` in `{monitored,gated}`.
- `record.running` presence → home running row (`_running_loaders.py`); monitor PID/process_identity fallback.
- `record.waiting` presence → WAITING override on STARTING/RUNNING (even empty wait lists).
- `record.pending_question` presence → `runner_slot_yielded`; QUESTION/ANSWERED unless waiting wins.
- `record.workflow_state` presence → workflow parent row.
- `record.plan_path.plan_path` → `plan_path` / `archived_plan_path`; plan-status enrichment.
- `record.prompt_steps` presence + order → spawn step children; parent `meta_*` merge.
- snapshot `clan_context[]` (`agent_clan`, `agent_clan_generation`, `clan_tribe`, `clan_summary`) → `_agent_loader_normalization.py` attaches tribe/summary by clan+generation. `tests/test_agent_loader_agents_list_projection.py` keeps this even when waiting-only records are omitted.

### `DoneMarkerWire`

- `outcome` → status (`DONE`/`FAILED`/`STOPPED`/`PLAN REJECTED`/`EPIC APPROVED`/`HIJACKED`/`MONITORED`/`GATED`); drop `noop`; vestigial workflow skip for `monitored`/`gated`.
- `cl_name` → identity, live `cl:`, grouping Patch, fold/query names.
- `project_file` → grouping / live `project:` (fallback to record).
- `workspace_num` / `workspace_dir` → workspace identity, hijack, tmux.
- `model` / `llm_provider` / `vcs_provider` → live `model:`/`provider:`; provider chip (`ordered_row_providers`).
- `name` → `agent_name`; live `name:`/`text:`; display.
- `plan_path` → plan enrichment / archived plan.
- `diff_path` → pencil hint (`agent_file_change_hint`); status-apply parent copy; `_agent_status_diff.py`.
- `step_output` list keys only: any `meta_*` (parent merge, status apply) and `meta_workspace` (`effective_workspace_num`); `diff_path` via `_diff_path.py`.
- `error` → FAILED / epic-launch-failed / monitored / gated list error.
- `retried_as_timestamp` / `retry_chain_root_timestamp` / `retry_error_category` → `FAILED (RETRIED)`, live `retry:`, retry chips.
- `approve` / `hidden` → auto-approve glyph; live `hidden:`; fold hidden-step.
- `status_bucket` → grouping `BY_STATUS`.
- `repeat_stopped` → STOPPED even when `outcome=="completed"`.
- `status_label` → monitored/gated display status.
- `imported_source_owner` / `source_machine` → live `machine:`; machine chip; grouping `BY_MACHINE`.
- `recovery.state/reason/reason_text/requested_at/updated_at/episode_id` → RESTARTING overlay / recovery chips (`_done_snapshot_loaders.py`).
- `recovery.hijack_id` / hijack expiry via recovery → hijack overlay; cheap hijack ingress.
- `agent_session_turn` (monitor/gate subset below) → terminal turn paint + kill kind.

### `AgentMetaWire`

- `name` → `agent_name` (non-child); live `name:`; display.
- `process_identity` / `runner_claim_owner_key` → PID merge/liveness; capacity claim chip.
- `status_bucket` → grouping.
- `model` / `llm_provider` / `reasoning_effort` / `model_alias` / `vcs_provider` → live `model:`/`provider:`; provider chip; wait/fork candidate label.
- `workspace_dir` / `workspace_num` → workspace identity, hijack, tmux, `effective_workspace_num` fallback.
- `plan_path` / `sdd_plan_path` / `epic_plan_ref` / `plan` / `plan_approved` / `plan_action` / `plan_committed` / `plan_submitted_at` → plan-status overlay (`PLAN`/`PENDING REVIEW`/`WORKING PLAN`/…); session planner copy (`_agent_status_agent_session_planner.py`); step RUNNING→DONE after plan progressed.
- `epic_bead_id` / `phase_bead_id` / `created_epics[].bead_id` → bead chip (`agent_bead.py`); clan-wave seal (`_agent_clan_waves.py`); stranded phase; `agent_has_confirmed_bead` in render key.
- `commit_diff_path` → `diff_path` fallback for pencil.
- `tribe` / `agent_tab` → live `tribe:`/`tab:`/`pinned:`; tribe colors; tab chip.
- `wait_for` / `wait_for_beads` / `wait_for_hoods` / `wait_for_epics_of` / `wait_epic_follows` / `wait_turn_bindings` / `wait_duration` / `wait_until` / `queue_*` / `wait_runners*` / `wait_priority` / `queue_weight*` → wait chips, runtime wait ticks, wait-directive presence (`wire_meta_has_wait_directive`).
- `approve` / `auto_approve_plan_action` / `auto_approve_argument` → approve glyph; plan auto-cover vs parked gate.
- `hidden` → live `hidden:`; fold.
- `role_suffix` / `agent_session` / `agent_session_role` / `agent_session_parallel` / `plan_chain_root` → identity, grouping, live `session:`/`role:`, fold, wait/fork root, `is_monitor`.
- `agent_clan` / `agent_clan_generation` / `clan_tribe` / `clan_summary` → clan identity/fold key `clan:{name}:{generation}`; live `clan:`.
- `parent_timestamp` → child linkage, parent fold, status-apply parent lookup, kill cascade.
- `retry_of_timestamp` / `retry_attempt` / `retry_chain_root_timestamp` / `retried_as_timestamp` / `retry_terminal` / `retry_error_category` / `retry_started_at` → live `retry:`/`attempt:`; retry chip.
- `plan_submitted_at` / `epic_started_at` / `feedback_submitted_at` / `questions_submitted_at` / `run_started_at` / `stopped_at` / `wait_completed_at` → runtime intervals (`_agent_time_*.py`); STARTING→RUNNING; live `since`/`until`/`after`/`before`/`min`/`max`; QUESTION/ANSWERED stop_time.
- `question_request_path` / `question_response_path` / `question_session_id` → QUESTION vs ANSWERED; render-key `question_response_path`.
- `imported_source_owner` / `source_machine` → live `machine:`; machine chip.
- `pid` → monitor workflow PID when `workflow_state.pid` missing.
- `output_path` → FAILED workflow synthetic-output path only (status FAILED rows).
- `finalizer_status.phase/status/updated_at/instance_count` → FINALIZING overlay / `⊛` chip (`finalizer_row_state.py`).
- `finalizer_status.instances[].id/status/op/step` → chip label.
- `auto_restart` (provenance dict) → replacement-row chip (`apply_provenance_to_agent`).
- `agent_session_turn` subset below.

### `WaitingMarkerWire`

- presence (`waiting is not None`) + active status → force `WAITING`.
- `waiting_for` / `wait_for_beads` / `wait_for_hoods` / `wait_for_epics_of` / `wait_epic_follows` / `wait_turn_bindings` → wait display (overrides meta).
- `wait_duration` / `wait_until` → wait ticks / suffix.
- `queue_capacity` / `queue_capacity_multiplier` / `queue_capacity_explicit` / `wait_runners*` / `wait_priority*` / `queue_weight*` → queue chips.
- `slot_requested_at` / `held_by` / `hold_expires_at` → hold/queue paint.

### `PendingQuestionMarkerWire`

- presence → `runner_slot_yielded`.
- `request_path` → QUESTION vs ANSWERED (`pending_question_status_for_request_path`).

### `RunningMarkerWire`

- presence → home running row (required; `running is None` drops the row).
- `pid` / `process_identity` → live PID gate, kill, dedup merge.
- `cl_name` / `model` / `llm_provider` / `vcs_provider` / `workspace_dir` → identity + live filters + provider chip.

### `WorkflowStateWire` + `WorkflowStepStateWire`

- `workflow_name` → parent `workflow`/`display_name`; live `workflow:`; kill kind (hook/mentor/crs).
- `cl_name` → identity.
- `status` → parent display (`WAITING INPUT`/`DONE`/`FAILED`/`RUNNING`); child RUNNING→FAILED/DONE propagation.
- `pid` → liveness; dead PID + no in-progress step → FAILED (unless session-turn member).
- `appears_as_agent` / `is_anonymous` / `hidden` → display type; fold; live `hidden:`.
- `current_step_index` + `steps` length → progress identity.
- `start_time` → fallback `start_time` if timestamp unparsable.
- `error` → FAILED list error (parent + in-progress children).
- `steps[].name/status/output/error` → last `output` dict for parent `step_output`; reverse scan for `output.diff_path`; failed-step error fallback.
- `activity` is copied onto `Agent.activity` and is not in the list render key.

### `PromptStepMarkerWire`

- `file_name` → `prompt_step_file_name`; hydration match (`_projected_record.py`).
- `workflow_name` → `workflow` + `parent_workflow` (child linkage).
- `step_name` / `step_type` / `step_source` / `step_index` / `total_steps` / `parent_step_index` / `parent_total_steps` → child identity (`cl_name=step_name`); tree title; runtime suffix only if `step_type=="agent"`; live `kind:workflow-child`.
- `status` → child display status.
- `hidden` / `is_pre_prompt_step` → fold hidden-step (pre-prompt forces hidden).
- `embedded_workflow_name` → live `workflow:`; render key.
- `artifacts_dir` → child artifacts; meta-reuse vs filesystem fallback.
- `diff_path` or `output.diff_path` → pencil.
- `error` → FAILED child.
- `model` / `llm_provider` / `reasoning_effort` / `model_alias` → live `model:`/`provider:`; provider chip.
- `output` keys `meta_*` (truthy) → parent `step_output` + status-apply parent merge; `meta_workspace` for workspace.

### `AgentSessionTurnWire` (meta + done)

Apply no-ops without string `id` (`_meta_enrichment_monitor.py` / `_meta_enrichment_gate.py`).

**Shared:** `kind`, `id`, `state`, `label`, `start_status`, `stop_status`, `followup_outcome`, `followup_error`, `followup_agent`, `followup_degraded_reason`.

**Monitor:** `monitor.exit_code`; `host_completion_status`. Used by list paint, grouping Monitoring bucket, kill kind (`is_monitor` + `monitor_state=="running"`), fold gating.

**Gate:** `gate.kind`, `gate.accent`, `gate.bundle_path`, `gate.notification_id`. Used by list paint, `is_gate` (`agent_session_role` + `gate_id`), Enter/gate actions (`_agent_enter_index.py`), fold gating.

`is_monitor` is role/suffix (`agent_session_role`/`role_suffix`), not `monitor_id` alone (`agent.py`).

### `WaitTurnBindingWire`

- `name`, `turn_name` → wait chip (`format_wait_targets`); render-key tuple.

### `Agent` list identity (derived, `agent.py`)

- `identity = (agent_type, cl_name, raw_suffix)` (clan/session containers special-case).
- `child_linkage`: `parent_workflow` → workflow-step; else `parent_timestamp` → session member.
- Fold: `raw_suffix` or `clan:{name}:{generation}`; parent fold `parent_timestamp` (`_agent_tree_fold.py`, `_fold_filter.py`).

### Dedup / status / time (post-load)

- `_dedup.py`: identity, `status`, `pid`, `process_identity`, `raw_suffix`, `workflow`, `project_file`, `workspace_num`, `model`, `diff_path`, `step_output`, `error_message`, `runner_is_live`.
- `_agent_status_apply.py`: `status`, `role_suffix`/`agent_session_role`, plan times, `step_output.meta_*`, `diff_path`, `runner_is_live`, `agent_type` DONE markerless vs done.json, `questions_times`.
- `_agent_time_aggregate.py` / `_agent_time_intervals.py`: `start_time`/`run_start_time`/`stop_time`, plan/feedback/questions times, `runtime_children`, `step_type=="agent"`, monitor/gate membership, planner-phase `role_suffix`/`step_name=="plan"`.

### Live query (`agent_live_query.py` + `agent_live_query_pushdown.py`)

Pushable: `cl`, `model` (contains); `provider`, `type`←`kind`, `project`, `machine` (equals). Fallback (in-memory): `after/attempt/attention/before/clan/session/hidden/max/min/name/needs/pinned/retry/role/since/source/status/stranded/tab/text/tribe/unread/until/workflow`. `_metadata_values` is only `cl_name`/`display_name`/`agent_name`/`status`.

---

## 2. DEFER (field path → why)

**Explicitly restored on selected-detail hydration** (`_projected_record.py`):

- `done.step_output` full dict / last `workflow_state.steps[].output` / matching `prompt_steps[].output` → list keeps `meta_*` + `diff_path`; `_raw`/`_data`/`meta_commits`/`meta_commit_*` wait for hydrate.
- `agent_meta.linked_repos` (`name`, `workspace_dir`) → skipped when `record_shape=="list"`; restored on hydrate. Linked-commit diffs then feed `_agent_status_diff.py` / `linked_file_change_hint`.

**Scan already omits:**

- `record.raw_prompt_snippet` → `include_raw_prompt_snippets=False`.

**Copied by loaders, unused by list paint/filters/grouping/identity/runtime/status/dedup/row-local capability:**

- `record.used_macros[]` → unused by TUI list.
- `done.finished_at`, `done.pid`, `done.patch_name`, `done.imported_transaction_key`, `done.stopped_by`.
- `done.traceback` / `workflow_state.traceback` / `prompt_steps[].traceback` / `steps[].traceback` → detail error panel.
- `done.markdown_pdf_paths` / `image_paths` / `video_paths` → `extra_files` file-panel only (`_done_common.py`).
- `instruction_bundle_files` → lazy filesystem `run_bundle_paths`, not wire.
- `done.response_path` / `output_path` (non-FAILED-workflow) / `prompt_steps[].response_path` → detail.
- `agent_meta.output_variables` → copied; prompt-panel / revive / clan-summary sections; not list or live filters.
- `agent_meta.artifact_agent_id` / `artifact_source_dir` / `patch_name` / `changespec_name` / `bead_id` / `sdd_prompt_path` / `commit_patch_name` / `commit_changespec_name` / `stitch_id` / `commit_entry_id` / `commit_result` / `parent_agent_timestamp` / `parent_agent_name` / `workflow_name` (meta; parent uses `workflow_state`) / `output_path` (non-FAILED) / `model_alias_trail` / `model_alias_origin` / `proc_id` / `turn_kind` / `autonomy` / `monitor_queue_weight_overridden`.
- `waiting.patch_name` / `waiting.cl_name` / `waiting.eligible_since`.
- `running.patch_name`.
- `workflow_state.pdf_status` / `steps[].output_types` / `prompt_steps[].output_types` / `prompt_steps[].model_alias_trail|origin`.
- Turn diagnostics: `timeout_seconds`, `elapsed_seconds`, `output_path`, `output_truncated`, `request_fingerprint`, `next_action/output/model`, `completion_ref`, `profile`, `policy_digest`, `followup_prompt_path`, `followup_attempt_*`, `followup_error_stage/type`, `host_completion_message/reason`.
- Monitor-only: `command`, `cwd`, `starter_agent`, `tail_lines`, `pgid`, `supervisor_identity`, `settled`, `idle_timeout_seconds`, `tool_run_id`, `tool_run_joined`.
- Gate-only unused by list/actions: `creator_agent`, `next_fork/suffix/role`, `next_raw_prompt`, `workspace_policy`, `decision_path`, `claim_holder_pid`.
- Meta continuation/monitor refs: `monitor_diagnostic_manifest_ref`, `monitor_retained_log_ref`, `continuation_*`, `monitor_followup_budget_decision_path`.
- Finalizer: `schema_version`, `reason`, `plan_digest`, `run_id`, `started_at`, `runner.pid/identity`, instance `attempt/max_attempts/started_at/finished_at/headline/warnings/reason`.
- Recovery unused by list: `ledger_key`, `kind`, `action`, `successor`, `model_changed`.

---

## 3. Compact step-row facts that must survive

**Workflow parent**

- Record: `timestamp`, `artifact_dir`, `project_file`, `workflow_dir_name`, `record_shape`, `has_done_marker`.
- `workflow_state`: `workflow_name`, `cl_name`, `status`, `pid`, `appears_as_agent`, `is_anonymous`, `hidden`, `current_step_index`, `start_time`, `error`, `steps[].name/status/output{meta_*,diff_path}/error`.
- `prompt_steps` non-empty (children exist).
- `done.outcome` if present (`monitored`/`gated` drop vestigial parent).
- Meta identity/status/wait/plan/session/clan/turn/finalizer subset above.
- `waiting` / `pending_question` / `plan_path` / `running` (monitor pid).

**Prompt-step children**

- `file_name`, `workflow_name`, `step_name`, `step_type`, `step_source`, `step_index`, `total_steps`, `parent_step_index`, `parent_total_steps`, `status`, `hidden`, `is_pre_prompt_step`, `embedded_workflow_name`, `artifacts_dir`, `diff_path`, `error`, `model`, `llm_provider`, `reasoning_effort`, `model_alias`, `output.meta_*`, `output.diff_path`.
- Parent `workflow_state.status/error/appears_as_agent`.
- Parent `agent_meta.plan_approved` + `plan_action` (stale RUNNING plan-step → DONE).
- Parent `timestamp` as `raw_suffix`/`parent_timestamp`; `record_shape` + `artifact_dir` for later match.

---

## 4. Marker presence vs parsed-state

| Signal | Effect |
|---|---|
| `has_done_marker=True` and `done is None` | No done row (`_done_snapshot_loaders.py`). |
| Parsed `done.outcome=="noop"` | Dropped. |
| `repeat_stopped=True` with `outcome=="completed"` | STOPPED. |
| `running is None` | No home running row. |
| `workflow_state is None` | No workflow parent. |
| Empty `prompt_steps` | No children. |
| `waiting is not None` on STARTING/RUNNING | WAITING, even if wait lists empty. |
| Empty meta `wait_for` vs missing | Empty does not copy; `None` duration vs `0` matters for wait-directive presence. |
| `pending_question is not None` | `runner_slot_yielded`; QUESTION unless `request_path` says ANSWERED. Simultaneous waiting marker wins. |
| `done.outcome` in `{monitored,gated}` | Skip vestigial `workflow_state` parent (`SETTLED_AGENT_SESSION_TURN_DONE_OUTCOMES`). |
| `agents_list_projection=True` | Index omits waiting-only records (waiting marker without meta/done/running/workflow). Test: `tests/test_agent_loader_agents_list_projection.py`. |
| Turn `id` missing/non-string | `apply_monitor_meta` / `apply_gate_meta` no-op; role/suffix still classify monitor; gate needs `gate_id`. |
| Dead `workflow_state.pid` + no in-progress step + not session-turn | Parent FAILED. Session-turn member keeps RUNNING. |

---

## 5. Output-variable keys live filters inspect

None. Live query never reads `agent.output_variables`. Repeat STOP is `done.repeat_stopped` / `outcome=="stopped"`, not a `STOP` var lookup. `output_variables` is prompt-panel / clan-summary / revive only.

List-time `step_output` keys (not live-query): any `meta_*` (including `meta_workspace`) and `diff_path`.

---

## 6. Action capability facts (no full-record hydrate)

From `_app_action_availability_agents.py`, `_hijack_decision.py`, `_kill_identity.py`, `_wait_helpers.py`, `_agent_enter_index.py`:

- Identity: `agent_type`, `cl_name`, `raw_suffix`, `agent_name`.
- `status`; `hidden`; `approve` / `auto_approve_plan_action`.
- `pid`, `process_identity`, `runner_is_live`.
- `artifacts_dir` / `index_record_dir` / `record_shape` (know list vs full; do not need hydrated `step_output`/`linked_repos`).
- `tribe` / `agent_tab`.
- `agent_session` / `agent_session_role` / `role_suffix` / `plan_chain_root` / `is_workflow_child`.
- `parent_timestamp` / `parent_workflow` / `workflow` (kill kind: monitor/workflow/hook/mentor/crs/running).
- Wait lists + duration/until + queue fields (wait/fork).
- `gate_id` / `gate_kind` / `gate_state` / `gate_bundle_path` / `gate_notification_id`.
- `monitor_id` / `monitor_state`.
- `fleet_origin_alias`, `fleet_capabilities` (`lifecycle.stop/retry/fork`), `fleet_attention`, `fleet_content`, `fleet_dispatch_operation_key`.
- `hijack_id` / overlay / expired; `is_named_proc` / `is_bulk`; `workspace_num`.
- Recovery `state`/`reason`/`episode_id` for restart chips; not traceback, prompts, media, instruction manifests, or full output dicts.

I’ll add the compact list contract as a new additive `agent_scan/list` module, then wire the query, scan, and PyO3 entry points.

I'll pick up the remaining clippy fix, then verify the compact-list work and close the bead. First I'll load the required skills and inspect the failing test.

Clippy is the one remaining compile error. I’ll patch that test, then load lint rules and confirm the sase-core checkout.

Bead is still in progress. Next I’ll read the sase-core instructions, then re-run clippy and gather the inventory for the close note.

Bead output was truncated, so I’ll pull notes and the field inventory, then run clippy and the core check.

I’ll pull the KEEP/DEFER inventory from the earlier work, then confirm the wire types cover those fields.

The inventory marks `status_bucket` and waiting hold fields as KEEP. I’ll check whether those made it into the compact wire.

Implementation looks complete. I’ll run clippy, then the compact tests, and start the core gate.

Clippy ran in the wrong checkout. I’ll run it from the sase-core tree.

The last commands ran in the sase tree, not sase-core. I’ll check that test run and switch to the linked checkout.

That test was the sase wrapper rebuilding the extension. I’ll stop it and run the compact tests in sase-core.

Compact tests passed. I’ll start the sase-core gate and record the field inventory while it runs.

The gate may have run in the sase project. I’ll inspect that command and confirm which catalog it used.

That check is the sase project gate, not sase-core. I’ll stop it and rerun from the linked checkout.

I’ll record the inventory note, then start the sase-core check from its checkout.

The compact list contract is in sase-core and bead `sase-1t3.10.1.1` is closed.

Additive wire types `AgentArtifactListRecordWire` / `AgentArtifactListSnapshotWire` (`schema_version=1`, `record_shape=compact`, `meta`/`workflow`) project from the existing full scan and index pipeline. PyO3 bindings: `scan_agent_artifacts_list`, `scan_agent_artifact_dirs_list`, `scan_agent_artifact_dir_list`, `query_agent_artifact_index_list`, `agent_artifact_list_wire_schema_version`. Full-record APIs are unchanged; no production Python caller uses the new bindings yet.

Verified: compact unit tests (8) and PyO3 round-trip; `sase tool run check acf469d8b5a150564d53d8a6fc81bb4c` from sase-core succeeded; `sase bead epic-symbols` had no leftovers. Field KEEP/DEFER inventory is on the bead note.

The host will stitch sase-core after this turn. `sase-1t3.10.1.2` should pin `sase-core-revision.txt` to that commit. One proposed follow-up: Rust full `WaitingMarkerWire` / meta / done still omit `held_by`/`hold_expires_at` and `status_bucket`; compact rows cannot emit them until the scanner parses them.

Scratch files are removed. The host will commit the sase-core tree after this turn.
