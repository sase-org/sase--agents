%queue(weight=1)
%auto
#fork:sase-14n.3--plan
%model:muse-spark-1.3-contributor@xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
sase tool run check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-09-20T21:43:49.241530+00:00 |
| **Finished** | 2026-09-20T21:47:26.706764+00:00 |
| **Elapsed** | 3m 36s of a 1h 0m 0s budget |
| **Output** | 4 KiB · evidence refs: `file:monitor-diagnostic-manifest:a7y4x102vgq2`, `file:monitor-retained-log:a7y4x102vgq2`, `file:monitor-stage:lint-symvision-1762697-1789940845567234220-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show a7y4x102vgq2 --all-lines` |

**Why this was monitored:** Recorded just-check gate for phase bead sase-14n.3 test-side queue-weight settlement

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=3046, output_lines=32, retained_bytes=3046]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-11y(CapturedServiceEnvironment)" --epic-symbol "sase-11y(NativeInspection)" --epic-symbol "sase-11y(NativeServiceDefinition)" --epic-symbol "sase-11y(ServiceFieldProvenance)" --epic-symbol "sase-11y(ServicePlatformApplyResult)" --epic-symbol "sase-11y(build_native_definition)" --epic-symbol "sase-11y(clear_service_enablement)" --epic-symbol "sase-11y(compose_service_config)" --epic-symbol "sase-11y(inspect_native_service)" --epic-symbol "sase-11y(readiness_warnings)" --epic-symbol "sase-11y(resolve_service_enablement)" --epic-symbol "sase-11y(service_platform_supported)" 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  acquire_remote_clone_permit in src/sase/sdd/_store_clone_admission.py
  appears_as_agent in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  can_retry_without_reference in src/sase/sdd/_store_clone_remote.py
  capacity_agent_family in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  capacity_record_is_live in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  capacity_run_started_at in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  capacity_timestamp in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  clone_attempt_telemetry in src/sase/sdd/_store_clone_remote.py
  clone_attempt_timeout in src/sase/sdd/_store_clone_remote.py
  coherent in src/sase/completion/runtime_cache_generation.py
  configured_remote_clone_concurrency in src/sase/sdd/_store_clone_admission.py
  family_shell_id in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  family_shell_kind in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  family_shell_state in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  gateway_builtin_argv in src/sase/service/host_support.py
  matching_clone_reference in src/sase/sdd/_store_clone_remote.py
  observation in src/sase/service/host_reporting.py
  parsed_artifact_path in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  participates_in_runner_slots in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  remote_clone_args in src/sase/sdd/_store_clone_remote.py
  remote_clone_lock_dir in src/sase/sdd/_store_clone_admission.py
  sase_command in src/sase/service/host_support.py
  try_remote_clone_permit in src/sase/sdd/_store_clone_admission.py
  tui_hold_membership_tribes in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  workflow_dir_name in src/sase/ace/tui/models/_agent_runner_slot_capacity.py
  write_host_status in src/sase/service/host_reporting.py
error: recipe `_lint-symvision` failed on line 378 with exit code 1

```

<!--sase:budget-span:close:1-->

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-5e21eb005b2deab1.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "sase tool run check",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36",
    "member_agent_name": "sase-14n.3--mon",
    "monitor_id": "a7y4x102vgq2",
    "next_output": "auto",
    "parent_node_ids": [],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:8a4b70f60ae2486a2144f9cb9aeb04fe8b7e69172dac0f13668c25dfe42b2053",
    "starter_agent": "sase-14n.3--plan",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/20/20260920171609"
  },
  "recorded_at_epoch": 1789940630.4410775,
  "schema_version": 1
}
```


## Your next action

The sase tool run check gate for phase bead sase-14n.3 finished. 1) Inspect the monitor output: if check passed (all lint gates green, scoped tests green), proceed to step 2. If it failed, diagnose: a failure in tests/test_capacity_gate_to_admission.py or caused by this phase edit must be fixed in this turn; an unrelated red gate must NOT be fixed - record it via sase bead note sase-14n.3 'PROPOSED FOLLOW-UP: <one-line summary - detail>' instead. 2) Run sase bead epic-symbols sase-14n.3 (expect no entries; resolve or re-key any leftovers to a still-open bead). 3) Close ONLY the phase bead with sase bead close sase-14n.3 --note '<what you verified>'. Do NOT close parent epic sase-14n or any ancestor plan bead, and do NOT close task bead sase-13o (leave it for the land agent; mention its state in the close note). Do not create beads. Context: this phase settled the land-segment queue-weight contract on the test side - commit 28d1e8708 deliberately removed %q(w=2.0) from bd/land_epic and docs/xprompt.md now states bundled landers claim the default 1.0 unit, so tests/test_capacity_gate_to_admission.py was updated (land and phase queue_weight None non-explicit; heavy admission fixture raised to 4.0 so the weighted-capacity park still triggers; omitted-capacity test renamed to test_omitted_capacity_uses_default_weight_and_global_budget with a full-global-budget park case). Both nodes passed via direct pytest before this gate, and neighbors (test_bead_xprompt_tags, test_work_queue_capacity, test_work_rendering: 46 passed) were green.
%xprompts_enabled:true