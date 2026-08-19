# Chat History - ace-run (sase-qw.land--mon-0)

- **TIMESTAMP:** 2026-08-19 14:39:29 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-qw.land--mon-0

## Prompt

sase monitor start --command 'sh -c just check-full && just test-visual' --reason 'Re-run the pre-land gate for epic sase-qw; attempt 1 was killed by an external SIGTERM before pytest could name its 2 failures'

## Response

Available recipes:
    agent-disk-load-ops-check *args    # Run the Agents-tab disk-load operation-count regression floor.
    all                                # Fix code, run linters, and run tests.
    audit-patch-stitch-terminology
    bead-perf-smoke *args              # thresholds.
    bench-agent-launch *args           # ProjectSpec files so launch planning/spawn baselines do not start LLM CLIs.
    bench-agent-scan *args             # backend against.
    bench-core *args                   # rows have been removed.
    bench-git-query-ops *args          # parse cost to subprocess fork+exec cost.
    bench-plugin-catalog-scale *args   # sub-quadratic scan work, no silent 1000-result truncation).
    bench-query *args                  # against.
    bench-status-state-machine *args   # whether the status state machine is worth porting to Rust.
    build                              # Build wheel and sdist
    build-check                        # Build and verify package (CI mode)
    check                              # just finished writing to show what the run decided either way.
    check-full                         # suite. Run this before landing, and in CI.
    clean                              # Remove build artifacts
    default
    demos *args                        # Pass -y/--yes to skip the commit confirmation prompt.
    dev-shell                          # Activate venv in subshell
    docs-check                         # import the Python package and should not need the Rust core checkout.
    docs-deploy-artifact-check         # Verify the generated docs deploy artifact contains the normal site plus PDF.
    docs-pdf-check                     # the `docs-pdf` optional dependency group in pyproject.toml.
    fix                                # Auto-fix all code (format + keep-sorted)
    fix-keep-sorted                    # Auto-fix keep-sorted blocks in YAML files
    fmt                                # Auto-format all code
    fmt-check                          # Check all formatting (CI mode)
    fmt-docs                           # Render generated Markdown blocks
    fmt-md                             # Auto-format Markdown files
    fmt-md-check                       # Check Markdown formatting (CI mode)
    fmt-py                             # Auto-format Python code
    fmt-py-check                       # Check Python formatting (CI mode)
    install                            # distribution instead.
    install-terminal-smoke             # Install in editable mode with dev and real-terminal smoke-test dependencies.
    install-visual                     # Install in editable mode with dev and visual-test dependencies.
    launch-perf-check *args            # Run the Rust-backed agent-launch regression check against the Phase 1 baseline.
    lint                               # Run linters (ruff + mypy + feature flags + pyscripts + test waits + changelog + terminology audit + symvision + toobig + keep-sorted)
    lint-keep-sorted                   # Lint keep-sorted blocks in YAML files (CI mode)
    phase7-perf-check *args            # so CI can upload it on failure.
    plugin-catalog-scale-check *args   # Run the Updates > Plugins catalog-scale regression floor (sase-qn.5).
    pypi-smoke
    pypi-smoke-clean
    pypi-smoke-shell
    ratchet-core-window *args
    refresh-contexts-baseline *args    # static import closure when the cache is empty.
    refresh-contract-manifest          # `@pytest.mark.contract` from a test module.
    rust-bench *args                   # Run the Rust direct-parser benchmark (no Python in the loop).
    rust-check                         # Combined Rust check (fmt-check + clippy + tests). No-op when linked repo absent.
    rust-clippy                        # Run clippy with warnings-as-errors in ../sase-core.
    rust-dev-install VENV=venv_dir_abs # dev-update Cargo profile and target-isolated caches, then install both into a venv.
    rust-dev-install-uv-tool           # venv for `sase` (typically ~/.local/share/uv/tools/sase).
    rust-fmt                           # Auto-format Rust sources in ../sase-core.
    rust-fmt-check                     # Verify Rust sources are formatted (CI mode).
    rust-install VENV=venv_dir_abs     # `rust-install-uv-tool` for the uv-tool case.
    rust-install-uv-tool               # repo's `.venv` against a local sase-core checkout.
    rust-lsp-install VENV=venv_dir_abs # so `sase lsp` can prefer the update-managed server over stale PATH copies.
    rust-lsp-install-uv-tool           # (typically ~/.local/share/uv/tools/sase).
    rust-test                          # Run `cargo test --workspace` in ../sase-core.
    selection-backtest *args           # opt-in and must stay that way.
    selection-health *args             # numbers machine-readably.
    symvision *args                    # Find unused Python function/class definitions
    sync-completion-spec               # Rewrite the checked-in structural completion spec snapshot from the argparse tree.
    sync-feature-flags-schema          # Rewrite the generated feature_flags JSON Schema block from the registry.
    test *args                         # at module scope, and marker deselection happens after collection.
    test-ace-page-group-isolated       # timings or selection-health evidence.
    test-bead-store-soak *args         # bead store.
    test-contention *args              # SASE_CONTENTION_CPUS, SASE_CONTENTION_WORKERS, and SASE_CONTENTION_REPEAT.
    test-contexts *args                # `SASE_TEST_SELECTION_INSTALL_CONTEXTS=0` to record without caching.
    test-cost *args                    # lane; ordinary fast/cov/scoped runs keep the cheap timing recorder.
    test-cost-budget                   # Check the latest test-cost recording against committed suite-cost budgets.
    test-cov *args                     # the visual snapshot suite; still depends on `_setup-visual` for collection.
    test-py VER                        # Run tests for a specific Python version (e.g., just test-py 312)
    test-scoped *args                  # `_setup-visual`.
    test-slow *args                    # Run slow tests (excluded from the default `just test` run)
    test-terminal-smoke *args          # PTY, so keep it separate from the default and visual snapshot lanes.
    test-tox                           # Run tests across all Python versions
    test-visual *args                  # committed PNG snapshot goldens and a PNG rasterizer dependency.
    test-visual-contention *args       # SASE_VISUAL_CONTENTION_WORKERS.
    toobig *args                       # Check Python file line counts
    update-visual-snapshots            # Linux platform.
    validate                           # Validate SASE initialization and SDD prompt/plan frontmatter links.
    validate-committed-plans           # Validate committed plans with the month-based schema cutover policy.
    view-hints-perf-check *args        # Run the Agents-tab view-hints regression floor against the committed baseline.
    workflow-status *args              # Report the status of the last fully-completed GitHub Actions workflow set.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 3/3 workers
3 workers [730 items]

