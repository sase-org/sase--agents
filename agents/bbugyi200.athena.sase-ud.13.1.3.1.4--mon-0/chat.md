# Chat History - ace-run (sase-ud.13.1.3.1.4--mon-0)

- **TIMESTAMP:** 2026-08-27 18:48:40 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-ud.13.1.3.1.4--mon-0

## Prompt

sase monitor start --command 'sh -c just check-full; check_status=$?; just test-visual; visual_status=$?; if [ "$check_status" -ne 0 ]; then exit "$check_status"; fi; exit "$visual_status"' --reason 'Run full and visual verification before closing phase bead sase-ud.13.1.3.1.4 after fixing rail parity and updating visual goldens'

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
    check-bead-note-migration *args    # Compare legacy bead note blobs with the structured note projection.
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
    ratchet-core-revision *args        # verify without writing, or --report-only to preview the pin change.
    ratchet-core-window *args
    refresh-contexts-baseline *args    # to the static import closure when the cache is empty.
    refresh-contract-manifest          # `@pytest.mark.contract` from a test module.
    refresh-shard-timings *args        # split.
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
    test-cost-budget *args             # Check the latest test-cost recording against committed suite-cost budgets.
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
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.32.11 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.31.12,<0.32.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [840 items]

........................................................................ [  8%]
........................................................................ [ 17%]
........................................................................ [ 25%]
........................................................................ [ 34%]
........................................................................ [ 42%]
........................................................................ [ 51%]
.......F................................................................ [ 60%]
........................................................................ [ 68%]
..F..................................................................... [ 77%]
......................................................F................. [ 85%]
........................................................................ [ 94%]
................................................                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________________ test_epic_plan_toast_png_snapshot _______________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ac...ts_plan_toast.py', test_line=26, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc2288214e0>

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
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01:\xb1IDA....\xfd\t\x00\x00\x00\x00\x00N<#\xb5\xcb\xcb\xb5\xcb\xf31pg\xab\t\xfe?I\xebn\xa4\x1d\xccUW\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py::test_epic_plan_toast_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-2537514860-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py'
test_line = 26
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/visual/snapshots/png/plan_toast_epic_120x40.png
E       Changed pixels: 3717/1520532 (0.244454%); materially changed pixels: 3600/1520532 (0.236759%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_plan_toast.py__test_epic_plan_toast_png_snapshot/plan_toast_epic_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
____________________ test_startup_update_toast_png_snapshot ____________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ac...update_toast.py', test_line=144, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4b1a938360>

    async def test_startup_update_toast_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The startup update toast is readable and tied to the Updates tab accent."""
        patch_startup_loaders(monkeypatch)
        status = _toast_status()
        monkeypatch.setattr(
            update_toast,
            "_load_update_toast_config",
            lambda: update_toast._UpdateToastConfig(startup_toast=True),
        )
        monkeypatch.setattr(
            update_toast,
            "get_cached_update_status",
            lambda **_kwargs: status,
        )
        schedule_toast = UpdateToastMixin._schedule_startup_update_toast_check
        monkeypatch.setattr(
            UpdateToastMixin,
            "_schedule_startup_update_toast_check",
            lambda _self: None,
        )
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            notifications=True,
            startup_policy="real",
        ) as page:
            await page.press(page.artifacts_digit("patches"))
            await page.expect_state("artifacts_subtab", "patches")
            schedule_toast(page.app)
            await page.wait_for(lambda _s: bool(list(page.app._notifications)))
            await page.wait_for(lambda _s: _toast_is_mounted(page))
            page.app.screen.set_focus(None)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "startup_update_toast_120x40",
                title="ACE startup update toast",
            )

tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py:182: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'startup_update_toast_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x8d-IDA...x00\x00\x98x\xf6\x17\xb7=\xc5\xed\xc9\xe8\xb8\xb3\xd9\x08\xff?\xba\x04\xcf"\xec\x814\xca\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py::test_startup_update_toast_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...tLength="109.8" clip-path="url(#terminal-4033075961-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py'
test_line = 144
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/visual/snapshots/png/startup_update_toast_120x40.png
E       Changed pixels: 1707/1520532 (0.112263%); materially changed pixels: 1603/1520532 (0.105424%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_toast.py__test_startup_update_toast_png_snapshot/startup_update_toast_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_toast.py__test_startup_update_toast_png_snapshot/startup_update_toast_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_toast.py__test_startup_update_toast_png_snapshot/startup_update_toast_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_update_toast.py__test_startup_update_toast_png_snapshot/startup_update_toast_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
_____________________ test_help_panel_keymaps_png_snapshot _____________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ac...ts_help_panel.py', test_line=31, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe33edd9780>

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
            await page.press(page.artifacts_digit("patches"))
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
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\xb1\x97...x10B\x08!\x84\x10B\x08!\x84\x10Bt\x1eK\xf1k>~\x8d\xb1pgZ\x82?\x03\xe2$\x89\x98\x938\xc1m\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py::test_help_panel_keymaps_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...xtLength="109.8" clip-path="url(#terminal-147143256-line-39)">&#160;STOPPED&#160;</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py'
test_line = 31
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15')

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/visual/snapshots/png/help_keymaps_changespecs_120x40.png
E       Changed pixels: 55538/1520532 (3.652537%); materially changed pixels: 55471/1520532 (3.648131%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_help_panel.py__test_help_panel_keymaps_png_snapshot/help_keymaps_changespecs_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
============================= slowest 20 durations =============================
27.38s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
22.15s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
15.40s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_scoped_frontmatter_png_snapshot
12.91s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_normal_png_snapshot
12.81s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
12.62s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_codeblock_highlight_stack_png_snapshot[textual-dark-prompt_codeblock_highlight_stack_dark_120x40-ACE prompt stack \u2014 code highlighting, dark theme]
12.52s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
11.56s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
11.25s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_tree_fold_levels_png_snapshots
11.17s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_bullet_highlight_solo_png_snapshot[textual-light-prompt_bullet_highlight_solo_light_120x40-ACE prompt input \u2014 bullet-dash highlighting, light theme]
10.95s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot
10.94s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_populated_png_snapshot
10.91s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_new_and_clean_png_snapshots[True-mini_xprompt_pane_clean_light_120x40-ACE mini-xprompt pane - clean light]
10.90s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_project_completion.py::test_vcs_project_completion_panel_png_snapshot
10.82s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_provider_scoped_menu_png_snapshot
10.80s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_skill_completion.py::test_prompt_skill_completion_long_description_png_snapshot
10.79s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py::test_wait_target_completion_png_snapshot
10.54s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
10.09s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
9.96s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_g_prefix_hints_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_plan_toast.py::test_epic_plan_toast_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py::test_startup_update_toast_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_help_panel.py::test_help_panel_keymaps_png_snapshot
============= 3 failed, 837 passed, 1 skipped in 199.91s (0:03:19) =============
error: recipe `test-visual` failed on line 454 with exit code 1

