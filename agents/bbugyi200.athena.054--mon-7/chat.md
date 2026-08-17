# Chat History - ace-run (054--mon-7)

- **TIMESTAMP:** 2026-08-17 14:54:50 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 054--mon-7

## Prompt

sase monitor start --command 'just install && just check' --reason 're-verify the kill_and_edit_force_reuse plan implementation now that master has been fast-forwarded 5 commits (which already fixed the stale symvision epic-symbol whitelist churn that caused the last several failures) and the local working tree now contains only the plan own changes'

## Response

[install] Building sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Finished `release` profile [optimized] target(s) in 0.16s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/.tmpfFyzGJ/sase_core_rs-0.27.18-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.27.18
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 98 packages in 285ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
Prepared 1 package in 542ms
Uninstalled 1 package in 9ms
Installed 1 package in 10ms
 ~ sase==0.16.0 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19)
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

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 2894 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 942 commits behind HEAD) matched 3 changed file(s) and contributed 14 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, asyncio-1.4.0, hypothesis-6.165.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [2746 items]

........................................................................ [  2%]
........................................................................ [  5%]
........................................................................ [  7%]
........................................................................ [ 10%]
........................................................................ [ 13%]
........................................................................ [ 15%]
........................................................................ [ 18%]
........................................................................ [ 20%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 28%]
........................................................................ [ 31%]
........................................................................ [ 34%]
........................................................................ [ 36%]
........................................................................ [ 39%]
........................................................................ [ 41%]
........................................................................ [ 44%]
........................................................................ [ 47%]
........................................................................ [ 49%]
..............F.....FFF................................................. [ 52%]
........................................................................ [ 55%]
........................................................................ [ 57%]
........................................................................ [ 60%]
........................................................................ [ 62%]
........................................................................ [ 65%]
........................................................................ [ 68%]
........................................................................ [ 70%]
........................................................................ [ 73%]
........................................................................ [ 76%]
........................................................................ [ 78%]
........................................................................ [ 81%]
........................................................................ [ 83%]
........................................................................ [ 86%]
........................................................................ [ 89%]
........................................................................ [ 91%]
........................................................................ [ 94%]
........................................................................ [ 97%]
........................................................................ [ 99%]
..........                                                               [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_launcher_qualifies_research_swarm_per_dispatch ______________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-ad89b80b/pytest-of-bryan/pytest-15/popen-gw2/test_launcher_qualifies_resear0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb586bae430>

    @patch("sase.history.prompt.add_or_update_prompt")
    @patch(
        "sase.main.utils.ensure_project_file_and_get_workspace_num",
        return_value=(None, None, None),
    )
    def test_launcher_qualifies_research_swarm_per_dispatch(
        mock_project: MagicMock,
        mock_history: MagicMock,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A later keyed swarm gets a new hood without changing prior prompt text."""
        from sase.agent.launcher import launch_agents_from_cwd
        from sase.agent.names import _registry
    
        del mock_project, mock_history
        monkeypatch.setenv("SASE_HOME", str(tmp_path / ".sase"))
        _registry._CACHE_PATH = None
        _registry._CACHE_SIGNATURE = None
        _registry._CACHE_DATA = None
        marker = tmp_path / ".sase" / "agent_name_auto_migration.json"
        marker.parent.mkdir(parents=True, exist_ok=True)
        marker.write_text(
            '{"schema_version": 1, "completed": true, "migrated_count": 0}\n',
            encoding="utf-8",
        )
        catalog = {
            "research_swarm": XPrompt(
                name="research_swarm",
                content=(
                    "%clan(research.{@1}, description=Research) "
                    "%id:research.{@1}.cdx\n"
                    "CDX\n"
                    "---\n"
                    "%id(cld, clan=research.{@1})\n"
                    "CLD\n"
                    "---\n"
                    "%id(final, clan=research.{@1}) "
                    "%wait:research.{@1}.cdx\n"
                    "Read `research.{@1}.cdx`; #fork:research.{@1}.cld\n"
                    "---\n"
                    "%id(image, clan=research.{@1}) "
                    "%wait:research.{@1}.final\n"
                    "Image"
                ),
            )
        }
    
        with (
            patch.object(Path, "home", return_value=tmp_path),
            patch("sase.agent.xprompt_swarm.get_all_xprompts", return_value=catalog),
            patch(
                "sase.agent.launch_projects.extract_known_project_vcs_launch_ref",
                return_value=None,
            ),
            patch(
                "sase.agent.multi_prompt_launcher.launch_multi_prompt_agents",
                return_value=[],
            ) as launch_multi,
            patch("sase.core.time.generate_timestamp", return_value="260729_093000"),
        ):
            launch_agents_from_cwd("#!research_swarm")
            first_segments = list(launch_multi.call_args.kwargs["segments"])
    
            make_agent(tmp_path, "proj", "first", "research.0.cdx", done=True)
            _registry._CACHE_PATH = None
            _registry._CACHE_SIGNATURE = None
            _registry._CACHE_DATA = None
    
>           launch_agents_from_cwd("#!research_swarm")

tests/test_multi_prompt_launcher_xprompt_groups.py:378: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/agent/launch_cwd.py:27: in launch_agents_from_cwd
    return launch_agents_from_cwd_impl(
src/sase/agent/launch_cwd_agents.py:208: in launch_agents_from_cwd_impl
    validate_launch_name_requests(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

prompts = ['%clan(research.0, description=Research) %id:research.0.cdx\n#git:home CDX', '%id(cld, clan=research.0)\n#git:home CL...me Read `research.0.cdx`; #fork:research.0.cld', '%id(image, clan=research.0) %wait:research.0.final\n#git:home Image']
allow_force_reuse = False, allow_reserved_family_separator_names = False
allow_hyphenated_names = None

    def validate_launch_name_requests(
        prompts: list[str],
        *,
        allow_force_reuse: bool = False,
        allow_reserved_family_separator_names: bool = False,
        allow_hyphenated_names: bool | None = None,
    ) -> None:
        """Validate explicit launch names under the global name allocation lock."""
        if allow_hyphenated_names is not None:
            allow_reserved_family_separator_names = allow_hyphenated_names
    
        requests = _preflight_launch_name_requests(
            prompts,
            allow_force_reuse=allow_force_reuse,
            allow_reserved_family_separator_names=(allow_reserved_family_separator_names),
        )
        if not requests:
            return
    
        from sase.agent.names import (
            agent_name_allocation_lock,
            get_reserved_agent_names,
            get_reserved_clan_names,
            get_reserved_family_names,
            lowest_name_suggestion,
        )
    
        from sase.core.agent_identity_facade import (
            AgentIdentitySnapshot,
            current_owner_agent_name_key,
        )
    
        identity = AgentIdentitySnapshot.current()
        seen: set[str] = set()
        # Load the reserved-name set once per launch instead of per explicit name.
        # ``is_name_reserved`` reloads the registry (and re-runs O(entries) stale-owner
        # checks) on every call, so a multi-prompt launch with N explicit names paid
        # that cost N times. Computing the set once under the allocation lock keeps the
        # same collision contract while making validation independent of segment count.
        reserved_names: set[str] | None = None
        clan_names: set[str] | None = None
        family_names: set[str] | None = None
        reserved_keys: set[str] | None = None
        clan_keys: set[str] | None = None
        family_keys: set[str] | None = None
        with agent_name_allocation_lock():
            for request in requests:
                if request.name_template:
                    continue
                if request.force_reuse:
                    if reserved_names is None:
                        reserved_names = get_reserved_agent_names()
                        clan_names = get_reserved_clan_names()
                        family_names = get_reserved_family_names()
                        reserved_keys = {
                            current_owner_agent_name_key(name, identity)
                            for name in reserved_names
                        }
                        clan_keys = {
                            current_owner_agent_name_key(name, identity)
                            for name in clan_names
                        }
                        family_keys = {
                            current_owner_agent_name_key(name, identity)
                            for name in family_names
                        }
                    request_key = current_owner_agent_name_key(request.name, identity)
                    if clan_keys is not None and request_key in clan_keys:
                        raise _AgentNameClanCollisionError(request.name)
                    if family_keys is not None and request_key in family_keys:
                        raise _AgentNameFamilyCollisionError(request.name)
                    continue
                if reserved_names is None:
                    reserved_names = get_reserved_agent_names()
                    clan_names = get_reserved_clan_names()
                    family_names = get_reserved_family_names()
                    reserved_keys = {
                        current_owner_agent_name_key(name, identity)
                        for name in reserved_names
                    }
                    clan_keys = {
                        current_owner_agent_name_key(name, identity) for name in clan_names
                    }
                    family_keys = {
                        current_owner_agent_name_key(name, identity)
                        for name in family_names
                    }
                request_key = current_owner_agent_name_key(request.name, identity)
                assert reserved_keys is not None
                if request_key in seen or request_key in reserved_keys:
                    if clan_keys is not None and request_key in clan_keys:
                        raise _AgentNameClanCollisionError(request.name)
                    if family_keys is not None and request_key in family_keys:
                        raise _AgentNameFamilyCollisionError(request.name)
>                   raise AgentNameLaunchCollisionError(
                        request.name, lowest_name_suggestion(request.name)
                    )
E                   sase.agent.launch_validation.AgentNameLaunchCollisionError: Agent name 'research.0.cdx' is taken. Try 'research.0.cdx1'.

src/sase/agent/launch_validation.py:315: AgentNameLaunchCollisionError
___________ test_launch_query_rolls_back_partial_multi_prompt_launch ___________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb586bafaf0>
capsys = <_pytest.capture.CaptureFixture object at 0x7fb588cb8ec0>

    def test_launch_query_rolls_back_partial_multi_prompt_launch(
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        from sase.agent.multi_prompt_launcher import _MultiPromptPartialLaunchError
        from sase.main.query_handler import _launch
    
        result = _launch_result()
    
        def fail_launch(query: str) -> list[AgentLaunchResult]:
            del query
            raise _MultiPromptPartialLaunchError([result], RuntimeError("boom"))
    
        rollback = MagicMock(
            return_value=SimpleNamespace(
                terminated_pids=(result.pid,),
                released_workspaces=((result.project_file, result.workspace_num),),
            )
        )
        _clear_agent_launch_gate_env(monkeypatch)
        monkeypatch.setattr(_launch, "launch_agents_from_cwd", fail_launch)
        monkeypatch.setattr(
            "sase.agent.partial_launch.rollback_partial_launch_results", rollback
        )
    
        with pytest.raises(SystemExit) as exc_info:
>           _launch.launch_query("one\n---\ntwo")

tests/test_partial_launch_cleanup.py:92: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'one\n---\ntwo'

    def launch_query(query: str) -> None:
        """Launch *query* as detached background agent process(es).
    
        Replicates the TUI ``@`` keybinding behaviour without TUI dependencies.
        The spawned agent appears in the TUI Agents tab.
    
        For multi-prompt queries (containing ``---`` separators), all segments
        are launched sequentially before this function returns.
        """
        from sase.ops.cli import load_request
        from sase.ops.names import RUN_LAUNCH
    
        request = load_request(RUN_LAUNCH)
        payload = dict(request.payload)
        if isinstance(payload.get("prompt"), str) and payload["prompt"]:
            query = payload["prompt"]
        allow_force_reuse = bool(payload.get("allow_force_reuse"))
        from sase.agent.prompt_inputs import missing_required_input_names
    
        missing_inputs = missing_required_input_names(query)
        if missing_inputs:
            from sase.output import print_status
            from sase.ops.commands.run import emit_run_launch_result
    
            names = ", ".join(missing_inputs)
            message = (
                f"Prompt declares required input(s) without defaults: {names}. "
                "Interactive input collection is only available in `sase ace`; "
                "add a default to each input or launch from the TUI."
            )
            print_status(message, "error")
            emit_run_launch_result(success=False, message=message)
            sys.exit(1)
    
        from sase.output import print_status
        from sase.xprompt.unresolved import (
            format_unresolved_reference_warning,
            scan_query_for_unresolved_references,
        )
    
        for name in scan_query_for_unresolved_references(query):
            print_status(format_unresolved_reference_warning(name), "warning")
    
        from sase.agent.launch_request import (
            LaunchRequestError,
            cancel_launch_approval_request,
            create_launch_approval_request_from_prompt,
            running_agent_context_requires_launch_approval,
            wait_for_launch_approval,
        )
    
        if running_agent_context_requires_launch_approval():
            try:
                approval_request = create_launch_approval_request_from_prompt(
                    query,
                    reason="Running agent requested a detached launch.",
                    source_surface="agent_skill",
                )
            except LaunchRequestError as exc:
                print(f"Error: {exc}", file=sys.stderr)
                sys.exit(1)
            try:
                outcome = wait_for_launch_approval(approval_request)
            except KeyboardInterrupt:
                try:
                    cancel_launch_approval_request(approval_request)
                except LaunchRequestError:
                    pass
                print("Launch request cancelled", file=sys.stderr)
                sys.exit(130)
            print(json.dumps(outcome.to_dict(), sort_keys=True))
            sys.exit(0)
    
        segment_extra_env = None
        if allow_force_reuse:
            from sase.agent.force_reuse_launch import (
                apply_force_reuse_launch,
                plan_force_reuse_launch,
            )
            from sase.history.prompt import record_failed_launch_prompt
            from sase.ops.commands.run import emit_run_launch_result
    
            try:
                force_reuse_plan = plan_force_reuse_launch(query)
            except RuntimeError as exc:
                message = str(exc)
                record_failed_launch_prompt(query)
                print(f"Error: {message}", file=sys.stderr)
                emit_run_launch_result(success=False, message=message)
                sys.exit(1)
            if force_reuse_plan is not None:
                try:
                    apply_force_reuse_launch(force_reuse_plan)
                except Exception as exc:
                    message = f"Agent name reuse failed: {exc}"
                    record_failed_launch_prompt(query)
                    print(f"Error: {message}", file=sys.stderr)
                    emit_run_launch_result(success=False, message=message)
                    sys.exit(1)
                query = force_reuse_plan.rewritten_prompt
                segment_extra_env = force_reuse_plan.segment_envs
    
        try:
>           results = launch_agents_from_cwd(query, segment_extra_env=segment_extra_env)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E           TypeError: test_launch_query_rolls_back_partial_multi_prompt_launch.<locals>.fail_launch() got an unexpected keyword argument 'segment_extra_env'

src/sase/main/query_handler/_launch.py:112: TypeError
_______________ test_launch_query_prints_each_launched_agent_pid _______________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb5861390f0>
capsys = <_pytest.capture.CaptureFixture object at 0x7fb588ccb4d0>

    def test_launch_query_prints_each_launched_agent_pid(
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        from dataclasses import replace
    
        from sase.main.query_handler import _launch
    
        first = _launch_result()
        second = replace(first, pid=5678, workspace_num=8)
        _clear_agent_launch_gate_env(monkeypatch)
        monkeypatch.setattr(
            _launch,
            "launch_agents_from_cwd",
            lambda _query: [first, second],
        )
    
        with pytest.raises(SystemExit) as exc_info:
>           _launch.launch_query("one\n---\ntwo")

tests/test_partial_launch_cleanup.py:119: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'one\n---\ntwo'

    def launch_query(query: str) -> None:
        """Launch *query* as detached background agent process(es).
    
        Replicates the TUI ``@`` keybinding behaviour without TUI dependencies.
        The spawned agent appears in the TUI Agents tab.
    
        For multi-prompt queries (containing ``---`` separators), all segments
        are launched sequentially before this function returns.
        """
        from sase.ops.cli import load_request
        from sase.ops.names import RUN_LAUNCH
    
        request = load_request(RUN_LAUNCH)
        payload = dict(request.payload)
        if isinstance(payload.get("prompt"), str) and payload["prompt"]:
            query = payload["prompt"]
        allow_force_reuse = bool(payload.get("allow_force_reuse"))
        from sase.agent.prompt_inputs import missing_required_input_names
    
        missing_inputs = missing_required_input_names(query)
        if missing_inputs:
            from sase.output import print_status
            from sase.ops.commands.run import emit_run_launch_result
    
            names = ", ".join(missing_inputs)
            message = (
                f"Prompt declares required input(s) without defaults: {names}. "
                "Interactive input collection is only available in `sase ace`; "
                "add a default to each input or launch from the TUI."
            )
            print_status(message, "error")
            emit_run_launch_result(success=False, message=message)
            sys.exit(1)
    
        from sase.output import print_status
        from sase.xprompt.unresolved import (
            format_unresolved_reference_warning,
            scan_query_for_unresolved_references,
        )
    
        for name in scan_query_for_unresolved_references(query):
            print_status(format_unresolved_reference_warning(name), "warning")
    
        from sase.agent.launch_request import (
            LaunchRequestError,
            cancel_launch_approval_request,
            create_launch_approval_request_from_prompt,
            running_agent_context_requires_launch_approval,
            wait_for_launch_approval,
        )
    
        if running_agent_context_requires_launch_approval():
            try:
                approval_request = create_launch_approval_request_from_prompt(
                    query,
                    reason="Running agent requested a detached launch.",
                    source_surface="agent_skill",
                )
            except LaunchRequestError as exc:
                print(f"Error: {exc}", file=sys.stderr)
                sys.exit(1)
            try:
                outcome = wait_for_launch_approval(approval_request)
            except KeyboardInterrupt:
                try:
                    cancel_launch_approval_request(approval_request)
                except LaunchRequestError:
                    pass
                print("Launch request cancelled", file=sys.stderr)
                sys.exit(130)
            print(json.dumps(outcome.to_dict(), sort_keys=True))
            sys.exit(0)
    
        segment_extra_env = None
        if allow_force_reuse:
            from sase.agent.force_reuse_launch import (
                apply_force_reuse_launch,
                plan_force_reuse_launch,
            )
            from sase.history.prompt import record_failed_launch_prompt
            from sase.ops.commands.run import emit_run_launch_result
    
            try:
                force_reuse_plan = plan_force_reuse_launch(query)
            except RuntimeError as exc:
                message = str(exc)
                record_failed_launch_prompt(query)
                print(f"Error: {message}", file=sys.stderr)
                emit_run_launch_result(success=False, message=message)
                sys.exit(1)
            if force_reuse_plan is not None:
                try:
                    apply_force_reuse_launch(force_reuse_plan)
                except Exception as exc:
                    message = f"Agent name reuse failed: {exc}"
                    record_failed_launch_prompt(query)
                    print(f"Error: {message}", file=sys.stderr)
                    emit_run_launch_result(success=False, message=message)
                    sys.exit(1)
                query = force_reuse_plan.rewritten_prompt
                segment_extra_env = force_reuse_plan.segment_envs
    
        try:
>           results = launch_agents_from_cwd(query, segment_extra_env=segment_extra_env)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E           TypeError: test_launch_query_prints_each_launched_agent_pid.<locals>.<lambda>() got an unexpected keyword argument 'segment_extra_env'

src/sase/main/query_handler/_launch.py:112: TypeError
_______ test_launch_query_warns_on_unresolved_xprompt_and_still_launches _______
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb586138d70>
capsys = <_pytest.capture.CaptureFixture object at 0x7fb588ccb9d0>

    def test_launch_query_warns_on_unresolved_xprompt_and_still_launches(
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        from sase.main.query_handler import _launch
    
        warnings: list[tuple[str, str]] = []
        _clear_agent_launch_gate_env(monkeypatch)
        monkeypatch.setattr(
            "sase.xprompt.unresolved.scan_query_for_unresolved_references",
            lambda _query: ("reviewww",),
        )
        monkeypatch.setattr("sase.xprompt.loader.get_all_prompts", lambda: {})
        monkeypatch.setattr(
            "sase.output.print_status",
            lambda message, status: warnings.append((message, status)),
        )
        monkeypatch.setattr(
            _launch,
            "launch_agents_from_cwd",
            lambda _query: [_launch_result()],
        )
    
        with pytest.raises(SystemExit) as exc_info:
>           _launch.launch_query("do work #reviewww")

tests/test_partial_launch_cleanup.py:152: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

query = 'do work #reviewww'

    def launch_query(query: str) -> None:
        """Launch *query* as detached background agent process(es).
    
        Replicates the TUI ``@`` keybinding behaviour without TUI dependencies.
        The spawned agent appears in the TUI Agents tab.
    
        For multi-prompt queries (containing ``---`` separators), all segments
        are launched sequentially before this function returns.
        """
        from sase.ops.cli import load_request
        from sase.ops.names import RUN_LAUNCH
    
        request = load_request(RUN_LAUNCH)
        payload = dict(request.payload)
        if isinstance(payload.get("prompt"), str) and payload["prompt"]:
            query = payload["prompt"]
        allow_force_reuse = bool(payload.get("allow_force_reuse"))
        from sase.agent.prompt_inputs import missing_required_input_names
    
        missing_inputs = missing_required_input_names(query)
        if missing_inputs:
            from sase.output import print_status
            from sase.ops.commands.run import emit_run_launch_result
    
            names = ", ".join(missing_inputs)
            message = (
                f"Prompt declares required input(s) without defaults: {names}. "
                "Interactive input collection is only available in `sase ace`; "
                "add a default to each input or launch from the TUI."
            )
            print_status(message, "error")
            emit_run_launch_result(success=False, message=message)
            sys.exit(1)
    
        from sase.output import print_status
        from sase.xprompt.unresolved import (
            format_unresolved_reference_warning,
            scan_query_for_unresolved_references,
        )
    
        for name in scan_query_for_unresolved_references(query):
            print_status(format_unresolved_reference_warning(name), "warning")
    
        from sase.agent.launch_request import (
            LaunchRequestError,
            cancel_launch_approval_request,
            create_launch_approval_request_from_prompt,
            running_agent_context_requires_launch_approval,
            wait_for_launch_approval,
        )
    
        if running_agent_context_requires_launch_approval():
            try:
                approval_request = create_launch_approval_request_from_prompt(
                    query,
                    reason="Running agent requested a detached launch.",
                    source_surface="agent_skill",
                )
            except LaunchRequestError as exc:
                print(f"Error: {exc}", file=sys.stderr)
                sys.exit(1)
            try:
                outcome = wait_for_launch_approval(approval_request)
            except KeyboardInterrupt:
                try:
                    cancel_launch_approval_request(approval_request)
                except LaunchRequestError:
                    pass
                print("Launch request cancelled", file=sys.stderr)
                sys.exit(130)
            print(json.dumps(outcome.to_dict(), sort_keys=True))
            sys.exit(0)
    
        segment_extra_env = None
        if allow_force_reuse:
            from sase.agent.force_reuse_launch import (
                apply_force_reuse_launch,
                plan_force_reuse_launch,
            )
            from sase.history.prompt import record_failed_launch_prompt
            from sase.ops.commands.run import emit_run_launch_result
    
            try:
                force_reuse_plan = plan_force_reuse_launch(query)
            except RuntimeError as exc:
                message = str(exc)
                record_failed_launch_prompt(query)
                print(f"Error: {message}", file=sys.stderr)
                emit_run_launch_result(success=False, message=message)
                sys.exit(1)
            if force_reuse_plan is not None:
                try:
                    apply_force_reuse_launch(force_reuse_plan)
                except Exception as exc:
                    message = f"Agent name reuse failed: {exc}"
                    record_failed_launch_prompt(query)
                    print(f"Error: {message}", file=sys.stderr)
                    emit_run_launch_result(success=False, message=message)
                    sys.exit(1)
                query = force_reuse_plan.rewritten_prompt
                segment_extra_env = force_reuse_plan.segment_envs
    
        try:
>           results = launch_agents_from_cwd(query, segment_extra_env=segment_extra_env)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E           TypeError: test_launch_query_warns_on_unresolved_xprompt_and_still_launches.<locals>.<lambda>() got an unexpected keyword argument 'segment_extra_env'

src/sase/main/query_handler/_launch.py:112: TypeError
============================= slowest 20 durations =============================
8.97s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
4.45s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_partial_line
2.67s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
2.44s call     tests/monitor/test_monitor_start.py::test_start_monitor_refuses_a_numbered_cwd_claimed_by_another_live_agent
2.19s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child
2.14s call     tests/ace/tui/test_agent_collapsed_panel_kill.py::test_confirming_last_panel_member_preserves_neighbors_and_valid_focus
2.02s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
1.85s call     tests/monitor/test_monitor_start.py::test_monitor_claim_survives_stale_cleanup_allocation_and_followup_transfer
1.83s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_kills_the_whole_process_group_on_timeout
1.81s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_continuous_output
1.78s call     tests/monitor/test_monitor_start.py::test_start_monitor_epic_launch_from_non_numbered_cwd_uses_workspace_zero
1.78s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_child_closes_stdio
1.78s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_completes_when_grandchild_holds_stdout
1.67s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls
1.60s call     tests/main/test_monitor_handler_start.py::test_start_prints_the_summary_before_the_agent_runner_handoff_kill
1.58s call     tests/monitor/test_monitor_supervise.py::test_supervisor_subprocess_stops_cleanly_on_sigterm
1.57s call     tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion
1.57s call     tests/monitor/test_monitor_start.py::test_start_monitor_without_metadata_workspace_num_claims_the_cwd_checkout
1.56s call     tests/test_fork_workflow.py::test_embedded_single_parent_fork_keeps_legacy_envelope
1.55s call     tests/test_fork_workflow.py::test_embedded_family_fork_injects_each_completed_member_reply_once
=========================== short test summary info ============================
FAILED tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch
FAILED tests/test_partial_launch_cleanup.py::test_launch_query_rolls_back_partial_multi_prompt_launch
FAILED tests/test_partial_launch_cleanup.py::test_launch_query_prints_each_launched_agent_pid
FAILED tests/test_partial_launch_cleanup.py::test_launch_query_warns_on_unresolved_xprompt_and_still_launches
================== 4 failed, 2742 passed in 120.95s (0:02:00) ==================
error: recipe `test-scoped` failed on line 433 with exit code 1
error: recipe `check` failed on line 626 with exit code 1