........................................................................ [  9%]
........................................................................ [ 19%]
........................................................................ [ 29%]
.......................................F..F............FFF.........F.... [ 39%]
.F......................................F..F.F.F.F.F....F.F..F.......... [ 49%]
.......................F................................................ [ 59%]
........................................................................ [ 69%]
...................................FF....F.................F..F......... [ 78%]
............................................................F..FF.F..... [ 88%]
...F..F.........................................F..FF.F.......F..F...... [ 98%]
....F.....                                                               [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________________ test_footer_leader_overflow_wide_png_snapshot _________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ng_snapshots.py', test_line=146, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff973f87890>

    async def test_footer_leader_overflow_wide_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """LEADER mode at 120x40: chips overflow into a deterministic grid."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("2")
            await page.expect_state("artifacts_subtab", "patches")
            await _render_leader_footer(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "footer_leader_overflow_120x40",
                title="ACE footer LEADER grid (wide)",
            )

tests/ace/tui/visual/test_ace_png_snapshots.py:159: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'footer_leader_overflow_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x9clIDA...0\x98|\xde\xf7\x1eQ\xef\xf1\xa6\x06\xee\x0c\x9b\xe0\xff\x07\x0c\xa7\x87\xd2\xc6\xda\xa7C\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots.py::test_footer_leader_overflow_wide_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...125289893-line-39)">update&#160;SASE&#160;+&#160;CLIs&#160;+&#160;hood&#160;cache</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots.py', test_line = 146
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/footer_leader_overflow_120x40.png
E       Changed pixels: 80002/1520532 (5.261448%); materially changed pixels: 79245/1520532 (5.211663%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_wide_png_snapshot/footer_leader_overflow_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_wide_png_snapshot/footer_leader_overflow_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_wide_png_snapshot/footer_leader_overflow_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_wide_png_snapshot/footer_leader_overflow_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_footer_leader_overflow_narrow_png_snapshot ________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ng_snapshots.py', test_line=166, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff9863cec50>

    async def test_footer_leader_overflow_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """LEADER mode at 80x30: narrower width drops more chips into more rows."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches(), size=(80, 30)) as page:
            await wait_for_startup(page)
            await page.press("2")
            await page.expect_state("artifacts_subtab", "patches")
            await _render_leader_footer(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "footer_leader_overflow_80x30",
                title="ACE footer LEADER grid (narrow)",
            )

tests/ace/tui/visual/test_ace_png_snapshots.py:179: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'footer_leader_overflow_80x30'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x03\xe2\x00\x00\x03\x0e\x08\x06\x00\x00\x00\x9a\x9c\xbc\xb2\x00\x01d\xf5...ba\xdd\x90\x08!\x84\x10B\x08!\x84\x10b.>I\xb7B\xba\x9d\'1[l\x87?\x02\xc3dt@\xb0\xa4P\xa4\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots.py::test_footer_leader_overflow_narrow_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 994 782.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...534742616-line-29)">update&#160;SASE&#160;+&#160;CLIs&#160;+&#160;hood&#160;cache</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots.py', test_line = 166
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/footer_leader_overflow_80x30.png
E       Changed pixels: 62155/777308 (7.996187%); materially changed pixels: 60937/777308 (7.839492%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_narrow_png_snapshot/footer_leader_overflow_80x30/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_narrow_png_snapshot/footer_leader_overflow_80x30/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_narrow_png_snapshot/footer_leader_overflow_80x30/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots.py__test_footer_leader_overflow_narrow_png_snapshot/footer_leader_overflow_80x30/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_axe_add_chooser_png_snapshot _______________________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_axe_editor.py', test_line=314, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc609666dd0>

    async def test_axe_add_chooser_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The AXE add chooser prioritizes a contextual chop under the parent."""
        _patch_axe_editor_visual_loaders(monkeypatch)
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.push_screen(AxeAddChooserModal("hooks.main"))
            await page.expect_modal("AxeAddChooserModal")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_add_chooser_120x40",
                title="ACE axe add chooser",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py:326: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_add_chooser_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01C%IDATx\...\x00\x00\x00\x00x\xf6,\x15\x97\xf9\xe2\xf2IL\xdc\xd9m\x81\xff\x0f"\x10&\xcc\xe8g\xf0\xea\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_add_chooser_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-394690857-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py'
test_line = 314
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/axe_add_chooser_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2684/1520532 (0.176517%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_add_chooser_png_snapshot/axe_add_chooser_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_add_chooser_png_snapshot/axe_add_chooser_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_add_chooser_png_snapshot/axe_add_chooser_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_add_chooser_png_snapshot/axe_add_chooser_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________________ test_axe_script_picker_png_snapshot ______________________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_axe_editor.py', test_line=333, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc6096666d0>

    async def test_axe_script_picker_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Discovered installed chop scripts show source and configured metadata."""
        _patch_axe_editor_visual_loaders(monkeypatch)
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.push_screen(AxeScriptPickerModal(_visual_chop_inventory()))
            await page.expect_modal("AxeScriptPickerModal")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_script_picker_120x40",
                title="ACE axe discovered script picker",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py:345: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_script_picker_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x95BIDA...x00\x00\x00\x00\x00\xb0\xf6\x8cT?\x17\xab\x9f\x17c\xe0\xcev\x13\xfc\xffm}z\x00\xcf\xf8JH\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_script_picker_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-2365071742-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py'
test_line = 333
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/axe_script_picker_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2684/1520532 (0.176517%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_script_picker_png_snapshot/axe_script_picker_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_script_picker_png_snapshot/axe_script_picker_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_script_picker_png_snapshot/axe_script_picker_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_script_picker_png_snapshot/axe_script_picker_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_axe_new_lumberjack_identity_png_snapshot _________________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_axe_editor.py', test_line=352, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc60863bc40>

    async def test_axe_new_lumberjack_identity_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The new-lumberjack identity form validates exact mapping keys."""
        _patch_axe_editor_visual_loaders(monkeypatch)
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.push_screen(
                AxeNewEntryIdentityModal(
                    kind="lumberjack",
                    initial_name="nightly.docs",
                    lumberjack_names=("hooks.main", "comments"),
                )
            )
            await page.expect_modal("AxeNewEntryIdentityModal")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_new_lumberjack_identity_120x40",
                title="ACE axe new lumberjack identity",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py:370: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_new_lumberjack_identity_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01#zIDATx\...\x00\x00\x00\x00\x008y\xf2\xc1e+\xb8\xdc\xd1\xc4\x9dQ\x0b\xfc?\xfc*\xf0\x8b\xb34\x04\x19\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_new_lumberjack_identity_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3231476056-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py'
test_line = 352
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/axe_new_lumberjack_identity_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2684/1520532 (0.176517%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_new_lumberjack_identity_png_snapshot/axe_new_lumberjack_identity_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_new_lumberjack_identity_png_snapshot/axe_new_lumberjack_identity_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_new_lumberjack_identity_png_snapshot/axe_new_lumberjack_identity_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_new_lumberjack_identity_png_snapshot/axe_new_lumberjack_identity_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_axe_editor_constrained_width_png_snapshot ________________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_axe_editor.py', test_line=491, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc609994c90>

    async def test_axe_editor_constrained_width_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The AXE editor collapses to the narrow layout on constrained terminals."""
        _patch_axe_editor_visual_loaders(monkeypatch)
        async with AcePage(query='"visual"', patches=patches(), size=(70, 36)) as page:
            await wait_for_startup(page)
            modal = await _push_visual_editor(page, _visual_new_lumberjack_seed())
            await wait_for_state(
                page,
                lambda: modal.has_class("-narrow"),
                description="AXE editor narrow layout",
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_editor_constrained_width_70x36",
                title="ACE axe editor constrained width",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py:507: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_editor_constrained_width_70x36'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x03h\x00\x00\x03\xa0\x08\x06\x00\x00\x00H\xadU\xe4\x00\x017gIDATx\x9c\xe...xfcx\xe5\x8f\xfe\xe8\x8f\xee\x8a\xfe\xd4\xef\xfb\xe2\xd3\xfc\xffa\xda\xdc\xb6\xf2}\x0c\\\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_editor_constrained_width_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 872 928.4" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich ...xtLength="109.8" clip-path="url(#terminal-571363303-line-35)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py'
test_line = 491
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/axe_editor_constrained_width_70x36.png
E       Changed pixels: 17075/809216 (2.110067%); materially changed pixels: 2685/809216 (0.331803%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_constrained_width_png_snapshot/axe_editor_constrained_width_70x36/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_constrained_width_png_snapshot/axe_editor_constrained_width_70x36/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_constrained_width_png_snapshot/axe_editor_constrained_width_70x36/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_constrained_width_png_snapshot/axe_editor_constrained_width_70x36/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________ test_axe_editor_compact_lumberjack_sheet_png_snapshot _____________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_axe_editor.py', test_line=571, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc60df17af0>

    async def test_axe_editor_compact_lumberjack_sheet_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A three-property lumberjack sheet shrinks to its content."""
        _patch_axe_editor_visual_loaders(monkeypatch)
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            seed = _visual_new_lumberjack_seed()
            seed = replace(seed, new_entry=False, initial_touched=())
            await _push_visual_editor(page, seed)
    
>           ace_png_visual.assert_page_png(
                page,
                "axe_editor_compact_lumberjack_sheet_120x40",
                title="ACE axe compact lumberjack property sheet",
            )

tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py:583: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'axe_editor_compact_lumberjack_sheet_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01v\x05IDA...8Q\x01\x00\x00\x00\x00\xc0\xd6s\xa1~\x9c\xa9\x1fG3qg\xdf\x02\xff?\xc6$\xfc\xab\x9aO|\xc3\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_editor_compact_lumberjack_sheet_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...extLength="109.8" clip-path="url(#terminal-66559749-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py'
test_line = 571
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/axe_editor_compact_lumberjack_sheet_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2684/1520532 (0.176517%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_compact_lumberjack_sheet_png_snapshot/axe_editor_compact_lumberjack_sheet_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_compact_lumberjack_sheet_png_snapshot/axe_editor_compact_lumberjack_sheet_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_compact_lumberjack_sheet_png_snapshot/axe_editor_compact_lumberjack_sheet_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_axe_editor.py__test_axe_editor_compact_lumberjack_sheet_png_snapshot/axe_editor_compact_lumberjack_sheet_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_glossary_panel_populated_png_snapshot[textual-dark-glossary_panel_populated_dark_120x40-ACE glossary panel - populated dark theme] _
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ossary_panel.py', test_line=207, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa31216b700>
theme = 'textual-dark', snapshot_name = 'glossary_panel_populated_dark_120x40'
title = 'ACE glossary panel - populated dark theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "glossary_panel_populated_dark_120x40",
                "ACE glossary panel - populated dark theme",
            ),
            (
                "textual-light",
                "glossary_panel_populated_light_120x40",
                "ACE glossary panel - populated light theme",
            ),
        ],
    )
    async def test_glossary_panel_populated_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        ref, snapshot = _populated_snapshot()
        _install_panel_load(monkeypatch, ref, snapshot)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.theme = theme
            page.app.push_screen(GlossaryPanel(initial_term="Agent Hood"))
            await page.expect_modal("GlossaryPanel")
            await wait_for_state(page, lambda: _panel_ready(page), description="panel load")
            await page.press("1")
            await wait_for_state(
                page,
                lambda: (
                    isinstance(page.app.screen, GlossaryPanel)
                    and page.app.screen._current_term == "Sase Agent"
                    and page.app.screen._trail == ["Agent Hood"]
                ),
                description="followed SEE ALSO to Sase Agent",
            )
            await wait_for_svg_contains(page, "TRAIL")
            await wait_for_svg_contains(page, "SEE ALSO")
            await wait_for_svg_contains(page, "REFERENCED BY")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py:254: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_panel_populated_dark_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01^\xf7IDA...00\x00\x80\xbd\xe7\xca\xca\xeb\xe2\xca\xeb\x81<\xb8\xb3o\x80\xff\x1f;\x8b\xc8\x9e{@\xc60\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_populated_png_snapshot[textual-dark-glossary_panel_populated_dark_120x40-ACE glossary panel - populated dark theme]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3243603496-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py'
test_line = 207
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_panel_populated_dark_120x40.png
E       Changed pixels: 300/1520532 (0.019730%); materially changed pixels: 90/1520532 (0.005919%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-dark-glossary_panel_populated_dark_120x40-ACE_glossary_panel_-_populated_dark_theme/glossary_panel_populated_dark_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-dark-glossary_panel_populated_dark_120x40-ACE_glossary_panel_-_populated_dark_theme/glossary_panel_populated_dark_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-dark-glossary_panel_populated_dark_120x40-ACE_glossary_panel_-_populated_dark_theme/glossary_panel_populated_dark_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-dark-glossary_panel_populated_dark_120x40-ACE_glossary_panel_-_populated_dark_theme/glossary_panel_populated_dark_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_glossary_panel_populated_png_snapshot[textual-light-glossary_panel_populated_light_120x40-ACE glossary panel - populated light theme] _
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ossary_panel.py', test_line=207, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa32b4be660>
theme = 'textual-light', snapshot_name = 'glossary_panel_populated_light_120x40'
title = 'ACE glossary panel - populated light theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "glossary_panel_populated_dark_120x40",
                "ACE glossary panel - populated dark theme",
            ),
            (
                "textual-light",
                "glossary_panel_populated_light_120x40",
                "ACE glossary panel - populated light theme",
            ),
        ],
    )
    async def test_glossary_panel_populated_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        ref, snapshot = _populated_snapshot()
        _install_panel_load(monkeypatch, ref, snapshot)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.theme = theme
            page.app.push_screen(GlossaryPanel(initial_term="Agent Hood"))
            await page.expect_modal("GlossaryPanel")
            await wait_for_state(page, lambda: _panel_ready(page), description="panel load")
            await page.press("1")
            await wait_for_state(
                page,
                lambda: (
                    isinstance(page.app.screen, GlossaryPanel)
                    and page.app.screen._current_term == "Sase Agent"
                    and page.app.screen._trail == ["Agent Hood"]
                ),
                description="followed SEE ALSO to Sase Agent",
            )
            await wait_for_svg_contains(page, "TRAIL")
            await wait_for_svg_contains(page, "SEE ALSO")
            await wait_for_svg_contains(page, "REFERENCED BY")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py:254: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_panel_populated_light_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01`\x16IDA...00\x00\x00\xb6\x9f\x87\x16~\x8e,\xfc\xdc\x91\x07wv\r\xf0\xff\x03\xab\xb3\xfaW\'\xe8_\xc9\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_populated_png_snapshot[textual-light-glossary_panel_populated_light_120x40-ACE glossary panel - populated light theme]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3811693817-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py'
test_line = 207
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_panel_populated_light_120x40.png
E       Changed pixels: 300/1520532 (0.019730%); materially changed pixels: 81/1520532 (0.005327%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-light-glossary_panel_populated_light_120x40-ACE_glossary_panel_-_populated_light_theme/glossary_panel_populated_light_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-light-glossary_panel_populated_light_120x40-ACE_glossary_panel_-_populated_light_theme/glossary_panel_populated_light_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-light-glossary_panel_populated_light_120x40-ACE_glossary_panel_-_populated_light_theme/glossary_panel_populated_light_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_populated_png_snapshot_textual-light-glossary_panel_populated_light_120x40-ACE_glossary_panel_-_populated_light_theme/glossary_panel_populated_light_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_glossary_panel_empty_png_snapshot[textual-dark-glossary_panel_empty_dark_120x40-ACE glossary panel - empty dark theme] _
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ossary_panel.py', test_line=257, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2fae21400>
theme = 'textual-dark', snapshot_name = 'glossary_panel_empty_dark_120x40'
title = 'ACE glossary panel - empty dark theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "glossary_panel_empty_dark_120x40",
                "ACE glossary panel - empty dark theme",
            ),
            (
                "textual-light",
                "glossary_panel_empty_light_120x40",
                "ACE glossary panel - empty light theme",
            ),
        ],
    )
    async def test_glossary_panel_empty_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        ref, snapshot = _empty_snapshot()
        _install_panel_load(monkeypatch, ref, snapshot)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.theme = theme
            page.app.push_screen(GlossaryPanel())
            await page.expect_modal("GlossaryPanel")
            await wait_for_state(page, lambda: _panel_ready(page), description="panel load")
            await wait_for_svg_contains(page, "No glossary in")
            await wait_for_svg_contains(page, "Research")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py:293: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_panel_empty_dark_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x00\xb9\xfa...9$\x00\x00\x00\x00\x008{\xc6\xd3\xcb\xde\xf4\xf2~>q\xe7q\x0f\xf8\xffd$\x17\xc7\x08\xa6J_\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_empty_png_snapshot[textual-dark-glossary_panel_empty_dark_120x40-ACE glossary panel - empty dark theme]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1334769366-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py'
test_line = 257
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_panel_empty_dark_120x40.png
E       Changed pixels: 300/1520532 (0.019730%); materially changed pixels: 90/1520532 (0.005919%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-dark-glossary_panel_empty_dark_120x40-ACE_glossary_panel_-_empty_dark_theme/glossary_panel_empty_dark_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-dark-glossary_panel_empty_dark_120x40-ACE_glossary_panel_-_empty_dark_theme/glossary_panel_empty_dark_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-dark-glossary_panel_empty_dark_120x40-ACE_glossary_panel_-_empty_dark_theme/glossary_panel_empty_dark_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-dark-glossary_panel_empty_dark_120x40-ACE_glossary_panel_-_empty_dark_theme/glossary_panel_empty_dark_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_glossary_panel_empty_png_snapshot[textual-light-glossary_panel_empty_light_120x40-ACE glossary panel - empty light theme] _
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ossary_panel.py', test_line=257, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa308e0aeb0>
theme = 'textual-light', snapshot_name = 'glossary_panel_empty_light_120x40'
title = 'ACE glossary panel - empty light theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "glossary_panel_empty_dark_120x40",
                "ACE glossary panel - empty dark theme",
            ),
            (
                "textual-light",
                "glossary_panel_empty_light_120x40",
                "ACE glossary panel - empty light theme",
            ),
        ],
    )
    async def test_glossary_panel_empty_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        ref, snapshot = _empty_snapshot()
        _install_panel_load(monkeypatch, ref, snapshot)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.theme = theme
            page.app.push_screen(GlossaryPanel())
            await page.expect_modal("GlossaryPanel")
            await wait_for_state(page, lambda: _panel_ready(page), description="panel load")
            await wait_for_svg_contains(page, "No glossary in")
            await wait_for_svg_contains(page, "Research")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py:293: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_panel_empty_light_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x00\xbb\tID...0\x00\x00\xe0\xe1\xb3?\xfe\xea\x8f\xbf\xae\xe5\x0f\xee\x9cu\x87\xff\x0f\xf1r(dj\xb6k\xf5\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_empty_png_snapshot[textual-light-glossary_panel_empty_light_120x40-ACE glossary panel - empty light theme]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-2228002063-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py'
test_line = 257
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_panel_empty_light_120x40.png
E       Changed pixels: 300/1520532 (0.019730%); materially changed pixels: 81/1520532 (0.005327%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-light-glossary_panel_empty_light_120x40-ACE_glossary_panel_-_empty_light_theme/glossary_panel_empty_light_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-light-glossary_panel_empty_light_120x40-ACE_glossary_panel_-_empty_light_theme/glossary_panel_empty_light_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-light-glossary_panel_empty_light_120x40-ACE_glossary_panel_-_empty_light_theme/glossary_panel_empty_light_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_panel.py__test_glossary_panel_empty_png_snapshot_textual-light-glossary_panel_empty_light_120x40-ACE_glossary_panel_-_empty_light_theme/glossary_panel_empty_light_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_glossary_preview_card_full_png_snapshot[textual-dark-glossary_preview_card_full_dark_120x40-ACE glossary preview card - full dark theme] _
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ssary_preview.py', test_line=33, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa31347ecf0>
theme = 'textual-dark', snapshot_name = 'glossary_preview_card_full_dark_120x40'
title = 'ACE glossary preview card - full dark theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "glossary_preview_card_full_dark_120x40",
                "ACE glossary preview card - full dark theme",
            ),
            (
                "textual-light",
                "glossary_preview_card_full_light_120x40",
                "ACE glossary preview card - full light theme",
            ),
        ],
    )
    async def test_glossary_preview_card_full_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        catalog = _visual_glossary_catalog(full=True)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.theme = theme
            page.app.push_screen(
                GlossaryPreviewModal(
                    catalog,
                    catalog.entries[0],
                    matched_text="hood",
                )
            )
            await page.expect_modal("GlossaryPreviewModal")
            await wait_for_svg_contains(page, "SEE ALSO")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_preview_card_full_dark_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x86\xda...01\x00\x00\x00\x00\xc0\xe6sn\xfevj\xfe\xf6h\x06\xee\xec5\xc1\xff\x0f\xcb.\x10V1K\xd9\xe6\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_glossary_preview_card_full_png_snapshot[textual-dark-glossary_preview_card_full_dark_120x40-ACE glossary preview card - full dark theme]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-4268752188-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py'
test_line = 33
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_preview_card_full_dark_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2680/1520532 (0.176254%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-dark-glossary_preview_card_full_dark_120x40-ACE_glossary_preview_card_-_full_dark_theme/glossary_preview_card_full_dark_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-dark-glossary_preview_card_full_dark_120x40-ACE_glossary_preview_card_-_full_dark_theme/glossary_preview_card_full_dark_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-dark-glossary_preview_card_full_dark_120x40-ACE_glossary_preview_card_-_full_dark_theme/glossary_preview_card_full_dark_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-dark-glossary_preview_card_full_dark_120x40-ACE_glossary_preview_card_-_full_dark_theme/glossary_preview_card_full_dark_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_glossary_preview_card_full_png_snapshot[textual-light-glossary_preview_card_full_light_120x40-ACE glossary preview card - full light theme] _
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ssary_preview.py', test_line=33, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa33af9bd90>
theme = 'textual-light'
snapshot_name = 'glossary_preview_card_full_light_120x40'
title = 'ACE glossary preview card - full light theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "glossary_preview_card_full_dark_120x40",
                "ACE glossary preview card - full dark theme",
            ),
            (
                "textual-light",
                "glossary_preview_card_full_light_120x40",
                "ACE glossary preview card - full light theme",
            ),
        ],
    )
    async def test_glossary_preview_card_full_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        catalog = _visual_glossary_catalog(full=True)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.theme = theme
            page.app.push_screen(
                GlossaryPreviewModal(
                    catalog,
                    catalog.entries[0],
                    matched_text="hood",
                )
            )
            await page.expect_modal("GlossaryPreviewModal")
            await wait_for_svg_contains(page, "SEE ALSO")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(page, snapshot_name, title=title)

tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_preview_card_full_light_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x887IDA...b{\x1cU\x00\x00\x00\x00\x00`\xf3yr\xee\xb1o\xeeqW:\xee\x1c4\xc0\xff\x0f\x84di`e=\xab\x10\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_glossary_preview_card_full_png_snapshot[textual-light-glossary_preview_card_full_light_120x40-ACE glossary preview card - full light theme]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1678367121-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py'
test_line = 33
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_preview_card_full_light_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2439/1520532 (0.160404%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-light-glossary_preview_card_full_light_120x40-ACE_glossary_preview_card_-_full_light_theme/glossary_preview_card_full_light_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-light-glossary_preview_card_full_light_120x40-ACE_glossary_preview_card_-_full_light_theme/glossary_preview_card_full_light_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-light-glossary_preview_card_full_light_120x40-ACE_glossary_preview_card_-_full_light_theme/glossary_preview_card_full_light_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_full_png_snapshot_textual-light-glossary_preview_card_full_light_120x40-ACE_glossary_preview_card_-_full_light_theme/glossary_preview_card_full_light_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_glossary_preview_card_minimal_png_snapshot ________________
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ssary_preview.py', test_line=75, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa311110360>

    async def test_glossary_preview_card_minimal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        catalog = _visual_glossary_catalog(full=False)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.push_screen(
                GlossaryPreviewModal(
                    catalog,
                    catalog.entries[0],
                    matched_text="Patch",
                )
            )
            await page.expect_modal("GlossaryPreviewModal")
            await wait_for_svg_contains(page, "Matches")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "glossary_preview_card_minimal_120x40",
                title="ACE glossary preview card - minimal entry",
            )

tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py:95: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'glossary_preview_card_minimal_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01;\x85IDA...xe3\t\x00\x00\x00\x00\x00\x9e=K\xc5e\xbe\xb8|\x12\x13wv[\xe0\xff\x03\x00_\xba-.e\xf9\x1c\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_glossary_preview_card_minimal_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3964285479-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py'
test_line = 75
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/glossary_preview_card_minimal_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2684/1520532 (0.176517%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_minimal_png_snapshot/glossary_preview_card_minimal_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_minimal_png_snapshot/glossary_preview_card_minimal_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_minimal_png_snapshot/glossary_preview_card_minimal_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_glossary_preview_card_minimal_png_snapshot/glossary_preview_card_minimal_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________________ test_repo_preview_card_png_snapshot ______________________
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...sary_preview.py', test_line=102, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2efd23540>

    async def test_repo_preview_card_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        catalog, mention = _visual_repo_mention_catalog()
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.push_screen(RepoPreviewModal(catalog, mention, matched_text=None))
            await page.expect_modal("RepoPreviewModal")
            await wait_for_svg_contains(page, "Checkout")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "repo_preview_card_120x40",
                title="ACE repo preview card",
            )

tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py:116: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'repo_preview_card_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xa2\xe5...x00\x00\x00\x00\x80\xb5\xe7p\xe7\xb1\xbf\xf3x \x1dw\xf6\x1a\xe0\xff\x03[\x0c&\xbez)*\x01\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_repo_preview_card_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1323694026-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py'
test_line = 102
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/repo_preview_card_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 2684/1520532 (0.176517%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_repo_preview_card_png_snapshot/repo_preview_card_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_repo_preview_card_png_snapshot/repo_preview_card_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_repo_preview_card_png_snapshot/repo_preview_card_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_glossary_preview.py__test_repo_preview_card_png_snapshot/repo_preview_card_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________________ test_help_panel_keymaps_png_snapshot _____________________
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ts_help_panel.py', test_line=31, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa2efd239a0>

    async def test_help_panel_keymaps_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The Help panel opens to the keymap reference first."""
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(
            query='"visual"',
            size=(120, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("2")
            await page.expect_state("artifacts_subtab", "patches")
            await page.expect_state("tab", "patches")
    
            page.app.push_screen(
                HelpModal(
                    current_tab="patches",
                    active_query=page.app.canonical_query_string,
                    registry=page.app._keymap_registry,
                )
            )
            await page.expect_modal("HelpModal")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "sase ace Help")
            assert_page_svg_contains(page, "Keymaps")
            assert_page_svg_contains(page, "Guide")
>           ace_png_visual.assert_page_png(
                page,
                # legacy compatibility retained PNG filename
                "help_keymaps_changespecs_120x40",
                title="ACE Help panel keymaps (PRs)",
            )

tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py:61: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'help_keymaps_changespecs_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02x\xd9IDA...\x00\x00\x00\x00\x00\xbd\xc7\xe1\xe43\x92|\xb6k\xe1\xce\xb4\x1d\xfe\x7fYr\xce#2\xcb\x86{\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py::test_help_panel_keymaps_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1351894298-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py'
test_line = 31
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/help_keymaps_changespecs_120x40.png
E       Changed pixels: 182/1520532 (0.011969%); materially changed pixels: 168/1520532 (0.011049%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...family_panel.py', test_line=361, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff98728d470>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_family_conversation_monit0')

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

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:397: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_conversation_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xe9\xbf...00\x00\x00\x00\x00\x00\xe6\x9f\xf3\xd1O&\xfa9\xad\x81;\x93^\xf0\xff\'\x1e0\xa4Dz\xb0\xc2\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_conversation_monitor_phase_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric... y="971.6" textLength="85.4" clip-path="url(#terminal-579084759-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py'
test_line = 361
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
E       Changed pixels: 94194/1520532 (6.194806%); materially changed pixels: 93852/1520532 (6.172313%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_notification_report_modal_png_snapshot __________________
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ation_report.py', test_line=199, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa325589400>

    async def test_notification_report_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        report = _resolved_report()
        patch_startup_loaders(monkeypatch, agents=[])
        _freeze_report_ages(monkeypatch)
    
        async with AcePage(
            query='"visual"',
            size=(120, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            page.app.push_screen(ReportModal(report))
            await page.expect_modal("ReportModal")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "Release readiness")
            assert_page_svg_contains(page, "live · updated 2m ago")
            assert_page_svg_contains(page, "base branch not green")
>           ace_png_visual.assert_page_png(
                page,
                "notification_report_modal_120x40",
                title="ACE full release report",
            )

tests/ace/tui/visual/test_ace_png_snapshots_notification_report.py:220: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'notification_report_modal_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xc5ZIDA...xec\x18I\x00\x00\x00\x00\x00\xe0\xea9\xcc\x8ezv\xd4b\xe3\xcen\x0b\xfe\x02+-J\x1e\xdbMD\r\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_notification_report.py::test_notification_report_modal_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-4100080351-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_notification_report.py'
test_line = 199
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/notification_report_modal_120x40.png
E       Changed pixels: 1225/1520532 (0.080564%); materially changed pixels: 396/1520532 (0.026044%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_notification_report.py__test_notification_report_modal_png_snapshot/notification_report_modal_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_notification_report.py__test_notification_report_modal_png_snapshot/notification_report_modal_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_notification_report.py__test_notification_report_modal_png_snapshot/notification_report_modal_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_notification_report.py__test_notification_report_modal_png_snapshot/notification_report_modal_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_______________ test_copy_as_stitches_selected_dark_png_snapshot _______________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...py_as_palette.py', test_line=82, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc606ecb850>

    async def test_copy_as_stitches_selected_dark_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        result = _patch_commits(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_commits_palette(page, result)
    
>           ace_png_visual.assert_page_png(
                page,
                "copy_as_stitches_selected_dark_120x40",
                title="ACE Copy as palette — selected commit, dark theme",
            )

tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py:92: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'copy_as_stitches_selected_dark_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x91\x15...xa1Ka\xc7\x00\xc9_\xf2\x1b\x1e\x00\x00\xf49\xb5j|\xdc\x99\x06\x0fo\xb9V+\x16\x0f\xf9\xdd\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py::test_copy_as_stitches_selected_dark_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1667020240-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py'
test_line = 82
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/copy_as_stitches_selected_dark_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 3667/1520532 (0.241166%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_stitches_selected_dark_png_snapshot/copy_as_stitches_selected_dark_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_stitches_selected_dark_png_snapshot/copy_as_stitches_selected_dark_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_stitches_selected_dark_png_snapshot/copy_as_stitches_selected_dark_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_stitches_selected_dark_png_snapshot/copy_as_stitches_selected_dark_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________ test_copy_as_over_artifact_files_modal_png_snapshot ______________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...y_as_palette.py', test_line=176, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc60b6b3620>

    async def test_copy_as_over_artifact_files_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        _patch_commits(monkeypatch)
        artifact_files = [
            ArtifactFile(
                id="explicit:111111111111111111111111",
                label="Copy as palette design",
                kind="markdown",
                path="/home/visual/.sase/artifacts/copy_as_palette.md",
                source_path="docs/copy_as_palette.md",
                workspace_dir="/home/visual/workspace",
                project="sase",
                explicit=True,
                sha256="a" * 64,
                size_bytes=4096,
                mime_type="text/markdown",
            ),
            ArtifactFile(
                id="explicit:222222222222222222222222",
                label="Palette preview",
                kind="image",
                path="/home/visual/.sase/artifacts/copy_as_palette.png",
                project="sase",
                explicit=True,
                sha256="b" * 64,
                size_bytes=24_576,
                mime_type="image/png",
            ),
        ]
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            page.app.push_screen(ArtifactFileSelectionModal(artifact_files))
            await page.expect_modal("ArtifactFileSelectionModal")
            await page.press("m", "m", "%")
            await page.expect_modal("CopyAsModal")
            await wait_for_svg_contains(page, "marked artifact files")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "copy_as_over_artifact_files_modal_dark_120x40",
                title="ACE Copy as palette — artifact file representations",
            )

tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py:218: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'copy_as_over_artifact_files_modal_dark_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02-\x14IDA...\x00\x00\x00\x00\x00\xbc<C{\xe9\xda\xcb7\x1a\xb8\xb3j\x82\xff\x06>\x91\xe3\x85\x9dx\x1a,\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py::test_copy_as_over_artifact_files_modal_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3761638166-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py'
test_line = 176
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/copy_as_over_artifact_files_modal_dark_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 3140/1520532 (0.206507%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_over_artifact_files_modal_png_snapshot/copy_as_over_artifact_files_modal_dark_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_over_artifact_files_modal_png_snapshot/copy_as_over_artifact_files_modal_dark_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_over_artifact_files_modal_png_snapshot/copy_as_over_artifact_files_modal_dark_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_copy_as_palette.py__test_copy_as_over_artifact_files_modal_png_snapshot/copy_as_over_artifact_files_modal_dark_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_epic_plan_toast_png_snapshot _______________________
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ts_plan_toast.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa3242188a0>

    async def test_epic_plan_toast_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The epic toast shows the Epic tier word and phase/wave/size counts."""
        patch_startup_loaders(monkeypatch)
        notification = _make(
            action="EpicApproval",
            action_data={
                "agent_name": "y4",
                "original_plan_file": "/plans/agent_group_clan_collapse.md",
                "plan_tier": "epic",
                "plan_phase_count": "7",
                "plan_wave_count": "3",
                "plan_phase_sizes": "xsmall=1,small=2,medium=3,large=1",
            },
        )
        message, severity = _format_notification_toast(notification)
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            notifications=True,
            startup_policy="real",
        ) as page:
            page.app.notify(message, severity=severity)
            await page.wait_for(lambda _s: _toast_is_mounted(page))
            page.app.screen.set_focus(None)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "plan_toast_epic_120x40",
                title="ACE epic plan approval toast",
            )

tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py:56: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'plan_toast_epic_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x1bPIDA...x00\x00\x8c?}\xc1\xc7\xa9\xe0\xe3\x15M\xdc\x19\xb7\xc0\xff\x03A\xa2\xca\xc7M\xef\x15\x80\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py::test_epic_plan_toast_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1631001271-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py'
test_line = 26
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/plan_toast_epic_120x40.png
E       Changed pixels: 18900/1520532 (1.242986%); materially changed pixels: 18836/1520532 (1.238777%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________________ test_tale_plan_toast_png_snapshot _______________________
[gw1] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ts_plan_toast.py', test_line=63, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa323e03c40>

    async def test_tale_plan_toast_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The tale toast shows the Tale tier word and no detail line."""
        patch_startup_loaders(monkeypatch)
        notification = _make(
            action="PlanApproval",
            action_data={
                "agent_name": "y4",
                "original_plan_file": "/plans/bead_wait_store_diagnostics.md",
                "plan_tier": "tale",
            },
        )
        message, severity = _format_notification_toast(notification)
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            notifications=True,
            startup_policy="real",
        ) as page:
            page.app.notify(message, severity=severity)
            await page.wait_for(lambda _s: _toast_is_mounted(page))
            page.app.screen.set_focus(None)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "plan_toast_tale_120x40",
                title="ACE tale plan approval toast",
            )

tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py:90: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'plan_toast_tale_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\n\xb6ID...02\x00\x00\x00\x00\x80\xc9\xe7h\xedr\xa4v\xd9\x1d\x03w\xb6Z\xe0\xff\x017i}\xbeEg\xde\x99\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py::test_tale_plan_toast_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-844753526-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py'
test_line = 63
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/plan_toast_tale_120x40.png
E       Changed pixels: 18300/1520532 (1.203526%); materially changed pixels: 18237/1520532 (1.199383%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_tale_plan_toast_png_snapshot/plan_toast_tale_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_tale_plan_toast_png_snapshot/plan_toast_tale_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_tale_plan_toast_png_snapshot/plan_toast_tale_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_tale_plan_toast_png_snapshot/plan_toast_tale_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_artifacts_beads_populated_png_snapshot __________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...tifacts_beads.py', test_line=30, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff989fc7a80>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_beads_populated0')

    async def test_artifacts_beads_populated_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        snapshot = replace(
            snapshot,
            plan_links={("alpha", "alpha-1"): "/workspace/alpha--plans/202608/beads.md"},
        )
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            assert pane.select_entry_target(
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "epic", "alpha-1"))
            )
            await page.press("l")
            await page.wait_for(
                lambda _state: (
                    not pane._epic_fold_registry.is_collapsed(("alpha", "alpha-1"))
                )
            )
            pane._update_detail()
            await wait_for_svg_contains(page, "Build bead browsing")
            await wait_for_visual_idle(page)
    
            for token in ("Tasks", "Epics", "awaiting triage", "-status:closed"):
>               assert_page_svg_contains(page, token)

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py:70: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7ff959ba8350>
text = '-status:closed'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = svg.replace("&#160;", " ")
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:40: AssertionError
__________ test_artifacts_beads_collapsed_relations_rail_png_snapshot __________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...tifacts_beads.py', test_line=79, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff984bd2890>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_beads_collapsed0')

    async def test_artifacts_beads_collapsed_relations_rail_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        snapshot = replace(
            snapshot,
            plan_links={("alpha", "alpha-1"): "/workspace/alpha--plans/202608/beads.md"},
        )
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            assert pane.select_entry_target(
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "epic", "alpha-1"))
            )
            pane.refresh_relation_panel()
            # alpha-1 is an epic: the rail reports children and plans, not a parent.
            # The relation panel starts collapsed by default, so no press is needed.
            await wait_for_svg_contains(page, "expand relations")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "artifacts_beads_collapsed_relations_120x40",
                title="ACE Artifacts - Beads collapsed relations",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py:114: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_beads_collapsed_relations_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02s\xaeIDA...00\x00\x00\xd0\xf9\xec\xf3~\x1a\xbd\x9f-\x1a\xb83l\x82\xff\x07\x0b.\x84\xd6\x81\x93O\xb7\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_collapsed_relations_rail_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-873159577-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py'
test_line = 79
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_beads_collapsed_relations_120x40.png
E       Changed pixels: 290700/1520532 (19.118309%); materially changed pixels: 289314/1520532 (19.027156%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads.py__test_artifacts_beads_collapsed_relations_rail_png_snapshot/artifacts_beads_collapsed_relations_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads.py__test_artifacts_beads_collapsed_relations_rail_png_snapshot/artifacts_beads_collapsed_relations_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads.py__test_artifacts_beads_collapsed_relations_rail_png_snapshot/artifacts_beads_collapsed_relations_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads.py__test_artifacts_beads_collapsed_relations_rail_png_snapshot/artifacts_beads_collapsed_relations_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
___________________ test_artifacts_beads_empty_png_snapshot ____________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_beads_empty.py', test_line=27, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff984d2da20>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_beads_empty_png0')

    async def test_artifacts_beads_empty_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = replace(
            _snapshot(tmp_path),
            tasks=(),
            epics=(),
            phases_by_epic={},
            ready_ids=frozenset(),
            blocked_ids=frozenset(),
            plan_links={},
            triage_gates={},
        )
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            pane._update_detail()
            detail = page.query_one_widget("#beads-detail", Markdown)
            await page.wait_for(lambda _state: "/sase_new_task" in detail.source)
            assert "TaskTriage" in detail.source
            await wait_for_svg_contains(page, "No beads yet")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "artifacts_beads_empty_120x40",
                title="ACE Artifacts - Beads empty",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_empty.py:65: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_beads_empty_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xa5\xa3...6mv\x02\x00\x00\x00\x00\x80\xdd\xcf\xd6\xc6ms\xe3vw\\\xb8\xb3\xd5\x04\xff?\xfd\xa59%XT]l\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_empty.py::test_artifacts_beads_empty_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3920774203-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_empty.py'
test_line = 27
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_beads_empty_120x40.png
E       Changed pixels: 214438/1520532 (14.102827%); materially changed pixels: 212837/1520532 (13.997535%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_empty.py__test_artifacts_beads_empty_png_snapshot/artifacts_beads_empty_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_empty.py__test_artifacts_beads_empty_png_snapshot/artifacts_beads_empty_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_empty.py__test_artifacts_beads_empty_png_snapshot/artifacts_beads_empty_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_empty.py__test_artifacts_beads_empty_png_snapshot/artifacts_beads_empty_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________ test_artifacts_beads_reopened_detail_png_snapshot _______________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...eads_reopened.py', test_line=30, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff956067700>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_beads_reopened_0')

    async def test_artifacts_beads_reopened_detail_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        snapshot = _snapshot(tmp_path)
        snapshot.tasks[1].issue.close_history.append(
            CloseRecord(
                closed_at="2026-07-30T09:12:04Z",
                reopened_at="2026-08-05T17:04:11Z",
                reopened_via=ReopenCause.PLUS_ONE,
                close_reason="Not reproducible on main; the retry shim already covers this.",
                resolution=Resolution.CANCELED,
                reopened_by="claude.probe",
            )
        )
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.artifacts.beads_pane.load_beads_snapshot",
            lambda _project, **_kwargs: snapshot,
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            assert pane.select_entry_target(
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "task", "alpha-open"))
            )
            pane._update_detail()
            await wait_for_svg_contains(page, "Previously Closed")
            await wait_for_visual_idle(page)
    
            for token in ("Previously closed", "↺1", "canceled"):
                assert_page_svg_contains(page, token)
    
