# Chat History - ace-run (054--mon-8)

- **TIMESTAMP:** 2026-08-17 15:01:20 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 054--mon-8

## Prompt

sase monitor start --command 'just check' --reason 'Re-verify kill_and_edit_force_reuse plan implementation after making segment_extra_env kwarg conditional in _launch.py (only pass it when force-reuse actually produced a plan), which fixes the TypeError raised in test_partial_launch_cleanup.py and test_multi_prompt_launcher_xprompt_groups.py against single-arg launch_agents_from_cwd lambdas'

## Response

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
........................................................F............... [ 49%]
........................................................................ [ 52%]
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
.......FF............................................................... [ 94%]
........................................................................ [ 97%]
........................................................................ [ 99%]
..........                                                               [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_launcher_qualifies_research_swarm_per_dispatch ______________
[gw3] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-ad89b80b/pytest-of-bryan/pytest-16/popen-gw3/test_launcher_qualifies_resear0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe6a7f4f2a0>

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
____ test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse ____
[gw3] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

self = <MagicMock name='launch_agents_from_cwd' id='140628628571536'>
args = ('%id:!foo\nDo work',), kwargs = {'segment_extra_env': None}

    def assert_called_with(self, /, *args, **kwargs):
        """assert that the last call was made with the specified arguments.
    
        Raises an AssertionError if the args and keyword args passed in are
        different to the last call to the mock."""
        if self.call_args is None:
            expected = self._format_mock_call_signature(args, kwargs)
            actual = 'not called.'
            error_message = ('expected call not found.\nExpected: %s\n  Actual: %s'
                    % (expected, actual))
            raise AssertionError(error_message)
    
        def _error_message():
            msg = self._format_mock_failure_message(args, kwargs)
            return msg
        expected = self._call_matcher(_Call((args, kwargs), two=True))
        actual = self._call_matcher(self.call_args)
        if actual != expected:
            cause = expected if isinstance(expected, Exception) else None
>           raise AssertionError(_error_message()) from cause
E           AssertionError: expected call not found.
E           Expected: launch_agents_from_cwd('%id:!foo\nDo work', segment_extra_env=None)
E             Actual: launch_agents_from_cwd('%id:!foo\nDo work')

../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:985: AssertionError

During handling of the above exception, another exception occurred:

self = <MagicMock name='launch_agents_from_cwd' id='140628628571536'>
args = ('%id:!foo\nDo work',), kwargs = {'segment_extra_env': None}

    def assert_called_once_with(self, /, *args, **kwargs):
        """assert that the mock was called exactly once and that that call was
        with the specified arguments."""
        if not self.call_count == 1:
            msg = ("Expected '%s' to be called once. Called %s times.%s"
                   % (self._mock_name or 'mock',
                      self.call_count,
                      self._calls_repr()))
            raise AssertionError(msg)
>       return self.assert_called_with(*args, **kwargs)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError: expected call not found.
E       Expected: launch_agents_from_cwd('%id:!foo\nDo work', segment_extra_env=None)
E         Actual: launch_agents_from_cwd('%id:!foo\nDo work')
E       
E       pytest introspection follows:
E       
E       Kwargs:
E       assert {} == {'segment_extra_env': None}
E         
E         Right contains 1 more item:
E         {'segment_extra_env': None}
E         Use -v to get more diff

../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:997: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe6aba78670>

    def test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
>       _run_launch_query_unauthorized(
            "%id:!foo\nDo work", request=None, monkeypatch=monkeypatch
        )

tests/test_force_reuse_launch_seam.py:233: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

prompt = '%id:!foo\nDo work', request = None
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe6aba78670>

    def _run_launch_query_unauthorized(
        prompt: str,
        *,
        request: DurableOperationRequest | None,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        from sase.agent.launch_validation import AgentNameReuseConfirmationRequiredError
        from sase.main.query_handler._launch import launch_query
    
        monkeypatch.delenv("SASE_AGENT", raising=False)
        load_request_patch = (
            patch("sase.ops.cli.load_request", return_value=request)
            if request is not None
            else patch("sase.ops.cli.resolve_request_path", return_value=None)
        )
        with (
            load_request_patch,
            patch("sase.agent.prompt_inputs.missing_required_input_names", return_value=[]),
            patch(
                "sase.xprompt.unresolved.scan_query_for_unresolved_references",
                return_value=[],
            ),
            patch(
                "sase.main.query_handler._launch.launch_agents_from_cwd",
                side_effect=AgentNameReuseConfirmationRequiredError("foo"),
            ) as mock_launch,
            pytest.raises(SystemExit) as excinfo,
        ):
            launch_query(prompt)
    
        assert excinfo.value.code == 1
        # No authorization means no force-reuse rewrite/wipe: the untouched
        # (still-``!``) prompt reaches the same validation the child always ran.
>       mock_launch.assert_called_once_with(prompt, segment_extra_env=None)
E       AssertionError: expected call not found.
E       Expected: launch_agents_from_cwd('%id:!foo\nDo work', segment_extra_env=None)
E         Actual: launch_agents_from_cwd('%id:!foo\nDo work')
E       
E       pytest introspection follows:
E       
E       Kwargs:
E       assert {} == {'segment_extra_env': None}
E         
E         Right contains 1 more item:
E         {'segment_extra_env': None}
E         Use -v to get more diff

tests/test_force_reuse_launch_seam.py:227: AssertionError
----------------------------- Captured stderr call -----------------------------
Error: Agent name 'foo' uses forced reuse; confirmation is required.
________ test_sidecar_without_authorization_still_rejects_forced_reuse _________
[gw3] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

self = <MagicMock name='launch_agents_from_cwd' id='140628628578928'>
args = ('%id:!foo\nDo work',), kwargs = {'segment_extra_env': None}

    def assert_called_with(self, /, *args, **kwargs):
        """assert that the last call was made with the specified arguments.
    
        Raises an AssertionError if the args and keyword args passed in are
        different to the last call to the mock."""
        if self.call_args is None:
            expected = self._format_mock_call_signature(args, kwargs)
            actual = 'not called.'
            error_message = ('expected call not found.\nExpected: %s\n  Actual: %s'
                    % (expected, actual))
            raise AssertionError(error_message)
    
        def _error_message():
            msg = self._format_mock_failure_message(args, kwargs)
            return msg
        expected = self._call_matcher(_Call((args, kwargs), two=True))
        actual = self._call_matcher(self.call_args)
        if actual != expected:
            cause = expected if isinstance(expected, Exception) else None
>           raise AssertionError(_error_message()) from cause
E           AssertionError: expected call not found.
E           Expected: launch_agents_from_cwd('%id:!foo\nDo work', segment_extra_env=None)
E             Actual: launch_agents_from_cwd('%id:!foo\nDo work')

../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:985: AssertionError

During handling of the above exception, another exception occurred:

self = <MagicMock name='launch_agents_from_cwd' id='140628628578928'>
args = ('%id:!foo\nDo work',), kwargs = {'segment_extra_env': None}

    def assert_called_once_with(self, /, *args, **kwargs):
        """assert that the mock was called exactly once and that that call was
        with the specified arguments."""
        if not self.call_count == 1:
            msg = ("Expected '%s' to be called once. Called %s times.%s"
                   % (self._mock_name or 'mock',
                      self.call_count,
                      self._calls_repr()))
            raise AssertionError(msg)
>       return self.assert_called_with(*args, **kwargs)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError: expected call not found.
E       Expected: launch_agents_from_cwd('%id:!foo\nDo work', segment_extra_env=None)
E         Actual: launch_agents_from_cwd('%id:!foo\nDo work')
E       
E       pytest introspection follows:
E       
E       Kwargs:
E       assert {} == {'segment_extra_env': None}
E         
E         Right contains 1 more item:
E         {'segment_extra_env': None}
E         Use -v to get more diff

../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/unittest/mock.py:997: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe6aa378fa0>

    def test_sidecar_without_authorization_still_rejects_forced_reuse(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        request = DurableOperationRequest(
            operation=RUN_LAUNCH,
            payload={"prompt": "%id:!foo\nDo work", "workflow": "w"},
        )
>       _run_launch_query_unauthorized(
            "%id:!foo\nDo work", request=request, monkeypatch=monkeypatch
        )

tests/test_force_reuse_launch_seam.py:245: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

prompt = '%id:!foo\nDo work'
request = DurableOperationRequest(operation='run.launch', payload={'prompt': '%id:!foo\nDo work', 'workflow': 'w'}, schema_version=1)
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe6aa378fa0>

    def _run_launch_query_unauthorized(
        prompt: str,
        *,
        request: DurableOperationRequest | None,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        from sase.agent.launch_validation import AgentNameReuseConfirmationRequiredError
        from sase.main.query_handler._launch import launch_query
    
        monkeypatch.delenv("SASE_AGENT", raising=False)
        load_request_patch = (
            patch("sase.ops.cli.load_request", return_value=request)
            if request is not None
            else patch("sase.ops.cli.resolve_request_path", return_value=None)
        )
        with (
            load_request_patch,
            patch("sase.agent.prompt_inputs.missing_required_input_names", return_value=[]),
            patch(
                "sase.xprompt.unresolved.scan_query_for_unresolved_references",
                return_value=[],
            ),
            patch(
                "sase.main.query_handler._launch.launch_agents_from_cwd",
                side_effect=AgentNameReuseConfirmationRequiredError("foo"),
            ) as mock_launch,
            pytest.raises(SystemExit) as excinfo,
        ):
            launch_query(prompt)
    
        assert excinfo.value.code == 1
        # No authorization means no force-reuse rewrite/wipe: the untouched
        # (still-``!``) prompt reaches the same validation the child always ran.
>       mock_launch.assert_called_once_with(prompt, segment_extra_env=None)
E       AssertionError: expected call not found.
E       Expected: launch_agents_from_cwd('%id:!foo\nDo work', segment_extra_env=None)
E         Actual: launch_agents_from_cwd('%id:!foo\nDo work')
E       
E       pytest introspection follows:
E       
E       Kwargs:
E       assert {} == {'segment_extra_env': None}
E         
E         Right contains 1 more item:
E         {'segment_extra_env': None}
E         Use -v to get more diff

tests/test_force_reuse_launch_seam.py:227: AssertionError
----------------------------- Captured stderr call -----------------------------
Error: Agent name 'foo' uses forced reuse; confirmation is required.
============================= slowest 20 durations =============================
8.86s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
4.81s call     tests/main/test_monitor_handler_start.py::test_start_implicit_family_member_uses_caller_workspace_without_agent_flag
4.76s call     tests/monitor/test_monitor_followup.py::test_launch_followup_agent_attaches_to_the_lane_and_transfers_the_claim
4.47s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_partial_line
4.37s call     tests/test_dismissed_agent_lifecycle.py::test_workflow_parent_and_children_consistent_through_lifecycle
4.25s call     tests/main/test_monitor_handler_start.py::test_start_json_envelope_is_stable
4.20s call     tests/monitor/test_monitor_start.py::test_start_monitor_refuses_a_numbered_cwd_claimed_by_another_live_agent
3.59s call     tests/test_fork_workflow.py::test_embedded_multi_parent_fork_renders_provenance_envelope[#fork(planner, coder)]
3.52s call     tests/monitor/test_monitor_followup.py::test_launch_followup_agent_omits_the_fork_prefix_when_the_starter_never_settles
3.40s call     tests/test_fork_workflow.py::test_embedded_single_parent_fork_keeps_legacy_envelope
3.34s call     tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_retry_does_not_unmark_already_ready_epic_on_launch_failure
3.30s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls
3.24s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child
2.97s call     tests/main/test_monitor_handler_start.py::test_start_json_envelope_reports_handed_off_before_the_kill
2.97s call     tests/test_fork_workflow.py::test_embedded_bare_resume_loads_resolved_chat_path
2.85s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_continuous_output
2.74s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_child_closes_stdio
2.64s call     tests/monitor/test_monitor_start.py::test_monitor_claim_survives_stale_cleanup_allocation_and_followup_transfer
2.63s call     tests/test_fork_workflow.py::test_embedded_multi_parent_fork_renders_provenance_envelope[#fork:planner,coder]
2.62s call     tests/monitor/test_monitor_supervise.py::test_run_supervisor_survives_invalid_utf8_output
=========================== short test summary info ============================
FAILED tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch
FAILED tests/test_force_reuse_launch_seam.py::test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse
FAILED tests/test_force_reuse_launch_seam.py::test_sidecar_without_authorization_still_rejects_forced_reuse
================== 3 failed, 2743 passed in 115.43s (0:01:55) ==================
error: recipe `test-scoped` failed on line 433 with exit code 1
error: recipe `check` failed on line 626 with exit code 1

