# Chat History - ace-run (sase-xr.6)

- **TIMESTAMP:** 2026-09-07 08:40:32 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-xr.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-xr, bead=sase-xr.6)
%model:@medium
%auto
%w(bead=sase-xr.5)
Can you complete the work for bead sase-xr.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-xr.6 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-xr.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-xr.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the SASE skills this phase depends on.

The bead is an acceptance phase for epic launches. Next I’ll read the plan and prior phases so the landing checks match the design.

I'll inspect prior phases, existing tests, and docs so this acceptance work fills the remaining gaps rather than duplicating them.

I’ll inspect the measure-phase benchmark, existing structural tests, and `docs/beads.md` to see what acceptance still needs.

I’ll inventory existing tests and docs against the acceptance gates so we only add what’s still missing.

I’ll map remaining gaps by reading the landed batch-launch work, work-command docs, and the tests the plan says to extend.

I’ll inspect launch-timing counters, lock/scan bounds, and recovery tests so the new structural gates match the real code.

I’ll inventory remaining test gaps and read the batch-launch APIs in parallel so the new gates match the landed code.

I'll start from the epic plan and the listed test/

implementation files, then

 map each

 structural

 gate and

 scenario to existing

 coverage.

I'll now read the listed suites and the scan/rebuild/lock APIs so we can map each required gate to existing tests.

Next I’ll inspect the cleanup, reservation, timing, and helper modules for the actual call-count and lock APIs.

The per-target revalidation path may still be scanning too often; I’ll read that next along with wipe-lock usage and existing registry tests.

# Acceptance coverage vs structural gates (`sase-xr.6`)

Implementation already has batch-ish paths (one catalog wipe, batch reserve, exact planned claim, selection snapshot). **Ordinary CI still does not assert the four structural gates**, and several production paths still do O(K×H) work. That is the main 10x/45s risk.

---



## 1. Already covered scenarios (with test functions)

### Waiting-to-running, all-active, family, collisions

 (mostly behavioral, not scan-bounded)

| Scenario | File | Tests |
|---|---|

---|
| Waiting owner starts running between preview and cleanup | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_relaunch.py` | `test_waiting_phase_that_starts_running_before_cleanup_is_preserved` |
| All-active retry skips ready/preclaim/checkpoint/spawn | same | `test_work_all_running_epic_is_idempotent_without_mutation` (`launch_state == "already_running"`) |
| Preserve running, launch missing | same | `test_work_preserves_running_phase_and_launches_only_missing_segments` |
| Stale owner wipe + rewrite | same | `test_work_stale_owner_round_trip_wipes_and_rewrites` |
| Interrupted family wipe | same | `test_work_interrupted_phase_family_is_wiped_before_retry` |
| Legacy clan skip | same | `test_work_retry_allows_legacy_epic_clan_container_skip` |
|

 Closed phases + lander | same | `test_work_all_closed_epic_launches_only_missing_lander`, `

test_work_all_closed_epic_preserves_matching_live_lander_without_mutation` |
| Clan join after failure | same | `test_work_relaunch_after_failure_joins_existing_epic_clan` |
| Mismatched / missing bead (family) | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_launch_cleanup.py` | `test_work_conflicting_family_bead_still_blocks`, `test_select_bead_work_launch_returns_blocked_targets_instead_of_raising`, `test_revalidate_raises_when_blocker_appears_after_preview`, `test_work_direct_registry_name_mismatch_without_beads_blocks` |
| Family member accepted via ancestor / beadless members | same | `test_work_family_member_with_ancestor_epic_bead_is_accepted`, `test_work_beadless_family_members_do_not_wedge_retry` |
| Planned/clan/family container collisions | same | `test_work_expected_name_container_conflict_aborts_before_mutation` |
| One registry snapshot for K slots | same | `test_select_bead_work_launch_uses_one_registry_snapshot` (counts snapshot **calls**, not archive scans) |
| Terminal / waiting / workflow-name alias | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead

/test_cli_work_collisions.py` | `test_work_retry_allows_terminal_same_name_attempt

`, `test_work_retry_force_reuses_live_phase_owner_and_launches`, `test_work_force_reuses_workflow_name_only_owner` |
| Task mismatched bead | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_task.py` | `test_task_work_refuses_mismatched_bead_owner_without_cleanup` |

### Cleanup apply / unrelated records