>           ace_png_visual.assert_page_png(
                page,
                "artifacts_beads_reopened_detail_120x40",
                title="ACE Artifacts - Beads reopened detail",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_reopened.py:72: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_beads_reopened_detail_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x88_IDA...00\x00\x00\x00@\xff\xb39\xbauF\xb7\xd5\xea\xb83i\x80\xff\x1f\x0f\xf3\xc6\xc5\xaa\'\x08\n\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_reopened.py::test_artifacts_beads_reopened_detail_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-2480476035-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_reopened.py'
test_line = 30
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_beads_reopened_detail_120x40.png
E       Changed pixels: 399007/1520532 (26.241276%); materially changed pixels: 397593/1520532 (26.148282%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_reopened.py__test_artifacts_beads_reopened_detail_png_snapshot/artifacts_beads_reopened_detail_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_reopened.py__test_artifacts_beads_reopened_detail_png_snapshot/artifacts_beads_reopened_detail_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_reopened.py__test_artifacts_beads_reopened_detail_png_snapshot/artifacts_beads_reopened_detail_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_beads_reopened.py__test_artifacts_beads_reopened_detail_png_snapshot/artifacts_beads_reopened_detail_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_________________ test_artifacts_files_populated_png_snapshot __________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...ifacts_files.py', test_line=140, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff971cf3a80>

    async def test_artifacts_files_populated_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        rows = _fixture_rows()
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _all_choices,
        )
        monkeypatch.setattr(
            files_pane,
            "load_files_snapshot",
            lambda project, _limit: snapshot(rows, project=project),
        )
        monkeypatch.setattr(files_detail_panel, "load_file_detail", _fixture_detail)
        # No clock pin: Files no longer date-buckets rows. Default grouping is
        # by_source (Created / Captured banners), so files_options.local_now is gone.
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("files"), "(")
            await page.expect_state("artifacts_subtab", "files")
            pane = page.query_one_widget("#artifacts-files-pane", ArtifactsFilesPane)
            await page.wait_for(
                lambda _state: (
                    pane.snapshot is not None
                    and len(pane.snapshot.rows) == len(rows)
                    and pane.snapshot.rows[0].label == "release-notes artifact"
                )
            )
            await wait_for_svg_contains(page, "release-notes artifact")
