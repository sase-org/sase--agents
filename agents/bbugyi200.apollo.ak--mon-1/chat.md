# Chat History - ace-run (ak--mon-1)

- **TIMESTAMP:** 2026-10-27 11:42:56 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** ak--mon-1

## Prompt

sase monitor start --command 'just check' --reason 'Verify unstick waiters before host completion'

## Response

sase tool run 93a905d764ddac423b82ed5054280896
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.42.7 is missing 13 capability(s) that exist in a published sase-core release.
[core-floor-probe] agent_publication_protection_wire_schema_version: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] assess_repository_landing_proof: first appears in sase-core 800caef (fix(beads): recover every eligible failed-run close in one mutation); release v0.43.0 contains it.
[core-floor-probe] bead_recover_failed_closes: first appears in sase-core 4f17b72 (feat(beads): recover failed-run closes atomically); release v0.43.0 contains it.
[core-floor-probe] classify_sidecar_publication_push_result: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_empty: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_validate: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_lookup: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_rejection: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_scan: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_resolve_verified_clean: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_retry_allowed: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_upsert: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_scan_disposition: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
{"cache_hit": true, "capabilities": [{"commit": "416db28", "name": "agent_publication_protection_wire_schema_version", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "800caef", "name": "assess_repository_landing_proof", "release": "v0.43.0", "subject": "fix(beads): recover every eligible failed-run close in one mutation"}, {"commit": "4f17b72", "name": "bead_recover_failed_closes", "release": "v0.43.0", "subject": "feat(beads): recover failed-run closes atomically"}, {"commit": "416db28", "name": "classify_sidecar_publication_push_result", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_empty", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_validate", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_lookup", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_rejection", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_scan", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_resolve_verified_clean", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_retry_allowed", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_upsert", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_scan_disposition", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}], "declared_floor": "0.42.7", "exit_code": 3, "message": "sase-core-rs==0.42.7 is missing 13 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-missing, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 5407 test files in scope
coverage contexts: no baseline cached (run `just refresh-contexts-baseline`); static closure only
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: inline-snapshot-0.36.0, cov-7.1.0, anyio-4.15.1, xdist-3.8.0, mock-3.16.0, asyncio-1.4.0, platformdirs-4.13.6, hypothesis-6.168.3
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [2614 items]

........................................................................ [  2%]
........................................................................ [  5%]
......................F.F.F.F........................................... [  8%]
........................................................................ [ 11%]
........................................................................ [ 13%]
........................................................................ [ 16%]
........................................................................ [ 19%]
.........................F...F.......................................... [ 22%]
........................................................................ [ 24%]
........................................................................ [ 27%]
........................................................................ [ 30%]
........................................................................ [ 33%]
........................................................................ [ 35%]
........................................................................ [ 38%]
........................................................................ [ 41%]
...........F............................................................ [ 44%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 52%]
........................................................................ [ 55%]
........................................................................ [ 57%]
........................................................................ [ 60%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 68%]
........................................................................ [ 71%]
........................................................................ [ 74%]
........................................................................ [ 77%]
........................................................................ [ 79%]
........................................................................ [ 82%]
........................................................................ [ 85%]
........................................................................ [ 88%]
........................................................................ [ 90%]
........................................................................ [ 93%]
........................................................................ [ 96%]
........................................................................ [ 99%]
......................                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] _
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agent_session_conversatio0')
level = <FoldLevel.COLLAPSED: 'collapsed'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides1] _
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agent_session_conversatio1')
level = <FoldLevel.EXPANDED: 'expanded'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2] _
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agent_session_conversatio2')
level = <FoldLevel.FULLY_EXPANDED: 'fully_expanded'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.EXHAUSTIVE-overrides3] _
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agent_session_conversatio3')
level = <FoldLevel.EXHAUSTIVE: 'exhaustive'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
________ test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers ________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0')

    def test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers(
        tmp_path: Path,
    ) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        panel = _DetachedPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
            raw_prompt="Read @src/example.py",
        )
    
        result = panel.update_display_with_hints(agent)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert identity.raw_prompt.plain == "Read [1] @src/example.py"
