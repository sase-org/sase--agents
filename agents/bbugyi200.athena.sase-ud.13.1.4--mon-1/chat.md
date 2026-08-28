# Chat History - ace-run (sase-ud.13.1.4--mon-1)

- **TIMESTAMP:** 2026-08-28 11:29:33 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-ud.13.1.4--mon-1

## Prompt

sase monitor start --command 'just check && just check-full && just test-visual' --reason 'Rerun just check plus required full-suite and ACE PNG visual verification for bead sase-ud.13.1.4 after registering the TUI ref-prefix dispatch audit as a dirty-tree source-audit root'

## Response

[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.32.12 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.31.12,<0.32.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.31.12 is missing 5 capability(s) that exist in a published sase-core release.
[core-floor-probe] bead_note_edit: first appears in sase-core f06a103 (feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations); release v0.32.4 contains it.
[core-floor-probe] bead_note_remove: first appears in sase-core f06a103 (feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations); release v0.32.4 contains it.
[core-floor-probe] load_agent_artifact_records: first appears in sase-core bdce575 (feat(agent-scan): project list-shaped artifact records); release v0.32.11 contains it.
[core-floor-probe] scan_agent_artifacts: first appears in sase-core f5e9c25 (feat: Phase 3C — sase_core_rs.scan_agent_artifacts PyO3 binding (sase-18.3)); release v0.1.1 contains it.
[core-floor-probe] vacuum_agent_artifact_index: first appears in sase-core b786e90 (feat(agent-scan): add read-only index opens and a VACUUM binding); release v0.32.10 contains it.
{"cache_hit": true, "capabilities": [{"commit": "f06a103", "name": "bead_note_edit", "release": "v0.32.4", "subject": "feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations"}, {"commit": "f06a103", "name": "bead_note_remove", "release": "v0.32.4", "subject": "feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations"}, {"commit": "bdce575", "name": "load_agent_artifact_records", "release": "v0.32.11", "subject": "feat(agent-scan): project list-shaped artifact records"}, {"commit": "f5e9c25", "name": "scan_agent_artifacts", "release": "v0.1.1", "subject": "feat: Phase 3C \u2014 sase_core_rs.scan_agent_artifacts PyO3 binding (sase-18.3)"}, {"commit": "b786e90", "name": "vacuum_agent_artifact_index", "release": "v0.32.10", "subject": "feat(agent-scan): add read-only index opens and a VACUUM binding"}], "declared_floor": "0.31.12", "exit_code": 3, "message": "sase-core-rs==0.31.12 is missing 5 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✓ test (scoped)
scoped: selected 1306 of 3467 test files (37.7%; rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); contexts baseline stale; est 2207s/232s; gear 4 workers
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.32.12 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.31.12,<0.32.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.31.12 is missing 5 capability(s) that exist in a published sase-core release.
[core-floor-probe] bead_note_edit: first appears in sase-core f06a103 (feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations); release v0.32.4 contains it.
[core-floor-probe] bead_note_remove: first appears in sase-core f06a103 (feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations); release v0.32.4 contains it.
[core-floor-probe] load_agent_artifact_records: first appears in sase-core bdce575 (feat(agent-scan): project list-shaped artifact records); release v0.32.11 contains it.
[core-floor-probe] scan_agent_artifacts: first appears in sase-core f5e9c25 (feat: Phase 3C — sase_core_rs.scan_agent_artifacts PyO3 binding (sase-18.3)); release v0.1.1 contains it.
[core-floor-probe] vacuum_agent_artifact_index: first appears in sase-core b786e90 (feat(agent-scan): add read-only index opens and a VACUUM binding); release v0.32.10 contains it.
{"cache_hit": true, "capabilities": [{"commit": "f06a103", "name": "bead_note_edit", "release": "v0.32.4", "subject": "feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations"}, {"commit": "f06a103", "name": "bead_note_remove", "release": "v0.32.4", "subject": "feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations"}, {"commit": "bdce575", "name": "load_agent_artifact_records", "release": "v0.32.11", "subject": "feat(agent-scan): project list-shaped artifact records"}, {"commit": "f5e9c25", "name": "scan_agent_artifacts", "release": "v0.1.1", "subject": "feat: Phase 3C \u2014 sase_core_rs.scan_agent_artifacts PyO3 binding (sase-18.3)"}, {"commit": "b786e90", "name": "vacuum_agent_artifact_index", "release": "v0.32.10", "subject": "feat(agent-scan): add read-only index opens and a VACUUM binding"}], "declared_floor": "0.31.12", "exit_code": 3, "message": "sase-core-rs==0.31.12 is missing 5 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✓ test cost
test cost budget advisories: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260828T152546Z-3140029.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] causes.ace_page_enter: actual 848.203 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=847.907s, count=665)
- [advisory] causes.ace_settle_pilot: actual 399.380 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=362.846s, count=6815)
- [advisory] causes.pilot_pause_delay: actual 331.177 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=326.065s, count=13710)
- [advisory] causes.textual_app_run_test_enter: actual 707.703 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=708.460s, count=3637)
✓ flake baseline
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.32.12 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.31.12,<0.32.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [842 items]

