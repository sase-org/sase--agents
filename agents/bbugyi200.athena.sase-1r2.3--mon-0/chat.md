# Chat History - ace-run (sase-1r2.3--mon-0)

- **TIMESTAMP:** 2026-11-03 11:47:20 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1r2.3--mon-0

## Prompt

sase monitor start --command 'set -eu\nUV_PROJECT_ENVIRONMENT=.venv/py312 uv sync --locked --python 3.12 --extra dev\nPY312=.venv/py312/bin/python\nprintf "Python 3.12 stress repetitions\\n"\ntest_paths="tests/ace/tui/widgets/decks/test_deck_view_files_pilot.py::test_stale_results_dropped_and_reset_to_auto_redecides\n tests/ace/tui/modals/test_new_project_create_execution.py::test_create_review_button_enters_review_and_back_restores_configure\n tests/ace/tui/widgets/test_prompt_todo_highlight.py::test_todo_background_yields_to_selection_search_yank_and_cursor\n tests/ace/tui/test_prompt_bar_hot_spare.py::test_cancel_saves_once_submit_path_quiet\n tests/completion/test_candidates_providers.py::test_pending_plan_candidates_offer_display_names_newest_first\n tests/test_core_facade/test_notification_store_real_extension.py::test_real_extension_round_trips_bulk_mute_and_snooze\n tests/test_notification_indicator.py\n tests/test_agent_auto_restart_sweep_safety.py::test_recent_legacy_skew_row_is_candidate\n tests/test_agent_auto_restart_ux.py::test_apply_recovery_flags_stale_pending\n tests/sdd_store/test_sdd_git_streaming.py::test_interruption_kills_process_group_with_pipe_holding_descendant\n tests/sdd_store/test_sdd_git_streaming.py::test_streaming_stall_timeout_fires_without_progress\n tests/test_sudo_ledger_settlement.py::test_sudo_answer_defers_after_long_lock_timeout_and_reclaim_settles_later\n tests/ace/tui/actions/test_prompt_mini_macro_location_flow_picker.py\n tests/ace/tui/actions/test_prompt_mini_macro_location_flow_existing.py::test_existing_typeahead_seeds_finder_query\n tests/monitor"\nfor iteration in $(seq 1 20); do\n  printf "Python 3.12 serial pass %s/20\\n" "$iteration"\n  $PY312 -m pytest -q --disable-warnings $test_paths\ndone\nprintf "Python 3.12 xdist passes\\n"\nfor iteration in 1 2 3; do\n  printf "Python 3.12 xdist pass %s/3\\n" "$iteration"\n  $PY312 -m pytest -n 8 --dist=worksteal -q -m "not slow and not visual" tests/ace/tui tests/monitor tests/sdd_store/test_sdd_git_streaming.py tests/test_sudo_ledger_settlement.py tests/completion/test_candidates_providers.py tests/test_core_facade/test_notification_store_real_extension.py tests/test_notification_indicator.py tests/test_agent_auto_restart_sweep_safety.py tests/test_agent_auto_restart_ux.py\ndone\nprintf "Python 3.14 xdist passes\\n"\nfor iteration in 1 2 3; do\n  printf "Python 3.14 xdist pass %s/3\\n" "$iteration"\n  .venv/bin/python -m pytest -n 8 --dist=worksteal -q -m "not slow and not visual" tests/ace/tui tests/monitor tests/sdd_store/test_sdd_git_streaming.py tests/test_sudo_ledger_settlement.py tests/completion/test_candidates_providers.py tests/test_core_facade/test_notification_store_real_extension.py tests/test_notification_indicator.py tests/test_agent_auto_restart_sweep_safety.py tests/test_agent_auto_restart_ux.py\ndone' --reason 'Repeat the blocking CI failure lanes serially and under xdist after correcting the stale test path'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Resolved 139 packages in 3ms
Checked 98 packages in 170ms
Python 3.12 stress repetitions
Python 3.12 serial pass 1/20
........................................................................ [ 10%]
........................................................................ [ 20%]
........................................................................ [ 30%]
............................................................F........F.. [ 41%]
...........................................FFFFFFFFFFFFFFFFFFFFFFFFFFFFF [ 51%]
FFFFFFFFF..F...F.....F............F..................................... [ 61%]
.FFF.........FF......................................................... [ 72%]
.....................F...F..........................F..F...FF........... [ 82%]
.F...................................................................... [ 92%]
...................................................                      [100%]
=================================== FAILURES ===================================
________ test_owner_cleanup_stops_monitor_child_and_suppresses_followup ________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_owner_cleanup_stops_monit0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd44c5c40>

    def test_owner_cleanup_stops_monitor_child_and_suppresses_followup(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        project_file = write_project_file(
            "proj",
            running_claims=[WorkspaceClaim(3, "ace-run", "acme", pid=os.getpid())],
        )
        make_starter_agent(
            "proj",
            "20260812120000",
            "acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=3,
            pid=os.getpid(),
            cl_name="acme",
        )
        _patch_live_records(monkeypatch)
        record = start_monitor(
            StartMonitorRequest(
                command="sleep 30",
                reason="owner cleanup should stop this command",
                timeout_seconds=60.0,
                cwd=str(tmp_path),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
                next_action="SENTINEL_NEXT should never launch",
            )
        )
        supervisor = record.pid
        assert supervisor is not None
        assert is_process_running(supervisor)
    
        identity = {
            "agent_type": "run",
            "cl_name": "acme--mon",
            "raw_suffix": Path(record.artifacts_dir).name,
        }
        success, message, _payload = _apply_cleanup_payload_for_result(
            {
                "action": "kill",
                "transaction": "bulk_kill",
                "cleanup_plan": {
                    "schema_version": AGENT_CLEANUP_WIRE_SCHEMA_VERSION,
                    "kill_items": [
                        {
                            "identity": identity,
                            "kind": "monitor",
                            "monitor_id": record.monitor_id,
                        }
                    ],
                    "side_effects": {
                        "monitor_stop_requests": [
                            {
                                "identity": identity,
                                "monitor_id": record.monitor_id,
                            }
                        ]
                    },
                },
                "kill_items": [],
                "dismissable": [],
                "added_identities": [],
            }
        )
        assert success is True, message
        done = wait_for_done(record.artifacts_dir, timeout=10.0)
        assert done["monitor_state"] == "stopped"
        deadline = time.monotonic() + 5
        while is_process_running(supervisor) and time.monotonic() < deadline:
            time.sleep(0.05)  # sase-test-wait: poll monitor supervisor exit
        assert not is_process_running(supervisor)
        proc = get_proc(record.monitor_id)
        assert proc is not None
        assert proc.status == "killed"
        meta = json.loads(
            (Path(record.artifacts_dir) / "agent_meta.json").read_text(encoding="utf-8")
        )
        assert meta.get("monitor_followup_agent") is None
        assert meta.get("monitor_followup_outcome") in {None, "suppressed"}
        listed = list_monitors(project="proj")
        assert listed[0].monitor_state == "stopped"
        assert listed[0].followup_agent is None
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=3040823, artifacts_timestamp='20261103114103', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_owner_cleanup.py:146: AssertionError
_______________ test_claim_is_released_when_there_is_no_followup _______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_claim_is_released_when_th0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce9d8980>

    def test_claim_is_released_when_there_is_no_followup(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        project_file = write_project_file(
            "proj",
            running_claims=[WorkspaceClaim(3, "ace-run", "acme", pid=os.getpid())],
        )
        make_starter_agent(
            "proj",
            "20260812120000",
            "acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=3,
            pid=os.getpid(),
            cl_name="acme",
        )
        _patch_live_records(monkeypatch)
        record = start_monitor(
            StartMonitorRequest(
                command="true",
                reason="verify claim release",
                timeout_seconds=30.0,
                cwd=str(tmp_path),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
            )
        )
        wait_for_done(record.artifacts_dir)
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=3049671, artifacts_timestamp='20261103114129', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_proc_facade.py:320: AssertionError
_______________ test_prepared_completion_success_releases_clean ________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_prepared_completion_succe0')

    def test_prepared_completion_success_releases_clean(tmp_path: Path) -> None:
        """A committed host completion releases a clean workspace normally."""
        from sase.monitor._host_completion_shared import HOST_COMPLETED_OUTCOME
    
        repo = init_retention_repo(tmp_path / "ws", dirty=False)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome=HOST_COMPLETED_OUTCOME
        )
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:103: AssertionError
________________ test_prepared_completion_failure_retains_dirty ________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_prepared_completion_failu0')

    def test_prepared_completion_failure_retains_dirty(tmp_path: Path) -> None:
        """A failed completion with unresolved dirt retains the workspace."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo, outcome="not-launchable")
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:117: AssertionError
____________________ test_repeated_settlement_is_idempotent ____________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_repeated_settlement_is_id0')

    def test_repeated_settlement_is_idempotent(tmp_path: Path) -> None:
        """Settling twice pins once and keeps the checkout intact."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
    
        first = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="stopped",
            exit_code=None,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
        meta = read_retention_meta(artifacts_dir)
        second = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="stopped",
            exit_code=None,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
>       assert first.error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = _MonitorFollowupSettlementResult(error='workspace retention settlement failed: stale binding (sase_core_rs is importab...ipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)', launch_result=None).error

tests/monitor/test_monitor_retention_lifecycle.py:154: AssertionError
_____________ test_resume_success_label_without_proof_leaves_hold ______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_resume_success_label_with0')

    def test_resume_success_label_without_proof_leaves_hold(tmp_path: Path) -> None:
        """A success label without live successor custody cannot clear unresolved."""
        from sase.monitor.resume import _settle_retention_after_resume
        from sase.workspace_provider.retention_record import (
            read_workspace_retention_record,
        )
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, _project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
>       assert (
            release_monitor_claim(meta, project_name="proj", artifacts_dir=artifacts_dir)
            is None
        )
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = release_monitor_claim({'agent_session': 'acme', 'agent_session_role': 'monitor', 'cl_name': 'acme', 'model': 'test', ...}, project_name='proj', artifacts_dir='/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_resume_success_label_with0/.sase/projects/proj/artifacts/ace-run/202609/06/20260906120000')

tests/monitor/test_monitor_retention_lifecycle.py:172: AssertionError
__________________ test_resume_degraded_and_failed_leave_hold __________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_resume_degraded_and_faile0')

    def test_resume_degraded_and_failed_leave_hold(tmp_path: Path) -> None:
        """Degraded or failed resumes must not clear the original hold."""
        from sase.monitor.resume import _settle_retention_after_resume
    
        cases = (
            FollowupLaunchResult(
                launched=True,
                degraded_reason="fell back to workspace #0",
                agent_name="acme--mon@1",
            ),
            FollowupLaunchResult(launched=False, error="boom"),
        )
        for index, launch in enumerate(cases):
            repo = init_retention_repo(tmp_path / f"ws-{index}", dirty=True)
            write_project_file(
                "proj",
                running_claims=[
                    WorkspaceClaim(
                        10 + index,
                        RETENTION_CLAIM_WORKFLOW,
                        "acme",
                        pid=os.getpid(),
                        artifacts_timestamp=f"2026090612000{index}",
                    )
                ],
            )
            artifacts_dir = make_starter_agent(
                "proj",
                f"2026090612000{index}",
                "acme--mon",
                agent_session="acme",
                agent_session_role="monitor",
                monitor_id="abc123def456",
                monitor_command="true",
                monitor_cwd=str(repo),
                monitor_reason="test",
                monitor_start_status="MONITORING",
                monitor_stop_status="MONITORED",
                monitor_timeout_seconds=30.0,
                monitor_state="failed",
                cl_name="acme",
                workspace_dir=str(repo),
                workspace_num=10 + index,
                pid=os.getpid(),
                monitor_continuation_protocol=MONITOR_CONTINUATION_PROTOCOL_RECORDS_V1,
                monitor_next_action="Report it.",
            )
            meta = read_retention_meta(artifacts_dir)
>           assert (
                release_monitor_claim(
                    meta, project_name="proj", artifacts_dir=artifacts_dir
                )
                is None
            )
E           assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E            +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = release_monitor_claim({'agent_session': 'acme', 'agent_session_role': 'monitor', 'cl_name': 'acme', 'model': 'test', ...}, project_name='proj', artifacts_dir='/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_resume_degraded_and_faile0/.sase/projects/proj/artifacts/ace-run/202609/06/20260906120000')

tests/monitor/test_monitor_retention_lifecycle.py:240: AssertionError
___________________________ test_stale_claim_is_noop ___________________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stale_claim_is_noop0')

    def test_stale_claim_is_noop(tmp_path: Path) -> None:
        """Settlement against a moved claim never pins or clears the occupant."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
        meta["pid"] = 999999999
        write_retention_meta(artifacts_dir, meta)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:268: AssertionError
____________________ test_proc_reconcile_path_retains_dirty ____________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_proc_reconcile_path_retai0')

    def test_proc_reconcile_path_retains_dirty(tmp_path: Path) -> None:
        """The proc settlement entry point converges on the same retention."""
        from sase.monitor.proc_adapter import settle_monitor_followup
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo, next_action=None)
        meta = read_retention_meta(artifacts_dir)
        state: dict[str, object] = {
            "artifacts_dir": artifacts_dir,
            "proc_id": "abc123def456",
            "status": "success",
            "termination_reason": "success",
            "exit_code": 0,
            "monitor_state": "completed",
            "monitor_exit_code": 0,
            "monitor_elapsed_seconds": 0.0,
            "monitor_meta": dict(meta),
        }
    
        settle_monitor_followup(state)
    
        # Completed + clean would release; dirty retains through the same adapter.
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_lifecycle.py:299: AssertionError
----------------------------- Captured stdout call -----------------------------
{"context": "monitor-settlement", "event": "launch_scratch_cleanup", "reason": "no-scratch-key", "removed": 0, "removed_bytes": 0, "scratch_key": null, "skipped": 0, "status": "skipped"}
______________ test_dirty_linked_repo_beyond_eighth_still_retains ______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_dirty_linked_repo_beyond_0')

    def test_dirty_linked_repo_beyond_eighth_still_retains(tmp_path: Path) -> None:
        """No eight-repository cutoff: the ninth dirty linked repo retains."""
        repos: list[tuple[str, Path]] = []
        primary = init_retention_repo(tmp_path / "ws-0", dirty=False)
        repos.append(("primary", primary))
        for index in range(1, 9):
            clean = init_retention_repo(tmp_path / f"ws-{index}", dirty=False)
            repos.append((f"linked-{index}", clean))
        ninth = init_retention_repo(tmp_path / "ws-9", dirty=True)
        repos.append(("linked-9", ninth))
        artifacts_dir, project_file = make_retention_monitor(primary)
        _write_monitor_baselines(artifacts_dir, repos)
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:322: AssertionError
____________ test_unavailable_owned_checkout_retains_as_uncertainty ____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_unavailable_owned_checkou0')

    def test_unavailable_owned_checkout_retains_as_uncertainty(
        tmp_path: Path,
    ) -> None:
        """A deleted owned checkout is uncertainty, not a clean release."""
        import shutil
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        _write_monitor_baselines(artifacts_dir, [("primary", repo)])
        shutil.rmtree(repo)
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:348: AssertionError
_______________ test_stale_binding_retries_in_fresh_interpreter ________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stale_binding_retries_in_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce095070>

    def test_stale_binding_retries_in_fresh_interpreter(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A stale loaded binding retries the same Rust settlement fresh."""
        from sase.turns import workspace_retention as _adapter
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
    
        def _stale(*_args: object, **_kwargs: object) -> object:
            raise TypeError("old release_workspace signature")
    
        monkeypatch.setattr(_adapter, "settle_stranded_workspace", _stale)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert 'workspace retention settlement failed: stale binding (old release_workspace signature; ecide_workspace_retention")\n ... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)' is None

tests/monitor/test_monitor_retention_lifecycle.py:377: AssertionError
______________ test_failed_git_preflight_without_baseline_retains ______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_failed_git_preflight_with0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce91e300>

    def test_failed_git_preflight_without_baseline_retains(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A failed git preflight keeps the known dirty workspace instead of dropping it."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
        monkeypatch.setattr(
            "sase.monitor.settlement_fresh_owner._classify_git_toplevel",
            lambda _path: ("failed", "git preflight failed"),
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:403: AssertionError
___________ test_discovery_failure_with_dirty_opened_linked_retains ____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_discovery_failure_with_di0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcf7e2240>

    def test_discovery_failure_with_dirty_opened_linked_retains(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Failed linked discovery retains rather than classifying only a clean primary."""
        primary = init_retention_repo(tmp_path / "ws", dirty=False)
        linked = init_retention_repo(tmp_path / "linked", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(primary)
        write_opened_linked(artifacts_dir, "linked-core", linked)
        monkeypatch.setattr(
            "sase.monitor.settlement_fresh_owner._shared_repos",
            lambda *_args, **_kwargs: ([], set(), "linked discovery failed"),
        )
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:431: AssertionError
_______________________ test_repo_less_command_releases ________________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_repo_less_command_release0')

    def test_repo_less_command_releases(tmp_path: Path) -> None:
        """A positively known non-repository command still releases."""
        workspace = tmp_path / "plain"
        workspace.mkdir()
        (workspace / "notes.txt").write_text("not a repo\n", encoding="utf-8")
        artifacts_dir, project_file = make_retention_monitor(workspace)
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:454: AssertionError
________________ test_unchanged_foreign_baseline_dirt_releases _________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_unchanged_foreign_baselin0')

    def test_unchanged_foreign_baseline_dirt_releases(tmp_path: Path) -> None:
        """Dirt already present in the starter baseline still releases."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        _write_monitor_baselines(
            artifacts_dir, [("primary", repo)], capture_fingerprints=True
        )
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:473: AssertionError
__ test_stale_owner_and_unavailable_fresh_interpreter_pins_monitor_timestamp ___

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stale_owner_and_unavailab0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcf368950>

    def test_stale_owner_and_unavailable_fresh_interpreter_pins_monitor_timestamp(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Failure pin uses the monitor artifact timestamp, never parent_timestamp."""
        import sase.monitor._settlement_retention as settlement_mod
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
        meta["parent_timestamp"] = "20260906115900"
        write_retention_meta(artifacts_dir, meta)
    
        def _stale_owner(*_args: object, **_kwargs: object) -> object:
            raise AttributeError("stale owner adapter")
    
        monkeypatch.setattr(settlement_mod, "_build_retention_owner", _stale_owner)
        monkeypatch.setattr(
            subprocess,
            "run",
            fail_fresh_python_c(OSError("fresh interpreter unavailable")),
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
        assert error is not None
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_lifecycle.py:508: AssertionError
______________ test_successor_collection_failure_pins_dirty_claim ______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_successor_collection_fail0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd0efe8d0>

    def test_successor_collection_failure_pins_dirty_claim(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Successor-proof collection failure pins the exact owner instead of releasing."""
        import sase.monitor._settlement_retention as settlement_mod
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
    
        def _boom(*_args: object, **_kwargs: object) -> object:
            raise OSError("successor collection failed")
    
        monkeypatch.setattr(settlement_mod, "_retention_successor_from_meta", _boom)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
        assert error is not None
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_lifecycle.py:539: AssertionError
____________________ test_pending_write_failure_still_pins _____________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_pending_write_failure_sti0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcf369b80>

    def test_pending_write_failure_still_pins(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A failed pending write still pins the exact matching claim."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
        monkeypatch.setattr(
            "sase.turns.workspace_retention_pending.write_pending_retention_identity",
            lambda *_args, **_kwargs: None,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_lifecycle.py:563: AssertionError
_______________ test_fresh_interpreter_timeout_pins_dirty_claim ________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_fresh_interpreter_timeout0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcf36a8a0>

    def test_fresh_interpreter_timeout_pins_dirty_claim(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A timed-out fresh interpreter still pins the original dirty claim."""
        from sase.turns import workspace_retention as _adapter
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
    
        def _stale(*_args: object, **_kwargs: object) -> object:
            raise TypeError("old release_workspace signature")
    
        monkeypatch.setattr(_adapter, "settle_stranded_workspace", _stale)
        monkeypatch.setattr(
            subprocess,
            "run",
            fail_fresh_python_c(
                subprocess.TimeoutExpired(cmd=["python", "-c"], timeout=60)
            ),
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
        assert error is not None
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_lifecycle.py:601: AssertionError
_______________ test_resume_transfer_with_live_successor_settles _______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_resume_transfer_with_live0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcf36ae70>

    def test_resume_transfer_with_live_successor_settles(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Resume settles a hold only after live successor custody is proven."""
        from sase.monitor.resume import _settle_retention_after_resume
        from sase.workspace_provider.occupant import read_occupant_record
        from sase.workspace_provider.retention_record import read_workspace_retention_record
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo)
        meta = read_retention_meta(artifacts_dir)
>       assert (
            release_monitor_claim(meta, project_name="proj", artifacts_dir=artifacts_dir)
            is None
        )
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = release_monitor_claim({'agent_session': 'acme', 'agent_session_role': 'monitor', 'cl_name': 'acme', 'model': 'test', ...}, project_name='proj', artifacts_dir='/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_resume_transfer_with_live0/.sase/projects/proj/artifacts/ace-run/202609/06/20260906120000')

tests/monitor/test_monitor_retention_lifecycle.py:620: AssertionError
________ test_stopped_dirty_monitor_pins_claim_and_keeps_files[legacy] _________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stopped_dirty_monitor_pin0')
protocol = 'legacy'

    @pytest.mark.parametrize(
        "protocol",
        [MONITOR_CONTINUATION_PROTOCOL_LEGACY, MONITOR_CONTINUATION_PROTOCOL_RECORDS_V1],
    )
    def test_stopped_dirty_monitor_pins_claim_and_keeps_files(
        tmp_path: Path, protocol: str
    ) -> None:
        """Stopped monitors with uncommitted work retain the workspace on both protocols."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo, protocol=protocol)
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="stopped",
            exit_code=None,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
>       assert result.error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = _MonitorFollowupSettlementResult(error='workspace retention settlement failed: stale binding (sase_core_rs is importab...ipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)', launch_result=None).error

tests/monitor/test_monitor_retention_settlement.py:83: AssertionError
______ test_stopped_dirty_monitor_pins_claim_and_keeps_files[records_v1] _______

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stopped_dirty_monitor_pin1')
protocol = 'records_v1'

    @pytest.mark.parametrize(
        "protocol",
        [MONITOR_CONTINUATION_PROTOCOL_LEGACY, MONITOR_CONTINUATION_PROTOCOL_RECORDS_V1],
    )
    def test_stopped_dirty_monitor_pins_claim_and_keeps_files(
        tmp_path: Path, protocol: str
    ) -> None:
        """Stopped monitors with uncommitted work retain the workspace on both protocols."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo, protocol=protocol)
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="stopped",
            exit_code=None,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
>       assert result.error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = _MonitorFollowupSettlementResult(error='workspace retention settlement failed: stale binding (sase_core_rs is importab...ipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)', launch_result=None).error

tests/monitor/test_monitor_retention_settlement.py:83: AssertionError
______________ test_stopped_clean_monitor_releases_claim[legacy] _______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stopped_clean_monitor_rel0')
protocol = 'legacy'

    @pytest.mark.parametrize(
        "protocol",
        [MONITOR_CONTINUATION_PROTOCOL_LEGACY, MONITOR_CONTINUATION_PROTOCOL_RECORDS_V1],
    )
    def test_stopped_clean_monitor_releases_claim(tmp_path: Path, protocol: str) -> None:
        """Stopped monitors with no dirty work keep the normal release path."""
        repo = init_retention_repo(tmp_path / "ws", dirty=False)
        artifacts_dir, project_file = make_retention_monitor(repo, protocol=protocol)
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="stopped",
            exit_code=0,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
>       assert result.error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = _MonitorFollowupSettlementResult(error='workspace retention settlement failed: stale binding (sase_core_rs is importab...ipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)', launch_result=None).error

tests/monitor/test_monitor_retention_settlement.py:128: AssertionError
____________ test_stopped_clean_monitor_releases_claim[records_v1] _____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stopped_clean_monitor_rel1')
protocol = 'records_v1'

    @pytest.mark.parametrize(
        "protocol",
        [MONITOR_CONTINUATION_PROTOCOL_LEGACY, MONITOR_CONTINUATION_PROTOCOL_RECORDS_V1],
    )
    def test_stopped_clean_monitor_releases_claim(tmp_path: Path, protocol: str) -> None:
        """Stopped monitors with no dirty work keep the normal release path."""
        repo = init_retention_repo(tmp_path / "ws", dirty=False)
        artifacts_dir, project_file = make_retention_monitor(repo, protocol=protocol)
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="stopped",
            exit_code=0,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
>       assert result.error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = _MonitorFollowupSettlementResult(error='workspace retention settlement failed: stale binding (sase_core_rs is importab...ipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)', launch_result=None).error

tests/monitor/test_monitor_retention_settlement.py:128: AssertionError
____________________ test_reboot_lost_dirty_monitor_retains ____________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_reboot_lost_dirty_monitor0')

    def test_reboot_lost_dirty_monitor_retains(tmp_path: Path) -> None:
        """A reboot-lost monitor (unknown outcome) retains dirty work."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo, next_action="Report it.")
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="lost",
            exit_code=None,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
        assert result.error is not None  # lost follow-up cannot launch
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_settlement.py:154: AssertionError
____________ test_failed_monitor_with_failed_followup_retains_dirty ____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_failed_monitor_with_faile0')

    def test_failed_monitor_with_failed_followup_retains_dirty(tmp_path: Path) -> None:
        """Launch failure with unresolved dirt retains the original workspace."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, monitor_state="failed", next_action="Report it."
        )
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="failed",
            exit_code=1,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=_failed_launch,
        )
    
        assert result.error is not None
        assert result.launch_result is not None
        assert result.launch_result.launched is False
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_settlement.py:183: AssertionError
_________ test_failed_monitor_with_failed_followup_releases_when_clean _________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_failed_monitor_with_faile1')

    def test_failed_monitor_with_failed_followup_releases_when_clean(
        tmp_path: Path,
    ) -> None:
        """Launch failure with a proven-clean tree keeps the release path."""
        repo = init_retention_repo(tmp_path / "ws", dirty=False)
        artifacts_dir, project_file = make_retention_monitor(repo, next_action="Report it.")
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="failed",
            exit_code=1,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=_failed_launch,
        )
    
        assert result.error is not None  # the launch failure is still reported
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_retention_settlement.py:224: AssertionError
___________ test_degraded_followup_retains_original_dirty_workspace ____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_degraded_followup_retains0')

    def test_degraded_followup_retains_original_dirty_workspace(
        tmp_path: Path,
    ) -> None:
        """A follow-up in another checkout does not discharge the dirty original."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(repo, next_action="Report it.")
        meta = read_retention_meta(artifacts_dir)
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="failed",
            exit_code=1,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=_degraded_launch,
        )
    
>       assert result.error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None
E        +  where "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" = _MonitorFollowupSettlementResult(error='workspace retention settlement failed: stale binding (sase_core_rs is importab... error=None, prompt_path=None, agent_name='acme--mon@1', artifacts_dir='/tmp/other', pid=999999, host_completed=False)).error

tests/monitor/test_monitor_retention_settlement.py:247: AssertionError
_______________ test_blocked_continuation_capture_retains_dirty ________________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_blocked_continuation_capt0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce2ea150>

    def test_blocked_continuation_capture_retains_dirty(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Blocked dispatch (records protocol) retains instead of direct release."""
        import sase.monitor._settlement_followup as settlement
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo,
            monitor_state="failed",
            next_action="Report it.",
            protocol=MONITOR_CONTINUATION_PROTOCOL_RECORDS_V1,
        )
        meta = read_retention_meta(artifacts_dir)
        monkeypatch.setattr(
            settlement, "_continuation_dispatch_blocked_reason", lambda _m: "blocked"
        )
        monkeypatch.setattr(
            settlement, "_repair_missing_starter_parent", lambda _a, _m: False
        )
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="failed",
            exit_code=1,
            elapsed_seconds=0.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=no_launch_followup,
        )
    
        assert result.error is not None
        assert result.launch_result is not None
        assert result.launch_result.launched is False
        claims = get_claimed_workspaces(project_file)
        assert len(claims) == 1
>       assert claims[0].pinned is True
E       AssertionError: assert False is True
E        +  where False = WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260906120000', pinned=False, suffix_fields=()).pinned

tests/monitor/test_monitor_retention_settlement.py:303: AssertionError
____________ test_same_workspace_successor_keeps_transferred_claim _____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_same_workspace_successor_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcfc1e240>

    def test_same_workspace_successor_keeps_transferred_claim(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """An actual transferred claim stays with the successor and its occupant."""
        from sase.workspace_provider.occupant import read_occupant_record
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "acme--mon@1"
        meta["project_file"] = project_file
        meta["project_name"] = "proj"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir, meta, agent="acme--mon@1", disposition="acknowledged"
        )
        successor_pid = os.getpid() + 17
        transfer_retention_to_successor(
            project_file,
            repo,
            from_pid=os.getpid(),
            to_pid=successor_pid,
            timestamp="20260906120100",
        )
        monkeypatch.setattr(
            "sase.monitor.settlement_fresh_owner._receiver_is_live",
            lambda *_args, **_kwargs: True,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:342: AssertionError
_____________ test_stale_launch_label_without_proof_retains_dirty ______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_stale_launch_label_withou0')

    def test_stale_launch_label_without_proof_retains_dirty(tmp_path: Path) -> None:
        """A bare launched label with a still-owned dirty claim must retain."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:365: AssertionError
________ test_delivery_history_without_live_successor_retains[reserved] ________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_delivery_history_without_0')
disposition = 'reserved'

    @pytest.mark.parametrize(
        "disposition",
        ["reserved", "dispatching", "acknowledged", "settled"],
    )
    def test_delivery_history_without_live_successor_retains(
        tmp_path: Path, disposition: str
    ) -> None:
        """Historical delivery labels without a live successor keep the dirty origin."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "receiver-that-does-not-exist"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir,
            meta,
            agent="receiver-that-does-not-exist",
            disposition=disposition,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:401: AssertionError
______ test_delivery_history_without_live_successor_retains[dispatching] _______

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_delivery_history_without_1')
disposition = 'dispatching'

    @pytest.mark.parametrize(
        "disposition",
        ["reserved", "dispatching", "acknowledged", "settled"],
    )
    def test_delivery_history_without_live_successor_retains(
        tmp_path: Path, disposition: str
    ) -> None:
        """Historical delivery labels without a live successor keep the dirty origin."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "receiver-that-does-not-exist"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir,
            meta,
            agent="receiver-that-does-not-exist",
            disposition=disposition,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:401: AssertionError
______ test_delivery_history_without_live_successor_retains[acknowledged] ______

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_delivery_history_without_2')
disposition = 'acknowledged'

    @pytest.mark.parametrize(
        "disposition",
        ["reserved", "dispatching", "acknowledged", "settled"],
    )
    def test_delivery_history_without_live_successor_retains(
        tmp_path: Path, disposition: str
    ) -> None:
        """Historical delivery labels without a live successor keep the dirty origin."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "receiver-that-does-not-exist"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir,
            meta,
            agent="receiver-that-does-not-exist",
            disposition=disposition,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:401: AssertionError
________ test_delivery_history_without_live_successor_retains[settled] _________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_delivery_history_without_3')
disposition = 'settled'

    @pytest.mark.parametrize(
        "disposition",
        ["reserved", "dispatching", "acknowledged", "settled"],
    )
    def test_delivery_history_without_live_successor_retains(
        tmp_path: Path, disposition: str
    ) -> None:
        """Historical delivery labels without a live successor keep the dirty origin."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "receiver-that-does-not-exist"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir,
            meta,
            agent="receiver-that-does-not-exist",
            disposition=disposition,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:401: AssertionError
____________ test_wrong_result_id_delivery_does_not_prove_transfer _____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_wrong_result_id_delivery_0')

    def test_wrong_result_id_delivery_does_not_prove_transfer(tmp_path: Path) -> None:
        """A delivery for another result cannot discharge this monitor's hold."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "acme--mon@1"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir,
            meta,
            agent="acme--mon@1",
            disposition="acknowledged",
            result_id="other-result",
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:433: AssertionError
________ test_degraded_delivery_does_not_prove_same_workspace_transfer _________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_degraded_delivery_does_no0')

    def test_degraded_delivery_does_not_prove_same_workspace_transfer(
        tmp_path: Path,
    ) -> None:
        """A degraded delivery is not same-workspace successor proof."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "acme--mon@1"
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir,
            meta,
            agent="acme--mon@1",
            disposition="acknowledged",
            degraded=True,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:466: AssertionError
_____________ test_live_receiver_without_transferred_claim_retains _____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_live_receiver_without_tra0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd00ceb70>

    def test_live_receiver_without_transferred_claim_retains(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A live name is not transfer while the original still owns the claim."""
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "acme--mon@1"
        meta["project_file"] = project_file
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir, meta, agent="acme--mon@1", disposition="acknowledged"
        )
        monkeypatch.setattr(
            "sase.monitor.settlement_fresh_owner._receiver_is_live",
            lambda *_args, **_kwargs: True,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:500: AssertionError
__________ test_different_workspace_occupant_does_not_prove_transfer ___________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_different_workspace_occup0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce91c2c0>

    def test_different_workspace_occupant_does_not_prove_transfer(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """Occupancy of another workspace cannot prove this workspace transferred."""
        from sase.workspace_provider.occupant import (
            new_occupant_record,
            write_occupant_record,
        )
    
        repo = init_retention_repo(tmp_path / "ws", dirty=True)
        artifacts_dir, project_file = make_retention_monitor(
            repo, outcome="launched", protocol=MONITOR_CONTINUATION_PROTOCOL_LEGACY
        )
        meta = read_retention_meta(artifacts_dir)
        meta["monitor_followup_agent"] = "acme--mon@1"
        meta["project_file"] = project_file
        write_retention_meta(artifacts_dir, meta)
        persist_retention_delivery(
            artifacts_dir, meta, agent="acme--mon@1", disposition="acknowledged"
        )
        write_occupant_record(
            str(repo),
            new_occupant_record(
                pid=os.getpid() + 99,
                workflow="ace-run",
                project="proj",
                workspace_num=99,
                artifacts_timestamp="20260906120100",
                agent_name="acme--mon@1",
                cl_name="acme",
            ),
        )
        monkeypatch.setattr(
            "sase.monitor.settlement_fresh_owner._receiver_is_live",
            lambda *_args, **_kwargs: True,
        )
    
        error = release_monitor_claim(
            meta, project_name="proj", artifacts_dir=artifacts_dir
        )
    
>       assert error is None
E       assert "workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_... built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).)" is None

tests/monitor/test_monitor_retention_settlement.py:552: AssertionError
_______ test_settlement_still_not_launchable_when_starter_never_settles ________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_settlement_still_not_laun0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce094b90>

    def test_settlement_still_not_launchable_when_starter_never_settles(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Preserves today's behavior when the starter never settles at all."""
        monkeypatch.setattr(
            "sase.turns.followup.DEFAULT_STARTER_SETTLE_TIMEOUT_SECONDS", 0.05
        )
        monkeypatch.setattr("sase.turns.followup.STARTER_SETTLE_POLL_SECONDS", 0.01)
        _init_dirty_git_worktree(tmp_path)
    
        starter = tmp_path / "starter"
        starter.mkdir()
        (starter / "agent_meta.json").write_text(
            json.dumps({"name": "acme"}), encoding="utf-8"
        )
        artifacts_dir = _make_settlement_monitor(tmp_path, starter)
        meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        _publish_blocked_capture(artifacts_dir, meta)
        assert meta["continuation_capture_disposition"] == "needs_recovery"
        capture_errors = starter / "continuation" / "capture_errors.jsonl"
        capture_errors.parent.mkdir(parents=True, exist_ok=True)
        capture_errors.write_text(
            json.dumps(
                {
                    "stage": "agent_delta:interrupted",
                    "message": "validation: authored_local_request contains unsupported control characters",
                }
            )
            + "\n",
            encoding="utf-8",
        )
    
        def fake_launch(
            _artifacts_dir: str, _meta: dict[str, Any], **_kwargs: object
        ) -> FollowupLaunchResult:
            raise AssertionError("follow-up must not launch while blocked")
    
        result = settle_claim_and_followup(
            artifacts_dir,
            meta,
            monitor_state="completed",
            exit_code=0,
            elapsed_seconds=1.0,
            capture=OutputCapture(),
            timeout_kind=None,
            project_name="proj",
            launch_followup=fake_launch,
        )
    
        assert result.launch_result is not None
        assert result.launch_result.launched is False
        assert _MISSING_STARTER_PARENT_ERROR in str(result.launch_result.error)
        assert "starter acme continuation capture failed" in str(result.launch_result.error)
        assert "agent_delta:interrupted: validation: authored_local_request" in str(
            result.launch_result.error
        )
        assert "`sase monitor resume abc123 -k FILE`" in str(result.launch_result.error)
        assert "`sase monitor resume abc123 -m MODEL`" in str(result.launch_result.error)
        assert meta["monitor_followup_outcome"] == "not-launchable"
        assert meta["continuation_capture_error"] == _MISSING_STARTER_PARENT_ERROR
        assert meta["monitor_followup_error"] == result.launch_result.error
>       assert result.error == result.launch_result.error
E       AssertionError: assert 'workspace re...orce sase`).)' == 'monitor resu...123 -m MODEL`'
E         
E         - monitor result is missing its exact starter parent node; automatic dispatch is blocked pending recovery; starter acme continuation capture failed (agent_delta:interrupted: validation: authored_local_request contains unsupported control characters); recover with `sase monitor resume abc123 -k FILE` or `sase monitor resume abc123 -m MODEL`
E         + workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_workspace_retention'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this...
E         
E         ...Full output truncated (5 lines hidden), use '-vv' to show

tests/monitor/test_monitor_settlement_starter_race.py:271: AssertionError
________ test_start_monitor_promotes_a_bare_lane_and_runs_to_completion ________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_start_monitor_promotes_a_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcfc63d70>

    def test_start_monitor_promotes_a_bare_lane_and_runs_to_completion(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        project_file = write_project_file(
            "proj",
            running_claims=[WorkspaceClaim(3, "ace-run", "acme", pid=os.getpid())],
        )
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=3,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
    
        request = StartMonitorRequest(
            command="true",
            reason="verify",
            timeout_seconds=30.0,
            idle_timeout_seconds=10.0,
            cwd=str(tmp_path),
            project_name="proj",
            start_status="MONITORING",
            stop_status="MONITORED",
            lane="acme",
        )
    
        record = start_monitor(request)
    
        assert record.monitor_state == "running"
        assert record.member_agent_name == "acme--mon"
        assert record.lane == "acme"
        assert record.idle_timeout_seconds == 10.0
    
        # The starter is now a promoted agent-session root.
        starter_meta = json.loads((Path(starter_dir) / "agent_meta.json").read_text())
        assert starter_meta["agent_session"] == "acme"
        assert "agent_family" not in starter_meta
        assert starter_meta["name"] == "acme--0"
    
        done = wait_for_done(record.artifacts_dir)
        assert done["monitor_state"] == "completed"
        assert done["monitor_exit_code"] == 0
    
        # No next action: the transferred claim is released once the command
        # finishes.
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=3, workflow='ace-monitor', cl_name='acme', pid=3107576, artifacts_timestamp='20261103114248', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_start.py:160: AssertionError
___ test_start_monitor_epic_launch_from_non_numbered_cwd_uses_workspace_zero ___

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_start_monitor_epic_launch0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd12b3080>

    def test_start_monitor_epic_launch_from_non_numbered_cwd_uses_workspace_zero(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        primary = tmp_path / "primary"
        primary.mkdir()
        outside = tmp_path / "outside"
        outside.mkdir()
        project_file = write_project_file("proj", workspace_dir=str(primary))
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--0",
            agent_session="acme",
            model="claude-sonnet-5",
            workspace_dir=str(primary),
            workspace_num=0,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
    
        record = start_monitor(
            StartMonitorRequest(
                command="true",
                reason="verify non-numbered cwd",
                timeout_seconds=30.0,
                cwd=str(outside),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
                inherit_lane_workspace_claim=False,
            )
        )
    
        meta = json.loads((Path(record.artifacts_dir) / "agent_meta.json").read_text())
        assert meta["workspace_num"] == 0
        assert meta["workspace_dir"] == str(outside)
        wait_for_done(record.artifacts_dir)
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=0, workflow='ace-monitor', cl_name='acme', pid=3116658, artifacts_timestamp='20261103114302', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_start.py:568: AssertionError
_________________ test_adoption_waits_for_finalizer_settlement _________________

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
>           return getattr(module, name)
                   ^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase_core_rs' has no attribute 'recovery_adoption_lock_filename'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:69: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_adoption_waits_for_finali0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd1c90530>

    def test_adoption_waits_for_finalizer_settlement(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """The monitor check cannot launch before the commit finalizer settles."""
        from sase.axe.run_agent_exec_staged import dispatch_completed_staged_handoff
        from sase.axe.run_agent_exec_staged import StagedInlineContinuation
        from sase.agent.staged_handoff import write_staged_handoff
        from tests._axe_run_agent_exec_helpers import make_exec_ctx
        from sase.axe.run_agent_exec import LoopState
    
        staged_id = "aaaaaaaa-bbbb-4ccc-8ddd-eeeeeeeeeeee"
        monkeypatch.setenv("SASE_AGENT", "agent")
        monkeypatch.setenv("SASE_AGENT_NAME", "agent")
        ctx = make_exec_ctx(tmp_path, is_home_mode=False)
        artifacts = Path(ctx.artifacts_dir)
        monkeypatch.setenv("SASE_ARTIFACTS_DIR", str(artifacts))
        state = LoopState(
            current_prompt="p",
            current_role_suffix="",
            current_artifacts_dir=str(artifacts),
            loop_outcome="completed",
            sdd_spec_path=None,
            original_prompt="p",
        )
        record = {
            "schema_version": 1,
            "staged_id": staged_id,
            "kind": "monitor",
            "created_at": "2026-10-26T12:00:00Z",
            "payload": {"monitor_id": "monitor-1"},
            "successor_workspace": "inherit",
            "carry_allowed": True,
            "dirty_obligations_at_stage": [],
        }
        write_staged_handoff(record, artifacts_dir=str(artifacts))
        _write_agent_meta(artifacts)
        # Unsettled finalizer: adoption is held and no proc launches.
        (artifacts / "finalizer_result.json").write_text(
            json.dumps({"status": "running", "instances": []}), encoding="utf-8"
        )
        launches: list[str] = []
        monkeypatch.setattr(
            "sase.monitor.staged_owner.read_staged_owner_index",
            lambda monitor_id: {
                "staged_id": staged_id,
                "artifacts_dir": str(tmp_path / "m"),
            },
        )
    
        monkeypatch.setattr(
            "sase.axe.run_agent_exec_monitor.capture_monitor_handoff",
            lambda *_args, **_kwargs: SimpleNamespace(node_id="starter-node-1"),
        )
        monkeypatch.setattr(
            "sase.monitor.start_stage.launch_from_persisted_payload",
            lambda member_dir, **_kwargs: (
                launches.append(member_dir)
                or SimpleNamespace(monitor_id="m", artifacts_dir=member_dir)
            ),
        )
>       dispatch = dispatch_completed_staged_handoff(
            str(artifacts), StagedInlineContinuation(ctx=ctx, state=state)
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/monitor/test_monitor_start_activation.py:439: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/run_agent_exec_staged_dispatch.py:471: in dispatch_completed_staged_handoff
    with acquire_adoption_lock(Path(artifacts_dir)):
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/_staged_handoff_recovery.py:83: in acquire_adoption_lock
    adoption_filename = recovery_adoption_lock_filename()
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/staged_handoff.py:187: in recovery_adoption_lock_filename
    binding = require_rust_binding("recovery_adoption_lock_filename")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
            return getattr(module, name)
        except AttributeError as exc:
>           raise AttributeError(
                f"{RUST_EXTENSION_MODULE_NAME} is importable but does not expose "
                f"binding {name!r}; the installed wheel is stale or was built "
                f"without the shipped bindings. {_install_hint().capitalize()}."
            ) from exc
E           AttributeError: sase_core_rs is importable but does not expose binding 'recovery_adoption_lock_filename'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:71: AttributeError
__ test_failed_finalization_releases_monitor_resources_and_keeps_stage[owned] __

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
>           return getattr(module, name)
                   ^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase_core_rs' has no attribute 'recovery_adoption_lock_filename'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:69: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_failed_finalization_relea0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd186a660>
resource = 'owned'

    @pytest.mark.parametrize("resource", ["owned", "joined", "prepared"])
    def test_failed_finalization_releases_monitor_resources_and_keeps_stage(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch, resource: str
    ) -> None:
        from unittest.mock import Mock
    
        from sase.axe.run_agent_exec_staged import (
            StagedInlineContinuation,
            dispatch_completed_staged_handoff,
        )
        from sase.monitor.staged_owner import read_staged_owner_index
        from tests.staged_handoff_acceptance_helpers import make_continuation
    
        root = sandbox_project(tmp_path)
        if resource == "prepared":
            (root / "sase" / "sase.yml").write_text(
                SANDBOX_CATALOG.replace('["true"]', '["just", "check"]'),
                encoding="utf-8",
            )
        monkeypatch.setattr(
            "sase.monitor.start_prepare.get_monitor_tool_wrap", lambda: "verify"
        )
        dirs = stage_env(tmp_path, monkeypatch, cwd=str(root), workspace_dir=str(root))
        joined_run = (
            reserve_detached_run("--", "true", agent="acme")
            if resource == "joined"
            else None
        )
        prepared = (
            persist_prepared_completion(
                sealed_intent(["just", "check"]), artifacts_dir=dirs[0]
            )
            if resource == "prepared"
            else None
        )
        staged = stage_monitor(
            stage_request(
                tmp_path,
                cwd=str(root),
                command="just check" if prepared else "true",
                join_run_id=joined_run,
                profile="verify" if resource != "joined" else None,
                completion_ref=prepared.intent_ref if prepared else None,
            )
        )
        dirs.append(staged.record.artifacts_dir)
        starter = Path(dirs[0])
        before = read_staged_handoff(dirs[0])
        (starter / "finalizer_result.json").write_text(
            json.dumps({"status": "failed", "instances": []}), encoding="utf-8"
        )
        submit = Mock(side_effect=AssertionError("held monitor must not launch"))
        monkeypatch.setattr("sase.monitor.start_launch.submit_proc_request", submit)
        continuation = StagedInlineContinuation(*make_continuation(tmp_path, starter))
    
>       result = dispatch_completed_staged_handoff(dirs[0], continuation)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/monitor/test_monitor_start_stage_cleanup.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/run_agent_exec_staged_dispatch.py:471: in dispatch_completed_staged_handoff
    with acquire_adoption_lock(Path(artifacts_dir)):
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/_staged_handoff_recovery.py:83: in acquire_adoption_lock
    adoption_filename = recovery_adoption_lock_filename()
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/staged_handoff.py:187: in recovery_adoption_lock_filename
    binding = require_rust_binding("recovery_adoption_lock_filename")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
            return getattr(module, name)
        except AttributeError as exc:
>           raise AttributeError(
                f"{RUST_EXTENSION_MODULE_NAME} is importable but does not expose "
                f"binding {name!r}; the installed wheel is stale or was built "
                f"without the shipped bindings. {_install_hint().capitalize()}."
            ) from exc
E           AttributeError: sase_core_rs is importable but does not expose binding 'recovery_adoption_lock_filename'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:71: AttributeError
_ test_failed_finalization_releases_monitor_resources_and_keeps_stage[joined] __

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
>           return getattr(module, name)
                   ^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase_core_rs' has no attribute 'recovery_adoption_lock_filename'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:69: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_failed_finalization_relea1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd1868200>
resource = 'joined'

    @pytest.mark.parametrize("resource", ["owned", "joined", "prepared"])
    def test_failed_finalization_releases_monitor_resources_and_keeps_stage(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch, resource: str
    ) -> None:
        from unittest.mock import Mock
    
        from sase.axe.run_agent_exec_staged import (
            StagedInlineContinuation,
            dispatch_completed_staged_handoff,
        )
        from sase.monitor.staged_owner import read_staged_owner_index
        from tests.staged_handoff_acceptance_helpers import make_continuation
    
        root = sandbox_project(tmp_path)
        if resource == "prepared":
            (root / "sase" / "sase.yml").write_text(
                SANDBOX_CATALOG.replace('["true"]', '["just", "check"]'),
                encoding="utf-8",
            )
        monkeypatch.setattr(
            "sase.monitor.start_prepare.get_monitor_tool_wrap", lambda: "verify"
        )
        dirs = stage_env(tmp_path, monkeypatch, cwd=str(root), workspace_dir=str(root))
        joined_run = (
            reserve_detached_run("--", "true", agent="acme")
            if resource == "joined"
            else None
        )
        prepared = (
            persist_prepared_completion(
                sealed_intent(["just", "check"]), artifacts_dir=dirs[0]
            )
            if resource == "prepared"
            else None
        )
        staged = stage_monitor(
            stage_request(
                tmp_path,
                cwd=str(root),
                command="just check" if prepared else "true",
                join_run_id=joined_run,
                profile="verify" if resource != "joined" else None,
                completion_ref=prepared.intent_ref if prepared else None,
            )
        )
        dirs.append(staged.record.artifacts_dir)
        starter = Path(dirs[0])
        before = read_staged_handoff(dirs[0])
        (starter / "finalizer_result.json").write_text(
            json.dumps({"status": "failed", "instances": []}), encoding="utf-8"
        )
        submit = Mock(side_effect=AssertionError("held monitor must not launch"))
        monkeypatch.setattr("sase.monitor.start_launch.submit_proc_request", submit)
        continuation = StagedInlineContinuation(*make_continuation(tmp_path, starter))
    
>       result = dispatch_completed_staged_handoff(dirs[0], continuation)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/monitor/test_monitor_start_stage_cleanup.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/run_agent_exec_staged_dispatch.py:471: in dispatch_completed_staged_handoff
    with acquire_adoption_lock(Path(artifacts_dir)):
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/_staged_handoff_recovery.py:83: in acquire_adoption_lock
    adoption_filename = recovery_adoption_lock_filename()
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/staged_handoff.py:187: in recovery_adoption_lock_filename
    binding = require_rust_binding("recovery_adoption_lock_filename")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
            return getattr(module, name)
        except AttributeError as exc:
>           raise AttributeError(
                f"{RUST_EXTENSION_MODULE_NAME} is importable but does not expose "
                f"binding {name!r}; the installed wheel is stale or was built "
                f"without the shipped bindings. {_install_hint().capitalize()}."
            ) from exc
E           AttributeError: sase_core_rs is importable but does not expose binding 'recovery_adoption_lock_filename'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:71: AttributeError
_ test_failed_finalization_releases_monitor_resources_and_keeps_stage[prepared] _

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
>           return getattr(module, name)
                   ^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase_core_rs' has no attribute 'recovery_adoption_lock_filename'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:69: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_failed_finalization_relea2')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce8f7fe0>
resource = 'prepared'

    @pytest.mark.parametrize("resource", ["owned", "joined", "prepared"])
    def test_failed_finalization_releases_monitor_resources_and_keeps_stage(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch, resource: str
    ) -> None:
        from unittest.mock import Mock
    
        from sase.axe.run_agent_exec_staged import (
            StagedInlineContinuation,
            dispatch_completed_staged_handoff,
        )
        from sase.monitor.staged_owner import read_staged_owner_index
        from tests.staged_handoff_acceptance_helpers import make_continuation
    
        root = sandbox_project(tmp_path)
        if resource == "prepared":
            (root / "sase" / "sase.yml").write_text(
                SANDBOX_CATALOG.replace('["true"]', '["just", "check"]'),
                encoding="utf-8",
            )
        monkeypatch.setattr(
            "sase.monitor.start_prepare.get_monitor_tool_wrap", lambda: "verify"
        )
        dirs = stage_env(tmp_path, monkeypatch, cwd=str(root), workspace_dir=str(root))
        joined_run = (
            reserve_detached_run("--", "true", agent="acme")
            if resource == "joined"
            else None
        )
        prepared = (
            persist_prepared_completion(
                sealed_intent(["just", "check"]), artifacts_dir=dirs[0]
            )
            if resource == "prepared"
            else None
        )
        staged = stage_monitor(
            stage_request(
                tmp_path,
                cwd=str(root),
                command="just check" if prepared else "true",
                join_run_id=joined_run,
                profile="verify" if resource != "joined" else None,
                completion_ref=prepared.intent_ref if prepared else None,
            )
        )
        dirs.append(staged.record.artifacts_dir)
        starter = Path(dirs[0])
        before = read_staged_handoff(dirs[0])
        (starter / "finalizer_result.json").write_text(
            json.dumps({"status": "failed", "instances": []}), encoding="utf-8"
        )
        submit = Mock(side_effect=AssertionError("held monitor must not launch"))
        monkeypatch.setattr("sase.monitor.start_launch.submit_proc_request", submit)
        continuation = StagedInlineContinuation(*make_continuation(tmp_path, starter))
    
>       result = dispatch_completed_staged_handoff(dirs[0], continuation)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/monitor/test_monitor_start_stage_cleanup.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/run_agent_exec_staged_dispatch.py:471: in dispatch_completed_staged_handoff
    with acquire_adoption_lock(Path(artifacts_dir)):
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/_staged_handoff_recovery.py:83: in acquire_adoption_lock
    adoption_filename = recovery_adoption_lock_filename()
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/staged_handoff.py:187: in recovery_adoption_lock_filename
    binding = require_rust_binding("recovery_adoption_lock_filename")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
            return getattr(module, name)
        except AttributeError as exc:
>           raise AttributeError(
                f"{RUST_EXTENSION_MODULE_NAME} is importable but does not expose "
                f"binding {name!r}; the installed wheel is stale or was built "
                f"without the shipped bindings. {_install_hint().capitalize()}."
            ) from exc
E           AttributeError: sase_core_rs is importable but does not expose binding 'recovery_adoption_lock_filename'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:71: AttributeError
________ test_staged_monitor_waits_for_real_finalizer_controller[False] ________

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
>           return getattr(module, name)
                   ^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase_core_rs' has no attribute 'recovery_adoption_lock_filename'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:69: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_staged_monitor_waits_for_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd1037d40>
fail_fix = False

    @pytest.mark.parametrize("fail_fix", [False, True])
    def test_staged_monitor_waits_for_real_finalizer_controller(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        fail_fix: bool,
    ) -> None:
        import os
        from dataclasses import replace
    
        from sase.agent.staged_handoff import write_staged_handoff_response
        from sase.axe.run_agent_exec import LoopState
        from sase.axe.run_agent_exec_staged import (
            StagedInlineContinuation,
            dispatch_completed_staged_handoff,
        )
        from sase.core.tool_run import tool_run_show
        from sase.finalizers.plan import resolve_and_persist_finalizer_plan
        from sase.macro.directives import PromptDirectives
        from tests._axe_run_agent_exec_helpers import make_exec_ctx
        from tests.finalizers_live_e2e_test_helpers import (
            command_instance,
            commit_instance,
            config_for,
            use_config,
        )
        from tests.finalizers_protocol_harness_test_helpers import (
            dirty_repo,
            prepare_agent_env,
            run_controller,
        )
        from tests.staged_handoff_acceptance_helpers import patch_dirty_for_settlement
    
        root = sandbox_project(tmp_path)
        monkeypatch.setattr(
            "sase.monitor.start_prepare.get_monitor_tool_wrap", lambda: "verify"
        )
        dirs = stage_env(
            tmp_path,
            monkeypatch,
            cwd=str(root),
            workspace_dir=str(root),
            starter_workspace_dir=str(root),
        )
        starter_dir = Path(dirs[0])
        prepare_agent_env(monkeypatch, starter_dir, root)
        monkeypatch.setenv("SASE_AGENT_TIMESTAMP", "20260812120000")
        monkeypatch.setenv("SASE_AGENT_NAME", "acme")
    
        fake_bin = tmp_path / "fake-bin"
        fake_bin.mkdir()
        events_path = tmp_path / "finalizer-events"
        fake_just = fake_bin / "just"
        fake_just.write_text(
            "#!/bin/sh\n"
            'printf \'%s\\n\' "$1" >> "$SASE_FINALIZER_EVENTS"\n'
            '[ "${SASE_FINALIZER_FAIL:-}" != "$1" ]\n',
            encoding="utf-8",
        )
        fake_just.chmod(0o755)
        monkeypatch.setenv("PATH", f"{fake_bin}{os.pathsep}{os.environ['PATH']}")
        monkeypatch.setenv("SASE_FINALIZER_EVENTS", str(events_path))
        if fail_fix:
            monkeypatch.setenv("SASE_FINALIZER_FAIL", "fix")
        else:
            monkeypatch.delenv("SASE_FINALIZER_FAIL", raising=False)
    
        def observed_command(
            instance_id: str,
            command: list[str],
            *,
            after: tuple[str, ...] = (),
        ) -> Any:
            instance = command_instance(instance_id, command, after=after)
            return replace(
                instance,
                config={
                    **instance.config,
                    "env": ["SASE_FINALIZER_EVENTS", "SASE_FINALIZER_FAIL"],
                },
            )
    
        config = config_for(
            {
                "fix": observed_command("fix", ["just", "fix"]),
                "commit": replace(commit_instance(), after=("fix",), refusal="defer"),
                "audit": observed_command("audit", ["just", "audit"], after=("commit",)),
            },
            ("fix", "commit", "audit"),
        )
        use_config(monkeypatch, config)
        dirty = {"repos": (dirty_repo(root),)}
        patch_dirty_for_settlement(monkeypatch, root, dirty)
    
        staged = stage_monitor(
            stage_request(
                tmp_path,
                cwd=str(root),
                profile="verify",
            )
        )
        dirs.append(staged.record.artifacts_dir)
        write_staged_handoff_response(
            staged.staged_id,
            "The provider's real final response.",
            artifacts_dir=str(starter_dir),
        )
        resolve_and_persist_finalizer_plan(
            PromptDirectives(), artifacts_dir=str(starter_dir)
        )
    
        original_meta = json.loads((starter_dir / "agent_meta.json").read_text())
        ctx = replace(
            make_exec_ctx(tmp_path, is_home_mode=False),
            artifacts_dir=str(starter_dir),
            agent_name="acme",
            agent_meta=original_meta,
            project_name="proj",
        )
        state = LoopState(
            current_prompt="Run the staged verification.",
            current_role_suffix="",
            current_artifacts_dir=str(starter_dir),
            loop_outcome="completed",
            sdd_spec_path=None,
            original_prompt="Run the staged verification.",
        )
        continuation = StagedInlineContinuation(ctx=ctx, state=state)
        launches: list[str] = []
    
        def fake_launch(context: Any, timer: Any) -> Any:
            del timer
            assert events_path.read_text(encoding="utf-8").splitlines() == (
                ["fix"] if fail_fix else ["fix", "audit"]
            )
            launches.append("launch")
            return staged.record
    
        monkeypatch.setattr("sase.monitor.start_stage_adopt.launch_monitor", fake_launch)
    
        if fail_fix:
            with pytest.raises(RuntimeError, match="failed on attempt"):
                run_controller(starter_dir)
            assert events_path.read_text(encoding="utf-8").splitlines() == ["fix"]
        else:
            result = run_controller(starter_dir)
            assert result.content == "done"
            assert events_path.read_text(encoding="utf-8").splitlines() == [
                "fix",
                "audit",
            ]
            accepted = json.loads(
                (starter_dir / "final_submission.json").read_text(encoding="utf-8")
            )
            assert accepted["synthesized"]["kind"] == "handoff_carry"
            assert accepted["synthesized"]["source"] == "host"
    
>       dispatch = dispatch_completed_staged_handoff(str(starter_dir), continuation)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/monitor/test_monitor_start_stage_prepared.py:201: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/run_agent_exec_staged_dispatch.py:471: in dispatch_completed_staged_handoff
    with acquire_adoption_lock(Path(artifacts_dir)):
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/_staged_handoff_recovery.py:83: in acquire_adoption_lock
    adoption_filename = recovery_adoption_lock_filename()
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/staged_handoff.py:187: in recovery_adoption_lock_filename
    binding = require_rust_binding("recovery_adoption_lock_filename")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
            return getattr(module, name)
        except AttributeError as exc:
>           raise AttributeError(
                f"{RUST_EXTENSION_MODULE_NAME} is importable but does not expose "
                f"binding {name!r}; the installed wheel is stale or was built "
                f"without the shipped bindings. {_install_hint().capitalize()}."
            ) from exc
E           AttributeError: sase_core_rs is importable but does not expose binding 'recovery_adoption_lock_filename'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:71: AttributeError
________ test_staged_monitor_waits_for_real_finalizer_controller[True] _________

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
>           return getattr(module, name)
                   ^^^^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase_core_rs' has no attribute 'recovery_adoption_lock_filename'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:69: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_staged_monitor_waits_for_1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce2fa5d0>
fail_fix = True

    @pytest.mark.parametrize("fail_fix", [False, True])
    def test_staged_monitor_waits_for_real_finalizer_controller(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        fail_fix: bool,
    ) -> None:
        import os
        from dataclasses import replace
    
        from sase.agent.staged_handoff import write_staged_handoff_response
        from sase.axe.run_agent_exec import LoopState
        from sase.axe.run_agent_exec_staged import (
            StagedInlineContinuation,
            dispatch_completed_staged_handoff,
        )
        from sase.core.tool_run import tool_run_show
        from sase.finalizers.plan import resolve_and_persist_finalizer_plan
        from sase.macro.directives import PromptDirectives
        from tests._axe_run_agent_exec_helpers import make_exec_ctx
        from tests.finalizers_live_e2e_test_helpers import (
            command_instance,
            commit_instance,
            config_for,
            use_config,
        )
        from tests.finalizers_protocol_harness_test_helpers import (
            dirty_repo,
            prepare_agent_env,
            run_controller,
        )
        from tests.staged_handoff_acceptance_helpers import patch_dirty_for_settlement
    
        root = sandbox_project(tmp_path)
        monkeypatch.setattr(
            "sase.monitor.start_prepare.get_monitor_tool_wrap", lambda: "verify"
        )
        dirs = stage_env(
            tmp_path,
            monkeypatch,
            cwd=str(root),
            workspace_dir=str(root),
            starter_workspace_dir=str(root),
        )
        starter_dir = Path(dirs[0])
        prepare_agent_env(monkeypatch, starter_dir, root)
        monkeypatch.setenv("SASE_AGENT_TIMESTAMP", "20260812120000")
        monkeypatch.setenv("SASE_AGENT_NAME", "acme")
    
        fake_bin = tmp_path / "fake-bin"
        fake_bin.mkdir()
        events_path = tmp_path / "finalizer-events"
        fake_just = fake_bin / "just"
        fake_just.write_text(
            "#!/bin/sh\n"
            'printf \'%s\\n\' "$1" >> "$SASE_FINALIZER_EVENTS"\n'
            '[ "${SASE_FINALIZER_FAIL:-}" != "$1" ]\n',
            encoding="utf-8",
        )
        fake_just.chmod(0o755)
        monkeypatch.setenv("PATH", f"{fake_bin}{os.pathsep}{os.environ['PATH']}")
        monkeypatch.setenv("SASE_FINALIZER_EVENTS", str(events_path))
        if fail_fix:
            monkeypatch.setenv("SASE_FINALIZER_FAIL", "fix")
        else:
            monkeypatch.delenv("SASE_FINALIZER_FAIL", raising=False)
    
        def observed_command(
            instance_id: str,
            command: list[str],
            *,
            after: tuple[str, ...] = (),
        ) -> Any:
            instance = command_instance(instance_id, command, after=after)
            return replace(
                instance,
                config={
                    **instance.config,
                    "env": ["SASE_FINALIZER_EVENTS", "SASE_FINALIZER_FAIL"],
                },
            )
    
        config = config_for(
            {
                "fix": observed_command("fix", ["just", "fix"]),
                "commit": replace(commit_instance(), after=("fix",), refusal="defer"),
                "audit": observed_command("audit", ["just", "audit"], after=("commit",)),
            },
            ("fix", "commit", "audit"),
        )
        use_config(monkeypatch, config)
        dirty = {"repos": (dirty_repo(root),)}
        patch_dirty_for_settlement(monkeypatch, root, dirty)
    
        staged = stage_monitor(
            stage_request(
                tmp_path,
                cwd=str(root),
                profile="verify",
            )
        )
        dirs.append(staged.record.artifacts_dir)
        write_staged_handoff_response(
            staged.staged_id,
            "The provider's real final response.",
            artifacts_dir=str(starter_dir),
        )
        resolve_and_persist_finalizer_plan(
            PromptDirectives(), artifacts_dir=str(starter_dir)
        )
    
        original_meta = json.loads((starter_dir / "agent_meta.json").read_text())
        ctx = replace(
            make_exec_ctx(tmp_path, is_home_mode=False),
            artifacts_dir=str(starter_dir),
            agent_name="acme",
            agent_meta=original_meta,
            project_name="proj",
        )
        state = LoopState(
            current_prompt="Run the staged verification.",
            current_role_suffix="",
            current_artifacts_dir=str(starter_dir),
            loop_outcome="completed",
            sdd_spec_path=None,
            original_prompt="Run the staged verification.",
        )
        continuation = StagedInlineContinuation(ctx=ctx, state=state)
        launches: list[str] = []
    
        def fake_launch(context: Any, timer: Any) -> Any:
            del timer
            assert events_path.read_text(encoding="utf-8").splitlines() == (
                ["fix"] if fail_fix else ["fix", "audit"]
            )
            launches.append("launch")
            return staged.record
    
        monkeypatch.setattr("sase.monitor.start_stage_adopt.launch_monitor", fake_launch)
    
        if fail_fix:
            with pytest.raises(RuntimeError, match="failed on attempt"):
                run_controller(starter_dir)
            assert events_path.read_text(encoding="utf-8").splitlines() == ["fix"]
        else:
            result = run_controller(starter_dir)
            assert result.content == "done"
            assert events_path.read_text(encoding="utf-8").splitlines() == [
                "fix",
                "audit",
            ]
            accepted = json.loads(
                (starter_dir / "final_submission.json").read_text(encoding="utf-8")
            )
            assert accepted["synthesized"]["kind"] == "handoff_carry"
            assert accepted["synthesized"]["source"] == "host"
    
>       dispatch = dispatch_completed_staged_handoff(str(starter_dir), continuation)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/monitor/test_monitor_start_stage_prepared.py:201: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/run_agent_exec_staged_dispatch.py:471: in dispatch_completed_staged_handoff
    with acquire_adoption_lock(Path(artifacts_dir)):
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/_staged_handoff_recovery.py:83: in acquire_adoption_lock
    adoption_filename = recovery_adoption_lock_filename()
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/staged_handoff.py:187: in recovery_adoption_lock_filename
    binding = require_rust_binding("recovery_adoption_lock_filename")
              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'recovery_adoption_lock_filename'

    def require_rust_binding(name: str) -> Any:
        """Return ``sase_core_rs.<name>`` or raise with operation-specific text.
    
        Raises:
            ImportError: when the extension module itself is not importable
                (delegated to :func:`require_rust_extension`).
            AttributeError: when the extension is importable but does not
                expose the requested binding. This typically means the wheel
                is too old or was built without the shipped bindings.
        """
        module = require_rust_extension()
        try:
            return getattr(module, name)
        except AttributeError as exc:
>           raise AttributeError(
                f"{RUST_EXTENSION_MODULE_NAME} is importable but does not expose "
                f"binding {name!r}; the installed wheel is stale or was built "
                f"without the shipped bindings. {_install_hint().capitalize()}."
            ) from exc
E           AttributeError: sase_core_rs is importable but does not expose binding 'recovery_adoption_lock_filename'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py:71: AttributeError
__ test_dead_supervisor_reconciliation_kills_tree_releases_claim_and_settles ___

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_dead_supervisor_reconcili0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce2f8f20>

    def test_dead_supervisor_reconciliation_kills_tree_releases_claim_and_settles(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        import sase.monitor.reconcile as reconcile_module
    
        child = subprocess.Popen(
            ["sh", "-c", "trap '' TERM; sleep 30 & wait"],
            start_new_session=True,
        )
        workspace = tmp_path / "plain"
        workspace.mkdir()
        project_file = write_project_file(
            "proj",
            running_claims=[
                WorkspaceClaim(
                    workspace_num=0,
                    workflow=MONITOR_WORKSPACE_CLAIM_WORKFLOW,
                    cl_name="acme",
                    pid=DEAD_PID,
                    artifacts_timestamp="20260812120000",
                )
            ],
        )
        monitor_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--mon",
            agent_session="acme",
            agent_session_role="monitor",
            monitor_id="aaa",
            monitor_state="running",
            monitor_command="sleep 60",
            monitor_stop_status="MONITORED",
            monitor_pgid=child.pid,
            pid=DEAD_PID,
            workspace_num=0,
            workspace_dir=str(workspace),
            cl_name="acme",
        )
        (Path(monitor_dir) / "live_reply.md").write_text("before crash\n")
        patch_project_records(monkeypatch, [monitor_dir])
        monkeypatch.setattr(reconcile_module, "_RECONCILE_KILL_GRACE_SECONDS", 0.05)
    
        try:
            record = MonitorRecord.from_record(record_from_disk(monitor_dir))
    
            result = stop_monitor(record)
    
            assert result.monitor_state == "failed"
            assert result.settled is True
>           assert get_claimed_workspaces(project_file) == []
E           AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E             
E             Left contains one more item: WorkspaceClaim(workspace_num=0, workflow='ace-monitor', cl_name='acme', pid=99999999, artifacts_timestamp='20260812120000', pinned=False, suffix_fields=())
E             Use -v to get more diff

tests/monitor/test_monitor_store_reconcile.py:90: AssertionError
____ test_pre_reboot_monitor_reconciles_to_lost_without_followup_or_signal _____

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_pre_reboot_monitor_reconc0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bcf51bc80>

    def test_pre_reboot_monitor_reconciles_to_lost_without_followup_or_signal(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        import sase.monitor.reconcile as reconcile_module
        from sase.monitor.settlement import LOST_FOLLOWUP_ERROR
    
        workspace = tmp_path / "plain"
        workspace.mkdir()
        project_file = write_project_file(
            "proj",
            running_claims=[
                WorkspaceClaim(
                    workspace_num=0,
                    workflow=MONITOR_WORKSPACE_CLAIM_WORKFLOW,
                    cl_name="acme",
                    pid=DEAD_PID,
                    artifacts_timestamp="20260812120000",
                )
            ],
        )
        monitor_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--mon",
            agent_session="acme",
            agent_session_role="monitor",
            monitor_id="aaa",
            monitor_state="running",
            monitor_command="just check-full",
            monitor_stop_status="MONITORED",
            monitor_next_action="fix the failure",
            monitor_supervisor_identity="old-boot:123",
            monitor_pgid=12345,
            pid=DEAD_PID,
            workspace_num=0,
            workspace_dir=str(workspace),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [monitor_dir])
        signaled: list[tuple[int, int]] = []
        monkeypatch.setattr(reconcile_module, "_current_boot_id", lambda: "new-boot")
        monkeypatch.setattr(
            os,
            "killpg",
            lambda pgid, sig: signaled.append((pgid, sig)),
        )
    
        record = MonitorRecord.from_record(record_from_disk(monitor_dir))
        result = stop_monitor(record)
    
        assert result.monitor_state == "lost"
        assert result.status_bucket == "Failed"
        assert signaled == []
        done = json.loads((Path(monitor_dir) / "done.json").read_text())
        assert done["monitor_state"] == "lost"
>       assert done["monitor_followup_error"] == LOST_FOLLOWUP_ERROR
E       assert 'workspace re...orce sase`).)' == 'follow-up no...me is unknown'
E         
E         - follow-up not launched because the monitor command outcome is unknown
E         + workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_workspace_retention'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).; ecide_workspace_retention")
E         +               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E         +   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py", line 71, in require_...
E         
E         ...Full output truncated (3 lines hidden), use '-vv' to show

tests/monitor/test_monitor_store_reconcile.py:362: AssertionError
____ test_run_supervisor_records_a_clean_completion_and_releases_the_claim _____

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_run_supervisor_records_a_0')

    def test_run_supervisor_records_a_clean_completion_and_releases_the_claim(
        tmp_path: Path,
    ) -> None:
        artifacts_dir, project_file = _make_member(tmp_path, command="echo hello world")
    
        exit_status = run_supervisor(artifacts_dir)
    
        assert exit_status == 0
        meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        assert meta["monitor_state"] == "completed"
        assert meta["monitor_exit_code"] == 0
        assert meta["monitor_output_truncated"] is False
        assert meta["monitor_output_path"] == str(Path(artifacts_dir) / "live_reply.md")
        assert meta["run_started_at"]
    
        done = json.loads((Path(artifacts_dir) / "done.json").read_text())
        assert done["outcome"] == "monitored"
        assert done["monitor_state"] == "completed"
        assert done["monitor_exit_code"] == 0
        assert done["status_label"] == "MONITORED"
        assert done["response_path"]
        assert isinstance(done["finished_at"], int | float)
    
        live_reply = (Path(artifacts_dir) / "live_reply.md").read_text()
        assert "hello world" in live_reply
    
        # No next action: the claim taken in _make_member is released.
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260812120000', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_supervise.py:113: AssertionError
_____________ test_run_supervisor_fails_without_the_launch_barrier _____________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_run_supervisor_fails_with0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce0f8440>

    def test_run_supervisor_fails_without_the_launch_barrier(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        import sase.monitor.supervise as supervise_module
    
        sentinel = tmp_path / "command-ran"
        monkeypatch.setattr(supervise_module, "MONITOR_LAUNCH_BARRIER_TIMEOUT_SECONDS", 0.1)
        artifacts_dir, project_file = _make_member(
            tmp_path,
            command=f"touch {sentinel}",
            timeout_seconds=30.0,
            go_barrier=False,
        )
    
        exit_status = run_supervisor(artifacts_dir)
    
        assert exit_status == 1
        assert not sentinel.exists()
        meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        assert meta["monitor_state"] == "failed"
        assert meta["monitor_settled"] is True
        # Written as soon as the log is opened, before the barrier wait -- unlike
        # run_started_at, which only appears once the command actually spawns.
        assert meta["monitor_output_path"] == str(Path(artifacts_dir) / "live_reply.md")
        assert "run_started_at" not in meta
        done = json.loads((Path(artifacts_dir) / "done.json").read_text())
        assert done["monitor_state"] == "failed"
        assert "command was not run" in done["error"]
>       assert get_claimed_workspaces(project_file) == []
E       AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E         
E         Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260812120000', pinned=False, suffix_fields=())
E         Use -v to get more diff

tests/monitor/test_monitor_supervise.py:200: AssertionError
___ test_run_supervisor_records_degraded_followup_and_releases_monitor_claim ___

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_run_supervisor_records_de0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bce072270>

    def test_run_supervisor_records_degraded_followup_and_releases_monitor_claim(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        artifacts_dir, project_file = _make_member(
            tmp_path, command="true", next_action="Report that it finished."
        )
        followup_dir = tmp_path / "followup"
        followup_dir.mkdir()
        import sase.monitor.supervise as supervise_module
    
        wait_calls: list[tuple[str, int | None]] = []
    
        def fake_launch_degraded(
            _artifacts_dir: str, meta: dict[str, object], **_kwargs: object
        ) -> FollowupLaunchResult:
            meta["monitor_followup_agent"] = "acme--1"
            return FollowupLaunchResult(
                launched=True,
                degraded_reason="fresh claim on the same workspace",
                agent_name="acme--1",
                artifacts_dir=str(followup_dir),
                pid=456,
            )
    
        def fake_wait(artifacts_dir_arg: str, pid: int | None) -> bool:
            wait_calls.append((artifacts_dir_arg, pid))
            return True
    
        monkeypatch.setattr(supervise_module, "launch_followup_agent", fake_launch_degraded)
        monkeypatch.setattr(supervise_module, "wait_for_followup_started", fake_wait)
    
        run_supervisor(artifacts_dir)
    
        meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        assert wait_calls == [(str(followup_dir), 456)]
        assert meta["monitor_followup_outcome"] == "launched-degraded"
        assert meta["monitor_followup_degraded_reason"] == (
            "fresh claim on the same workspace"
        )
        done = json.loads((Path(artifacts_dir) / "done.json").read_text())
        assert done["monitor_followup_outcome"] == "launched-degraded"
        assert done["monitor_followup_degraded_reason"] == (
            "fresh claim on the same workspace"
        )
>       assert "monitor_followup_error" not in done
E       AssertionError: assert 'monitor_followup_error' not in {'changespec_name': 'acme', 'cl_name': 'acme', 'continuation_manifest_path': '/home/bryan/.cache/sase/tmp/agent-tmp/gh...ion/monitor_result_manifest.json', 'continuation_manifest_ref': 'local:continuation/monitor_result_manifest.json', ...}

tests/monitor/test_monitor_supervise_followup.py:138: AssertionError
____ test_run_supervisor_releases_the_claim_when_the_followup_launch_fails _____

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_run_supervisor_releases_t0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0bd0e42630>

    def test_run_supervisor_releases_the_claim_when_the_followup_launch_fails(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        artifacts_dir, project_file = _make_member(
            tmp_path, command="true", next_action="Report that it finished."
        )
        import sase.monitor.supervise as supervise_module
    
        def fake_launch_failure(
            _artifacts_dir: str, meta: dict[str, object], **_kwargs: object
        ) -> bool:
            assert not (Path(_artifacts_dir) / "done.json").exists()
            meta["monitor_followup_error"] = "boom"
            return False
    
        monkeypatch.setattr(supervise_module, "launch_followup_agent", fake_launch_failure)
        monkeypatch.setattr(
            supervise_module,
            "wait_for_followup_started",
            lambda *_args: pytest.fail("failed follow-up launch should not wait"),
        )
    
        run_supervisor(artifacts_dir)
    
        meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        assert meta["monitor_state"] == "completed"
        assert meta["monitor_settled"] is True
        done = json.loads((Path(artifacts_dir) / "done.json").read_text())
        assert done["monitor_state"] == "completed"
>       assert done["monitor_followup_error"] == "boom"
E       assert 'workspace re...orce sase`).)' == 'boom'
E         
E         - boom
E         + workspace retention settlement failed: stale binding (sase_core_rs is importable but does not expose binding 'decide_workspace_retention'; the installed wheel is stale or was built without the shipped bindings. Reinstall sase in this environment (for example `uv tool install --force sase`).; ecide_workspace_retention")
E         +               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E         +   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/core/rust.py", line 71, in require_rust_binding
E         +     raise AttributeError(
E         + AttributeError: sase_core_rs is importable but d...
E         
E         ...Full output truncated (1 line hidden), use '-vv' to show

tests/monitor/test_monitor_supervise_followup.py:171: AssertionError
_____________ test_supervisor_subprocess_stops_cleanly_on_sigterm ______________

tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws22-261103_113445/pytest-of-bryan/pytest-0/test_supervisor_subprocess_sto0')

    def test_supervisor_subprocess_stops_cleanly_on_sigterm(tmp_path: Path) -> None:
        ready_file = tmp_path / "ready"
        artifacts_dir, project_file = _make_member(
            tmp_path, command=f"touch {ready_file} && sleep 30", timeout_seconds=120.0
        )
    
        process = subprocess.Popen(
            [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ],
            env=os.environ.copy(),
        )
        try:
            deadline = time.monotonic() + _STOP_POLL_TIMEOUT
            while not ready_file.exists() and time.monotonic() < deadline:
                time.sleep(_STOP_POLL_INTERVAL)
            assert ready_file.exists(), "monitored command never started"
    
            process.send_signal(signal.SIGTERM)
            process.wait(timeout=_STOP_POLL_TIMEOUT)
    
            meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
            assert meta["monitor_state"] == "stopped"
            done = json.loads((Path(artifacts_dir) / "done.json").read_text())
            assert done["monitor_state"] == "stopped"
            # A stopped monitor releases the claim -- no follow-up is launched.
>           assert get_claimed_workspaces(project_file) == []
E           AssertionError: assert [WorkspaceCla...ix_fields=())] == []
E             
E             Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=2915271, artifacts_timestamp='20260812120000', pinned=False, suffix_fields=())
E             Use -v to get more diff

tests/monitor/test_monitor_supervise_timeout.py:263: AssertionError
============================= slowest 20 durations =============================
10.15s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
9.34s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
8.84s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
8.39s call     tests/monitor/test_monitor_proc_facade.py::test_background_grandchild_and_resistant_group_are_stopped
5.72s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_cancel_saves_once_submit_path_quiet
5.64s call     tests/monitor/test_monitor_start_conflicts.py::test_start_monitor_serializes_concurrent_starts_in_one_lane
5.62s call     tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_after_partial_line
4.06s call     tests/monitor/test_monitor_tool_handoff.py::test_explicit_tool_run_reserved_not_doubled
3.90s call     tests/monitor/test_monitor_tool_wrap.py::test_completion_argv_still_resolves_the_raw_command
3.89s call     tests/monitor/test_monitor_proc_facade.py::test_stop_uses_the_proc_service_and_suppresses_followup
3.85s call     tests/monitor/test_monitor_tool_handoff.py::test_completion_argv_still_raw
3.79s call     tests/monitor/test_monitor_tool_handoff.py::test_named_upgrade_reserves_handoff
3.78s call     tests/monitor/test_monitor_tool_wrap.py::test_verify_true_becomes_named_check_run
3.75s call     tests/monitor/test_monitor_tool_wrap.py::test_verify_compound_becomes_single_adhoc_run
3.75s call     tests/monitor/test_monitor_tool_handoff.py::test_failed_reservation_falls_back_with_reason_line
3.72s call     tests/monitor/test_monitor_start_supervisor.py::test_sighup_to_supervisor_does_not_stop_the_monitor
3.56s call     tests/monitor/test_monitor_tool_wrap.py::test_already_wrapped_monitor_is_not_rewrapped
3.54s call     tests/monitor/test_monitor_start_stage_adopt.py::test_tool_run_id_is_stable_from_stage_to_launch
3.54s call     tests/monitor/test_monitor_start_stage_cleanup.py::test_held_cleanup_keeps_outer_record
3.51s call     tests/monitor/test_monitor_proc_facade.py::test_start_uses_one_proc_id_and_artifacts_cross_links
=========================== short test summary info ============================
FAILED tests/monitor/test_monitor_owner_cleanup.py::test_owner_cleanup_stops_monitor_child_and_suppresses_followup
FAILED tests/monitor/test_monitor_proc_facade.py::test_claim_is_released_when_there_is_no_followup
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_prepared_completion_success_releases_clean
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_prepared_completion_failure_retains_dirty
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_repeated_settlement_is_idempotent
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_resume_success_label_without_proof_leaves_hold
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_resume_degraded_and_failed_leave_hold
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_stale_claim_is_noop
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_proc_reconcile_path_retains_dirty
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_dirty_linked_repo_beyond_eighth_still_retains
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_unavailable_owned_checkout_retains_as_uncertainty
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_stale_binding_retries_in_fresh_interpreter
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_failed_git_preflight_without_baseline_retains
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_discovery_failure_with_dirty_opened_linked_retains
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_repo_less_command_releases
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_unchanged_foreign_baseline_dirt_releases
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_stale_owner_and_unavailable_fresh_interpreter_pins_monitor_timestamp
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_successor_collection_failure_pins_dirty_claim
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_pending_write_failure_still_pins
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_fresh_interpreter_timeout_pins_dirty_claim
FAILED tests/monitor/test_monitor_retention_lifecycle.py::test_resume_transfer_with_live_successor_settles
FAILED tests/monitor/test_monitor_retention_settlement.py::test_stopped_dirty_monitor_pins_claim_and_keeps_files[legacy]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_stopped_dirty_monitor_pins_claim_and_keeps_files[records_v1]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_stopped_clean_monitor_releases_claim[legacy]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_stopped_clean_monitor_releases_claim[records_v1]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_reboot_lost_dirty_monitor_retains
FAILED tests/monitor/test_monitor_retention_settlement.py::test_failed_monitor_with_failed_followup_retains_dirty
FAILED tests/monitor/test_monitor_retention_settlement.py::test_failed_monitor_with_failed_followup_releases_when_clean
FAILED tests/monitor/test_monitor_retention_settlement.py::test_degraded_followup_retains_original_dirty_workspace
FAILED tests/monitor/test_monitor_retention_settlement.py::test_blocked_continuation_capture_retains_dirty
FAILED tests/monitor/test_monitor_retention_settlement.py::test_same_workspace_successor_keeps_transferred_claim
FAILED tests/monitor/test_monitor_retention_settlement.py::test_stale_launch_label_without_proof_retains_dirty
FAILED tests/monitor/test_monitor_retention_settlement.py::test_delivery_history_without_live_successor_retains[reserved]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_delivery_history_without_live_successor_retains[dispatching]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_delivery_history_without_live_successor_retains[acknowledged]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_delivery_history_without_live_successor_retains[settled]
FAILED tests/monitor/test_monitor_retention_settlement.py::test_wrong_result_id_delivery_does_not_prove_transfer
FAILED tests/monitor/test_monitor_retention_settlement.py::test_degraded_delivery_does_not_prove_same_workspace_transfer
FAILED tests/monitor/test_monitor_retention_settlement.py::test_live_receiver_without_transferred_claim_retains
FAILED tests/monitor/test_monitor_retention_settlement.py::test_different_workspace_occupant_does_not_prove_transfer
FAILED tests/monitor/test_monitor_settlement_starter_race.py::test_settlement_still_not_launchable_when_starter_never_settles
FAILED tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion
FAILED tests/monitor/test_monitor_start.py::test_start_monitor_epic_launch_from_non_numbered_cwd_uses_workspace_zero
FAILED tests/monitor/test_monitor_start_activation.py::test_adoption_waits_for_finalizer_settlement
FAILED tests/monitor/test_monitor_start_stage_cleanup.py::test_failed_finalization_releases_monitor_resources_and_keeps_stage[owned]
FAILED tests/monitor/test_monitor_start_stage_cleanup.py::test_failed_finalization_releases_monitor_resources_and_keeps_stage[joined]
FAILED tests/monitor/test_monitor_start_stage_cleanup.py::test_failed_finalization_releases_monitor_resources_and_keeps_stage[prepared]
FAILED tests/monitor/test_monitor_start_stage_prepared.py::test_staged_monitor_waits_for_real_finalizer_controller[False]
FAILED tests/monitor/test_monitor_start_stage_prepared.py::test_staged_monitor_waits_for_real_finalizer_controller[True]
FAILED tests/monitor/test_monitor_store_reconcile.py::test_dead_supervisor_reconciliation_kills_tree_releases_claim_and_settles
FAILED tests/monitor/test_monitor_store_reconcile.py::test_pre_reboot_monitor_reconciles_to_lost_without_followup_or_signal
FAILED tests/monitor/test_monitor_supervise.py::test_run_supervisor_records_a_clean_completion_and_releases_the_claim
FAILED tests/monitor/test_monitor_supervise.py::test_run_supervisor_fails_without_the_launch_barrier
FAILED tests/monitor/test_monitor_supervise_followup.py::test_run_supervisor_records_degraded_followup_and_releases_monitor_claim
FAILED tests/monitor/test_monitor_supervise_followup.py::test_run_supervisor_releases_the_claim_when_the_followup_launch_fails
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_supervisor_subprocess_stops_cleanly_on_sigterm
56 failed, 643 passed, 1 warning in 455.02s (0:07:35)