>       assert result.file_hints == {1: str(workspace / "src/example.py")}
E       AssertionError: assert {1: '/var/tmp...c/example.py'} == {1: '/var/tmp...c/example.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Left contains 1 more item:
E         {2: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0/workspace/src/example.py'}
E         
E         Full diff:
E           {
E               1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
E         +     2: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
E           }

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:127: AssertionError
_______________ test_collapsed_detached_raw_prompt_skips_markers _______________
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0')

    def test_collapsed_detached_raw_prompt_skips_markers(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        panel = _CollapsedDetachedPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
            raw_prompt="Read @src/example.py",
        )
        prompt_path = Path(str(agent.artifacts_dir)) / "01_prompt.md"
        prompt_path.write_text("See src/body.py\n", encoding="utf-8")
    
        result = panel.update_display_with_hints(agent)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert identity.raw_prompt.plain == "Read @src/example.py"
        assert "[1]" not in identity.raw_prompt.plain
>       assert str(workspace / "src/example.py") not in result.file_hints.values()
E       AssertionError: assert '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py']) = <built-in method values of dict object at 0x754c272c2640>()
E        +    where <built-in method values of dict object at 0x754c272c2640> = {1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:153: AssertionError
____________ test_current_source_avoids_stale_shell_concept_phrases ____________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_current_source_avoids_stale_shell_concept_phrases() -> None:
        findings: list[str] = []
        candidates = [
            *sorted((_ROOT / "src").rglob("*.py")),
            *sorted((_ROOT / "src").rglob("*.json")),
        ]
        for path in candidates:
            relative = path.relative_to(_ROOT)
            if relative in _SRC_STALE_PHRASE_FILE_ALLOWLIST:
                continue
            content = path.read_text(encoding="utf-8").lower()
            for phrase in _SRC_STALE_PHRASES:
                if (
                    phrase in content
                    and (
                        relative.as_posix(),
                        phrase,
                    )
                    not in _SRC_STALE_PHRASE_ALLOWLIST
                ):
                    findings.append(f"{relative}: {phrase}")
    
>       assert findings == []
E       AssertionError: assert ['src/sase/co...shell member'] == []
E         
E         Left contains one more item: 'src/sase/core/wait_dependency_resolution/_index_entities.py: shell member'
E         
E         Full diff:
E         - []
E         + [
E         +     'src/sase/core/wait_dependency_resolution/_index_entities.py: shell member',
E         + ]

tests/test_sase_turn_terminology.py:261: AssertionError
=============================== warnings summary ===============================
tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
70.21s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
45.12s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
44.09s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
39.78s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
23.72s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
20.32s call     tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales
18.38s call     tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths
16.53s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent
16.12s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
9.70s call     tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
8.42s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
7.34s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
6.54s call     tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms
5.58s call     tests/test_plan_approval_launch_reliability_integration.py::test_combined_tale_approval_to_coder_link_lifecycle[poller_first]
5.49s call     tests/test_macro_terminology.py::test_macro_imports_avoid_xprompt_modules
5.43s call     tests/test_macro_terminology.py::test_macro_source_avoids_xprompt_identifiers
5.40s call     tests/fakey/test_pipe_e2e.py::test_fresh_named_model_pipe_skips_fork_and_records_model
5.02s call     tests/test_macro_terminology.py::test_macro_comments_avoid_xprompt_terms
5.02s call     tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[poller_first-1]
4.90s call     tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[poller_first-2]
=========================== short test summary info ============================
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides1] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXHAUSTIVE-overrides3] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers - AssertionError: assert {1: '/var/tmp...c/example.py'} == {1: '/var/tmp...c/example.py'}
  
  Omitting 1 identical items, use -vv to show
  Left contains 1 more item:
  {2: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0/workspace/src/example.py'}
  
  Full diff:
    {
        1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
  +     2: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
    }
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_collapsed_detached_raw_prompt_skips_markers - AssertionError: assert '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py'])
 +  where '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace') / 'src/example.py'))
 +  and   dict_values(['/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py']) = <built-in method values of dict object at 0x754c272c2640>()
 +    where <built-in method values of dict object at 0x754c272c2640> = {1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py'}.values
 +      where {1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_pr0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_collapsed_detached_raw_... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints
FAILED tests/test_sase_turn_terminology.py::test_current_source_avoids_stale_shell_concept_phrases - AssertionError: assert ['src/sase/co...shell member'] == []
  
  Left contains one more item: 'src/sase/core/wait_dependency_resolution/_index_entities.py: shell member'
  
  Full diff:
  - []
  + [
  +     'src/sase/core/wait_dependency_resolution/_index_entities.py: shell member',
  + ]
=========== 7 failed, 2607 passed, 20 warnings in 507.18s (0:08:27) ============
error: Recipe `test-scoped` failed on line 611 with exit code 1
error: Recipe `check` failed on line 877 with exit code 1
failed  exit=1  duration=1193944ms
unattrib  18.1s
triage test (scoped): 4 NEW stopped
NEW test (scoped): FAILED tests/test_sase_turn_terminology.py::test_current_source_avoids_stale_shell_concept_phrases - AssertionError: assert ['src/sase/co...shell member'] == [] — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n' — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_collapsed_detached_raw_prompt_skips_markers - AssertionError: assert '/var<tmp> not in dict_values(['/var<tmp> — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers - AssertionError: assert {1: '/var/tmp...c/example.py'} == {1: '/var/tmp...c/example.py'} — recorded evidence; no owner
verdict: new_failures — 4 NEW; exit 1

