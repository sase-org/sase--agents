# Chat History - ace-run (sase-1pj.7.1.5.3--mon)

- **TIMESTAMP:** 2026-11-02 18:50:49 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1pj.7.1.5.3--mon

## Prompt

sase monitor start --command 'just check' --reason 'Verify before host completion'

## Response

sase tool run e6cdf63503980ae13fe0278c0740ee9e
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ epic-symbol freshness
✓ fmt (python)
✓ fmt (markdown)
✓ fmt (generated docs)
✓ fmt (sase-backed docs)
✓ model policy
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.43.2 is missing 21 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_prompt_select: first appears in sase-core 45c6a26 (feat(agent-prompts): add Rust-owned agent prompt selection policy); no release tag contains it yet.
[core-floor-probe] bead_assess_epic_symbol_freshness: first appears in sase-core e60f3e1 (feat(bead): classify epic symbol freshness in Rust); no release tag contains it yet.
[core-floor-probe] bead_parse_epic_symbol_entries: first appears in sase-core e60f3e1 (feat(bead): classify epic symbol freshness in Rust); no release tag contains it yet.
[core-floor-probe] decide_workspace_retention: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] decide_workspace_retention_dismissal: first appears in sase-core 154fe9e (feat(stranded-work): retain held workspace as stranded unless live successor owns); no release tag contains it yet.
[core-floor-probe] default_publication_cleanup_timeout: first appears in sase-core f061f5f (fix(git-lock): enforce effective budget in backoff and aged-lock decisions); no release tag contains it yet.
[core-floor-probe] effective_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] evaluate_recovery_decision: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] parse_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] plan_checked_release_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] plan_pin_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] recovery_adoption_lock_filename: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] recovery_context_wire_schema_version: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] resolve_agent_run_state_observations: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_discovery_window: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_hoods: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_current_wait_turn: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] staged_handoff_receipt_transition_allowed: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] staged_reconcile_page: first appears in sase-core 16a3ed0 (feat(staged-handoff): add bounded discovery and automatic recovery policy); no release tag contains it yet.
[core-floor-probe] validate_recovery_context: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] workspace_retention_wire_schema_version: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "45c6a26", "name": "agent_prompt_select", "release": null, "subject": "feat(agent-prompts): add Rust-owned agent prompt selection policy"}, {"commit": "e60f3e1", "name": "bead_assess_epic_symbol_freshness", "release": null, "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "e60f3e1", "name": "bead_parse_epic_symbol_entries", "release": null, "subject": "feat(bead): classify epic symbol freshness in Rust"}, {"commit": "80338d6", "name": "decide_workspace_retention", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "154fe9e", "name": "decide_workspace_retention_dismissal", "release": null, "subject": "feat(stranded-work): retain held workspace as stranded unless live successor owns"}, {"commit": "f061f5f", "name": "default_publication_cleanup_timeout", "release": null, "subject": "fix(git-lock): enforce effective budget in backoff and aged-lock decisions"}, {"commit": "d7b00dd", "name": "effective_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "evaluate_recovery_decision", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "d7b00dd", "name": "parse_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "80338d6", "name": "plan_checked_release_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "80338d6", "name": "plan_pin_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "73ec04a", "name": "recovery_adoption_lock_filename", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "73ec04a", "name": "recovery_context_wire_schema_version", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "dc5383f", "name": "resolve_agent_run_state_observations", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_discovery_window", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_hoods", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "d7b00dd", "name": "select_current_wait_turn", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "staged_handoff_receipt_transition_allowed", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "16a3ed0", "name": "staged_reconcile_page", "release": null, "subject": "feat(staged-handoff): add bounded discovery and automatic recovery policy"}, {"commit": "73ec04a", "name": "validate_recovery_context", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "80338d6", "name": "workspace_retention_wire_schema_version", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}], "declared_floor": "0.43.2", "exit_code": 4, "message": "sase-core-rs==0.43.2 is missing 21 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✓ docs (build + links)
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, contract-set-always, marker-audit, no-baseline-depth-boost, serial-budget-exceeded); 5570 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 4964 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [4457 items]

........................................................................ [  1%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  6%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 14%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 19%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 27%]
........................................................................ [ 29%]
........................................................................ [ 30%]
...................F...F.....F....F..................................... [ 32%]
........................................................................ [ 33%]
........................................................................ [ 35%]
........................................................................ [ 37%]
........................................................................ [ 38%]
............................F........................................... [ 40%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 48%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 56%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 61%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 69%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 77%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 82%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 90%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 95%]
........................................................................ [ 96%]
.......................................................F................ [ 98%]
.................................................................        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
____ test_run_supervisor_records_a_clean_completion_and_releases_the_claim _____
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw1/test_run_supervisor_records_a_0')

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
E         Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=1235222, artifacts_timestamp=None, pinned=False, suffix_fields=())
E         
E         Full diff:
E         - []
E         + [
E         +     WorkspaceClaim(
E         +         workspace_num=1,
E         +         workflow='ace-monitor',
E         +         cl_name='acme',
E         +         pid=1235222,
E         +         artifacts_timestamp=None,
E         +         pinned=False,
E         +         suffix_fields=(),
E         +     ),
E         + ]

