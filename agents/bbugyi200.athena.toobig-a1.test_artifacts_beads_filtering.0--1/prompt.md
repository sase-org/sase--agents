%queue(weight=1)
#fork:toobig-a1.test_artifacts_beads_filtering.0--plan
%model:gpt-6-luna@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-18T06:46:38.257583+00:00 |
| **Finished** | 2026-11-18T06:57:29.691049Z |
| **Elapsed** | 9m 37s of a 1h 0m 0s budget |
| **Output** | 28 KiB · evidence refs: `file:monitor-diagnostic-manifest:xwvhweagjf3s`, `file:monitor-retained-log:xwvhweagjf3s`, `file:monitor-stage:test-scoped-2311411-1794985047876480088-8949acab` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show xwvhweagjf3s --all-lines` |
| **Tool run** | sase tool show 999625eff2d18fbc6455f3ab362b5f38 |

**Why this was monitored:** Verify the Artifacts Beads test split before host completion

## Failure triage

verdict: new_failures — 1 NEW; exit 1

NEW test (scoped): ERROR tests/ace/tui/test_artifacts_beads_filtering_queries.py::test_invalid_bead_filter_tokens_are_rejected — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show 999625eff2d18fbc6455f3ab362b5f38 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== test (scoped) (failed exit 1) ==
[counts: output_bytes=14276, output_lines=150, retained_bytes=14276]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
selected 93 of 5785 test files (rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost)
coverage contexts: baseline 96183d71b3ef (stale, 5293 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, platformdirs-4.13.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 1173 items

tests/ace/tui/test_artifacts_beads_filtering_queries.py ..E.........     [  1%]
tests/ace/tui/test_artifacts_beads_filtering_stranded.py ..              [  1%]
tests/ace/tui/test_artifacts_beads_filtering_ui.py ......                [  1%]
tests/ace/tui/test_visual_fixture_host_paths.py .                        [  1%]
tests/test_agent_session_terminology.py ..                               [  1%]
tests/test_agent_stop_hook_config.py .                                   [  2%]
tests/test_agent_tribe_terminology.py ..                                 [  2%]
tests/test_check_sase_core_rs_bindings_tool.py ..........                [  3%]
tests/test_ci_bootstrap_sidecars_tool.py ..................              [  4%]
tests/test_commit_type_tag_contract.py ..                                [  4%]
tests/test_config_schema.py ................                             [  6%]
tests/test_config_schema_ace.py .......................                  [  8%]
tests/test_config_schema_beads.py ...................                    [  9%]
tests/test_config_schema_extensions.py ................................. [ 12%]
.............                                                            [ 13%]
tests/test_config_schema_gate_turn.py .....                              [ 14%]
tests/test_config_schema_keymaps.py .................                    [ 15%]
tests/test_config_schema_runtime_limits.py .........................     [ 17%]
tests/test_core_finalizer_facade.py .........                            [ 18%]
tests/test_demo_media_postprocessor.py ............                      [ 19%]
tests/test_exercise_release.py .......................                   [ 21%]
tests/test_gemini_active_surface_guard.py ..                             [ 21%]
tests/test_github_actions_build_core.py .............                    [ 22%]
tests/test_github_actions_ci_master_gate.py ............................ [ 25%]
.......                                                                  [ 25%]
tests/test_github_actions_ci_workflow.py ............................... [ 28%]
                                                                         [ 28%]
tests/test_github_actions_install_smoke.py ...................           [ 29%]
tests/test_github_actions_publish.py .....                               [ 30%]
tests/test_github_actions_release.py ..............................      [ 32%]
tests/test_github_actions_release_steward.py ..........                  [ 33%]
tests/test_github_actions_setup_sase.py ............                     [ 34%]
tests/test_github_actions_testpypi_drill.py .........                    [ 35%]
tests/test_justfile_lint_check.py ...........................            [ 37%]
tests/test_justfile_lint_lint.py .................                       [ 39%]
tests/test_justfile_lint_setup.py .....................                  [ 41%]
tests/test_justfile_sase_core_dir.py ...............................     [ 43%]
tests/test_macro_terminology.py ..........                               [ 44%]
tests/test_patch_stitch_terminology_audit.py ..................          [ 46%]
tests/test_probe_core_floor_tool.py ........                             [ 46%]
tests/test_project_display_presentation_audit.py .........               [ 47%]
tests/test_prompt_prediction_replay_sources.py ......                    [ 48%]
tests/test_ratchet_core_pin_source_normalization.py ..........           [ 48%]
tests/test_ratchet_core_pin_tool_core.py .                               [ 49%]
tests/test_ratchet_core_pin_tool_guardrails.py .......                   [ 49%]
tests/test_ratchet_core_pin_tool_modes.py ........                       [ 50%]
tests/test_ratchet_core_pin_tool_reconciliation.py .......               [ 50%]
tests/test_ratchet_core_pin_tool_ref.py ....                             [ 51%]
tests/test_ratchet_core_revision_tool.py ...........                     [ 52%]
tests/test_release_candidate_inventory.py .............................. [ 54%]
.............                                                            [ 55%]
tests/test_release_candidate_publish.py ........                         [ 56%]
tests/test_release_candidate_published_core.py ....................      [ 58%]
tests/test_release_candidate_qualify_red.py ...                          [ 58%]
tests/test_release_candidate_rerun.py ...........                        [ 59%]
tests/test_release_candidate_seal.py ...........................         [ 61%]
tests/test_release_core.py ........................................      [ 65%]
tests/test_require_tool_run.py .................                         [ 66%]
tests/test_ruff_config.py .                                              [ 66%]
tests/test_run_pytest_command.py ................................        [ 69%]
tests/test_run_pytest_contention.py ..................................   [ 72%]
tests/test_run_pytest_health.py .....                                    [ 72%]
tests/test_run_pytest_main.py .............                              [ 73%]
tests/test_run_pytest_scoped.py ..............                           [ 75%]
tests/test_run_pytest_tmpdir.py ...................                      [ 76%]
tests/test_run_pytest_workers.py ...................                     [ 78%]
tests/test_rust_install_cleanup.py ..                                    [ 78%]
tests/test_sase_bead_tool.py ....                                        [ 78%]
tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py ..          [ 78%]
tests/test_sase_core_rs_bead_resolution_smoke_tool.py .                  [ 79%]
tests/test_sase_core_rs_feature_flag_state_smoke_tool.py ..              [ 79%]
tests/test_sase_core_rs_glossary_line_break_smoke_tool.py ..             [ 79%]
tests/test_sase_core_rs_plan_header_smoke_tool.py ..                     [ 79%]
tests/test_sase_core_rs_telemetry_smoke_tool.py .....                    [ 79%]
tests/test_sase_core_wheel_cache_tool.py ...........                     [ 80%]
tests/test_sase_migrate_statuses.py ...                                  [ 81%]
tests/test_sase_turn_terminology.py ...                                  [ 81%]
tests/test_sdd_canonical_layout.py ..                                    [ 81%]
tests/test_setup_required_plugins_tool.py ...................            [ 83%]
tests/test_suite_gate.py .................                               [ 84%]
tests/test_suite_gate_budget.py ...............                          [ 85%]
tests/test_suite_gate_lease.py ............                              [ 86%]
tests/test_suite_gate_reclaim.py ................                        [ 88%]
tests/test_timezone_display_guard.py .                       

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true