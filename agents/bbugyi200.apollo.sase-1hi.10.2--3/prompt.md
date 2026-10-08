%queue(weight=1)
%auto
#fork:sase-1hi.10.2--2
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-08T12:20:29.851772+00:00 |
| **Finished** | 2026-10-08T12:45:27.059038+00:00 |
| **Elapsed** | 24m 56s of a 1h 0m 0s budget |
| **Output** | 158 KiB · evidence refs: `file:monitor-diagnostic-manifest:gb3vz2sq0gma`, `file:monitor-retained-log:gb3vz2sq0gma`, `file:monitor-stage:lint-symvision-3306378-1791462443648670178-eca0ba39`, `file:monitor-stage:test-scoped-3405451-1791463523006407688-8949acab` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show gb3vz2sq0gma --all-lines` |
| **Tool run** | sase tool show c6c8f235a102ab9b2efbc727683931f5 |

**Why this was monitored:** Verify before host completion

## Failure triage

verdict: new_failures — 7 NEW, 62 KNOWN; exit 1

NEW test (scoped): FAILED tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_prompt_semantic.py::test_agent_macro_and_prompt_receive_roles_replies_do_not — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_bead/test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_gate_cli_answer_detach.py::test_ordinary_gate_detaches_when_explicitly_asked — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_plan_approval_actions_archive.py::test_neutral_plan_archive_failure_is_retryable_without_duplicate_option_work — recorded evidence; no owner
NEW test (scoped): FAILED tests/test_finalizers_discard_guard_before_head.py::test_post_dispatch_foreign_race_on_external_is_exempt — recorded evidence; no owner
KNOWN 62; FLAKY 0

sase tool show c6c8f235a102ab9b2efbc727683931f5 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=4625, output_lines=59, retained_bytes=4625]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  BeadBoardSnapshot in src/sase/core/bead_read_facade.py
  BeadStoreFingerprint in src/sase/core/bead_read_facade.py
  CacheKeyInputs in src/sase/instructions/cache.py
  CoreMemoryUnit in src/sase/amd/memory_units.py
  InstructionManifestError in src/sase/core/instruction_manifest.py
  InstructionManifestError in src/sase/instructions/manifest.py
  MemoryIntroTexts in src/sase/amd/memory_units.py
  ParityIssue in src/sase/instructions/parity.py
  ParityReport in src/sase/instructions/parity.py
  ReferenceMemoryUnit in src/sase/amd/memory_units.py
  RunManifest in src/sase/instructions/manifests.py
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
  expanded_row_text in src/sase/ace/tui/modals/plan_decision_rows.py
  finalizer_owned_monitor_refusal in src/sase/monitor/start_flow.py
  finalizer_reports_failure in src/sase/axe/run_agent_exec_finalize.py
  git_fetch_origin in src/sase/llm_provider/commit_finalizer_git_status.py
  git_is_ahead_of_upstream in src/sase/llm_provider/commit_finalizer_git_status.py
  git_remote_tracking_ref in src/sase/llm_provider/commit_finalizer_git_status.py
  grok_cwd_dir in src/sase/instructions/_runs.py
  grok_sessions_root in src/sase/instructions/_runs.py
  hidden_sidecar_clone_dirs in src/sase/sdd/_store_maintenance.py
  instruction_shadow_render_enabled in src/sase/llm_provider/_instruction_boundary.py
  is_unverified_row in src/sase/ace/tui/modals/plan_decision_rows.py
  macro_input_choice_to_wire in src/sase/macro/_input_hint_wire.py
  maybe_gc_hidden_sidecar_clone in src/sase/sdd/_store_maintenance.py
  observe_agy_session in src/sase/instructions/agy.py
  prune_cache_entries in src/sase/instructions/cache.py
  report_to_json_dict in src/sase/instructions/render.py
  route_bead_targets in src/sase/core/bead_target_routing_facade.py
  run_instructions_render in src/sase/main/instructions_handler.py
  run_instructions_verify in src/sase/main/instructions_handler.py
  section_diff_to_json_dict in src/sase/instructions/render.py
  staged_sdd_files in src/sase/sdd/_commit_store.py
  validate_config_input_type in src/sase/ace/tui/modals/macro_config_modal.py
  write_acceptance_meta in src/sase/notification_gates/decision.py
error: Recipe `_lint-symvision` failed on line 410 with exit code 1
== test (scoped) (failed exit 1) ==
[counts: output_bytes=115696, output_lines=1758, retained_bytes=115696]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-missing, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 4963 test files in scope
coverage contexts: no baseline cached (run `just refresh-contexts-baseline`); static closure only
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
plugins: cov-7.1.0, xdist-3.8.0, mock-3.15.1, hypothesis-6.168.0, asyncio-1.4.0, inline-snapshot-0.35.4
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [7385 items]

........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  2%]
........s............................................................... [  3%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  9%]
..................................................................F..... [ 10%]
........................................................................ [ 11%]
.......................................

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true