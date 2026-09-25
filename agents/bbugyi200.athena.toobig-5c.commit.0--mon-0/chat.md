# Chat History - ace-run (toobig-5c.commit.0--mon-0)

- **TIMESTAMP:** 2026-09-14 00:30:32 EDT
- **MODEL:** claude/sonnet
- **AGENT:** toobig-5c.commit.0--mon-0

## Prompt

sase monitor start --command 'just test-scoped' --reason 'Verify the commit.py split (finalizers/commit.py, commit_validation.py, new commit_unpushed_resume.py) passes the diff-scoped test lane before replying to the user'

## Response

.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 3828 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 2424 commits behind HEAD) matched 0 changed file(s) and contributed 0 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [1612 items]

........................................................................ [  4%]
........................................................................ [  8%]
........................F.....F...F......F.....F......F......F......F... [ 13%]
.F..F....F....F......F..FF.FF.FF........................................ [ 17%]
........................................................................ [ 22%]
........................................................................ [ 26%]
........................................................................ [ 31%]
........................................................................ [ 35%]
........................................................................ [ 40%]
........................................................................ [ 44%]
........................................................................ [ 49%]
.........................................................F.........F.... [ 53%]
........................................................................ [ 58%]
........................................................................ [ 62%]
........................................................................ [ 66%]
..............................................................FFFFFFFFFF [ 71%]
FFFFFF.FF............................................................... [ 75%]
........................................................................ [ 80%]
........................................................................ [ 84%]
.....................................................................FFF [ 89%]
.FFF..F................................................................. [ 93%]
........................................................................ [ 98%]
............................                                             [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________ test_builtin_commit_executes_declared_stitch_without_reprompt _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_builtin_commit_executes_d0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324663230>

    def test_builtin_commit_executes_declared_stitch_without_reprompt(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:39: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
________ test_builtin_commit_refusal_is_rejected_before_running_stitch _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_builtin_commit_refusal_is0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3246607c0>

    def test_builtin_commit_refusal_is_rejected_before_running_stitch(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:101: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________ test_post_submit_cleanup_fails_without_proven_transition ___________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_post_submit_cleanup_fails0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324661240>

    def test_post_submit_cleanup_fails_without_proven_transition(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:123: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________ test_stale_commit_results_do_not_prove_clean_transition ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_stale_commit_results_do_n0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324660130>

    def test_stale_commit_results_do_not_prove_clean_transition(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:155: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_____________ test_prior_attempt_marker_proves_already_clean_retry _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_prior_attempt_marker_prov0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324663a80>

    def test_prior_attempt_marker_proves_already_clean_retry(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:201: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_______________ test_unpushed_marker_resumes_already_clean_retry _______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_unpushed_marker_resumes_a0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324663700>

    def test_unpushed_marker_resumes_already_clean_retry(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:248: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
__________ test_unpushed_marker_resume_failure_keeps_push_diagnostic ___________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_unpushed_marker_resume_fa0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324662ac0>

    def test_unpushed_marker_resume_failure_keeps_push_diagnostic(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:320: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________ test_pending_checkpoint_resumes_before_clean_acceptance ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_pending_checkpoint_resume0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32663fb60>

    def test_pending_checkpoint_resumes_before_clean_acceptance(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:383: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
__________ test_pending_checkpoint_refuses_foreign_run_before_resume ___________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_pending_checkpoint_refuse0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32663dbe0>

    def test_pending_checkpoint_refuses_foreign_run_before_resume(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:457: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________ test_pending_checkpoint_refuses_foreign_agent_before_resume __________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_pending_checkpoint_refuse1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32663f9a0>

    def test_pending_checkpoint_refuses_foreign_agent_before_resume(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:507: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________ test_pending_checkpoint_refuses_same_subject_different_body __________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_pending_checkpoint_refuse2')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32663fc40>

    def test_pending_checkpoint_refuses_same_subject_different_body(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation.py:557: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
________ test_reconciliation_mixed_sidecar_stitches_remaining_document _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_mixed_side0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32663f000>

    def test_reconciliation_mixed_sidecar_stitches_remaining_document(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """research.0w.cld: auto-commit the link index, then stitch the report."""
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        report, index = mixed_sidecar_files()
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=(report, index),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_mixed_sidecar.py:57: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______ test_reconciliation_mixed_sidecar_rejects_edited_residual_document ______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_mixed_side1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe326e9c1a0>

    def test_reconciliation_mixed_sidecar_rejects_edited_residual_document(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        report, index = mixed_sidecar_files()
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=(report, index),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_mixed_sidecar.py:160: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______ test_reconciliation_mixed_sidecar_rejects_unexpected_residual_path ______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_mixed_side2')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324478050>

    def test_reconciliation_mixed_sidecar_rejects_unexpected_residual_path(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        report, index = mixed_sidecar_files()
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=(report, index),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_mixed_sidecar.py:230: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___ test_reconciliation_mixed_sidecar_rejects_transition_without_new_marker ____
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_mixed_side3')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32447b1c0>

    def test_reconciliation_mixed_sidecar_rejects_transition_without_new_marker(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        report, index = mixed_sidecar_files()
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=(report, index),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_mixed_sidecar.py:292: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_____ test_reconciliation_mixed_sidecar_rejects_marker_for_other_checkout ______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_mixed_side4')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32447be70>

    def test_reconciliation_mixed_sidecar_rejects_marker_for_other_checkout(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        report, index = mixed_sidecar_files()
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=(report, index),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_mixed_sidecar.py:355: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___ test_reconciliation_auto_commit_updates_marker_and_skips_sidecar_stitch ____
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_auto_commi0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324478910>

    def test_reconciliation_auto_commit_updates_marker_and_skips_sidecar_stitch(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """0ak: auto-committing a plans sidecar must prove the already-clean repo."""
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(repo),
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=("links/202608/one.md.json",),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_multi_repo.py:53: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______ test_reconciliation_marker_for_other_checkout_does_not_prove_clean ______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reconciliation_marker_for0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32447af20>

    def test_reconciliation_marker_for_other_checkout_does_not_prove_clean(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=("links/202608/one.md.json",),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_multi_repo.py:138: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
________ test_unpublished_artifact_links_fail_after_proven_auto_commit _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_unpublished_artifact_link0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324478360>

    def test_unpublished_artifact_links_fail_after_proven_auto_commit(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        plans = tmp_path / "plans"
        plans.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(
                    plans,
                    name="plans",
                    kind="sibling",
                    changed_files=("links/202608/one.md.json",),
                ),
            )
        }
>       patch_multi_repo_state(monkeypatch, repo, dirty)

tests/test_finalizers_commit_reconciliation_multi_repo.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:136: in patch_multi_repo_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_____ test_timed_out_stitch_with_landed_commit_instance_result_is_success ______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw0/test_timed_out_stitch_with_lan0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f141644f070>

    def test_timed_out_stitch_with_landed_commit_instance_result_is_success(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        dirty = {"value": True}
        prepare_agent_env(monkeypatch, artifacts, repo)
>       patch_commit_state(monkeypatch, repo, dirty)

tests/test_commit_dispatch_stitch_timeout_rescue.py:538: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_commit_reconciliation_test_helpers.py:107: in patch_commit_state
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_______ test_stitch_create_requires_keep_then_closes_only_assigned_phase _______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw0/test_stitch_create_requires_ke0')

    def test_stitch_create_requires_keep_then_closes_only_assigned_phase(
        tmp_path: Path,
    ) -> None:
        repo = init_live_repo(tmp_path / "repo")
        attach_bare_remote(repo, tmp_path / "remote.git")
        epic_id, phase_id, dependent_id = _seed_phase_beads(repo)
        starting_commits = run_git(repo, "rev-list", "--count", "HEAD").stdout.strip()
        (repo / "agent.py").write_text("print('missing')\n", encoding="utf-8")
    
        missing, missing_message = _run_stitch(
            repo,
            tmp_path,
            phase_id,
            "fix(lifecycle): first phase change",
            action=None,
        )
    
        assert missing.returncode == 1
        assert "bead_action is required" in missing.stdout + missing.stderr
        assert missing_message.is_file()
        assert run_git(repo, "rev-list", "--count", "HEAD").stdout.strip() == (
            starting_commits
        )
        assert run_git(repo, "status", "--short", "--", "agent.py").stdout == (
            "?? agent.py\n"
        )
        (repo / "agent.py").write_text("print('keep')\n", encoding="utf-8")
    
        kept, kept_message = _run_stitch(
            repo,
            tmp_path,
            phase_id,
            "fix(lifecycle): keep phase open",
            action="keep",
        )
    
        assert kept.returncode == 0, kept.stdout + kept.stderr
        assert not kept_message.exists()
        assert run_git(repo, "rev-list", "--count", "HEAD").stdout.strip() == (
            str(int(starting_commits) + 1)
        )
        head_message = run_git(repo, "show", "-s", "--format=%B", "HEAD").stdout
        assert f"SASE_BEAD={phase_id}" in head_message
        assert _show(repo, phase_id).status is Status.IN_PROGRESS
        assert _show(repo, epic_id).status is Status.OPEN
        assert _show(repo, dependent_id).status is Status.OPEN
    
        (repo / "agent.py").write_text("print('close')\n", encoding="utf-8")
        closed, closed_message = _run_stitch(
            repo,
            tmp_path,
            phase_id,
            "fix(lifecycle): close phase",
            action="close",
        )
    
>       assert closed.returncode == 0, closed.stdout + closed.stderr
E       AssertionError: ❌ unreadable_bead_status: the assigned bead status could not be read; close is 
E         refused
E         Commit message preserved at /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw0/test_stitch_create_requires_ke0/repo/.sase/commit-message.md — re-run with the same -M flag after fixing.
E         
E       assert 1 == 0
E        +  where 1 = CompletedProcess(args=['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-m', 'sase'...popen-gw0/test_stitch_create_requires_ke0/repo/.sase/commit-message.md — re-run with the same -M flag after fixing.\n').returncode

tests/test_commit_workflow_bead_lifecycle_e2e.py:182: AssertionError
____________________ test_handoff_skips_generic_controller _____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_handoff_skips_generic_con0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3253c4050>

    def test_handoff_skips_generic_controller(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        (artifacts / PLAN_PENDING_MARKER).write_text("1\n", encoding="utf-8")
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness.py:73: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________________ test_final_none_writes_empty_success_result __________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_final_none_writes_empty_s0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3253c4600>

    def test_final_none_writes_empty_success_result(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": ()}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________________ test_clean_commit_only_does_not_recover ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_clean_commit_only_does_no0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3253c69e0>

    def test_clean_commit_only_does_not_recover(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": ()}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness.py:117: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
____________ test_successful_conflict_resume_continues_same_stitch _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_successful_conflict_resum0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324662270>

    def test_successful_conflict_resume_continues_same_stitch(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:48: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
____________ test_resumed_sidecar_row_is_matched_by_exact_cwd[True] ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_resumed_sidecar_row_is_ma0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe323351e10>
marker_matches_sidecar = True

    @pytest.mark.parametrize("marker_matches_sidecar", [True, False])
    def test_resumed_sidecar_row_is_matched_by_exact_cwd(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        marker_matches_sidecar: bool,
    ) -> None:
        """A resumed sidecar row counts only when its cwd is that sidecar."""
        repo = tmp_path / "repo"
        repo.mkdir()
        sidecar = tmp_path / "plans"
        sidecar.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(sidecar, name="plans", kind="sibling"),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:119: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________ test_resumed_sidecar_row_is_matched_by_exact_cwd[False] ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_resumed_sidecar_row_is_ma1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe323352970>
marker_matches_sidecar = False

    @pytest.mark.parametrize("marker_matches_sidecar", [True, False])
    def test_resumed_sidecar_row_is_matched_by_exact_cwd(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        marker_matches_sidecar: bool,
    ) -> None:
        """A resumed sidecar row counts only when its cwd is that sidecar."""
        repo = tmp_path / "repo"
        repo.mkdir()
        sidecar = tmp_path / "plans"
        sidecar.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(sidecar, name="plans", kind="sibling"),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:119: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______________ test_stale_checkpoint_after_conflict_fails_closed _______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_stale_checkpoint_after_co0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3359f7380>

    def test_stale_checkpoint_after_conflict_fails_closed(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:183: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______________ test_post_submit_edit_is_rejected_before_mutation _______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_post_submit_edit_is_rejec0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3259b4d00>

    def test_post_submit_edit_is_rejected_before_mutation(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:212: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________________ test_later_finalizer_dirt_reactivates_commit _________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_later_finalizer_dirt_reac0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3259b70e0>

    def test_later_finalizer_dirt_reactivates_commit(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": ()}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:245: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______ test_identical_stitch_failure_skips_retry_without_spending_budget _______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_identical_stitch_failure_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3259b67b0>

    def test_identical_stitch_failure_skips_retry_without_spending_budget(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A `stitch_failed` retry whose inputs are unchanged must not re-run.
    
        Retrying an identical repository, exclude set, and message against an
        unchanged HEAD is guaranteed to fail the same way, so the host must
        detect that before spending its second (and, here, last) mutating
        attempt -- see bead sase-ti.5.
        """
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:319: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
____________ test_stitch_failure_with_changed_message_still_retries ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_stitch_failure_with_chang0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3253c6dd0>

    def test_stitch_failure_with_changed_message_still_retries(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A genuinely different retry attempt (here: a new message) must still run."""
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:366: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________________ test_controller_no_progress_fails_closed ___________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_controller_no_progress_fa0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3253c5c50>

    def test_controller_no_progress_fails_closed(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_controller.py:416: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___________ test_sequential_multi_repo_kinds_and_protected_excludes ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_sequential_multi_repo_kin0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3233bf1c0>

    def test_sequential_multi_repo_kinds_and_protected_excludes(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        linked = tmp_path / "linked"
        linked.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {
            "repos": (
                dirty_repo(repo, name="main", kind="main"),
                dirty_repo(linked, name="plans", kind="sibling"),
            )
        }
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_multi_repo.py:73: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________ test_reversed_manifest_still_executes_in_host_context_order __________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reversed_manifest_still_e0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe32445c360>

    def test_reversed_manifest_still_executes_in_host_context_order(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        linked = tmp_path / "linked"
        linked.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {
            "repos": (
                dirty_repo(repo, name="main", kind="main"),
                dirty_repo(linked, name="plans", kind="sibling"),
            )
        }
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_multi_repo.py:131: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________ test_reversed_manifest_first_host_repo_conflict_blocks_later _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_reversed_manifest_first_h0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3233bd5c0>

    def test_reversed_manifest_first_host_repo_conflict_blocks_later(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        other = tmp_path / "other"
        other.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {
            "repos": (
                dirty_repo(repo, name="main"),
                dirty_repo(other, name="research", kind="sibling"),
            )
        }
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_multi_repo.py:161: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
________________ test_first_repo_conflict_blocks_later_dispatch ________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_first_repo_conflict_block0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe323351f60>

    def test_first_repo_conflict_blocks_later_dispatch(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        other = tmp_path / "other"
        other.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {
            "repos": (
                dirty_repo(repo, name="main"),
                dirty_repo(other, name="research", kind="sibling"),
            )
        }
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_multi_repo.py:209: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_______ test_repaired_repo_conflict_does_not_starve_later_repo_conflict ________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_repaired_repo_conflict_do0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe324479ef0>

    def test_repaired_repo_conflict_does_not_starve_later_repo_conflict(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        other = tmp_path / "other"
        other.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        main = dirty_repo(repo, name="main")
        research = dirty_repo(other, name="research", kind="sibling")
        dirty = {"repos": (main, research)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_multi_repo.py:255: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______ test_same_repo_second_conflict_after_repair_later_cycle_fails_fast ______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw1/test_same_repo_second_conflict0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe3233bd470>

    def test_same_repo_second_conflict_after_repair_later_cycle_fails_fast(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        prepare_agent_env(monkeypatch, artifacts, repo)
        dirty = {"repos": (dirty_repo(repo, name="main"),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/test_finalizers_protocol_harness_multi_repo.py:326: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______________ test_real_controller_success_uses_zero_model_calls ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_real_controller_success_u0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f4985780>

    def test_real_controller_success_uses_zero_model_calls(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:217: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_ test_stale_or_missing_checks_use_one_recovery[stale_worktree_fingerprint-<lambda>] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_stale_or_missing_checks_u0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f4984590>
reason = 'stale_worktree_fingerprint'
mutate = <function <lambda> at 0x7ff3f3f74300>

    @pytest.mark.parametrize(
        ("reason", "mutate"),
        [
            (
                "stale_worktree_fingerprint",
                lambda observations: observations.__setitem__(
                    0, {**observations[0], "head": "b" * 64}
                ),
            ),
            (
                "missing_required_stage",
                lambda _observations: "drop-full-tests",
            ),
        ],
    )
    def test_stale_or_missing_checks_use_one_recovery(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        reason: str,
        mutate: Any,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:295: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_ test_stale_or_missing_checks_use_one_recovery[missing_required_stage-<lambda>] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_stale_or_missing_checks_u1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f4986ac0>
reason = 'missing_required_stage'
mutate = <function <lambda> at 0x7ff3f3f743b0>

    @pytest.mark.parametrize(
        ("reason", "mutate"),
        [
            (
                "stale_worktree_fingerprint",
                lambda observations: observations.__setitem__(
                    0, {**observations[0], "head": "b" * 64}
                ),
            ),
            (
                "missing_required_stage",
                lambda _observations: "drop-full-tests",
            ),
        ],
    )
    def test_stale_or_missing_checks_use_one_recovery(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        reason: str,
        mutate: Any,
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:295: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________________ test_unsupported_finalizer_uses_one_recovery _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_unsupported_finalizer_use0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f63674d0>

    def test_unsupported_finalizer_uses_one_recovery(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:345: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
______________ test_tree_drift_after_finalizers_uses_one_recovery ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_tree_drift_after_finalize0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f4f780c0>

    def test_tree_drift_after_finalizers_uses_one_recovery(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        extra = tmp_path / "extra"
        extra.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:398: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
___ test_two_repository_partial_crash_retains_receipts_and_does_not_complete ___
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_two_repository_partial_cr0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f4f78520>

    def test_two_repository_partial_crash_retains_receipts_and_does_not_complete(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        linked = tmp_path / "linked"
        linked.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {
            "repos": (
                dirty_repo(repo, name="main", kind="main"),
                dirty_repo(linked, name="plans", kind="sibling"),
            )
        }
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:460: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
_________ test_real_declaration_submit_is_not_stubbed_on_success_path __________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
>           obj = getattr(obj, name)
                  ^^^^^^^^^^^^^^^^^^
E           AttributeError: module 'sase.finalizers.commit' has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:95: AttributeError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-17/popen-gw2/test_real_declaration_submit_i0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff3f6365ef0>

    def test_real_declaration_submit_is_not_stubbed_on_success_path(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        repo = tmp_path / "repo"
        repo.mkdir()
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        prepare_agent_env(monkeypatch, artifacts, repo)
        monkeypatch.setenv("SASE_WORKSPACE_NUM", "20")
        resolve_and_persist_finalizer_plan(PromptDirectives(), artifacts_dir=str(artifacts))
        dirty: dict[str, tuple[DirtyRepo, ...]] = {"repos": (dirty_repo(repo),)}
>       patch_dirty(monkeypatch, repo, dirty)

tests/monitor/test_monitor_host_completion_controller.py:628: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/finalizers_protocol_harness_test_helpers.py:80: in patch_dirty
    monkeypatch.setattr(
.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:109: in derive_importpath
    annotated_getattr(target, attr, ann=module)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

obj = <module 'sase.finalizers.commit' from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/finalizers/commit.py'>
name = 'git_changed_files', ann = 'sase.finalizers.commit'

    def annotated_getattr(obj: object, name: str, ann: str) -> object:
        try:
            obj = getattr(obj, name)
        except AttributeError as e:
>           raise AttributeError(
                f"{type(obj).__name__!r} object at {ann} has no attribute {name!r}"
            ) from e
E           AttributeError: 'module' object at sase.finalizers.commit has no attribute 'git_changed_files'

.venv/lib/python3.14/site-packages/_pytest/monkeypatch.py:97: AttributeError
============================= slowest 20 durations =============================
64.53s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
9.59s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
9.34s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
8.85s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
6.87s call     tests/test_finalizers_live_e2e_cycles.py::test_live_command_and_fixture_plugin_run_in_order
6.80s call     tests/monitor/test_monitor_proc_facade.py::test_background_grandchild_and_resistant_group_are_stopped
6.24s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
5.85s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
5.79s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
5.73s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
5.34s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace
5.18s call     tests/monitor/test_continuation_delivery.py::test_concurrent_dispatch_spawns_once
4.59s call     tests/monitor/test_monitor_start_conflicts.py::test_start_monitor_serializes_concurrent_starts_in_one_lane
4.11s call     tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[after_spawn-dispatching]
3.87s call     tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[before_spawn-dispatching]
3.55s call     tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[after_reserve-reserved]
3.51s call     tests/test_plan_approval_launch_reliability_epic_launch.py::test_epic_approval_during_code_swap_creates_one_dag[writer_first]
3.19s call     tests/fakey/test_pipe_e2e.py::test_fresh_named_model_pipe_skips_fork_and_records_model
2.94s call     tests/monitor/test_continuation_delivery.py::test_followup_reserves_identity_before_spawn
2.90s call     tests/monitor/test_monitor_followup.py::test_launch_followup_agent_attaches_to_the_lane_and_transfers_the_claim
=========================== short test summary info ============================
FAILED tests/test_finalizers_commit_reconciliation.py::test_builtin_commit_executes_declared_stitch_without_reprompt
FAILED tests/test_finalizers_commit_reconciliation.py::test_builtin_commit_refusal_is_rejected_before_running_stitch
FAILED tests/test_finalizers_commit_reconciliation.py::test_post_submit_cleanup_fails_without_proven_transition
FAILED tests/test_finalizers_commit_reconciliation.py::test_stale_commit_results_do_not_prove_clean_transition
FAILED tests/test_finalizers_commit_reconciliation.py::test_prior_attempt_marker_proves_already_clean_retry
FAILED tests/test_finalizers_commit_reconciliation.py::test_unpushed_marker_resumes_already_clean_retry
FAILED tests/test_finalizers_commit_reconciliation.py::test_unpushed_marker_resume_failure_keeps_push_diagnostic
FAILED tests/test_finalizers_commit_reconciliation.py::test_pending_checkpoint_resumes_before_clean_acceptance
FAILED tests/test_finalizers_commit_reconciliation.py::test_pending_checkpoint_refuses_foreign_run_before_resume
FAILED tests/test_finalizers_commit_reconciliation.py::test_pending_checkpoint_refuses_foreign_agent_before_resume
FAILED tests/test_finalizers_commit_reconciliation.py::test_pending_checkpoint_refuses_same_subject_different_body
FAILED tests/test_finalizers_commit_reconciliation_mixed_sidecar.py::test_reconciliation_mixed_sidecar_stitches_remaining_document
FAILED tests/test_finalizers_commit_reconciliation_mixed_sidecar.py::test_reconciliation_mixed_sidecar_rejects_edited_residual_document
FAILED tests/test_finalizers_commit_reconciliation_mixed_sidecar.py::test_reconciliation_mixed_sidecar_rejects_unexpected_residual_path
FAILED tests/test_finalizers_commit_reconciliation_mixed_sidecar.py::test_reconciliation_mixed_sidecar_rejects_transition_without_new_marker
FAILED tests/test_finalizers_commit_reconciliation_mixed_sidecar.py::test_reconciliation_mixed_sidecar_rejects_marker_for_other_checkout
FAILED tests/test_finalizers_commit_reconciliation_multi_repo.py::test_reconciliation_auto_commit_updates_marker_and_skips_sidecar_stitch
FAILED tests/test_finalizers_commit_reconciliation_multi_repo.py::test_reconciliation_marker_for_other_checkout_does_not_prove_clean
FAILED tests/test_finalizers_commit_reconciliation_multi_repo.py::test_unpublished_artifact_links_fail_after_proven_auto_commit
FAILED tests/test_commit_dispatch_stitch_timeout_rescue.py::test_timed_out_stitch_with_landed_commit_instance_result_is_success
FAILED tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
FAILED tests/test_finalizers_protocol_harness.py::test_handoff_skips_generic_controller
FAILED tests/test_finalizers_protocol_harness.py::test_final_none_writes_empty_success_result
FAILED tests/test_finalizers_protocol_harness.py::test_clean_commit_only_does_not_recover
FAILED tests/test_finalizers_protocol_harness_controller.py::test_successful_conflict_resume_continues_same_stitch
FAILED tests/test_finalizers_protocol_harness_controller.py::test_resumed_sidecar_row_is_matched_by_exact_cwd[True]
FAILED tests/test_finalizers_protocol_harness_controller.py::test_resumed_sidecar_row_is_matched_by_exact_cwd[False]
FAILED tests/test_finalizers_protocol_harness_controller.py::test_stale_checkpoint_after_conflict_fails_closed
FAILED tests/test_finalizers_protocol_harness_controller.py::test_post_submit_edit_is_rejected_before_mutation
FAILED tests/test_finalizers_protocol_harness_controller.py::test_later_finalizer_dirt_reactivates_commit
FAILED tests/test_finalizers_protocol_harness_controller.py::test_identical_stitch_failure_skips_retry_without_spending_budget
FAILED tests/test_finalizers_protocol_harness_controller.py::test_stitch_failure_with_changed_message_still_retries
FAILED tests/test_finalizers_protocol_harness_controller.py::test_controller_no_progress_fails_closed
FAILED tests/test_finalizers_protocol_harness_multi_repo.py::test_sequential_multi_repo_kinds_and_protected_excludes
FAILED tests/test_finalizers_protocol_harness_multi_repo.py::test_reversed_manifest_still_executes_in_host_context_order
FAILED tests/test_finalizers_protocol_harness_multi_repo.py::test_reversed_manifest_first_host_repo_conflict_blocks_later
FAILED tests/test_finalizers_protocol_harness_multi_repo.py::test_first_repo_conflict_blocks_later_dispatch
FAILED tests/test_finalizers_protocol_harness_multi_repo.py::test_repaired_repo_conflict_does_not_starve_later_repo_conflict
FAILED tests/test_finalizers_protocol_harness_multi_repo.py::test_same_repo_second_conflict_after_repair_later_cycle_fails_fast
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_real_controller_success_uses_zero_model_calls
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_stale_or_missing_checks_use_one_recovery[stale_worktree_fingerprint-<lambda>]
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_stale_or_missing_checks_use_one_recovery[missing_required_stage-<lambda>]
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_unsupported_finalizer_uses_one_recovery
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_tree_drift_after_finalizers_uses_one_recovery
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_two_repository_partial_crash_retains_receipts_and_does_not_complete
FAILED tests/monitor/test_monitor_host_completion_controller.py::test_real_declaration_submit_is_not_stubbed_on_success_path
================= 46 failed, 1566 passed in 148.42s (0:02:28) ==================
error: recipe `test-scoped` failed on line 455 with exit code 1