tests/monitor/test_monitor_supervise.py:113: AssertionError
_____________ test_run_supervisor_fails_without_the_launch_barrier _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw1/test_run_supervisor_fails_with0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff907d35d30>

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
E         Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=1235222, artifacts_timestamp=None, pinned=False, suffix_fields=())
E         
E         Full diff:
E         - []
E         + [
E         +     WorkspaceClaim(
E         +         workspace_num=1,
E         +         workflow='ace-monitor',
E         +         cl_name='acme',
E         +         pid=1235222,
E         +         artifacts_timestamp=None,
E         +         pinned=False,
E         +         suffix_fields=(),
E         +     ),
E         + ]

tests/monitor/test_monitor_supervise.py:200: AssertionError
___ test_run_supervisor_records_degraded_followup_and_releases_monitor_claim ___
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw1/test_run_supervisor_records_de0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff907d34210>

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
E       AssertionError: assert 'monitor_followup_error' not in {'changespec_name': 'acme', 'cl_name': 'acme', 'continuation_manifest_path': '/var/tmp/sase-02a72d87/pytest-of-bryan/p...ion/monitor_result_manifest.json', 'continuation_manifest_ref': 'local:continuation/monitor_result_manifest.json', ...}

tests/monitor/test_monitor_supervise_followup.py:138: AssertionError
____ test_run_supervisor_releases_the_claim_when_the_followup_launch_fails _____
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw1/test_run_supervisor_releases_t0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff91a54b2a0>

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
E       AssertionError: assert 'workspace re...guarded retry' == 'boom'
E         
E         - boom
E         + workspace retention settlement failed: unresolved monitor owner (missing pid); claim left untouched for guarded retry

tests/monitor/test_monitor_supervise_followup.py:171: AssertionError
_____________ test_supervisor_subprocess_stops_cleanly_on_sigterm ______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw1/test_supervisor_subprocess_sto0')

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
E             Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=1235222, artifacts_timestamp=None, pinned=False, suffix_fields=())
E             
E             Full diff:
E             - []
E             + [
E             +     WorkspaceClaim(
E             +         workspace_num=1,
E             +         workflow='ace-monitor',
E             +         cl_name='acme',
E             +         pid=1235222,
E             +         artifacts_timestamp=None,
E             +         pinned=False,
E             +         suffix_fields=(),
E             +     ),
E             + ]

tests/monitor/test_monitor_supervise_timeout.py:263: AssertionError
_______ test_settlement_still_not_launchable_when_starter_never_settles ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw2/test_settlement_still_not_laun0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1ca7062b30>

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
E       AssertionError: assert 'workspace re...guarded retry' == 'monitor resu...123 -m MODEL`'
E         
E         - monitor result is missing its exact starter parent node; automatic dispatch is blocked pending recovery; starter acme continuation capture failed (agent_delta:interrupted: validation: authored_local_request contains unsupported control characters); recover with `sase monitor resume abc123 -k FILE` or `sase monitor resume abc123 -m MODEL`
E         + workspace retention settlement failed: unresolved monitor owner (missing pid); claim left untouched for guarded retry

tests/monitor/test_monitor_settlement_starter_race.py:260: AssertionError
=============================== warnings summary ===============================
tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=1235279) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
62.20s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
26.87s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
19.31s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
19.19s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
14.87s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
9.24s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
8.85s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
8.59s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
8.53s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
7.57s call     tests/tool/test_inline_escalation.py::test_sigterm_leaves_run_running
7.15s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
7.10s call     tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths
6.98s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
6.67s call     tests/monitor/test_monitor_proc_facade.py::test_background_grandchild_and_resistant_group_are_stopped
6.56s call     tests/tool/test_detach.py::test_watchdog_reports_ended_join_monitor
6.47s call     tests/fakey/test_autonomy_lifecycle_e2e.py::test_tale_lifecycle_inherits_to_gate_followup
5.83s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
5.80s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
5.66s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
5.45s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
=========================== short test summary info ============================
FAILED tests/monitor/test_monitor_supervise.py::test_run_supervisor_records_a_clean_completion_and_releases_the_claim - AssertionError: assert [WorkspaceCla...ix_fields=())] == []
  
  Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=1235222, artifacts_timestamp=None, pinned=False, suffix_fields=())
  
  Full diff:
  - []
  + [
  +     WorkspaceClaim(
  +         workspace_num=1,
  +         workflow='ace-monitor',
  +         cl_name='acme',
  +         pid=1235222,
  +         artifacts_timestamp=None,
  +         pinned=False,
  +         suffix_fields=(),
  +     ),
  + ]