>           await wait_for_svg_contains(page, "Source:")

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files.py:172: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_waits.py:55: in wait_for_svg_contains
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7ff9595af710>
predicate = <function wait_for_svg_contains.<locals>.<lambda> at 0x7ff9865b66c0>
description = "SVG sentinel 'Source:'", timeout = 15.0

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
E               AssertionError: Timed out after 15.00s waiting for SVG sentinel 'Source:'; last_frame_digest=c575064d7210; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-2202794891-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-2202794891-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-2202794891-r1 { fill: #c5c8c6 }\n.terminal-2202794891-r2 { fill: #fffcf0 }\n.terminal-2202794891-r3 { fill: #888888 }\n.terminal-2202794891-r4 { fill: #444444 }\n.terminal-2202794891-r5 { fill: #00d7af;font-weight: bold }\n.terminal-2202794891-r6 { fill: #05adad }\n.terminal-2202794891-r7 { fill: #adaba3 }\n.terminal-2202794891-r8 { fill: #ad5e05;font-weight: bold }\n.terminal-2202794891-r9 { fill: #ad9305;font-weight: bold }\n.terminal-2202794891-r10 { fill: #666666 }\n.terminal-2202794891-r11 { fill: #ffaf5f }\n.terminal-2202794891-r12 { fill: #ffaf5f;font-weight: bold }\n.terminal-2202794891-r13 { fill: #3a3a3a }\n.terminal-2202794891-r14 { fill: #adaba3;font-style: italic; }\n.terminal-2202794891-r15 { fill: #1a1a1a;font-weight: bold }\n.terminal-2202794891-r16 { fill: #b1afa7 }\n.terminal-2202794891-r17 { fill: #87d7ff;font-weight: bold }\n.terminal-2202794891-r18 { fill: #af87ff;font-weight: bold }\n.terminal-2202794891-r19 { fill: #d7af5f;font-weight: bold }\n.terminal-2202794891-r20 { fill: #afafaf;font-weight: bold }\n.terminal-2202794891-r21 { fill: #5fd7af;font-weight: bold }\n.terminal-2202794891-r22 { fill: #ffd700;font-weight: bold }\n.terminal-2202794891-r23 { fill: #5f5f87 }\n.terminal-2202794891-r24 { fill: #100f0f }\n.terminal-2202794891-r25 { fill: #ffaf5f;font-weight: bold;text-decoration: underline; }\n.terminal-2202794891-r26 { fill: #205ea6 }\n.terminal-2202794891-r27 { fill: #fffcf0;font-weight: bold }\n.terminal-2202794891-r28 { fill: #c4c5b5;font-weight: bold }\n.terminal-2202794891-r29 { fill: #5d5c5a }\n.terminal-2202794891-r30 { fill: #4b4b65 }\n.terminal-2202794891-r31 { fill: #797877 }\n.terminal-2202794891-r32 { fill: #beb3a8;font-weight: bold }\n.terminal-2202794891-r33 { fill: #b5b3aa }\n.terminal-2202794891-r34 { fill: #87d7ff }\n.terminal-2202794891-r35 { fill: #87afff;font-weight: bold }\n.terminal-2202794891-r36 { fill: #d7af5f }\n.terminal-2202794891-r37 { fill: #af87ff }\n.terminal-2202794891-r38 { fill: #afafaf }\n.terminal-2202794891-r39 { fill: #000000 }\n.terminal-2202794891-r40 { fill: #ffaf00;font-weight: bold }\n.terminal-2202794891-r41 { fill: #5fd75f;font-weight: bold }\n.terminal-2202794891-r42 { fill: #494846 }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-2202794891-clip-terminal">\n      <rect x="0" y="0" width="1463.0" height="975.0" />\n    </clipPath>\n    <clipPath id="terminal-2202794891-line-0">\n    <rect x="0" y="1.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-1">\n    <rect x="0" y="25.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-2">\n    <rect x="0" y="50.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-3">\n    <rect x="0" y="74.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-4">\n    <rect x="0" y="99.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-5">\n    <rect x="0" y="123.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-6">\n    <rect x="0" y="147.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-7">\n    <rect x="0" y="172.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-8">\n    <rect x="0" y="196.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-9">\n    <rect x="0" y="221.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-10">\n    <rect x="0" y="245.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-11">\n    <rect x="0" y="269.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-12">\n    <rect x="0" y="294.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-13">\n    <rect x="0" y="318.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-14">\n    <rect x="0" y="343.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-15">\n    <rect x="0" y="367.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-16">\n    <rect x="0" y="391.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-17">\n    <rect x="0" y="416.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-18">\n    <rect x="0" y="440.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-19">\n    <rect x="0" y="465.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-20">\n    <rect x="0" y="489.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-21">\n    <rect x="0" y="513.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-22">\n    <rect x="0" y="538.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-23">\n    <rect x="0" y="562.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-24">\n    <rect x="0" y="587.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-25">\n    <rect x="0" y="611.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-26">\n    <rect x="0" y="635.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-27">\n    <rect x="0" y="660.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-28">\n    <rect x="0" y="684.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-29">\n    <rect x="0" y="709.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-30">\n    <rect x="0" y="733.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-31">\n    <rect x="0" y="757.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-32">\n    <rect x="0" y="782.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-33">\n    <rect x="0" y="806.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-34">\n    <rect x="0" y="831.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-35">\n    <rect x="0" y="855.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-36">\n    <rect x="0" y="879.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-37">\n    <rect x="0" y="904.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2202794891-line-38">\n    <rect x="0" y="928.7" width="1464" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="1480" height="1024" rx="8"/><text class="terminal-2202794891-title" fill="#c5c8c6" text-anchor="middle" x="740" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-2202794891-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="97.6" y="1.5" width="512.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="610" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="817.4" y="1.5" width="524.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1342" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1354.2" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1354.2" y="1.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="25.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="25.9" width="622.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1000.4" y="25.9" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1366.4" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1378.6" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1403" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1415.2" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="329.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="366" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="561.2" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="719.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="732" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="841.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="890.6" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="963.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1037" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1049.2" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1122.4" y="50.3" width="256.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1378.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1390.8" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1439.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="74.7" width="1403" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1439.6" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="74.7" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="12.2" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="48.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="99.1" width="451.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="512.4" y="99.1" width="902.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1415.2" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1427.4" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1439.6" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="1403" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1439.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#ffaf5f" x="12.2" y="147.9" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="85.4" y="147.9" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="292.8" y="147.9" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="147.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="147.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="147.9" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="147.9" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="841.8" y="147.9" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1037" y="147.9" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1159" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1195.6" y="147.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1305.4" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1342" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1378.6" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="147.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="172.3" width="1439.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="196.7" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="196.7" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="221.1" width="280.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="221.1" width="414.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="221.1" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="221.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="245.5" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="707.6" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="245.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="245.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="245.5" width="549" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="245.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="269.9" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="269.9" width="463.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1232.2" y="269.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1268.8" y="269.9" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="294.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="158.6" y="294.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="207.4" y="294.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="305" y="294.3" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="294.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="294.3" width="414.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1183.4" y="294.3" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#674f35" x="36.6" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#674f35" x="48.8" y="318.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#674f35" x="146.4" y="318.7" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#674f35" x="292.8" y="318.7" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#674f35" x="536.8" y="318.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#674f35" x="561.2" y="318.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="318.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="318.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="318.7" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="318.7" width="658.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="318.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="61" y="343.1" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="170.8" y="343.1" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="219.6" y="343.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="317.2" y="343.1" width="353.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="343.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="343.1" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="817.4" y="343.1" width="610" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="48.8" y="367.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="367.5" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="292.8" y="367.5" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="561.2" y="367.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="367.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="367.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="854" y="367.5" width="268.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1122.4" y="367.5" width="305" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="48.8" y="391.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="391.9" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="292.8" y="391.9" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="561.2" y="391.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="391.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="391.9" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="841.8" y="391.9" width="231.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1073.6" y="391.9" width="353.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="48.8" y="416.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="416.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="292.8" y="416.3" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="561.2" y="416.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="416.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="416.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="416.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="915" y="416.3" width="512.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="48.8" y="440.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="146.4" y="440.7" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="292.8" y="440.7" width="244" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="536.8" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="561.2" y="440.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="440.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="440.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="902.8" y="440.7" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1061.4" y="440.7" width="366" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="465.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="465.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="465.1" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="841.8" y="465.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="927.2" y="465.1" width="500.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="489.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="489.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="489.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="489.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="489.5" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1037" y="489.5" width="390.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="489.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="513.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="513.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="513.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="513.9" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="513.9" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1073.6" y="513.9" width="353.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="513.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="538.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="538.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="538.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="538.3" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="538.3" width="658.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="538.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="562.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="562.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="562.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="562.7" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="841.8" y="562.7" width="585.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="562.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="587.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="587.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="587.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="587.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="854" y="587.1" width="573.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="587.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="611.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="611.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="611.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="611.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="611.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="939.4" y="611.5" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="611.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="635.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="635.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="635.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="635.9" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="890.6" y="635.9" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="939.4" y="635.9" width="488" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="635.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="660.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="660.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="660.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="660.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="854" y="660.3" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1012.6" y="660.3" width="414.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="660.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="684.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="684.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="684.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="684.7" width="183" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="951.6" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="963.8" y="684.7" width="463.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#0c2542" x="1427.4" y="684.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="709.1" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="709.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="709.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="709.1" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="927.2" y="709.1" width="500.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="709.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="733.5" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="733.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="733.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="733.5" width="549" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1317.6" y="733.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="733.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="757.9" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="757.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="757.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="757.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="866.2" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="757.9" width="549" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="757.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="782.3" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="782.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="782.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="782.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="878.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="890.6" y="782.3" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="782.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="36.6" y="806.7" width="634.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="671" y="806.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="806.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="806.7" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="806.7" width="658.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="806.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#205ea6" x="12.2" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#272624" x="24.4" y="831.1" width="683.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="707.6" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="831.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="831.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="829.6" y="831.1" width="597.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="831.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#ffaf5f" x="24.4" y="855.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="85.4" y="855.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="170.8" y="855.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="231.8" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="855.5" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="378.2" y="855.5" width="341.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="719.8" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="744.2" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="768.6" y="855.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="866.2" y="855.5" width="414.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1281" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1354.2" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#000000" x="1427.4" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="855.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="0" y="879.9" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="732" y="879.9" width="732" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="73.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="134.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="329.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="390.4" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="451.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="463.6" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="610" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="904.3" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="915" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="976" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="904.3" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1146.8" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1207.8" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1220" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1293.2" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1354.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1366.4" y="904.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="928.7" width="1464" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="953.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="231.8" y="953.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="292.8" y="953.1" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="390.4" y="953.1" width="890.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="1281" y="953.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="1342" y="953.1" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-2202794891-matrix">\n    <text class="terminal-2202794891-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-2202794891-line-0)">⭘</text><text class="terminal-2202794891-r2" x="610" y="20" textLength="207.4" clip-path="url(#terminal-2202794891-line-0)">sase&#160;ace&#160;(v0.7.1)</text><text class="terminal-2202794891-r1" x="1464" y="20" textLength="12.2" clip-path="url(#terminal-2202794891-line-0)">\n</text><text class="terminal-2202794891-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-2202794891-line-1)">&#160;Agents&#160;</text><text class="terminal-2202794891-r4" x="109.8" y="44.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-1)">&#160;│&#160;</text><text class="terminal-2202794891-r5" x="146.4" y="44.4" textLength="134.2" clip-path="url(#terminal-2202794891-line-1)">&#160;Artifacts&#160;</text><text class="terminal-2202794891-r4" x="280.6" y="44.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-1)">&#160;│&#160;</text><text class="terminal-2202794891-r3" x="317.2" y="44.4" textLength="61" clip-path="url(#terminal-2202794891-line-1)">&#160;AXE&#160;</text><text class="terminal-2202794891-r6" x="1000.4" y="44.4" textLength="366" clip-path="url(#terminal-2202794891-line-1)">&#160;CODEX(visual-snapshot-model)&#160;</text><text class="terminal-2202794891-r8" x="1378.6" y="44.4" textLength="24.4" clip-path="url(#terminal-2202794891-line-1)">⚑1</text><text class="terminal-2202794891-r9" x="1415.2" y="44.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-1)">✉18</text><text class="terminal-2202794891-r1" x="1464" y="44.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-1)">\n</text><text class="terminal-2202794891-r10" x="329.4" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;1&#160;</text><text class="terminal-2202794891-r10" x="366" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">◉</text><text class="terminal-2202794891-r3" x="378.2" y="68.8" textLength="97.6" clip-path="url(#terminal-2202794891-line-2)">&#160;Stitch&#160;</text><text class="terminal-2202794891-r4" x="475.8" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;│&#160;</text><text class="terminal-2202794891-r10" x="512.4" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;2&#160;</text><text class="terminal-2202794891-r10" x="549" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">⎇</text><text class="terminal-2202794891-r3" x="561.2" y="68.8" textLength="85.4" clip-path="url(#terminal-2202794891-line-2)">&#160;Patch&#160;</text><text class="terminal-2202794891-r4" x="646.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;│&#160;</text><text class="terminal-2202794891-r10" x="683.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;3&#160;</text><text class="terminal-2202794891-r10" x="719.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">◈</text><text class="terminal-2202794891-r3" x="732" y="68.8" textLength="73.2" clip-path="url(#terminal-2202794891-line-2)">&#160;Bead&#160;</text><text class="terminal-2202794891-r4" x="805.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;│&#160;</text><text class="terminal-2202794891-r10" x="841.8" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;4&#160;</text><text class="terminal-2202794891-r10" x="878.4" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">✎</text><text class="terminal-2202794891-r3" x="890.6" y="68.8" textLength="73.2" clip-path="url(#terminal-2202794891-line-2)">&#160;Plan&#160;</text><text class="terminal-2202794891-r4" x="963.8" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;│&#160;</text><text class="terminal-2202794891-r11" x="1000.4" y="68.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-2)">&#160;5&#160;</text><text class="terminal-2202794891-r11" x="1037" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">▤</text><text class="terminal-2202794891-r12" x="1049.2" y="68.8" textLength="73.2" clip-path="url(#terminal-2202794891-line-2)">&#160;FILE&#160;</text><text class="terminal-2202794891-r10" x="1378.6" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">{</text><text class="terminal-2202794891-r11" x="1390.8" y="68.8" textLength="24.4" clip-path="url(#terminal-2202794891-line-2)">██</text><text class="terminal-2202794891-r13" x="1415.2" y="68.8" textLength="24.4" clip-path="url(#terminal-2202794891-line-2)">██</text><text class="terminal-2202794891-r10" x="1439.6" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">}</text><text class="terminal-2202794891-r1" x="1464" y="68.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-2)">\n</text><text class="terminal-2202794891-r11" x="36.6" y="93.2" textLength="1403" clip-path="url(#terminal-2202794891-line-3)">┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐</text><text class="terminal-2202794891-r1" x="1464" y="93.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-3)">\n</text><text class="terminal-2202794891-r12" x="12.2" y="117.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-4)">/</text><text class="terminal-2202794891-r11" x="36.6" y="117.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-4)">│</text><text class="terminal-2202794891-r14" x="61" y="117.6" textLength="451.4" clip-path="url(#terminal-2202794891-line-4)">label,&#160;stored&#160;path,&#160;source&#160;path&#160;(AND)</text><text class="terminal-2202794891-r11" x="1427.4" y="117.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-4)">│</text><text class="terminal-2202794891-r1" x="1464" y="117.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-4)">\n</text><text class="terminal-2202794891-r11" x="36.6" y="142" textLength="1403" clip-path="url(#terminal-2202794891-line-5)">└─────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘</text><text class="terminal-2202794891-r1" x="1464" y="142" textLength="12.2" clip-path="url(#terminal-2202794891-line-5)">\n</text><text class="terminal-2202794891-r15" x="12.2" y="166.4" textLength="73.2" clip-path="url(#terminal-2202794891-line-6)">&#160;File&#160;</text><text class="terminal-2202794891-r16" x="85.4" y="166.4" textLength="207.4" clip-path="url(#terminal-2202794891-line-6)">&#160;&#160;Project&#160;scope&#160;&#160;</text><text class="terminal-2202794891-r12" x="292.8" y="166.4" textLength="170.8" clip-path="url(#terminal-2202794891-line-6)">&#160;All&#160;projects&#160;</text><text class="terminal-2202794891-r16" x="463.6" y="166.4" textLength="61" clip-path="url(#terminal-2202794891-line-6)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r16" x="524.6" y="166.4" textLength="97.6" clip-path="url(#terminal-2202794891-line-6)">p&#160;change</text><text class="terminal-2202794891-r16" x="622.2" y="166.4" textLength="61" clip-path="url(#terminal-2202794891-line-6)">&#160;&#160;│&#160;&#160;</text><text class="terminal-2202794891-r17" x="683.2" y="166.4" textLength="122" clip-path="url(#terminal-2202794891-line-6)">▨&#160;1&#160;images</text><text class="terminal-2202794891-r16" x="805.2" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">&#160;·&#160;</text><text class="terminal-2202794891-r18" x="841.8" y="166.4" textLength="158.6" clip-path="url(#terminal-2202794891-line-6)">▤&#160;2&#160;documents</text><text class="terminal-2202794891-r16" x="1000.4" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">&#160;·&#160;</text><text class="terminal-2202794891-r19" x="1037" y="166.4" textLength="122" clip-path="url(#terminal-2202794891-line-6)">▶&#160;1&#160;videos</text><text class="terminal-2202794891-r16" x="1159" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">&#160;·&#160;</text><text class="terminal-2202794891-r20" x="1195.6" y="166.4" textLength="109.8" clip-path="url(#terminal-2202794891-line-6)">•&#160;1&#160;files</text><text class="terminal-2202794891-r16" x="1305.4" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">&#160;·&#160;</text><text class="terminal-2202794891-r21" x="1342" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">R&#160;0</text><text class="terminal-2202794891-r16" x="1378.6" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">&#160;·&#160;</text><text class="terminal-2202794891-r22" x="1415.2" y="166.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-6)">C&#160;…</text><text class="terminal-2202794891-r1" x="1464" y="166.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-6)">\n</text><text class="terminal-2202794891-r1" x="1464" y="190.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-7)">\n</text><text class="terminal-2202794891-r11" x="0" y="215.2" textLength="732" clip-path="url(#terminal-2202794891-line-8)">╭─&#160;Files&#160;──────────────────────────────────────────────────╮</text><text class="terminal-2202794891-r23" x="732" y="215.2" textLength="732" clip-path="url(#terminal-2202794891-line-8)">╭─&#160;Details&#160;────────────────────────────────────────────────╮</text><text class="terminal-2202794891-r1" x="1464" y="215.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-8)">\n</text><text class="terminal-2202794891-r11" x="0" y="239.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-9)">│</text><text class="terminal-2202794891-r16" x="24.4" y="239.6" textLength="280.6" clip-path="url(#terminal-2202794891-line-9)">5&#160;artifact&#160;files&#160;loaded</text><text class="terminal-2202794891-r11" x="719.8" y="239.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-9)">│</text><text class="terminal-2202794891-r23" x="732" y="239.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-9)">│</text><text class="terminal-2202794891-r23" x="1451.8" y="239.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-9)">│</text><text class="terminal-2202794891-r1" x="1464" y="239.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-9)">\n</text><text class="terminal-2202794891-r11" x="0" y="264" textLength="12.2" clip-path="url(#terminal-2202794891-line-10)">│</text><text class="terminal-2202794891-r11" x="719.8" y="264" textLength="12.2" clip-path="url(#terminal-2202794891-line-10)">│</text><text class="terminal-2202794891-r23" x="732" y="264" textLength="12.2" clip-path="url(#terminal-2202794891-line-10)">│</text><text class="terminal-2202794891-r25" x="768.6" y="264" textLength="109.8" clip-path="url(#terminal-2202794891-line-10)">REFERENCE</text><text class="terminal-2202794891-r23" x="1451.8" y="264" textLength="12.2" clip-path="url(#terminal-2202794891-line-10)">│</text><text class="terminal-2202794891-r1" x="1464" y="264" textLength="12.2" clip-path="url(#terminal-2202794891-line-10)">\n</text><text class="terminal-2202794891-r11" x="0" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">│</text><text class="terminal-2202794891-r24" x="12.2" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">▊</text><text class="terminal-2202794891-r26" x="24.4" y="288.4" textLength="683.2" clip-path="url(#terminal-2202794891-line-11)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-2202794891-r26" x="707.6" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">│</text><text class="terminal-2202794891-r23" x="732" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">│</text><text class="terminal-2202794891-r27" x="768.6" y="288.4" textLength="463.6" clip-path="url(#terminal-2202794891-line-11)">file:explicit:1a2b3c4d5e6f708192a3b4c5</text><text class="terminal-2202794891-r7" x="1232.2" y="288.4" textLength="36.6" clip-path="url(#terminal-2202794891-line-11)">&#160;&#160;→</text><text class="terminal-2202794891-r23" x="1451.8" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">│</text><text class="terminal-2202794891-r1" x="1464" y="288.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-11)">\n</text><text class="terminal-2202794891-r11" x="0" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">│</text><text class="terminal-2202794891-r24" x="12.2" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">▊</text><text class="terminal-2202794891-r12" x="36.6" y="312.8" textLength="24.4" clip-path="url(#terminal-2202794891-line-12)">▾&#160;</text><text class="terminal-2202794891-r28" x="61" y="312.8" textLength="97.6" clip-path="url(#terminal-2202794891-line-12)">Created&#160;</text><text class="terminal-2202794891-r29" x="158.6" y="312.8" textLength="48.8" clip-path="url(#terminal-2202794891-line-12)">(1)&#160;</text><text class="terminal-2202794891-r30" x="207.4" y="312.8" textLength="97.6" clip-path="url(#terminal-2202794891-line-12)">────────</text><text class="terminal-2202794891-r26" x="707.6" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">│</text><text class="terminal-2202794891-r23" x="732" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">│</text><text class="terminal-2202794891-r7" x="768.6" y="312.8" textLength="414.8" clip-path="url(#terminal-2202794891-line-12)">/visual/artifacts/release_notes.md</text><text class="terminal-2202794891-r23" x="1451.8" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">│</text><text class="terminal-2202794891-r1" x="1464" y="312.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-12)">\n</text><text class="terminal-2202794891-r11" x="0" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">│</text><text class="terminal-2202794891-r24" x="12.2" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">▊</text><text class="terminal-2202794891-r18" x="36.6" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">▤</text><text class="terminal-2202794891-r32" x="48.8" y="337.2" textLength="97.6" clip-path="url(#terminal-2202794891-line-13)">&#160;16:05&#160;&#160;</text><text class="terminal-2202794891-r17" x="146.4" y="337.2" textLength="146.4" clip-path="url(#terminal-2202794891-line-13)">[Alpha]&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r28" x="292.8" y="337.2" textLength="244" clip-path="url(#terminal-2202794891-line-13)">alpha.1--code&#160;&#160;&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r22" x="536.8" y="337.2" textLength="24.4" clip-path="url(#terminal-2202794891-line-13)">C&#160;</text><text class="terminal-2202794891-r18" x="561.2" y="337.2" textLength="109.8" clip-path="url(#terminal-2202794891-line-13)">release-…</text><text class="terminal-2202794891-r26" x="707.6" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">│</text><text class="terminal-2202794891-r23" x="732" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">│</text><text class="terminal-2202794891-r23" x="1451.8" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">│</text><text class="terminal-2202794891-r1" x="1464" y="337.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-13)">\n</text><text class="terminal-2202794891-r11" x="0" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">│</text><text class="terminal-2202794891-r24" x="12.2" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">▊</text><text class="terminal-2202794891-r12" x="36.6" y="361.6" textLength="24.4" clip-path="url(#terminal-2202794891-line-14)">▾&#160;</text><text class="terminal-2202794891-r28" x="61" y="361.6" textLength="109.8" clip-path="url(#terminal-2202794891-line-14)">Captured&#160;</text><text class="terminal-2202794891-r29" x="170.8" y="361.6" textLength="48.8" clip-path="url(#terminal-2202794891-line-14)">(4)&#160;</text><text class="terminal-2202794891-r30" x="219.6" y="361.6" textLength="97.6" clip-path="url(#terminal-2202794891-line-14)">────────</text><text class="terminal-2202794891-r26" x="707.6" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">│</text><text class="terminal-2202794891-r23" x="732" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">│</text><text class="terminal-2202794891-r25" x="768.6" y="361.6" textLength="48.8" clip-path="url(#terminal-2202794891-line-14)">FILE</text><text class="terminal-2202794891-r23" x="1451.8" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">│</text><text class="terminal-2202794891-r1" x="1464" y="361.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-14)">\n</text><text class="terminal-2202794891-r11" x="0" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">│</text><text class="terminal-2202794891-r24" x="12.2" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">▊</text><text class="terminal-2202794891-r17" x="36.6" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">▨</text><text class="terminal-2202794891-r33" x="48.8" y="386" textLength="97.6" clip-path="url(#terminal-2202794891-line-15)">&#160;15:40&#160;&#160;</text><text class="terminal-2202794891-r17" x="146.4" y="386" textLength="146.4" clip-path="url(#terminal-2202794891-line-15)">[Alpha]&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r28" x="292.8" y="386" textLength="244" clip-path="url(#terminal-2202794891-line-15)">alpha.2--research&#160;&#160;&#160;</text><text class="terminal-2202794891-r12" x="536.8" y="386" textLength="24.4" clip-path="url(#terminal-2202794891-line-15)">A&#160;</text><text class="terminal-2202794891-r34" x="561.2" y="386" textLength="109.8" clip-path="url(#terminal-2202794891-line-15)">architec…</text><text class="terminal-2202794891-r26" x="707.6" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">│</text><text class="terminal-2202794891-r23" x="732" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">│</text><text class="terminal-2202794891-r35" x="768.6" y="386" textLength="85.4" clip-path="url(#terminal-2202794891-line-15)">Label:&#160;</text><text class="terminal-2202794891-r2" x="854" y="386" textLength="268.4" clip-path="url(#terminal-2202794891-line-15)">release-notes&#160;artifact</text><text class="terminal-2202794891-r23" x="1451.8" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">│</text><text class="terminal-2202794891-r1" x="1464" y="386" textLength="12.2" clip-path="url(#terminal-2202794891-line-15)">\n</text><text class="terminal-2202794891-r11" x="0" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">│</text><text class="terminal-2202794891-r24" x="12.2" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">▊</text><text class="terminal-2202794891-r19" x="36.6" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">▶</text><text class="terminal-2202794891-r33" x="48.8" y="410.4" textLength="97.6" clip-path="url(#terminal-2202794891-line-16)">&#160;14:20&#160;&#160;</text><text class="terminal-2202794891-r17" x="146.4" y="410.4" textLength="146.4" clip-path="url(#terminal-2202794891-line-16)">[Beta]&#160;&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r28" x="292.8" y="410.4" textLength="244" clip-path="url(#terminal-2202794891-line-16)">beta.1--demo&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r12" x="536.8" y="410.4" textLength="24.4" clip-path="url(#terminal-2202794891-line-16)">A&#160;</text><text class="terminal-2202794891-r36" x="561.2" y="410.4" textLength="109.8" clip-path="url(#terminal-2202794891-line-16)">walkthro…</text><text class="terminal-2202794891-r26" x="707.6" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">│</text><text class="terminal-2202794891-r23" x="732" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">│</text><text class="terminal-2202794891-r35" x="768.6" y="410.4" textLength="73.2" clip-path="url(#terminal-2202794891-line-16)">Kind:&#160;</text><text class="terminal-2202794891-r2" x="841.8" y="410.4" textLength="231.8" clip-path="url(#terminal-2202794891-line-16)">markdown&#160;·&#160;markdown</text><text class="terminal-2202794891-r23" x="1451.8" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">│</text><text class="terminal-2202794891-r1" x="1464" y="410.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-16)">\n</text><text class="terminal-2202794891-r11" x="0" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">│</text><text class="terminal-2202794891-r24" x="12.2" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">▊</text><text class="terminal-2202794891-r18" x="36.6" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">▤</text><text class="terminal-2202794891-r33" x="48.8" y="434.8" textLength="97.6" clip-path="url(#terminal-2202794891-line-17)">&#160;13:05&#160;&#160;</text><text class="terminal-2202794891-r17" x="146.4" y="434.8" textLength="146.4" clip-path="url(#terminal-2202794891-line-17)">[Beta]&#160;&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r28" x="292.8" y="434.8" textLength="244" clip-path="url(#terminal-2202794891-line-17)">beta.2--review&#160;&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r12" x="536.8" y="434.8" textLength="24.4" clip-path="url(#terminal-2202794891-line-17)">A&#160;</text><text class="terminal-2202794891-r37" x="561.2" y="434.8" textLength="109.8" clip-path="url(#terminal-2202794891-line-17)">design-r…</text><text class="terminal-2202794891-r26" x="707.6" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">│</text><text class="terminal-2202794891-r23" x="732" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">│</text><text class="terminal-2202794891-r35" x="768.6" y="434.8" textLength="109.8" clip-path="url(#terminal-2202794891-line-17)">Version:&#160;</text><text class="terminal-2202794891-r2" x="878.4" y="434.8" textLength="36.6" clip-path="url(#terminal-2202794891-line-17)">1/1</text><text class="terminal-2202794891-r23" x="1451.8" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">│</text><text class="terminal-2202794891-r1" x="1464" y="434.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-17)">\n</text><text class="terminal-2202794891-r11" x="0" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">│</text><text class="terminal-2202794891-r24" x="12.2" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">▊</text><text class="terminal-2202794891-r20" x="36.6" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">•</text><text class="terminal-2202794891-r33" x="48.8" y="459.2" textLength="97.6" clip-path="url(#terminal-2202794891-line-18)">&#160;18:30&#160;&#160;</text><text class="terminal-2202794891-r17" x="146.4" y="459.2" textLength="146.4" clip-path="url(#terminal-2202794891-line-18)">[Alpha]&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r28" x="292.8" y="459.2" textLength="244" clip-path="url(#terminal-2202794891-line-18)">alpha.3--lint&#160;&#160;&#160;&#160;&#160;&#160;&#160;</text><text class="terminal-2202794891-r12" x="536.8" y="459.2" textLength="24.4" clip-path="url(#terminal-2202794891-line-18)">A&#160;</text><text class="terminal-2202794891-r38" x="561.2" y="459.2" textLength="109.8" clip-path="url(#terminal-2202794891-line-18)">build-lo…</text><text class="terminal-2202794891-r26" x="707.6" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">│</text><text class="terminal-2202794891-r23" x="732" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">│</text><text class="terminal-2202794891-r35" x="768.6" y="459.2" textLength="134.2" clip-path="url(#terminal-2202794891-line-18)">MIME&#160;type:&#160;</text><text class="terminal-2202794891-r2" x="902.8" y="459.2" textLength="158.6" clip-path="url(#terminal-2202794891-line-18)">text/markdown</text><text class="terminal-2202794891-r23" x="1451.8" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">│</text><text class="terminal-2202794891-r1" x="1464" y="459.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-18)">\n</text><text class="terminal-2202794891-r11" x="0" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">│</text><text class="terminal-2202794891-r24" x="12.2" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">│</text><text class="terminal-2202794891-r23" x="732" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">│</text><text class="terminal-2202794891-r35" x="768.6" y="483.6" textLength="73.2" clip-path="url(#terminal-2202794891-line-19)">Size:&#160;</text><text class="terminal-2202794891-r2" x="841.8" y="483.6" textLength="85.4" clip-path="url(#terminal-2202794891-line-19)">8.2&#160;KiB</text><text class="terminal-2202794891-r23" x="1451.8" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">│</text><text class="terminal-2202794891-r1" x="1464" y="483.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-19)">\n</text><text class="terminal-2202794891-r11" x="0" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">│</text><text class="terminal-2202794891-r24" x="12.2" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">│</text><text class="terminal-2202794891-r23" x="732" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">│</text><text class="terminal-2202794891-r35" x="768.6" y="508" textLength="109.8" clip-path="url(#terminal-2202794891-line-20)">SHA-256:&#160;</text><text class="terminal-2202794891-r7" x="878.4" y="508" textLength="158.6" clip-path="url(#terminal-2202794891-line-20)">9f2c1d7ab34e…</text><text class="terminal-2202794891-r23" x="1451.8" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">│</text><text class="terminal-2202794891-r1" x="1464" y="508" textLength="12.2" clip-path="url(#terminal-2202794891-line-20)">\n</text><text class="terminal-2202794891-r11" x="0" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">│</text><text class="terminal-2202794891-r24" x="12.2" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">│</text><text class="terminal-2202794891-r23" x="732" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">│</text><text class="terminal-2202794891-r35" x="768.6" y="532.4" textLength="109.8" clip-path="url(#terminal-2202794891-line-21)">Created:&#160;</text><text class="terminal-2202794891-r2" x="878.4" y="532.4" textLength="195.2" clip-path="url(#terminal-2202794891-line-21)">2026-07-24&#160;16:05</text><text class="terminal-2202794891-r23" x="1451.8" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">│</text><text class="terminal-2202794891-r1" x="1464" y="532.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-21)">\n</text><text class="terminal-2202794891-r11" x="0" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">│</text><text class="terminal-2202794891-r24" x="12.2" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">│</text><text class="terminal-2202794891-r23" x="732" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">│</text><text class="terminal-2202794891-r23" x="1451.8" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">│</text><text class="terminal-2202794891-r1" x="1464" y="556.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-22)">\n</text><text class="terminal-2202794891-r11" x="0" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">│</text><text class="terminal-2202794891-r24" x="12.2" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">│</text><text class="terminal-2202794891-r23" x="732" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">│</text><text class="terminal-2202794891-r25" x="768.6" y="581.2" textLength="73.2" clip-path="url(#terminal-2202794891-line-23)">ORIGIN</text><text class="terminal-2202794891-r23" x="1451.8" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">│</text><text class="terminal-2202794891-r1" x="1464" y="581.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-23)">\n</text><text class="terminal-2202794891-r11" x="0" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">│</text><text class="terminal-2202794891-r24" x="12.2" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">│</text><text class="terminal-2202794891-r23" x="732" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">│</text><text class="terminal-2202794891-r2" x="768.6" y="605.6" textLength="85.4" clip-path="url(#terminal-2202794891-line-24)">created</text><text class="terminal-2202794891-r23" x="1451.8" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">│</text><text class="terminal-2202794891-r1" x="1464" y="605.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-24)">\n</text><text class="terminal-2202794891-r11" x="0" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">│</text><text class="terminal-2202794891-r24" x="12.2" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">│</text><text class="terminal-2202794891-r23" x="732" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">│</text><text class="terminal-2202794891-r35" x="768.6" y="630" textLength="109.8" clip-path="url(#terminal-2202794891-line-25)">Project:&#160;</text><text class="terminal-2202794891-r2" x="878.4" y="630" textLength="61" clip-path="url(#terminal-2202794891-line-25)">Alpha</text><text class="terminal-2202794891-r23" x="1451.8" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">│</text><text class="terminal-2202794891-r1" x="1464" y="630" textLength="12.2" clip-path="url(#terminal-2202794891-line-25)">\n</text><text class="terminal-2202794891-r11" x="0" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">│</text><text class="terminal-2202794891-r24" x="12.2" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">│</text><text class="terminal-2202794891-r23" x="732" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">│</text><text class="terminal-2202794891-r35" x="768.6" y="654.4" textLength="122" clip-path="url(#terminal-2202794891-line-26)">Workflow:&#160;</text><text class="terminal-2202794891-r2" x="890.6" y="654.4" textLength="48.8" clip-path="url(#terminal-2202794891-line-26)">code</text><text class="terminal-2202794891-r23" x="1451.8" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">│</text><text class="terminal-2202794891-r1" x="1464" y="654.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-26)">\n</text><text class="terminal-2202794891-r11" x="0" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">│</text><text class="terminal-2202794891-r24" x="12.2" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">│</text><text class="terminal-2202794891-r23" x="732" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">│</text><text class="terminal-2202794891-r35" x="768.6" y="678.8" textLength="85.4" clip-path="url(#terminal-2202794891-line-27)">Agent:&#160;</text><text class="terminal-2202794891-r2" x="854" y="678.8" textLength="158.6" clip-path="url(#terminal-2202794891-line-27)">alpha.1--code</text><text class="terminal-2202794891-r23" x="1451.8" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">│</text><text class="terminal-2202794891-r1" x="1464" y="678.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-27)">\n</text><text class="terminal-2202794891-r11" x="0" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">│</text><text class="terminal-2202794891-r24" x="12.2" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">│</text><text class="terminal-2202794891-r23" x="732" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">│</text><text class="terminal-2202794891-r35" x="768.6" y="703.2" textLength="183" clip-path="url(#terminal-2202794891-line-28)">Artifacts&#160;dir:&#160;</text><text class="terminal-2202794891-r2" x="951.6" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">-</text><text class="terminal-2202794891-r39" x="1427.4" y="703.2" textLength="24.4" clip-path="url(#terminal-2202794891-line-28)">▆▆</text><text class="terminal-2202794891-r23" x="1451.8" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">│</text><text class="terminal-2202794891-r1" x="1464" y="703.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-28)">\n</text><text class="terminal-2202794891-r11" x="0" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">│</text><text class="terminal-2202794891-r24" x="12.2" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">│</text><text class="terminal-2202794891-r23" x="732" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">│</text><text class="terminal-2202794891-r35" x="768.6" y="727.6" textLength="158.6" clip-path="url(#terminal-2202794891-line-29)">Logical&#160;path:</text><text class="terminal-2202794891-r23" x="1451.8" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">│</text><text class="terminal-2202794891-r1" x="1464" y="727.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-29)">\n</text><text class="terminal-2202794891-r11" x="0" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">│</text><text class="terminal-2202794891-r24" x="12.2" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">│</text><text class="terminal-2202794891-r23" x="732" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">│</text><text class="terminal-2202794891-r7" x="768.6" y="752" textLength="549" clip-path="url(#terminal-2202794891-line-30)">/visual/recycled/sase_7/docs/release_notes.md</text><text class="terminal-2202794891-r23" x="1451.8" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">│</text><text class="terminal-2202794891-r1" x="1464" y="752" textLength="12.2" clip-path="url(#terminal-2202794891-line-30)">\n</text><text class="terminal-2202794891-r11" x="0" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">│</text><text class="terminal-2202794891-r24" x="12.2" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">│</text><text class="terminal-2202794891-r23" x="732" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">│</text><text class="terminal-2202794891-r35" x="768.6" y="776.4" textLength="97.6" clip-path="url(#terminal-2202794891-line-31)">Object:&#160;</text><text class="terminal-2202794891-r7" x="866.2" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">-</text><text class="terminal-2202794891-r23" x="1451.8" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">│</text><text class="terminal-2202794891-r1" x="1464" y="776.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-31)">\n</text><text class="terminal-2202794891-r11" x="0" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">│</text><text class="terminal-2202794891-r24" x="12.2" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">│</text><text class="terminal-2202794891-r23" x="732" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">│</text><text class="terminal-2202794891-r35" x="768.6" y="800.8" textLength="109.8" clip-path="url(#terminal-2202794891-line-32)">Sidecar:&#160;</text><text class="terminal-2202794891-r7" x="878.4" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">-</text><text class="terminal-2202794891-r23" x="1451.8" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">│</text><text class="terminal-2202794891-r1" x="1464" y="800.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-32)">\n</text><text class="terminal-2202794891-r11" x="0" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">│</text><text class="terminal-2202794891-r24" x="12.2" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">▊</text><text class="terminal-2202794891-r26" x="707.6" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">│</text><text class="terminal-2202794891-r23" x="732" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">│</text><text class="terminal-2202794891-r23" x="1451.8" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">│</text><text class="terminal-2202794891-r1" x="1464" y="825.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-33)">\n</text><text class="terminal-2202794891-r11" x="0" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">│</text><text class="terminal-2202794891-r24" x="12.2" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">▊</text><text class="terminal-2202794891-r26" x="24.4" y="849.6" textLength="683.2" clip-path="url(#terminal-2202794891-line-34)">▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁</text><text class="terminal-2202794891-r26" x="707.6" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">▎</text><text class="terminal-2202794891-r11" x="719.8" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">│</text><text class="terminal-2202794891-r23" x="732" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">│</text><text class="terminal-2202794891-r25" x="768.6" y="849.6" textLength="61" clip-path="url(#terminal-2202794891-line-34)">PATHS</text><text class="terminal-2202794891-r23" x="1451.8" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">│</text><text class="terminal-2202794891-r1" x="1464" y="849.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-34)">\n</text><text class="terminal-2202794891-r11" x="0" y="874" textLength="12.2" clip-path="url(#terminal-2202794891-line-35)">│</text><text class="terminal-2202794891-r15" x="24.4" y="874" textLength="61" clip-path="url(#terminal-2202794891-line-35)">&#160;▸&#160;.&#160;</text><text class="terminal-2202794891-r11" x="85.4" y="874" textLength="85.4" clip-path="url(#terminal-2202794891-line-35)">&#160;expand</text><text class="terminal-2202794891-r16" x="170.8" y="874" textLength="61" clip-path="url(#terminal-2202794891-line-35)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r40" x="231.8" y="874" textLength="24.4" clip-path="url(#terminal-2202794891-line-35)">~&#160;</text><text class="terminal-2202794891-r12" x="256.2" y="874" textLength="12.2" clip-path="url(#terminal-2202794891-line-35)">1</text><text class="terminal-2202794891-r16" x="268.4" y="874" textLength="109.8" clip-path="url(#terminal-2202794891-line-35)">&#160;versions</text><text class="terminal-2202794891-r11" x="719.8" y="874" textLength="12.2" clip-path="url(#terminal-2202794891-line-35)">│</text><text class="terminal-2202794891-r23" x="732" y="874" textLength="12.2" clip-path="url(#terminal-2202794891-line-35)">│</text><text class="terminal-2202794891-r35" x="768.6" y="874" textLength="97.6" clip-path="url(#terminal-2202794891-line-35)">Stored:&#160;</text><text class="terminal-2202794891-r7" x="866.2" y="874" textLength="414.8" clip-path="url(#terminal-2202794891-line-35)">/visual/artifacts/release_notes.md</text><text class="terminal-2202794891-r41" x="1281" y="874" textLength="73.2" clip-path="url(#terminal-2202794891-line-35)">&#160;&#160;live</text><text class="terminal-2202794891-r23" x="1451.8" y="874" textLength="12.2" clip-path="url(#terminal-2202794891-line-35)">│</text><text class="terminal-2202794891-r1" x="1464" y="874" textLength="12.2" clip-path="url(#terminal-2202794891-line-35)">\n</text><text class="terminal-2202794891-r11" x="0" y="898.4" textLength="732" clip-path="url(#terminal-2202794891-line-36)">╰──────────────────────────────────────────────────────────╯</text><text class="terminal-2202794891-r23" x="732" y="898.4" textLength="732" clip-path="url(#terminal-2202794891-line-36)">╰──────────────────────────────────────────────────────────╯</text><text class="terminal-2202794891-r1" x="1464" y="898.4" textLength="12.2" clip-path="url(#terminal-2202794891-line-36)">\n</text><text class="terminal-2202794891-r12" x="0" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">j</text><text class="terminal-2202794891-r16" x="12.2" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;next</text><text class="terminal-2202794891-r16" x="73.2" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="134.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">k</text><text class="terminal-2202794891-r16" x="146.4" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;prev</text><text class="terminal-2202794891-r16" x="207.4" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="268.4" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">Enter</text><text class="terminal-2202794891-r16" x="329.4" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;view</text><text class="terminal-2202794891-r16" x="390.4" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="451.4" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">f</text><text class="terminal-2202794891-r16" x="463.6" y="922.8" textLength="85.4" clip-path="url(#terminal-2202794891-line-37)">&#160;filter</text><text class="terminal-2202794891-r16" x="549" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="610" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">z</text><text class="terminal-2202794891-r16" x="622.2" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;kind</text><text class="terminal-2202794891-r16" x="683.2" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="744.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">(</text><text class="terminal-2202794891-r16" x="756.4" y="922.8" textLength="158.6" clip-path="url(#terminal-2202794891-line-37)">&#160;prev&#160;version</text><text class="terminal-2202794891-r16" x="915" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="976" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">)</text><text class="terminal-2202794891-r16" x="988.2" y="922.8" textLength="158.6" clip-path="url(#terminal-2202794891-line-37)">&#160;next&#160;version</text><text class="terminal-2202794891-r16" x="1146.8" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="1207.8" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">a</text><text class="terminal-2202794891-r16" x="1220" y="922.8" textLength="73.2" clip-path="url(#terminal-2202794891-line-37)">&#160;agent</text><text class="terminal-2202794891-r16" x="1293.2" y="922.8" textLength="61" clip-path="url(#terminal-2202794891-line-37)">&#160;&#160;·&#160;&#160;</text><text class="terminal-2202794891-r12" x="1354.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">E</text><text class="terminal-2202794891-r16" x="1366.4" y="922.8" textLength="97.6" clip-path="url(#terminal-2202794891-line-37)">&#160;extern…</text><text class="terminal-2202794891-r1" x="1464" y="922.8" textLength="12.2" clip-path="url(#terminal-2202794891-line-37)">\n</text><text class="terminal-2202794891-r42" x="0" y="947.2" textLength="1464" clip-path="url(#terminal-2202794891-line-38)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-2202794891-r1" x="1464" y="947.2" textLength="12.2" clip-path="url(#terminal-2202794891-line-38)">\n</text><text class="terminal-2202794891-r5" x="12.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-39)">.</text><text class="terminal-2202794891-r16" x="36.6" y="971.6" textLength="195.2" clip-path="url(#terminal-2202794891-line-39)">expand&#160;relations</text><text class="terminal-2202794891-r16" x="231.8" y="971.6" textLength="36.6" clip-path="url(#terminal-2202794891-line-39)">&#160;·&#160;</text><text class="terminal-2202794891-r5" x="268.4" y="971.6" textLength="12.2" clip-path="url(#terminal-2202794891-line-39)">~</text><text class="terminal-2202794891-r16" x="292.8" y="971.6" textLength="97.6" clip-path="url(#terminal-2202794891-line-39)">versions</text><text class="terminal-2202794891-r28" x="1281" y="971.6" textLength="61" clip-path="url(#terminal-2202794891-line-39)">&#160;AXE&#160;</text><text class="terminal-2202794891-r28" x="1342" y="971.6" textLength="109.8" clip-path="url(#terminal-2202794891-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:41: AssertionError
___________________ test_artifacts_files_empty_png_snapshot ____________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...s_files_empty.py', test_line=24, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff9586fd2b0>

    async def test_artifacts_files_empty_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        monkeypatch.setattr(
            "sase.ace.tui.actions.artifacts._collect_artifacts_project_choices",
            _choices,
        )
        monkeypatch.setattr(
            files_pane,
            "load_files_snapshot",
            lambda project, _limit: snapshot((), project=project),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press(page.artifacts_digit("files"), "(")
            await page.expect_state("artifacts_subtab", "files")
            pane = page.query_one_widget("#artifacts-files-pane", ArtifactsFilesPane)
            await page.wait_for(
                lambda _state: pane.snapshot is not None and pane.snapshot.rows == ()
            )
            await wait_for_svg_contains(page, "No artifact files")
            await wait_for_svg_contains(page, "Select an artifact file to inspect it.")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "artifacts_files_empty_120x40",
                title="ACE Artifacts - Files empty",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files_empty.py:51: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_files_empty_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x017\xfeIDA...00\x00\xe8\x7f\x8e\x07\xb7\xce\xe0\xf6\x96&\xee\x8cz\xc1\x7f\x03\x8f\xc0r\x88\'\xfa\xbbP\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files_empty.py::test_artifacts_files_empty_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-196022824-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files_empty.py'
test_line = 24
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_files_empty_120x40.png
E       Changed pixels: 161076/1520532 (10.593398%); materially changed pixels: 160655/1520532 (10.565710%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_files_empty.py__test_artifacts_files_empty_png_snapshot/artifacts_files_empty_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_files_empty.py__test_artifacts_files_empty_png_snapshot/artifacts_files_empty_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_files_empty.py__test_artifacts_files_empty_png_snapshot/artifacts_files_empty_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_files_empty.py__test_artifacts_files_empty_png_snapshot/artifacts_files_empty_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_artifacts_split_mode_png_snapshot[narrow-size0-artifacts_split_narrow_120x40] _
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

mode = 'narrow', size = (120, 40)
snapshot_name = 'artifacts_split_narrow_120x40'
ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...tifacts_split.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff954b41fd0>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_split_mode_png_0')

    @pytest.mark.parametrize(
        ("mode", "size", "snapshot_name"),
        (
            ("narrow", (120, 40), "artifacts_split_narrow_120x40"),
            ("even", (120, 40), "artifacts_split_even_120x40"),
            ("wide", (120, 40), "artifacts_split_wide_120x40"),
            ("narrow", (80, 24), "artifacts_split_narrow_80x24"),
        ),
    )
    async def test_artifacts_split_mode_png_snapshot(
        mode: ArtifactsSplitMode,
        size: tuple[int, int],
        snapshot_name: str,
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
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
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            pane._update_detail()
            page.app.artifacts_split_mode = mode
            await wait_for_svg_contains(page, "Tasks")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=f"ACE Artifacts - {mode.title()} split",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py:65: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_split_narrow_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01c\x10IDA...13\x00\x00\x00\x00\x00L?\x83\xd9m \xbb=\x16\x13wV-\xf0\xff\x00\xa0\x80\xf3$\xcbq\x84\x0b\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[narrow-size0-artifacts_split_narrow_120x40]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3544530407-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py'
test_line = 26
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_split_narrow_120x40.png
E       Changed pixels: 183613/1520532 (12.075576%); materially changed pixels: 182970/1520532 (12.033288%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size0-artifacts_split_narrow_120x40/artifacts_split_narrow_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size0-artifacts_split_narrow_120x40/artifacts_split_narrow_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size0-artifacts_split_narrow_120x40/artifacts_split_narrow_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size0-artifacts_split_narrow_120x40/artifacts_split_narrow_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_artifacts_split_mode_png_snapshot[even-size1-artifacts_split_even_120x40] _
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

mode = 'even', size = (120, 40), snapshot_name = 'artifacts_split_even_120x40'
ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...tifacts_split.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff953ecfc40>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_split_mode_png_1')

    @pytest.mark.parametrize(
        ("mode", "size", "snapshot_name"),
        (
            ("narrow", (120, 40), "artifacts_split_narrow_120x40"),
            ("even", (120, 40), "artifacts_split_even_120x40"),
            ("wide", (120, 40), "artifacts_split_wide_120x40"),
            ("narrow", (80, 24), "artifacts_split_narrow_80x24"),
        ),
    )
    async def test_artifacts_split_mode_png_snapshot(
        mode: ArtifactsSplitMode,
        size: tuple[int, int],
        snapshot_name: str,
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
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
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            pane._update_detail()
            page.app.artifacts_split_mode = mode
            await wait_for_svg_contains(page, "Tasks")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=f"ACE Artifacts - {mode.title()} split",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py:65: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_split_even_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x98AIDA...x00\x00\x00\x00\x00\x0e>;k\x97\xc1\xda\xe5\xfe\x98\xb8\xb3\xd1\x02\xff\x172\x004\x07htnq\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[even-size1-artifacts_split_even_120x40]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-1753372725-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py'
test_line = 26
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_split_even_120x40.png
E       Changed pixels: 209076/1520532 (13.750187%); materially changed pixels: 207723/1520532 (13.661205%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_even-size1-artifacts_split_even_120x40/artifacts_split_even_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_even-size1-artifacts_split_even_120x40/artifacts_split_even_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_even-size1-artifacts_split_even_120x40/artifacts_split_even_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_even-size1-artifacts_split_even_120x40/artifacts_split_even_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_artifacts_split_mode_png_snapshot[wide-size2-artifacts_split_wide_120x40] _
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

mode = 'wide', size = (120, 40), snapshot_name = 'artifacts_split_wide_120x40'
ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...tifacts_split.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff953ecfcb0>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_split_mode_png_2')

    @pytest.mark.parametrize(
        ("mode", "size", "snapshot_name"),
        (
            ("narrow", (120, 40), "artifacts_split_narrow_120x40"),
            ("even", (120, 40), "artifacts_split_even_120x40"),
            ("wide", (120, 40), "artifacts_split_wide_120x40"),
            ("narrow", (80, 24), "artifacts_split_narrow_80x24"),
        ),
    )
    async def test_artifacts_split_mode_png_snapshot(
        mode: ArtifactsSplitMode,
        size: tuple[int, int],
        snapshot_name: str,
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
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
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            pane._update_detail()
            page.app.artifacts_split_mode = mode
            await wait_for_svg_contains(page, "Tasks")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=f"ACE Artifacts - {mode.title()} split",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py:65: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_split_wide_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb7xIDA...x00\x00\xb0\xe5Y\x9d\xfd\xac\xc8~\xe6\xc7\xc0\x9d\x8d&\xf8\xff\xbe?\x0b\x01\xdac\xad\xa3\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[wide-size2-artifacts_split_wide_120x40]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-3540808445-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py'
test_line = 26
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_split_wide_120x40.png
E       Changed pixels: 222067/1520532 (14.604559%); materially changed pixels: 220673/1520532 (14.512881%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_wide-size2-artifacts_split_wide_120x40/artifacts_split_wide_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_wide-size2-artifacts_split_wide_120x40/artifacts_split_wide_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_wide-size2-artifacts_split_wide_120x40/artifacts_split_wide_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_wide-size2-artifacts_split_wide_120x40/artifacts_split_wide_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_ test_artifacts_split_mode_png_snapshot[narrow-size3-artifacts_split_narrow_80x24] _
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

mode = 'narrow', size = (80, 24), snapshot_name = 'artifacts_split_narrow_80x24'
ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...tifacts_split.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff973227c40>
tmp_path = PosixPath('/var/tmp/sase-45aeffea/pytest-of-bryan/pytest-3/popen-gw0/test_artifacts_split_mode_png_3')

    @pytest.mark.parametrize(
        ("mode", "size", "snapshot_name"),
        (
            ("narrow", (120, 40), "artifacts_split_narrow_120x40"),
            ("even", (120, 40), "artifacts_split_even_120x40"),
            ("wide", (120, 40), "artifacts_split_wide_120x40"),
            ("narrow", (80, 24), "artifacts_split_narrow_80x24"),
        ),
    )
    async def test_artifacts_split_mode_png_snapshot(
        mode: ArtifactsSplitMode,
        size: tuple[int, int],
        snapshot_name: str,
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
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
            await page.press("3")
            await page.expect_state("artifacts_subtab", "beads")
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is snapshot)
            pane._update_detail()
            page.app.artifacts_split_mode = mode
            await wait_for_svg_contains(page, "Tasks")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=f"ACE Artifacts - {mode.title()} split",
            )

tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py:65: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'artifacts_split_narrow_80x24'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x03\xe2\x00\x00\x02|\x08\x06\x00\x00\x00z\x01\x1b\xcc\x00\x016RIDATx\x9c...8et\xeaG\x0b!\x84\x10B\x08!\x84\x10B"q\xc0\x12\xdf\x07\xc3\x15\xf8\xff$@!\xde*\xa2\\\xb7\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[narrow-size3-artifacts_split_narrow_80x24]'
source_svg = '<svg class="rich-terminal" viewBox="0 0 994 635.5999999999999" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generate...tLength="109.8" clip-path="url(#terminal-3229263571-line-23)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py'
test_line = 26
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/artifacts_split_narrow_80x24.png
E       Changed pixels: 133964/632184 (21.190666%); materially changed pixels: 133161/632184 (21.063646%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size3-artifacts_split_narrow_80x24/artifacts_split_narrow_80x24/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size3-artifacts_split_narrow_80x24/artifacts_split_narrow_80x24/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size3-artifacts_split_narrow_80x24/artifacts_split_narrow_80x24/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_artifacts_split.py__test_artifacts_split_mode_png_snapshot_narrow-size3-artifacts_split_narrow_80x24/artifacts_split_narrow_80x24/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
______________ test_fuzzy_at_reference_payload_panel_png_snapshot ______________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...e_completion.py', test_line=132, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff955173230>

    async def test_fuzzy_at_reference_payload_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        rows = [
            _document_payload(
                "202607/sase_sites_hub_and_pages/sase_sites_hub_and_pages.md",
                "SASE Sites Hub and Pages",
                fuzzy=True,
            ),
            _document_payload(
                "202605/site_deployment_checklist.md",
                "Site Deployment Checklist",
                fuzzy=True,
            ),
            _document_payload(
                "202604/research_portal.md",
                "Research Site Portal",
                fuzzy=True,
            ),
        ]
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            bar = await mount_prompt_bar(page, "Attach research")
            bar.show_file_completions(
                "research: documents",
                rows,
                selected_index=0,
                completion_kind=ARTIFACT_REF_COMPLETION_KIND,
                artifact_ref_payload_count=3,
                artifact_ref_payload_total=305,
            )
            await wait_for_svg_contains(page, "fuzzy")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "at_reference_fuzzy_payload_panel_120x40",
                title="ACE prompt input — fuzzy @ payload completion",
            )

tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py:169: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'at_reference_fuzzy_payload_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xac\xf7...\x08!\x84\x10B\x08!\xa4\xebqJ\xbfN\xe8\xd7~,\xdc\xe9\xb7\xc1\xff\x0fK\xac\xdd\xb22\xealV\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_fuzzy_at_reference_payload_panel_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="971.6" textLength="36.6" clip-path="url(#terminal-1102417095-line-39)">&#160;─┘</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py'
test_line = 132
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/at_reference_fuzzy_payload_panel_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 32261/1520532 (2.121692%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_fuzzy_at_reference_payload_panel_png_snapshot/at_reference_fuzzy_payload_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_fuzzy_at_reference_payload_panel_png_snapshot/at_reference_fuzzy_payload_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_fuzzy_at_reference_payload_panel_png_snapshot/at_reference_fuzzy_payload_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_fuzzy_at_reference_payload_panel_png_snapshot/at_reference_fuzzy_payload_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________ test_truncated_at_reference_payload_panel_png_snapshot ____________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...e_completion.py', test_line=176, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff95964a350>

    async def test_truncated_at_reference_payload_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        rows = [
            _document_payload(
                "202607/site_inventory.md",
                "Site Inventory",
                fuzzy=False,
            ),
            _document_payload(
                "202607/site_rollout.md",
                "Site Rollout",
                fuzzy=False,
            ),
        ]
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            bar = await mount_prompt_bar(page, "Attach research")
            bar.show_file_completions(
                "research: documents",
                rows,
                selected_index=0,
                completion_kind=ARTIFACT_REF_COMPLETION_KIND,
                artifact_ref_payload_count=2,
                artifact_ref_payload_total=1205,
                artifact_ref_truncated_payloads=1203,
            )
            await wait_for_svg_contains(page, "not scanned")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "at_reference_truncated_payload_panel_120x40",
                title="ACE prompt input — truncated @ payload completion",
            )

tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py:209: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'at_reference_truncated_payload_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01p@IDATx\...\x08!\x84\x10B\x08!z\x1e\xfb\xa2\xd7\xbb\xd1k3\x0bw&\xed\xf0\xff\x01\x1e2}J\xe4\xa7\xa5h\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_truncated_at_reference_payload_panel_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="971.6" textLength="36.6" clip-path="url(#terminal-2752970867-line-39)">&#160;─┘</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py'
test_line = 176
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/at_reference_truncated_payload_panel_120x40.png
E       Changed pixels: 32325/1520532 (2.125901%); materially changed pixels: 32261/1520532 (2.121692%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_truncated_at_reference_payload_panel_png_snapshot/at_reference_truncated_payload_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_truncated_at_reference_payload_panel_png_snapshot/at_reference_truncated_payload_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_truncated_at_reference_payload_panel_png_snapshot/at_reference_truncated_payload_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_at_reference_completion.py__test_truncated_at_reference_payload_panel_png_snapshot/at_reference_truncated_payload_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
________________ test_prompt_stack_g_prefix_hints_png_snapshot _________________
[gw2] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ac...prompt_stack.py', test_line=370, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc6089217f0>

    async def test_prompt_stack_g_prefix_hints_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("2")
            await page.expect_state("artifacts_subtab", "patches")
            await page.expect_state("tab", "patches")
            indicator = page.app.query_one(
                "#stashed-prompts-indicator", StashedPromptsIndicator
            )
            indicator.set_count(2)
            bar = await mount_prompt_bar(page, TWO_PANE_PROMPT)
    
            await page.press("escape", "g")
            text_area = bar.active_text_area()
            await wait_for_state(
                page,
                lambda: (
                    text_area._vim_mode == "normal"
                    and text_area._pending_keys == "g"
                    and bar._g_prefix_hints_visible
                ),
                description="NORMAL-mode g-prefix hint panel",
            )
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "prompt_stack_g_prefix_hints_120x40",
                title="ACE prompt stack — g prefix hints",
            )

tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py:400: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'prompt_stack_g_prefix_hints_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02!\xc2IDA...x00\x00\xbd\xcf\xd6\xe8gc\xf4\xf3\x92&\xeeLz\xc3\xff\x07\x88\xb9\x99\xcf\x0e\xa7\x00\xec\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_g_prefix_hints_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...="971.6" textLength="36.6" clip-path="url(#terminal-1645793308-line-39)">&#160;─┘</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py'
test_line = 370
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/tests/ace/tui/visual/snapshots/png/prompt_stack_g_prefix_hints_120x40.png
E       Changed pixels: 266181/1520532 (17.505781%); materially changed pixels: 205754/1520532 (13.531711%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_prompt_stack.py__test_prompt_stack_g_prefix_hints_png_snapshot/prompt_stack_g_prefix_hints_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_prompt_stack.py__test_prompt_stack_g_prefix_hints_png_snapshot/prompt_stack_g_prefix_hints_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_prompt_stack.py__test_prompt_stack_g_prefix_hints_png_snapshot/prompt_stack_g_prefix_hints_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_prompt_stack.py__test_prompt_stack_g_prefix_hints_png_snapshot/prompt_stack_g_prefix_hints_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
============================= slowest 20 durations =============================
40.72s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
26.73s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
18.70s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
17.01s call     tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files.py::test_artifacts_files_populated_png_snapshot
13.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
13.73s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
11.45s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
11.03s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
10.90s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
10.88s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py::test_prompt_cursor_readout_stack_png_snapshot
10.64s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_codeblock_highlight_stack_png_snapshot[textual-dark-prompt_codeblock_highlight_stack_dark_120x40-ACE prompt stack \u2014 code highlighting, dark theme]
10.38s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_visual_png_snapshot
10.36s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_bullet_highlight_solo_png_snapshot[textual-dark-prompt_bullet_highlight_solo_dark_120x40-ACE prompt input \u2014 bullet-dash highlighting, dark theme]
9.75s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_saved_feedback_png_snapshot
9.62s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
9.57s call     tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py::test_placeholder_highlight_png_snapshot
9.56s call     tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_fuzzy_at_reference_payload_panel_png_snapshot
9.34s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py::test_vcs_ref_completion_panel_no_orgs_png_snapshot
9.33s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_cell_edit_png_snapshot
9.19s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots.py::test_footer_leader_overflow_wide_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots.py::test_footer_leader_overflow_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_add_chooser_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_script_picker_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_new_lumberjack_identity_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_editor_constrained_width_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_axe_editor.py::test_axe_editor_compact_lumberjack_sheet_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_populated_png_snapshot[textual-dark-glossary_panel_populated_dark_120x40-ACE glossary panel - populated dark theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_populated_png_snapshot[textual-light-glossary_panel_populated_light_120x40-ACE glossary panel - populated light theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_empty_png_snapshot[textual-dark-glossary_panel_empty_dark_120x40-ACE glossary panel - empty dark theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_empty_png_snapshot[textual-light-glossary_panel_empty_light_120x40-ACE glossary panel - empty light theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_glossary_preview_card_full_png_snapshot[textual-dark-glossary_preview_card_full_dark_120x40-ACE glossary preview card - full dark theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_glossary_preview_card_full_png_snapshot[textual-light-glossary_preview_card_full_light_120x40-ACE glossary preview card - full light theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_glossary_preview_card_minimal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_glossary_preview.py::test_repo_preview_card_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py::test_help_panel_keymaps_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_notification_report.py::test_notification_report_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py::test_copy_as_stitches_selected_dark_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_copy_as_palette.py::test_copy_as_over_artifact_files_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py::test_epic_plan_toast_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py::test_tale_plan_toast_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_populated_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_collapsed_relations_rail_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_empty.py::test_artifacts_beads_empty_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads_reopened.py::test_artifacts_beads_reopened_detail_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files.py::test_artifacts_files_populated_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files_empty.py::test_artifacts_files_empty_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[narrow-size0-artifacts_split_narrow_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[even-size1-artifacts_split_even_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[wide-size2-artifacts_split_wide_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[narrow-size3-artifacts_split_narrow_80x24]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_fuzzy_at_reference_payload_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_truncated_at_reference_payload_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_g_prefix_hints_png_snapshot
============ 35 failed, 695 passed, 1 skipped in 769.15s (0:12:49) =============
error: recipe `test-visual` failed on line 459 with exit code 1