| Scenario | File | Tests |
|---|---|---|
| Stale later target aborts before any wipe | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_cleanup_apply.py` | `test_stale_later_target_aborts_before_any_wipe` |
| Partial wipe names completed owners | same | `test_partial_wipe_failure_names_already_wiped_owners`, `test_first_target_wipe_failure_has_no_stale_already_wiped_claim` |
| Apply is one `wipe_force_reuse_owners` call | same | `test_cleanup_apply_wipes_selected_owners_as_one_batch` |
| Bundle-only wipe + unrelated survive | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_name_wipe.py` | `test_wipe_dismissed_bundle_only_agent_removes_bundle_and_index`, `test_wipe_workflow_parent_removes_children_and_followups`, `test_wipe_family_member_finds_day_sharded_handoff_and_bundle`, `test_wipe_code_member_preserves_plan_member_and_family_container` |
| Batch wipe shares one catalog + one rebuild | same | `test_batch_wipe_shares_catalog_and_registry_rebuild` (`_scan_artifacts`/`_scan_bundles`/`rebuild_name_registry` each called once) |
| Newest family generation + clan preserved | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_names_forced_reuse.py` | `test_wipe_force_reuse_owner_replaces_newest_family_generation`, `test_wipe_force_reuse_owner_family_preserves_enclosing_clan`, `test_wipe_force_reuse_owner_refuses_populated_clan_container` |
| Concurrent member/dir races | same | `test_wipe_force_reuse_owner_family_tolerates_member_removed_concurrently`, `test_wipe_force_reuse_owner_concurrent_directory_removal_is_not_an_error` |
| Bundle-only registry collect | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_name_registry_rebuild.py` | `test_registry_rebuild_collects_bundle_only_agent` |
| Stale/missing index rebuild | same | `test_missing_index_rebuilds_on_lookup`, `test_stale_index_rebuilds_when_owner_disappears` |

### Reservations / exact child claim / concurrent claims

| Scenario | File | Tests |
|---|---|---|
| One snapshot for batch reserve | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_name_registry_reservations.py` | `test_batch_reserve_registered_names_uses_one_fresh_snapshot` (`load_name_registry` count == 1) |
| Collision is all-or-nothing | same | `test_batch_reservation_collision_is_all_or_nothing` |
| Two concurrent batch groups keep both claim sets | same | `test_concurrent_batch_reservations_preserve_unrelated_claims` |
| Current-owner alias claim | same | `test_batch_claim_uses_current_owner_alias_for_planned_entry` |
| Cleanup guard survives rebuild | same | `test_cleanup_guard_reservation_survives_rebuild` |


| Exact planned claim skips `_registry_file_is_stale` | same | `test_exact_planned_claim_avoids_stale_proof_lookup` |
| Planned survives rebuild until child claims | same | `test_planned_reservation_survives_rebuild_until_child_claims` |
| Clan collisions | same | `test_clan_reservation_blocks_exact_agent_name_but_allows

_hood_members`, `test_clan_reservation_rejects_existing_

agent_and_claims_first_member`, `test_concurrent_create_only_clan_reservations_allow_one_declaration` |
| Multiprocess-ish concurrent claims | same | `test_concurrent_claim_registered_name_preserves_all_claims`, `test_concurrent_explicit_claims_without_metadata_reject_collision` |
| Reservation evidence skips full spawn validation | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_launch_executor.py` | `test_execute_launch_plan_uses_matching_reservation_evidence_for_validation` |
| Parent reserves names+clan in one batch | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_launch_planned_bead_work.py` | `test_adapter_reserves_static_names_and_declared_clan_in_one_batch` |
| Partial spawn releases unconsumed reservations | same | `test_adapter_releases_unspawned_bulk_reservations_on_partial_

failure` |

### Crash / rollback / publication / later-target

| Scenario | File | Tests |
|---|---|---|
| Zero-spawn restore | `/home/

bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_lifecycle.py` | `test_