FAILED tests/monitor/test_monitor_supervise.py::test_run_supervisor_fails_without_the_launch_barrier - AssertionError: assert [WorkspaceCla...ix_fields=())] == []
  
  Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=1235222, artifacts_timestamp=None, pinned=False, suffix_fields=())
  
  Full diff:
  - []
  + [
  +     WorkspaceClaim(
  +         workspace_num=1,
  +         workflow='ace-monitor',
  +         cl_name='acme',
  +         pid=1235222,
  +         artifacts_timestamp=None,
  +         pinned=False,
  +         suffix_fields=(),
  +     ),
  + ]
FAILED tests/monitor/test_monitor_supervise_followup.py::test_run_supervisor_records_degraded_followup_and_releases_monitor_claim - AssertionError: assert 'monitor_followup_error' not in {'changespec_name': 'acme', 'cl_name': 'acme', 'continuation_manifest_path': '/var/tmp/sase-02a72d87/pytest-of-bryan/p...ion/monitor_result_manifest.json', 'continuation_manifest_ref': 'local:continuation/monitor_result_manifest.json', ...}
FAILED tests/monitor/test_monitor_supervise_followup.py::test_run_supervisor_releases_the_claim_when_the_followup_launch_fails - AssertionError: assert 'workspace re...guarded retry' == 'boom'
  
  - boom
  + workspace retention settlement failed: unresolved monitor owner (missing pid); claim left untouched for guarded retry
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_supervisor_subprocess_stops_cleanly_on_sigterm - AssertionError: assert [WorkspaceCla...ix_fields=())] == []
  
  Left contains one more item: WorkspaceClaim(workspace_num=1, workflow='ace-monitor', cl_name='acme', pid=1235222, artifacts_timestamp=None, pinned=False, suffix_fields=())
  
  Full diff:
  - []
  + [
  +     WorkspaceClaim(
  +         workspace_num=1,
  +         workflow='ace-monitor',
  +         cl_name='acme',
  +         pid=1235222,
  +         artifacts_timestamp=None,
  +         pinned=False,
  +         suffix_fields=(),
  +     ),
  + ]
FAILED tests/monitor/test_monitor_settlement_starter_race.py::test_settlement_still_not_launchable_when_starter_never_settles - AssertionError: assert 'workspace re...guarded retry' == 'monitor resu...123 -m MODEL`'
  
  - monitor result is missing its exact starter parent node; automatic dispatch is blocked pending recovery; starter acme continuation capture failed (agent_delta:interrupted: validation: authored_local_request contains unsupported control characters); recover with `sase monitor resume abc123 -k FILE` or `sase monitor resume abc123 -m MODEL`
  + workspace retention settlement failed: unresolved monitor owner (missing pid); claim left untouched for guarded retry
=========== 6 failed, 4451 passed, 49 warnings in 332.73s (0:05:32) ============
error: recipe `test-scoped` failed on line 650 with exit code 1
error: recipe `check` failed on line 917 with exit code 1
failed  exit=1  duration=692031ms
unattrib  15.9s
triage test (scoped): 6 NEW stopped
NEW test (scoped): FAILED tests/monitor/test_monitor_settlement_starter_race.py::test_settlement_still_not_launchable_when_starter_never_settles - AssertionError: assert 'workspace re...guarded retry' == 'monitor resu...123 -m MODEL`' — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_supervise_timeout.py::test_supervisor_subprocess_stops_cleanly_on_sigterm - AssertionError: assert [WorkspaceCla...ix_fields=())] == [] — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_supervise.py::test_run_supervisor_records_a_clean_completion_and_releases_the_claim - AssertionError: assert [WorkspaceCla...ix_fields=())] == [] — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_supervise.py::test_run_supervisor_fails_without_the_launch_barrier - AssertionError: assert [WorkspaceCla...ix_fields=())] == [] — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_supervise_followup.py::test_run_supervisor_records_degraded_followup_and_releases_monitor_claim - AssertionError: assert 'monitor_followup_error' not in {'changespec_name': 'acme', 'cl_name': 'acme', 'continuation_manifest_path': '/var<tmp> 'continuation_manifest_ref': 'local:continuation/monitor_result_manifest.json', ...} — recorded evidence; no owner
NEW test (scoped): FAILED tests/monitor/test_monitor_supervise_followup.py::test_run_supervisor_releases_the_claim_when_the_followup_launch_fails - AssertionError: assert 'workspace re...guarded retry' == 'boom' — recorded evidence; no owner
verdict: new_failures — 6 NEW; exit 1

