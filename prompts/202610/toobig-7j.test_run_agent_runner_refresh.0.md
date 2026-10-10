- **AGENTS:**
  - [bbugyi200.athena.toobig-7j.test_run_agent_runner_refresh.0--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.toobig-7j.test_run_agent_runner_refresh.0.md)

%queue(weight=1) #fork:toobig-7j.test_run_agent_runner_refresh.0--plan
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false

# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
```

|              |                                                                                                                                                                                                                                                                                                                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Outcome**  | FAILED — exit 1                                                                                                                                                                                                                                                                                                                                                        |
| **Started**  | 2026-10-10T00:36:40.952412+00:00                                                                                                                                                                                                                                                                                                                                       |
| **Finished** | 2026-10-10T00:46:31.339659+00:00                                                                                                                                                                                                                                                                                                                                       |
| **Elapsed**  | 9m 49s of a 1h 0m 0s budget                                                                                                                                                                                                                                                                                                                                            |
| **Output**   | 61 KiB · evidence refs: `file:monitor-diagnostic-manifest:f6xq0s4xp1s4`, `file:monitor-retained-log:f6xq0s4xp1s4`, `file:monitor-stage:lint-symvision-1706427-1791592902467897611-eca0ba39`, `file:monitor-stage:test-scoped-1770104-1791593188474428842-8949acab` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show f6xq0s4xp1s4 --all-lines` |
| **Tool run** | sase tool show f03e7edcc6d5a5060cfd337163140ec4                                                                                                                                                                                                                                                                                                                        |

**Why this was monitored:** run command

## Failure triage

verdict: no_new_failures — 18 KNOWN; exit 1

KNOWN 18; FLAKY 0

sase tool show f03e7edcc6d5a5060cfd337163140ec4 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->

**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=2592, output_lines=25, retained_bytes=2592]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1j6.6(refresh_episode_report)'
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  AgentFailureAttributeErrorWire in src/sase/core/agent_auto_restart_wire.py
  AgentFailureChainLinkWire in src/sase/core/agent_auto_restart_wire.py
  AgentFailureFrameWire in src/sase/core/agent_auto_restart_wire.py
  AgentFailureImportErrorWire in src/sase/core/agent_auto_restart_wire.py
  AutoRestartLedgerHistoryWire in src/sase/core/agent_auto_restart_wire.py
  AutoRestartProbeWire in src/sase/core/agent_auto_restart_wire.py
  HealerTarget in src/sase/agent/auto_restart/healer.py
  ProbeResult in src/sase/agent/auto_restart/probe.py
  QuiescenceResult in src/sase/agent/auto_restart/quiescence.py
  SkipDecision in src/sase/agent/auto_restart/healer.py
  apply_skip_rules in src/sase/agent/auto_restart/healer.py
  auto_restart_recovery_is_in_flight in src/sase/core/agent_auto_restart_facade.py
  ledger_dir in src/sase/agent/auto_restart/ledger.py
  ledger_record_path in src/sase/agent/auto_restart/ledger.py
  python_wire_schema_version in src/sase/core/agent_auto_restart_facade.py
  resolve_pending_targets in src/sase/agent/auto_restart/healer.py
  write_recovery in src/sase/agent/auto_restart/healer.py
error: recipe `_lint-symvision` failed on line 441 with exit code 1
== test (scoped) (failed exit 1) ==
[counts: output_bytes=12239, output_lines=151, retained_bytes=12239]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
selected 80 of 5063 test files (rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost)
coverage contexts: baseline 96183d71b3ef (stale, 4162 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 850 items

tests/ace/tui/test_visual_fixture_host_paths.py .                        [  0%]
tests/test_agent_session_terminology.py ..                               [  0%]
tests/test_agent_stop_hook_config.py .                                   [  0%]
tests/test_agent_tribe_terminology.py ..                                 [  0%]
tests/test_check_sase_core_rs_bindings_tool.py ..........                [  1%]
tests/test_ci_bootstrap_sidecars_tool.py ..................              [  4%]
tests/test_commit_type_tag_contract.py ..                                [  4%]
tests/test_config_schema.py ...F............                             [  6%]
tests/test_config_schema_ace.py .......................                  [  8%]
tests/test_config_schema_beads.py ...................                    [ 11%]
tests/test_config_schema_extensions.py ................................. [ 14%]
.............                                                            [ 16%]
tests/test_config_schema_gate_turn.py .....                              [ 17%]
tests/test_config_schema_keymaps.py .................                    [ 19%]
tests/test_config_schema_runtime_limits.py .........................     [ 22%]
tests/test_core_finalizer_facade.py ........                             [ 22%]
tests/test_demo_media_postprocessor.py ............                      [ 24%]
tests/test_gemini_active_surface_guard.py ..                             [ 24%]
tests/test_github_actions_ci_master_gate.py ............................ [ 27%]
..                                                                       [ 28%]
tests/test_github_actions_ci_workflow.py ......................          [ 30%]
tests/test_github_actions_publish.py ....                                [ 31%]
tests/test_github_actions_setup_sase.py ........                         [ 32%]
tests/test_justfile_lint_check.py ........................               [ 34%]
tests/test_justfile_lint_lint.py ...............                         [ 36%]
tests/test_justfile_lint_setup.py ....................                   [ 39%]
tests/test_justfile_sase_core_dir.py .....................               [ 41%]
tests/test_macro_terminology.py ..........                               [ 42%]
tests/test_patch_stitch_terminology_audit.py ..................          [ 44%]
tests/test_probe_core_floor_tool.py ........                             [ 45%]
tests/test_project_display_presentation_audit.py .....                   [ 46%]
tests/test_prompt_prediction_replay_sources.py ......                    [ 47%]
tests/test_ratchet_core_revision_tool.py ...........                     [ 48%]
tests/test_ratchet_core_window_source_normalization.py ..........        [ 49%]
tests/test_ratchet_core_window_tool_core.py ...                          [ 49%]
tests/test_ratchet_core_window_tool_guardrails.py .......                [ 50%]
tests/test_ratchet_core_window_tool_modes.py .......                     [ 51%]
tests/test_ratchet_core_window_tool_reconciliation.py .......            [ 52%]
tests/test_require_tool_run.py .................                         [ 54%]
tests/test_ruff_config.py .

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the
original task. %macros_enabled:true