work_rolls_back_on_launch_failure`, `test_work_checkpoint_failure_rolls_back_before_launch`, `test_work_retry_does_not_unmark_already_ready_epic_on_launch_failure`, `test_work_rollback_restores_prior_in_progress_status` |
| Partial-spawn kill | same | `test_rollback_kills_partially_launched_agents` |
| Task zero-spawn | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_task.py` | `test_zero_spawn_failure_restores_prior_task_state` |
| Plan-file zero-spawn after publication | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_from_plan_resume.py` | `test_zero_spawn_after_publication_commits_and_publishes_rollback`, `test_plan_file_launch_failure_rolls_back_for_resume` |
| Publication failure before spawn | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_checkpoint.py` | `test_work_push_failure_stops_before_launch_and_preserves

_checkpoint`, `test_work_retry_push_failure_preserves

_existing_checkpoint`, `test_work_no_push_rejects_detached_store_before_launch` |
| Bead relocation rewrite | same | `test_work_rewrites_launch_query_and_env_after_graph_relocation` |
| Later-target failure keeps prior JSON Lines | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_multi_target.py` | `test_multi_target_short_circuits_on_first_failure_with_json_lines` |
| Plan-file later success/fail | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_from_plan_publication.py` | `test_synchronous_graph_push_failure_preserves_state_and_stops_launch` |

### Task / plan-file / dry-run / JSON / human

| Scenario | File | Tests |
|---|---|---|
| Task launch + dry-run + JSON | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_task.py` | `test_task_work_launches_one_checkpointed_agent`, `test_task_work_dry_run_is_read_only`, `test_task_work_json_reports_task_launch_state`, `test_in_progress_task_with_live_assignee_is_idempotent_success` |
| Plan-file resume | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_from_plan_resume.py` | `test_plan_file_resume_reuses_linked_epic`, `test_retrying_original_file_preserves_archived_bead_link` |
| Plan-file dry-run | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_from_plan_preview.py` | `test_plan_file_dry_run_is_pure_and_previews_waves` |
| Epic dry-run | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_dry_run.py` | `test_work_dry_run_never_mutates_or_launches` |
| Missing bead JSON | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_validation.py` | `test_work_missing_bead_json_error_is_one_envelope` |
| Timing instrumentation | `/

home/bryan/.

local/state/sase/workspaces/sase-org/sase/sase_19/tests/agent/test_launch_timing.py` | `test_slow_stage_is_marked_and_warned`, `test_durable_stage_events_preserve_nested_parentage` |
| Bench smoke only | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/bench_epic_launch.py` | `test_bench_epic_launch_smoke` (history=5, phases=1; **not** 10x/45s) |

---

## 2. Missing tests this acceptance phase should add (by file)

### Structural gates — **all four are missing as CI assertions**

No test asserts `full_scans`, `rebuilds`, or `parsed_source_files` vs K. Grep of `tests/**/*.py` for `full_scans|rebuilds=|parsed_source` is empty. Timing fields exist in production (`owner_discovery`, `registry_rebuild`, `registry_source_proof`) but are unused as

 bounds.

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_cleanup_apply.py`

- **K vs scans:** 1 vs 12 vs 40 selected slots, unchanged history; assert `scan_agent_artifacts`, `_scan_artifacts`, `_scan_bundles`, `rebuild_name_registry`, `_source_signature` do **not** grow with K.
- **Per-target revalidation:** `_verify_cleanup_target_still_selected` still calls `select_bead_work_launch(slots=(slot,))` or full `revalidate_...` per destructive target. Need a test that `load_agent_owner_view` / `registered_name_reservation_snapshot` are **not** called K times at apply.
- **Overlapping closures:** two roots sharing a retry/bundle child; each effect once; unrelated name

 intact.
- **

Incomplete indexes

:**

 truncated

 dismissed

/

artifact index must not

 authorize wipe of a selected owner.
- **Missing/corrupt selected metadata:** fail closed; unrelated records remain.
- **Crash after reservation / after some removals:** `cleanup_in_progress` + launcher PID dead → reconcile, no duplicate workers, leftover guard released or resumed.
- **New generation after preview:** abort, do not broaden.
- **Family-member promotion between preview and wipe:** abort or shrink per contract; do not expand.

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_relaunch.py`

- **All-active never enters wipe/publication:** patch `wipe_force_reuse_owners`, `mutate_registered_name_reservations`, `checkpoint_epic_work_launch`; already skips launch, but does **not** prove no snapshot/bead writes/reservations.
- **PID reuse:** WAITING/RUNNING owner whose `pid` now belongs to an unrelated process; must not treat as live or skip wipe incorrectly.
- **Duplicate aliases:** same slot matched by registry name **and** family/workflow alias → already raises in `select_bead_work_launch` (`multiple existing owners match one bead-work logical slot`) but has **no CLI test**.
- **Fresh launch does not parse historical bundles per segment.**

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_multi_target.py`

- **Later-target failure retains prior target success** at the **bead/registry** layer, not just JSON Lines dispatch mocks.
- **Command

-scoped reuse

:** second target must not reclean/reserve the first; mutable ownership refreshed; **no** preclaim of later targets.
- **Two concurrent launchers** with disjoint claim sets (process-level, not just ThreadPool on `reserve_registered_names`).

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_checkpoint.py` / `test_cli_work_from_plan_publication.py`

