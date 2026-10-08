- **AGENTS:**
  - [bbugyi200.apollo.sase-1hi.10.3--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.3.md)

%queue(weight=1) %auto #fork:sase-1hi.10.3--plan %model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false

# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
```

|              |                                                                                                                                                                                                                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Outcome**  | FAILED — exit 1                                                                                                                                                                                                                                                                                 |
| **Started**  | 2026-10-08T14:29:32.977623+00:00                                                                                                                                                                                                                                                                |
| **Finished** | 2026-10-08T14:40:33.291427+00:00                                                                                                                                                                                                                                                                |
| **Elapsed**  | 10m 59s of a 1h 0m 0s budget                                                                                                                                                                                                                                                                    |
| **Output**   | 10 KiB · evidence refs: `file:monitor-diagnostic-manifest:4x9knmyrhgva`, `file:monitor-retained-log:4x9knmyrhgva`, `file:monitor-stage:lint-symvision-4121714-1791470426664093222-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 4x9knmyrhgva --all-lines` |
| **Tool run** | sase tool show 6a0e3c26e82c33c8743c7465ef0f2d93                                                                                                                                                                                                                                                 |

**Why this was monitored:** Verify before host completion

## Failure triage

verdict: undetermined; exit 1

KNOWN 0; FLAKY 0

sase tool show 6a0e3c26e82c33c8743c7465ef0f2d93 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->

**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=5075, output_lines=68, retained_bytes=5075]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  AgentScope in src/sase/agent/scope_sweep.py
  BeadBoardSnapshot in src/sase/core/bead_read_facade.py
  BeadStoreFingerprint in src/sase/core/bead_read_facade.py
  CacheKeyInputs in src/sase/instructions/cache.py
  CoreMemoryUnit in src/sase/amd/memory_units.py
  InstructionManifestError in src/sase/core/instruction_manifest.py
  InstructionManifestError in src/sase/instructions/manifest.py
  MemoryIntroTexts in src/sase/amd/memory_units.py
  ParityIssue in src/sase/instructions/parity.py
  ParityReport in src/sase/instructions/parity.py
  ReapResult in src/sase/agent/scope_sweep.py
  ReapedScope in src/sase/agent/scope_sweep.py
  ReferenceMemoryUnit in src/sase/amd/memory_units.py
  RunManifest in src/sase/instructions/manifests.py
  ScopeMember in src/sase/agent/scope_sweep.py
  ScopeSweepPlan in src/sase/agent/scope_sweep.py
  WebMemoryUnit in src/sase/amd/memory_units.py
  advertised_config_type_names in src/sase/ace/tui/modals/macro_config_modal.py
  aggregate_rows in src/sase/instructions/verify.py
  bead_push_log_retention_config in src/sase/bead/_sync_logs.py
  cache_entry_path in src/sase/instructions/cache.py
  check_instructions_coverage in src/sase/doctor/checks_instructions.py
  check_instructions_delivery in src/sase/doctor/checks_instructions.py
  check_instructions_helpers in src/sase/doctor/checks_instructions.py
  classify_callout in src/sase/ace/tui/modals/plan_decision_document.py
  claude_projects_root in src/sase/instructions/_runs.py
  codex_sessions_root in src/sase/instructions/_runs.py
  collapsed_row_text in src/sase/ace/tui/modals/plan_decision_rows.py
  context_block_texts in src/sase/instructions/muse.py
  controller_failure_for_handoff in src/sase/finalizers/controller_run.py
  coverage_block_to_json_dict in src/sase/instructions/render.py
  default_provider in src/sase/instructions/facts.py
  detect_host in src/sase/instructions/facts.py
  discover_agent_scopes in src/sase/agent/scope_sweep.py
  expanded_row_text in src/sase/ace/tui/modals/plan_decision_rows.py
  fetch_worker_argv in src/sase/goals/fetch_worker.py
  finalizer_owned_monitor_refusal in src/sase/monitor/start_flow.py
  finalizer_reports_failure in src/sase/axe/run_agent_exec_finalize.py
  git_fetch_origin in src/sase/llm_provider/commit_finalizer_git_status.py
  git_is_ahead_of_upstream in src/sase/llm_provider/commit_finalizer_git_status.py
  git_remote_tracking_ref in src/sase/llm_provider/commit_finalizer_git_status.py
  grok_cwd_dir in src/sase/instructions/_runs.py
  grok_sessions_root in src/sase/instructions/_runs.py
  hidden_sidecar_clone_dirs in src/sase/sdd/_store_maintenance.py
  instruction_shadow_render_enabled in src/sase/llm_provider/_instruction_boundary.py
  is_agent_runner in src/sase/agent/scope_sweep.py
  is_unverified_row in src/sase/ace/tui/modals/plan_decision_rows.py
  macro_input_choice_to_wire in src/sase/macro/_input_hint_wire.py
  maybe_gc_hidden_sidecar_clone in src/sase/sdd/_store_maintenance.py
  observe_agy_session in src/sase/instructions/agy.py
  plan_scope_sweep in src/sase/agent/scope_sweep.py
  prune_cache_entries in src/sase/instructions/cache.py
  report_to_json_dict in src/sase/instructions/render.py
  route_bead_targets in src/sase/core/bead_target_routing_facade.py
  run_instructions_render in src/sase/main/instructions_handler.py
  run_instructions_verify in src/sase/main/instructions_handler.py
  section_diff_to_json_dict in src/sase/instructions/render.py
  staged_sdd_files in src/sase/sdd/_commit_store.py
  validate_config_input_type in src/sase/ace/tui/modals/macro_config_modal.py
  write_acceptance_meta in src/sase/notification_gates/decision.py
error: Recipe `_lint-symvision` failed on line 414 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the
original task. %macros_enabled:true
