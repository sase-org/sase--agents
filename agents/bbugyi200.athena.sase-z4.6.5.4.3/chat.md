# Chat History - ace-run (sase-z4.6.5.4.3)

- **TIMESTAMP:** 2026-09-10 18:39:08 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-z4.6.5.4.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-z4.6.5.4, bead=sase-z4.6.5.4.3)
%model:@medium
%auto
%w:sase-z4.6.5.4.1
%w(bead=sase-z4.6.5.4.1)
Can you complete the work for bead sase-z4.6.5.4.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-z4.6.5.4.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-z4.6.5.4.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-z4.6.5.4.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's details to understand the work required.

Now let's read the full `_admission.py` file, which appears central.

This confirms item A: `runner_capacity_snapshot` in `_admission.py` is the shared runtime admission entry point. Now let's look at the TUI model and CLI list entries.

Clean tree. I'll wait for the exploration agent's findings before designing the test.

Found it: `src/sase/agents/cli_list.py`. Let's read it fully.

Good, no epic-symbol cleanup needed for this phase. Now waiting on the Explore agent's findings about the capacity-display surfaces before designing the test.

I'll wait for the Explore agent's report before proceeding with test design.

That confirms `src/sase/agent_clis/cli_list.py` is unrelated (that's for `agent-cli list`, listing supported CLI providers, not `agent list`). The correct one is `src/sase/agents/cli_list.py` wired via `src/sase/main/agent_handler.py`. Now let's look at the TUI capacity header widget file C, and part D/E/F/G.

I found the core snapshot function directly. Let me hold off further manual digging and wait for the Explore agent's full report to avoid duplicating effort — checking if it has completed.

Still running. I'll wait for its completion notification rather than poll further.

Now let's look at D (queue rank/blockers/details), E (local/remote badges), F (unknown usage), and G (fold/filter) in the TUI. Let's search broadly.

`src/sase/ace/tui/widgets/prompt_panel/_agent_queue_section.py` looks highly relevant for D. Let's read it.

I'll pause here and wait for the Explore agent's completion notification.

This confirms the filter-by-status query language: `src/sase/ace/agent_query/` (tokenizer, parser, evaluator, types) supports `status:failed` etc. Now let's confirm the fold mechanism more specifically for "folding queued agents" — check `fold_state.py`, `agent_group_fold.py`, and whether queue folding exists specifically.

Good, this confirms D's test pattern (direct `RunnerQueueEntry`/`RunnerCapacitySnapshot` construction for the queue ladder). Let's quickly check `test_agent_info_panel.py` and the fleet fixture file for E.

This is exactly item E's existing test, jackpot. Let's read that test in full.

This is the exact existing test naming and pattern for E. Let's view the rest of this test.

`test_runner_slot_queue_rank_matches_tui_projection` at line 247 is exactly the cross-surface consistency test pattern. Let's read it in full.

I have plenty of detail already. Let me do one more check on the WaitingMarkerWire fields and then compile the final report.

It's already built in the workspace venv. Let me verify the actual admission behavior for invalid/unknown queue weight directly against the real binding before writing test assertions.

I now have comprehensive findings across all nine areas. Here is the organized report.

Good — confirmed the compiled Rust extension is available in this project's `.venv`, so tests calling `runner_capacity_snapshot` directly (no mocking of Rust) will work as the existing tests already rely on.

Now here is the full research report.

---

# Research Report: Capacity Snapshot Consistency Across Admission / CLI / TUI

## A. The shared "capacity snapshot" source of truth

**File:** `src/sase/core/runner_slots/_admission.py`

- **`runner_capacity_snapshot(records: Iterable[AgentArtifactRecordWire], is_live: RecordLiveness, *, effective_limit, now=None, deference_seconds_per_step=0, deference_max_seconds=0, candidate=None) -> dict[str, Any]`** (line 340) — Converts each `AgentArtifactRecordWire` into a plain capacity-record dict via `_capacity_record_from_scan` (line 233), then delegates to the function below. This is the entry point used by admission (`run_agent_wait_slots.py`) and by the CLI list path (`agent_list_entries.py`).
- **`runner_capacity_snapshot_from_capacity_records(records: Iterable[Mapping[str, Any]], *, effective_limit, now=None, deference_seconds_per_step=0, deference_max_seconds=0, candidate=None) -> dict[str, Any]`** (line 372) — The true bottom of the stack. Builds a `request` dict (`effective_limit`, `records`, `candidate`, `now`, `deference_seconds_per_step`, `deference_max_seconds`) and calls `_core_runner_capacity_snapshot(request)` (line 148), which invokes `import_module("sase_core_rs").runner_capacity_snapshot(request)` — **the actual Rust binding call**. This one function is the single shared entry to the Rust admission engine (`sase-core`'s `runner_capacity.rs`, per the docstring at line 296-298 of `run_agent_wait_slots.py`). Its output shape (verified from Rust-call sites/tests) is a dict with keys: `effective_limit`, `occupied_lanes` (int), `occupied_capacity` (float), `waiters` (list of dicts: `artifact_dir`, `queue_position`, `priority`, `slot_requested_at`, `timestamp`, `requested_weight`, `wait_runners`, `eligible`, `blockers`), and `candidate_decision` (only when a `candidate` was supplied: `artifact_dir`, `decision` ∈ {`acquire_capacity`,`reuse_existing_claim`,`blocked`,`invalid`}, `owner_key`, `lineage_key`, `effective_weight`, `blockers`).
- **`_capacity_record_from_scan`** (line 233) — the canonical adapter from `AgentArtifactRecordWire` → capacity-record dict. Produces keys: `artifact_dir`, `project_name`, `workflow_dir_name`, `timestamp`, `has_agent_meta`, `has_done_marker`, `appears_as_agent`, `live`, `pending_question`, `pid`, `run_started_at`, `runner_claim_owner_key`, `parent_timestamp`, `agent_family`, `agent_family_role`, `agent_family_parallel`, `family_shell_kind/id/state`, `queue_weight`, `queue_weight_explicit`, `queue_weight_invalid`, `slot_requested_at`, `wait_runners`, `wait_runners_explicit`, `wait_priority`, `eligible_since`.
- A second adapter for the exact same dict shape, `_capacity_record_from_agent` (`src/sase/ace/tui/models/agent_runner_slots.py:347`), builds the identical key set from the TUI's `Agent` dataclass instead of the wire record — see C below.
- Higher-level helpers built on top: `running_agent_slot_count` (line 566), `live_runner_slot_waiters` (line 580, returns `tuple[RunnerSlotWaiter, ...]`), `may_start` (line 622), all re-derived from one `runner_capacity_snapshot` call — none hand-roll their own counting.

**Runtime admission caller:** `src/sase/axe/run_agent_wait_slots.py`, `_try_claim_runner_slot` (line 425) builds a `candidate` via `runner_slot_candidate_record` (`_admission.py:393`), scans live records with `_scan_runner_slot_records` (line 66), then calls `runner_capacity_snapshot(records, is_live, effective_limit=..., candidate=candidate, ...)` at line 514, and requires an authoritative `candidate_decision` via `_require_candidate_decision` (line 290) — "fails closed" if Rust doesn't return one.

## B. `sase agent list -j` CLI implementation

- **`src/sase/agents/cli_list.py`** — `handle_agents_list(args)` (line 34) is the actual command handler, wired from `src/sase/main/agent_handler.py:14-16`. (Note: `src/sase/agent_clis/cli_list.py` is an unrelated file for `sase agent-cli list`, i.e. the supported-provider-CLI inventory — not this command.)
  - `handle_agents_list` calls `agent_list_entries(include_recent=include_all, project=project_filter)` (line 40) from `src/sase/integrations/agent_list_entries.py`, then either `_print_json(agents)` (line 49) or `_print_pretty(...)`.
  - `_agent_to_json(agent: AgentListEntry) -> dict[str, object]` (line 56) is the actual JSON payload builder — it includes `queue_weight`, `queue_weight_explicit`, `queue_weight_invalid`, `queue_weight_error`, `wait_runners(_explicit)`, `wait_priority`, `slot_requested_at`, `runner_slots_in_use`, `runner_occupied_capacity`, `runner_effective_limit`, `runner_slot_queue_position`, `runner_slot_queue_size`, `runner_capacity_blockers`, `runner_slot_holders`, sourced from `agent.wait: AgentWaitInfo`.

- **`src/sase/integrations/agent_list_entries.py`** — `agent_list_entries(*, include_recent=False, project=None) -> list[AgentListEntry]` (line 56):
  - Calls `list_all_agents()`/`list_running_agents()` (from `sase.agent.running`), which return a `RunningAgentListing` (a `list[RunningAgentInfo]` subclass carrying `.artifact_snapshot: AgentArtifactScanWire` — see `src/sase/agent/_running_listing_types.py:66-83`).
  - `_runner_capacity_snapshot_from_listing` (line 171) calls **the exact same** `runner_capacity_snapshot(snapshot.records, is_live_fn, effective_limit=get_max_running_agents())` from `sase.core.runner_slots` (imported at line 26) — i.e., **CLI list -j reuses the identical admission-layer function**, not a re-derivation. It is only skipped (falling back to a position-only estimate in `_runner_slot_context`, line 192) when `snapshot` is `None` (i.e., the caller constructed a `RunningAgentListing` without an `artifact_snapshot`).
  - `_attach_runner_slot_context(entries, runner_slots_in_use, *, runner_capacity=None, runner_slot_holders=())` (line 116) maps the Rust snapshot's `waiters`/`occupied_lanes`/`occupied_capacity`/`effective_limit` onto each `AgentListEntry.wait` (an `AgentWaitInfo`, from `src/sase/integrations/_agent_list_entry_models.py`).

**Conclusion for B:** CLI `list -j` does **not** recompute capacity independently — it calls the same `runner_capacity_snapshot` Python wrapper (and hence the same Rust call) as the runtime admission path in `run_agent_wait_slots.py`.

## C. ACE TUI capacity header / capacity-strip

- **`src/sase/ace/tui/widgets/agent_info_panel.py`**, class `AgentInfoPanel` (line 14):
  - `_append_capacity_prefix(self, text: Text) -> None` (line 342) — appends `occupied/limit` (e.g. `"3.5/10"`) using `format_capacity_value` from `agent_runner_slots.py`, styled via `_runner_capacity_style()` (line 328, a pressure-based color ramp).
  - It consumes only **three pre-computed scalars** stored on the widget instance: `self._runner_limit: float`, `self._runner_occupied_capacity: float | None`, `self._runner_queue_count: int` — set via `update_runner_capacity(effective_limit, queue_count, occupied_capacity)` (line 128) or the batched `update_state(...)` (line 175, params `runner_limit`, `runner_occupied_capacity`, `runner_queue_count`). **It does not take the snapshot object and does not re-derive from raw records** — it is a pure presentation layer over already-reduced numbers.
  - `_build_display_text()` (line 399) is the top-level renderer; `_append_status_strip` (line 358) appends the `[N running · M queued · ...]` strip using the same scalars plus `self._runner_queue_count`.

- **Feed point:** `src/sase/ace/tui/actions/agents/_display_detail_info.py`, `_update_agents_info_panel_impl` (line 111): reads `self._agent_runner_capacity: RunnerCapacitySnapshot` (line 159-161) and passes `runner_capacity.effective_limit`, `.occupied_capacity`, `.queued_count` into `AgentInfoPanel.update_state(...)` (lines 185-187).
- **`self._agent_runner_capacity`** is a `RunnerCapacitySnapshot` dataclass (`src/sase/ace/tui/models/agent_runner_slots.py:45`, fields `effective_limit`, `slots_in_use`, `queued_count`, `queue: tuple[RunnerQueueEntry, ...]`, `occupied_capacity`), assigned at `src/sase/ace/tui/actions/agents/_loading_apply.py:404` from `boundary.runner_capacity`, which is computed in `src/sase/ace/tui/actions/agents/_loading_compute.py:206-211` by calling **`refresh_runner_slot_context(prep.filtered_agents, effective_limit=..., capacity_agents=prep.capacity_agents or None)`**.

- **`refresh_runner_slot_context`** (`agent_runner_slots.py:86`) converts each TUI `Agent` row into the same capacity-record dict shape via `_capacity_record_from_agent` (line 347) and calls **`runner_capacity_snapshot_from_capacity_records`** (line 116-119) — the same bottom-level Rust wrapper used by admission/CLI (see A), just fed from `Agent` objects instead of `AgentArtifactRecordWire`. `_apply_runner_capacity_snapshot` (line 212) then turns the raw Rust dict into the `RunnerCapacitySnapshot`/`RunnerQueueEntry` tuple and mutates each `Agent`'s `runner_*` fields.

**Conclusion for C:** the capacity header widget itself is a dumb renderer of 3 floats/ints; the actual TUI-side capacity computation happens one layer up in `refresh_runner_slot_context`, which converges on the exact same Rust `runner_capacity_snapshot_from_capacity_records` call as admission/CLI, but starting from a different (TUI `Agent`) adapter than the CLI/admission one (`AgentArtifactRecordWire`).

## D. Queue rank / blockers / details for parked agents

- **`src/sase/ace/tui/models/agent_runner_slots.py`**:
  - `RunnerQueueEntry` (line 28, frozen dataclass) — one waiter's presentation facts: `identity`, `presented_name`, `threshold`, `wait_runners_explicit`, `priority`, `slot_requested_at`, `status`, `requested_weight`, `eligible`, `blockers: tuple[dict[str, Any], ...]`, `parked: bool`.
  - `_apply_runner_capacity_snapshot` (line 212) builds `queue_entries` directly from the Rust snapshot's `waiters` list, using `queue_position` from Rust as rank (`_ordered_snapshot_waiters`, line 544) and `_snapshot_waiter_is_parked` (line 562, "parked" = not eligible and has a non-`queue-order` blocker).

- **`src/sase/ace/tui/widgets/prompt_panel/_agent_queue_section.py`** — renders the detail ladder for a selected waiting agent:
  - `runner_queue_selection(agent, capacity: RunnerCapacitySnapshot | None)` (line 51) — resolves a selected agent's index into `capacity.queue`.
  - `append_runner_queue_section(text, agent, selection)` (line 78) — renders the `❖ QUEUE · N waiting · M parked · occupied/limit capacity` heading plus a bounded window of ranked rows.
  - `_queue_window(queue, selected_index)` (line 159) — the "folding" logic: shows all rows if `len(queue) <= 7`, otherwise shows only a window around the selected row plus `#1`, collapsing the rest into `_QueueWindowRow(hidden_count=N)` rows rendered as `"… +N more"` (line 144).
  - `_queue_entry_capacity_detail` / `_queue_entry_capacity_parts` / `_has_capacity_blocker` (lines 272-322) — turn each entry's `blockers` (Rust-produced dicts with `code`, `message`, `free_capacity`, `needed_capacity`) into human text: `"weight exceeds current limit"` (code `weight-exceeds-limit`), `"invalid weight"` (code `invalid-request-weight`), `"priority deference"` (code `deference-window`), else falls back to `blocker["message"]`.

- **CLI-side queue position/blockers**: `src/sase/integrations/agent_list_entries.py`, `_runner_slot_context` (line 192) builds `positions: dict[int, int]` and `blockers: dict[int, tuple[dict, ...]]` from the same Rust `waiters`/`blockers` shape, attached onto `AgentWaitInfo.runner_slot_queue_position`, `.runner_slot_queue_size`, `.runner_capacity_blockers` (see B). There is no separate "queue rank" computation in the CLI — it reuses Rust's `queue_position` exactly like the TUI.

- **Per-row wait detail (not the full ladder)**: `src/sase/ace/tui/widgets/prompt_panel/_agent_wait_section.py`, `_runner_capacity_parts` (line 279) and `_runner_wait_has_detail` (line 269) — the single selected agent's own "needs X / Y free" line, gated by `agent.queue_weight_invalid` (returns nothing when invalid — see F).

There is no field literally named `queue_rank` anywhere; the canonical name is `queue_position` (Rust wire) / `runner_slot_queue_position` (Python `Agent`/`AgentWaitInfo` field) / local variable `rank` in `_agent_queue_section.py`.

## E. Local vs remote non-default weight badges

- **Single badge implementation (shared by local rows and the queue ladder):** `src/sase/ace/tui/widgets/_queue_weight_badge.py`:
  - `append_queue_weight_badge(text, weight, *, pad=True) -> bool` (line 14) — appends `"wN"` (e.g. `w0.25`) using `format_queue_weight_badge_value` from `agent_runner_slots.py:73`, which returns `None` for a default (≈1.0) or invalid weight — the same non-default filter used everywhere.
  - `append_agent_queue_weight_badge(text, agent: Agent) -> bool` (line 26) — the row-level badge, gated off for clan containers/proc shells/gate/monitor rows, otherwise renders `wait_display_agent(agent).queue_weight`.
  - Used from `src/sase/ace/tui/widgets/_agent_list_render_agent_status.py:62` (row status badge) and `_agent_queue_section.py:237` (queue ladder badge) — **there is no separate "remote badge" widget**; remote (fleet) rows use the identical `append_queue_weight_badge`/`format_queue_weight_badge_value` code path, just fed a `queue_weight` sourced differently.

- **Remote weight is populated purely as display metadata from the federation payload, structurally isolated from local admission:**
  - `src/sase/ace/tui/models/_fleet_agents_rows.py`, `rows_from_response(...)` (line 23) builds `Agent` rows straight from a remote host's federation JSON (`host_payloads`/`summary_payloads`); `_queue_weight(summary)` (line 300) and the `Agent(... queue_weight=..., queue_weight_explicit=summary.get("queue_weight_explicit") is True, queue_weight_invalid=..., queue_weight_error=... )` construction (~line 189-196) copy the remote-reported weight verbatim onto the row for **display only**.
  - Fleet rows are on a completely separate projection path from the local admission scan: `src/sase/ace/tui/actions/agents/_fleet_projection.py`, `_agents_source_for_current_mode(local_agents)` (line 101) returns fleet rows (via `_fleet_rows_with_dispatch_provisionals`) *instead of* local scan-derived agents when the Agents pane is in fleet mode; `is_remote_fleet_agent(agent)` is defined in `src/sase/ace/tui/actions/agents/_remote_lifecycle.py:13`.
  - **Why remote weight can't charge local capacity:** a fleet `Agent` row has no local `pid`/`run_start_time` set by the local process/artifact scanner, so `_capacity_run_started_at` (`agent_runner_slots.py:465`) and `_capacity_record_is_live` (line 461) both evaluate as "not started/not live" for it even if it is fed into `_capacity_record_from_agent`; Rust's admission only counts a record as occupying a lane when it is both live and started (see `is_runner_slot_occupying_record`, `_admission.py:475`, and its Rust counterpart). This is verified by an **existing test**:
    - `tests/ace/tui/test_fleet_agents.py`, `test_project_fleet_agents_carries_remote_queue_weight_without_local_charge` (line 126): builds a `fleet_summary(queue_weight=0.25, queue_weight_explicit=True)` remote row via `project_fleet_agents`, asserts the row's badge renders `"w0.25 (RUNNING)"` and detail text `"Weight: 0.25 capacity units"`, then constructs one local `Agent` with default weight and calls `refresh_runner_slot_context([local, row], effective_limit=1)`, asserting `capacity.slots_in_use == 1` and `capacity.occupied_capacity == 1.0` — i.e. **the remote row's 0.25 weight is not charged**, only the local 1.0.

## F. "Unknown"/unrecognized weight (invalid usage) handling

- **Wire schema:** `queue_weight_invalid: bool` + `queue_weight_error: str | None` exist on both `AgentMetaWire` and `WaitingMarkerWire` (`src/sase/core/agent_scan_wire_markers.py:112-...` and `:231-255`, e.g. `WaitingMarkerWire.queue_weight_invalid`/`.queue_weight_error` at lines 251-252).
- **Admission layer:** `_record_queue_weight` (`_admission.py:173`) returns `(None, explicit, invalid=True)` whenever a waiting-marker or meta weight is present but non-finite/non-positive/wrong-type, so Rust receives `queue_weight: None, queue_weight_invalid: True` for that record (i.e., "unknown usage" is passed through explicitly rather than silently defaulted).
- **Fail-closed at the *candidate's own* weight**: `src/sase/axe/run_agent_wait_slots.py`, `_marker_queue_weight_state` (line 173) and `_candidate_scan_queue_weight_error` (line 355) raise `_invalid_queue_weight_error(...)` (`_RunnerSlotAdmissionError`, line 108-118) if *this* candidate's own persisted weight is invalid — admission refuses to start rather than guessing a default. Covered by an existing test:
  - `tests/test_run_agent_runner_slot_weight_invalid.py`, `test_invalid_waiting_marker_queue_weight_fails_closed` (whole 101-line file), parametrized over `[None, 0, -1, True, "0.25", inf, nan]`.
- **Display for *other* agents with unknown weight (not the candidate):** the `queue_weight_invalid`/`queue_weight_error` flags are threaded through `AgentListEntry`/`AgentWaitInfo` (`src/sase/integrations/_agent_list_entry_builder.py:370-378`, `_agent_list_entry_models.py:31-54`) and the TUI `Agent` (`src/sase/ace/tui/models/_agent_state.py:315-316`), then:
  - CLI JSON: `queue_weight_invalid`/`queue_weight_error` are both emitted verbatim in `_agent_to_json` (`cli_list.py:84-85`).
  - TUI per-agent detail: `_runner_capacity_parts` (`_agent_wait_section.py:279`) returns `()` (suppresses the "needs X" line) when `agent.queue_weight_invalid` is true; `_runner_wait_has_detail` (line 269) still flags the row as "has detail" so *something* shows.
  - TUI queue ladder: Rust surfaces an `invalid-request-weight` blocker code for such a waiter, rendered as literal text `"invalid weight"` by `_queue_entry_capacity_detail` (`_agent_queue_section.py:288`).
- There is no dedicated `"unknown"` string literal for this concept in the runner-capacity code (unlike the unrelated LLM-provider "usage" percentage code under `src/sase/llm_provider/usage/*.py`, which is a different "usage" subsystem entirely and not what the user's requirements describe).

## G. TUI filtering and folding

- **Status/text filtering (search query):** `src/sase/ace/agent_query/` package — `tokenizer.py` (recognizes `status` as a property key, line 36), `parser.py` (`parse_agent_query("status:failed")` → `PropertyMatch(key='status', value='failed')`, docstring lines 181-182), `evaluator.py` — `PropertyMatch` evaluation for `status` (line 96-97: `needle in (agent.status or "").lower()`), plus derived predicates like `_STOPPED_STATUSES`/`_NEEDS_INPUT_STATUSES` (lines 154, 183) and canonical serialization in `types.py` (`to_canonical_string`, lines 130-131). Driven from the TUI via `src/sase/ace/tui/actions/agents/_loading_finalize.py`'s `get_or_parse_agent_query` and `_loading_filter.py`'s `_get_or_parse_agent_query`/`_refilter_agents` (lines 29-114).
- **Hierarchical fold (family/workflow tree collapse):** `src/sase/ace/tui/models/_fold_filter.py`, `filter_agents_by_fold_state(agents, fold_manager: FoldStateManager) -> tuple[list[Agent], dict[str, tuple[int, int]]]` (line 8) — walks each agent's `agent_fold_key`/`agent_parent_fold_key`/`agent_gating_fold_key` (from `_agent_tree.py`) and a `FoldStateManager`/`FoldLevel` (`fold_state.py:13,112`) to decide row visibility; called from `_loading_compute.py`, `_filter_agents_by_fold_snapshot` (line 153).
- **Folding a queue of parked agents into a compact summary:**
  - The queue-ladder window truncation itself: `_queue_window` in `_agent_queue_section.py:159` (see D) — collapses non-adjacent waiters into `"… +N more"`.
  - Clan/container aggregate counts (including a `queued` bucket) rolled into one summary chip when a family/clan is collapsed to its container row: `src/sase/ace/tui/models/_agent_clan.py` (`queued` fields at lines 53, 61, 66, 162-188, 224-252) and `src/sase/ace/tui/agent_count_chip.py`, `format_agent_count_chip(...)` (line ~29) which renders a `[S.. R.. Q.. W.. F.. U.. D..]` compact chip including the `"queued"` metric (`AGENT_COUNT_CHIP_METRICS`, lines 18-25).
  - `refresh_runner_slot_context`'s fallback path (`agent_runner_slots.py:127`) also aggregates a clan container's status from its queued members via `aggregate_clan_status`/`clan_members` (`_agent_clan.py`), overwriting a container's own status once all its members are parked/queued.

## H. Existing tests already exercising these surfaces

- **`tests/test_agent_list_runner_slots.py`** (435 lines) — the closest existing precedent to what you want to write:
  - `test_runner_slot_queue_rank_matches_tui_projection` (line 247) builds the **same waiter specs three times** (once via `record()`+`_build_agent_list_entry`/`_attach_runner_slot_context` for the CLI/integration path, once via `TuiAgent(...)`+`refresh_runner_slot_context` for the TUI path, once via `record()`+`live_runner_slot_waiters` for the raw admission-layer helper) and asserts queue order/position match across all three (`integration_positions == tui_positions == {...}`, `integration_order == tui_order == core_order`).
  - Other tests in the same file: `test_runner_slot_wait_info_includes_live_count_and_queue_position` (29), `test_runner_slot_queue_orders_priority_before_fifo_with_default_priority` (81), `test_runner_slot_queue_orders_parked_waiters_after_open_thresholds` (151), `test_runner_slot_queue_defaults_invalid_priorities` (346), `test_pending_gate_member_frees_runner_slot` (408), `test_inherited_gate_id_without_gate_role_uses_ordinary_started_rule` (424).
- **`tests/ace/tui/test_agent_runner_slots.py`** (811 lines) — TUI-only capacity tests, e.g. `test_refresh_runner_slot_context_ranks_all_waiters_while_pool_is_full` (line 59), using a local `_agent(name, **overrides)` helper (line 20) that builds `Agent` dataclasses purely in memory and calls the **real** `refresh_runner_slot_context` (no Rust mocking).
- **`tests/ace/tui/widgets/test_agent_queue_section.py`** — direct unit tests of `_queue_window`/`runner_queue_selection` (queue ladder truncation and rank/selection logic) using local `_agent(...)`/`_entry(...)` builders (lines 26, ~63).
- **`tests/ace/tui/widgets/test_agent_info_panel.py`** — sets `panel._runner_limit`/`panel._runner_occupied_capacity`/`panel._runner_queue_count` directly and asserts on the rendered `Text` (e.g. lines 98-99, 272-297, 323-385) — confirms the header widget can be tested with bare scalars, no snapshot construction needed.
- **`tests/ace/tui/test_fleet_agents.py`**, `test_project_fleet_agents_carries_remote_queue_weight_without_local_charge` (line 126) — exactly the "remote weight is presentation-only, doesn't charge local capacity" test (see E).
- **`tests/test_agent_list_entries.py`** (594 lines) — `test_agent_list_json_exposes_runner_slot_fields` (line 30) builds an `AgentListEntry` via `_build_agent_list_entry`, then calls `_attach_runner_slot_context([entry], 0, runner_capacity={...raw dict shaped exactly like a Rust snapshot...})` and asserts on `_agent_to_json(entry)` — demonstrates that `_attach_runner_slot_context` accepts a **hand-built raw snapshot dict** (bypassing Rust) as an alternative synthesis point. Also imports `_agent_to_json`/`_status_badge` from `cli_list.py` directly (no argparse/stdout harness).
- **`tests/test_run_agent_runner_slot_lineage.py`** (398 lines) and **`tests/test_run_agent_runner_slot_weight_invalid.py`** (101 lines) — runtime admission tests (`_try_claim_runner_slot`) using the filesystem-lite `tests/_runner_slot_fixtures.py` helpers (writes small JSON files under `tmp_path`, then reads them back into `AgentArtifactRecordWire`) — these mock only `_scan_runner_slot_records`/`is_process_alive`/`get_max_running_agents`, not `sase_core_rs` itself (the real Rust binding runs).
- No dedicated end-to-end test drives `handle_agents_list` (the actual `sase agent list -j` argparse entry point + stdout capture) — only the JSON-payload-building helpers (`_agent_to_json`) are unit-tested directly.

## I. Existing lightweight synthetic-snapshot helpers

Yes — there are already two complementary, fully in-memory (no subprocess, no fakey harness, and for two of them no filesystem at all) builder sets, plus proof that the raw Rust-shaped snapshot dict can itself be hand-built and injected:

1. **`tests/_agent_list_entries_helpers.py`** (44 lines, pure in-memory, zero filesystem I/O):
   - `agent(**overrides) -> RunningAgentInfo` (line 13) — sensible defaults (`name`, `project`, `pid`, `model`, `provider`, `status`, `artifacts_dir`, etc.), override any field via kwargs.
   - `record(**overrides) -> AgentArtifactRecordWire` (line 34) — same pattern for the wire record (`project_name`, `artifact_dir`, `timestamp`, plus pass `agent_meta=AgentMetaWire(...)`/`waiting=WaitingMarkerWire(...)` overrides for `queue_weight`, `wait_runners`, `wait_priority`, `slot_requested_at`, `runner_claim_owner_key`, etc., since those are frozen dataclasses in `src/sase/core/agent_scan_wire_markers.py`).
   - These feed directly into `_build_agent_list_entry(agent(...), record=record(...))` (from `src/sase/integrations/_agent_list_entry_builder.py`) to get an `AgentListEntry`, then `_attach_runner_slot_context([entry, ...], running_count, runner_capacity=<raw dict or None>)` for CLI-side context, and separately into `_agent_to_json` for the exact CLI JSON payload — all without touching disk.

2. **`tests/_runner_slot_fixtures.py`** (107 lines, filesystem-lite): `artifact(tmp_path, name, pid, **extra_meta) -> Path` (line 18, writes a minimal `agent_meta.json`) and `record(path, *, started=False, meta_wait_priority=None) -> AgentArtifactRecordWire` (line 25, reads back `agent_meta.json`/`waiting.json` into a full wire record). Used only by the runtime-admission tests that need `_try_claim_runner_slot` to interact with `waiting.json`/`agent_meta.json` on disk under the runner-slot lock; **not required** if you only need to hand `AgentArtifactRecordWire`s straight to `runner_capacity_snapshot`/`runner_capacity_snapshot_from_capacity_records` (those take in-memory objects/dicts and never touch disk themselves).

3. **TUI side:** `tests/ace/tui/test_agent_runner_slots.py`'s local `_agent(name, **overrides) -> Agent` (line 20) and `tests/ace/tui/widgets/test_agent_queue_section.py`'s local `_agent(...)`/`_entry(...) -> RunnerQueueEntry` builders — same idea, `Agent(**dataclass kwargs)` directly, no loader/scan involved. `Agent` is defined in `src/sase/ace/tui/models/agent.py`.

4. **Fleet/remote side:** `tests/ace/tui/fleet_fixture.py`, `fleet_summary(...)` (line 76, builds a raw federation-response JSON dict with `queue_weight`/`queue_weight_explicit`/`queue_weight_invalid`/`queue_weight_error` kwargs at lines 98-101/178-185) and `fleet_host_response(...)` (line 189) — feed `project_fleet_agents(catalog_response=...)` (`src/sase/ace/tui/models/fleet_agents.py`) to get fleet `Agent` rows for the "remote badge" side of E.

5. **Raw Rust-snapshot injection, bypassing the binding entirely:** `tests/test_agent_list_entries.py:30` shows `_attach_runner_slot_context(entries, running_count, runner_capacity={ "effective_limit":..., "occupied_lanes":..., "occupied_capacity":..., "waiters":[{...}] })` accepts a **hand-authored dict shaped like Rust's actual output** — i.e., if you want a test that doesn't depend on the compiled `sase_core_rs` extension being present, you can fabricate the Rust-shaped snapshot dict once and feed it to both `_attach_runner_slot_context` (CLI) and `_apply_runner_capacity_snapshot` (TUI, `agent_runner_slots.py:212`, currently only called internally by `refresh_runner_slot_context` but importable/callable directly) for a snapshot-consistency comparison without invoking Rust at all.

6. **Confirmed the real Rust extension is available in this repo's venv** (`.venv/bin/python -c "import sase_core_rs; sase_core_rs.runner_capacity_snapshot"` succeeds), so tests can also choose to exercise the real binding (as `tests/test_agent_list_runner_slots.py` and `tests/ace/tui/test_agent_runner_slots.py` already do) rather than fabricating the output dict — no mocking is required either way.

**Bottom line for your planned test:** the natural "one snapshot → compare N presentations" test would construct one set of `AgentArtifactRecordWire` (or raw capacity-record dicts) using the `tests/_agent_list_entries_helpers.py` patterns, then: (1) call `runner_capacity_snapshot`/`runner_capacity_snapshot_from_capacity_records` directly for the "admission" viewpoint; (2) wrap the same records in `AgentArtifactScanWire(records=[...])` → `RunningAgentListing(..., artifact_snapshot=that)`, monkeypatch `list_all_agents`/`list_running_agents` in `sase.integrations.agent_list_entries`, and call `agent_list_entries()` → `_agent_to_json` for the CLI viewpoint; (3) build equivalent TUI `Agent` rows with matching fields and call `refresh_runner_slot_context` for the TUI viewpoint (capacity header scalars, `RunnerQueueEntry` queue, badges via `format_queue_weight_badge_value`/`append_queue_weight_badge`, and `_queue_window` folding) — then assert the three views agree on occupied capacity, queue order/position, blockers, and badge text, exactly following the shape of the existing `test_runner_slot_queue_rank_matches_tui_projection` in `tests/test_agent_list_runner_slots.py:247`.

Now I have thorough, empirically-verified ground truth for the test scenarios. Let me write the test file.

Now let's run this test file to verify everything works as designed.

Now let's fix the folding test's parent/child construction so the parent isn't classified as a "hidden-only" workflow.

Now fix the `_by_name` return type and the unused-variable lint warnings.

All 7 tests pass and only the expected informational (non-error) hints remain. Now let's run `just check` per this repo's verification convention since I've changed a tracked file.

Just a formatting issue. Let me run `just fmt` to auto-format, then re-run `just check`.

Now let's run `just check` for real this time.

I made a mistake — my `git stash` found no local changes to save (since my only edit is an untracked file), but the subsequent `git stash pop` popped a **pre-existing stash entry** that was already sitting in this repo's stash list before I touched anything, and it conflicts with the current tree. Let me carefully assess before doing anything else.

That popped stash (`gh-workflow-1789062836`) is unrelated CI-automation state, not mine or the user's in-progress work — and it's still safely preserved in the stash list since the conflicted pop didn't drop it. I'll cleanly reset my working tree back to HEAD to undo my mistaken pop, which won't touch the stash list or my own untracked test file.

HEAD matches the original session snapshot (840824c5b), confirming nothing else changed. Proceeding with the reset.

Recovery confirmed clean: working tree is back to exactly HEAD plus my own untracked test file, and both pre-existing stash entries are intact and untouched. I'll avoid `git stash` for the rest of this task — let me re-verify symvision's pre-existing failure a different way (checking git blame/log on those specific files instead of stashing).

My test change is verified clean; all 21 failures reproduce identically with my file removed, confirming they're pre-existing drift on master unrelated to this phase. Let me record these as proposed follow-ups and then close out the phase.

Now let's close the phase bead with a summary of what was verified.

Bead `sase-z4.6.5.4.3` is closed.

**What was done:** Added `tests/test_capacity_snapshot_parity.py` — 7 tests that build one shared weighted-capacity snapshot and prove runtime admission (`runner_capacity_snapshot`), `sase agent list -j`, and the ACE TUI capacity header/queue all agree on occupied capacity, queue order, blockers, and eligibility. It also locks in that remote weight badges never charge local capacity, that project filtering and TUI fold-collapsing never recompute the shared queue numbers, and that a single live claim with unrecognized weight fails the whole snapshot closed identically everywhere.

**Verification:** the new tests pass, formatting/ruff/mypy/keep-sorted are clean on the file, and I ran the full `just test-scoped` lane. It surfaced 21 test failures plus 3 red lint gates (feature-flags, symvision, test-waits) — I confirmed all of these reproduce identically with my new file removed, so they pre-date and are unrelated to this phase. I recorded them as `PROPOSED FOLLOW-UP` notes on the bead for the epic's land agent to triage into task beads.

One process note: partway through, I mistakenly ran `git stash`/`git stash pop` to sanity-check a symvision finding, which popped a pre-existing, unrelated CI-automation stash entry (`gh-workflow-1789062836`) and created merge conflicts. I caught it immediately and cleanly recovered with `git reset --hard HEAD` — both original stash entries are still intact in the stash list, untouched, and nothing was lost.

Single repository, single dirty file that this run wrote (`tests/test_capacity_snapshot_parity.py`, new since run start). Building the commit manifest now.

Declaration submitted and accepted: the commit finalizer will preserve `tests/test_capacity_snapshot_parity.py` for bead sase-z4.6.5.4.3, which was already closed per the prior turn's report.