- Crash **after registry publication, before spawn**.
- Crash **between spawns** and **before child claim**.
- Rerun does not duplicate workers (planned reservations stay, claimed names not re-spawned).

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/test_cli_work_epic_dry_run.py` / `test_cli_work_task.py` / `test_cli_work_from_plan_preview.py`

- Dry-run must not call `mutate_registered_name_reservations` / `reserve_registered_names` (today only `test_axe_chop_clan_launch.py::test_dry_run_previews_one_concrete_clan_without_reserving_names` covers a different path).
- Human

 stderr progress vs JSON/JSONL stdout shape

 unchanged (`

launch_timing target=...` must

 stay

 off stdout).

### `/home/

bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_name_registry_reservations.py`

- **`RegisteredNameReservationRetryError`** after `max_retries` (class is untested).
- Concurrent **source** change (new artifact dir / bundle rewrite) → bounded retries + targeted reconciliation, **not** writing a stale whole-registry snapshot.
- Snapshot load **outside** lock; merge/write **inside**; `registry_file_is_stale` / `_source_signature` **not** under lock (today `_try_apply_reservation_plan` still calls `hooks.registry_file_is_stale(latest)` **inside** `mutation_lock()`).

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_name_wipe.py`

- Overlapping closures across many roots share **one** catalog.
- Incomplete/corrupt **unrelated** file: best-effort continue; corrupt **selected** owner: fail closed.
- Wipe must not hold `agent_name_allocation_lock` across `shutil.rmtree` / `killpg` / `_scan_artifacts

`.
- Incremental registry update vs mandatory full rebuild after wipe

 (`_execute_wipe_plan` still always

 `rebuild_name_registry()`).

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_names_forced_reuse.py`

- Family wipe must **not** call `find_agent_family` → `_iter_family_members` full `iter_ace_run_artifact_dirs()` per family (this is remaining O(K×H)).
- Shared catalog between container skip pass and member wipe (today: skip families, then `_wipe_names_for_reuse_batch` members → **second catalog scan + second rebuild**).

### `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_agent_launch_executor.py` + multi-prompt

- Child exact claim: `claim_exact_planned_registered_name` true → no `collect_artifact_entries` / bundle `read_json_object`.
- Public executor **without** evidence still uses strict validation.
- Spawn loop does not call `load_name_registry(trust_stale_proof_memo=False)` per slot.

### `/home

/bryan/.local

/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/bench_epic_launch.py` / `tests/agent/test_launch_timing.py`

- Small structural fixture: K=1 vs K=12 vs K=40 at H≈50–200; assert scan/rebuild/proof counts.
- Timing stages present: `initial_selection`, `owner_discovery`, `registry_lock_hold` with `lock_wait_ms`, `registry_rebuild`, `registry_source_proof`.
- Do **not** put 40k/45s in ordinary CI; keep `test_bench_epic_launch_smoke` tiny.

### Docs / artifact (acceptance text, not tests)

- `docs/beads.md`: progress lines, timing env, scheduling vs capacity admission — **not updated**.
- Benchmark report artifact: **not present**.

---

## 3. Recommended scan/rebuild bound test approach

Use a **small H** (tens–low hundreds of dummy artifacts + a few dismissed bundles) and **vary K**. Count calls, never wall-clock.

**Monkeypatch / wrap these:**

| What | Where | Why |
|---|---|---|
| Full owner discovery | `sase.core.agent_scan_facade.scan_agent_artifacts` (used by `load_agent_owner_view`) | `cli_work_cleanup_targets.py` always scans ace-run history |
| Wipe catalog | `sase.agent.names._wipe._scan_artifacts`, `_scan_bundles` | independent full parse of meta/done/bundles |
| Registry rebuild | `sase.agent.names._registry.rebuild_name_registry` or `_rebuild_name_registry_locked` | wipe still rebuilds after effects |
| Source proof | `sase.agent.names._registry_store.registry_file_is_stale` / `_source_signature` | reservation snapshot + merge retry |
| Historical parse | `sase.agent.names._registry_scan_payloads.read_json_object` and `_wipe._read_json_object` | “never parse historical bundles per segment” |
| Family walk | `sase.agent.names._lookup_groups._iter_family_members` or `iter_ace_run_artifact_dirs` | remaining per-family archive walk |
| Snapshot | `registered_name_reservation_snapshot` | must stay O(1) per target, not O(K) |

**Assert (unchanged H):**

- `scan_agent_artifacts` ≤ 2 per processed epic (preview + one revalidate), **independent of K**.
- `_scan_artifacts` + `_scan_bundles` ≤ 1 per cleanup batch.
- `rebuild_name_registry` ≤ 1 per cleanup batch (0 if incremental reconcile lands).
- `_source_signature` / `registry_file_is_stale` bounded (1–few retries), not ×K.
- `read_json_object` on dismissed bundles == 0 on fresh spawn / exact child claim.

**Use real APIs, not CLI wipe stubs:** many relaunch tests patch `wipe_agent_name_for_reuse` (singular). That trips `_wipe_names_for_reuse_batch`’s test fallback:

```296:304:src/sase/agent/names/_forced_reuse.py
    if (
        single_helper is not wipe_module.wipe_agent_name_for_reuse
        and batch_helper is wipe_module.wipe_agent_names_for_reuse
    ):
        ...
        return tuple(single_helper(name) for name in names)
