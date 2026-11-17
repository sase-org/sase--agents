# Chat History - ace-run (sase-1t2.11.1.6--mon)

- **TIMESTAMP:** 2026-11-17 01:32:54 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1t2.11.1.6--mon

## Prompt

sase monitor start --command 'env SASE_PYTEST_WORKERS=1 just test tests/fakey/test_agent_hijack_canary.py tests/test_agent_hijack_facts.py' --reason 'Run monitor hijack recovery canaries'

## Response

sase tool run 9df0fc68110c3e031db21550c4083ca9
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test                     │
└───────────────────────────────────────────────────────┘

---------- Running pytest (parallel, no coverage)... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [15 items]

....FF.........                                                          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_________________ test_monitor_hijack_continue_same_workspace __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/.venv/bin/python

harness = <tests.fakey._agent_hijack_canary_harness.CanaryHarness object at 0x7f81b33d2b10>
original_name = 'canary--0', monitor_name = 'canary--mon'

    def _wait_recovery_successor(
        harness: CanaryHarness,
        *,
        original_name: str,
        monitor_name: str,
    ) -> tuple[Path, dict[str, Any]]:
        selected: list[tuple[Path, dict[str, Any]]] = []
    
        def settled() -> bool:
            selected.clear()
            for artifacts_dir in iter_agent_artifact_dirs(PROJECT, newest_first=False):
                meta_path = artifacts_dir / "agent_meta.json"
                if not meta_path.is_file():
                    continue
                try:
                    meta = read_json(meta_path)
                except (OSError, json.JSONDecodeError):
                    continue
                if (
                    meta.get("name") in {original_name, monitor_name}
                    or meta.get("workspace_num") != WORKSPACE_NUM
                ):
                    continue
                done_path = artifacts_dir / "done.json"
                if not done_path.is_file():
                    continue
                done = read_json(done_path)
                if done.get("outcome") in {"success", "succeeded", "completed"}:
                    selected.append((artifacts_dir, meta))
            return len(selected) >= 1
    
        try:
>           _wait_for_condition(
                settled,
                LOAD_TOLERANT_TIMEOUT,
                "a successful same-session recovery successor",
            )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/fakey/_agent_hijack_monitor_canary.py:371: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function _wait_recovery_successor.<locals>.settled at 0x7f81a8b32cf0>
timeout = 60.0, description = 'a successful same-session recovery successor'

    def _wait_for_condition(
        predicate: Callable[[], bool], timeout: float, description: str
    ) -> None:
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            if predicate():
                return
            time.sleep(min(0.01, max(0.0, deadline - time.monotonic())))