........................................................................ [  8%]
........................................................................ [ 17%]
........................................................................ [ 25%]
..............................................................F......... [ 34%]
..........F...F................F........................................ [ 42%]
....................F.F..........F....................................F. [ 51%]
...F......................................................F...........F. [ 59%]
...F...............F..F................................................. [ 68%]
........................................................................ [ 76%]
........................................................................ [ 85%]
........................................................................ [ 94%]
..................................................                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
______________ test_python_step_parent_family_footer_png_snapshot ______________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...nts_families.py', test_line=127, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7bec794e0>

    async def test_python_step_parent_family_footer_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 22, 6, 30, 0))
        patch_startup_loaders(monkeypatch, agents=parent_navigation_family_agents())
    
        async with AcePage(query='"visual-house-navigation"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await page.press("l", "l")
            await page.expect_state("agent_count", 5)
            for _ in range(5):
                if page.app._agents[page.app.current_idx].cl_name == "setup":
                    break
                await page.press("j")
            else:
                raise AssertionError("hidden Python setup row was not selectable")
            await wait_for_visual_idle(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            bindings, _mode_label = footer._last_layout_inputs
            assert ("h", "parent family") in bindings
            assert_page_svg_contains(page, "setup")
            assert_page_svg_contains(page, "parent family")
>           ace_png_visual.assert_page_png(
                page,
                "agents_python_step_parent_family_120x40",
                title="ACE Python workflow step parent navigation",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:155: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_python_step_parent_family_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xc9\x9e...\x00\x00\x00\x00\x00\x00\x00\x00<z\xd2\xf65i_#zpg\xa1\x05\xfe\x05\xc9h\x1d\xd9\xdc-\xd4r\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_python_step_parent_family_footer_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-2582900450-line-39)">cleanup&#160;(4&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py'
test_line = 127
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_python_step_parent_family_120x40.png
E       Changed pixels: 1447/1520532 (0.095164%); materially changed pixels: 1447/1520532 (0.095164%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_renamed_generic_family_root_png_snapshot _________________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...nts_families.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7c245b000>

    async def test_renamed_generic_family_root_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 11, 10, 0))
        patch_startup_loaders(monkeypatch, agents=renamed_generic_family_agents())
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await page.press("l")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[0].agent_name == "cx--0"
            assert page.app._agents[0].presented_agent_name == "cx"
            assert_page_svg_contains(page, "cx--0")
            assert_page_svg_contains(page, "cx--code")
>           ace_png_visual.assert_page_png(
                page,
                "agents_renamed_generic_family_root_120x40",
                title="ACE renamed generic family root",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:215: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_renamed_generic_family_root_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02$2IDATx\...x08!\x84\x10B\x08!\x84\x10R|\x9c\xd6\xaf\xb0~}\x84\x8d;\xbd\x12\xfc_w\xad\xe9^DL\xa5\xf3\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_renamed_generic_family_root_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1721399503-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py'
test_line = 195
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_renamed_generic_family_root_120x40.png
E       Changed pixels: 1962/1520532 (0.129034%); materially changed pixels: 1948/1520532 (0.128113%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________________ test_agent_list_png_snapshot _________________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...pshots_agents.py', test_line=42, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd5553f64e0>

    async def test_agent_list_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_list_120x40",
                title="ACE agents list",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:55: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_list_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xec)IDA...10B\x08!\x84\x10B\x8c=N\xa6?}\xe9\xcf\x016\xee\x8c\x1d\xf0\xff!\x83\xc8\xfe?\xa5\x1c\xd6\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_list_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-2488048041-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py'
test_line = 42
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_list_120x40.png
E       Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_agent_reverted_indicator_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...pshots_agents.py', test_line=62, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd56e24a350>

    async def test_agent_reverted_indicator_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = agents()
        rows[0].reverted = True
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "↺")
>           ace_png_visual.assert_page_png(
                page,
                "agents_reverted_indicator_120x40",
                title="ACE agents reverted indicator",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:78: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_reverted_indicator_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf3\x14...\x84\x10B\x88\xf1\xc7\xc9\xf8\xd5\x1f\xbf\x0e\xb1qg\xd2\x01\xff\x0fX\xa9\xab9\xea\t\xbc~\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_reverted_indicator_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-2220769080-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py'
test_line = 62
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_reverted_indicator_120x40.png
E       Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_family_and_lone_planner_color_png_snapshot ________________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...nts_families.py', test_line=248, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7b8218280>

    async def test_family_and_lone_planner_color_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 12, 15, 0))
        rows = family_and_lone_planner_agents()
        family = next(row for row in rows if row.cl_name == "visual-real-family")
        lone_planner = next(row for row in rows if row.cl_name == "visual-lone-planner")
        assert family.is_family_container_row is True
        assert lone_planner.is_family_container_row is False
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 2)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-real-family")
            assert_page_svg_contains(page, "visual-lone-planner")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_and_lone_planner_color_120x40",
                title="ACE family and lone planner color contrast",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:269: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_and_lone_planner_color_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x11(IDA...\x84\x10B\x08!\x84\x10b\xf8\xb1/zuG\xaf\x97H\xdc\x99\xb4\xc1\xff\x07KI\xf0RR\xc9\x9b\xd5\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_family_and_lone_planner_color_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-3415743032-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py'
test_line = 248
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_and_lone_planner_color_120x40.png
E       Changed pixels: 1016/1520532 (0.066819%); materially changed pixels: 998/1520532 (0.065635%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_agent_stopped_status_png_snapshot ____________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...pshots_agents.py', test_line=85, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd54e9414e0>

    async def test_agent_stopped_status_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=agents_with_stopped_status())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "Ø STOPPED")