```

Those tests **hide** remaining per-name work. Bound tests must **not** patch the singular helper.

**Timing-based alternative:** wrap `LaunchTimingRecorder` via `active_launch_timing_recorder()` and sum `full_scans` / `rebuilds` / `parsed_source_files` on stages `owner_discovery`, `owner_discovery_counts`, `registry_rebuild`, `registry_artifact_source_counts`. Production already emits those fields; no new counter API is required.

---

## 4. Recommended lock-hold assertions

Lock: `sase.agent.names._resume.agent_name_allocation_lock` (`fcntl` on `~/.sase/agent_name_allocation.lock`). Timing stage: `registry_lock_hold` with `lock_wait_ms`.

**Pattern:** wrap the lock context manager; while `depth > 0`, forbid:

- `scan_agent_artifacts`, `_scan_artifacts`, `_scan_bundles`, `read_json_object`
- `shutil.rmtree`, `_terminate_artifact_process` / `os.kill`
- `subprocess` / provider spawn / git push / network

**Current hole:** `rebuild_name_registry()` takes the lock then `_rebuild_name_registry_locked()` → `_collect_artifact_entries` / `_collect_dismissed_bundle_entries` (parses history **under the lock**).

**Second hole:** `_try_apply_reservation_plan` holds `mutation_lock` and calls `registry_file_is_stale` → `_source_signature()` (walks ~H paths under the lock).

**Contention test:** one thread/process holds the lock with a short sleep **outside** parse; another reservation waits; assert waiter’s `lock_wait_ms` > 0 and holder did not parse/delete under the lock.

**Exact claim path already good:** `claim_exact_planned_registered_name` only `read_registry` + `save_entries_locked` under the lock.

---

## 5. Helpers already in `cli_work_helpers.py` and nearby

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_bead/cli_work_helpers.py`

- `FakeLaunchResult` — stub spawn (`pid=4242`)
- `seed_diamond` — 4-phase DAG
- `seed_patch_epic`, `seed_task`
- `make_args` — `dry_run` / `yes` / `yes_to_all` / `json` / `no_push` / `wait`
- `write_bead_agent_meta` — live/waiting/done + family/clan fields
- `write_orphan_meta` — collision owners without beads
- `epic_clan_declaration`, `bead_wait_lines`

Also useful:

- `tests/test_bead/test_cli_work_epic_launch_cleanup.py`: `_phase_slot`, `_write_family_member`, `_stub_family_wipe`
- `tests/test_bead/cli_work_from_plan_helpers.py`: `EPIC_PLAN`, `write_plan_update`
- `tests/_agent_names_fixtures.py`: `make_agent` (used by registry tests)
- Wipe local `_artifact` / `_bundle` in `test_agent_name_wipe.py` and `test_agent_names_forced_reuse.py`
- `tests/perf/bench_epic_launch.py`: linear-time history seeder + `_temp_sase_home` + sleeper PIDs — reuse at **tiny** H for structural tests
- `tests/test_bead/work_test_helpers.py`: rendering-only (`epic`, `phase`, `seed`) — not launch/cleanup

---

## 6. Remaining repeated work that would miss 10x / 45s

