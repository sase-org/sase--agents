# Chat History - ace-run (sase-14n.14--mon)

- **TIMESTAMP:** 2026-09-20 19:17:03 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14n.14--mon

## Prompt

sase monitor start --command 'sase tool run check' --reason 'Verify bead sase-14n.14 workspace-error work with the recorded check before closing'

## Response

sase tool run 6ac89644126eefbb95eca1d5bcf47e3f
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✓ committed plans
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 4058 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 2828 commits behind HEAD) matched 3 changed file(s) and contributed 16 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [2413 items]

..................................................F.FF.................. [  2%]
........................................................................ [  5%]
........................................................................ [  8%]
........................................................................ [ 11%]
........................................................................ [ 14%]
........................................................................ [ 17%]
........................................................................ [ 20%]
........................................................................ [ 23%]
.....................................................F.................. [ 26%]
........................................................................ [ 29%]
........................................................................ [ 32%]
........................................................................ [ 35%]
........................................................................ [ 38%]
........................................................................ [ 41%]
........................................................................ [ 44%]
........................................................................ [ 47%]
........................................................................ [ 50%]
........................................................................ [ 53%]
........................................................................ [ 56%]
........................................................................ [ 59%]
........................................................................ [ 62%]
...F...............................................F.................... [ 65%]
........................................................................ [ 68%]
........................................................................ [ 71%]
........................................................................ [ 74%]
........................................................................ [ 77%]
........................................................................ [ 80%]
........................................................................ [ 83%]
........................................................................ [ 86%]
........................................................................ [ 89%]
........................................................................ [ 92%]
........................................................................ [ 95%]
........................................................................ [ 98%]
.....................................                                    [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____ test_prepare_workspace_skips_shared_agents_clone_while_sync_holds_lock ____
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f117e414670>

    def test_prepare_workspace_skips_shared_agents_clone_while_sync_holds_lock(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A busy agents sync blocks the clean instead of racing its payload."""
    
        repo = _shared_agents_clone()
        monkeypatch.setenv("SASE_AGENTS_SYNC_LOCK_TIMEOUT", "0")
        clean = MagicMock(return_value=(True, None))
        descriptor = os.open(_lock_path(repo), os.O_RDWR | os.O_CREAT, 0o600)
        fcntl.flock(descriptor, fcntl.LOCK_EX)
        try:
            with (
                patch("sase.workflows.commit_utils.run_sase_hg_clean", clean),
                patch(
                    "sase.axe.runner_workspace_prepare.get_vcs_provider",
                    return_value=_successful_provider(),
                ),
            ):
>               result = prepare_workspace(str(repo), "agents", VCS_DEFAULT_REVISION)
                         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_axe_runner_workspace_agents_lock.py:89: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/home29/.sase/projects/gh_sase-org__sase/repos/agents'
cl_name = 'agents', update_target = '__vcs_default__', backup_suffix = 'ace'
project_basename = ''

    def prepare_workspace(
        workspace_dir: str,
        cl_name: str,
        update_target: str,
        backup_suffix: str = "ace",
        project_basename: str = "",
    ) -> None:
        """Clean and update workspace before running agent or workflow.
    
        Args:
            workspace_dir: The workspace directory.
            cl_name: Display name for the Patch/project (used for backup diff name).
            update_target: What to checkout (Patch branch or "p4head").
            backup_suffix: Suffix appended to cl_name for the backup diff name
                (e.g., "ace" produces "{cl_name}-ace").
            project_basename: Project basename for resolving patch names to
                git branch names.
    
        Raises:
            WorkspacePreparationError: If any step fails. The error's ``reason``
                carries the underlying git/update failure text, and each failure
                is also printed so the run log records the cause.
        """
        with _agents_sidecar_sync_guard(workspace_dir) as acquired:
            if not acquired:
                reason = (
                    "workspace preparation refused to clean the shared agents sidecar "
                    f"clone at {workspace_dir}: agents sync lock is busy"
                )
                print(reason, file=sys.stderr)
>               raise WorkspacePreparationError(
                    reason, step="agents-sync-guard", workspace_dir=workspace_dir
                )
E               sase.axe.runner_workspace_prepare.WorkspacePreparationError: Failed to prepare workspace /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/home29/.sase/projects/gh_sase-org__sase/repos/agents during agents-sync-guard: workspace preparation refused to clean the shared agents sidecar clone at /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/home29/.sase/projects/gh_sase-org__sase/repos/agents: agents sync lock is busy

src/sase/axe/runner_workspace_prepare.py:119: WorkspacePreparationError
----------------------------- Captured stderr call -----------------------------
workspace preparation refused to clean the shared agents sidecar clone at /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/home29/.sase/projects/gh_sase-org__sase/repos/agents: agents sync lock is busy
__________ test_prepare_workspace_holds_agents_lock_across_the_clean ___________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f118efbb150>

    def test_prepare_workspace_holds_agents_lock_across_the_clean(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The lock covers the clean and checkout, and is released afterwards."""
    
        repo = _shared_agents_clone()
        monkeypatch.setenv("SASE_AGENTS_SYNC_LOCK_TIMEOUT", "0")
        provider = _successful_provider()
        observed: list[bool] = []
    
        def _clean(workspace_dir: str, diff_name: str) -> tuple[bool, None]:
            assert workspace_dir and diff_name
            observed.append(_lock_is_free(_lock_path(repo)))
            return (True, None)
    
        with (
            patch("sase.workflows.commit_utils.run_sase_hg_clean", _clean),
            patch(
                "sase.axe.runner_workspace_prepare.get_vcs_provider", return_value=provider
            ),
        ):
            result = prepare_workspace(str(repo), "agents", VCS_DEFAULT_REVISION)
    
>       assert result is True
E       assert None is True

tests/test_axe_runner_workspace_agents_lock.py:121: AssertionError
----------------------------- Captured stdout call -----------------------------
Cleaning workspace...
Updating workspace to origin/main...
Workspace ready
____ test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded _____
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_leaves_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f117d097770>

    def test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Only the machine-shared clone is coordinated, not a workspace sidecar."""
    
        repo = _git_init(tmp_path / "sase_3" / "sase" / "repos" / "agents")
        monkeypatch.setenv("SASE_AGENTS_SYNC_LOCK_TIMEOUT", "0")
        observed: list[bool] = []
    
        def _clean(workspace_dir: str, diff_name: str) -> tuple[bool, None]:
            assert workspace_dir and diff_name
            observed.append(_lock_is_free(_lock_path(repo)))
            return (True, None)
    
        with (
            patch("sase.workflows.commit_utils.run_sase_hg_clean", _clean),
            patch(
                "sase.axe.runner_workspace_prepare.get_vcs_provider",
                return_value=_successful_provider(),
            ),
        ):
            result = prepare_workspace(str(repo), "agents", VCS_DEFAULT_REVISION)
    
>       assert result is True
E       assert None is True

tests/test_axe_runner_workspace_agents_lock.py:151: AssertionError
----------------------------- Captured stdout call -----------------------------
Cleaning workspace...
Updating workspace to origin/main...
Workspace ready
________ TestOpen.test_open_preparation_failure_returns_1_without_path _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python

self = <tests.main.test_workspace_handler_open.TestOpen object at 0x7f68aa966850>
project_layout = ('demo', '/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw1/test_open_preparation_failure_0/home/.sase/project....sase', PosixPath('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw1/test_open_preparation_failure_0/primary'))
capsys = <_pytest.capture.CaptureFixture object at 0x7f68a97ad2d0>

    def test_open_preparation_failure_returns_1_without_path(
        self,
        project_layout: tuple[str, str, Path],
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        project_name, _, primary = project_layout
        checkout = str(primary.parent / "managed" / "primary_42")
        args = make_args(
            workspace_subcommand="open",
            project=project_name,
            reason="prepare workspace",
            workspace_num=42,
            print_path=False,
            clean=True,
        )
    
        with (
            patch(
                "sase.main.workspace_handler._resolve_checkout_path",
                return_value=checkout,
            ),
            patch("sase.axe.runner_workspace.prepare_workspace", return_value=False),
            pytest.raises(SystemExit) as exc,
        ):
            handle_workspace_command(args)
    
>       assert exc.value.code == 1
E       assert 0 == 1
E        +  where 0 = SystemExit(0).code
E        +    where SystemExit(0) = <ExceptionInfo SystemExit(0) tblen=2>.value

tests/main/test_workspace_handler_open.py:311: AssertionError
----------------------------- Captured stdout call -----------------------------
/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw1/test_open_preparation_failure_0/managed/primary_42
----------------------------- Captured stderr call -----------------------------
Warning: 'sase workspace open' is deprecated; use 'sase repo open'
_ test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[plans-embedded] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f117a46fe70>
beads_dirname = 'beads'

    @pytest.mark.parametrize(
        "beads_dirname",
        ["beads", BEADS_DIRNAME_ROOT],
        ids=["plans-embedded", "repo-root"],
    )
    def test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        beads_dirname: str,
    ) -> None:
        _remote, local, upstream_writer, phase_ids = _seed_claim_soak_remote(
            tmp_path,
            phase_count=2,
            beads_dirname=beads_dirname,
        )
        local_phase, upstream_phase = phase_ids
        local_beads = local / beads_dirname
        upstream_beads = upstream_writer / beads_dirname
        with BeadProject(local, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(local_phase, "local-agent")
        assert changed
        assert commit_bead_claim(local_beads, local_phase, "local-agent")
        local_commit = _git(local, "rev-parse", "HEAD").stdout.strip()
    
        with BeadProject(upstream_writer, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(
                upstream_phase,
                "upstream-agent",
            )
        assert changed
        assert commit_bead_claim(
            upstream_beads,
            upstream_phase,
            "upstream-agent",
        )
        _git(upstream_writer, "push")
        _git(local, "fetch", "origin")
        assert unpushed_bead_commit_count(local, local_beads) == 1
    
        sync_log = tmp_path / "failed-sync.log"
        sync_attempts: list[Path] = []
    
        def fail_publish(beads_dir: Path) -> SimpleNamespace:
            sync_attempts.append(beads_dir)
            return SimpleNamespace(
                pushed=False,
                error="injected managed sync failure",
                log_path=sync_log,
            )
    
        class ResettingProvider:
            checkout_revisions: list[str]
    
            def __init__(self) -> None:
                self.checkout_revisions = []
    
            def get_default_parent_revision(self, cwd: str) -> str:
                return "origin/main"
    
            def checkout(self, revision: str, cwd: str) -> tuple[bool, str | None]:
                self.checkout_revisions.append(revision)
                _git(Path(cwd), "reset", "--hard", revision)
                return True, None
    
            def sync_workspace(self, cwd: str) -> tuple[bool, str | None]:
                return True, None
    
        provider = ResettingProvider()
        monkeypatch.setattr("sase.bead.sync.push_bead_work_launch", fail_publish)
        monkeypatch.setattr(
            "sase.workflows.commit_utils.run_sase_hg_clean",
            lambda *_args: (True, ""),
        )
        monkeypatch.setattr(
            "sase.axe.runner_workspace_prepare.get_vcs_provider",
            lambda _cwd: provider,
        )
    
>       assert prepare_workspace(
            str(local),
            "sidecar",
            VCS_DEFAULT_REVISION,
        )
E       AssertionError: assert None
E        +  where None = prepare_workspace('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues0/claim-soak-local', 'sidecar', '__vcs_default__')
E        +    where '/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues0/claim-soak-local' = str(PosixPath('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues0/claim-soak-local'))

tests/test_bead/test_sync_workspace_prepare_regressions.py:102: AssertionError
----------------------------- Captured stdout call -----------------------------
Found 1 unpushed local bead commit(s) in /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues0/claim-soak-local; publishing before workspace cleanup...
Cleaning workspace...
Updating workspace to origin/main...
Workspace ready
----------------------------- Captured stderr call -----------------------------
Warning: retained 1 unpushed local bead commit(s) at refs/sase/recovery/20260920T231352Z-main-30022e3461 before workspace cleanup; injected managed sync failure (managed sync log: /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues0/failed-sync.log)
_ test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[repo-root] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f117a46fd90>
beads_dirname = '.'

    @pytest.mark.parametrize(
        "beads_dirname",
        ["beads", BEADS_DIRNAME_ROOT],
        ids=["plans-embedded", "repo-root"],
    )
    def test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        beads_dirname: str,
    ) -> None:
        _remote, local, upstream_writer, phase_ids = _seed_claim_soak_remote(
            tmp_path,
            phase_count=2,
            beads_dirname=beads_dirname,
        )
        local_phase, upstream_phase = phase_ids
        local_beads = local / beads_dirname
        upstream_beads = upstream_writer / beads_dirname
        with BeadProject(local, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(local_phase, "local-agent")
        assert changed
        assert commit_bead_claim(local_beads, local_phase, "local-agent")
        local_commit = _git(local, "rev-parse", "HEAD").stdout.strip()
    
        with BeadProject(upstream_writer, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(
                upstream_phase,
                "upstream-agent",
            )
        assert changed
        assert commit_bead_claim(
            upstream_beads,
            upstream_phase,
            "upstream-agent",
        )
        _git(upstream_writer, "push")
        _git(local, "fetch", "origin")
        assert unpushed_bead_commit_count(local, local_beads) == 1
    
        sync_log = tmp_path / "failed-sync.log"
        sync_attempts: list[Path] = []
    
        def fail_publish(beads_dir: Path) -> SimpleNamespace:
            sync_attempts.append(beads_dir)
            return SimpleNamespace(
                pushed=False,
                error="injected managed sync failure",
                log_path=sync_log,
            )
    
        class ResettingProvider:
            checkout_revisions: list[str]
    
            def __init__(self) -> None:
                self.checkout_revisions = []
    
            def get_default_parent_revision(self, cwd: str) -> str:
                return "origin/main"
    
            def checkout(self, revision: str, cwd: str) -> tuple[bool, str | None]:
                self.checkout_revisions.append(revision)
                _git(Path(cwd), "reset", "--hard", revision)
                return True, None
    
            def sync_workspace(self, cwd: str) -> tuple[bool, str | None]:
                return True, None
    
        provider = ResettingProvider()
        monkeypatch.setattr("sase.bead.sync.push_bead_work_launch", fail_publish)
        monkeypatch.setattr(
            "sase.workflows.commit_utils.run_sase_hg_clean",
            lambda *_args: (True, ""),
        )
        monkeypatch.setattr(
            "sase.axe.runner_workspace_prepare.get_vcs_provider",
            lambda _cwd: provider,
        )
    
>       assert prepare_workspace(
            str(local),
            "sidecar",
            VCS_DEFAULT_REVISION,
        )
E       AssertionError: assert None
E        +  where None = prepare_workspace('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues1/claim-soak-local', 'sidecar', '__vcs_default__')
E        +    where '/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues1/claim-soak-local' = str(PosixPath('/var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues1/claim-soak-local'))

tests/test_bead/test_sync_workspace_prepare_regressions.py:102: AssertionError
----------------------------- Captured stdout call -----------------------------
Found 1 unpushed local bead commit(s) in /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues1/claim-soak-local; publishing before workspace cleanup...
Cleaning workspace...
Updating workspace to origin/main...
Workspace ready
----------------------------- Captured stderr call -----------------------------
Warning: retained 1 unpushed local bead commit(s) at refs/sase/recovery/20260920T231354Z-main-9c145cdc00 before workspace cleanup; injected managed sync failure (managed sync log: /var/tmp/sase-0d81aaf8/pytest-of-bryan/pytest-6/popen-gw2/test_prepare_workspace_rescues1/failed-sync.log)
=============================== warnings summary ===============================
tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
64.93s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
31.20s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
15.68s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
10.29s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
9.65s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace
6.96s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
6.43s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
6.39s call     tests/fakey/test_pipe_e2e.py::test_fresh_named_model_pipe_skips_fork_and_records_model
5.02s call     tests/fakey/test_retry_pipeline_e2e.py::test_retryable_failure_then_success_records_lifecycle_and_nudge
4.88s call     tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error
4.56s call     tests/fakey/test_retry_pipeline_e2e.py::test_spawn_new_agent_writes_handoff_and_terminal_parent_artifacts
4.38s call     tests/fakey/test_pipe_e2e.py::test_monitor_sleep_one_next_still_attaches_and_transfers_claim
4.28s call     tests/fakey/test_retry_pipeline_e2e.py::test_kill_during_retry_wait_stops_before_another_subprocess
4.23s call     tests/fakey/test_retry_pipeline_e2e.py::test_execution_override_runs_fakey_with_requested_model_metadata
4.12s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_off_leaves_agents_alone
3.85s call     tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[poller_first-2]
3.83s call     tests/test_fork_workflow.py::test_embedded_bare_resume_loads_resolved_chat_path
3.77s call     tests/test_plan_gate_wait.py::test_tale_gate_wait_stamps_coder_successor_prompt
3.74s call     tests/fakey/test_retry_pipeline_e2e.py::test_fallback_switches_the_real_subprocess_model
3.68s call     tests/fakey/test_retry_pipeline_e2e.py::test_retries_exhausted_raises_after_snapshotting_terminal_attempt
=========================== short test summary info ============================
FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_skips_shared_agents_clone_while_sync_holds_lock
FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_holds_agents_lock_across_the_clean
FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded
FAILED tests/main/test_workspace_handler_open.py::TestOpen::test_open_preparation_failure_returns_1_without_path
FAILED tests/test_bead/test_sync_workspace_prepare_regressions.py::test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[plans-embedded]
FAILED tests/test_bead/test_sync_workspace_prepare_regressions.py::test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[repo-root]
=========== 6 failed, 2407 passed, 50 warnings in 303.48s (0:05:03) ============
error: recipe `test-scoped` failed on line 480 with exit code 1
error: recipe `check` failed on line 704 with exit code 1
failed  exit=1  duration=664586ms
unattrib  6.9s

