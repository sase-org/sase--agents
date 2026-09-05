# Chat History - ace-run (0gf--mon)

- **TIMESTAMP:** 2026-09-05 18:17:19 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0gf--mon

## Prompt

sase monitor start --command 'just test-visual' --reason 'Run the PNG visual snapshot suite required by plans/202609/starting_agents_count_only.md before confirming the STARTING-row count-only fix is complete'

## Response

.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [855 items]

........................................................................ [  8%]
........................................................................ [ 16%]
........................................................................ [ 25%]
.........................................F.............................. [ 33%]
.............F.F............F........................F.....F............ [ 42%]
F....F..............F.F......F.F........................................ [ 50%]
......................F................................................. [ 58%]
...........................................................F............ [ 67%]
........................................................................ [ 75%]
................F.........F.F.......F.........F.FF.F.................... [ 84%]
.........................F..F....F...............F...................... [ 92%]
..F.F..........................F...............................          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_config_center_plugins_not_uv_tool_png_snapshot ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ugin_actions.py', test_line=117, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f084715fa80>

    async def test_config_center_plugins_not_uv_tool_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A non-uv-tool install surfaces the unavailable banner; no ``i install``."""
        patch_startup_loaders(monkeypatch)
        _patch_xprompt_sources(monkeypatch)
        _patch_config_view(monkeypatch, _build_view(_config_schema(), _config_layers()))
        _patch_plugins_catalog(monkeypatch, uv_tool=_not_uv_tool())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
            _, pane = await _open_plugins_modal(page)
            await page.wait_for(lambda _s: pane._detail_key == "plugin:github")
            await _wait_for_plugins_detail(page, pane)
            await page.wait_for(
                lambda _s: (
                    bool(pane._incoming_commit_cache) and not pane._incoming_commit_loading
                )
            )
    
>           ace_png_visual.assert_page_png(
                page,
                "config_center_plugins_not_uv_tool_120x40",
                title="ACE SASE Admin Center — Updates tab (install unavailable)",
            )

tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugin_actions.py:140: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'config_center_plugins_not_uv_tool_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x8c\x8b...00\x00\x00\x1a\x8f\xc3\xd1\xa7\'\xfati\xe2\xce\xa4\x15\xfe\x7f<\x87\x1b?\xef\x9d\xb4\xab\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugin_actions.py::test_config_center_plugins_not_uv_tool_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3015269915-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugin_actions.py'
test_line = 117
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/config_center_plugins_not_uv_tool_120x40.png
E       Changed pixels: 3504/1520532 (0.230446%); materially changed pixels: 3501/1520532 (0.230248%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_center_plugin_actions.py__test_config_center_plugins_not_uv_tool_png_snapshot/config_center_plugins_not_uv_tool_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_center_plugin_actions.py__test_config_center_plugins_not_uv_tool_png_snapshot/config_center_plugins_not_uv_tool_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_center_plugin_actions.py__test_config_center_plugins_not_uv_tool_png_snapshot/config_center_plugins_not_uv_tool_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_config_center_plugin_actions.py__test_config_center_plugins_not_uv_tool_png_snapshot/config_center_plugins_not_uv_tool_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_epic_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...s_clan_panel.py', test_line=147, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb301fc5240>

    async def test_epic_clan_panel_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 12, 15, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=decorate_clan_panel_sections(
                epic_clan_agents(clan_summary=_EPIC_CLAN_SUMMARY)
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "CLAN")
            assert_page_svg_contains(page, "sase-6n")
            assert_page_svg_contains(page, ".phase-runtime")
            assert_page_svg_contains(page, "Title:")
            assert_page_svg_contains(page, "Rich clan summaries")
            assert_page_svg_contains(page, "Counts:")
            assert_page_svg_contains(page, "phases")
            assert_page_svg_contains(page, "waves")
            assert_page_svg_contains(page, "Page:")
            assert_page_svg_contains(page, "3 agents")
            ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_120x40",
                title="ACE epic clan panel fold level 1",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level.value == "expanded"
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_level_2_120x40",
                title="ACE epic clan panel fold level 2",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:185: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_epic_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02V\x98IDA...\x00\x00\x00\x00\x00\x00]\xcf\xb6\xe8\xa7%\xfayI\x1dw&\r\xf0\xff\x01/i\x8dg\xcb\xe5\x94f\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1671705247-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py'
test_line = 147
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_level_2_120x40.png
E       Changed pixels: 62027/1520532 (4.079296%); materially changed pixels: 61945/1520532 (4.073903%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_preview_panel_active_search_png_snapshot _________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...review_panel.py', test_line=277, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5c1e1fec80>

    async def test_preview_panel_active_search_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        payload = PreviewPayload(
            kind_label="chat",
            icon="◈",
            title="reader-search transcript",
            source_path="/workspace/sase/chats/reader-search.md",
            reference="chat:bbugyi200.athena.reader-search",
            lexer="markdown",
            content=(
                "# Reader Search\n\n"
                "The preview reader searches source text on enter.\n\n"
                "## Matching\n\n"
                "Every reader match is highlighted, while n and N navigate.\n\n"
                "The reader keeps navigation responsive on narrow terminals.\n"
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
            modal = PreviewPanelModal(payload)
            page.app.push_screen(modal)
            await page.expect_modal("PreviewPanelModal")
            await page.press("/")
            for key in "reader":
                await page.press(key)
            await page.press("enter")
            await wait_for_state(
                page,
                lambda: modal._match_lines == (1, 3, 7, 9),  # noqa: SLF001
                description="preview search matches to finish loading",
            )
            # Reopen the prefilled input so the snapshot covers the complete search UI.
            await page.press("/")
            await wait_for_state(
                page,
                lambda: (
                    modal.query_one("#preview-search-input", Input).display
                    and modal.query_one("#preview-search-input", Input).value == "reader"
                ),
                description="preview search input to reopen with its committed query",
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "preview_panel_active_search_120x40",
                title="ACE preview panel - active source search",
            )

tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py:326: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'preview_panel_active_search_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01y\x8dIDA...0\x00\x00\x00\x00\xd0{\xa6\xa2\xd7x\xf4:\xa9\x81;\x93&\xf8\xaf\x13\xb6}\xff\xbbi\xb8\xe1\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py::test_preview_panel_active_search_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1903480511-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py'
test_line = 277
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/preview_panel_active_search_120x40.png
E       Changed pixels: 2861/1520532 (0.188158%); materially changed pixels: 2860/1520532 (0.188092%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_preview_panel.py__test_preview_panel_active_search_png_snapshot/preview_panel_active_search_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...s_clan_panel.py', test_line=284, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2e99273f0>

    async def test_swarm_clan_panel_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 10, 15, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=decorate_clan_panel_sections(
                clan_tree_agents(clan_summary=_RESEARCH_CLAN_SUMMARY)
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "CLAN")
            assert_page_svg_contains(page, ".family")
            assert_page_svg_contains(page, "RESEARCH PROMPT:")
            assert_page_svg_contains(page, "across every fold level?")
            assert_page_svg_contains(page, "3 agents")
            assert_page_svg_contains(page, "1 family")
            assert_page_svg_contains(page, "--code")
            ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_swarm_120x40",
                title="ACE swarm clan panel fold level 1",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level.value == "expanded"
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_swarm_level_2_120x40",
                title="ACE swarm clan panel fold level 2",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:319: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_swarm_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x01\x15...84\x10BH\xff\xe3\x98\xf3\x8a8\xaf\xddH\xdc\xe9\xb5\xc1\xff\x07\xe0\xb2a\xb2\x04\xe4\xd4b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-2667924045-line-39)">cleanup&#160;(1&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py'
test_line = 284
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_clan_panel_swarm_level_2_120x40.png
E       Changed pixels: 2996/1520532 (0.197036%); materially changed pixels: 2976/1520532 (0.195721%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________ test_agents_external_repo_diff_file_panel_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...xternal_repos.py', test_line=82, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2eae4db70>

    async def test_agents_external_repo_diff_file_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agent = _external_repo_diff_agent()
        _seed_external_repo_visual_delta(monkeypatch, agent)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "gh:pallets/click")
            assert_page_svg_contains(page, "external repo")
            assert_page_svg_contains(page, "sase/repos/external")
>           ace_png_visual.assert_page_png(
                page,
                "agents_external_repo_diff_file_panel_120x40",
                title="ACE agents external repo diff file panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py:100: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_external_repo_diff_file_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x029)IDATx\...x00\x00\x00\x00\x80\xd1\xe7x\xf4\xea\x8f^\xafh\xe0\xce\xa4\t\xfe\x1f\xe8\xe4(^\xa0\xcaZ;\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2018100102-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py'
test_line = 82
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
E       Changed pixels: 682/1520532 (0.044853%); materially changed pixels: 672/1520532 (0.044195%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_beads_link_reveal_chip_png_snapshots[size0-link_reveal_chip_beads_120x40] _
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...k_reveal_chip.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe4fe3a4210>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw1/test_beads_link_reveal_chip_pn0')
size = (120, 40), snapshot_name = 'link_reveal_chip_beads_120x40'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "link_reveal_chip_beads_120x40"),
            ((60, 30), "link_reveal_chip_beads_60x30"),
        ],
    )
    async def test_beads_link_reveal_chip_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches(), size=size) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("beads"))
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            await page.wait_for(
                lambda _state: getattr(pane, "_project_display_name", None) == "Alpha",
                timeout=15.0,
            )
    
            current = pane_canonical_query(pane)
            page.app._link_reveals["beads"] = make_link_reveal(  # type: ignore[attr-defined]
                pane_id="beads",
                ref="bead:sase-hidden.3",
                origin_source="-status:closed",
                origin_canonical="-status:closed",
                origin_target=None,
                revealed_canonical=current,
            )
            pane._update_static("#beads-info", pane._scope_text())
>           await wait_for_svg_contains(page, "Revealed bead:sase-hidden.3")

tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_waits.py:56: in wait_for_svg_contains
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fe4f2d26990>
predicate = <function wait_for_svg_contains.<locals>.<lambda> at 0x7fe4dfd5aa30>
description = "SVG sentinel 'Revealed bead:sase-hidden.3'", timeout = 15.0

    async def wait_for_state(
        page: AcePage,
        predicate: Callable[[], bool],
        *,
        description: str = "visual state predicate",
        timeout: float = 15.0,
    ) -> None:
        """Wait until a semantic visual-state predicate becomes true.
    
        Unlike :func:`wait_for_visual_idle`, this helper proves that the intended
        UI state was reached. Frame convergence alone can accept a stable but
        incorrect frame (for example, the screen behind a modal that has not
        painted yet).
        """
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
    
        while True:
            await page.pause(0)
            if predicate():
                return
            if loop.time() >= deadline:
                last_frame = page.export_svg(title="ACE visual state timeout")
                digest = hashlib.sha256(last_frame.encode()).hexdigest()[:12]
>               raise AssertionError(
                    f"Timed out after {timeout:.2f}s waiting for {description}; "
                    f"last_frame_digest={digest}; last_frame_svg={last_frame!r}"
                )
E               AssertionError: Timed out after 15.00s waiting for SVG sentinel 'Revealed bead:sase-hidden.3'; last_frame_digest=20ef33044e1f; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-1083259580-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-1083259580-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-1083259580-r1 { fill: #c5c8c6 }\n.terminal-1083259580-r2 { fill: #fffcf0 }\n.terminal-1083259580-r3 { fill: #888888 }\n.terminal-1083259580-r4 { fill: #444444 }\n.terminal-1083259580-r5 { fill: #00d7af;font-weight: bold }\n.terminal-1083259580-r6 { fill: #05adad }\n.terminal-1083259580-r7 { fill: #adaba3 }\n.terminal-1083259580-r8 { fill: #ad5e05;font-weight: bold }\n.terminal-1083259580-r9 { fill: #ad9305;font-weight: bold }\n.terminal-1083259580-r10 { fill: #666666 }\n.terminal-1083259580-r11 { fill: #d787ff }\n.terminal-1083259580-r12 { fill: #d787ff;font-weight: bold }\n.terminal-1083259580-r13 { fill: #3a3a3a }\n.terminal-1083259580-r14 { fill: #fffcf0;font-style: italic; }\n.terminal-1083259580-r15 { fill: #9762b1 }\n.terminal-1083259580-r16 { fill: #ff5f5f;font-weight: bold }\n.terminal-1083259580-r17 { fill: #87d7ff;font-weight: bold }\n.terminal-1083259580-r18 { fill: #d7af5f }\n.terminal-1083259580-r19 { fill: #fffcf0;font-weight: bold }\n.terminal-1083259580-r20 { fill: #1a1a1a;font-weight: bold }\n.terminal-1083259580-r21 { fill: #b1afa7 }\n.terminal-1083259580-r22 { fill: #5f5f87 }\n.terminal-1083259580-r23 { fill: #ff875f }\n.terminal-1083259580-r24 { fill: #ffd700 }\n.terminal-1083259580-r25 { fill: #87d7ff }\n.terminal-1083259580-r26 { fill: #100f0f }\n.terminal-1083259580-r27 { fill: #205ea6 }\n.terminal-1083259580-r28 { fill: #205ea6;font-weight: bold }\n.terminal-1083259580-r29 { fill: #5d5c5a }\n.terminal-1083259580-r30 { fill: #4b4b65 }\n.terminal-1083259580-r31 { fill: #797877 }\n.terminal-1083259580-r32 { fill: #b5b3aa;font-style: italic; }\n.terminal-1083259580-r33 { fill: #ffd700;font-weight: bold }\n.terminal-1083259580-r34 { fill: #c4c5b5 }\n.terminal-1083259580-r35 { fill: #5fd787;font-weight: bold }\n.terminal-1083259580-r36 { fill: #af87ff;font-weight: bold }\n.terminal-1083259580-r37 { fill: #c4c5b5;font-weight: bold }\n.terminal-1083259580-r38 { fill: #494846 }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-1083259580-clip-terminal">\n      <rect x="0" y="0" width="1463.0" height="975.0" />\n    </clipPath>\n    <clipPath id="terminal-1083259580-line-0">\n    <rect x="0" y="1.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-1">\n    <rect x="0" y="25.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-2">\n    <rect x="0" y="50.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-3">\n    <rect x="0" y="74.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-4">\n    <rect x="0" y="99.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-5">\n    <rect x="0" y="123.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-6">\n    <rect x="0" y="147.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-7">\n    <rect x="0" y="172.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-8">\n    <rect x="0" y="196.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-9">\n    <rect x="0" y="221.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-10">\n    <rect x="0" y="245.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-11">\n    <rect x="0" y="269.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-12">\n    <rect x="0" y="294.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-13">\n    <rect x="0" y="318.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-14">\n    <rect x="0" y="343.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-15">\n    <rect x="0" y="367.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-16">\n    <rect x="0" y="391.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-17">\n    <rect x="0" y="416.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-18">\n    <rect x="0" y="440.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-19">\n    <rect x="0" y="465.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-20">\n    <rect x="0" y="489.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-21">\n    <rect x="0" y="513.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-22">\n    <rect x="0" y="538.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-23">\n    <rect x="0" y="562.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-24">\n    <rect x="0" y="587.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-25">\n    <rect x="0" y="611.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-26">\n    <rect x="0" y="635.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-27">\n    <rect x="0" y="660.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-28">\n    <rect x="0" y="684.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-29">\n    <rect x="0" y="709.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-30">\n    <rect x="0" y="733.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-31">\n    <rect x="0" y="757.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-32">\n    <rect x="0" y="782.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-33">\n    <rect x="0" y="806.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-34">\n    <rect x="0" y="831.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-35">\n    <rect x="0" y="855.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-36">\n    <rect x="0" y="879.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-37">\n    <rect x="0" y="904.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1083259580-line-38">\n    <rect x="0" y="928.7" width="1464" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="1480" height="1024" rx="8"/><text class="terminal-1083259580-title" fill="#c5c8c6" text-anchor="middle" x="740" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-1083259580-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="97.6" y="1.5" width="512.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="610" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="817.4" y="1.5" width="524.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1342" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1354.2" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1354.2" y="1.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="25.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="25.9" width="622.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1000.4" y="25.9" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1366.4" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1378.6" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1403" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1415.2" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="244" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="292.8" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="414.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="561.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="597.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="634.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="732" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="817.4" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="890.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="927.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="963.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="976" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1049.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1085.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1122.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1134.6" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1207.8" y="50.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1378.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1390.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1439.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="74.7" width="1146.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1220" y="74.7" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="1171.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1207.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1220" y="99.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="48.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="73.2" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="353.8" y="123.5" width="829.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1183.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1195.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1207.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1220" y="123.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1329.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1390.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="1171.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1207.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1220" y="147.9" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="463.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#d787ff" x="463.6" y="172.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="536.8" y="172.3" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="172.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="829.6" y="172.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="890.6" y="172.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="172.3" width="475.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="1439.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="221.1" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="221.1" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="536.8" y="245.5" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="658.8" y="245.5" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="245.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="269.9" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="269.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="294.3" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="294.3" width="280.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1049.2" y="294.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1110.2" y="294.3" width="292.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1403" y="294.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="318.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="318.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="318.7" width="268.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="488" y="318.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="585.6" y="318.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="318.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="318.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="343.1" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="343.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="451.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="488" y="343.1" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="561.2" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#87d7ff" x="585.6" y="343.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="343.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="343.1" width="500.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1268.8" y="343.1" width="183" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="367.5" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="367.5" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="367.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#ffd75f" x="561.2" y="367.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="658.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="367.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="367.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="391.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="391.9" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="391.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="317.2" y="391.9" width="353.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="391.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="391.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="416.3" width="292.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="329.4" y="416.3" width="341.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="416.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="416.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="440.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="244" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="366" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="378.2" y="440.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="440.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="597.8" y="440.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="440.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="440.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="465.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="207.4" y="465.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="465.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="465.1" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="465.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="465.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="489.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="489.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="489.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="513.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="513.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="513.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="538.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="538.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="538.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="562.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="562.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="562.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="587.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="587.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="587.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="611.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="611.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="611.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="635.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="635.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="635.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="660.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="660.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="660.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="684.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="684.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="684.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="709.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="709.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="709.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="733.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="733.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="733.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="757.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="757.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="757.9" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="782.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="782.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="782.3" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="806.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="806.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="806.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="831.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="831.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="831.1" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="855.5" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="855.5" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="879.9" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="879.9" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="390.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="610" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="939.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1098" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1159" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1171.2" y="904.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1281" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1342" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1354.2" y="904.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="928.7" width="1464" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="1268.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="1281" y="953.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="1342" y="953.1" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-1083259580-matrix">\n    <text class="terminal-1083259580-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-1083259580-line-0)">⭘</text><text class="terminal-1083259580-r2" x="610" y="20" textLength="207.4" clip-path="url(#terminal-1083259580-line-0)">sase&#160;ace&#160;(v0.7.1)</text><text class="terminal-1083259580-r1" x="1464" y="20" textLength="12.2" clip-path="url(#terminal-1083259580-line-0)">\n</text><text class="terminal-1083259580-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-1083259580-line-1)">&#160;Agents&#160;</text><text class="terminal-1083259580-r4" x="109.8" y="44.4" textLength="36.6" clip-path="url(#terminal-1083259580-line-1)">&#160;│&#160;</text><text class="terminal-1083259580-r5" x="146.4" y="44.4" textLength="134.2" clip-path="url(#terminal-1083259580-line-1)">&#160;Artifacts&#160;</text><text class="terminal-1083259580-r4" x="280.6" y="44.4" textLength="36.6" clip-path="url(#terminal-1083259580-line-1)">&#160;│&#160;</text><text class="terminal-1083259580-r3" x="317.2" y="44.4" textLength="61" clip-path="url(#terminal-1083259580-line-1)">&#160;AXE&#160;</text><text class="terminal-1083259580-r6" x="1000.4" y="44.4" textLength="366" clip-path="url(#terminal-1083259580-line-1)">&#160;CODEX(visual-snapshot-model)&#160;</text><text class="terminal-1083259580-r8" x="1378.6" y="44.4" textLength="24.4" clip-path="url(#terminal-1083259580-line-1)">⚑1</text><text class="terminal-1083259580-r9" x="1415.2" y="44.4" textLength="36.6" clip-path="url(#terminal-1083259580-line-1)">✉18</text><text class="terminal-1083259580-r1" x="1464" y="44.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-1)">\n</text><text class="terminal-1083259580-r10" x="244" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;1&#160;</text><text class="terminal-1083259580-r10" x="280.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">⬡</text><text class="terminal-1083259580-r3" x="292.8" y="68.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-2)">&#160;Agent&#160;</text><text class="terminal-1083259580-r4" x="378.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="414.8" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;2&#160;</text><text class="terminal-1083259580-r10" x="451.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">◉</text><text class="terminal-1083259580-r3" x="463.6" y="68.8" textLength="97.6" clip-path="url(#terminal-1083259580-line-2)">&#160;Stitch&#160;</text><text class="terminal-1083259580-r4" x="561.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="597.8" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;3&#160;</text><text class="terminal-1083259580-r10" x="634.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">⎇</text><text class="terminal-1083259580-r3" x="646.6" y="68.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-2)">&#160;Patch&#160;</text><text class="terminal-1083259580-r4" x="732" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r11" x="768.6" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;4&#160;</text><text class="terminal-1083259580-r11" x="805.2" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">◈</text><text class="terminal-1083259580-r12" x="817.4" y="68.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-2)">&#160;BEAD&#160;</text><text class="terminal-1083259580-r4" x="890.6" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="927.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;5&#160;</text><text class="terminal-1083259580-r10" x="963.8" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">✎</text><text class="terminal-1083259580-r3" x="976" y="68.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-2)">&#160;Plan&#160;</text><text class="terminal-1083259580-r4" x="1049.2" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;│&#160;</text><text class="terminal-1083259580-r10" x="1085.8" y="68.8" textLength="36.6" clip-path="url(#terminal-1083259580-line-2)">&#160;6&#160;</text><text class="terminal-1083259580-r10" x="1122.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">▤</text><text class="terminal-1083259580-r3" x="1134.6" y="68.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-2)">&#160;File&#160;</text><text class="terminal-1083259580-r10" x="1378.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">{</text><text class="terminal-1083259580-r11" x="1390.8" y="68.8" textLength="24.4" clip-path="url(#terminal-1083259580-line-2)">██</text><text class="terminal-1083259580-r13" x="1415.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1083259580-line-2)">██</text><text class="terminal-1083259580-r10" x="1439.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">}</text><text class="terminal-1083259580-r1" x="1464" y="68.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-2)">\n</text><text class="terminal-1083259580-r12" x="12.2" y="93.2" textLength="24.4" clip-path="url(#terminal-1083259580-line-3)">▌&#160;</text><text class="terminal-1083259580-r2" x="36.6" y="93.2" textLength="36.6" clip-path="url(#terminal-1083259580-line-3)">◈&#160;&#160;</text><text class="terminal-1083259580-r14" x="73.2" y="93.2" textLength="1146.8" clip-path="url(#terminal-1083259580-line-3)">The&#160;work&#160;SASE&#160;tracks:&#160;plan&#160;and&#160;epic&#160;beads,&#160;the&#160;phases&#160;beneath&#160;them,&#160;and&#160;standalone&#160;task&#160;beads.</text><text class="terminal-1083259580-r15" x="1415.2" y="93.2" textLength="36.6" clip-path="url(#terminal-1083259580-line-3)">▸&#160;D</text><text class="terminal-1083259580-r1" x="1464" y="93.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-3)">\n</text><text class="terminal-1083259580-r11" x="36.6" y="117.6" textLength="1171.2" clip-path="url(#terminal-1083259580-line-4)">┌──────────────────────────────────────────────────────────────────────────────────────────────┐</text><text class="terminal-1083259580-r1" x="1464" y="117.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-4)">\n</text><text class="terminal-1083259580-r12" x="12.2" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">/</text><text class="terminal-1083259580-r11" x="36.6" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">│</text><text class="terminal-1083259580-r16" x="61" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">-</text><text class="terminal-1083259580-r17" x="73.2" y="142" textLength="85.4" clip-path="url(#terminal-1083259580-line-5)">status:</text><text class="terminal-1083259580-r18" x="158.6" y="142" textLength="73.2" clip-path="url(#terminal-1083259580-line-5)">closed</text><text class="terminal-1083259580-r17" x="244" y="142" textLength="73.2" clip-path="url(#terminal-1083259580-line-5)">limit:</text><text class="terminal-1083259580-r18" x="317.2" y="142" textLength="36.6" clip-path="url(#terminal-1083259580-line-5)">100</text><text class="terminal-1083259580-r11" x="1195.6" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">│</text><text class="terminal-1083259580-r19" x="1220" y="142" textLength="109.8" clip-path="url(#terminal-1083259580-line-5)">4&#160;matches</text><text class="terminal-1083259580-r7" x="1329.8" y="142" textLength="61" clip-path="url(#terminal-1083259580-line-5)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r11" x="1390.8" y="142" textLength="61" clip-path="url(#terminal-1083259580-line-5)">exact</text><text class="terminal-1083259580-r1" x="1464" y="142" textLength="12.2" clip-path="url(#terminal-1083259580-line-5)">\n</text><text class="terminal-1083259580-r11" x="36.6" y="166.4" textLength="1171.2" clip-path="url(#terminal-1083259580-line-6)">└──────────────────────────────────────────────────────────────────────────────────────────────┘</text><text class="terminal-1083259580-r1" x="1464" y="166.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-6)">\n</text><text class="terminal-1083259580-r20" x="463.6" y="190.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-7)">&#160;Bead&#160;</text><text class="terminal-1083259580-r21" x="536.8" y="190.8" textLength="207.4" clip-path="url(#terminal-1083259580-line-7)">&#160;&#160;Project&#160;scope&#160;&#160;</text><text class="terminal-1083259580-r12" x="744.2" y="190.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-7)">&#160;Alpha&#160;</text><text class="terminal-1083259580-r21" x="829.6" y="190.8" textLength="61" clip-path="url(#terminal-1083259580-line-7)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r21" x="890.6" y="190.8" textLength="97.6" clip-path="url(#terminal-1083259580-line-7)">p&#160;change</text><text class="terminal-1083259580-r1" x="1464" y="190.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-7)">\n</text><text class="terminal-1083259580-r1" x="1464" y="215.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-8)">\n</text><text class="terminal-1083259580-r11" x="0" y="239.6" textLength="732" clip-path="url(#terminal-1083259580-line-9)">╭─&#160;Beads&#160;──────────────────────────────────────────────────╮</text><text class="terminal-1083259580-r22" x="732" y="239.6" textLength="732" clip-path="url(#terminal-1083259580-line-9)">╭─&#160;Details&#160;────────────────────────────────────────────────╮</text><text class="terminal-1083259580-r1" x="1464" y="239.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-9)">\n</text><text class="terminal-1083259580-r11" x="0" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r11" x="24.4" y="264" textLength="109.8" clip-path="url(#terminal-1083259580-line-10)">2/2&#160;tasks</text><text class="terminal-1083259580-r21" x="134.2" y="264" textLength="61" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r23" x="195.2" y="264" textLength="109.8" clip-path="url(#terminal-1083259580-line-10)">0/0&#160;flags</text><text class="terminal-1083259580-r21" x="305" y="264" textLength="61" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r24" x="366" y="264" textLength="109.8" clip-path="url(#terminal-1083259580-line-10)">1/1&#160;epics</text><text class="terminal-1083259580-r21" x="475.8" y="264" textLength="61" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r25" x="536.8" y="264" textLength="122" clip-path="url(#terminal-1083259580-line-10)">1/2&#160;phases</text><text class="terminal-1083259580-r21" x="658.8" y="264" textLength="48.8" clip-path="url(#terminal-1083259580-line-10)">&#160;&#160;·…</text><text class="terminal-1083259580-r11" x="719.8" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r22" x="732" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">│</text><text class="terminal-1083259580-r1" x="1464" y="264" textLength="12.2" clip-path="url(#terminal-1083259580-line-10)">\n</text><text class="terminal-1083259580-r11" x="0" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r11" x="719.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r22" x="732" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">│</text><text class="terminal-1083259580-r1" x="1464" y="288.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-11)">\n</text><text class="terminal-1083259580-r11" x="0" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r26" x="12.2" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">▊</text><text class="terminal-1083259580-r27" x="24.4" y="312.8" textLength="683.2" clip-path="url(#terminal-1083259580-line-12)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1083259580-r27" x="707.6" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r22" x="732" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r28" x="1049.2" y="312.8" textLength="61" clip-path="url(#terminal-1083259580-line-12)">Beads</text><text class="terminal-1083259580-r22" x="1451.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">│</text><text class="terminal-1083259580-r1" x="1464" y="312.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-12)">\n</text><text class="terminal-1083259580-r11" x="0" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r26" x="12.2" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="337.2" textLength="109.8" clip-path="url(#terminal-1083259580-line-13)">──&#160;Tasks&#160;</text><text class="terminal-1083259580-r29" x="146.4" y="337.2" textLength="73.2" clip-path="url(#terminal-1083259580-line-13)">(2/2)&#160;</text><text class="terminal-1083259580-r12" x="219.6" y="337.2" textLength="268.4" clip-path="url(#terminal-1083259580-line-13)">·&#160;✦&#160;1&#160;awaiting&#160;triage&#160;</text><text class="terminal-1083259580-r30" x="488" y="337.2" textLength="97.6" clip-path="url(#terminal-1083259580-line-13)">────────</text><text class="terminal-1083259580-r27" x="707.6" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r22" x="732" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">│</text><text class="terminal-1083259580-r1" x="1464" y="337.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-13)">\n</text><text class="terminal-1083259580-r11" x="0" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r26" x="12.2" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="361.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-14)">◆&#160;</text><text class="terminal-1083259580-r32" x="61" y="361.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-14)">·&#160;</text><text class="terminal-1083259580-r12" x="85.4" y="361.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-14)">✦&#160;</text><text class="terminal-1083259580-r33" x="109.8" y="361.6" textLength="146.4" clip-path="url(#terminal-1083259580-line-14)">alpha-ready&#160;</text><text class="terminal-1083259580-r34" x="256.2" y="361.6" textLength="195.2" clip-path="url(#terminal-1083259580-line-14)">Ready&#160;for&#160;triage</text><text class="terminal-1083259580-r5" x="475.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">◇</text><text class="terminal-1083259580-r5" x="488" y="361.6" textLength="73.2" clip-path="url(#terminal-1083259580-line-14)">&#160;ready</text><text class="terminal-1083259580-r20" x="585.6" y="361.6" textLength="85.4" clip-path="url(#terminal-1083259580-line-14)">&#160;small…</text><text class="terminal-1083259580-r27" x="707.6" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r22" x="732" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r2" x="768.6" y="361.6" textLength="500.2" clip-path="url(#terminal-1083259580-line-14)">Select&#160;a&#160;task,&#160;flag,&#160;epic,&#160;or&#160;phase&#160;bead.</text><text class="terminal-1083259580-r22" x="1451.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">│</text><text class="terminal-1083259580-r1" x="1464" y="361.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-14)">\n</text><text class="terminal-1083259580-r11" x="0" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r26" x="12.2" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="386" textLength="24.4" clip-path="url(#terminal-1083259580-line-15)">◆&#160;</text><text class="terminal-1083259580-r32" x="61" y="386" textLength="24.4" clip-path="url(#terminal-1083259580-line-15)">·&#160;</text><text class="terminal-1083259580-r33" x="85.4" y="386" textLength="134.2" clip-path="url(#terminal-1083259580-line-15)">alpha-open&#160;</text><text class="terminal-1083259580-r34" x="219.6" y="386" textLength="219.6" clip-path="url(#terminal-1083259580-line-15)">Ordinary&#160;follow-up</text><text class="terminal-1083259580-r17" x="463.6" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">○</text><text class="terminal-1083259580-r17" x="475.8" y="386" textLength="61" clip-path="url(#terminal-1083259580-line-15)">&#160;open</text><text class="terminal-1083259580-r20" x="561.2" y="386" textLength="97.6" clip-path="url(#terminal-1083259580-line-15)">&#160;medium&#160;</text><text class="terminal-1083259580-r2" x="658.8" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">…</text><text class="terminal-1083259580-r27" x="707.6" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r22" x="732" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">│</text><text class="terminal-1083259580-r1" x="1464" y="386" textLength="12.2" clip-path="url(#terminal-1083259580-line-15)">\n</text><text class="terminal-1083259580-r11" x="0" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r26" x="12.2" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="410.4" textLength="109.8" clip-path="url(#terminal-1083259580-line-16)">──&#160;Flags&#160;</text><text class="terminal-1083259580-r29" x="146.4" y="410.4" textLength="73.2" clip-path="url(#terminal-1083259580-line-16)">(0/0)&#160;</text><text class="terminal-1083259580-r30" x="219.6" y="410.4" textLength="97.6" clip-path="url(#terminal-1083259580-line-16)">────────</text><text class="terminal-1083259580-r27" x="707.6" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r22" x="732" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">│</text><text class="terminal-1083259580-r1" x="1464" y="410.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-16)">\n</text><text class="terminal-1083259580-r11" x="0" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r26" x="12.2" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">▊</text><text class="terminal-1083259580-r29" x="36.6" y="434.8" textLength="292.8" clip-path="url(#terminal-1083259580-line-17)">&#160;&#160;No&#160;matching&#160;flag&#160;beads</text><text class="terminal-1083259580-r27" x="707.6" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r22" x="732" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">│</text><text class="terminal-1083259580-r1" x="1464" y="434.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-17)">\n</text><text class="terminal-1083259580-r11" x="0" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r26" x="12.2" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="459.2" textLength="109.8" clip-path="url(#terminal-1083259580-line-18)">──&#160;Epics&#160;</text><text class="terminal-1083259580-r29" x="146.4" y="459.2" textLength="73.2" clip-path="url(#terminal-1083259580-line-18)">(1/1)&#160;</text><text class="terminal-1083259580-r29" x="219.6" y="459.2" textLength="24.4" clip-path="url(#terminal-1083259580-line-18)">·&#160;</text><text class="terminal-1083259580-r16" x="244" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">⊜</text><text class="terminal-1083259580-r29" x="256.2" y="459.2" textLength="109.8" clip-path="url(#terminal-1083259580-line-18)">&#160;blocked&#160;</text><text class="terminal-1083259580-r35" x="366" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">►</text><text class="terminal-1083259580-r29" x="378.2" y="459.2" textLength="85.4" clip-path="url(#terminal-1083259580-line-18)">&#160;ready&#160;</text><text class="terminal-1083259580-r5" x="463.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">▶</text><text class="terminal-1083259580-r29" x="475.8" y="459.2" textLength="122" clip-path="url(#terminal-1083259580-line-18)">&#160;launched&#160;</text><text class="terminal-1083259580-r30" x="597.8" y="459.2" textLength="73.2" clip-path="url(#terminal-1083259580-line-18)">─────…</text><text class="terminal-1083259580-r27" x="707.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r22" x="732" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">│</text><text class="terminal-1083259580-r1" x="1464" y="459.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-18)">\n</text><text class="terminal-1083259580-r11" x="0" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r26" x="12.2" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">▊</text><text class="terminal-1083259580-r12" x="36.6" y="483.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-19)">▸&#160;</text><text class="terminal-1083259580-r33" x="61" y="483.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-19)">▸&#160;</text><text class="terminal-1083259580-r36" x="85.4" y="483.6" textLength="24.4" clip-path="url(#terminal-1083259580-line-19)">▤&#160;</text><text class="terminal-1083259580-r33" x="109.8" y="483.6" textLength="97.6" clip-path="url(#terminal-1083259580-line-19)">alpha-1&#160;</text><text class="terminal-1083259580-r37" x="207.4" y="483.6" textLength="231.8" clip-path="url(#terminal-1083259580-line-19)">Build&#160;bead&#160;browsing</text><text class="terminal-1083259580-r17" x="463.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">○</text><text class="terminal-1083259580-r17" x="475.8" y="483.6" textLength="61" clip-path="url(#terminal-1083259580-line-19)">&#160;open</text><text class="terminal-1083259580-r25" x="536.8" y="483.6" textLength="134.2" clip-path="url(#terminal-1083259580-line-19)">&#160;&#160;1/2&#160;phas…</text><text class="terminal-1083259580-r27" x="707.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r22" x="732" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">│</text><text class="terminal-1083259580-r1" x="1464" y="483.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-19)">\n</text><text class="terminal-1083259580-r11" x="0" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r26" x="12.2" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r22" x="732" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">│</text><text class="terminal-1083259580-r1" x="1464" y="508" textLength="12.2" clip-path="url(#terminal-1083259580-line-20)">\n</text><text class="terminal-1083259580-r11" x="0" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r26" x="12.2" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r22" x="732" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">│</text><text class="terminal-1083259580-r1" x="1464" y="532.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-21)">\n</text><text class="terminal-1083259580-r11" x="0" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r26" x="12.2" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r22" x="732" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">│</text><text class="terminal-1083259580-r1" x="1464" y="556.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-22)">\n</text><text class="terminal-1083259580-r11" x="0" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r26" x="12.2" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r22" x="732" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">│</text><text class="terminal-1083259580-r1" x="1464" y="581.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-23)">\n</text><text class="terminal-1083259580-r11" x="0" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r26" x="12.2" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r22" x="732" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">│</text><text class="terminal-1083259580-r1" x="1464" y="605.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-24)">\n</text><text class="terminal-1083259580-r11" x="0" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r26" x="12.2" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r22" x="732" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">│</text><text class="terminal-1083259580-r1" x="1464" y="630" textLength="12.2" clip-path="url(#terminal-1083259580-line-25)">\n</text><text class="terminal-1083259580-r11" x="0" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r26" x="12.2" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r22" x="732" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">│</text><text class="terminal-1083259580-r1" x="1464" y="654.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-26)">\n</text><text class="terminal-1083259580-r11" x="0" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r26" x="12.2" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r22" x="732" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">│</text><text class="terminal-1083259580-r1" x="1464" y="678.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-27)">\n</text><text class="terminal-1083259580-r11" x="0" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r26" x="12.2" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r22" x="732" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">│</text><text class="terminal-1083259580-r1" x="1464" y="703.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-28)">\n</text><text class="terminal-1083259580-r11" x="0" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r26" x="12.2" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r22" x="732" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">│</text><text class="terminal-1083259580-r1" x="1464" y="727.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-29)">\n</text><text class="terminal-1083259580-r11" x="0" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r26" x="12.2" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r22" x="732" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">│</text><text class="terminal-1083259580-r1" x="1464" y="752" textLength="12.2" clip-path="url(#terminal-1083259580-line-30)">\n</text><text class="terminal-1083259580-r11" x="0" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r26" x="12.2" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r22" x="732" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">│</text><text class="terminal-1083259580-r1" x="1464" y="776.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-31)">\n</text><text class="terminal-1083259580-r11" x="0" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r26" x="12.2" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r22" x="732" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">│</text><text class="terminal-1083259580-r1" x="1464" y="800.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-32)">\n</text><text class="terminal-1083259580-r11" x="0" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r26" x="12.2" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r22" x="732" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">│</text><text class="terminal-1083259580-r1" x="1464" y="825.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-33)">\n</text><text class="terminal-1083259580-r11" x="0" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r26" x="12.2" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">▊</text><text class="terminal-1083259580-r27" x="707.6" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r22" x="732" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">│</text><text class="terminal-1083259580-r1" x="1464" y="849.6" textLength="12.2" clip-path="url(#terminal-1083259580-line-34)">\n</text><text class="terminal-1083259580-r11" x="0" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r26" x="12.2" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">▊</text><text class="terminal-1083259580-r27" x="24.4" y="874" textLength="683.2" clip-path="url(#terminal-1083259580-line-35)">▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁</text><text class="terminal-1083259580-r27" x="707.6" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">▎</text><text class="terminal-1083259580-r11" x="719.8" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r22" x="732" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r22" x="1451.8" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">│</text><text class="terminal-1083259580-r1" x="1464" y="874" textLength="12.2" clip-path="url(#terminal-1083259580-line-35)">\n</text><text class="terminal-1083259580-r11" x="0" y="898.4" textLength="732" clip-path="url(#terminal-1083259580-line-36)">╰──────────────────────────────────────────────────────────╯</text><text class="terminal-1083259580-r22" x="732" y="898.4" textLength="732" clip-path="url(#terminal-1083259580-line-36)">╰──────────────────────────────────────────────────────────╯</text><text class="terminal-1083259580-r1" x="1464" y="898.4" textLength="12.2" clip-path="url(#terminal-1083259580-line-36)">\n</text><text class="terminal-1083259580-r12" x="0" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">j</text><text class="terminal-1083259580-r21" x="12.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;next</text><text class="terminal-1083259580-r21" x="73.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="134.2" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">k</text><text class="terminal-1083259580-r21" x="146.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;prev</text><text class="terminal-1083259580-r21" x="207.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="268.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">Enter</text><text class="terminal-1083259580-r21" x="329.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;view</text><text class="terminal-1083259580-r21" x="390.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="451.4" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">f</text><text class="terminal-1083259580-r21" x="463.6" y="922.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-37)">&#160;filter</text><text class="terminal-1083259580-r21" x="549" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="610" y="922.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-37)">Ctrl+J</text><text class="terminal-1083259580-r21" x="683.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;more</text><text class="terminal-1083259580-r21" x="744.2" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="805.2" y="922.8" textLength="73.2" clip-path="url(#terminal-1083259580-line-37)">Ctrl+K</text><text class="terminal-1083259580-r21" x="878.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;less</text><text class="terminal-1083259580-r21" x="939.4" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="1000.4" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">l</text><text class="terminal-1083259580-r21" x="1012.6" y="922.8" textLength="85.4" clip-path="url(#terminal-1083259580-line-37)">&#160;expand</text><text class="terminal-1083259580-r21" x="1098" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="1159" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">h</text><text class="terminal-1083259580-r21" x="1171.2" y="922.8" textLength="109.8" clip-path="url(#terminal-1083259580-line-37)">&#160;collapse</text><text class="terminal-1083259580-r21" x="1281" y="922.8" textLength="61" clip-path="url(#terminal-1083259580-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1083259580-r12" x="1342" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">R</text><text class="terminal-1083259580-r21" x="1354.2" y="922.8" textLength="97.6" clip-path="url(#terminal-1083259580-line-37)">&#160;refresh</text><text class="terminal-1083259580-r1" x="1464" y="922.8" textLength="12.2" clip-path="url(#terminal-1083259580-line-37)">\n</text><text class="terminal-1083259580-r38" x="0" y="947.2" textLength="1464" clip-path="url(#terminal-1083259580-line-38)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1083259580-r1" x="1464" y="947.2" textLength="12.2" clip-path="url(#terminal-1083259580-line-38)">\n</text><text class="terminal-1083259580-r37" x="1281" y="971.6" textLength="61" clip-path="url(#terminal-1083259580-line-39)">&#160;AXE&#160;</text><text class="terminal-1083259580-r37" x="1342" y="971.6" textLength="109.8" clip-path="url(#terminal-1083259580-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
_ test_beads_link_reveal_chip_png_snapshots[size1-link_reveal_chip_beads_60x30] _
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...k_reveal_chip.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe50cf5f5b0>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw1/test_beads_link_reveal_chip_pn1')
size = (60, 30), snapshot_name = 'link_reveal_chip_beads_60x30'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "link_reveal_chip_beads_120x40"),
            ((60, 30), "link_reveal_chip_beads_60x30"),
        ],
    )
    async def test_beads_link_reveal_chip_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches(), size=size) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("beads"))
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            await page.wait_for(
                lambda _state: getattr(pane, "_project_display_name", None) == "Alpha",
                timeout=15.0,
            )
    
            current = pane_canonical_query(pane)
            page.app._link_reveals["beads"] = make_link_reveal(  # type: ignore[attr-defined]
                pane_id="beads",
                ref="bead:sase-hidden.3",
                origin_source="-status:closed",
                origin_canonical="-status:closed",
                origin_target=None,
                revealed_canonical=current,
            )
            pane._update_static("#beads-info", pane._scope_text())
>           await wait_for_svg_contains(page, "Revealed bead:sase-hidden.3")

tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_waits.py:56: in wait_for_svg_contains
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fe4dedcf410>
predicate = <function wait_for_svg_contains.<locals>.<lambda> at 0x7fe4f10f7110>
description = "SVG sentinel 'Revealed bead:sase-hidden.3'", timeout = 15.0

    async def wait_for_state(
        page: AcePage,
        predicate: Callable[[], bool],
        *,
        description: str = "visual state predicate",
        timeout: float = 15.0,
    ) -> None:
        """Wait until a semantic visual-state predicate becomes true.
    
        Unlike :func:`wait_for_visual_idle`, this helper proves that the intended
        UI state was reached. Frame convergence alone can accept a stable but
        incorrect frame (for example, the screen behind a modal that has not
        painted yet).
        """
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
    
        while True:
            await page.pause(0)
            if predicate():
                return
            if loop.time() >= deadline:
                last_frame = page.export_svg(title="ACE visual state timeout")
                digest = hashlib.sha256(last_frame.encode()).hexdigest()[:12]
>               raise AssertionError(
                    f"Timed out after {timeout:.2f}s waiting for {description}; "
                    f"last_frame_digest={digest}; last_frame_svg={last_frame!r}"
                )
E               AssertionError: Timed out after 15.00s waiting for SVG sentinel 'Revealed bead:sase-hidden.3'; last_frame_digest=00824c895556; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 750 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-1526668734-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-1526668734-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-1526668734-r1 { fill: #c5c8c6 }\n.terminal-1526668734-r2 { fill: #fffcf0 }\n.terminal-1526668734-r3 { fill: #888888 }\n.terminal-1526668734-r4 { fill: #444444 }\n.terminal-1526668734-r5 { fill: #05adad }\n.terminal-1526668734-r6 { fill: #adaba3 }\n.terminal-1526668734-r7 { fill: #ad5e05;font-weight: bold }\n.terminal-1526668734-r8 { fill: #ad9305;font-weight: bold }\n.terminal-1526668734-r9 { fill: #666666 }\n.terminal-1526668734-r10 { fill: #d787ff }\n.terminal-1526668734-r11 { fill: #d787ff;font-weight: bold }\n.terminal-1526668734-r12 { fill: #3a3a3a }\n.terminal-1526668734-r13 { fill: #fffcf0;font-style: italic; }\n.terminal-1526668734-r14 { fill: #ff5f5f;font-weight: bold }\n.terminal-1526668734-r15 { fill: #87d7ff;font-weight: bold }\n.terminal-1526668734-r16 { fill: #d7af5f }\n.terminal-1526668734-r17 { fill: #fffcf0;font-weight: bold }\n.terminal-1526668734-r18 { fill: #1a1a1a;font-weight: bold }\n.terminal-1526668734-r19 { fill: #b1afa7 }\n.terminal-1526668734-r20 { fill: #5f5f87 }\n.terminal-1526668734-r21 { fill: #ff875f }\n.terminal-1526668734-r22 { fill: #ffd700 }\n.terminal-1526668734-r23 { fill: #100f0f }\n.terminal-1526668734-r24 { fill: #205ea6 }\n.terminal-1526668734-r25 { fill: #205ea6;font-weight: bold }\n.terminal-1526668734-r26 { fill: #5d5c5a }\n.terminal-1526668734-r27 { fill: #b5b3aa;font-style: italic; }\n.terminal-1526668734-r28 { fill: #ffd700;font-weight: bold }\n.terminal-1526668734-r29 { fill: #c4c5b5 }\n.terminal-1526668734-r30 { fill: #4b4b65 }\n.terminal-1526668734-r31 { fill: #797877 }\n.terminal-1526668734-r32 { fill: #5fd787;font-weight: bold }\n.terminal-1526668734-r33 { fill: #00d7af;font-weight: bold }\n.terminal-1526668734-r34 { fill: #af87ff;font-weight: bold }\n.terminal-1526668734-r35 { fill: #c4c5b5;font-weight: bold }\n.terminal-1526668734-r36 { fill: #494846 }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-1526668734-clip-terminal">\n      <rect x="0" y="0" width="731.0" height="731.0" />\n    </clipPath>\n    <clipPath id="terminal-1526668734-line-0">\n    <rect x="0" y="1.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-1">\n    <rect x="0" y="25.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-2">\n    <rect x="0" y="50.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-3">\n    <rect x="0" y="74.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-4">\n    <rect x="0" y="99.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-5">\n    <rect x="0" y="123.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-6">\n    <rect x="0" y="147.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-7">\n    <rect x="0" y="172.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-8">\n    <rect x="0" y="196.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-9">\n    <rect x="0" y="221.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-10">\n    <rect x="0" y="245.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-11">\n    <rect x="0" y="269.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-12">\n    <rect x="0" y="294.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-13">\n    <rect x="0" y="318.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-14">\n    <rect x="0" y="343.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-15">\n    <rect x="0" y="367.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-16">\n    <rect x="0" y="391.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-17">\n    <rect x="0" y="416.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-18">\n    <rect x="0" y="440.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-19">\n    <rect x="0" y="465.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-20">\n    <rect x="0" y="489.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-21">\n    <rect x="0" y="513.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-22">\n    <rect x="0" y="538.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-23">\n    <rect x="0" y="562.7" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-24">\n    <rect x="0" y="587.1" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-25">\n    <rect x="0" y="611.5" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-26">\n    <rect x="0" y="635.9" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-27">\n    <rect x="0" y="660.3" width="732" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-1526668734-line-28">\n    <rect x="0" y="684.7" width="732" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="748" height="780" rx="8"/><text class="terminal-1526668734-title" fill="#c5c8c6" text-anchor="middle" x="374" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-1526668734-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="97.6" y="1.5" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="244" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="451.4" y="1.5" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="610" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="268.4" y="25.9" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="646.6" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="683.2" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="219.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="231.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="244" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="292.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="50.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="488" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="536.8" y="50.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="658.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="74.7" width="646.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="475.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="99.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="48.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="73.2" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="123.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="353.8" y="123.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="451.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="463.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="475.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="123.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="597.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="658.8" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="475.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="147.9" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#d787ff" x="97.6" y="172.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="170.8" y="172.3" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="172.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="172.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="172.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="172.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="707.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="221.1" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="221.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="245.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="245.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="245.5" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="269.9" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="269.9" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="294.3" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="585.6" y="294.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="646.6" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="294.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="318.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="318.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="318.7" width="256.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="318.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="318.7" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="343.1" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="343.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="451.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="343.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="343.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="343.1" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="367.5" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="367.5" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="367.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="367.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="367.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="391.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="391.9" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="391.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="317.2" y="391.9" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="391.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="391.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="391.9" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="416.3" width="292.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="329.4" y="416.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="416.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="416.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="671" y="416.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="440.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="244" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="256.2" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="366" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="378.2" y="440.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="440.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="440.7" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="440.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="85.4" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="109.8" y="465.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="207.4" y="465.1" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="439.2" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="463.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="465.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="465.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="634.4" y="465.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="489.5" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="489.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="489.5" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="513.9" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="513.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="513.9" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="538.3" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="538.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="538.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="562.7" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="562.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="562.7" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="587.1" width="439.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="475.8" y="587.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="587.1" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="611.5" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="524.6" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="611.5" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="635.9" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="536.8" y="635.9" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="390.4" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="660.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="660.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="610" y="660.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="660.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="684.7" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="709.1" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="709.1" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="549" y="709.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="610" y="709.1" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-1526668734-matrix">\n    <text class="terminal-1526668734-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-1526668734-line-0)">⭘</text><text class="terminal-1526668734-r2" x="244" y="20" textLength="207.4" clip-path="url(#terminal-1526668734-line-0)">sase&#160;ace&#160;(v0.7.1)</text><text class="terminal-1526668734-r1" x="732" y="20" textLength="12.2" clip-path="url(#terminal-1526668734-line-0)">\n</text><text class="terminal-1526668734-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-1526668734-line-1)">&#160;Agents&#160;</text><text class="terminal-1526668734-r4" x="109.8" y="44.4" textLength="24.4" clip-path="url(#terminal-1526668734-line-1)">&#160;│</text><text class="terminal-1526668734-r5" x="268.4" y="44.4" textLength="366" clip-path="url(#terminal-1526668734-line-1)">&#160;CODEX(visual-snapshot-model)&#160;</text><text class="terminal-1526668734-r7" x="646.6" y="44.4" textLength="24.4" clip-path="url(#terminal-1526668734-line-1)">⚑1</text><text class="terminal-1526668734-r8" x="683.2" y="44.4" textLength="36.6" clip-path="url(#terminal-1526668734-line-1)">✉18</text><text class="terminal-1526668734-r1" x="732" y="44.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-1)">\n</text><text class="terminal-1526668734-r9" x="195.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">1&#160;</text><text class="terminal-1526668734-r9" x="219.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">⬡</text><text class="terminal-1526668734-r4" x="231.8" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="244" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">2&#160;</text><text class="terminal-1526668734-r9" x="268.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">◉</text><text class="terminal-1526668734-r4" x="280.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="292.8" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">3&#160;</text><text class="terminal-1526668734-r9" x="317.2" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">⎇</text><text class="terminal-1526668734-r4" x="329.4" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r10" x="341.6" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">4&#160;</text><text class="terminal-1526668734-r10" x="366" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">◈</text><text class="terminal-1526668734-r11" x="378.2" y="68.8" textLength="61" clip-path="url(#terminal-1526668734-line-2)">&#160;BEAD</text><text class="terminal-1526668734-r4" x="439.2" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="451.4" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">5&#160;</text><text class="terminal-1526668734-r9" x="475.8" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">✎</text><text class="terminal-1526668734-r4" x="488" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">│</text><text class="terminal-1526668734-r9" x="500.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">6&#160;</text><text class="terminal-1526668734-r9" x="524.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">▤</text><text class="terminal-1526668734-r9" x="646.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">{</text><text class="terminal-1526668734-r10" x="658.8" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">██</text><text class="terminal-1526668734-r12" x="683.2" y="68.8" textLength="24.4" clip-path="url(#terminal-1526668734-line-2)">██</text><text class="terminal-1526668734-r9" x="707.6" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">}</text><text class="terminal-1526668734-r1" x="732" y="68.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-2)">\n</text><text class="terminal-1526668734-r11" x="12.2" y="93.2" textLength="24.4" clip-path="url(#terminal-1526668734-line-3)">▌&#160;</text><text class="terminal-1526668734-r2" x="36.6" y="93.2" textLength="36.6" clip-path="url(#terminal-1526668734-line-3)">◈&#160;&#160;</text><text class="terminal-1526668734-r13" x="73.2" y="93.2" textLength="646.6" clip-path="url(#terminal-1526668734-line-3)">The&#160;work&#160;SASE&#160;tracks:&#160;plan&#160;and&#160;epic&#160;beads,&#160;the&#160;phase…</text><text class="terminal-1526668734-r1" x="732" y="93.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-3)">\n</text><text class="terminal-1526668734-r10" x="36.6" y="117.6" textLength="439.2" clip-path="url(#terminal-1526668734-line-4)">┌──────────────────────────────────┐</text><text class="terminal-1526668734-r1" x="732" y="117.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-4)">\n</text><text class="terminal-1526668734-r11" x="12.2" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">/</text><text class="terminal-1526668734-r10" x="36.6" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">│</text><text class="terminal-1526668734-r14" x="61" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">-</text><text class="terminal-1526668734-r15" x="73.2" y="142" textLength="85.4" clip-path="url(#terminal-1526668734-line-5)">status:</text><text class="terminal-1526668734-r16" x="158.6" y="142" textLength="73.2" clip-path="url(#terminal-1526668734-line-5)">closed</text><text class="terminal-1526668734-r15" x="244" y="142" textLength="73.2" clip-path="url(#terminal-1526668734-line-5)">limit:</text><text class="terminal-1526668734-r16" x="317.2" y="142" textLength="36.6" clip-path="url(#terminal-1526668734-line-5)">100</text><text class="terminal-1526668734-r10" x="463.6" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">│</text><text class="terminal-1526668734-r17" x="488" y="142" textLength="109.8" clip-path="url(#terminal-1526668734-line-5)">4&#160;matches</text><text class="terminal-1526668734-r6" x="597.8" y="142" textLength="61" clip-path="url(#terminal-1526668734-line-5)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r10" x="658.8" y="142" textLength="61" clip-path="url(#terminal-1526668734-line-5)">exact</text><text class="terminal-1526668734-r1" x="732" y="142" textLength="12.2" clip-path="url(#terminal-1526668734-line-5)">\n</text><text class="terminal-1526668734-r10" x="36.6" y="166.4" textLength="439.2" clip-path="url(#terminal-1526668734-line-6)">└──────────────────────────────────┘</text><text class="terminal-1526668734-r1" x="732" y="166.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-6)">\n</text><text class="terminal-1526668734-r18" x="97.6" y="190.8" textLength="73.2" clip-path="url(#terminal-1526668734-line-7)">&#160;Bead&#160;</text><text class="terminal-1526668734-r19" x="170.8" y="190.8" textLength="207.4" clip-path="url(#terminal-1526668734-line-7)">&#160;&#160;Project&#160;scope&#160;&#160;</text><text class="terminal-1526668734-r11" x="378.2" y="190.8" textLength="85.4" clip-path="url(#terminal-1526668734-line-7)">&#160;Alpha&#160;</text><text class="terminal-1526668734-r19" x="463.6" y="190.8" textLength="61" clip-path="url(#terminal-1526668734-line-7)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r19" x="524.6" y="190.8" textLength="97.6" clip-path="url(#terminal-1526668734-line-7)">p&#160;change</text><text class="terminal-1526668734-r1" x="732" y="190.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-7)">\n</text><text class="terminal-1526668734-r1" x="732" y="215.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-8)">\n</text><text class="terminal-1526668734-r10" x="0" y="239.6" textLength="536.8" clip-path="url(#terminal-1526668734-line-9)">╭─&#160;Beads&#160;──────────────────────────────────╮</text><text class="terminal-1526668734-r20" x="536.8" y="239.6" textLength="195.2" clip-path="url(#terminal-1526668734-line-9)">╭─&#160;Details&#160;────╮</text><text class="terminal-1526668734-r1" x="732" y="239.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-9)">\n</text><text class="terminal-1526668734-r10" x="0" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r10" x="24.4" y="264" textLength="109.8" clip-path="url(#terminal-1526668734-line-10)">2/2&#160;tasks</text><text class="terminal-1526668734-r19" x="134.2" y="264" textLength="61" clip-path="url(#terminal-1526668734-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r21" x="195.2" y="264" textLength="109.8" clip-path="url(#terminal-1526668734-line-10)">0/0&#160;flags</text><text class="terminal-1526668734-r19" x="305" y="264" textLength="61" clip-path="url(#terminal-1526668734-line-10)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r22" x="366" y="264" textLength="109.8" clip-path="url(#terminal-1526668734-line-10)">1/1&#160;epics</text><text class="terminal-1526668734-r19" x="475.8" y="264" textLength="36.6" clip-path="url(#terminal-1526668734-line-10)">&#160;&#160;…</text><text class="terminal-1526668734-r10" x="524.6" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r20" x="536.8" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r20" x="719.8" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">│</text><text class="terminal-1526668734-r1" x="732" y="264" textLength="12.2" clip-path="url(#terminal-1526668734-line-10)">\n</text><text class="terminal-1526668734-r10" x="0" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r10" x="524.6" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r20" x="536.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r20" x="719.8" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">│</text><text class="terminal-1526668734-r1" x="732" y="288.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-11)">\n</text><text class="terminal-1526668734-r10" x="0" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r23" x="12.2" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">▊</text><text class="terminal-1526668734-r24" x="24.4" y="312.8" textLength="488" clip-path="url(#terminal-1526668734-line-12)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1526668734-r24" x="512.4" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r20" x="536.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r25" x="585.6" y="312.8" textLength="61" clip-path="url(#terminal-1526668734-line-12)">Beads</text><text class="terminal-1526668734-r20" x="719.8" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">│</text><text class="terminal-1526668734-r1" x="732" y="312.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-12)">\n</text><text class="terminal-1526668734-r10" x="0" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r23" x="12.2" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="337.2" textLength="109.8" clip-path="url(#terminal-1526668734-line-13)">──&#160;Tasks&#160;</text><text class="terminal-1526668734-r26" x="146.4" y="337.2" textLength="73.2" clip-path="url(#terminal-1526668734-line-13)">(2/2)&#160;</text><text class="terminal-1526668734-r11" x="219.6" y="337.2" textLength="256.2" clip-path="url(#terminal-1526668734-line-13)">·&#160;✦&#160;1&#160;awaiting&#160;triag…</text><text class="terminal-1526668734-r24" x="512.4" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r20" x="536.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r20" x="719.8" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">│</text><text class="terminal-1526668734-r1" x="732" y="337.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-13)">\n</text><text class="terminal-1526668734-r10" x="0" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r23" x="12.2" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">◆&#160;</text><text class="terminal-1526668734-r27" x="61" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">·&#160;</text><text class="terminal-1526668734-r11" x="85.4" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">✦&#160;</text><text class="terminal-1526668734-r28" x="109.8" y="361.6" textLength="146.4" clip-path="url(#terminal-1526668734-line-14)">alpha-ready&#160;</text><text class="terminal-1526668734-r29" x="256.2" y="361.6" textLength="195.2" clip-path="url(#terminal-1526668734-line-14)">Ready&#160;for&#160;triage</text><text class="terminal-1526668734-r2" x="451.4" y="361.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-14)">&#160;…</text><text class="terminal-1526668734-r24" x="512.4" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r20" x="536.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r2" x="573.4" y="361.6" textLength="97.6" clip-path="url(#terminal-1526668734-line-14)">Select&#160;a</text><text class="terminal-1526668734-r20" x="719.8" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">│</text><text class="terminal-1526668734-r1" x="732" y="361.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-14)">\n</text><text class="terminal-1526668734-r10" x="0" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r23" x="12.2" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="386" textLength="24.4" clip-path="url(#terminal-1526668734-line-15)">◆&#160;</text><text class="terminal-1526668734-r27" x="61" y="386" textLength="24.4" clip-path="url(#terminal-1526668734-line-15)">·&#160;</text><text class="terminal-1526668734-r28" x="85.4" y="386" textLength="134.2" clip-path="url(#terminal-1526668734-line-15)">alpha-open&#160;</text><text class="terminal-1526668734-r29" x="219.6" y="386" textLength="219.6" clip-path="url(#terminal-1526668734-line-15)">Ordinary&#160;follow-up</text><text class="terminal-1526668734-r15" x="463.6" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">…</text><text class="terminal-1526668734-r24" x="512.4" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r20" x="536.8" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r2" x="573.4" y="386" textLength="61" clip-path="url(#terminal-1526668734-line-15)">task,</text><text class="terminal-1526668734-r20" x="719.8" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">│</text><text class="terminal-1526668734-r1" x="732" y="386" textLength="12.2" clip-path="url(#terminal-1526668734-line-15)">\n</text><text class="terminal-1526668734-r10" x="0" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r23" x="12.2" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="410.4" textLength="109.8" clip-path="url(#terminal-1526668734-line-16)">──&#160;Flags&#160;</text><text class="terminal-1526668734-r26" x="146.4" y="410.4" textLength="73.2" clip-path="url(#terminal-1526668734-line-16)">(0/0)&#160;</text><text class="terminal-1526668734-r30" x="219.6" y="410.4" textLength="97.6" clip-path="url(#terminal-1526668734-line-16)">────────</text><text class="terminal-1526668734-r24" x="512.4" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r20" x="536.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r2" x="573.4" y="410.4" textLength="61" clip-path="url(#terminal-1526668734-line-16)">flag,</text><text class="terminal-1526668734-r20" x="719.8" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">│</text><text class="terminal-1526668734-r1" x="732" y="410.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-16)">\n</text><text class="terminal-1526668734-r10" x="0" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r23" x="12.2" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">▊</text><text class="terminal-1526668734-r26" x="36.6" y="434.8" textLength="292.8" clip-path="url(#terminal-1526668734-line-17)">&#160;&#160;No&#160;matching&#160;flag&#160;beads</text><text class="terminal-1526668734-r24" x="512.4" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r20" x="536.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r2" x="573.4" y="434.8" textLength="97.6" clip-path="url(#terminal-1526668734-line-17)">epic,&#160;or</text><text class="terminal-1526668734-r20" x="719.8" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">│</text><text class="terminal-1526668734-r1" x="732" y="434.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-17)">\n</text><text class="terminal-1526668734-r10" x="0" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r23" x="12.2" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="459.2" textLength="109.8" clip-path="url(#terminal-1526668734-line-18)">──&#160;Epics&#160;</text><text class="terminal-1526668734-r26" x="146.4" y="459.2" textLength="73.2" clip-path="url(#terminal-1526668734-line-18)">(1/1)&#160;</text><text class="terminal-1526668734-r26" x="219.6" y="459.2" textLength="24.4" clip-path="url(#terminal-1526668734-line-18)">·&#160;</text><text class="terminal-1526668734-r14" x="244" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">⊜</text><text class="terminal-1526668734-r26" x="256.2" y="459.2" textLength="109.8" clip-path="url(#terminal-1526668734-line-18)">&#160;blocked&#160;</text><text class="terminal-1526668734-r32" x="366" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">►</text><text class="terminal-1526668734-r26" x="378.2" y="459.2" textLength="85.4" clip-path="url(#terminal-1526668734-line-18)">&#160;ready&#160;</text><text class="terminal-1526668734-r33" x="463.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">…</text><text class="terminal-1526668734-r24" x="512.4" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r20" x="536.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r2" x="573.4" y="459.2" textLength="61" clip-path="url(#terminal-1526668734-line-18)">phase</text><text class="terminal-1526668734-r20" x="719.8" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">│</text><text class="terminal-1526668734-r1" x="732" y="459.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-18)">\n</text><text class="terminal-1526668734-r10" x="0" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r23" x="12.2" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">▊</text><text class="terminal-1526668734-r11" x="36.6" y="483.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-19)">▸&#160;</text><text class="terminal-1526668734-r28" x="61" y="483.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-19)">▸&#160;</text><text class="terminal-1526668734-r34" x="85.4" y="483.6" textLength="24.4" clip-path="url(#terminal-1526668734-line-19)">▤&#160;</text><text class="terminal-1526668734-r28" x="109.8" y="483.6" textLength="97.6" clip-path="url(#terminal-1526668734-line-19)">alpha-1&#160;</text><text class="terminal-1526668734-r35" x="207.4" y="483.6" textLength="231.8" clip-path="url(#terminal-1526668734-line-19)">Build&#160;bead&#160;browsing</text><text class="terminal-1526668734-r15" x="463.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">…</text><text class="terminal-1526668734-r24" x="512.4" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r20" x="536.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r2" x="573.4" y="483.6" textLength="61" clip-path="url(#terminal-1526668734-line-19)">bead.</text><text class="terminal-1526668734-r20" x="719.8" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">│</text><text class="terminal-1526668734-r1" x="732" y="483.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-19)">\n</text><text class="terminal-1526668734-r10" x="0" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r23" x="12.2" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r20" x="536.8" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r20" x="719.8" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">│</text><text class="terminal-1526668734-r1" x="732" y="508" textLength="12.2" clip-path="url(#terminal-1526668734-line-20)">\n</text><text class="terminal-1526668734-r10" x="0" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r23" x="12.2" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r20" x="536.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r20" x="719.8" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">│</text><text class="terminal-1526668734-r1" x="732" y="532.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-21)">\n</text><text class="terminal-1526668734-r10" x="0" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r23" x="12.2" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r20" x="536.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r20" x="719.8" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">│</text><text class="terminal-1526668734-r1" x="732" y="556.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-22)">\n</text><text class="terminal-1526668734-r10" x="0" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r23" x="12.2" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r20" x="536.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r20" x="719.8" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">│</text><text class="terminal-1526668734-r1" x="732" y="581.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-23)">\n</text><text class="terminal-1526668734-r10" x="0" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r23" x="12.2" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">▊</text><text class="terminal-1526668734-r24" x="512.4" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r20" x="536.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r20" x="719.8" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">│</text><text class="terminal-1526668734-r1" x="732" y="605.6" textLength="12.2" clip-path="url(#terminal-1526668734-line-24)">\n</text><text class="terminal-1526668734-r10" x="0" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r23" x="12.2" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">▊</text><text class="terminal-1526668734-r24" x="24.4" y="630" textLength="488" clip-path="url(#terminal-1526668734-line-25)">▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁</text><text class="terminal-1526668734-r24" x="512.4" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">▎</text><text class="terminal-1526668734-r10" x="524.6" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r20" x="536.8" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r20" x="719.8" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">│</text><text class="terminal-1526668734-r1" x="732" y="630" textLength="12.2" clip-path="url(#terminal-1526668734-line-25)">\n</text><text class="terminal-1526668734-r10" x="0" y="654.4" textLength="536.8" clip-path="url(#terminal-1526668734-line-26)">╰──────────────────────────────────────────╯</text><text class="terminal-1526668734-r20" x="536.8" y="654.4" textLength="195.2" clip-path="url(#terminal-1526668734-line-26)">╰──────────────╯</text><text class="terminal-1526668734-r1" x="732" y="654.4" textLength="12.2" clip-path="url(#terminal-1526668734-line-26)">\n</text><text class="terminal-1526668734-r11" x="0" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">j</text><text class="terminal-1526668734-r19" x="12.2" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;next</text><text class="terminal-1526668734-r19" x="73.2" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="134.2" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">k</text><text class="terminal-1526668734-r19" x="146.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;prev</text><text class="terminal-1526668734-r19" x="207.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="268.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">Enter</text><text class="terminal-1526668734-r19" x="329.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;view</text><text class="terminal-1526668734-r19" x="390.4" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="451.4" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">f</text><text class="terminal-1526668734-r19" x="463.6" y="678.8" textLength="85.4" clip-path="url(#terminal-1526668734-line-27)">&#160;filter</text><text class="terminal-1526668734-r19" x="549" y="678.8" textLength="61" clip-path="url(#terminal-1526668734-line-27)">&#160;&#160;·&#160;&#160;</text><text class="terminal-1526668734-r11" x="610" y="678.8" textLength="73.2" clip-path="url(#terminal-1526668734-line-27)">Ctrl+J</text><text class="terminal-1526668734-r19" x="683.2" y="678.8" textLength="48.8" clip-path="url(#terminal-1526668734-line-27)">&#160;mo…</text><text class="terminal-1526668734-r1" x="732" y="678.8" textLength="12.2" clip-path="url(#terminal-1526668734-line-27)">\n</text><text class="terminal-1526668734-r36" x="0" y="703.2" textLength="732" clip-path="url(#terminal-1526668734-line-28)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-1526668734-r1" x="732" y="703.2" textLength="12.2" clip-path="url(#terminal-1526668734-line-28)">\n</text><text class="terminal-1526668734-r35" x="549" y="727.6" textLength="61" clip-path="url(#terminal-1526668734-line-29)">&#160;AXE&#160;</text><text class="terminal-1526668734-r35" x="610" y="727.6" textLength="109.8" clip-path="url(#terminal-1526668734-line-29)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
_______ test_family_panel_fold_levels_and_member_override_png_snapshots ________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac..._family_panel.py', test_line=34, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb30d535630>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw0/test_family_panel_fold_levels_0')

    async def test_family_panel_fold_levels_and_member_override_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(tmp_path, member_count=3, with_content=True),
        )
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            container_identity = container.identity
            assert container.is_family_container_row is True
            assert len(page.app._member_jump_maps[container_identity].targets) == 3
            ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_level_1_120x40",
                title="ACE family panel fold level 1",
            )
    
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                await page.press("ctrl+j")
                if panel.active_section_identity == "agent-xprompt":
                    break
            assert panel.active_section_identity == "agent-xprompt"
            await wait_for_visual_idle(page)
            ace_png_visual.assert_page_png(
                page,
                "agents_family_conversation_level_1_120x40",
                title="ACE family conversation at fold level 1",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level is FoldLevel.FULLY_EXPANDED
            await wait_for_visual_idle(page)
            assert panel.active_section_identity == "agent-xprompt"
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_conversation_level_2_120x40",
                title="ACE family conversation at fold level 2",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:79: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_conversation_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02-\x15IDA...10B\x08!\x84\x10B\x08!\x84\x0c=z\xf4+\xa8_\x07\x11\xb8\xd3k\x83\xff\x07\xbav=\x16WZL\x8b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-3033066951-line-39)">cleanup&#160;(1&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py'
test_line = 34
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_family_conversation_level_2_120x40.png
E       Changed pixels: 287/1520532 (0.018875%); materially changed pixels: 267/1520532 (0.017560%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_conversation_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_family_gate_shells_png_snapshots _____________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ly_panel_gate.py', test_line=32, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2ecb6a5f0>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw0/test_family_gate_shells_png_sn0')

    async def test_family_gate_shells_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_gate_family_agents(tmp_path),
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
            assert [shell.is_gate for shell in shells] == [
                False,
                False,
                True,
                True,
                True,
                True,
            ]
            assert [shell.gate_state for shell in shells if shell.is_gate] == [
                "pending",
                "settling",
                "answered",
                "failed",
            ]
            assert_page_svg_contains(page, "Shells:")
            assert_page_svg_contains(page, "pending")
            assert_page_svg_contains(page, "settling")
            assert_page_svg_contains(page, "answered")
            assert_page_svg_contains(page, "failed")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_gate_120x40",
                title="ACE family panel shell metadata with gate rows",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:76: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_gate_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x1dUIDA...10B\x08!\x03\x8fS\xfa\x15\xd6\xaf\xbd\x08\xdc\xe9\x95\xe0\x7f\x03\xee{\xd6iq\xa2\x97\x1d\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-3776423625-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py'
test_line = 32
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_120x40.png
E       Changed pixels: 131/1520532 (0.008615%); materially changed pixels: 129/1520532 (0.008484%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_family_gate_shells_narrow_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ly_panel_gate.py', test_line=83, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2ea1f15c0>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw0/test_family_gate_shells_narrow0')

    async def test_family_gate_shells_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_gate_family_agents(tmp_path),
        )
    
        async with AcePage(
            query='"visual-family-root"',
            size=(90, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-family")
            assert_page_svg_contains(page, "⋔")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_gate_90x40",
                title="ACE family panel gate shells narrow",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_gate_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01#BIDATx\x9...0\x00\xb0@\xf8\x9b\x04@!\\\xb6K\xca.Cj\x90\x9bm\x87\xff\x00\x80\x06\xd6\xc7\x87\xeb"\x94\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_narrow_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1116 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-3352958946-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py'
test_line = 83
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_90x40.png
E       Changed pixels: 131/1145016 (0.011441%); materially changed pixels: 129/1145016 (0.011266%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...panel_monitor.py', test_line=33, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2e8f6bee0>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw0/test_family_panel_shells_monit0')

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
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xff\x07...x08!\x84\x90\xe2\xe3\xac\xfe\x04\xf5\xe7\x08\x12w\xba\xad\xf0\xef\xf7\x12J\xe6\x90H2\x13\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2034667708-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py'
test_line = 33
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_120x40.png
E       Changed pixels: 99/1520532 (0.006511%); materially changed pixels: 93/1520532 (0.006116%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...anel_monitor.py', test_line=114, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2ebee0980>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw0/test_family_conversation_monit0')

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
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xe8\xf9...\x00\x00\x00\x00X|\xceG?\x99\xe8\xe7\xb4\x06\xeeLz\xc1\xff\x03\x14\x89n\x0f\x91\x8d\xe7+\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... y="971.6" textLength="85.4" clip-path="url(#terminal-853941433-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py'
test_line = 114
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
E       Changed pixels: 99/1520532 (0.006511%); materially changed pixels: 93/1520532 (0.006116%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________ test_agents_lane_neighbors_section_fold_levels_png_snapshots _________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ts_neighbors.py', test_line=452, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2ecbc4590>

    async def test_agents_lane_neighbors_section_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, _LANE_NOW)
        patch_startup_loaders(monkeypatch, agents=_single_lane_neighbor_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=(160, 50)) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 6)
            lane = next(
                agent
                for agent in page.app._agents
                if agent.agent_name == "visual.lane.plan"
            )
            lane_identity = lane.identity
            page.app.current_idx = page.app._agents.index(lane)
            await wait_for_svg_contains(page, "NEIGHBORS")
            await wait_for_visual_idle(page)
    
            # A startup refresh may replace and reorder the Agent instances while
            # preserving their stable identities. Re-resolve the row after the
            # startup frame settles so the numeric selection cannot drift onto a
            # different lane under contention.
            lane = next(
                agent for agent in page.app._agents if agent.identity == lane_identity
            )
            page.app.current_idx = page.app._agents.index(lane)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].identity == lane_identity
            jump_map = page.app._member_jump_maps[lane.identity]
            assert [target.number for target in jump_map.targets] == ["0", "1", "2"]
            assert {target.role for target in jump_map.targets} == {"neighbor"}
            assert_page_svg_contains(page, "NEIGHBORS")
            assert_page_svg_contains(page, "visual.lane hood")
            assert_page_svg_contains(page, "more neighbors")
    
            ace_png_visual.assert_page_png(
                page,
                "agents_lane_neighbors_section_first_level_160x50",
                title="ACE lane neighbors section first fold level",
            )
    
            await page.press("z", "z")
            assert page.app.panel_fold_level is FoldLevel.EXPANDED
            await wait_for_svg_contains(page, "visual hood")
            await wait_for_visual_idle(page)
    
            expanded_map = page.app._member_jump_maps[lane.identity]
            assert [target.number for target in expanded_map.targets] == list("01234")
            assert_page_svg_contains(page, ".bench")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_lane_neighbors_section_expanded_160x50",
                title="ACE lane neighbors section expanded",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:507: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_lane_neighbors_section_expanded_160x50'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x07\xb2\x00\x00\x04\xf6\x08\x06\x00\x00\x00\xaf7\xec\x82\x00\x031;IDATx\...\x08!\x84\x10B\x08\xd1<\x87\xe2\xd7H\xfcz&v`\x1fJ\xdb\xe1\xff\x03\xe2"\xfdz\x90\xbbl\xac\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_section_fold_levels_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1970 1270.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="195.2" clip-path="url(#terminal-1218152774-line-49)">cleanup&#160;(4&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py'
test_line = 452
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_expanded_160x50.png
E       Changed pixels: 1250/2501900 (0.049962%); materially changed pixels: 1250/2501900 (0.049962%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_expanded_160x50/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________ test_models_panel_builtin_selection_effort_step_png_snapshot _________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...l_navigation.py', test_line=190, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe4fddc0980>

    async def test_models_panel_builtin_selection_effort_step_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        _patch_alias_views(monkeypatch, calm_views)
        monkeypatch.setattr(models_panel, "_now", lambda: FROZEN_NOW)
        monkeypatch.setattr(
            ModelsPanel,
            "_load_effective_effort_snapshot",
            lambda self: (effort_snapshot(), True),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_override_picker(page)
            await page.press("enter")
            await page.expect_modal("DefaultEffortLevelModal")
            await wait_for_svg_contains(page, "Reasoning Effort")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "models_panel_builtin_effort_picker_120x40",
                title="ACE Launch Control — effort after builtin model",
            )

tests/ace/tui/visual/test_ace_png_snapshots_models_panel_navigation.py:210: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'models_panel_builtin_effort_picker_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfc\x19...00\x00\x00\x00\xb0z.\xfd\xeb\xcc\xbf\xbe\xd6\xc0\x9dy\x13\xfc\x1b\x9a\xab\xaeU(J\xe9\xee\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_models_panel_navigation.py::test_models_panel_builtin_selection_effort_step_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3103516006-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_models_panel_navigation.py'
test_line = 190
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/models_panel_builtin_effort_picker_120x40.png
E       Changed pixels: 110/1520532 (0.007234%); materially changed pixels: 106/1520532 (0.006971%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_navigation.py__test_models_panel_builtin_selection_effort_step_png_snapshot/models_panel_builtin_effort_picker_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_navigation.py__test_models_panel_builtin_selection_effort_step_png_snapshot/models_panel_builtin_effort_picker_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_navigation.py__test_models_panel_builtin_selection_effort_step_png_snapshot/models_panel_builtin_effort_picker_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_models_panel_navigation.py__test_models_panel_builtin_selection_effort_step_png_snapshot/models_panel_builtin_effort_picker_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_agents_task_bead_notes_png_snapshot ___________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...sase_context.py', test_line=288, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2d71a17f0>
tmp_path = PosixPath('/var/tmp/sase-f777dba6/pytest-of-bryan/pytest-2/popen-gw0/test_agents_task_bead_notes_pn0')

    async def test_agents_task_bead_notes_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        notes = (
            "[2026-08-01T14:03:00Z · alice] Confirmed the notes row belongs "
            "directly under the task description.\n\n"
            "[2026-08-01T14:07:00Z · bob] This second note is intentionally long "
            "enough to wrap in the BEAD lane while keeping attribution readable."
        )
        bead = BeadSummary(
            id="sase-notes.4",
            phase_title="Display persisted bead notes",
            description="Render task metadata without requiring a plan file.",
            actual_plan_path=None,
            display_plan_path=None,
            plan_exists=False,
            plan_readable=False,
            epic_title=None,
            size="medium",
            created_at="2026-07-03T13:00:00Z",
            bead_type="task",
            notes=notes,
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-task-notes",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 8, 1, 14, 0, 0),
            raw_suffix="20260801140000",
            agent_name="sase-notes.4",
            step_type="bash",
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.prompt_panel._agent_display_header_summary."
            "resolve_agent_plan_enrichment",
            lambda *_args, **_kwargs: _AgentPlanEnrichment("task", bead, None, ()),
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual-task-notes"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "Notes:")
            await page.press("z", "z")
            await wait_for_svg_contains(page, "alice")
            await wait_for_svg_contains(page, "attribution readable")
            await wait_for_visual_idle(page)
    
            svg_plain = page.export_svg(title="ACE task BEAD notes assertion").replace(
                "&#160;",
                " ",
            )
            assert "Task Title:" in svg_plain
            assert "Description:" in svg_plain
            assert "Notes:" in svg_plain
>           assert "Size:" in svg_plain
E           assert 'Size:' in '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric..." y="971.6" textLength="85.4" clip-path="url(#terminal-61125597-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:351: AssertionError
____________________ test_update_panel_pending_png_snapshot ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...update_panel.py', test_line=138, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe518544600>

    async def test_update_panel_pending_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Populated rows: core rebuild and manual-steps providers."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
    
            option_list = await _push_update_panel(page, _pending_state())
            await wait_for_state(
                page,
                lambda: (
                    option_list.option_count == 3
                    and "e/E" in _option_plain(option_list, 0)
                    and "core rebuild" in _option_plain(option_list, 1)
                    and "needs manual steps" in _option_plain(option_list, 2)
                ),
                description="pending Update panel rows",
            )
            await wait_for_svg_contains(page, "core rebuild")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "update_panel_pending_120x40",
                title="ACE Update panel (pending)",
            )

tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py:164: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'update_panel_pending_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfc\x16...00\x00\x00\x00\x00\x00\x00\xa0\xfe\xacG\xb7\xe5\xe86\xad\x81;\x93&\xf8g\xde-\x86G\xcfs{!\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_pending_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3471882741-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py'
test_line = 138
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/update_panel_pending_120x40.png
E       Changed pixels: 244012/1520532 (16.047804%); materially changed pixels: 229114/1520532 (15.068016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_pending_png_snapshot/update_panel_pending_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_update_panel_unchecked_png_snapshot ___________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...update_panel.py', test_line=171, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe4fc72c670>

    async def test_update_panel_unchecked_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Never-checked evidence still renders three selectable unknown rows."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
    
            option_list = await _push_update_panel(page, _unchecked_state())
            await wait_for_state(
                page,
                lambda: (
                    option_list.option_count == 3
                    and "e/E" in _option_plain(option_list, 0)
                    and all(
                        "· not checked yet" in _option_plain(option_list, index)
                        for index in range(3)
                    )
                ),
                description="never-checked Update panel rows",
            )
            await wait_for_svg_contains(page, "never checked")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "update_panel_unchecked_120x40",
                title="ACE Update panel (never checked)",
            )

tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py:199: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'update_panel_unchecked_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf0EIDA...x00\x00\x80\xd6\xb3\x11\xddV\xa2\xdb\xb4\x06\xeeL\x9a\xe0?\x00\xca\xf6\x9eJ\xdb\x9f+\xe3\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_unchecked_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-864792578-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py'
test_line = 171
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/update_panel_unchecked_120x40.png
E       Changed pixels: 189561/1520532 (12.466755%); materially changed pixels: 184696/1520532 (12.146801%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_panel.py__test_update_panel_unchecked_png_snapshot/update_panel_unchecked_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_axe_lumberjack_tree_png_snapshot _____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...snapshots_axe.py', test_line=66, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f085f750d70>

    async def test_axe_lumberjack_tree_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Lumberjack tree with expanded chops and a bgcmd row below."""
        patch_startup_loaders(monkeypatch, axe_data=axe_lumberjack_tree_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_lumberjack_tree_120x40",
                title="ACE axe lumberjack tree",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe.py:79: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_lumberjack_tree_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xccpIDA...08!\x84\x10B\x08!\x84\x10B\x081\xfb\x18\t\x96\xa1`\xe9#qg\\\x81\xb7\x01}\xa7{k\xa0&:\x90\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_lumberjack_tree_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... textLength="73.2" clip-path="url(#terminal-4254261217-line-39)">&#160;[✓1]&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py', test_line = 66
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_lumberjack_tree_120x40.png
E       Changed pixels: 3043/1520532 (0.200127%); materially changed pixels: 3043/1520532 (0.200127%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_lumberjack_tree_png_snapshot/axe_lumberjack_tree_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_axe_chop_overrun_png_snapshot ______________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...napshots_axe.py', test_line=129, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f08530b3e70>

    async def test_axe_chop_overrun_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The sidebar chips, roll-up chip, PACE column, and advisory line together."""
        patch_startup_loaders(monkeypatch, axe_data=axe_chop_overrun_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await _pin_axe_output_top(page, hide_scrollbar=True)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_chop_overrun_120x40",
                title="ACE axe chop overrun",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe.py:143: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_chop_overrun_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb7\x01...0\x00\x00\x80\xf5\xe7\xa9\xc1\xcf\xee\xc1\xcf72pg\xd7\x13\xfe\x7f\x83}.\x8b\x18\x8c$\x06\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-2634223678-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py'
test_line = 129
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_chop_overrun_120x40.png
E       Changed pixels: 2989/1520532 (0.196576%); materially changed pixels: 2989/1520532 (0.196576%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_png_snapshot/axe_chop_overrun_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_axe_chop_overrun_narrow_png_snapshot ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...napshots_axe.py', test_line=150, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f08604d1cc0>

    async def test_axe_chop_overrun_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The overrun indicators degrade sanely in the narrow compact layout."""
        patch_startup_loaders(monkeypatch, axe_data=axe_chop_overrun_data())
    
        async with AcePage(query='"visual"', patches=patches(), size=(70, 36)) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await _pin_axe_output_top(page, hide_scrollbar=True)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_chop_overrun_narrow_70x36",
                title="ACE axe chop overrun narrow",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe.py:164: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_chop_overrun_narrow_70x36'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x03h\x00\x00\x03\xa0\x08\x06\x00\x00\x00H\xadU\xe4\x00\x01{oIDATx\x9c\xe...VE\xc6\x8f\x8d\x9f\xf8\xc4\'\x1e\x8b\xde\xf2\xf7\xde\xf81\xff\x01\xcc\xffX\xb3iR\xbb\x04\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_narrow_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 872 928.4" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...tLength="109.8" clip-path="url(#terminal-3300072793-line-35)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe.py'
test_line = 150
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_chop_overrun_narrow_70x36.png
E       Changed pixels: 27052/809216 (3.342989%); materially changed pixels: 26970/809216 (3.332856%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe.py__test_axe_chop_overrun_narrow_png_snapshot/axe_chop_overrun_narrow_70x36/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_tribe_panel_four_level_png_snapshots ___________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac..._tribe_panel.py', test_line=355, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb310d4b230>

    async def test_tribe_panel_four_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            epic_index = page.app._panel_group.panel_keys.index("epic")
            epic_panel = list(page.app.query("AgentList"))[epic_index]
            assert Text.from_markup(epic_panel.border_title).plain == (
                "▲ @epic · 2 [R1 F1]"
            )
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
    
            await page.press("=")
            await page.wait_for(
                lambda _screen: (
                    None in page.app._collapsed_panel_keys
                    and page.app._panel_isolation_revert is not None
                )
            )
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "↺")
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            bindings, _mode_label = footer._last_layout_inputs
            assert ("H", "collapse fold") in bindings
            assert ("=", "restore panels") in bindings
            ace_png_visual.assert_page_png(
                page,
                "agents_tribe_panel_isolation_armed_120x40",
                title="ACE tribe panel isolation restore markers",
            )
    
            await page.press("=")
            await page.wait_for(
                lambda _screen: (
                    None not in page.app._collapsed_panel_keys
                    and page.app._panel_isolation_revert is None
                )
            )
            await page.press("h")
            await page.wait_for(lambda _screen: "epic" in page.app._collapsed_panel_keys)
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "TRIBE")
            assert_page_svg_contains(page, "@epic")
            tribe_summary = page.app._focused_tribe_summary()
            assert tribe_summary is not None
            assert tribe_summary.lane_count == 2
            assert_page_svg_contains(page, "lanes")
            assert_page_svg_contains(page, "NEEDS ATTENTION")
            assert page.app._member_jump_maps[("panel", "epic")].targets
            ace_png_visual.assert_page_png(
                page,
                "agents_tribe_panel_level_1_120x40",
                title="ACE tribe panel glance",
            )
    
            await page.press("z", "1")
            assert page.app.panel_fold_level.value == "collapsed"
            assert page.app._member_jump_pending_digit is None
    
            for position, fold_value, snapshot_name, title in (
                (
                    "2",
                    "expanded",
                    "agents_tribe_panel_level_2_120x40",
                    "ACE tribe panel triage",
                ),
                (
                    "3",
                    "fully_expanded",
                    "agents_tribe_panel_level_3_120x40",
                    "ACE tribe panel inspect",
                ),
                (
                    "4",
                    "exhaustive",
                    "agents_tribe_panel_level_4_120x40",
                    "ACE tribe panel forensics",
                ),
            ):
                selected_idx = page.app.current_idx
                await page.press("z", position)
                assert page.app.panel_fold_level.value == fold_value
                assert page.app._member_jump_pending_digit is None
                assert page.app.current_idx == selected_idx
                assert page.app._resolve_focused_panel() is not None
                await wait_for_visual_idle(page)
>               ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:457: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_tribe_panel_level_2_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xd6\x08...\x00\x00\x00\x80\xab\xcfe\xef\x91\xf0\x1e\'\xb4pg\xd0\x06\xff\x03P\x98\xc8\x8f.\xc6N\xab\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...h="195.2" clip-path="url(#terminal-922010455-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py'
test_line = 355
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/agents_tribe_panel_level_2_120x40.png
E       Changed pixels: 1058/1520532 (0.069581%); materially changed pixels: 1032/1520532 (0.067871%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_tribe_panel.py__test_tribe_panel_four_level_png_snapshots/agents_tribe_panel_level_2_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_axe_lumberjack_description_png_snapshot _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac..._descriptions.py', test_line=23, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0845acf620>

    async def test_axe_lumberjack_description_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A selected lumberjack keeps its description above scrolling output."""
        patch_startup_loaders(monkeypatch, axe_data=axe_lumberjack_tree_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            page.app._refresh_axe_display()
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_lumberjack_description_120x40",
                title="ACE axe lumberjack description banner",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py:37: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_lumberjack_description_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xd0\xa2...x84\x10B\x08!\x84\x10B\x08!F\x1e\'\xc2\xa5?\\\x0e\x91\xb83n\x85\xf7\x01\xc9a\x15c%3H\x8b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py::test_axe_lumberjack_description_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... textLength="73.2" clip-path="url(#terminal-1710613867-line-39)">&#160;[✓1]&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py'
test_line = 23
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_lumberjack_description_120x40.png
E       Changed pixels: 3043/1520532 (0.200127%); materially changed pixels: 3043/1520532 (0.200127%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_descriptions.py__test_axe_lumberjack_description_png_snapshot/axe_lumberjack_description_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
__________________ test_axe_long_label_widening_png_snapshot ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ts_axe_layout.py', test_line=54, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0860027540>

    async def test_axe_long_label_widening_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Long lumberjack/chop labels widen the sidebar without wrapping."""
        patch_startup_loaders(monkeypatch, axe_data=axe_long_label_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
    
            sidebar = page.app.query_one("#bgcmd-list-container")
            width = sidebar.styles.width
            assert width is not None, "expected sidebar to have a width set"
            sidebar_width = int(width.value)
            assert sidebar_width > _MIN_BGCMD_LIST_WIDTH, (
                f"expected sidebar to widen past {_MIN_BGCMD_LIST_WIDTH}, "
                f"got {sidebar_width}"
            )
            # The AXE footer repaint can lag the tab change under xdist; settle
            # only the footer so the dashboard golden stays focused on layout.
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            footer.update_axe_bindings(axe_current_view=page.app._axe_current_view)
            await wait_for_state(
                page,
                lambda: _axe_long_label_summary_populated(page),
                description="populated AXE long-label status summary",
            )
            await _pin_axe_output_top(page)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_long_label_widened_120x40",
                title="ACE axe long-label widened sidebar",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py:86: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_long_label_widened_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01[\x95IDA...x00\x00\x13\xcf\xbe\xdam\xa0v\xdb\x1c\x17\xee\x1cm\x87\x7f\x07\x97k\xce\xdd\xbdg\x08\xae\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_long_label_widening_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...6" textLength="73.2" clip-path="url(#terminal-78485834-line-39)">&#160;[✓1]&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py'
test_line = 54
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_long_label_widened_120x40.png
E       Changed pixels: 11748/1520532 (0.772624%); materially changed pixels: 11748/1520532 (0.772624%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_long_label_widening_png_snapshot/axe_long_label_widened_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_axe_constrained_width_no_wrap_png_snapshot ________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ts_axe_layout.py', test_line=93, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f08530b3e70>

    async def test_axe_constrained_width_no_wrap_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Narrow terminal with long labels proves no-wrap + ellipsis behavior."""
        patch_startup_loaders(monkeypatch, axe_data=axe_long_label_data())
    
        # 60x30 is small enough that the sidebar gets clamped to its minimum and
        # the long lumberjack/chop labels can't fit — they must ellipsize on a
        # single line rather than wrap.
        async with AcePage(query='"visual"', patches=patches(), size=(60, 30)) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await wait_for_state(
                page,
                lambda: _axe_long_label_summary_populated(page),
                description="populated AXE long-label status summary",
            )
            await _pin_axe_output_top(page)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_constrained_width_no_wrap_60x30",
                title="ACE axe constrained width no-wrap",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py:115: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_constrained_width_no_wrap_60x30'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x02\xee\x00\x00\x03\x0e\x08\x06\x00\x00\x00A.\x83\xfc\x00\x01\x1buIDATx\...\x1b\x00\x00\x00\x00\x85r0\xb84\x06\x97\xb74\x105j\x81\xff\x1f\xff\xcb\xca\xe2\xbbN\x02.\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_constrained_width_no_wrap_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 750 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...6" textLength="109.8" clip-path="url(#terminal-952786875-line-29)">start&#160;axe</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py'
test_line = 93
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_constrained_width_no_wrap_60x30.png
E       Changed pixels: 10835/586500 (1.847400%); materially changed pixels: 10834/586500 (1.847229%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_layout.py__test_axe_constrained_width_no_wrap_png_snapshot/axe_constrained_width_no_wrap_60x30/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_axe_lumberjack_error_png_snapshot ____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...hots_axe_runs.py', test_line=88, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f083e3ab380>

    async def test_axe_lumberjack_error_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Errored lumberjack exercises red/warning styling in tree row + panel."""
        patch_startup_loaders(monkeypatch, axe_data=axe_lumberjack_error_data())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("tab")
            await page.expect_state("tab", "axe")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_lumberjack_error_120x40",
                title="ACE axe lumberjack error",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py:101: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_lumberjack_error_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x012\xf3IDA...a\x00\x00\x00\x00\x00\xe0\xf8\xf3l\xef6\xde\xbb=\x9c\x81;\xdb&\xf8\'-X\x06\xf6$6\xc1\x85\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_lumberjack_error_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3295740626-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py'
test_line = 88
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_lumberjack_error_120x40.png
E       Changed pixels: 31171/1520532 (2.050006%); materially changed pixels: 31158/1520532 (2.049151%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_lumberjack_error_png_snapshot/axe_lumberjack_error_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_axe_chop_report_error_png_snapshot ____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...ots_axe_runs.py', test_line=175, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f083e4e31c0>

    async def test_axe_chop_report_error_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A check_error run surfaces reason and error in the RESULT card."""
        patch_startup_loaders(monkeypatch, axe_data=axe_chop_report_error_120x40())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            selected = await _select_first_chop(page)
            assert (selected.lumberjack_name, selected.chop_name) == (
                "reports",
                "recent_bug_audit",
            )
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_chop_report_error_120x40",
                title="ACE axe chop report error",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py:189: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_chop_report_error_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x00\xe6\xad...\x00\x00\x00\x00\x80\xe3\xb3\tg\x1d\xce"\xbe\xb8\xf3\xb2\x07~\x02T\xda|\xaf\xf5\x99y\xaa\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_chop_report_error_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3534565456-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py'
test_line = 175
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/axe_chop_report_error_120x40.png
E       Changed pixels: 33298/1520532 (2.189891%); materially changed pixels: 33295/1520532 (2.189694%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_runs.py__test_axe_chop_report_error_png_snapshot/axe_chop_report_error_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_artifact_links_panel_needs_reveal_row_png_snapshots[size0-artifact_links_panel_needs_reveal_row_120x40] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac..._links_panel.py', test_line=246, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2fcc72e40>
size = (120, 40), snapshot_name = 'artifact_links_panel_needs_reveal_row_120x40'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "artifact_links_panel_needs_reveal_row_120x40"),
            ((60, 30), "artifact_links_panel_needs_reveal_row_60x30"),
        ],
    )
    async def test_artifact_links_panel_needs_reveal_row_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
>       await _assert_panel_snapshot(
            ace_png_visual=ace_png_visual,
            monkeypatch=monkeypatch,
            size=size,
            snapshot_name=snapshot_name,
            title="ACE artifact links panel needs-reveal row",
            chips=_needs_reveal_chips(),
            wait_text="needs reveal",
            reveal_flags=frozenset({1}),
        )

tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:259: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:170: in _assert_panel_snapshot
    ace_png_visual.assert_page_png(page, snapshot_name, title=title)
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifact_links_panel_needs_reveal_row_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x028\x8dIDA...00\x00\x00\x00\xe0\xf63S\xff\\\xaf\x7f^\xca\xc4\x9d\xc3^\xf0\xff\x03RLu\x8f\xfb\xb6z\x1e\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size0-artifact_links_panel_needs_reveal_row_120x40]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3774766520-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py'
test_line = 246
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
>           raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
E           AssertionError: Missing ACE PNG snapshot golden: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/artifact_links_panel_needs_reveal_row_120x40.png
E           Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size0-artifact_links_panel_needs_reveal_row_120x40/artifact_links_panel_needs_reveal_row_120x40/actual.png
E           Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size0-artifact_links_panel_needs_reveal_row_120x40/artifact_links_panel_needs_reveal_row_120x40/summary.txt
E           Re-run with --sase-update-visual-snapshots to accept this snapshot intentionally.

tests/ace/tui/visual/png_diff.py:234: AssertionError
_ test_artifact_links_panel_needs_reveal_row_png_snapshots[size1-artifact_links_panel_needs_reveal_row_60x30] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac..._links_panel.py', test_line=246, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2fcc73e00>
size = (60, 30), snapshot_name = 'artifact_links_panel_needs_reveal_row_60x30'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "artifact_links_panel_needs_reveal_row_120x40"),
            ((60, 30), "artifact_links_panel_needs_reveal_row_60x30"),
        ],
    )
    async def test_artifact_links_panel_needs_reveal_row_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
>       await _assert_panel_snapshot(
            ace_png_visual=ace_png_visual,
            monkeypatch=monkeypatch,
            size=size,
            snapshot_name=snapshot_name,
            title="ACE artifact links panel needs-reveal row",
            chips=_needs_reveal_chips(),
            wait_text="needs reveal",
            reveal_flags=frozenset({1}),
        )

tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:259: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py:170: in _assert_panel_snapshot
    ace_png_visual.assert_page_png(page, snapshot_name, title=title)
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifact_links_panel_needs_reveal_row_60x30'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x02\xee\x00\x00\x03\x0e\x08\x06\x00\x00\x00A.\x83\xfc\x00\x01~WIDATx\x9c...x97\x18\x86a\x18\x86a\x18\x86\xd1.\xaeW_3\xd5\xd7\x04\x0bQc7\xfc\x06\x1b*?W\xd6\xe4:\xad\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size1-artifact_links_panel_needs_reveal_row_60x30]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 750 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...83.2" y="727.6" textLength="24.4" clip-path="url(#terminal-650478770-line-29)">ED</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py'
test_line = 246
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
>           raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
E           AssertionError: Missing ACE PNG snapshot golden: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/artifact_links_panel_needs_reveal_row_60x30.png
E           Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size1-artifact_links_panel_needs_reveal_row_60x30/artifact_links_panel_needs_reveal_row_60x30/actual.png
E           Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifact_links_panel.py__test_artifact_links_panel_needs_reveal_row_png_snapshots_size1-artifact_links_panel_needs_reveal_row_60x30/artifact_links_panel_needs_reveal_row_60x30/summary.txt
E           Re-run with --sase-update-visual-snapshots to accept this snapshot intentionally.

tests/ace/tui/visual/png_diff.py:234: AssertionError
____________ test_artifacts_agents_filter_parse_error_png_snapshot _____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ac...facts_agents.py', test_line=319, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2d7125240>

    async def test_artifacts_agents_filter_parse_error_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        snapshot = _snapshot(_populated_rows())
        _install_agents_fixture(monkeypatch, snapshot)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            pane = await _open_agents(page, snapshot)
            bar = pane.query_one(AgentFilterBar)
            await page.press("slash")
            await page.wait_for(lambda _state: bar._editing)  # noqa: SLF001
            bar.query_one("#agent-filter-input", SingleLineVimTextArea).load_text("status:")
            await page.wait_for(
                lambda _state: bar.query_one("#agent-filter-status").has_class("error")
            )
            status = bar.query_one("#agent-filter-status", Static)
            await page.wait_for(
                lambda _state: "Expected property value" in status.content.plain
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "artifacts_agents_filter_parse_error_120x40",
                title="ACE Artifacts - Agent filter parse error",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py:341: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_agents_filter_parse_error_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb1\xa3...x00\x00\x00\x80\xa9\xe7\xd9\xec\xa7\'\xfby,&\xeel\xb6\xc0\xff\x05\x87\x90\x94C\x13A"\xdb\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py::test_artifacts_agents_filter_parse_error_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1672637057-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py'
test_line = 319
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/tests/ace/tui/visual/snapshots/png/artifacts_agents_filter_parse_error_120x40.png
E       Changed pixels: 26951/1520532 (1.772472%); materially changed pixels: 26896/1520532 (1.768855%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_agents.py__test_artifacts_agents_filter_parse_error_png_snapshot/artifacts_agents_filter_parse_error_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
27.50s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
16.58s call     tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size0-link_reveal_chip_beads_120x40]
16.46s call     tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size1-link_reveal_chip_beads_60x30]
12.02s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_completion_panel_png_snapshot
11.58s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
11.55s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
11.42s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
10.70s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_insert_png_snapshot
9.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
9.74s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py::test_vcs_ref_completion_panel_placeholder_png_snapshot
9.73s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_skill_completion.py::test_prompt_skill_completion_long_description_png_snapshot
9.64s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_cell_edit_png_snapshot
9.62s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
9.61s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_highlight_png_snapshot
9.41s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_normal_png_snapshot
9.41s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_new_and_clean_png_snapshots[True-mini_xprompt_pane_clean_light_120x40-ACE mini-xprompt pane - clean light]
9.14s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_sase_plan_metadata_png_snapshot
9.13s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_zoom_context.py::test_agents_context_zoom_modal_png_snapshot
9.00s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_submit_choice_modal_png_snapshot
8.81s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_ordered_highlight_solo_png_snapshot[textual-dark-prompt_ordered_highlight_solo_dark_120x40-ACE prompt input \u2014 ordered-marker highlighting, dark theme]
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugin_actions.py::test_config_center_plugins_not_uv_tool_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_preview_panel.py::test_preview_panel_active_search_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size0-link_reveal_chip_beads_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_link_reveal_chip.py::test_beads_link_reveal_chip_png_snapshots[size1-link_reveal_chip_beads_60x30]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_section_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_models_panel_navigation.py::test_models_panel_builtin_selection_effort_step_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_task_bead_notes_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_pending_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_update_panel.py::test_update_panel_unchecked_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_lumberjack_tree_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe.py::test_axe_chop_overrun_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_descriptions.py::test_axe_lumberjack_description_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_long_label_widening_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_constrained_width_no_wrap_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_lumberjack_error_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_runs.py::test_axe_chop_report_error_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size0-artifact_links_panel_needs_reveal_row_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py::test_artifact_links_panel_needs_reveal_row_png_snapshots[size1-artifact_links_panel_needs_reveal_row_60x30]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_agents.py::test_artifacts_agents_filter_parse_error_png_snapshot
====== 29 failed, 826 passed, 1 skipped, 4 warnings in 599.29s (0:09:59) =======
error: recipe `test-visual` failed on line 453 with exit code 1