These are still in the tree; CI will not catch them without the bound tests.

1. **Per-target revalidation still rescans history**  
   `_verify_cleanup_target_still_selected` → `select_bead_work_launch(slots=(slot,))` → `load_agent_owner_view()` (`scan_agent_artifacts`) + `registered_name_reservation_snapshot()` (cache reset + full proof). Family members revalidate the **entire** selection. Preview + revalidate + K verifies ≈ O(K) full scans.

2. **Family forced-reuse still walks the archive per family**  
   `_wipe_families_for_forced_reuse` → `find_agent_family` → `_iter_family_members` → `iter_ace_run_artifact_dirs()` + parse every `agent_meta.json`. Then a **second** `wipe_agent_names_for_reuse` catalog scan + rebuild.

3. **Wipe always full-rebuilds the registry**  
   `_execute_wipe_plan` → `rebuild_name_registry()`. Rebuild holds the **global allocation lock** while parsing artifacts and bundles.

4. **Reservation merge still fingerprints sources under the lock**  
   `_try_apply_reservation_plan`: `with hooks.mutation_lock(): ... hooks.registry_file_is_stale(latest)`.

5. **Wipe catalog is a second full history parse**  
   `_scan_artifacts` / `_scan_bundles` rglob+JSON, independent of `scan_agent_artifacts` used for selection. Unchanged H, growing K still pays two O(H) parsers plus one O(H) rebuild unless bounded.

6. **Snapshot always `reset_scan_caches()` + `trust_stale_proof_memo=False`**  
   Correct for freshness; must stay **once per target**, not once per slot. Apply-path currently violates that.

7. **CLI tests patch singular wipe**, so batch sharing is not what relaunch tests exercise.

8. **`RegisteredNameReservationRetryError` is untested** — concurrent source changes could spin or stale-write without a gate.

9. **No multiprocess lock-hold test** for parse/cleanup/network. Timing records `lock_wait_ms` but nothing asserts the critical section is short.

10. **`docs/beads.md` and the benchmark artifact** are still acceptance deliverables; `test_bench_epic_launch_smoke` cannot stand in for 40k/12-runner/45s.

**Litmus:** if `_verify_cleanup_target_still_selected` and `_iter_family_members` still run at 12 replacement slots against 40k sources, local orchestration will not hit 45s even if batch reserve and exact claim are perfect.

The remaining O(K) revalidation is the main risk. I’ll inspect the targeted-scan APIs and then start the fix plus structural tests.

I’ll fix the leftover per-target full scans, keep registry rebuild parsing off the allocation lock, then add the structural tests and docs.

I’ll replace per-target full scans with targeted checks, then move rebuild parsing off the name-allocation lock.

The locked rebuild fallback was treating a missing file signature as a conflict. I’ll restore that path so it writes under the lock without that check.

`_registry.py` is over the 700-line cap, so I’ll move the rebuild helpers out before running the larger benchmark.

Warm all-active is still ~11s at 40k because it full-scans history. I’ll add a registry-only fast path for already-running retries so that case stays on the K named slots.

Two cleanup-confirm tests failed. I’ll inspect them and fix the already-running fast path so orphaned family/clan releases still work.

The verify path was reclassifying stale clan/family releases as `REMOVE`. I’ll keep those targets stable when the registry entry is still a container with no live artifact.

Closed **sase-xr.6**. The parent epic is still open for its land agent.

Acceptance work is in the tree: leftover per-target archive revalidation is gone, registry rebuild parsing is off the name-allocation lock, and all-active retries no longer walk unrelated history. `docs/beads.md` now describes progress lines, `SASE_BEAD_WORK_TIMING`, and the split between scheduling and capacity admission.

**What was verified**
- `just check` passed (lint plus scoped tests). `sase bead epic-symbols sase-xr.6` was empty.
- Isolated 40k-history / 12-slot medians (n=5): fresh launch **25.1s cold / 22.9s warm** (~19× vs the recorded 486s production run); all-active no-op **3.53s cold / 1.19s warm**.
- Structural tests cover scan bounds vs slot count, lock-hold, dry-run non-reservation, and all-active skipping cleanup/publication.

**Report:** `file:explicit:8f8265e7880b018d112e5370`

Four sequential 40k fresh targets were **96.6s** vs the 90s goal, because each target still pays its own discovery pass. That is recorded on the bead as `PROPOSED FOLLOW-UP` for the land agent.