>           ace_png_visual.assert_page_png(
                page,
                "agents_stopped_status_120x40",
                title="ACE agents stopped status",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:99: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_stopped_status_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02!\xfaIDA...\x10B\x06\x1e=\xfa\x15\xd6\xaf\xf7\xb1p\xa7\xd7\x06\xff\x1f\xc7\xef\xcc\xc3\xfc\x9b\xba~\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_stopped_status_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-4276866879-line-39)">cleanup&#160;(4&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py'
test_line = 85
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_stopped_status_120x40.png
E       Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________ test_agent_plan_handoff_status_colors_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...shots_agents.py', test_line=106, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd54fdf48a0>

    async def test_agent_plan_handoff_status_colors_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=plan_handoff_status_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            for status in (
                "PLAN APPROVED",
                "TALE APPROVED",
                "WORKING PLAN",
                "WORKING TALE",
            ):
                assert_page_svg_contains(page, status)
>           ace_png_visual.assert_page_png(
                page,
                "agents_plan_handoff_status_colors_120x40",
                title="ACE agents plan handoff status colors",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:126: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_plan_handoff_status_colors_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf7\x94...EQ\x14EQ\x14EQF\x1e\xc7\x82W\x7f\xf0\xdaG\xe0\xce\xa8\x03\xfe\x0b\xf26.\xbf\xda\x17\xfee\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_plan_handoff_status_colors_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-3652386944-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py'
test_line = 106
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_plan_handoff_status_colors_120x40.png
E       Changed pixels: 2870/1520532 (0.188750%); materially changed pixels: 2870/1520532 (0.188750%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_agents_unread_highlight_png_snapshot ___________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...panel_layout.py', test_line=149, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efbf02bb620>

    async def test_agents_unread_highlight_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        done = _done_agents()
        patch_startup_loaders(monkeypatch, agents=done)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            identities = {agent.identity for agent in done}
            page.app._unread_completed_agent_ids = set(identities)
            page.app._manual_unread_agent_ids = set(identities)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            page.app._update_agents_info_panel()
            panel = page.app.query_one("#agent-info-panel", AgentInfoPanel)
            await wait_for_state(
                page,
                lambda: panel._unread_count == 3,
                description="three unread completed agents",
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_unread_highlight_120x40",
                title="ACE agents unread highlight",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py:173: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_unread_highlight_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf0\x91...10B\x08!\x84\x10b\xecq4~\xf5\xc5\xaf},\xdc\x99\xb4\xc1\xff\x03\x12\xd30\xa8\x13J\xfb\x10\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py::test_agents_unread_highlight_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1166170730-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py'
test_line = 149
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_unread_highlight_120x40.png
E       Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________ test_family_member_panel_shows_sibling_roster_png_snapshot __________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...family_panel.py', test_line=155, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7bdcdfd90>
tmp_path = PosixPath('/var/tmp/sase-96779168/pytest-of-bryan/pytest-0/popen-gw12/test_family_member_panel_shows0')

    async def test_family_member_panel_shows_sibling_roster_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(tmp_path, member_count=3, with_content=False),
        )
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            assert container.is_family_container_row is True
    
            await page.press("1")
            await page.wait_for(
                lambda _state: (
                    page.app._agents[page.app.current_idx].agent_name
                    == f"{_FAMILY_NAME}--code"
                )
            )
            member = page.app._agents[page.app.current_idx]
            assert member.is_family_container_row is False
            await wait_for_visual_idle(page)
    
            member_jump_map = page.app._member_jump_maps[member.identity]
            member_targets = {target.member_identity for target in member_jump_map.targets}
            assert member.identity not in member_targets
    
            assert_page_svg_contains(page, "FAMILY SHELLS")
            assert_page_svg_contains(page, "AGENT SHELL")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_member_roster_120x40",
                title="ACE family member panel roster",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:193: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_member_roster_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02M:IDATx\...0\x00\x00\x00\x18yz\x83\x9f\xee\xe0\xe7mM\xdc\x19\xb5\xc0\xff\x05D\x8dr\x85\xf6a\xce\x8d\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_member_panel_shows_sibling_roster_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-3715646778-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py'
test_line = 155
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_panel_member_roster_120x40.png
E       Changed pixels: 1007/1520532 (0.066227%); materially changed pixels: 979/1520532 (0.064385%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_agents_selected_row_png_snapshot _____________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...shots_agents.py', test_line=279, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd56e24a350>

    async def test_agents_selected_row_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            initial_idx = page.app.current_idx
            for _ in range(8):
                await page.press("j")
                if page.app.current_idx != initial_idx:
                    break
            else:
                raise AssertionError("j navigation did not move off the initial agent row")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_selected_row_120x40",
                title="ACE agents selected row",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:299: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_selected_row_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xec\xe8...B\x08!\x84\x10B\x08!\x84\x10B\x081\xf68\x1c\xbdz\xa3\xd7n\nw&m\xf0\xff\rHvo5\xd7\xab\x98\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agents_selected_row_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-3935522878-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents.py'
test_line = 279
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_selected_row_120x40.png
E       Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________ test_agent_pending_plan_status_colors_png_snapshot ______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...pending_plans.py', test_line=40, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efbda6298d0>

    async def test_agent_pending_plan_status_colors_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=_pending_plan_review_status_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            for status in ("EPIC", "TALE", "PLAN"):
                assert_page_svg_contains(page, status)
>           ace_png_visual.assert_page_png(
                page,
                "agents_pending_plan_status_colors_120x40",
                title="ACE agents pending plan status colors",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_pending_plans.py:55: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_pending_plan_status_colors_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x0cqIDA...84\x10B\x08!\x84\x10B\x08)=\xce\xeaWD\xbf\x0e#q\xa7\xdf\x06\xff\x1f:\r\xa0\xff\xb5x+\x8c\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_pending_plans.py::test_agent_pending_plan_status_colors_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2711870602-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_pending_plans.py'
test_line = 40
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_pending_plan_status_colors_120x40.png
E       Changed pixels: 1317/1520532 (0.086614%); materially changed pixels: 1302/1520532 (0.085628%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...panel_monitor.py', test_line=33, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7be7dd1d0>
tmp_path = PosixPath('/var/tmp/sase-96779168/pytest-of-bryan/pytest-0/popen-gw12/test_family_panel_shells_monit0')

    async def test_family_panel_shells_monitor_metadata_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(
                tmp_path,
                member_count=2,
                with_content=False,
                with_monitor=True,
                monitor_command=(
                    "just check-full --include visual --include slow "
                    "--include every-family-shell-metadata-case"
                ),
                monitor_reason=(
                    "Full-suite verification before landing the family shell "
                    "metadata renderer"
                ),
            ),
        )
    
        async with AcePage(
            query='"visual-family-root"',
            size=(120, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            assert container.is_family_container_row is True
            shells = concrete_family_shell_rows(container)
            assert [shell.is_monitor for shell in shells] == [False, False, True]
            monitor = shells[2]
            assert monitor.parent_timestamp != container.raw_suffix
            jump_map = page.app._member_jump_maps[container.identity]
            assert [target.number for target in jump_map.targets] == ["0", "1", "2"]
            assert jump_map.targets[2].member_identity == monitor.identity
            assert_page_svg_contains(page, "Shells:")
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "why")
            assert_page_svg_contains(page, "Full-suite")
            assert_page_svg_contains(page, "verification")
            assert_page_svg_contains(page, "FAMILY SHELLS")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_monitor_120x40",
                title="ACE family panel shell metadata with monitor",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:83: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x00\x89...8!\x84\x10BH\xe1qA\xbf\x02\xfau\x1c\x89;\xdd\x16\xf8\xff\x07\x08\xee\x85\xfa\x13\xaf\x9e\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-1819841000-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py'
test_line = 33
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_120x40.png
E       Changed pixels: 7642/1520532 (0.502587%); materially changed pixels: 7631/1520532 (0.501864%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...anel_monitor.py', test_line=114, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7bc26fe70>
tmp_path = PosixPath('/var/tmp/sase-96779168/pytest-of-bryan/pytest-0/popen-gw12/test_family_conversation_monit0')

    async def test_family_conversation_monitor_phase_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(
                tmp_path,
                member_count=2,
                with_content=False,
                with_monitor=True,
            ),
        )
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            assert container.is_family_container_row is True
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                await page.press("ctrl+j")
                if panel.active_section_identity == "agent-reply":
                    break
            assert panel.active_section_identity == "agent-reply"
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "MONITOR")
            assert_page_svg_contains(page, "just check-full")
            panel = page.app.query_one("#agent-list-panel", AgentList)
            assert "⚙1" in Text.from_markup(panel.border_title).plain
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_conversation_monitor_120x40",
                title="ACE family conversation with monitor phase",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_conversation_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xeaqIDA...x00\x00\x00\x80\xb9\xe7\\\xf4\x93\x89~Nh\xe0\xce\xa4\t\xfe\x1f\x93\x9f\x0fjI\xb6\xba\xaf\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2807766501-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py'
test_line = 114
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
E       Changed pixels: 7642/1520532 (0.502587%); materially changed pixels: 7631/1520532 (0.501864%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________ test_agents_auto_approve_workflow_child_alignment_png_snapshot ________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ac...auto_approve.py', test_line=168, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd545696e40>

    async def test_agents_auto_approve_workflow_child_alignment_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _auto_approve_workflow_child_agents()
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            page.app._fold_manager.expand("20260509-100000-workflow")
            page.app._refilter_agents()
            await page.expect_state("agent_count", 4)
            await wait_for_svg_contains(page, "⚡E ")
            await wait_for_visual_idle(page)
    
            svg_plain = page.export_svg(title="ACE auto child alignment").replace(
                "&#160;",
                " ",
            )
            assert svg_plain.count("⚡E ") == 2
            for token in ("sase", "setup", "diff", "❯ ", "visual.sase--plan"):
                assert token in svg_plain
            connector_positions = re.findall(
                r'x="([^"]+)" y="([^"]+)"[^>]*>└─ </text>',
                svg_plain,
            )
            assert len(connector_positions) == 3
            assert len({x for x, _ in connector_positions}) == 1
            connector_y = {y for _, y in connector_positions}
            child_bolt_positions = [
                (x, y)
                for x, y in re.findall(
                    r'x="([^"]+)" y="([^"]+)"[^>]*>⚡E </text>',
                    svg_plain,
                )
                if y in connector_y
            ]
            assert len(child_bolt_positions) == 1
            assert float(child_bolt_positions[0][0]) > float(connector_positions[0][0])
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_auto_approve_workflow_child_alignment_120x40",
                title="ACE agents auto-approve workflow child alignment",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py:210: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_auto_approve_workflow_child_alignment_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x9d\x91...0\x00\x00p\xe4\xd9S\xfc\xf4\x15?O\xc6\xc0\x9d\xad&\xf8\xff\x01H\xa4\x9f4\xa8\xd9\xcb\xc7\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py::test_agents_auto_approve_workflow_child_alignment_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-4227724825-line-39)">cleanup&#160;(3&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py'
test_line = 168
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_auto_approve_workflow_child_alignment_120x40.png
E       Changed pixels: 1430/1520532 (0.094046%); materially changed pixels: 1395/1520532 (0.091744%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
============================= slowest 20 durations =============================
34.14s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
32.63s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
12.77s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
12.43s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
11.76s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_insert_png_snapshot
11.39s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
11.35s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_xprompt_highlight_stack_png_snapshot
11.24s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_completion_panel_png_snapshot
10.91s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_new_png_snapshot
10.57s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_tree_fold_levels_png_snapshots
10.51s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_cell_edit_png_snapshot
10.49s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_codeblock_highlight_solo_png_snapshot[textual-dark-prompt_codeblock_highlight_solo_dark_120x40-ACE prompt input \u2014 code highlighting, dark theme]
10.33s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
10.27s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_new_and_clean_png_snapshots[True-mini_xprompt_pane_clean_light_120x40-ACE mini-xprompt pane - clean light]
10.25s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_populated_png_snapshot
10.18s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
10.11s call     tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py::test_placeholder_completion_panel_png_snapshot
10.02s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py::test_prompt_cursor_readout_stack_png_snapshot
9.97s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_codeblock_highlight_stack_png_snapshot[textual-dark-prompt_codeblock_highlight_stack_dark_120x40-ACE prompt stack \u2014 code highlighting, dark theme]
9.94s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_scoped_frontmatter_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_python_step_parent_family_footer_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_python_step_parent_family_120x40.png
Changed pixels: 1447/1520532 (0.095164%); materially changed pixels: 1447/1520532 (0.095164%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_renamed_generic_family_root_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_renamed_generic_family_root_120x40.png
Changed pixels: 1962/1520532 (0.129034%); materially changed pixels: 1948/1520532 (0.128113%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_list_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_list_120x40.png
Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_reverted_indicator_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_reverted_indicator_120x40.png
Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_family_and_lone_planner_color_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_and_lone_planner_color_120x40.png
Changed pixels: 1016/1520532 (0.066819%); materially changed pixels: 998/1520532 (0.065635%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_stopped_status_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_stopped_status_120x40.png
Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_plan_handoff_status_colors_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_plan_handoff_status_colors_120x40.png
Changed pixels: 2870/1520532 (0.188750%); materially changed pixels: 2870/1520532 (0.188750%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py::test_agents_unread_highlight_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_unread_highlight_120x40.png
Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_member_panel_shows_sibling_roster_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_panel_member_roster_120x40.png
Changed pixels: 1007/1520532 (0.066227%); materially changed pixels: 979/1520532 (0.064385%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agents_selected_row_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_selected_row_120x40.png
Changed pixels: 1000/1520532 (0.065766%); materially changed pixels: 1000/1520532 (0.065766%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_pending_plans.py::test_agent_pending_plan_status_colors_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_pending_plan_status_colors_120x40.png
Changed pixels: 1317/1520532 (0.086614%); materially changed pixels: 1302/1520532 (0.085628%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_120x40.png
Changed pixels: 7642/1520532 (0.502587%); materially changed pixels: 7631/1520532 (0.501864%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
Changed pixels: 7642/1520532 (0.502587%); materially changed pixels: 7631/1520532 (0.501864%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py::test_agents_auto_approve_workflow_child_alignment_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/visual/snapshots/png/agents_auto_approve_workflow_child_alignment_120x40.png
Changed pixels: 1430/1520532 (0.094046%); materially changed pixels: 1395/1520532 (0.091744%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
============ 14 failed, 828 passed, 1 skipped in 195.44s (0:03:15) =============
error: recipe `test-visual` failed on line 454 with exit code 1