>       raise TimeoutError(f"timed out waiting for {description}")
E       TimeoutError: timed out waiting for a successful same-session recovery successor

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/fakey/harness.py:570: TimeoutError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f81b3196eb0>

    def test_monitor_hijack_continue_same_workspace(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        harness = CanaryHarness(tmp_path, monkeypatch)
        starter_barrier = harness.barrier("monitor-continue-starter")
        started = tmp_path / "barriers" / "monitor-continue-command.started"
        runs = tmp_path / "barriers" / "monitor-continue-command.pids"
        release = tmp_path / "barriers" / "monitor-continue-command.release"
        launch = None
        try:
            launch = harness.spawn(
                _prompt(
                    directive="%id:canary",
                    body="Hold while the monitor is staged for hijack.",
                    barrier=starter_barrier,
                ),
                extra_env={"SASE_AGENT_PLANNED_NAME": SESSION},
            )
            harness.wait_meta(launch)
            harness.wait_barrier(launch, starter_barrier)
            monitor_id, monitor_dir, staged_id = _stage_monitor(
                harness,
                launch,
                command=_sleep_command(started, runs, release),
            )
            staged = read_staged_handoff(launch.artifacts_dir)
            assert staged is not None and staged.get("staged_id") == staged_id
    
            starter_barrier.open()
            starter_done = harness.wait_done(launch)
            assert starter_done.get("outcome") in {"success", "succeeded", "completed"}, (
                starter_done
            )
            meta = _wait_monitor_running(
                monitor_id=monitor_id,
                artifacts_dir=monitor_dir,
                started=started,
                runs=runs,
            )
            assert meta.get("workspace_num") == WORKSPACE_NUM, meta
            assert (
                Path(str(meta.get("workspace_dir"))).resolve()
                == Path(str(harness.workspace)).resolve()
            ), meta
            pids = _monitor_pid_list(runs)
            assert len(pids) == 1 and _pid_alive(pids[0]), pids
    
            _dirty_workspace(harness.workspace)
            _host, monitor_row, payload = _cached_tui_hijack(
                harness,
                monitor_id=monitor_id,
                artifacts_dir=monitor_dir,
            )
            assert payload.get("status") in {"hijacked", "stopped", "held"}, payload
            done, record = _wait_hijacked(
                harness,
                monitor_id=monitor_id,
                artifacts_dir=monitor_dir,
                command_pids=pids,
            )
            assert record["suppressed_followup"]["ref"]
            members = _session_members(harness)
            assert len(members) == 2, [
                (str(path), row.get("name")) for path, row in members
            ]
            assert done.get("monitor_followup_outcome") == "hijacked"
    
            code = _recover(harness, monitor_row.agent_name, "continue")
            assert code == 0, (
                f"recover continue failed: {harness.last_recover!r}\n{harness.diagnostics(launch)}"
            )
>           successor_dir, _successor_meta = _wait_recovery_successor(
                harness,
                original_name=str(harness.wait_meta(launch)["name"]),
                monitor_name=monitor_row.agent_name,
            )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/fakey/_agent_hijack_monitor_canary.py:490: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

harness = <tests.fakey._agent_hijack_canary_harness.CanaryHarness object at 0x7f81b33d2b10>
original_name = 'canary--0', monitor_name = 'canary--mon'

    def _wait_recovery_successor(
        harness: CanaryHarness,
        *,
        original_name: str,
        monitor_name: str,
    ) -> tuple[Path, dict[str, Any]]:
        selected: list[tuple[Path, dict[str, Any]]] = []
    
        def settled() -> bool:
            selected.clear()
            for artifacts_dir in iter_agent_artifact_dirs(PROJECT, newest_first=False):
                meta_path = artifacts_dir / "agent_meta.json"
                if not meta_path.is_file():
                    continue
                try:
                    meta = read_json(meta_path)
                except (OSError, json.JSONDecodeError):
                    continue
                if (
                    meta.get("name") in {original_name, monitor_name}
                    or meta.get("workspace_num") != WORKSPACE_NUM
                ):
                    continue
                done_path = artifacts_dir / "done.json"
                if not done_path.is_file():
                    continue
                done = read_json(done_path)
                if done.get("outcome") in {"success", "succeeded", "completed"}:
                    selected.append((artifacts_dir, meta))
            return len(selected) >= 1
    
        try:
            _wait_for_condition(
                settled,
                LOAD_TOLERANT_TIMEOUT,
                "a successful same-session recovery successor",
            )
        except TimeoutError as exc:
>           raise AssertionError(
                f"{exc}\nrecover={harness.last_recover!r}\n"
                f"session members={[(str(path), meta.get('name'), meta.get('workspace_num')) for path, meta in _session_members(harness)]!r}\n"
                f"{harness.dump_all_artifacts()}"
            ) from exc
E           AssertionError: timed out waiting for a successful same-session recovery successor
E           recover=(0, '{\n  "action": "continue",\n  "actions": null,\n  "default_action": null,\n  "error": null,\n  "header": null,\n  "hijack_id": "hijack-canary--mon-5c887f00bf90",\n  "message": "Recovery instruct launched canary--1 in the held workspace",\n  "mode": "recovery",\n  "model_changed": false,\n  "name": "canary--mon",\n  "ok": true,\n  "plan": null,\n  "prompt_supplied": null,\n  "result": {\n    "admission_request_id": "hijack-recover-hijack-canary--mon-5c887f00bf90-bfd78ac5cffa",\n    "detail": {\n      "context_mode": "monitor",\n      "launch_stage": "confirmed"\n    },\n    "kind": "launched",\n    "launch_identity": "bfd78ac5cffa4c8180491a12240c7927",\n    "successor": "canary--1"\n  },\n  "revision": 5,\n  "schema_version": 1,\n  "state": null,\n  "target": "fakey/fakey-large"\n}\n', '')
E           session members=[('/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013127', 'canary--0', 3), ('/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131', 'canary--mon', 3), ('/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013136', 'canary--1', 3)]
E           === all artifact dirs ===
E           /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013127: ['.sase_handoff.lock', '.sase_handoff_adopted.json', '.sase_handoff_recovery.json', '.sase_handoff_response.json', '.sase_handoff_staged.json', 'agent_meta.json', 'continuation', 'continuation_prompt_measurements.jsonl', 'done.json', 'final_context.json', 'final_context_host.json', 'final_declaration.lock', 'finalizer_baseline.json', 'finalizer_baseline.json.lock', 'finalizer_plan.authority.json', 'finalizer_plan.json', 'finalizer_plan.lock', 'finalizer_result.json', 'finalizer_result.lock', 'finalizers', 'instructions', 'live_reply.md', 'live_reply_timestamps.jsonl', 'prompt_step_main.json', 'raw_prompt.md', 'sase.md', 'submitted_prompt.md', 'workflow-tmp_261117_013130-main_prompt.md', 'workflow_state.json']
E           -- agent_meta.json --
E           n/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013127/continuation/prepared_prompt.json",
E             "continuation_materialized_prompt_ref": "local:continuation/text/a0d01b63b97179e8dabb4ccd60715c85a7e8e280d8f3019f0014229783b0c471.txt",
E             "finalizers": {
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "selected": [
E                 "commit"
E               ],
E               "raw_operations": []
E             },
E             "finalizer_status": {
E               "schema_version": 1,
E               "phase": "settled",
E               "reason": null,
E               "status": "success",
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "run_id": "347dc5ee403a474585e5d9c877457d9e",
E               "started_at": 1794897092.2601883,
E               "updated_at": 1794897092.8830576,
E               "runner": {
E                 "pid": 1156561,
E                 "identity": "39d14458-b9c5-4e7b-bfc2-10aeb016557d:14135794"
E               },
E               "instances": [
E                 {
E                   "id": "commit",
E                   "status": "success",
E                   "attempt": 0,
E                   "max_attempts": 2,
E                   "op": null,
E                   "step": null,
E                   "started_at": 1794897092.7457316,
E                   "finished_at": 1794897092.7648275,
E                   "headline": null,
E                   "warnings": 0,
E                   "reason": null
E                 }
E               ],
E               "instance_count": 1
E             },
E             "exec_llm_provider": "fakey",
E             "instructions": {
E               "schema_version": 1,
E               "count": 1,
E               "latest": {
E                 "seq": 0,
E                 "provider": "fakey",
E                 "purpose": "ordinary",
E                 "sha256": "d772cdc2c1e5dec4d0f29dc4ef5d9dfcd7b12b8397faeee3d79f323c5c800b78",
E                 "common_digest": "6218f8d5ea5809c3b15178e40b84ad8779c9c6dd2e73a3df092f4fd1408dfef7",
E                 "manifest": "instructions/00-fakey.json",
E                 "delivery_status": "inherits_native"
E               }
E             },
E             "workflow_name": "canary",
E             "role_suffix": "--0",
E             "agent_session": "canary",
E             "agent_session_role": "root",
E             "chat_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013127.md",
E             "monitor_id": "vmhsxrvgxce8",
E             "monitor_member_agent_name": "canary--mon",
E             "continuation_node_id": "agent-delta:20261117013127:9d1a246d043e6a83",
E             "continuation_manifest_ref": "local:continuation/manifest.json",
E             "continuation_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013127/continuation/manifest.json",
E             "continuation_agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013127:9d1a246d043e6a83.json",
E             "continuation_node_ref": "local:continuation/nodes/agent-delta:20261117013127:9d1a246d043e6a83.json",
E             "continuation_status": "completed",
E             "continuation_portable_content_ref": "file:explicit:cb382b854dba500c81167d8d",
E             "continuation_node_portable_ref": "file:explicit:c49bac0d32ab66f50f33b460",
E             "handoff_protocol": "staged",
E             "stopped_at": "2026-11-17T06:31:34.085252+00:00"
E           }
E           -- done.json --
E           {
E             "artifacts_timestamp": "20261117013127",
E             "changespec_name": "hijack-canary",
E             "cl_name": "hijack-canary",
E             "continuation": {
E               "agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013127:9d1a246d043e6a83.json",
E               "manifest_ref": "local:continuation/manifest.json",
E               "node_id": "agent-delta:20261117013127:9d1a246d043e6a83",
E               "node_ref": "local:continuation/nodes/agent-delta:20261117013127:9d1a246d043e6a83.json",
E               "workspace_ref": "local:continuation/workspace_facts.json"
E             },
E             "default_artifacts_persisted": true,
E             "diff_path": null,
E             "exec_llm_provider": "fakey",
E             "finished_at": 1794897094.055601,
E             "image_paths": [],
E             "llm_provider": "fakey",
E             "markdown_pdf_paths": [],
E             "model": "fakey-large",
E             "name": "canary--0",
E             "outcome": "completed",
E             "output_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/workflows/202611/hijack-canary_ace-run-261117_013127.txt",
E             "patch_name": "hijack-canary",
E             "plan_path": null,
E             "project_file": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/hijack-canary.sase",
E             "response_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013127.md",
E             "step_output": {
E               "_raw": "canary recovered"
E             },
E             "timestamp": "261117_013127",
E             "vcs_provider": "Git (bare)",
E             "video_paths": [],
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-p8g2tpg1/.local/state/sase/workspaces/primary-47754106/primary_3",
E             "workspace_num": 3
E           }
E           /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131: ['.agent_directive_persistence.lock', '.live_reply.md.lock', '.proc_settled.json', '.sase_user_kill_pending', 'agent_meta.json', 'continuation', 'diagnostics', 'done.json', 'finalizer_baseline.json', 'finalizer_baseline.json.lock', 'hijack_recovery', 'live_reply.md', 'monitor_start_timing.json', 'staged_monitor_launch.json', 'workflow_state.json']
E           -- agent_meta.json --
E           -home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/diagnostics/diagnostic_manifest.json",
E             "monitor_diagnostic_manifest_ref": "file:monitor-diagnostic-manifest:vmhsxrvgxce8",
E             "monitor_retained_log_metadata_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/diagnostics/retained_log_metadata.json",
E             "monitor_retained_log_ref": "file:monitor-retained-log:vmhsxrvgxce8",
E             "continuation_monitor_result_id": "result:vmhsxrvgxce8:f46e73b3ee8f82fe",
E             "continuation_monitor_result_ref": "local:continuation/records/monitor_result/result:vmhsxrvgxce8:f46e73b3ee8f82fe.json",
E             "continuation_monitor_result_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/continuation/records/monitor_result/result:vmhsxrvgxce8:f46e73b3ee8f82fe.json",
E             "continuation_monitor_result_sha256": "411144d0a69684d19dff4c124ede1f92e8656d3e6532e413d9ebd1e732040d7c",
E             "continuation_monitor_result_node_id": "monitor-result:vmhsxrvgxce8:f46e73b3ee8f82fe",
E             "continuation_monitor_result_node_ref": "local:continuation/nodes/monitor-result:vmhsxrvgxce8:f46e73b3ee8f82fe.json",
E             "continuation_monitor_result_manifest_ref": "local:continuation/monitor_result_manifest.json",
E             "continuation_monitor_result_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/continuation/monitor_result_manifest.json",
E             "continuation_node_id": "monitor-result:vmhsxrvgxce8:f46e73b3ee8f82fe",
E             "continuation_node_ref": "local:continuation/nodes/monitor-result:vmhsxrvgxce8:f46e73b3ee8f82fe.json",
E             "continuation_manifest_ref": "local:continuation/monitor_result_manifest.json",
E             "continuation_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/continuation/monitor_result_manifest.json",
E             "continuation_monitor_result_portable_ref": "file:explicit:a03e11c194f73aaa31d66f3c",
E             "continuation_node_portable_ref": "file:explicit:e3dad5f13322854388b7be10",
E             "continuation_parent_portable_refs": {
E               "agent-delta:20261117013127:9d1a246d043e6a83": "file:explicit:c7d60cbc78dc38cef645c4e4"
E             },
E             "stopped_at": "2026-11-17T06:31:34.452754Z",
E             "monitor_hijack_id": "hijack-canary--mon-5c887f00bf90",
E             "monitor_hijack_recovery_ref": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/hijack_recovery/hijack-canary--mon-5c887f00bf90.json",
E             "monitor_hijack_boundary_outcome": "stopped",
E             "monitor_hijack_state": "held",
E             "monitor_followup_outcome": "hijacked",
E             "monitor_followup_error": null
E           }
E           -- done.json --
E           facts_timestamp":"20261117013131","boundary_outcome":"stopped","changespec_name":"hijack-canary","cl_name":"hijack-canary","continuation_monitor_result_id":"result:vmhsxrvgxce8:f46e73b3ee8f82fe","continuation_monitor_result_manifest_path":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/continuation/monitor_result_manifest.json","continuation_monitor_result_manifest_ref":"local:continuation/monitor_result_manifest.json","continuation_monitor_result_node_ref":"local:continuation/nodes/monitor-result:vmhsxrvgxce8:f46e73b3ee8f82fe.json","continuation_monitor_result_path":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/continuation/records/monitor_result/result:vmhsxrvgxce8:f46e73b3ee8f82fe.json","continuation_monitor_result_ref":"local:continuation/records/monitor_result/result:vmhsxrvgxce8:f46e73b3ee8f82fe.json","continuation_monitor_result_sha256":"411144d0a69684d19dff4c124ede1f92e8656d3e6532e413d9ebd1e732040d7c","finished_at":1794897095.4997945,"monitor_diagnostic_manifest_path":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/diagnostics/diagnostic_manifest.json","monitor_diagnostic_manifest_ref":"file:monitor-diagnostic-manifest:vmhsxrvgxce8","monitor_elapsed_seconds":null,"monitor_exit_code":-15,"monitor_followup_outcome":"hijacked","monitor_hijack_id":"hijack-canary--mon-5c887f00bf90","monitor_hijack_recovery_ref":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/hijack_recovery/hijack-canary--mon-5c887f00bf90.json","monitor_id":"vmhsxrvgxce8","monitor_retained_log_metadata_path":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013131/diagnostics/retained_log_metadata.json","monitor_retained_log_ref":"file:monitor-retained-log:vmhsxrvgxce8","monitor_state":"stopped","monitor_timeout_kind":null,"monitor_timeout_message":null,"name":"canary--mon","outcome":"hijacked","patch_name":"hijack-canary","project_file":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/hijack-canary.sase","recovery":{"action":"instruct","hijack_id":"hijack-canary--mon-5c887f00bf90","kind":"hijack","launch_identity":"bfd78ac5cffa4c8180491a12240c7927","model_changed":false,"state":"resolved","successor":"canary--1"},"status_bucket":"Stopped","status_label":"Stopped","workspace_dir":"/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-p8g2tpg1/.local/state/sase/workspaces/primary-47754106/primary_3","workspace_num":3}
E           
E           /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013136: ['agent_meta.json', 'continuation', 'continuation_prompt_measurements.jsonl', 'done.json', 'embedded_workflows.json', 'error_report.md', 'failed_close_recovery_outcome.json', 'failed_close_recovery_request.json', 'final_context.json', 'final_context_host.json', 'final_declaration.lock', 'final_declaration_recovery_evidence.md', 'final_declaration_recovery_prompt.md', 'final_declaration_recovery_response.md', 'finalizer_baseline.json', 'finalizer_baseline.json.lock', 'finalizer_plan.authority.json', 'finalizer_plan.json', 'finalizer_plan.lock', 'finalizer_result.json', 'finalizer_result.lock', 'finalizers', 'hijack_recovery_ack.json', 'instructions', 'live_reply.md', 'live_reply_timestamps.jsonl', 'macros.json', 'prompt_step_main.json', 'raw_prompt.md', 'sase.md', 'submitted_prompt.md', 'workflow-tmp_261117_013141-main_prompt.md', 'workflow_state.json']
E           -- agent_meta.json --
E           nitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013136/continuation/workspace_facts.json",
E             "continuation_prepared_prompt_ref": "local:continuation/prepared_prompt.json",
E             "continuation_prepared_prompt_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013136/continuation/prepared_prompt.json",
E             "continuation_materialized_prompt_ref": "local:continuation/text/734cdd7563112917fdc6f630a267a8e9bd995436fe78e87778f8e2a0dc594b7a.txt",
E             "finalizers": {
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "selected": [
E                 "commit"
E               ],
E               "raw_operations": []
E             },
E             "finalizer_status": {
E               "schema_version": 1,
E               "phase": "settled",
E               "reason": null,
E               "status": "failed",
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "run_id": "123df6a747e24836bffb0841a33cd261",
E               "started_at": 1794897102.5865734,
E               "updated_at": 1794897103.401021,
E               "runner": {
E                 "pid": 1159178,
E                 "identity": "39d14458-b9c5-4e7b-bfc2-10aeb016557d:14136609"
E               },
E               "instances": [
E                 {
E                   "id": "commit",
E                   "status": "failed",
E                   "attempt": 1,
E                   "max_attempts": 1,
E                   "op": null,
E                   "step": null,
E                   "started_at": 1794897103.3143592,
E                   "finished_at": 1794897103.3778791,
E                   "headline": null,
E                   "warnings": 0,
E                   "reason": "RuntimeError: Finalizer declaration recovery failed: no fresh context was published for the recovery turn"
E                 }
E               ],
E               "instance_count": 1
E             },
E             "exec_llm_provider": "fakey",
E             "instructions": {
E               "schema_version": 1,
E               "count": 2,
E               "latest": {
E                 "seq": 1,
E                 "provider": "fakey",
E                 "purpose": "declaration_recovery",
E                 "sha256": "d772cdc2c1e5dec4d0f29dc4ef5d9dfcd7b12b8397faeee3d79f323c5c800b78",
E                 "common_digest": "6218f8d5ea5809c3b15178e40b84ad8779c9c6dd2e73a3df092f4fd1408dfef7",
E                 "manifest": "instructions/01-fakey.json",
E                 "delivery_status": "inherits_native"
E               }
E             },
E             "continuation_node_id": "agent-delta:20261117013136:036a84c51dffaf33",
E             "continuation_manifest_ref": "local:continuation/manifest.json",
E             "continuation_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_continue_s0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013136/continuation/manifest.json",
E             "continuation_agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013136:036a84c51dffaf33.json",
E             "continuation_node_ref": "local:continuation/nodes/agent-delta:20261117013136:036a84c51dffaf33.json",
E             "continuation_status": "failed",
E             "continuation_portable_content_ref": "file:explicit:752043dd0731ce2a5e40e0f7",
E             "continuation_node_portable_ref": "file:explicit:50ff4b928aba3ba4d44a8ed4",
E             "stopped_at": "2026-11-17T06:31:43.942609+00:00"
E           }
E           -- done.json --
E           sase/sase_27/src/sase/macro/workflow_executor.py\", line 352, in execute\n    success = self._execute_prompt_step(step, step_state)\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_executor_steps_prompt.py\", line 220, in _execute_prompt_step\n    response = invoke_agent(\n        expanded_prompt,\n        skip_preprocessing=True,\n        **invocation_kwargs,\n    )\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/llm_provider/_invoke.py\", line 460, in invoke_agent\n    raise LLMInvocationError(error_content) from e\nsase.llm_provider.types.LLMInvocationError: Error: Finalizer declaration recovery failed: no fresh context was published for the recovery turn\n\nThe above exception was the direct cause of the following exception:\n\nTraceback (most recent call last):\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner.py\", line 366, in main\n    _run_agent(state)\n    ~~~~~~~~~~^^^^^^^\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner.py\", line 288, in _run_agent\n    _admit_and_launch(state, bootstrap)\n    ~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner.py\", line 257, in _admit_and_launch\n    launch_agent_run(state, bootstrap)\n    ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner_launch.py\", line 401, in launch_agent_run\n    exec_result = run_execution_loop(\n        _build_exec_context(\n    ...<7 lines>...\n        state.prompt,\n    )\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_exec.py\", line 272, in run_execution_loop\n    return _run_execution_loop_bound(ctx, prompt)\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_exec.py\", line 369, in _run_execution_loop_bound\n    result = execute_workflow(\n        anon_workflow.name,\n    ...<8 lines>...\n        continuation_segments=state.continuation_segments,\n    )\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_runner.py\", line 596, in execute_workflow\n    execution = executor.execute()\n  File \"/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_executor.py\", line 425, in execute\n    raise WorkflowExecutionError(\n        f\"Step '{step.name}' failed: {e}\"\n    ) from e\nsase.macro.workflow_models.WorkflowExecutionError: Step 'main' failed: Error: Finalizer declaration recovery failed: no fresh context was published for the recovery turn\n",
E             "vcs_provider": "Git (bare)",
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-p8g2tpg1/.local/state/sase/workspaces/primary-47754106/primary_3",
E             "workspace_num": 3
E           }
E           -- hijack_recovery_ack.json --
E           {
E             "baseline_inherited": true,
E             "baselines_verified": true,
E             "bead": null,
E             "bead_verified": true,
E             "concrete_target": "fakey/fakey-large",
E             "effort": null,
E             "goal": null,
E             "goal_verified": true,
E             "inventory_verified": true,
E             "launch_identity": "bfd78ac5cffa4c8180491a12240c7927",
E             "lineage": {
E               "from_rung": "fakey/fakey-large",
E               "hijack_id": "hijack-canary--mon-5c887f00bf90",
E               "predecessor": "canary--mon",
E               "to_rung": "fakey/fakey-large"
E             },
E             "model": "fakey-large",
E             "permission": {
E               "digest": "c901a80c96319b4ff3a6c0b8df9b9fc60e67b4d4175a32e60153ec91c0ef8c07",
E               "inherited_from": "canary--mon",
E               "overrides": {},
E               "policy": {
E                 "gates": {
E                   "epic": "ask",
E                   "plan": "ask",
E                   "question": "ask"
E                 },
E                 "on_ask": "park"
E               },
E               "profile": "manual",
E               "revision": 1,
E               "schema_version": 1,
E               "selection": "manual",
E               "source": "inherited",
E               "updated_at": "2026-11-17T06:31:37Z",
E               "updated_by": {
E                 "kind": "host",
E                 "principal": "",
E                 "surface": ""
E               }
E             },
E             "process_token": "39d14458-b9c5-4e7b-bfc2-10aeb016557d:14136609",
E             "project": "hijack-canary",
E             "provider": "fakey",
E             "schema_version": 1,
E             "scope_verified": true,
E             "successor_name": "canary--1",
E             "transferred_repos": 0,
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-p8g2tpg1/.local/state/sase/workspaces/primary-47754106/primary_3",
E             "workspace_num": 3
E           }
E           
E           -- error_report.md --
E           following exception:
E           
E           Traceback (most recent call last):
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_executor.py", line 352, in execute
E               success = self._execute_prompt_step(step, step_state)
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_executor_steps_prompt.py", line 220, in _execute_prompt_step
E               response = invoke_agent(
E                   expanded_prompt,
E                   skip_preprocessing=True,
E                   **invocation_kwargs,
E               )
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/llm_provider/_invoke.py", line 460, in invoke_agent
E               raise LLMInvocationError(error_content) from e
E           sase.llm_provider.types.LLMInvocationError: Error: Finalizer declaration recovery failed: no fresh context was published for the recovery turn
E           
E           The above exception was the direct cause of the following exception:
E           
E           Traceback (most recent call last):
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner.py", line 366, in main
E               _run_agent(state)
E               ~~~~~~~~~~^^^^^^^
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner.py", line 288, in _run_agent
E               _admit_and_launch(state, bootstrap)
E               ~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner.py", line 257, in _admit_and_launch
E               launch_agent_run(state, bootstrap)
E               ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_runner_launch.py", line 401, in launch_agent_run
E               exec_result = run_execution_loop(
E                   _build_exec_context(
E               ...<7 lines>...
E                   state.prompt,
E               )
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_exec.py", line 272, in run_execution_loop
E               return _run_execution_loop_bound(ctx, prompt)
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/axe/run_agent_exec.py", line 369, in _run_execution_loop_bound
E               result = execute_workflow(
E                   anon_workflow.name,
E               ...<8 lines>...
E                   continuation_segments=state.continuation_segments,
E               )
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_runner.py", line 596, in execute_workflow
E               execution = executor.execute()
E             File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/macro/workflow_executor.py", line 425, in execute
E               raise WorkflowExecutionError(
E                   f"Step '{step.name}' failed: {e}"
E               ) from e
E           sase.macro.workflow_models.WorkflowExecutionError: Step 'main' failed: Error: Finalizer declaration recovery failed: no fresh context was published for the recovery turn
E           ```
E           
E           ## Workspace recovery
E           
E           Workspace #3 is held for this failed run. Inspect or commit its changes, then dismiss the failed agent in `sase tui` to release it.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/fakey/_agent_hijack_monitor_canary.py:377: AssertionError
----------------------------- Captured stdout call -----------------------------
Hijack hijack-canary--mon-5c887f00bf90 already holds canary--mon; nothing else was stopped
___________________ test_monitor_hijack_rerun_same_workspace ___________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f81a8f83450>

    def test_monitor_hijack_rerun_same_workspace(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        harness = CanaryHarness(tmp_path, monkeypatch)
        starter_barrier = harness.barrier("monitor-rerun-starter")
        started = tmp_path / "barriers" / "monitor-rerun-command.started"
        runs = tmp_path / "barriers" / "monitor-rerun-command.pids"
        release = tmp_path / "barriers" / "monitor-rerun-command.release"
        launch = None
        try:
            launch = harness.spawn(
                _prompt(
                    directive="%id:canary",
                    body="Hold while the monitor is staged for rerun.",
                    barrier=starter_barrier,
                ),
                extra_env={"SASE_AGENT_PLANNED_NAME": SESSION},
            )
            harness.wait_meta(launch)
            harness.wait_barrier(launch, starter_barrier)
            original_id, original_dir, _staged_id = _stage_monitor(
                harness,
                launch,
                command=_sleep_command(started, runs, release),
            )
            starter_barrier.open()
            starter_done = harness.wait_done(launch)
            assert starter_done.get("outcome") in {"success", "succeeded", "completed"}, (
                starter_done
            )
            _wait_monitor_running(
                monitor_id=original_id,
                artifacts_dir=original_dir,
                started=started,
                runs=runs,
            )
            original_pids = _monitor_pid_list(runs)
            assert len(original_pids) == 1 and _pid_alive(original_pids[0]), original_pids
    
            _dirty_workspace(harness.workspace)
            _host, original_row, _payload = _cached_tui_hijack(
                harness,
                monitor_id=original_id,
                artifacts_dir=original_dir,
            )
            _done, record = _wait_hijacked(
                harness,
                monitor_id=original_id,
                artifacts_dir=original_dir,
                command_pids=original_pids,
            )
>           assert _recover(harness, original_row.agent_name, "rerun") == 0, (
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                f"recover rerun failed: {harness.last_recover!r}\n{harness.diagnostics(launch)}"
            )
E           AssertionError: recover rerun failed: (2, '{\n  "action": "rerun",\n  "actions": null,\n  "default_action": null,\n  "error": {\n    "code": "ledger_rejected",\n    "message": "The recovery reservation was rejected: agent hijack transition requires a supported resolution action"\n  },\n  "header": null,\n  "hijack_id": "hijack-canary--mon-d1f1350ca311",\n  "message": "The recovery reservation was rejected: agent hijack transition requires a supported resolution action",\n  "mode": "recovery",\n  "model_changed": null,\n  "name": "canary--mon",\n  "ok": false,\n  "plan": null,\n  "prompt_supplied": null,\n  "result": {\n    "admission_request_id": null,\n    "detail": {\n      "code": "ledger_rejected"\n    },\n    "kind": "refused",\n    "launch_identity": null,\n    "successor": null\n  },\n  "revision": 2,\n  "schema_version": 1,\n  "state": null,\n  "target": null\n}\n', '')
E           pid=1176068 alive=True
E           output:
E           Starting agent run
E           Patch: hijack-canary
E           Workspace: /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-h639gipx/.local/state/sase/workspaces/primary-5230f3a5/primary_3
E           Workflow: ace(run)-261117_013238
E           
E           === Prompt ===
E           %id:canary
E           %model:fakey-large
E           Hold while the monitor is staged for rerun.
E           
E           ```fakey
E           steps:
E           - signal: /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/barriers/monitor-rerun-starter.started
E           - wait_for:
E               path: /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/barriers/monitor-rerun-starter.release
E               timeout: 60.0
E           reply: canary recovered
E           ```
E           
E           ==============
E           
E           Ignoring stale SASE_AGENT_PLANNED_NAME='canary' because its registry reservation does not belong to artifacts directory /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238
E           ╭────── 🤖 Workflow-Tmp_261117_013241-Main [Fakey-Large] Agent - Prompt ───────╮
E           │                                                                              │
E           │  Hold while the monitor is staged for rerun.                                 │
E           │                                                                              │
E           │  ```fakey                                                                    │
E           │  steps:                                                                      │
E           │  - signal:                                                                   │
E           │  /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hij  │
E           │  ack_rerun_same0/barriers/monitor-rerun-starter.started                      │
E           │  - wait_for:                                                                 │
E           │      path:                                                                   │
E           │  /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hij  │
E           │  ack_rerun_same0/barriers/monitor-rerun-starter.release                      │
E           │      timeout: 60.0                                                           │
E           │  reply: canary recovered                                                     │
E           │  ```                                                                         │
E           │                                                                              │
E           │                                                                              │
E           ╰──────────────────────────────────────────────────────────────────────────────╯
E           canary recovered
E           
E           ✅ Waiting for Fakey completed in 00:00/home/bryan/bin/bam: line 3: /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-h639gipx/lib/bugyi.sh: No such file or directory
E           
E           Chat history saved to: /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013238.md
E           Preparing PDFs from Markdown... found 0, cap 10
E           [PDF] preparing Markdown PDFs (0 source(s), cap 10)
E           [PDF] complete: 0 generated, 0 skipped
E           [artifacts] default capture: stored=0 referenced=0 skipped=0 declared=0 cap_fired=false
E           Done marker written to: /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238/done.json
E           
E           Agent completed with status: SUCCESS
E           Duration: 4s
E           {"context": "runner-exit", "event": "launch_scratch_cleanup", "reason": "shell-handoff:monitored", "removed": 0, "removed_bytes": 0, "scratch_key": "hijack-canary-ws3-261117_013238", "skipped": 0, "status": "skipped"}
E           
E           meta:
E           {
E             "pid": 1176068,
E             "process_identity": "39d14458-b9c5-4e7b-bfc2-10aeb016557d:14142875",
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-h639gipx/.local/state/sase/workspaces/primary-5230f3a5/primary_3",
E             "workspace_num": 3,
E             "output_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/workflows/202611/hijack-canary_ace-run-261117_013238.txt",
E             "name": "canary--0",
E             "queue_weight": 1.0,
E             "queue_weight_explicit": false,
E             "model": "fakey-large",
E             "llm_provider": "fakey",
E             "model_alias_origin": "none",
E             "vcs_provider": "Git (bare)",
E             "autonomy": {
E               "schema_version": 1,
E               "profile": "manual",
E               "selection": "manual",
E               "policy": {
E                 "gates": {
E                   "plan": "ask",
E                   "epic": "ask",
E                   "question": "ask"
E                 },
E                 "on_ask": "park"
E               },
E               "overrides": {},
E               "source": "prompt",
E               "revision": 1,
E               "digest": "c901a80c96319b4ff3a6c0b8df9b9fc60e67b4d4175a32e60153ec91c0ef8c07",
E               "updated_at": "2026-11-17T06:32:40Z",
E               "updated_by": {
E                 "kind": "host",
E                 "surface": "launch",
E                 "principal": "host"
E               }
E             },
E             "runner_capabilities": [
E               "hijack"
E             ],
E             "code_identity": {
E               "schema_version": 1,
E               "captured_at": "2026-11-17T06:32:39.878875+00:00",
E               "roots": [
E                 {
E                   "name": "sase",
E                   "role": "host",
E                   "version": "0.19.0",
E                   "commit": "3f3cf4fb3844d47b47ca9319d676a0344751d075",
E                   "source_root": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27",
E                   "install_type": "editable"
E                 },
E                 {
E                   "name": "sase-core-rs",
E                   "role": "core",
E                   "version": "0.44.2",
E                   "commit": null,
E                   "source_root": null,
E                   "install_type": "wheel"
E                 },
E                 {
E                   "name": "sase-github",
E                   "role": "plugin",
E                   "version": "0.2.11",
E                   "commit": null,
E                   "source_root": null,
E                   "install_type": "wheel"
E                 },
E                 {
E                   "name": "sase-research-artifacts",
E                   "role": "plugin",
E                   "version": "0.2.0",
E                   "commit": null,
E                   "source_root": null,
E                   "install_type": "wheel"
E                 }
E               ]
E             },
E             "booted_at": "2026-11-17T06:32:39.878851+00:00",
E             "launch_scratch_key": "hijack-canary-ws3-261117_013238",
E             "prompt_origin": "generated",
E             "prompt_source_surface": "unknown",
E             "patch_name": "hijack-canary",
E             "changespec_name": "hijack-canary",
E             "cl_name": "hijack-canary",
E             "launch_submitted_at": "2026-11-17T06:32:38.732795Z",
E             "runner_claim_owner_key": "20261117013238",
E             "run_started_at": "2026-11-17T06:32:40.676655+00:00",
E             "lifecycle_phase": "finalizing",
E             "lifecycle_phase_at": "2026-11-17T06:32:44.351064+00:00",
E             "lifecycle_phases": [
E               {
E                 "phase": "booting",
E                 "at": "2026-11-17T06:32:40.485140+00:00"
E               },
E               {
E                 "phase": "waiting",
E                 "at": "2026-11-17T06:32:40.634973+00:00"
E               },
E               {
E                 "phase": "provider_running",
E                 "at": "2026-11-17T06:32:41.045680+00:00"
E               },
E               {
E                 "phase": "provider_running",
E                 "at": "2026-11-17T06:32:41.821716+00:00"
E               },
E               {
E                 "phase": "provider_done",
E                 "at": "2026-11-17T06:32:42.791516+00:00"
E               },
E               {
E                 "phase": "finalizing",
E                 "at": "2026-11-17T06:32:42.813541+00:00"
E               },
E               {
E                 "phase": "finalizing",
E                 "at": "2026-11-17T06:32:44.351064+00:00"
E               }
E             ],
E             "runner_slot_wait_s": 0.04178881645202637,
E             "workspace_head": "1dcbba612a32cb49cb58610c98c1f4addf39f344",
E             "instruction_snapshot": [],
E             "continuation_workspace_ref": "local:continuation/workspace_facts.json",
E             "continuation_workspace_facts_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238/continuation/workspace_facts.json",
E             "continuation_prepared_prompt_ref": "local:continuation/prepared_prompt.json",
E             "continuation_prepared_prompt_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238/continuation/prepared_prompt.json",
E             "continuation_materialized_prompt_ref": "local:continuation/text/fdd9661c03ad879ace39948cc370c42f9f7c6367b7593ba40edda8deae17d2e0.txt",
E             "finalizers": {
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "selected": [
E                 "commit"
E               ],
E               "raw_operations": []
E             },
E             "finalizer_status": {
E               "schema_version": 1,
E               "phase": "settled",
E               "reason": null,
E               "status": "success",
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "run_id": "995a6d4a19de4c2a8b0f32b013849531",
E               "started_at": 1794897162.83846,
E               "updated_at": 1794897163.4843507,
E               "runner": {
E                 "pid": 1176068,
E                 "identity": "39d14458-b9c5-4e7b-bfc2-10aeb016557d:14142875"
E               },
E               "instances": [
E                 {
E                   "id": "commit",
E                   "status": "success",
E                   "attempt": 0,
E                   "max_attempts": 2,
E                   "op": null,
E                   "step": null,
E                   "started_at": 1794897163.341798,
E                   "finished_at": 1794897163.3581486,
E                   "headline": null,
E                   "warnings": 0,
E                   "reason": null
E                 }
E               ],
E               "instance_count": 1
E             },
E             "exec_llm_provider": "fakey",
E             "instructions": {
E               "schema_version": 1,
E               "count": 1,
E               "latest": {
E                 "seq": 0,
E                 "provider": "fakey",
E                 "purpose": "ordinary",
E                 "sha256": "d772cdc2c1e5dec4d0f29dc4ef5d9dfcd7b12b8397faeee3d79f323c5c800b78",
E                 "common_digest": "6218f8d5ea5809c3b15178e40b84ad8779c9c6dd2e73a3df092f4fd1408dfef7",
E                 "manifest": "instructions/00-fakey.json",
E                 "delivery_status": "inherits_native"
E               }
E             },
E             "workflow_name": "canary",
E             "role_suffix": "--0",
E             "agent_session": "canary",
E             "agent_session_role": "root",
E             "chat_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013238.md",
E             "monitor_id": "ac1ay0rdpev0",
E             "monitor_member_agent_name": "canary--mon",
E             "continuation_node_id": "agent-delta:20261117013238:3d844aa5248f476e",
E             "continuation_manifest_ref": "local:continuation/manifest.json",
E             "continuation_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238/continuation/manifest.json",
E             "continuation_agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013238:3d844aa5248f476e.json",
E             "continuation_node_ref": "local:continuation/nodes/agent-delta:20261117013238:3d844aa5248f476e.json",
E             "continuation_status": "completed",
E             "continuation_portable_content_ref": "file:explicit:9c0e48fa6812856b17f0ed01",
E             "continuation_node_portable_ref": "file:explicit:dbbf83c57ce3da0f9d2c2b02",
E             "handoff_protocol": "staged",
E             "stopped_at": "2026-11-17T06:32:44.510808+00:00"
E           }
E           done:
E           {
E             "artifacts_timestamp": "20261117013238",
E             "changespec_name": "hijack-canary",
E             "cl_name": "hijack-canary",
E             "continuation": {
E               "agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013238:3d844aa5248f476e.json",
E               "manifest_ref": "local:continuation/manifest.json",
E               "node_id": "agent-delta:20261117013238:3d844aa5248f476e",
E               "node_ref": "local:continuation/nodes/agent-delta:20261117013238:3d844aa5248f476e.json",
E               "workspace_ref": "local:continuation/workspace_facts.json"
E             },
E             "default_artifacts_persisted": true,
E             "diff_path": null,
E             "exec_llm_provider": "fakey",
E             "finished_at": 1794897164.480048,
E             "image_paths": [],
E             "llm_provider": "fakey",
E             "markdown_pdf_paths": [],
E             "model": "fakey-large",
E             "name": "canary--0",
E             "outcome": "completed",
E             "output_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/workflows/202611/hijack-canary_ace-run-261117_013238.txt",
E             "patch_name": "hijack-canary",
E             "plan_path": null,
E             "project_file": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/hijack-canary.sase",
E             "response_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013238.md",
E             "step_output": {
E               "_raw": "canary recovered"
E             },
E             "timestamp": "261117_013238",
E             "vcs_provider": "Git (bare)",
E             "video_paths": [],
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-h639gipx/.local/state/sase/workspaces/primary-5230f3a5/primary_3",
E             "workspace_num": 3
E           }
E           === all artifact dirs ===
E           /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238: ['.sase_handoff.lock', '.sase_handoff_adopted.json', '.sase_handoff_recovery.json', '.sase_handoff_response.json', '.sase_handoff_staged.json', 'agent_meta.json', 'continuation', 'continuation_prompt_measurements.jsonl', 'done.json', 'final_context.json', 'final_context_host.json', 'final_declaration.lock', 'finalizer_baseline.json', 'finalizer_baseline.json.lock', 'finalizer_plan.authority.json', 'finalizer_plan.json', 'finalizer_plan.lock', 'finalizer_result.json', 'finalizer_result.lock', 'finalizers', 'instructions', 'live_reply.md', 'live_reply_timestamps.jsonl', 'prompt_step_main.json', 'raw_prompt.md', 'sase.md', 'submitted_prompt.md', 'workflow-tmp_261117_013241-main_prompt.md', 'workflow_state.json']
E           -- agent_meta.json --
E           ryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238/continuation/prepared_prompt.json",
E             "continuation_materialized_prompt_ref": "local:continuation/text/fdd9661c03ad879ace39948cc370c42f9f7c6367b7593ba40edda8deae17d2e0.txt",
E             "finalizers": {
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "selected": [
E                 "commit"
E               ],
E               "raw_operations": []
E             },
E             "finalizer_status": {
E               "schema_version": 1,
E               "phase": "settled",
E               "reason": null,
E               "status": "success",
E               "plan_digest": "c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145",
E               "run_id": "995a6d4a19de4c2a8b0f32b013849531",
E               "started_at": 1794897162.83846,
E               "updated_at": 1794897163.4843507,
E               "runner": {
E                 "pid": 1176068,
E                 "identity": "39d14458-b9c5-4e7b-bfc2-10aeb016557d:14142875"
E               },
E               "instances": [
E                 {
E                   "id": "commit",
E                   "status": "success",
E                   "attempt": 0,
E                   "max_attempts": 2,
E                   "op": null,
E                   "step": null,
E                   "started_at": 1794897163.341798,
E                   "finished_at": 1794897163.3581486,
E                   "headline": null,
E                   "warnings": 0,
E                   "reason": null
E                 }
E               ],
E               "instance_count": 1
E             },
E             "exec_llm_provider": "fakey",
E             "instructions": {
E               "schema_version": 1,
E               "count": 1,
E               "latest": {
E                 "seq": 0,
E                 "provider": "fakey",
E                 "purpose": "ordinary",
E                 "sha256": "d772cdc2c1e5dec4d0f29dc4ef5d9dfcd7b12b8397faeee3d79f323c5c800b78",
E                 "common_digest": "6218f8d5ea5809c3b15178e40b84ad8779c9c6dd2e73a3df092f4fd1408dfef7",
E                 "manifest": "instructions/00-fakey.json",
E                 "delivery_status": "inherits_native"
E               }
E             },
E             "workflow_name": "canary",
E             "role_suffix": "--0",
E             "agent_session": "canary",
E             "agent_session_role": "root",
E             "chat_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013238.md",
E             "monitor_id": "ac1ay0rdpev0",
E             "monitor_member_agent_name": "canary--mon",
E             "continuation_node_id": "agent-delta:20261117013238:3d844aa5248f476e",
E             "continuation_manifest_ref": "local:continuation/manifest.json",
E             "continuation_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013238/continuation/manifest.json",
E             "continuation_agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013238:3d844aa5248f476e.json",
E             "continuation_node_ref": "local:continuation/nodes/agent-delta:20261117013238:3d844aa5248f476e.json",
E             "continuation_status": "completed",
E             "continuation_portable_content_ref": "file:explicit:9c0e48fa6812856b17f0ed01",
E             "continuation_node_portable_ref": "file:explicit:dbbf83c57ce3da0f9d2c2b02",
E             "handoff_protocol": "staged",
E             "stopped_at": "2026-11-17T06:32:44.510808+00:00"
E           }
E           -- done.json --
E           {
E             "artifacts_timestamp": "20261117013238",
E             "changespec_name": "hijack-canary",
E             "cl_name": "hijack-canary",
E             "continuation": {
E               "agent_delta_ref": "local:continuation/records/agent_delta/agent-delta:20261117013238:3d844aa5248f476e.json",
E               "manifest_ref": "local:continuation/manifest.json",
E               "node_id": "agent-delta:20261117013238:3d844aa5248f476e",
E               "node_ref": "local:continuation/nodes/agent-delta:20261117013238:3d844aa5248f476e.json",
E               "workspace_ref": "local:continuation/workspace_facts.json"
E             },
E             "default_artifacts_persisted": true,
E             "diff_path": null,
E             "exec_llm_provider": "fakey",
E             "finished_at": 1794897164.480048,
E             "image_paths": [],
E             "llm_provider": "fakey",
E             "markdown_pdf_paths": [],
E             "model": "fakey-large",
E             "name": "canary--0",
E             "outcome": "completed",
E             "output_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/workflows/202611/hijack-canary_ace-run-261117_013238.txt",
E             "patch_name": "hijack-canary",
E             "plan_path": null,
E             "project_file": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/hijack-canary.sase",
E             "response_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/chats/202611/hijack_canary-ace_run-canary__0-261117_013238.md",
E             "step_output": {
E               "_raw": "canary recovered"
E             },
E             "timestamp": "261117_013238",
E             "vcs_provider": "Git (bare)",
E             "video_paths": [],
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-h639gipx/.local/state/sase/workspaces/primary-5230f3a5/primary_3",
E             "workspace_num": 3
E           }
E           /var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242: ['.agent_directive_persistence.lock', '.live_reply.md.lock', '.proc_settled.json', '.sase_user_kill_pending', 'agent_meta.json', 'continuation', 'diagnostics', 'done.json', 'finalizer_baseline.json', 'finalizer_baseline.json.lock', 'hijack_recovery', 'live_reply.md', 'monitor_start_timing.json', 'staged_monitor_launch.json', 'workflow_state.json']
E           -- agent_meta.json --
E           -home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/diagnostics/diagnostic_manifest.json",
E             "monitor_diagnostic_manifest_ref": "file:monitor-diagnostic-manifest:ac1ay0rdpev0",
E             "monitor_retained_log_metadata_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/diagnostics/retained_log_metadata.json",
E             "monitor_retained_log_ref": "file:monitor-retained-log:ac1ay0rdpev0",
E             "continuation_monitor_result_id": "result:ac1ay0rdpev0:8c025eaee2f322ed",
E             "continuation_monitor_result_ref": "local:continuation/records/monitor_result/result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_monitor_result_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/continuation/records/monitor_result/result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_monitor_result_sha256": "3d9f9d9d9b6f45896d40536dee912595957ae61c244326f8e51d0dc0f94006a5",
E             "continuation_monitor_result_node_id": "monitor-result:ac1ay0rdpev0:8c025eaee2f322ed",
E             "continuation_monitor_result_node_ref": "local:continuation/nodes/monitor-result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_monitor_result_manifest_ref": "local:continuation/monitor_result_manifest.json",
E             "continuation_monitor_result_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/continuation/monitor_result_manifest.json",
E             "continuation_node_id": "monitor-result:ac1ay0rdpev0:8c025eaee2f322ed",
E             "continuation_node_ref": "local:continuation/nodes/monitor-result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_manifest_ref": "local:continuation/monitor_result_manifest.json",
E             "continuation_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/continuation/monitor_result_manifest.json",
E             "continuation_monitor_result_portable_ref": "file:explicit:7b01878d9be57d172077b6b7",
E             "continuation_node_portable_ref": "file:explicit:0a7922400fb778a84eefae52",
E             "continuation_parent_portable_refs": {
E               "agent-delta:20261117013238:3d844aa5248f476e": "file:explicit:b03ca0e52b14849ff31df5c2"
E             },
E             "stopped_at": "2026-11-17T06:32:44.766716Z",
E             "monitor_hijack_id": "hijack-canary--mon-d1f1350ca311",
E             "monitor_hijack_recovery_ref": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/hijack_recovery/hijack-canary--mon-d1f1350ca311.json",
E             "monitor_hijack_boundary_outcome": "stopped",
E             "monitor_hijack_state": "held",
E             "monitor_followup_outcome": "hijacked",
E             "monitor_followup_error": null
E           }
E           -- done.json --
E           ,
E             "boundary_outcome": "stopped",
E             "changespec_name": "hijack-canary",
E             "cl_name": "hijack-canary",
E             "continuation_monitor_result_id": "result:ac1ay0rdpev0:8c025eaee2f322ed",
E             "continuation_monitor_result_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/continuation/monitor_result_manifest.json",
E             "continuation_monitor_result_manifest_ref": "local:continuation/monitor_result_manifest.json",
E             "continuation_monitor_result_node_ref": "local:continuation/nodes/monitor-result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_monitor_result_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/continuation/records/monitor_result/result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_monitor_result_ref": "local:continuation/records/monitor_result/result:ac1ay0rdpev0:8c025eaee2f322ed.json",
E             "continuation_monitor_result_sha256": "3d9f9d9d9b6f45896d40536dee912595957ae61c244326f8e51d0dc0f94006a5",
E             "finished_at": 1794897165.8631191,
E             "monitor_diagnostic_manifest_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/diagnostics/diagnostic_manifest.json",
E             "monitor_diagnostic_manifest_ref": "file:monitor-diagnostic-manifest:ac1ay0rdpev0",
E             "monitor_elapsed_seconds": null,
E             "monitor_exit_code": -15,
E             "monitor_followup_outcome": "hijacked",
E             "monitor_hijack_id": "hijack-canary--mon-d1f1350ca311",
E             "monitor_hijack_recovery_ref": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/hijack_recovery/hijack-canary--mon-d1f1350ca311.json",
E             "monitor_id": "ac1ay0rdpev0",
E             "monitor_retained_log_metadata_path": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/artifacts/ace-run/202611/17/20261117013242/diagnostics/retained_log_metadata.json",
E             "monitor_retained_log_ref": "file:monitor-retained-log:ac1ay0rdpev0",
E             "monitor_state": "stopped",
E             "monitor_timeout_kind": null,
E             "monitor_timeout_message": null,
E             "name": "canary--mon",
E             "outcome": "hijacked",
E             "patch_name": "hijack-canary",
E             "project_file": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/test_monitor_hijack_rerun_same0/sase-home/projects/hijack-canary/hijack-canary.sase",
E             "recovery": {
E               "hijack_id": "hijack-canary--mon-d1f1350ca311",
E               "kind": "hijack",
E               "state": "pending"
E             },
E             "status_bucket": "Stopped",
E             "status_label": "Stopped",
E             "workspace_dir": "/var/tmp/sase-6f40cea7/pytest-of-bryan/pytest-7/popen-gw0/home-h639gipx/.local/state/sase/workspaces/primary-5230f3a5/primary_3",
E             "workspace_num": 3
E           }

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/fakey/_agent_hijack_monitor_canary.py:560: AssertionError
----------------------------- Captured stdout call -----------------------------
Hijack hijack-canary--mon-d1f1350ca311 already holds canary--mon; nothing else was stopped
============================= slowest 20 durations =============================
70.58s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_continue_same_workspace
10.57s call     tests/fakey/test_agent_hijack_canary.py::test_anonymous_tmp_workflow_hijack_continue_same_workspace
9.73s call     tests/fakey/test_agent_hijack_canary.py::test_session_hijack_chooses_running_member_one
9.65s call     tests/fakey/test_agent_hijack_canary.py::test_finalizing_latch_suppresses_staged_pipe_then_continues_same_workspace
7.76s call     tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_rerun_same_workspace
5.07s call     tests/fakey/test_agent_hijack_canary.py::test_finalizing_latch_without_handoff_moots_and_keeps_real_outcome
0.12s setup    tests/fakey/test_agent_hijack_canary.py::test_anonymous_tmp_workflow_hijack_continue_same_workspace
0.02s teardown tests/fakey/test_agent_hijack_canary.py::test_finalizing_latch_without_handoff_moots_and_keeps_real_outcome
0.01s teardown tests/fakey/test_agent_hijack_canary.py::test_finalizing_latch_suppresses_staged_pipe_then_continues_same_workspace
0.01s teardown tests/fakey/test_agent_hijack_canary.py::test_anonymous_tmp_workflow_hijack_continue_same_workspace
0.01s call     tests/test_agent_hijack_facts.py::test_reserved_delivery_is_pending_and_acknowledged_is_not
0.01s call     tests/test_agent_hijack_facts.py::test_pending_delivery_keeps_the_monitor_as_occupant
0.01s teardown tests/fakey/test_agent_hijack_canary.py::test_session_hijack_chooses_running_member_one

(7 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_continue_same_workspace
FAILED tests/fakey/test_agent_hijack_canary.py::test_monitor_hijack_rerun_same_workspace
=================== 2 failed, 13 passed in 117.67s (0:01:57) ===================
error: recipe `test` failed on line 641 with exit code 1
failed  exit=1  duration=119753ms

