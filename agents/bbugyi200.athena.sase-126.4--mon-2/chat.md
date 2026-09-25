# Chat History - ace-run (sase-126.4--mon-2)

- **TIMESTAMP:** 2026-09-17 21:34:27 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-126.4--mon-2

## Prompt

sase monitor start --command 'just install && just check && just test-visual && just phase7-perf-check && just check-full' --reason 'Run integrated verification for bead sase-126.4 after fixing gate failure outcome attempt ids for the pinned core contract'

## Response

[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/db4ece99d0947094d80d77f1048f98580a1317c29229d7be540fdd21777fb7c3/sase_core_rs-0.34.50-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 8ms
Prepared 1 package in 1ms
Uninstalled 1 package in 1ms
Installed 1 package in 12ms
 ~ sase-core-rs==0.34.50 (from file:///home/bryan/.sase/cache/sase-core-wheels/db4ece99d0947094d80d77f1048f98580a1317c29229d7be540fdd21777fb7c3/sase_core_rs-0.34.50-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `dev-update` profile [optimized] target(s) in 1.00s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 616ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
Prepared 1 package in 1.16s
Uninstalled 1 package in 17ms
Installed 1 package in 6ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.34.47 is missing 4 capability(s) that exist in a published sase-core release.
[core-floor-probe] service_enablement_resolve: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_build: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_read: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_write: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
{"cache_hit": true, "capabilities": [{"commit": "fe7c4a0", "name": "service_enablement_resolve", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_build", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_read", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_write", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}], "declared_floor": "0.34.47", "exit_code": 3, "message": "sase-core-rs==0.34.47 is missing 4 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✓ test (scoped)
scoped: selected 295 of 3972 test files (7.4%; rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); contexts baseline stale; est 954s/444s; gear 4 workers
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 9/9 workers
9 workers [960 items]

........................................................................ [  7%]
........................................................................ [ 15%]
........................................................................ [ 22%]
........................................................................ [ 30%]
..................................................F..................... [ 37%]
..F.......F....F.F...........F.......FF......F..........F.....F......... [ 45%]
.....F.F.....F..........F...F..F.....F.F........F.......F.....F....F.... [ 52%]
....F.....F.....F.FF.F......FF..FF.....F...F.....F.....FF.......FF...... [ 60%]
..F.F.....F......F......F......F.......F....F..F.......F.F....F........F [ 67%]
............F......F......F......F..............F.......F.....F......... [ 75%]
F.........F........F....F..F......F......F........F......FF..F.......F.. [ 82%]
..F..F......F...F........F...........F.....F...F.....F.F...........F.... [ 90%]
...........F............F......F.......FF..F....FF........F.FF.FF..F.F.F [ 97%]
.F.F..F..F....FF....F...                                                 [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________ test_real_fakey_completed_retry_chain_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_retry_e2e.py', test_line=240, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_real_fakey_completed_retr0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f061440fbf0>

    async def test_real_fakey_completed_retry_chain_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        harness = FakeyRetryHarness(
            tmp_path,
            monkeypatch,
            wait_times=[0],
            spawn_new_agent=True,
            expose_to_agent_loader=True,
            artifacts_timestamp="20260706114500",
        )
        harness.seed_running_agent(started_at=datetime(2026, 7, 6, 11, 45, 0))
        harness.use_scenario(
            monkeypatch,
            [retryable_failure("temporarily unavailable"), successful_attempt()],
        )
        child_artifacts = harness.run_spawn_retry_chain(
            child_artifacts_timestamp="20260706115500"
        )
        harness.normalize_visual_timestamps(
            _VISUAL_NOW,
            stopped_at=datetime(2026, 7, 6, 11, 46, 0),
        )
        harness.normalize_visual_timestamps(
            _VISUAL_NOW,
            stopped_at=datetime(2026, 7, 6, 11, 57, 0),
            artifacts_dir=child_artifacts,
        )
        _patch_sentinel_pid_liveness(monkeypatch)
        patch_startup_loaders(monkeypatch, use_real_agent_loader=True)
    
        async with AcePage(query='"fakey"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=2)
    
            loaded_states = [
                (
                    agent.status,
                    agent.retry_attempt,
                    agent.retried_as_timestamp,
                    agent.retry_chain_root_timestamp,
                )
                for agent in page.app._agents
            ]
            assert [state[0] for state in loaded_states] == ["DONE", "FAILED (RETRIED)"]
            assert loaded_states[0][1:] == (1, None, "20260706114500")
            assert loaded_states[1][1:] == (
                0,
                "20260706115500",
                "20260706114500",
            )
            await wait_for_svg_contains(page, "FAILED")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "FAILED")
            assert_page_svg_contains(page, "↳")
            assert_page_svg_contains(page, "↻1")
            assert_page_svg_contains(page, "DONE")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_e2e_completed_chain_120x40",
                title="ACE real fakey completed retry chain",
            )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py:298: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_e2e_completed_chain_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02ocIDATx\...\x00\x00\x00\x00L>\x07\x93\x9f\xa1\xe4\xe7W\x1a\xb83m\x82\xff\x1f9\xf1\xaf\x1ff\x85\xe8+\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_e2e_completed_chain_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_completed_retry_chain_png_snapshot/agents_retry_e2e_completed_chain_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_completed_retry_chain_png_snapshot/agents_retry_e2e_completed_chain_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_completed_retry_chain_png_snapshot/agents_retry_e2e_completed_chain_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_completed_retry_chain_png_snapshot/agents_retry_e2e_completed_chain_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:278: AssertionError
----------------------------- Captured stdout call -----------------------------
╭────── 🤖 Workflow-Tmp_260917_212730-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

✅ Waiting for Fakey completed in 00:00╭─────── 🤖 Workflow-Tmp_260917_212730-Main [Big]_Error Agent - Prompt ────────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_212730-Main [Big]_Error Agent - Response ───────╮
│                                                                              │
│  Error running LLM provider command (exit code 1)                            │
│  stderr: FAKEY-RETRYABLE: temporarily unavailable                            │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

Chat history saved to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_real_fakey_completed_retr0/sase-home/chats/202607/fakey_e2e-ace_run-fakey_e2e-260706_114500.md
Done marker written to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_real_fakey_completed_retr0/sase-home/projects/fakey-e2e/artifacts/ace-run/20260706114500/done.json (outcome: failed_retried)
╭────── 🤖 Workflow-Tmp_260917_212731-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Your previous attempt hit a model context limit or transient provider       │
│  failure. Any file edits, new tests, and other on-disk changes you made are  │
│  preserved. Before making additional changes, run `git status` and `git      │
│  diff` to see what is already in place, then continue implementing the plan  │
│  from wherever you left off. Do not re-apply edits that are already          │
│  present.                                                                    │
│                                                                              │
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
fakey recovered

✅ Waiting for Fakey completed in 00:00
Chat history saved to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_real_fakey_completed_retr0/sase-home/chats/202607/fakey_e2e-ace_run-fakey_e2e-260706_115500.md
Preparing PDFs from Markdown... found 0, cap 10
[PDF] preparing Markdown PDFs (0 source(s), cap 10)
[PDF] complete: 0 generated, 0 skipped
[artifacts] default capture: stored=0 referenced=0 skipped=0 declared=0 cap_fired=false
Done marker written to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_real_fakey_completed_retr0/sase-home/projects/fakey-e2e/artifacts/ace-run/20260706115500/done.json
----------------------------- Captured stderr call -----------------------------
FAKEY-RETRYABLE: temporarily unavailable
/home/bryan/bin/bam: line 3: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/home0/lib/bugyi.sh: No such file or directory
_________________________ test_agent_list_png_snapshot _________________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pshots_agents.py', test_line=45, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e100dd0>

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

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:58: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_list_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfacIDA...\x84\x10B\x08!\x84\x10Rz\\\xd3\xaf\x98~\x9dE\xe0N\xbf\x04\xff\x06\x10\x14\x1c3\xd2%O\x9c\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_list_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_list_png_snapshot/agents_list_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_agent_reverted_indicator_png_snapshot __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pshots_agents.py', test_line=65, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb266554d00>

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

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:81: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_reverted_indicator_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x01{IDA...B\x08!\x84\x90\xb1\xc7\x05\xfd\xe9\xd5\x9f\xe3\xd8\xb8\xd3/\xc0\xbf\x03G:\xfe_\xc6QA\xb8\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_reverted_indicator_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_reverted_indicator_png_snapshot/agents_reverted_indicator_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agents_sase_plan_metadata_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._sase_context.py', test_line=40, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060ed5c150>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_sase_plan_metadata0')

    async def test_agents_sase_plan_metadata_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        relative_plan_path = Path("sase/repos/plans/202607/agent intent metadata.md")
        plan_path = tmp_path / relative_plan_path
        plan_path.parent.mkdir(parents=True)
        plan_path.write_text(
            "---\n"
            "tier: tale\n"
            "title: Agent intent metadata\n"
            "goal: >\n"
            "  Make the selected agent's intended outcome legible while preserving fast\n"
            "  navigation and the approved destination.\n"
            "size: medium\n"
            "---\n"
            "# Plan\n",
            encoding="utf-8",
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-agent-intent",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 7, 15, 9, 0, 0),
            raw_suffix="20260715090000",
            agent_name="visual.agent-intent",
            plan_path=relative_plan_path.as_posix(),
            sdd_plan_path=relative_plan_path.as_posix(),
            plan_committed=True,
            plan_action="tale",
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "SASE CONTEXT")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "SASE CONTEXT")
            assert_page_svg_contains(page, "PLAN")
            assert_page_svg_contains(page, "tale")
            assert_page_svg_contains(page, "Title:")
            assert_page_svg_contains(page, "Agent intent metadata")
            assert_page_svg_contains(page, "Goal:")
            assert_page_svg_contains(page, "Path:")
            assert_page_svg_contains(page, "sase/repos/plans/202607")
            assert_page_svg_contains(page, "intended outcome")
            assert_page_svg_contains(page, "approved")
            assert_page_svg_contains(page, "destination")
>           ace_png_visual.assert_page_png(
                page,
                "agents_plan_goal_metadata_120x40",
                title="ACE agents SASE plan metadata",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:97: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_plan_goal_metadata_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf7\x1a...8!\x84\x10B\x08!$\xf7\xb8\xa8_A\xfd:\x8e\xc4\x9dn\x05\xfe\x1d\x9e\xc3\x17\x12\\K\xa4\xec\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_plan_goal_metadata_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_sase_plan_metadata_png_snapshot/agents_plan_goal_metadata_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_sase_plan_metadata_png_snapshot/agents_plan_goal_metadata_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_sase_plan_metadata_png_snapshot/agents_plan_goal_metadata_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_sase_plan_metadata_png_snapshot/agents_plan_goal_metadata_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
____________________ test_agent_stopped_status_png_snapshot ____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pshots_agents.py', test_line=88, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb267a61860>

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

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:102: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_stopped_status_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02)\xadIDA...x84\x10B\x08!d\xe0\xd1\xa3_\x9d\xfa\xf5!\x12w\xfam\xf0\xff\x01i\x8b\x00c\x0e\x19\xaf\x19\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_stopped_status_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_stopped_status_png_snapshot/agents_stopped_status_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________ test_agent_plan_handoff_status_colors_png_snapshot ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=109, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb268801ef0>

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

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:129: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_plan_handoff_status_colors_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfegIDA...a\xa2(\x8a\xa2(\xca\xe8\xe3\x98y\r\x98\xd7\x1e6\xee\x8c:\xe0\xff\x03%\xdf\xc4\x98wD\xfbV\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_plan_handoff_status_colors_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_plan_handoff_status_colors_png_snapshot/agents_plan_handoff_status_colors_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________ test_runner_slot_wait_rows_and_queue_detail_png_snapshot ___________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=136, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb281fc3bd0>

    async def test_runner_slot_wait_rows_and_queue_detail_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 12, 12, 3, 0))
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 10)
        patch_startup_loaders(monkeypatch, agents=runner_slot_wait_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            for _ in range(len(page.app._agents) + 1):
                selected = (
                    page.app._agents[page.app.current_idx]
                    if 0 <= page.app.current_idx < len(page.app._agents)
                    else None
                )
                if selected is not None and selected.agent_name == "global-cap":
                    break
                await page.press("j")
                await wait_for_visual_idle(page)
            selected = page.app._agents[page.app.current_idx]
            assert selected.agent_name == "global-cap"
            assert selected.status == "QUEUED"
            assert selected.runner_slot_queue_position == 1
            assert selected.runner_slot_queue_size == 2
            assert_page_svg_contains(page, "drain-barrier")
            assert_page_svg_contains(page, "global-cap")
            assert_page_svg_contains(page, "dependency-wait")
            assert_page_svg_contains(page, "Queue:")
            assert_page_svg_contains(page, "of 2")
            assert_page_svg_contains(page, "at the front")
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            prompt_text = renderable_to_text(prompt.content) or ""
            assert "Queue: #1 of 2 · at the front" in prompt_text
            assert "QUEUE · 2 waiting · 0.0/10.0 capacity" in prompt_text
            info = page.app.query_one("#agent-info-panel", AgentInfoPanel)
            assert info._build_display_text().plain.startswith(
                "3  0.0/10.0 [0 running · 2 queued · 1 waiting]"
            )
>           ace_png_visual.assert_page_png(
                page,
                "agents_runner_slot_waits_120x40",
                title="ACE agents runner slot waits",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:180: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_runner_slot_waits_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x020\xcdIDA...\x00`\xf4\xe9\x0b\x1e\xf1\xe0\xf1\x86\x06\xee\x8c\x9a\xe0\xff\x07\x07\xc4bV\x13r\xc1\xe0\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_runner_slot_waits_120x40.png
E       Changed pixels: 2726/1520532 (0.179279%); materially changed pixels: 2722/1520532 (0.179016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_wait_rows_and_queue_detail_png_snapshot/agents_runner_slot_waits_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_wait_rows_and_queue_detail_png_snapshot/agents_runner_slot_waits_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_wait_rows_and_queue_detail_png_snapshot/agents_runner_slot_waits_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_wait_rows_and_queue_detail_png_snapshot/agents_runner_slot_waits_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agents_epic_phase_roadmap_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...sase_context.py', test_line=104, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060794a3f0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_epic_phase_roadmap0')

    async def test_agents_epic_phase_roadmap_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        relative_plan_path = Path("sase/repos/plans/202607/epic phase roadmap.md")
        plan_path = tmp_path / relative_plan_path
        plan_path.parent.mkdir(parents=True)
        plan_path.write_text(
            "---\n"
            "tier: epic\n"
            "title: Epic phase roadmap\n"
            "goal: Show every validated phase in a responsive roadmap\n"
            "phases:\n"
            "  - id: core\n"
            "    title: Planner and safety checks\n"
            "    depends_on: []\n"
            "    description: Establish the normalized phase model.\n"
            "    size: small\n"
            "  - id: render\n"
            "    title: Responsive phase renderer\n"
            "    depends_on: [core]\n"
            "    size: medium\n"
            "    model: codex/gpt-5.6-sol\n"
            "  - id: verify\n"
            "    title: Visual verification\n"
            "    depends_on: [core, render]\n"
            "    size: large\n"
            "---\n"
            "# Plan\n\n"
            "Implement and verify the roadmap.\n",
            encoding="utf-8",
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-epic-roadmap",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 7, 15, 10, 0, 0),
            raw_suffix="20260715100000",
            agent_name="visual.epic-roadmap",
            plan_path=relative_plan_path.as_posix(),
            sdd_plan_path=relative_plan_path.as_posix(),
            plan_committed=True,
            plan_action="epic",
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "3 phases")
            await wait_for_visual_idle(page)
    
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            metadata = renderable_to_text(panel.content) or ""
            for expected in (
                "Planner and safety checks",
                "small",
                "Responsive phase renderer",
                "medium",
                "no dependencies",
                "after core",
                "codex/gpt-5.6-sol",
                "Visual verification",
                "large",
                "after core, render",
            ):
                assert expected in metadata
    
            assert_page_svg_contains(page, "SASE CONTEXT")
            assert_page_svg_contains(page, "PLAN")
            assert_page_svg_contains(page, "epic")
            assert_page_svg_contains(page, "3 phases")
            assert_page_svg_contains(page, "Title:")
            assert_page_svg_contains(page, "Epic phase roadmap")
            await wait_for_svg_contains(page, "Visual verification")
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_epic_phase_roadmap_120x40",
                title="ACE agents epic phase roadmap",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:187: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_epic_phase_roadmap_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02>\x1eIDA...0\x00\x00\x00\x00\x00\x80\xa1\xa7\'xu\x05\xaf\xb7\xd4qg\xd4\x00\xff?\xfe\x07XL1\xc1\xecQ\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_epic_phase_roadmap_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_epic_phase_roadmap_png_snapshot/agents_epic_phase_roadmap_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_epic_phase_roadmap_png_snapshot/agents_epic_phase_roadmap_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_epic_phase_roadmap_png_snapshot/agents_epic_phase_roadmap_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_epic_phase_roadmap_png_snapshot/agents_epic_phase_roadmap_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_reserved_tribe_wait_row_png_snapshot ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=197, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb266556cf0>

    async def test_reserved_tribe_wait_row_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=reserved_tribe_wait_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "WAITING")
            assert_page_svg_contains(page, "!")
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            prompt_text = renderable_to_text(prompt.content) or ""
            assert "Wait: [tribes] @default ! (reserved - never resolves)" in prompt_text
            assert "(next launch)" not in prompt_text
>           ace_png_visual.assert_page_png(
                page,
                "agents_reserved_tribe_wait_120x40",
                title="ACE agents reserved tribe wait",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:216: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_reserved_tribe_wait_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x89\xf5...\x00\xc0\xdc\xb3\xafx\x0c\x16\x8f\xc7\xa3\xe3\xcev\x03\xfc\xff\x81{0\x96\xc1\x00\xd9\xee\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_reserved_tribe_wait_120x40.png
E       Changed pixels: 2746/1520532 (0.180595%); materially changed pixels: 2743/1520532 (0.180397%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_reserved_tribe_wait_row_png_snapshot/agents_reserved_tribe_wait_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_reserved_tribe_wait_row_png_snapshot/agents_reserved_tribe_wait_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_reserved_tribe_wait_row_png_snapshot/agents_reserved_tribe_wait_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_reserved_tribe_wait_row_png_snapshot/agents_reserved_tribe_wait_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agents_phase_bead_context_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...sase_context.py', test_line=194, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f062a15de60>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_phase_bead_context0')

    async def test_agents_phase_bead_context_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        relative_plan_path = Path("sase/repos/plans/202607/phase bead context lane.md")
        plan_path = tmp_path / relative_plan_path
        plan_path.parent.mkdir(parents=True)
        plan_path.write_text(
            "---\n"
            "tier: epic\n"
            "title: Phase bead SASE context lane\n"
            "goal: Keep the complete epic roadmap private to its owner.\n"
            "phases:\n"
            "  - id: model\n"
            "    title: Typed phase metadata\n"
            "    depends_on: []\n"
            "    size: small\n"
            "  - id: render\n"
            "    title: Responsive BEAD lane\n"
            "    depends_on: [model]\n"
            "    description: >-\n"
            "      Present the selected phase identity and provenance without exposing\n"
            "      the full epic roadmap.\n"
            "    size: medium\n"
            "---\n"
            "# Plan\n",
            encoding="utf-8",
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-phase-bead",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 7, 17, 9, 30, 0),
            raw_suffix="20260717093000",
            agent_name="sase-visual.2",
            agent_family_role="phase",
            epic_bead_id="sase-visual",
            phase_bead_id="sase-visual.2",
            epic_plan_ref=relative_plan_path.as_posix(),
            plan_path=relative_plan_path.as_posix(),
            sdd_plan_path=relative_plan_path.as_posix(),
            plan_committed=True,
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        phase_issue = Issue(
            id="sase-visual.2",
            title="Responsive BEAD lane",
            issue_type=IssueType.PHASE,
            parent_id="sase-visual",
            created_at="2026-07-03T13:00:00Z",
        )
        monkeypatch.setattr(
            "sase.ace.tui.models.agent_associated_plan._lookup_issue",
            lambda _agent, bead_id, **_kwargs: (
                phase_issue if bead_id == phase_issue.id else None
            ),
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "Phase Title:")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "SASE CONTEXT")
            assert_page_svg_contains(page, "BEAD")
            svg = page.export_svg(title="ACE phase BEAD context assertion")
            assert re.search(
                r"phase&#160;</text><text[^>]*>sase-visual\.2</text>",
                svg,
            )
            assert_page_svg_contains(page, "Phase Title:")
            assert_page_svg_contains(page, "Responsive BEAD lane")
            assert_page_svg_contains(page, "Description:")
            assert_page_svg_contains(page, "Size:")
            assert_page_svg_contains(page, "medium")
            assert_page_svg_contains(page, "Epic Plan:")
            assert_page_svg_contains(page, "Epic Title:")
            assert_page_svg_contains(page, "Created:")
            assert_page_svg_contains(page, "2026-07-03")
            assert_page_svg_contains(page, "Phase bead SASE context lane")
            assert "Bead:" not in svg
            assert "ID:" not in svg
            assert "▸ PLAN" not in svg
            assert "Typed phase metadata" not in svg
            assert "small" not in svg
            assert "large" not in svg
            assert "Keep the complete epic roadmap" not in svg
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_phase_bead_context_120x40",
                title="ACE agents phase BEAD context lane",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:290: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_phase_bead_context_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02$\x9bIDA...!\x84\x10B\x08!\x84\x0c?z\xf4+\xa8_\'\x10\xb8\xd3-\xc1\xff\x02\xc1_\x0b\xd2\xfam\xcf\xbd\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_phase_bead_context_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_phase_bead_context_png_snapshot/agents_phase_bead_context_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_phase_bead_context_png_snapshot/agents_phase_bead_context_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_phase_bead_context_png_snapshot/agents_phase_bead_context_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_phase_bead_context_png_snapshot/agents_phase_bead_context_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________________ test_agents_task_bead_notes_png_snapshot ___________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...sase_context.py', test_line=297, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0622a32360>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_task_bead_notes_pn0')

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
            assert "alice" in svg_plain
            assert "bob" in svg_plain
            assert "attribution readable" in svg_plain
    
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            metadata = renderable_to_text(panel.content) or ""
            assert "Size:" in metadata
            assert "Task Type:" in metadata
            assert "untyped" in metadata
            assert "Created:" in metadata
            assert "2026-07-03" in metadata
            assert "Epic Plan:" not in svg_plain
            assert "Epic Title:" not in svg_plain
    
            await wait_for_svg_contains(page, "Size:")
            await wait_for_svg_contains(page, "Created:")
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_task_bead_notes_120x40",
                title="ACE agents task BEAD notes lane",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:377: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_task_bead_notes_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x026\xa3IDA...0\x00\x00\x00\x00\x00`\xf4\xe9\x8b\x1e=\xd1\xe3U\r\xdc\x994\xc1\xff\x01\x896[xr=\x19\x9d\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_task_bead_notes_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_runner_slot_queue_window_png_snapshot __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=223, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2641fa820>

    async def test_runner_slot_queue_window_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = runner_slot_queue_window_agents()
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 25, 12, 12, 0))
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 10)
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 9)
            await wait_for_visual_idle(page)
    
            for _ in range(len(rows) + 1):
                selected = (
                    page.app._agents[page.app.current_idx]
                    if 0 <= page.app.current_idx < len(page.app._agents)
                    else None
                )
                if selected is not None and selected.agent_name == "queue-middle":
                    break
                await page.press("j")
                await wait_for_visual_idle(page)
            selected = page.app._agents[page.app.current_idx]
            assert selected.agent_name == "queue-middle"
            assert selected.runner_slot_queue_position == 6
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            prompt_text = renderable_to_text(prompt.content) or ""
            assert "5 ahead" in prompt_text
            assert "QUEUE · 9 waiting · 0.0/10.0 capacity" in prompt_text
            assert "c0" in prompt_text
            assert "p1" in prompt_text
            assert "… +2 more" in prompt_text
            assert "… +1 more" in prompt_text
>           ace_png_visual.assert_page_png(
                page,
                "agents_runner_slot_queue_window_120x40",
                title="ACE agents runner slot queue window",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:260: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_runner_slot_queue_window_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x03Z\x04IDA...00\x00\xe8\x7f\xda\x82\x9fd\xf0\xf3\x9a:\xee\x8c\x1a\xe0\xff\x07.(\xa1\x98\xb4\xb8\x08\t\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_runner_slot_queue_window_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_runner_slot_queue_window_png_snapshot/agents_runner_slot_queue_window_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________ test_agents_phase_family_bead_and_plan_context_png_snapshot __________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...sase_context.py', test_line=384, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0613c6d630>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_phase_family_bead_0')

    async def test_agents_phase_family_bead_and_plan_context_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        epic_ref = Path("p/epic.md")
        epic_path = tmp_path / epic_ref
        epic_path.parent.mkdir(parents=True)
        epic_path.write_text(
            "---\n"
            "tier: epic\n"
            "title: Parent epic\n"
            "goal: Coordinate provider updates without leaking the full roadmap.\n"
            "phases:\n"
            "  - id: snapshot\n"
            "    title: Provider update snapshot\n"
            "    depends_on: []\n"
            "    description: Provider context.\n"
            "    size: small\n"
            "  - id: render\n"
            "    title: Render update awareness\n"
            "    depends_on: [snapshot]\n"
            "    size: medium\n"
            "---\n"
            "# Plan\n",
            encoding="utf-8",
        )
        authored_ref = Path("p/phase.md")
        authored_path = tmp_path / authored_ref
        authored_path.write_text(
            "---\n"
            "tier: tale\n"
            "title: Phase plan\n"
            "goal: Approved handoff beside the parent.\n"
            "size: small\n"
            "---\n"
            "# Plan\n",
            encoding="utf-8",
        )
        root = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-phase-plan-family",
            project_file="/workspace/sase/visual_project.sase",
            status="TALE APPROVED",
            start_time=datetime(2026, 7, 20, 10, 30, 0),
            stop_time=datetime(2026, 7, 20, 10, 36, 0),
            raw_suffix="20260720103000",
            role_suffix="--plan",
            agent_name="sase-83.1--plan",
            agent_family="sase-83.1",
            agent_family_role="root",
            plan_chain_root=True,
            epic_bead_id="sase-83",
            phase_bead_id="sase-83.1",
            epic_plan_ref=epic_ref.as_posix(),
            archived_plan_path=authored_ref.as_posix(),
            sdd_plan_path=authored_ref.as_posix(),
            plan_committed=True,
            plan_action="tale",
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        coder = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-phase-plan-family-code",
            project_file=root.project_file,
            status="DONE",
            start_time=datetime(2026, 7, 20, 10, 37, 0),
            stop_time=datetime(2026, 7, 20, 10, 45, 0),
            raw_suffix="20260720103700",
            parent_timestamp=root.raw_suffix,
            role_suffix="--code",
            agent_name="sase-83.1--code",
            agent_family="sase-83.1",
            agent_family_role="code",
            epic_bead_id="sase-83",
            phase_bead_id="sase-83.1",
            epic_plan_ref=epic_ref.as_posix(),
            archived_plan_path=authored_ref.as_posix(),
            sdd_plan_path=authored_ref.as_posix(),
            plan_committed=True,
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        phase_issue = Issue(
            id="sase-83.1",
            title="Provider update snapshot",
            issue_type=IssueType.PHASE,
            parent_id="sase-83",
            created_at="2026-07-03T13:00:00Z",
        )
        monkeypatch.setattr(
            "sase.ace.tui.models.agent_associated_plan._lookup_issue",
            lambda _agent, bead_id, **_kwargs: (
                phase_issue if bead_id == phase_issue.id else None
            ),
        )
        patch_startup_loaders(monkeypatch, agents=[root, coder])
    
        async with AcePage(query='"visual-phase-plan-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await page.press("p")
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _state: "Phase plan" in (renderable_to_text(panel.content) or "")
            )
            await page.press("Z")
>           await page.expect_modal("ZoomPanelModal")

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:496: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:439: in expect_modal
    await self.expect_state("modal", name, timeout=timeout)
src/sase/ace/testing/ace_page.py:428: in expect_state
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.expect_state.<locals>.predicate at 0x7f060779b5e0>

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: expect_state('modal', 'ZoomPanelModal') timed out after 5.0s — last value was 'AgentViewModal'

src/sase/ace/testing/wait.py:54: AssertionError
_________________ test_weighted_runner_capacity_png_snapshots __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=267, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb26532f620>

    async def test_weighted_runner_capacity_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = weighted_runner_capacity_agents()
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 30, 12, 8, 0))
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 3)
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "weighted-family")
            assert_page_svg_contains(page, "default-capacity")
            assert_page_svg_contains(page, "light-queue")
            assert_page_svg_contains(page, "heavy-queue")
            assert_page_svg_styled_text_contains(page, "3.0/3.0")
            assert_page_svg_styled_text_contains(page, "w2")
            assert_page_svg_styled_text_contains(page, "w0.25")
>           ace_png_visual.assert_page_png(
                page,
                "agents_weighted_runner_capacity_120x40",
                title="ACE agents weighted runner capacity",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:289: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_weighted_runner_capacity_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\xe0;IDA...8!\x84\x10B\x08!\x84\xe4\x1fg\xf5\xabG\xbf\x8e q\xa7_\x81\x7f\x07\x86B\x9d_\xe1\xcbf\xf8\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_weighted_runner_capacity_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_weighted_runner_capacity_png_snapshots/agents_weighted_runner_capacity_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_weighted_runner_capacity_png_snapshots/agents_weighted_runner_capacity_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_weighted_runner_capacity_png_snapshots/agents_weighted_runner_capacity_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_weighted_runner_capacity_png_snapshots/agents_weighted_runner_capacity_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________________ test_capacity_budget_accent_png_snapshot ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=336, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb26532dcc0>

    async def test_capacity_budget_accent_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Cover a quiet c1, a gold c100 bypass admit, and the red global header."""
        rows = capacity_budget_accent_agents()
        pin_agents_visual_now(monkeypatch, datetime(2026, 8, 3, 9, 5, 0))
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 1)
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await wait_for_visual_idle(page)
    
            info_panel = page.app.query_one(AgentInfoPanel)
            assert info_panel._runner_capacity_style() == "bold #FF5F5F"
    
            assert_page_svg_styled_text_contains(page, "c1")
            assert_page_svg_styled_text_contains(page, "c100")
>           ace_png_visual.assert_page_png(
                page,
                "agents_capacity_budget_accent_120x40",
                title="ACE agents capacity budget accent",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:357: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_capacity_budget_accent_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x0f,IDA...84\x10B\xc8\xd0\xe3\x8c~\x85\xf5\xeb\x10\x16\xee\xf4J\xf0\xff\x01d-X\xb1\xf7\xba\x17\x94\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_capacity_budget_accent_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_capacity_budget_accent_png_snapshot/agents_capacity_budget_accent_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_capacity_budget_accent_png_snapshot/agents_capacity_budget_accent_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_capacity_budget_accent_png_snapshot/agents_capacity_budget_accent_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_capacity_budget_accent_png_snapshot/agents_capacity_budget_accent_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________ test_agents_partially_streamed_context_lanes_png_snapshot ___________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...sase_context.py', test_line=535, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f063048a3d0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_partially_streamed0')

    async def test_agents_partially_streamed_context_lanes_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        """Mid-stream SASE CONTEXT marks unresolved lanes (bead sase-l6.4).
    
        Lanes resolve cheapest-first and publish as they land, so the section is
        routinely on screen while the store-backed lanes are still resolving.
        Holding ``memory`` and ``skills`` back for the whole capture makes that
        transient state a stable frame: the enrichment worker still runs to
        completion (so the page reaches visual idle) but never marks those two
        lanes ready, which is exactly what the renderer sees between two
        streamed publishes.
        """
        workspace = tmp_path / "sase_42"
        relative_plan_path = Path("sase/repos/plans/202608/streaming context lanes.md")
        plan_path = workspace / relative_plan_path
        plan_path.parent.mkdir(parents=True)
        plan_path.write_text(
            "---\n"
            "tier: tale\n"
            "title: Streaming SASE context lanes\n"
            "goal: Render each context lane as soon as it resolves.\n"
            "size: medium\n"
            "---\n"
            "# Plan\n",
            encoding="utf-8",
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-streaming-lanes",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 8, 13, 18, 15, 0),
            raw_suffix="20260813181500",
            agent_name="visual.streaming-lanes",
            plan_path=relative_plan_path.as_posix(),
            sdd_plan_path=relative_plan_path.as_posix(),
            plan_committed=True,
            plan_action="tale",
            workspace_dir=str(workspace),
            llm_provider="codex",
            model="gpt-5",
            step_output={
                "meta_commits": [
                    {
                        "message": "feat(ace): stream SASE CONTEXT lanes",
                        "sha": "1234567890abcdef",
                        "cwd": str(workspace),
                    }
                ],
            },
        )
    
        withheld: frozenset[DetailContextLane] = frozenset({"memory", "skills"})
    
        def _refresh_without_store_lanes(
            panel: AgentPromptPanel,
            row: Agent,
        ) -> frozenset[DetailContextLane]:
            return frozenset(should_refresh_detail_header_summary(panel, row) - withheld)
    
        monkeypatch.setattr(
            AgentPromptPanel,
            "_should_refresh_detail_header_summary",
            _refresh_without_store_lanes,
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _state: "resolving" in (renderable_to_text(panel.content) or "")
            )
            await wait_for_visual_idle(page)
    
            metadata = renderable_to_text(panel.content) or ""
            assert "SASE CONTEXT" in metadata
            assert "Streaming SASE context lanes" in metadata
            for resolved_label in ("PLAN", "ARTIFACTS"):
                assert f"▸ {resolved_label} · resolving…\n" not in metadata
            for pending_label in ("MEMORY", "SKILLS"):
                assert f"▸ {pending_label} · resolving…\n" in metadata
            assert metadata.index("▸ ARTIFACTS") < metadata.index("▸ MEMORY")
            assert metadata.index("▸ MEMORY") < metadata.index("▸ SKILLS")
            assert_page_svg_contains(page, "SASE CONTEXT")
            assert_page_svg_contains(page, "resolving")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_partially_streamed_context_lanes_120x40",
                title="ACE agents partially streamed SASE context lanes",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:628: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_partially_streamed_context_lanes_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x1f\xb9...0B\x08!\x84\x10B\x08\x19z\x9c\xd5\xaf\xa0~\x1dF\xe0N\xaf\x04\xff\x1f\x92\x0eXG\x9c\x0f!}\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_partially_streamed_context_lanes_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_partially_streamed_context_lanes_png_snapshot/agents_partially_streamed_context_lanes_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_partially_streamed_context_lanes_png_snapshot/agents_partially_streamed_context_lanes_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_partially_streamed_context_lanes_png_snapshot/agents_partially_streamed_context_lanes_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_partially_streamed_context_lanes_png_snapshot/agents_partially_streamed_context_lanes_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________ test_agent_output_variables_multi_agent_png_snapshot _____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=380, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2641fac80>

    async def test_agent_output_variables_multi_agent_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 8, 9, 9, 0))
        patch_startup_loaders(monkeypatch, agents=output_variable_family_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "OUTPUT VARIABLES")
            assert_page_svg_contains(page, "· 4")
            assert_page_svg_contains(page, "build_report")
>           ace_png_visual.assert_page_png(
                page,
                "agents_output_variables_multi_agent_120x40",
                title="ACE agents output variables multi agent",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:397: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_output_variables_multi_agent_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x16\xf4...x08!\x84\x10B\x88\xb1\xc7\xa1\xe8\xd5\x1f\xbd^%qg\xd2\x06\xff\x07\x070\x14F\xf9\xeak\x8b\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_output_variables_multi_agent_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_output_variables_multi_agent_png_snapshot/agents_output_variables_multi_agent_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_output_variables_multi_agent_png_snapshot/agents_output_variables_multi_agent_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_output_variables_multi_agent_png_snapshot/agents_output_variables_multi_agent_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agent_output_variables_multi_agent_png_snapshot/agents_output_variables_multi_agent_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
____________________ test_agents_selected_row_png_snapshot _____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...shots_agents.py', test_line=404, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d3ef20>

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

tests/ace/tui/visual/test_ace_png_snapshots_agents.py:424: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_selected_row_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf5\x0c...\x08!\x84\x10B\x08!F\x1f\'\xe2\xd7@\xfcz\x8d\xc2\x9dI\x1b\xfc;\xa6\xde"\x12\x97\xe8\x0f.\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_selected_row_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents.py__test_agents_selected_row_png_snapshot/agents_selected_row_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
____________ test_agents_slow_tool_calls_fold_levels_png_snapshots _____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_slow_tools.py', test_line=268, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0607dee0b0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_slow_tool_calls_fo0')

    async def test_agents_slow_tool_calls_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        monkeypatch.setattr(_agent_display_header, "DateTime", _FixedDateTime)
        monkeypatch.setattr(
            _agent_context_common,
            "get_timezone",
            lambda: ZoneInfo("UTC"),
        )
        pin_agents_visual_now(monkeypatch, _NOW.replace(tzinfo=None))
        tools_cache_module.tools_cache.clear()
        artifacts_dir = tmp_path / "visual-slow-tools"
        _populate_slow_tool_calls(artifacts_dir)
        agent = _slow_tool_agent(artifacts_dir)
        # This snapshot covers fold rendering, not asynchronous artifact discovery.
        # Prime the shared mtime cache so the metadata header and tools-availability
        # indicator start from the same source state under full-suite contention.
        assert build_slow_tool_sources(agent)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"slow-tools"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await page.press("h")
            await wait_for_visual_idle(page)
            await page.press("l")
    
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await wait_for_state(
                page,
                lambda: (
                    (summary := get_cached_detail_header_summary(panel, agent)) is not None
                    and bool(summary.slow_tool_sources)
                ),
                description="slow-tool detail-header summary",
            )
            await page.press("p", "n")
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
            await _focus_slow_tool_section(page)
            await wait_for_state(
                page,
                lambda: _slow_tool_section_ready(panel),
                description="active slow-tool section",
            )
            await wait_for_state(
                page,
                lambda: _rendered_tools_footer_selected(page),
                description="selected tools footer",
            )
            await wait_for_visual_idle(page, timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT)
    
            assert page.app.panel_fold_level is FoldLevel.COLLAPSED
>           ace_png_visual.assert_page_png(
                page,
                "agents_slow_tool_calls_level_1_120x40",
                title="ACE agents slow tool calls level 1",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:324: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_slow_tool_calls_level_1_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb7\xce...\x00\x00\x00\xcc<{\x8b\xaf\x81\xe2\xeb\xb1\x98\xb8\xb3\xd5\x02\xff\x7f\x86_\'PG?\xb3\xe7\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_slow_tool_calls_level_1_120x40.png
E       Changed pixels: 3156/1520532 (0.207559%); materially changed pixels: 3150/1520532 (0.207164%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_slow_tools.py__test_agents_slow_tool_calls_fold_levels_png_snapshots/agents_slow_tool_calls_level_1_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_slow_tools.py__test_agents_slow_tool_calls_fold_levels_png_snapshots/agents_slow_tool_calls_level_1_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_slow_tools.py__test_agents_slow_tool_calls_fold_levels_png_snapshots/agents_slow_tool_calls_level_1_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_slow_tools.py__test_agents_slow_tool_calls_fold_levels_png_snapshots/agents_slow_tool_calls_level_1_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________ test_agents_artifact_file_type_icons_png_snapshot _______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_artifacts.py', test_line=73, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25d9d5cc0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_agents_artifact_file_type0')

    async def test_agents_artifact_file_type_icons_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        agent = _artifact_icon_agent(tmp_path, monkeypatch)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "Files:")
            for icon in ("▨", "▶", "▤", "•"):
                assert_page_svg_contains(page, icon)
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_artifact_type_icons_120x40",
                title="ACE agents artifact-file type icons",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_artifacts.py:92: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_artifact_type_icons_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xc1\xd0...3\x00\x00\x00\x00\x00\x00\xdb\xe7;\xd6"V\x9a=\xdc\xf9\xd7\x86\x1f\xcd\x9fh*0\x80\x12\x98\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_artifact_type_icons_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_artifacts.py__test_agents_artifact_file_type_icons_png_snapshot/agents_artifact_type_icons_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_artifacts.py__test_agents_artifact_file_type_icons_png_snapshot/agents_artifact_type_icons_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_artifacts.py__test_agents_artifact_file_type_icons_png_snapshot/agents_artifact_type_icons_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_artifacts.py__test_agents_artifact_file_type_icons_png_snapshot/agents_artifact_type_icons_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agents_auto_approve_icons_png_snapshot __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...auto_approve.py', test_line=143, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d2d780>

    async def test_agents_auto_approve_icons_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _auto_approve_agents()
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_svg_contains(page, "⚡T ")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "⚡ ")
            assert_page_svg_contains(page, "⚡T ")
            assert_page_svg_contains(page, "⚡E ")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_auto_approve_icons_120x40",
                title="ACE agents auto-approve icons",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py:162: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_auto_approve_icons_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xac\xa7...0\x00\x00\x00`\xf6\xd9[<\xfa\x8b\xc7c\xd1qg\xab\x01\xfe\x7f\xb1\xac9\x87\xce\x80\xd3\x04\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_auto_approve_icons_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_icons_png_snapshot/agents_auto_approve_icons_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_icons_png_snapshot/agents_auto_approve_icons_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_icons_png_snapshot/agents_auto_approve_icons_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_icons_png_snapshot/agents_auto_approve_icons_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________ test_agents_auto_approve_workflow_child_alignment_png_snapshot ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...auto_approve.py', test_line=169, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb281b31710>

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

tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py:211: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_auto_approve_workflow_child_alignment_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xa4\xb3...00\x00\x00\x00\'\x9e\x03\xc5\xcf@\xf1\xf3x\x0c\xdc\xd9j\x82\xff\x1f\xf3iI\x81\tC\xc4\xfa\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_auto_approve_workflow_child_alignment_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_workflow_child_alignment_png_snapshot/agents_auto_approve_workflow_child_alignment_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_______________ test_agents_auto_approve_metadata_png_snapshots ________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...auto_approve.py', test_line=218, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e661cc0>

    async def test_agents_auto_approve_metadata_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _auto_approve_agents()
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
    
            for idx, (token, snapshot_name, title) in enumerate(
                (
                    ("⚡ PLAN", "agents_auto_approve_metadata_plan_120x40", "PLAN"),
                    ("⚡ TALE", "agents_auto_approve_metadata_tale_120x40", "TALE"),
                    ("⚡ EPIC", "agents_auto_approve_metadata_epic_120x40", "EPIC"),
                )
            ):
                if idx:
                    await page.press("j")
                await wait_for_state(
                    page,
                    lambda idx=idx: page.app.current_idx == idx,
                    description=f"selected auto-approve agent index {idx}",
                )
                await wait_for_svg_contains(page, "Auto:")
                await wait_for_visual_idle(page)
                assert_page_svg_contains(page, "Auto:")
                assert_page_svg_styled_text_contains(page, token)
    
>               ace_png_visual.assert_page_png(
                    page,
                    snapshot_name,
                    title=f"ACE agents auto-approve metadata {title}",
                )

tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py:250: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_auto_approve_metadata_plan_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xae\xac...00\x00\x00\x00\x000\xf7\xec+\x1e\x03\xc5\xe3\xb1\xe8\xb8\xb3\xd5\x00\xff??\x1d(=Q\xedS\n\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_auto_approve_metadata_plan_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_metadata_png_snapshots/agents_auto_approve_metadata_plan_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_metadata_png_snapshots/agents_auto_approve_metadata_plan_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_metadata_png_snapshots/agents_auto_approve_metadata_plan_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_metadata_png_snapshots/agents_auto_approve_metadata_plan_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________ test_agents_auto_approve_xprompts_metadata_png_snapshot ____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...auto_approve.py', test_line=289, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb291f4b1c0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_agents_auto_approve_xprom0')

    async def test_agents_auto_approve_xprompts_metadata_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        agent = _auto_approve_xprompts_agent(tmp_path / "xprompt-artifacts")
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "Xprompts:")
            await wait_for_visual_idle(page)
    
            svg = page.export_svg(title="ACE auto/xprompts metadata")
            svg_plain = svg.replace("&#160;", " ")
            assert "Auto:" in svg_plain
            assert "Model:" in svg_plain
            assert "Xprompts:" in svg_plain
            assert (
                svg_plain.index("Auto:")
                < svg_plain.index("Model:")
                < svg_plain.index("Xprompts:")
            )
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_auto_approve_xprompts_metadata_120x40",
                title="ACE agents auto-approve xprompts metadata",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py:316: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_auto_approve_xprompts_metadata_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x90\x86...\x00\x00\x00\xb3\xcf\xde\xe2\xd1_<\x1e\x8b\x8e;[\r\xf0\xff\x03\x06\xed\xe4\x05\xa09\x83^\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_auto_approve_xprompts_metadata_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_xprompts_metadata_png_snapshot/agents_auto_approve_xprompts_metadata_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_xprompts_metadata_png_snapshot/agents_auto_approve_xprompts_metadata_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_xprompts_metadata_png_snapshot/agents_auto_approve_xprompts_metadata_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_auto_approve.py__test_agents_auto_approve_xprompts_metadata_png_snapshot/agents_auto_approve_xprompts_metadata_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________________ test_epic_clan_panel_png_snapshots ______________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_clan_panel.py', test_line=148, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d549b00>

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
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_120x40",
                title="ACE epic clan panel fold level 1",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:177: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_epic_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\\XIDATx...00\x00\x00\x00\x00\x00\x00\x00\xf4<\xdb\xa3W{\xf4z^\x1dw&\r\xf0\xff\x01\xe039J/\xa4\xfd:\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_png_snapshots/agents_clan_panel_epic_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________________ test_agents_tools_panel_populated_png_snapshot ________________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pshots_tools.py', test_line=365, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa3d5100280>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw6/test_agents_tools_panel_popula0')

    async def test_agents_tools_panel_populated_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        _pin_tools_panel_now(monkeypatch)
        _clear_tools_cache()
    
        artifacts_dir = tmp_path / "ace-run" / "20260509100000"
        _populate_tool_calls(artifacts_dir)
        agent = _tools_agent(artifacts_dir)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            panel = await _open_tools_panel(page)
            assert panel._last_entries is not None
            assert {entry.runtime for entry in panel._last_entries} == {"codex"}
            assert {entry.source for entry in panel._last_entries} == {"stream"}
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_tools_panel_populated_120x40",
                title="ACE agents tools panel populated with Codex rows",
            )

tests/ace/tui/visual/test_ace_png_snapshots_tools.py:384: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_tools_panel_populated_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\'\xe2ID...\x00\x00\x00\x00`\xec9\x12=\xfa\xa3\xc7+\x1a\xb83i\x82\xff\x0f\xcb+\x0e\x8cI\x1f\x9c\xa6\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_tools_panel_populated_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_populated_png_snapshot/agents_tools_panel_populated_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_populated_png_snapshot/agents_tools_panel_populated_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_populated_png_snapshot/agents_tools_panel_populated_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_populated_png_snapshot/agents_tools_panel_populated_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________ test_agents_waiting_single_bead_labels_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_waiting.py', test_line=130, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0607fc34d0>

    async def test_agents_waiting_single_bead_labels_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _seed_single_bead_wait_status_cache()
        try:
            patch_startup_loaders(
                monkeypatch,
                agents=_single_bead_wait_agents(),
            )
    
            async with AcePage(query='"single-bead"', patches=patches()) as page:
                await wait_for_startup(page)
                await page.press("shift+tab")
                await page.expect_state("tab", "agents")
                await page.expect_state("agent_count", 4)
                await wait_for_svg_contains(page, "sase-yz")
                await wait_for_visual_idle(page)
    
                assert_page_svg_styled_text_contains(page, "WAITING ◐ sase-yz")
                assert_page_svg_styled_text_contains(
                    page,
                    "WAITING ○ sase-alpha.pipeline.review.12",
                )
                assert_page_svg_styled_text_contains(page, "WAITING ▶1 ◐1")
                assert_page_svg_contains(page, "Wait:")
                assert_page_svg_contains(page, "[beads]")
                assert_page_svg_contains(page, "sase-yz")
>               ace_png_visual.assert_page_png(
                    page,
                    "agents_waiting_single_bead_labels_120x40",
                    title="ACE agents single bead wait labels",
                )

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:158: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_waiting_single_bead_labels_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02^\xffIDA...x00\x00\x00\x00\x00@\xf1\xe9\x0c~:\x82\x9f\xb7\xd5qg\xd4\x00\xff?\x96IB?\xbe\xba\xd1\xe4\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_waiting_single_bead_labels_120x40.png
E       Changed pixels: 2726/1520532 (0.179279%); materially changed pixels: 2722/1520532 (0.179016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_png_snapshot/agents_waiting_single_bead_labels_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_png_snapshot/agents_waiting_single_bead_labels_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_png_snapshot/agents_waiting_single_bead_labels_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_png_snapshot/agents_waiting_single_bead_labels_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_epic_clan_panel_hint_mode_png_snapshot __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_clan_panel.py', test_line=216, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d54b2a0>

    async def test_epic_clan_panel_hint_mode_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """``v`` must annotate the clan document in place, not replace it."""
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
    
            await page.press("v")
            await page.wait_for(lambda _state: bool(page.app._hint_mappings))
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "CLAN")
            assert_page_svg_contains(page, "[1]")
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_hints_120x40",
                title="ACE epic clan panel in hint mode",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:242: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_epic_hints_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02L\xbaIDA...0\x00\x00\x00\x00\x00\x00\x86\x9fC\xd1Ow\xf4\xb3U\x03w&M\xf0\xff\x03\xef\x9d[5\xed\xf5a9\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_hints_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_hint_mode_png_snapshot/agents_clan_panel_epic_hints_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_hint_mode_png_snapshot/agents_clan_panel_epic_hints_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_hint_mode_png_snapshot/agents_clan_panel_epic_hints_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_hint_mode_png_snapshot/agents_clan_panel_epic_hints_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_agents_tools_panel_detail_level_png_snapshots[1-agents_tools_panel_expanded_120x40-ACE agents tools panel expanded detail] _
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pshots_tools.py', test_line=391, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa3d6fe2350>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw6/test_agents_tools_panel_detail0')
detail_level = <ToolDetailLevel.EXPANDED: 1>
snapshot_name = 'agents_tools_panel_expanded_120x40'
title = 'ACE agents tools panel expanded detail'

    @pytest.mark.parametrize(
        ("detail_level", "snapshot_name", "title"),
        [
            (
                ToolDetailLevel.EXPANDED,
                "agents_tools_panel_expanded_120x40",
                "ACE agents tools panel expanded detail",
            ),
            (
                ToolDetailLevel.FULL,
                "agents_tools_panel_full_120x40",
                "ACE agents tools panel full detail",
            ),
        ],
    )
    async def test_agents_tools_panel_detail_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        detail_level: ToolDetailLevel,
        snapshot_name: str,
        title: str,
    ) -> None:
        _pin_tools_panel_now(monkeypatch)
        _clear_tools_cache()
    
        artifacts_dir = tmp_path / "ace-run" / "20260509100000"
        _populate_expanded_tool_calls(artifacts_dir)
        agent = _tools_agent(artifacts_dir)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            panel = await _open_tools_panel(page)
            assert panel.set_detail_level(detail_level) is True
            page.app._refresh_agent_footer_bindings_only()
            page.app.refresh(layout=True)
            await page.app.wait_for_refresh()
            if detail_level is ToolDetailLevel.FULL:
                tools_scroll = page.app.query_one("#agent-tools-scroll")
                # A worker-completion repaint can race this explicit detail-level
                # change and leave the Static holding the worker's older render.
                # Rebuild once from the now-settled cached rows so Rich wrapping
                # and the proportional scrollbar use the requested level.
                panel._rerender_cached_tools()
            await wait_for_visual_idle(page)
            if detail_level is ToolDetailLevel.FULL:
                # The visible text is byte-identical at both measurements, but
                # Textual occasionally retains three extra off-screen wrap rows
                # under CPU starvation, moving only the proportional thumb. Pin
                # that derived test-only geometry to the canonical full-detail
                # measurement without changing the panel content or golden.
                canonical_size = Size(tools_scroll.virtual_size.width, 79)
                tools_scroll.set_reactive(Widget.virtual_size, canonical_size)
                tools_scroll._scroll_update(canonical_size)
                assert tools_scroll.virtual_size.height == 79
                mark_current_visual_frame_converged(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "compact tools") in footer._last_layout_inputs[0]
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=title,
            )

tests/ace/tui/visual/test_ace_png_snapshots_tools.py:452: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_tools_panel_expanded_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x0252IDATx\...x00\x000\xf2\x1c\x88\x1e\xbd\xd1\xe3%M\xdc\x99\xb4\xc0\xff\x06\x1f\xd9+\xed\xb0\x03\x165\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_tools_panel_expanded_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_1-agents_tools_panel_expanded_120x40-ACE_agents_tools_panel_expanded_detail/agents_tools_panel_expanded_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_1-agents_tools_panel_expanded_120x40-ACE_agents_tools_panel_expanded_detail/agents_tools_panel_expanded_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_1-agents_tools_panel_expanded_120x40-ACE_agents_tools_panel_expanded_detail/agents_tools_panel_expanded_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_1-agents_tools_panel_expanded_120x40-ACE_agents_tools_panel_expanded_detail/agents_tools_panel_expanded_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________ test_agents_waiting_single_bead_labels_narrow_png_snapshot __________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_waiting.py', test_line=167, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0607fc3b60>

    async def test_agents_waiting_single_bead_labels_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _seed_single_bead_wait_status_cache()
        try:
            patch_startup_loaders(
                monkeypatch,
                agents=_single_bead_wait_agents(),
            )
    
            async with AcePage(
                query='"single-bead"',
                patches=patches(),
                size=(90, 32),
            ) as page:
                await wait_for_startup(page)
                await page.press("shift+tab")
                await page.expect_state("tab", "agents")
                await page.expect_state("agent_count", 4)
                await page.press("j", "j")
                await wait_for_svg_contains(page, "sase-alpha.pipeline.review.12")
                await wait_for_visual_idle(page)
    
                assert_page_svg_styled_text_contains(page, "WAITING ◐ sase-yz")
                assert_page_svg_styled_text_contains(
                    page,
                    "WAITING ○ sase-alpha.pipeline.review.12",
                )
                assert_page_svg_styled_text_contains(page, "WAITING ▶1 ◐1")
                assert_page_svg_contains(page, "sase-alpha.pipeline.review.12")
>               ace_png_visual.assert_page_png(
                    page,
                    "agents_waiting_single_bead_labels_90x32",
                    title="ACE agents single bead wait labels narrow",
                )

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_waiting_single_bead_labels_90x32'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x03?\x08\x06\x00\x00\x00\xec\xbe\xc6\xb3\x00\x01\xb7\xedID...x00\x00\x00\x00\xa06\xd2\x0c\xb6j$\xcb`\xd4\xe7_p\x01\xa2\xff\x1fw\xa8h/\xee\xf6\xca\xc3\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_waiting_single_bead_labels_90x32.png
E       Changed pixels: 1470/927396 (0.158508%); materially changed pixels: 1467/927396 (0.158185%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_narrow_png_snapshot/agents_waiting_single_bead_labels_90x32/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_narrow_png_snapshot/agents_waiting_single_bead_labels_90x32/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_narrow_png_snapshot/agents_waiting_single_bead_labels_90x32/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_single_bead_labels_narrow_png_snapshot/agents_waiting_single_bead_labels_90x32/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_agents_tools_panel_detail_level_png_snapshots[2-agents_tools_panel_full_120x40-ACE agents tools panel full detail] _
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pshots_tools.py', test_line=391, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa3da50b7e0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw6/test_agents_tools_panel_detail1')
detail_level = <ToolDetailLevel.FULL: 2>
snapshot_name = 'agents_tools_panel_full_120x40'
title = 'ACE agents tools panel full detail'

    @pytest.mark.parametrize(
        ("detail_level", "snapshot_name", "title"),
        [
            (
                ToolDetailLevel.EXPANDED,
                "agents_tools_panel_expanded_120x40",
                "ACE agents tools panel expanded detail",
            ),
            (
                ToolDetailLevel.FULL,
                "agents_tools_panel_full_120x40",
                "ACE agents tools panel full detail",
            ),
        ],
    )
    async def test_agents_tools_panel_detail_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        detail_level: ToolDetailLevel,
        snapshot_name: str,
        title: str,
    ) -> None:
        _pin_tools_panel_now(monkeypatch)
        _clear_tools_cache()
    
        artifacts_dir = tmp_path / "ace-run" / "20260509100000"
        _populate_expanded_tool_calls(artifacts_dir)
        agent = _tools_agent(artifacts_dir)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            panel = await _open_tools_panel(page)
            assert panel.set_detail_level(detail_level) is True
            page.app._refresh_agent_footer_bindings_only()
            page.app.refresh(layout=True)
            await page.app.wait_for_refresh()
            if detail_level is ToolDetailLevel.FULL:
                tools_scroll = page.app.query_one("#agent-tools-scroll")
                # A worker-completion repaint can race this explicit detail-level
                # change and leave the Static holding the worker's older render.
                # Rebuild once from the now-settled cached rows so Rich wrapping
                # and the proportional scrollbar use the requested level.
                panel._rerender_cached_tools()
            await wait_for_visual_idle(page)
            if detail_level is ToolDetailLevel.FULL:
                # The visible text is byte-identical at both measurements, but
                # Textual occasionally retains three extra off-screen wrap rows
                # under CPU starvation, moving only the proportional thumb. Pin
                # that derived test-only geometry to the canonical full-detail
                # measurement without changing the panel content or golden.
                canonical_size = Size(tools_scroll.virtual_size.width, 79)
                tools_scroll.set_reactive(Widget.virtual_size, canonical_size)
                tools_scroll._scroll_update(canonical_size)
                assert tools_scroll.virtual_size.height == 79
                mark_current_visual_frame_converged(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "compact tools") in footer._last_layout_inputs[0]
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=title,
            )

tests/ace/tui/visual/test_ace_png_snapshots_tools.py:452: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_tools_panel_full_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02+\xbfIDA...00\x00\x00\x18~\xf6G\x8f\xee\xe8\xf1\x8a\x06\xeeL\x9a\xe0\x7f\x01g\xfa\x10\xa3\xb4\x9fxo\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_tools_panel_full_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_2-agents_tools_panel_full_120x40-ACE_agents_tools_panel_full_detail/agents_tools_panel_full_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_2-agents_tools_panel_full_120x40-ACE_agents_tools_panel_full_detail/agents_tools_panel_full_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_2-agents_tools_panel_full_120x40-ACE_agents_tools_panel_full_detail/agents_tools_panel_full_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_tools.py__test_agents_tools_panel_detail_level_png_snapshots_2-agents_tools_panel_full_120x40-ACE_agents_tools_panel_full_detail/agents_tools_panel_full_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________ test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot __________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_clan_panel.py', test_line=249, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24f908e50>

    async def test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """``v`` marks logical plan and archived prompt rows as whole tokens."""
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 12, 15, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=decorate_clan_panel_sections(
                epic_clan_agents(clan_summary=_EPIC_CLAN_SUMMARY_WITH_PROMPT_HINTS)
            ),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            await page.press("v")
            await page.wait_for(lambda _state: len(page.app._hint_mappings) >= 2)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "[1]")
            assert_page_svg_contains(page, "plan:202608/")
            assert_page_svg_contains(page, "hints.md")
            assert_page_svg_contains(page, "[2]")
            assert_page_svg_contains(page, "prompts/202608/")
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_epic_logical_prompt_hints_120x40",
                title="ACE epic clan panel logical and prompt hint mode",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:278: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_epic_logical_prompt_hints_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x11\x04...\x00\x00\x00\x00\xa3\x8f\xc3\xd1\xab/z\xed\xd0\xc4\x9dI\x0b\xfc\x7f\xf1j\xc2Vi\n\xe1\xff\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_clan_panel_epic_logical_prompt_hints_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot/agents_clan_panel_epic_logical_prompt_hints_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot/agents_clan_panel_epic_logical_prompt_hints_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot/agents_clan_panel_epic_logical_prompt_hints_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot/agents_clan_panel_epic_logical_prompt_hints_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________ test_agents_waiting_missing_target_row_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_waiting.py', test_line=207, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0607fc3d20>

    async def test_agents_waiting_missing_target_row_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _seed_wait_bead_status_cache()
        try:
            patch_startup_loaders(
                monkeypatch,
                agents=waiting_unknown_agents(),
            )
    
            async with AcePage(query='"wait-unknown"', patches=patches()) as page:
                await wait_for_startup(page)
                await page.press("shift+tab")
                await page.expect_state("tab", "agents")
                await page.expect_state("agent_count", 4)
                await wait_for_svg_contains(page, "wait-unknown")
                await wait_for_visual_idle(page)
    
                assert_page_svg_styled_text_contains(page, "WAITING ✗1 ▶1 ◐1 ✓1 ●1 ?1 ○1")
                assert_page_svg_styled_text_contains(page, "?1 ○1")
                assert_page_svg_styled_text_contains(page, "▶1")
                assert_page_svg_styled_text_contains(page, "◐1")
                assert_page_svg_contains(page, "Wait:")
                assert_page_svg_contains(page, "[agents]")
                assert_page_svg_contains(page, "[beads]")
                assert_page_svg_contains(page, "coder")
                assert_page_svg_contains(page, "builder")
                assert_page_svg_contains(page, "reviewer")
                assert_page_svg_contains(page, "✓")
                assert_page_svg_contains(page, "▶")
                assert_page_svg_contains(page, "✗")
                assert_page_svg_contains(page, "?")
>               ace_png_visual.assert_page_png(
                    page,
                    "agents_waiting_missing_target_row_120x40",
                    title="ACE agents missing wait target row and detail",
                )

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:240: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_waiting_missing_target_row_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x020\x85IDA...x84\x10B\x08!\x84\x0c<\xba\xf4+\xa8_\x9f p\xa7W\x82\xff\x03\xd8\xbc\xb3\x99\xc2Z\xbe\xd7\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_waiting_missing_target_row_120x40.png
E       Changed pixels: 2746/1520532 (0.180595%); materially changed pixels: 2743/1520532 (0.180397%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_missing_target_row_png_snapshot/agents_waiting_missing_target_row_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_missing_target_row_png_snapshot/agents_waiting_missing_target_row_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_missing_target_row_png_snapshot/agents_waiting_missing_target_row_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_missing_target_row_png_snapshot/agents_waiting_missing_target_row_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________________ test_agents_waiting_tribe_target_png_snapshot _________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_waiting.py', test_line=249, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0607fc3310>

    async def test_agents_waiting_tribe_target_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(
            monkeypatch,
            agents=waiting_tribe_agents(),
        )
    
        async with AcePage(query='"wait-tribe"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 2)
            await wait_for_svg_contains(page, "@epic")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "WAITING")
            assert_page_svg_contains(page, "Wait:")
            assert_page_svg_contains(page, "[tribes]")
            assert_page_svg_contains(page, "@epic")
            assert_page_svg_contains(page, "epic.builder")
            assert_page_svg_contains(page, "▶")
            assert "WAITING ?" not in page.export_svg(title="tribe wait assertion")
>           ace_png_visual.assert_page_png(
                page,
                "agents_waiting_tribe_target_row_120x40",
                title="ACE agents pending tribe wait row and detail",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:273: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_waiting_tribe_target_row_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xd4\xa6...\x00\x00\x00\x00\x00\x00\x00\x00n<C\xd1m0\xba\xf5j\xe2\xce\xa4\x15\xfe\x0fP+p\x98^?^\x84\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_waiting_tribe_target_row_120x40.png
E       Changed pixels: 2746/1520532 (0.180595%); materially changed pixels: 2743/1520532 (0.180397%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_tribe_target_png_snapshot/agents_waiting_tribe_target_row_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_tribe_target_png_snapshot/agents_waiting_tribe_target_row_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_tribe_target_png_snapshot/agents_waiting_tribe_target_row_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_waiting.py__test_agents_waiting_tribe_target_png_snapshot/agents_waiting_tribe_target_row_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_clan_panel.py', test_line=285, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb264b739a0>

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
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_panel_swarm_120x40",
                title="ACE swarm clan panel fold level 1",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:311: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_panel_swarm_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xf3eIDA...0B\x08!\x84\x10b\xfcq4|\r\x87\xaf}\x14\xee\x8c\xdb\xe0\xff\x03\xc6\x06.\xd5\xd2:\xb8\xd6\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_clan_panel_swarm_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clan_panel.py__test_swarm_clan_panel_png_snapshots/agents_clan_panel_swarm_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________________ test_queued_clan_counts_png_snapshot _____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._agents_clans.py', test_line=37, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb264b71cc0>

    async def test_queued_clan_counts_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr("sase.config.core.get_max_running_agents", lambda: 10)
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 24, 12, 5, 0))
        patch_startup_loaders(monkeypatch, agents=queued_clan_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[0].is_clan_container is True
            panel = page.app.query_one("#agent-list-panel", AgentList)
            assert Text.from_markup(panel.border_title).plain == "▲ @epic · 2 [Q2]"
            list_rows = "\n".join(
                option.prompt.plain
                for option in panel._options  # type: ignore[union-attr]
            )
            assert "(QUEUED) ×2 [Q2]" in list_rows
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            assert "Status: QUEUED [Q2]" in prompt.content.plain
            info = page.app.query_one("#agent-info-panel", AgentInfoPanel)
            assert info._build_display_text().plain.startswith(
                "2  0.0/10.0 [0 running · 2 queued]"
            )
            status_group_keys = [
                entry.group.group_key
                for entry in build_agent_tree(
                    page.app._agents,
                    mode=GroupingMode.BY_STATUS,
                )
                if entry.group is not None
            ]
            assert status_group_keys == [("Queued",)]
>           ace_png_visual.assert_page_png(
                page,
                "agents_queued_clan_counts_120x40",
                title="ACE queued clan counts",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py:75: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_queued_clan_counts_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01a\xc8IDA...00\x00\x00\x00\x00\x00\x80\xa9g0\xf8I\x04?\x874pg\xd4\x04\xff\x0f\x0bB\xe7u\xbf\x0e\xd2f\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_queued_clan_counts_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_queued_clan_counts_png_snapshot/agents_queued_clan_counts_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_queued_clan_counts_png_snapshot/agents_queued_clan_counts_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_queued_clan_counts_png_snapshot/agents_queued_clan_counts_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_queued_clan_counts_png_snapshot/agents_queued_clan_counts_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________ test_agents_waiting_unknown_zoom_modal_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_waiting.py', test_line=280, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f061250cad0>

    async def test_agents_waiting_unknown_zoom_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _seed_wait_bead_status_cache()
        try:
            patch_startup_loaders(
                monkeypatch,
                agents=waiting_unknown_agents(),
            )
    
            async with AcePage(query='"wait-unknown"', patches=patches()) as page:
                await wait_for_startup(page)
                await page.press("shift+tab")
                await page.expect_state("tab", "agents")
                await page.expect_state("agent_count", 4)
                await wait_for_visual_idle(page)
                await page.press("p")
                await page.press("Z")
>               await page.expect_modal("ZoomPanelModal")

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:299: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:439: in expect_modal
    await self.expect_state("modal", name, timeout=timeout)
src/sase/ace/testing/ace_page.py:428: in expect_state
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.expect_state.<locals>.predicate at 0x7f060d0d7060>

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: expect_state('modal', 'ZoomPanelModal') timed out after 5.0s — last value was 'AgentViewModal'

src/sase/ace/testing/wait.py:54: AssertionError
___________________ test_running_clan_runtime_png_snapshots ____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._agents_clans.py', test_line=82, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24eccb8c0>

    async def test_running_clan_runtime_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 19, 9, 45, 0))
        patch_startup_loaders(monkeypatch, agents=running_clan_runtime_agents())
    
        async with AcePage(query='"visual-runtime-clan"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[0].is_clan_container is True
            assert_page_svg_contains(page, "runtime-clan")
            assert_page_svg_contains(page, "38m")
            assert_page_svg_contains(page, "45m")
            # The collapsed clan lane must show the family's total (38m), never
            # the running coder shell's own runtime (35m) -- that single
            # absence is what fails loudly if the clan lane regresses. Scoped to
            # the live-marker-prefixed form so it doesn't false-positive on the
            # family roster detail panel, which legitimately lists the coder
            # shell's own 35m runtime alongside the clan row.
            assert_page_svg_styled_text_absent(page, "🏃‍♂️ 35m")
>           ace_png_visual.assert_page_png(
                page,
                "agents_running_clan_runtime_collapsed_120x40",
                title="ACE running clan runtime collapsed",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_running_clan_runtime_collapsed_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xca^IDA...\x00\x00\x00\x00\x00\xc0\xf1\xb3i\xa7u;%\xf4\xc5\x9d\xf9f\xf8\x03tM\x0f\x15\xc1y\xe6\xc9\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_running_clan_runtime_collapsed_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_running_clan_runtime_png_snapshots/agents_running_clan_runtime_collapsed_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_running_clan_runtime_png_snapshots/agents_running_clan_runtime_collapsed_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_running_clan_runtime_png_snapshots/agents_running_clan_runtime_collapsed_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_running_clan_runtime_png_snapshots/agents_running_clan_runtime_collapsed_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________________ test_clan_tree_fold_levels_png_snapshots ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_clans.py', test_line=128, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265293850>

    async def test_clan_tree_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 10, 15, 0))
        patch_startup_loaders(monkeypatch, agents=clan_tree_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[0].is_clan_container is True
            assert page.app._agents[0].clan_tribes == ("epic", "review")
            assert_page_svg_contains(page, "research")
            assert_page_svg_styled_text_contains(page, "[R1 W1 D1]")
            assert_page_svg_contains(page, "@epic")
            assert_page_svg_contains(page, "@review")
            # The clan has three direct lanes (family, workflow, standalone), and
            # the status buckets retain the loaded concrete family member.
            assert page.app._agent_info_metrics() == (0, 0, 1, 1, 0, 1, 3, 0, 0)
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_tree_collapsed_120x40",
                title="ACE clan tree collapsed",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py:151: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_tree_collapsed_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xbcdIDA...x00\x00\xf6<[k\xb7\xbe\xda\xed\x91\xe8\xb8\xb3\xd9\x00\xff?\xbc\xfd\xb1\xaaG\x18\xb0\xba\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_clan_tree_collapsed_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_tree_fold_levels_png_snapshots/agents_clan_tree_collapsed_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_tree_fold_levels_png_snapshots/agents_clan_tree_collapsed_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_tree_fold_levels_png_snapshots/agents_clan_tree_collapsed_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_tree_fold_levels_png_snapshots/agents_clan_tree_collapsed_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_agents_xprompt_panel_highlighting_png_snapshot[textual-dark-agents_xprompt_panel_highlighting_120x40-ACE agents xprompt panel highlighting] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...gents_xprompt.py', test_line=75, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0607bf7850>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_xprompt_panel_high0')
theme = 'textual-dark'
snapshot_name = 'agents_xprompt_panel_highlighting_120x40'
title = 'ACE agents xprompt panel highlighting'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "agents_xprompt_panel_highlighting_120x40",
                "ACE agents xprompt panel highlighting",
            ),
            (
                "textual-light",
                "agents_xprompt_panel_highlighting_light_120x40",
                "ACE agents xprompt panel highlighting, light theme",
            ),
        ],
    )
    async def test_agents_xprompt_panel_highlighting_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        agent = _xprompt_highlight_agent(tmp_path / "xprompt-highlight-artifacts")
        patch_startup_loaders(monkeypatch, agents=[agent])
        patch_visual_glossary_catalog(monkeypatch)
        patch_visual_repo_mention_catalog(monkeypatch)
    
        def _entries(
            _app: AceApp,
            _project: str | None,
            *,
            schedule: bool = True,
        ) -> list[XPromptAssistEntry]:
            del schedule
            return [_SKILL_ENTRY]
    
        monkeypatch.setattr(AceApp, "get_prompt_catalog_assist_entries", _entries)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            page.app.theme = theme
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "AGENT XPROMPT")
            await wait_for_svg_contains(page, "sase_plan")
            await wait_for_svg_contains(page, "Agent Clan")
            await wait_for_svg_contains(page, "sase-core")
            await wait_for_visual_idle(page)
    
            for token in (
                "#git",
                ":sase",
                "%auto",
                "#pr",
                ":my_change",
                "%m",
                ":opus",
                "plans",
                "bead",
                "agent",
                "---",
                "quoted",
                "payload.md",
                "commit",
                "sase_plan",
                "Agent Clan",
                "sase-core",
            ):
                assert_page_svg_contains(page, token)
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=title,
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_xprompt.py:146: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_xprompt_panel_highlighting_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02;eIDATx\...00\x00\x00\x00\x00\x00\x00\xa3Oo\xf2\xeaJ^;\xd4qg\xda\x00\xff\x07\xb4\x80\xdc\xa8\xeeE>0\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_xprompt_panel_highlighting_120x40.png
E       Changed pixels: 2755/1520532 (0.181187%); materially changed pixels: 2667/1520532 (0.175399%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-dark-agents_xprompt_panel_highlighting_120x40-ACE_agents_xprompt_panel_highlighting/agents_xprompt_panel_highlighting_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-dark-agents_xprompt_panel_highlighting_120x40-ACE_agents_xprompt_panel_highlighting/agents_xprompt_panel_highlighting_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-dark-agents_xprompt_panel_highlighting_120x40-ACE_agents_xprompt_panel_highlighting/agents_xprompt_panel_highlighting_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-dark-agents_xprompt_panel_highlighting_120x40-ACE_agents_xprompt_panel_highlighting/agents_xprompt_panel_highlighting_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_agents_xprompt_panel_highlighting_png_snapshot[textual-light-agents_xprompt_panel_highlighting_light_120x40-ACE agents xprompt panel highlighting, light theme] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...gents_xprompt.py', test_line=75, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0604e3fe70>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_xprompt_panel_high1')
theme = 'textual-light'
snapshot_name = 'agents_xprompt_panel_highlighting_light_120x40'
title = 'ACE agents xprompt panel highlighting, light theme'

    @pytest.mark.parametrize(
        ("theme", "snapshot_name", "title"),
        [
            (
                "textual-dark",
                "agents_xprompt_panel_highlighting_120x40",
                "ACE agents xprompt panel highlighting",
            ),
            (
                "textual-light",
                "agents_xprompt_panel_highlighting_light_120x40",
                "ACE agents xprompt panel highlighting, light theme",
            ),
        ],
    )
    async def test_agents_xprompt_panel_highlighting_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        theme: str,
        snapshot_name: str,
        title: str,
    ) -> None:
        agent = _xprompt_highlight_agent(tmp_path / "xprompt-highlight-artifacts")
        patch_startup_loaders(monkeypatch, agents=[agent])
        patch_visual_glossary_catalog(monkeypatch)
        patch_visual_repo_mention_catalog(monkeypatch)
    
        def _entries(
            _app: AceApp,
            _project: str | None,
            *,
            schedule: bool = True,
        ) -> list[XPromptAssistEntry]:
            del schedule
            return [_SKILL_ENTRY]
    
        monkeypatch.setattr(AceApp, "get_prompt_catalog_assist_entries", _entries)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            page.app.theme = theme
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "AGENT XPROMPT")
            await wait_for_svg_contains(page, "sase_plan")
            await wait_for_svg_contains(page, "Agent Clan")
            await wait_for_svg_contains(page, "sase-core")
            await wait_for_visual_idle(page)
    
            for token in (
                "#git",
                ":sase",
                "%auto",
                "#pr",
                ":my_change",
                "%m",
                ":opus",
                "plans",
                "bead",
                "agent",
                "---",
                "quoted",
                "payload.md",
                "commit",
                "sase_plan",
                "Agent Clan",
                "sase-core",
            ):
                assert_page_svg_contains(page, token)
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title=title,
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_xprompt.py:146: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_xprompt_panel_highlighting_light_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x029\x15IDA...00\x00\x00\x80\xdegG\xf2\xda\x9a\xbcV\xa9\xe3\xce\xb4\x01\xfe\x7f\xf3\xa5\xe9P&\xd6u\x94\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_xprompt_panel_highlighting_light_120x40.png
E       Changed pixels: 2754/1520532 (0.181121%); materially changed pixels: 2592/1520532 (0.170467%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-light-agents_xprompt_panel_highlighting_light_120x40-ACE_agents_xprompt_panel_highlighting__light_theme/agents_xprompt_panel_highlighting_light_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-light-agents_xprompt_panel_highlighting_light_120x40-ACE_agents_xprompt_panel_highlighting__light_theme/agents_xprompt_panel_highlighting_light_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-light-agents_xprompt_panel_highlighting_light_120x40-ACE_agents_xprompt_panel_highlighting__light_theme/agents_xprompt_panel_highlighting_light_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_xprompt.py__test_agents_xprompt_panel_highlighting_png_snapshot_textual-light-agents_xprompt_panel_highlighting_light_120x40-ACE_agents_xprompt_panel_highlighting__light_theme/agents_xprompt_panel_highlighting_light_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________________ test_clan_unread_count_png_snapshots _____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_clans.py', test_line=220, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25d4224a0>

    async def test_clan_unread_count_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 17, 10, 15, 0))
        patch_startup_loaders(monkeypatch, agents=clan_tree_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
    
            unread_member = next(
                agent
                for agent in page.app._agents_with_children
                if not agent.is_clan_container
                and agent.tree_depth == 1
                and agent.status == "DONE"
            )
            page.app._unread_completed_agent_ids.add(unread_member.identity)
            page.app._manual_unread_agent_ids.add(unread_member.identity)
            page.app._refresh_agents_display(list_changed=True)
            await wait_for_visual_idle(page)
    
            assert_page_svg_styled_text_contains(page, "[R1 W1 U1]")
>           ace_png_visual.assert_page_png(
                page,
                "agents_clan_unread_collapsed_120x40",
                title="ACE unread clan collapsed",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py:246: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_clan_unread_collapsed_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xbd\x9c...x00\x00\x00`\xf7\xb3\xb5v\xeb\xab\xdd\x1e\x89\x8e;\x9b\r\xf0\xff\x03\xa3JMlZ\x02\xd8\xc4\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_clan_unread_collapsed_120x40.png
E       Changed pixels: 2726/1520532 (0.179279%); materially changed pixels: 2722/1520532 (0.179016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_unread_count_png_snapshots/agents_clan_unread_collapsed_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_unread_count_png_snapshots/agents_clan_unread_collapsed_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_unread_count_png_snapshots/agents_clan_unread_collapsed_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_clans.py__test_clan_unread_count_png_snapshots/agents_clan_unread_collapsed_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
____________ test_agents_external_repo_diff_file_panel_png_snapshot ____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...xternal_repos.py', test_line=82, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25d420c90>

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_external_repo_diff_file_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02>\xa1IDA...00\x00\x00\x00\x00\x00\xc0\xf0s"x\xf4\x06\x8f=\x1a\xb83j\x82\xff\x03/\x9f\x83W\x03@8\xb7\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_external_repo_diff_file_panel_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_external_repos.py__test_agents_external_repo_diff_file_panel_png_snapshot/agents_external_repo_diff_file_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_waiting_family_child_row_png_snapshot __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_families.py', test_line=38, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25f24f310>

    async def test_waiting_family_child_row_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=waiting_family_child_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await page.press("l")
            await page.expect_state("agent_count", 2)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-parent")
            assert_page_svg_contains(page, "RUNNING")
            assert_page_svg_contains(page, "visual-parent--reviewer")
            assert_page_svg_contains(page, "WAITING")
>           ace_png_visual.assert_page_png(
                page,
                "agents_waiting_family_child_120x40",
                title="ACE agents waiting family child",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:57: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_waiting_family_child_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xea(IDA...B\x08!\x84\x10\xa2\xf5\xb8\x10=\xc6\xa3\xc71\x12w\xa6\x1d\xf0\xffj\xab\x9d\xe2|\xa3M\xeb\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_waiting_family_child_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_waiting_family_child_row_png_snapshot/agents_waiting_family_child_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_waiting_family_child_row_png_snapshot/agents_waiting_family_child_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_waiting_family_child_row_png_snapshot/agents_waiting_family_child_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_waiting_family_child_row_png_snapshot/agents_waiting_family_child_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________ test_running_family_current_runtime_png_snapshots _______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ents_families.py', test_line=64, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25f42e3c0>

    async def test_running_family_current_runtime_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 19, 9, 5, 5))
        patch_startup_loaders(monkeypatch, agents=running_family_runtime_agents())
    
        async with AcePage(query='"visual-runtime-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-runtime-family")
            assert_page_svg_contains(page, "1m05s")
            assert_page_svg_contains(page, "3m05s")
>           ace_png_visual.assert_page_png(
                page,
                "agents_running_family_runtime_collapsed_120x40",
                title="ACE running family runtime collapsed",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:81: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_running_family_runtime_collapsed_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xa0\xe8...\x00\x00\x00\xe0\xf8s\xb0\xf8\x19,~\x1e\x8b\x81;[M\xf0\xff\x07\xb7\xab\xd8\xecw\xbe~\xe9\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_running_family_runtime_collapsed_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_running_family_current_runtime_png_snapshots/agents_running_family_runtime_collapsed_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_running_family_current_runtime_png_snapshots/agents_running_family_runtime_collapsed_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_running_family_current_runtime_png_snapshots/agents_running_family_runtime_collapsed_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_running_family_current_runtime_png_snapshots/agents_running_family_runtime_collapsed_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_settled_monitor_lane_badge_png_snapshot _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_families.py', test_line=101, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24ddf3cb0>

    async def test_settled_monitor_lane_badge_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 26, 9, 30, 0))
        patch_startup_loaders(monkeypatch, agents=settled_monitor_family_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-monitor-family")
            assert_page_svg_contains(page, "⚙1")
            assert_page_svg_contains(page, "⚙3")
            panel = page.app.query_one("#agent-list-panel", AgentList)
            assert Text.from_markup(panel.border_title).plain == "⌂ @default · 1 [R1] ⚙1 ⚙3"
>           ace_png_visual.assert_page_png(
                page,
                "agents_settled_monitor_lane_badge_120x40",
                title="ACE agents settled monitor lane badge",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:120: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_settled_monitor_lane_badge_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x022\xbbIDA...x84\x10B\x08!\x84\x10B\x08\x19z\xf4\xe9WP\xbf\x0e#p\xa7[\x82\xff\x03\xcd\xe4yAFj\xe8\x1b\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_settled_monitor_lane_badge_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_settled_monitor_lane_badge_png_snapshot/agents_settled_monitor_lane_badge_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_settled_monitor_lane_badge_png_snapshot/agents_settled_monitor_lane_badge_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_settled_monitor_lane_badge_png_snapshot/agents_settled_monitor_lane_badge_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_settled_monitor_lane_badge_png_snapshot/agents_settled_monitor_lane_badge_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________ test_python_step_parent_family_footer_png_snapshot ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_families.py', test_line=127, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d2587c0>

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_python_step_parent_family_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xcf\xda...4\x10B\x08!\xc4\xfcc\xcc?F\xfc\xe3\x1a\x85;\x93\x0e\xf8\x08\xd3\xe6\xc8}\x82\xef\x01\xab\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_python_step_parent_family_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_python_step_parent_family_footer_png_snapshot/agents_python_step_parent_family_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agents_context_zoom_modal_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._zoom_context.py', test_line=38, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060c37c830>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_context_zoom_modal0')

    async def test_agents_context_zoom_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(
            monkeypatch,
            agents=[zoom_agent(tmp_path, include_plan=True)],
            artifact_reads=context_artifact_reads(),
            memory_reads=context_memory_reads(),
            skill_uses=context_skill_uses(),
            opened_workspaces=context_opened_workspaces(),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
            await page.press("p")
            await page.press("Z")
>           await page.expect_modal("ZoomPanelModal")

tests/ace/tui/visual/test_ace_png_snapshots_agents_zoom_context.py:60: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:439: in expect_modal
    await self.expect_state("modal", name, timeout=timeout)
src/sase/ace/testing/ace_page.py:428: in expect_state
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.expect_state.<locals>.predicate at 0x7f060cf53270>

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: expect_state('modal', 'ZoomPanelModal') timed out after 5.0s — last value was 'AgentViewModal'

src/sase/ace/testing/wait.py:54: AssertionError
________________ test_renamed_generic_family_root_png_snapshot _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_families.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d25bc40>

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_renamed_generic_family_root_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02*aIDATx\...0B\x08!\x84\x10B\x08!\x84\x10Rx\x9c\xd6\xaf\x90~}\x82\x8d;\xbd\x12\xfc_oG\xae\xfe\xbf|Qn\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_renamed_generic_family_root_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_renamed_generic_family_root_png_snapshot/agents_renamed_generic_family_root_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________ test_parallel_family_root_omits_counts_png_snapshot ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_families.py', test_line=222, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb281b310f0>

    async def test_parallel_family_root_omits_counts_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 16, 10, 10, 0))
        patch_startup_loaders(monkeypatch, agents=parallel_family_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "visual-parallel-family")
            svg_plain = page.export_svg(title="ACE visual assertion").replace("&#160;", " ")
            assert "[R2 D1]" not in svg_plain
            # (unread, stopped, running, waiting, failed, done, total, starting, procs)
            assert page.app._agent_info_metrics() == (0, 0, 1, 0, 0, 0, 1, 0, 0)
>           ace_png_visual.assert_page_png(
                page,
                "agents_parallel_family_no_counts_120x40",
                title="ACE parallel family without aggregate counts",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py:241: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_parallel_family_no_counts_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xe7cIDA...\x00\x00\x00\x00\x00\x98}\xceF?\xe3\xd1\xcf\x11\r\xdc\x994\xc3\xff\x03\n\xd0.>\xb9\x12d`\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_parallel_family_no_counts_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_parallel_family_root_omits_counts_png_snapshot/agents_parallel_family_no_counts_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_parallel_family_root_omits_counts_png_snapshot/agents_parallel_family_no_counts_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_parallel_family_root_omits_counts_png_snapshot/agents_parallel_family_no_counts_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_parallel_family_root_omits_counts_png_snapshot/agents_parallel_family_no_counts_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agents_metadata_zoom_modal_png_snapshot _________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...zoom_context.py', test_line=118, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060d069080>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw0/test_agents_metadata_zoom_moda0')

    async def test_agents_metadata_zoom_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(
            monkeypatch,
            agents=[zoom_agent(tmp_path, include_xprompts=True)],
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
            await page.press("p")
            await page.press("Z")
>           await page.expect_modal("ZoomPanelModal")

tests/ace/tui/visual/test_ace_png_snapshots_agents_zoom_context.py:136: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:439: in expect_modal
    await self.expect_state("modal", name, timeout=timeout)
src/sase/ace/testing/ace_page.py:428: in expect_state
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.expect_state.<locals>.predicate at 0x7f05f3e04040>

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: expect_state('modal', 'ZoomPanelModal') timed out after 5.0s — last value was 'AgentViewModal'

src/sase/ace/testing/wait.py:54: AssertionError
_______________ test_family_and_lone_planner_color_png_snapshot ________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_families.py', test_line=248, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d2c600>

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_and_lone_planner_color_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x1b\xd4...10B\x08!\x84\x10B\xfa\x1f\xa7\xf5+\xa2_\x1f#p\xa7W\x82\xff\x0f\x0f|\xf3\x9b\xe4\x83n\xe2\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_and_lone_planner_color_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_families.py__test_family_and_lone_planner_color_png_snapshot/agents_family_and_lone_planner_color_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_______ test_family_panel_fold_levels_and_member_override_png_snapshots ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._family_panel.py', test_line=34, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d2c670>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_panel_fold_levels_0')

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
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_level_1_120x40",
                title="ACE family panel fold level 1",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:56: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_level_1_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02-\xb4IDA...\x10B\x08!\x84\x10B\x06\x1fg\xf4\'\xa8?\x1f!p\xa7W\x82\xff\x0f$u\x12\x90\x8d\x8b\xb2\xfc\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_panel_level_1_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_panel_level_1_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_panel_level_1_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_panel_level_1_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_panel_fold_levels_and_member_override_png_snapshots/agents_family_panel_level_1_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________ test_family_member_panel_shows_sibling_roster_png_snapshot __________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...family_panel.py', test_line=155, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d2d9b0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_member_panel_shows0')

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_member_roster_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02R\xc1IDA...\x00\x00\x00\x00cO\x7f\xf4\xd3\x1b\xfd\xbc\xa6\x89;\x93\x16\xf8\xff\x01\xc9j\x1d:\xf3h q\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_panel_member_roster_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_member_panel_shows_sibling_roster_png_snapshot/agents_family_panel_member_roster_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________ test_family_two_digit_roster_and_pending_footer_png_snapshots _________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...family_panel.py', test_line=200, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24ff66120>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_two_digit_roster_a0')

    async def test_family_two_digit_roster_and_pending_footer_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 30, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=_family_agents(tmp_path, member_count=11, with_content=False),
        )
    
        async with AcePage(query='"visual-family"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            container = page.app._agents[page.app.current_idx]
            container_identity = container.identity
            jump_map = page.app._member_jump_maps[container_identity]
            assert jump_map.targets[0].number == "00"
            assert jump_map.targets[-1].number == "10"
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_two_digit_roster_120x40",
                title="ACE family panel two-digit roster",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:223: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_two_digit_roster_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02h IDATx\...00\x00\x00@\xfe\xa9\xf7\x1e\xb5\xde\xe3\x1du\xdc\x196\xc0\xff\x0f\xcb\x00>\xd5m|\x97\x7f\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_panel_two_digit_roster_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_two_digit_roster_and_pending_footer_png_snapshots/agents_family_panel_two_digit_roster_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_two_digit_roster_and_pending_footer_png_snapshots/agents_family_panel_two_digit_roster_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_two_digit_roster_and_pending_footer_png_snapshots/agents_family_panel_two_digit_roster_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel.py__test_family_two_digit_roster_and_pending_footer_png_snapshots/agents_family_panel_two_digit_roster_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
____________________ test_family_gate_shells_png_snapshots _____________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ly_panel_gate.py', test_line=32, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25da1a270>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_gate_shells_png_sn0')

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_gate_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x05uIDA...84\x10B\x08!\x84\x102\xf88\xaf_\x9d\xfau\x04\x89;\xdd6\xf8\xff\xb5.1\x89\xc0\xb9\xc3\xe3\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_png_snapshots/agents_family_panel_shells_gate_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_family_gate_shells_narrow_png_snapshot __________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ly_panel_gate.py', test_line=83, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25da18910>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_gate_shells_narrow0')

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_gate_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01)\xc2IDATx...\x84\x10B\x08!F\t\xe9$B\x88j\xd0\xe7>=\xees\x82\x00\xb9i7|\x01\x9f?h\x13\x03\xd9\xca\x03\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_gate_90x40.png
E       Changed pixels: 2745/1145016 (0.239735%); materially changed pixels: 2744/1145016 (0.239647%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_family_gate_shells_narrow_png_snapshot/agents_family_panel_shells_gate_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_selected_gate_shell_output_png_snapshot _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...y_panel_gate.py', test_line=114, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25da1a660>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_selected_gate_shell_outpu0')

    async def test_selected_gate_shell_output_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 13, 8, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=[_selected_gate_agent(tmp_path)],
        )
    
        async with AcePage(
            query='"visual-standalone-gate-run"',
            size=(120, 40),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            selected = page.app._agents[page.app.current_idx]
            assert selected.is_gate is True
            assert selected.gate_state == "settling"
            assert_page_svg_contains(page, "Run deployment preview")
            scroll = page.query_one_widget("#agent-prompt-scroll", VerticalScroll)
            scroll.scroll_to(y=16, animate=False, immediate=True)
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "gate output line 01")
            assert_page_svg_contains(page, "truncated")
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_gate_output_120x40",
                title="ACE selected gate shell with long output",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:145: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_gate_output_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x026\xe4IDA...0\x00\x00\x00\x00=\xcf\x8e\xe8\xd1\x1a=\xde\xd6\x8d;\x93&\xf8\x7f\xe4\xe7\xc6\xf1.\x1eI&\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_gate_output_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_selected_gate_shell_output_png_snapshot/agents_family_gate_output_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_selected_gate_shell_output_png_snapshot/agents_family_gate_output_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_selected_gate_shell_output_png_snapshot/agents_family_gate_output_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_gate.py__test_selected_gate_shell_output_png_snapshot/agents_family_gate_output_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______ test_monitor_state_detail_png_snapshots[running-overrides0-90-40] _______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e71d6a0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_0')
slug = 'running'
overrides = {'monitor_state': 'running', 'output': 'collecting diagnostics...\n', 'status': 'TESTING'}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_running_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01\xb3\x0cID...0@;\xe1\x9c\x04@\x1c\xf6y\xb7&\xef\xf6\x8e\n\xe4\x86M\xf0\xff\x03l\x1f\x95\xc1.\xf04\xad\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_running_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-90-40/agents_monitor_state_running_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-90-40/agents_monitor_state_running_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-90-40/agents_monitor_state_running_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-90-40/agents_monitor_state_running_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______ test_monitor_state_detail_png_snapshots[running-overrides0-120-40] ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e5d04b0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_1')
slug = 'running'
overrides = {'monitor_state': 'running', 'output': 'collecting diagnostics...\n', 'status': 'TESTING'}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_running_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x0c\x94...00\x00\x00\x00\x00\x004\x9f\x81\xe8\xd1\x17=vh\xe0\xce\xa4\t\xfe?B\xc9\xa4\xa4\xcf`\x9cx\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_running_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-120-40/agents_monitor_state_running_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-120-40/agents_monitor_state_running_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-120-40/agents_monitor_state_running_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_running-overrides0-120-40/agents_monitor_state_running_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___ test_monitor_state_detail_png_snapshots[host_completed-overrides1-90-40] ___
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e5d2c10>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_2')
slug = 'host_completed'
overrides = {'exit_code': 0, 'followup_outcome': 'host-completed', 'host_completion_message': 'Required checks passed in 4m12s.', 'host_completion_status': 'completed_by_host', ...}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_host_completed_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01\x1d\x87ID...5?\x07\x00\xe0\x92x&\x01\x86\xe1(]\x87\xe9j\xc6\x06\xb9g]\xf0\x0b#\x99\xc7\x11/,\xf3\xed\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_host_completed_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-90-40/agents_monitor_state_host_completed_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-90-40/agents_monitor_state_host_completed_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-90-40/agents_monitor_state_host_completed_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-90-40/agents_monitor_state_host_completed_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__ test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40] ___
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e39ef90>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_3')
slug = 'host_completed'
overrides = {'exit_code': 0, 'followup_outcome': 'host-completed', 'host_completion_message': 'Required checks passed in 4m12s.', 'host_completion_status': 'completed_by_host', ...}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_host_completed_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02)\xe6IDA...x00\x00PzN\x05\xb7\xe6\xe0\xf6\xa6\x06\xee\x8c\x9a\xe0\xff\x02\x1a\xde\xa9`\xf9I\xc2\xa2\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_host_completed_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-120-40/agents_monitor_state_host_completed_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-120-40/agents_monitor_state_host_completed_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-120-40/agents_monitor_state_host_completed_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_host_completed-overrides1-120-40/agents_monitor_state_host_completed_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-90-40] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25e71eac0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_4')
slug = 'failed_diagnostics'
overrides = {'checkpoint_ref': 'local:continuation/checkpoints/failed.yml', 'diagnostic_manifest_ref': 'artifact:diagnostics-failed', 'exit_code': 1, 'monitor_state': 'failed', ...}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_failed_diagnostics_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x00\xec\xc4ID...s\x00\x00N\x13u\x12 \xc3l\xef6\xd3\xbb=\x12\x03\xe4\xf6\x9b\xe0\xbf\x00\xc2/h\xcdV<o\x83\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_failed_diagnostics_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-90-40/agents_monitor_state_failed_diagnostics_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-90-40/agents_monitor_state_failed_diagnostics_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-90-40/agents_monitor_state_failed_diagnostics_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-90-40/agents_monitor_state_failed_diagnostics_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24c3abbd0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_5')
slug = 'failed_diagnostics'
overrides = {'checkpoint_ref': 'local:continuation/checkpoints/failed.yml', 'diagnostic_manifest_ref': 'artifact:diagnostics-failed', 'exit_code': 1, 'monitor_state': 'failed', ...}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_failed_diagnostics_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x17\xac...\x00\x00\x00\xe8x\xf6\x06\xb7\xc6\xe0\xb6Q\x1dwF\r\xf0\xff\x01\x16\xd3\xf6!o\x8d\x1f\xb6\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_failed_diagnostics_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-120-40/agents_monitor_state_failed_diagnostics_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-120-40/agents_monitor_state_failed_diagnostics_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-120-40/agents_monitor_state_failed_diagnostics_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_failed_diagnostics-overrides2-120-40/agents_monitor_state_failed_diagnostics_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________ test_agents_neighbor_jump_expands_target_panel_png_snapshot __________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_neighbors.py', test_line=253, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5b4ca4a0>

    async def test_agents_neighbor_jump_expands_target_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _neighbor_panel_reveal_agents()
        target = agents[1]
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "alpha"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            await page.press("h")
            await page.wait_for(lambda _screen: "alpha" in page.app._collapsed_panel_keys)
            assert page.app._panel_group.panel_keys == [None, "zeta", "alpha"]
            await page.press("J")
            assert page.app._panel_group.focused_key is None
            assert page.app._agents[page.app.current_idx].identity == agents[0].identity
    
            page.app.action_start_sibling_mode()
            await page.wait_for(
                lambda _screen: "alpha" not in page.app._collapsed_panel_keys
            )
            await wait_for_visual_idle(page)
    
            assert page.app._panel_group.panel_keys == [None, "alpha", "zeta"]
            assert page.app._panel_group.focused_key == "alpha"
            assert page.app._agents[page.app.current_idx].identity == target.identity
            target_widget = page.app.query_one("#agent-list-panel-1", AgentList)
            assert target_widget.highlighted is not None
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_neighbor_jump_expanded_panel_120x40",
                title="ACE folded-clan neighbor jump expanded panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:292: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_neighbor_jump_expanded_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02^\x9fIDA...0B\x08!\x84\x10B\x08!\x84\x0c<\x8e\xebOH\x7fv"p\xa7W\x82\xff\x0bs\'\x0f\x19*\xaa\x1d\xab\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_neighbor_jump_expanded_panel_120x40.png
E       Changed pixels: 2746/1520532 (0.180595%); materially changed pixels: 2743/1520532 (0.180397%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_jump_expands_target_panel_png_snapshot/agents_neighbor_jump_expanded_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______ test_monitor_state_detail_png_snapshots[timeout-overrides3-90-40] _______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb2644ae4a0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_6')
slug = 'timeout'
overrides = {'checkpoint_ref': 'local:continuation/checkpoints/timeout.yml', 'exit_code': 124, 'monitor_state': 'timeout', 'output': 'timed out waiting for quiet shard\n', ...}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_timeout_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01GhIDATx\x9...\x9a\x84\xfa$B\x88<8\x91|\x06\x93\xcfn\x1c\xe4\xa6\x05\xf8\x0f\x82\xde$h\x89\xe6\x92\xbe\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_timeout_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-90-40/agents_monitor_state_timeout_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-90-40/agents_monitor_state_timeout_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-90-40/agents_monitor_state_timeout_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-90-40/agents_monitor_state_timeout_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______ test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40] ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25d5f7d20>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_7')
slug = 'timeout'
overrides = {'checkpoint_ref': 'local:continuation/checkpoints/timeout.yml', 'exit_code': 124, 'monitor_state': 'timeout', 'output': 'timed out waiting for quiet shard\n', ...}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_timeout_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02K\xa4IDA...x00\x00\xa0\xf3\xd9\x17\xfc4\x05?\xef\xab\xe3\xce\xb8\x01\xfe\x7f\x0e5\x97H)\xd3\x87\x02\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_timeout_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-120-40/agents_monitor_state_timeout_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-120-40/agents_monitor_state_timeout_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-120-40/agents_monitor_state_timeout_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_timeout-overrides3-120-40/agents_monitor_state_timeout_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________ test_monitor_state_detail_png_snapshots[lost-overrides4-90-40] ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d3e900>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_8')
slug = 'lost'
overrides = {'monitor_state': 'lost', 'output': 'last retained line before reboot\n', 'result_ref': 'artifact:lost-result', 'status': 'TESTED'}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_lost_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01q1IDATx\x9...xe6\x00\x00\x00t\x12\xaeI\x00\xc4\xa19x5\x05\xaf\xadJ\x90\x1b5\xc0\x7f\x01bv);#_\xfc\xd1\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_lost_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-90-40/agents_monitor_state_lost_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-90-40/agents_monitor_state_lost_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-90-40/agents_monitor_state_lost_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-90-40/agents_monitor_state_lost_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_______ test_monitor_state_detail_png_snapshots[lost-overrides4-120-40] ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb265d3dcc0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_9')
slug = 'lost'
overrides = {'monitor_state': 'lost', 'output': 'last retained line before reboot\n', 'result_ref': 'artifact:lost-result', 'status': 'TESTED'}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_lost_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02.\xf5IDA...00\x00\x00\x00\x00\x00\x00\xf4<\xad\xc1\xad9\xb8mQ\xc7\x9dQ\x03\xfc\x7f\xc0Vg0\xf2\xd7n~\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_lost_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-120-40/agents_monitor_state_lost_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-120-40/agents_monitor_state_lost_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-120-40/agents_monitor_state_lost_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_lost-overrides4-120-40/agents_monitor_state_lost_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________ test_agents_lane_neighbors_section_fold_levels_png_snapshots _________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_neighbors.py', test_line=467, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab76da5e80>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw8/test_agents_lane_neighbors_sec0')

    async def test_agents_lane_neighbors_section_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, _LANE_NOW)
        patch_startup_loaders(monkeypatch, agents=_single_lane_neighbor_agents(tmp_path))
    
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
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            detail.update_display(lane)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].identity == lane_identity
            jump_map = page.app._member_jump_maps[lane.identity]
            assert [target.number for target in jump_map.targets] == ["0", "1", "2"]
            assert {target.role for target in jump_map.targets} == {"neighbor"}
            assert_page_svg_contains(page, "NEIGHBORS")
            assert_page_svg_contains(page, "visual.lane hood")
            assert_page_svg_contains(page, "more neighbors")
            await wait_for_svg_contains(page, "Review visual lane neighbor ordering.")
            await wait_for_svg_contains(page, "acknowledged")
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_lane_neighbors_section_first_level_160x50",
                title="ACE lane neighbors section first fold level",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:513: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_lane_neighbors_section_first_level_160x50'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x07\xb2\x00\x00\x04\xf6\x08\x06\x00\x00\x00\xaf7\xec\x82\x00\x03BTIDATx\...a\xa2(J\xe5\x1c\x0e_\x83\xe1\xeb\xa5\xd0\x81}\xd8\xb7\xc1\xff\x07l\xa7\xa2\x9f\x99\x89c(\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_section_first_level_160x50.png
E       Changed pixels: 2746/2501900 (0.109757%); materially changed pixels: 2743/2501900 (0.109637%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_first_level_160x50/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_first_level_160x50/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_first_level_160x50/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_section_fold_levels_png_snapshots/agents_lane_neighbors_section_first_level_160x50/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_ test_link_rail_agents_single_link_png_snapshots[size0-link_rail_agents_single_link_120x40] _
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_link_rail.py', test_line=173, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff1bb4d2200>
size = (120, 40), snapshot_name = 'link_rail_agents_single_link_120x40'

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "link_rail_agents_single_link_120x40"),
            ((60, 30), "link_rail_agents_single_link_60x30"),
        ],
    )
    async def test_link_rail_agents_single_link_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        size: tuple[int, int],
        snapshot_name: str,
    ) -> None:
        """n=1 teaches ``$$`` rather than ``$1``, with an inverse-direction label."""
    
        _freeze_rail(monkeypatch)
        patch_startup_loaders(monkeypatch, agents=visual_agents())
    
        async with AcePage(
            query='"visual"', patches=patches(), size=size, initial_tab="agents"
        ) as page:
            await wait_for_startup(page)
            await page.expect_state("tab", "agents")
            await _paint_rail(page, _single_inverse_chip())
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title="ACE link rail agents single link",
            )

tests/ace/tui/visual/test_ace_png_snapshots_link_rail.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'link_rail_agents_single_link_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02G\x1eIDA...\x10\xa2\xf18\x14\xbd\xfa\xa3\xd7\xeb,\xdc\x99\xb4\xc1\xff\x0f\x95\xee\xcf\x16\xe3>o\x90\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/link_rail_agents_single_link_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_link_rail.py__test_link_rail_agents_single_link_png_snapshots_size0-link_rail_agents_single_link_120x40/link_rail_agents_single_link_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_link_rail.py__test_link_rail_agents_single_link_png_snapshots_size0-link_rail_agents_single_link_120x40/link_rail_agents_single_link_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_link_rail.py__test_link_rail_agents_single_link_png_snapshots_size0-link_rail_agents_single_link_120x40/link_rail_agents_single_link_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_link_rail.py__test_link_rail_agents_single_link_png_snapshots_size0-link_rail_agents_single_link_120x40/link_rail_agents_single_link_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______ test_monitor_state_detail_png_snapshots[degraded-overrides5-90-40] ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24f8032a0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_10')
slug = 'degraded'
overrides = {'exit_code': 0, 'followup_degraded_reason': 'original workspace claim unavailable', 'followup_outcome': 'launched-degraded', 'monitor_state': 'completed', ...}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_degraded_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x01ExIDATx\x9...x99#\x84\x10B\x08\xd1$\xd4&\x11B\xe4\xc1\xf1d\x1bL\xb6]8\xc8M;\xe0\xff\x01F\x15t:\x92[d,\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_degraded_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-90-40/agents_monitor_state_degraded_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-90-40/agents_monitor_state_degraded_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-90-40/agents_monitor_state_degraded_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-90-40/agents_monitor_state_degraded_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________ test_agents_lane_neighbors_above_sase_context_png_snapshot __________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_neighbors.py', test_line=546, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab60e8b5b0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw8/test_agents_lane_neighbors_abo0')

    async def test_agents_lane_neighbors_above_sase_context_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, _LANE_NOW)
        patch_startup_loaders(monkeypatch, agents=_lane_neighbor_agents_with_plan(tmp_path))
    
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
            page.app.current_idx = page.app._agents.index(lane)
            await wait_for_svg_contains(page, "NEIGHBORS")
            await wait_for_svg_contains(page, "SASE CONTEXT")
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx] is lane
            assert_page_svg_contains(page, "NEIGHBORS")
            assert_page_svg_contains(page, "SASE CONTEXT")
            svg_plain = page.export_svg(title="ACE lane neighbors above context").replace(
                "&#160;", " "
            )
            assert svg_plain.index("NEIGHBORS") < svg_plain.index("SASE CONTEXT")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_lane_neighbors_above_context_160x50",
                title="ACE lane neighbors above SASE CONTEXT",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:577: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_lane_neighbors_above_context_160x50'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x07\xb2\x00\x00\x04\xf6\x08\x06\x00\x00\x00\xaf7\xec\x82\x00\x03\x9cJIDA...x00@\xed\x86\xa2\xaf\x81\xe8\xeb\xc5(\x80=\x94\xb4\xc1\xff\x05\x12\x11\xc4b\x93]\xb3\x7f\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_lane_neighbors_above_context_160x50.png
E       Changed pixels: 2746/2501900 (0.109757%); materially changed pixels: 2743/2501900 (0.109637%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_above_sase_context_png_snapshot/agents_lane_neighbors_above_context_160x50/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_above_sase_context_png_snapshot/agents_lane_neighbors_above_context_160x50/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_above_sase_context_png_snapshot/agents_lane_neighbors_above_context_160x50/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_lane_neighbors_above_sase_context_png_snapshot/agents_lane_neighbors_above_context_160x50/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____ test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40] ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24fa37af0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_11')
slug = 'degraded'
overrides = {'exit_code': 0, 'followup_degraded_reason': 'original workspace claim unavailable', 'followup_outcome': 'launched-degraded', 'monitor_state': 'completed', ...}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_degraded_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02i\xe3IDA...00\x00\x00\x00\x00h\x7f\xf6\x04_\r\xc1\xd7[\x1a\xb83j\x82\xff\x1f-k\x7f\x12R\x96\xac\xe9\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_degraded_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-120-40/agents_monitor_state_degraded_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-120-40/agents_monitor_state_degraded_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-120-40/agents_monitor_state_degraded_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_degraded-overrides5-120-40/agents_monitor_state_degraded_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________________ test_agents_family_lane_neighbors_png_snapshot ________________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_neighbors.py', test_line=584, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5b4ca4a0>

    async def test_agents_family_lane_neighbors_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, _LANE_NOW)
        patch_startup_loaders(monkeypatch, agents=_family_lane_neighbor_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=(160, 50)) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await wait_for_visual_idle(page)
    
            page.app.current_idx = _family_container_index(page)
            await wait_for_svg_contains(page, "FAMILY SHELLS")
            # Expanding inserts member rows above the container, so the selection
            # has to be re-resolved before the lane panel is captured.
            await page.press("l")
            page.app.current_idx = _family_container_index(page)
            await wait_for_svg_contains(page, "also listed under FAMILY SHELLS")
            await wait_for_visual_idle(page)
    
            lane = page.app._agents[page.app.current_idx]
            assert lane.is_family_container_row is True
            jump_map = page.app._member_jump_maps[lane.identity]
            assert [target.role for target in jump_map.targets] == [
                "member",
                "member",
                "member",
                "neighbor",
                "neighbor",
            ]
            assert [target.number for target in jump_map.targets] == list("01234")
            assert_page_svg_contains(page, "NEIGHBORS")
            assert_page_svg_contains(page, "also listed under FAMILY SHELLS")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_family_lane_neighbors_160x50",
                title="ACE family neighbors section",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:620: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_lane_neighbors_160x50'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x07\xb2\x00\x00\x04\xf6\x08\x06\x00\x00\x00\xaf7\xec\x82\x00\x03|\xc2IDA...\x00\x00\x00\x00\x00\x00\x00P\xbf}\xd1\xa3\'z\xfc6\n`\xefK\xda\xe0\xff\x07JCM\x18@Cj\xcb\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_lane_neighbors_160x50.png
E       Changed pixels: 2746/2501900 (0.109757%); materially changed pixels: 2743/2501900 (0.109637%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_family_lane_neighbors_png_snapshot/agents_family_lane_neighbors_160x50/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_family_lane_neighbors_png_snapshot/agents_family_lane_neighbors_160x50/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_family_lane_neighbors_png_snapshot/agents_family_lane_neighbors_160x50/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_family_lane_neighbors_png_snapshot/agents_family_lane_neighbors_160x50/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__ test_monitor_state_detail_png_snapshots[needs_attention-overrides6-90-40] ___
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d4a70e0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_12')
slug = 'needs_attention'
overrides = {'budget_decision_path': '/workspace/sase/.sase/monitor-budget.json', 'checkpoint_ref': 'local:continuation/checkpoints/attention.yml', 'exit_code': 0, 'followup_error': 'context_budget_exceeded; run monitor resume with checkpoint', ...}
width = 90, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_needs_attention_90x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x04\x02\x08\x06\x00\x00\x00\x91\xfd\xecN\x00\x00\xeb\xfcID...00\x00N\x12\xe7$@\x86\xc5\xee\xcf|\xf7\xe7\x9e\x18 \xb7\xdf\x0c\xff\x05"G\x89\x1f2.>\x01\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_needs_attention_90x40.png
E       Changed pixels: 2756/1145016 (0.240695%); materially changed pixels: 2753/1145016 (0.240433%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-90-40/agents_monitor_state_needs_attention_90x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-90-40/agents_monitor_state_needs_attention_90x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-90-40/agents_monitor_state_needs_attention_90x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-90-40/agents_monitor_state_needs_attention_90x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__ test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40] __
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=195, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d4a5a20>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_monitor_state_detail_png_13')
slug = 'needs_attention'
overrides = {'budget_decision_path': '/workspace/sase/.sase/monitor-budget.json', 'checkpoint_ref': 'local:continuation/checkpoints/attention.yml', 'exit_code': 0, 'followup_error': 'context_budget_exceeded; run monitor resume with checkpoint', ...}
width = 120, height = 40

    @pytest.mark.parametrize(("width", "height"), [(90, 40), (120, 40)])
    @pytest.mark.parametrize(("slug", "overrides"), _MONITOR_STATE_CASES)
    async def test_monitor_state_detail_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        slug: str,
        overrides: dict[str, object],
        width: int,
        height: int,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 9, 12, 12, 6, 0))
        agent = _monitor_state_agent(tmp_path, slug, **overrides)  # type: ignore[arg-type]
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query=f'"visual-monitor-{slug}"',
            size=(width, height),
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].is_monitor
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            for _ in range(20):
                if panel.active_section_identity == "monitor":
                    break
                await page.press("ctrl+j")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, f"visual-monitor-{slug}")
            if width >= 120:
                assert panel.active_section_identity == "monitor"
                assert_page_svg_contains(page, "MONITOR")
                assert_page_svg_contains(page, "Result:")
                assert_page_svg_contains(page, "Next:")
                assert_page_svg_contains(page, "Evidence:")
>           ace_png_visual.assert_page_png(
                page,
                f"agents_monitor_state_{slug}_{width}x{height}",
                title=f"ACE monitor detail {slug} {width}x{height}",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:235: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_monitor_state_needs_attention_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02-nIDATx\...00\x00\x00\x00\x00\x00\x00t=\r\xd1_}\xf4\xb7]\x1dw&\r\xf0\xff\x00\xb3\xdd\xcb\xc0mzb\x96\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_monitor_state_needs_attention_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-120-40/agents_monitor_state_needs_attention_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-120-40/agents_monitor_state_needs_attention_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-120-40/agents_monitor_state_needs_attention_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_monitor_state_detail_png_snapshots_needs_attention-overrides6-120-40/agents_monitor_state_needs_attention_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=242, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25f817c40>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_panel_shells_monit0')

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

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:292: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_panel_shells_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x02\xa4...x84\x10B\x08!\x84\x10B\x08\x99x\x9c\xd6\xaf\x90~\x1dB\xe2N\xaf\x05\xfe?\x11V WZ6\xf2\xe8\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_panel_shells_monitor_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_panel_shells_monitor_metadata_png_snapshot/agents_family_panel_shells_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________ test_sase_agent_cleanup_confirmation_png_snapshot _______________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_cleanup.py', test_line=129, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab624f6270>

    async def test_sase_agent_cleanup_confirmation_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _cleanup_confirmation_agents()
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            initial_tab="agents",
        ) as page:
            await wait_for_startup(page)
            cleanup_targets = [
                agent for agent in agents if agent.agent_name != "lane.cleanup.neighbor"
            ]
            page.app._present_bulk_kill_modal(
                cleanup_targets,
                header="Tribe: @cleanup",
            )
            await page.expect_modal("ConfirmDismissAllModal")
            modal = page.app.screen
            assert isinstance(modal, ConfirmDismissAllModal)
            description = modal.agent_description
            assert "Dismiss: 3 sase agents · 9 agents" in description
            assert "lane.cleanup.standalone" in description
            assert "lane.cleanup.workflow" in description
            assert "lane.cleanup.family" in description
            assert "internal.workflow.step" not in description
            assert "lane.cleanup.family--" not in description
            assert "lane.cleanup.neighbor" not in description
    
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "sase_agent_cleanup_confirmation_120x40",
                title="ACE sase agent cleanup confirmation",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_cleanup.py:162: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'sase_agent_cleanup_confirmation_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\xb9\x87...4\x10B\x08!\x84\xe8?\xd6\xe2\xd7\x8b\xf85G\xe2\xce\xa4\r\xfe\x1f\n\xe3\xc1M*\x18\x04\x1e\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/sase_agent_cleanup_confirmation_120x40.png
E       Changed pixels: 2735/1520532 (0.179871%); materially changed pixels: 2519/1520532 (0.165666%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_cleanup.py__test_sase_agent_cleanup_confirmation_png_snapshot/sase_agent_cleanup_confirmation_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_cleanup.py__test_sase_agent_cleanup_confirmation_png_snapshot/sase_agent_cleanup_confirmation_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_cleanup.py__test_sase_agent_cleanup_confirmation_png_snapshot/sase_agent_cleanup_confirmation_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_cleanup.py__test_sase_agent_cleanup_confirmation_png_snapshot/sase_agent_cleanup_confirmation_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...anel_monitor.py', test_line=323, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb281d7d080>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw2/test_family_conversation_monit0')

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

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:359: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_family_conversation_monitor_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xde7IDA...\x00\x00\x00\x00\x00f\x9e\x8b\xd1O:\xfa\xe9\xd1\xc0\x9dI3\xfc\x01/\x83\xd1\xa1A\x16D\xdd\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_family_conversation_monitor_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_family_panel_monitor.py__test_family_conversation_monitor_phase_png_snapshot/agents_family_conversation_monitor_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________ test_agents_overflowing_panel_uses_full_height_png_snapshot __________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...panel_layout.py', test_line=115, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5c81eac0>

    async def test_agents_overflowing_panel_uses_full_height_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = _overflowing_panel_agents()
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", len(rows))
            await wait_for_visual_idle(page)
    
            container = page.app.query_one("#agent-list-container")
            widgets = list(container.query(AgentList).results(AgentList))
            assert page.app._panel_group.panel_keys == [None, "apple", "banana"]
            assert len(widgets) == 3
            no_tribe, apple, banana = widgets
    
            assert no_tribe.styles.height.unit is Unit.FRACTION
            assert no_tribe.option_count + 2 > no_tribe.region.height
            for compact in (apple, banana):
                assert compact.styles.height.unit is Unit.CELLS
                assert compact.styles.height.value == compact.option_count + 2
            assert banana.region.bottom == container.content_region.bottom
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_overflowing_panel_full_height_120x40",
                title="ACE agents overflowing panel full height",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py:142: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_overflowing_panel_full_height_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x03\xeb6IDA...84\x10B\x08!\x84\x102\xf0\xe8\xd2\x1f\x9f\xfe\x1cB\xe0N\xaf\x1d\xfe\x7f/V\xdc\x98e%:\xd4\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_overflowing_panel_full_height_120x40.png
E       Changed pixels: 2726/1520532 (0.179279%); materially changed pixels: 2722/1520532 (0.179016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_overflowing_panel_uses_full_height_png_snapshot/agents_overflowing_panel_full_height_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_overflowing_panel_uses_full_height_png_snapshot/agents_overflowing_panel_full_height_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_overflowing_panel_uses_full_height_png_snapshot/agents_overflowing_panel_full_height_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_overflowing_panel_uses_full_height_png_snapshot/agents_overflowing_panel_full_height_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_______________ test_agents_filter_bar_idle_readout_png_snapshot _______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_filter_bar.py', test_line=29, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d3ad940>

    async def test_agents_filter_bar_idle_readout_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A committed query renders as a highlighted readout with a match count."""
        patch_startup_loaders(monkeypatch, agents=agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
    
            page.app._agent_search_query = "status:FAILED"
            page.app._refilter_agents()
            await page.pause()
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_filter_bar_idle_readout_120x40",
                title="ACE Agents filter bar idle readout",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_filter_bar.py:48: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_filter_bar_idle_readout_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x83\xb1...0\x00\x008\xf4\xec\xee|\x8dv\xbe\xbe\x9f\x81;\xfbM\xf0\xff\x039\xde\xfd\xb0\xcbR\xb9\x91\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_filter_bar_idle_readout_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_filter_bar.py__test_agents_filter_bar_idle_readout_png_snapshot/agents_filter_bar_idle_readout_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_filter_bar.py__test_agents_filter_bar_idle_readout_png_snapshot/agents_filter_bar_idle_readout_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_filter_bar.py__test_agents_filter_bar_idle_readout_png_snapshot/agents_filter_bar_idle_readout_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_filter_bar.py__test_agents_filter_bar_idle_readout_png_snapshot/agents_filter_bar_idle_readout_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_agents_unread_highlight_png_snapshot ___________________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...panel_layout.py', test_line=149, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5c81f690>

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_unread_highlight_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfe\x18...08!\x84\x10B\x08!\xa3\x8f\xf3\xfa\xd3\xab?G\xb1q\xa7W\x80\x7f\x03\x8e|\x9a\xef\x8a\xae;X\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_unread_highlight_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panel_layout.py__test_agents_unread_highlight_png_snapshot/agents_unread_highlight_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________ test_agents_fleet_followed_partial_offline_png_snapshot ____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_fleet.py', test_line=151, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24d5c66d0>

    async def test_agents_fleet_followed_partial_offline_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        summary_response = _fleet_visual_responses()
        facade = OfflineFleetFacade(
            summary_response=summary_response,
            catalog_response=summary_response,
        )
        patch_startup_loaders(monkeypatch, agents=agents())
        _patch_fleet_refresh(monkeypatch, facade=facade)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents(page)
            # Unified list concatenates 3 local visual fixtures with 3 fleet rows.
>           await _show_fleet(page, expected_count=6)

tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py:166: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py:78: in _show_fleet
    await page.expect_state("agent_count", expected_count)
src/sase/ace/testing/ace_page.py:428: in expect_state
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.expect_state.<locals>.predicate at 0x7fb281dc9d20>

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: expect_state('agent_count', 6) timed out after 5.0s — last value was 3

src/sase/ace/testing/wait.py:54: AssertionError
___________ test_agents_fleet_keyboard_focus_and_narrow_png_snapshot ___________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_fleet.py', test_line=183, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24cddd390>

    async def test_agents_fleet_keyboard_focus_and_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        summary_response = _fleet_visual_responses()
        facade = OfflineFleetFacade(
            summary_response=summary_response,
            catalog_response=summary_response,
        )
        patch_startup_loaders(monkeypatch, agents=agents())
        _patch_fleet_refresh(monkeypatch, facade=facade)
    
        async with AcePage(query='"visual"', patches=patches(), size=(82, 28)) as page:
            await _open_agents(page)
>           await _show_fleet(page, expected_count=6)

tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py:197: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py:78: in _show_fleet
    await page.expect_state("agent_count", expected_count)
src/sase/ace/testing/ace_page.py:428: in expect_state
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.expect_state.<locals>.predicate at 0x7fb266d3bed0>

    async def _poll_until[T](
        predicate: Callable[[], T | None],
        *,
        is_success: Callable[[T | None], bool],
        settle: Callable[[], Awaitable[None]],
        timeout: float,
        timeout_message: Callable[[], str],
        clock: Callable[[], float] | None = None,
        sleep: Callable[[float], Awaitable[None]] | None = None,
        backoff_after_misses: int = _BACKOFF_AFTER_MISSES,
        backoff_seconds: float = _BACKOFF_SECONDS,
    ) -> T | None:
        """Poll a predicate with event-driven settling and a bounded backoff."""
    
        if clock is None:
            clock = asyncio.get_running_loop().time
        if sleep is None:
            sleep = asyncio.sleep
    
        deadline = clock() + timeout
        misses = 0
        while True:
            value = predicate()
            if is_success(value):
                return value
            if clock() >= deadline:
>               raise AssertionError(timeout_message())
E               AssertionError: expect_state('agent_count', 6) timed out after 5.0s — last value was 3

src/sase/ace/testing/wait.py:54: AssertionError
______________________ test_running_fallback_png_snapshot ______________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._agents_retry.py', test_line=74, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67be1ad010>

    async def test_running_fallback_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = [
            retry_agent(
                name="fallback",
                status="RUNNING",
                start_time=datetime(2026, 7, 6, 11, 59, 0),
                raw_suffix="20260706115900",
                retry_status="running_fallback",
                retry_count=2,
                max_retries=2,
                using_fallback=True,
                fallback_model="claude-sonnet-4-5",
            )
        ]
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=1)
    
            await wait_for_svg_contains(page, "claude-sonnet-4-5")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "RUNNING")
            assert_page_svg_contains(page, "↻2▸sonnet")
            assert_page_svg_contains(page, "Fallback:")
            assert_page_svg_contains(page, "claude-sonnet-4-5")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_running_fallback_120x40",
                title="ACE agents running fallback",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py:102: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_running_fallback_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x8dBIDA...x00\x00\x00\x1c~\xf6\x14\x8f\xfe\xe2\xf1xt\xdc\xd9j\x80\xff\x1f\nG\xde\x16\'\x81\xe4\x84\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_running_fallback_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_running_fallback_png_snapshot/agents_retry_running_fallback_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_running_fallback_png_snapshot/agents_retry_running_fallback_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_running_fallback_png_snapshot/agents_retry_running_fallback_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_running_fallback_png_snapshot/agents_retry_running_fallback_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________________ test_completed_retry_chain_png_snapshot ____________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_retry.py', test_line=109, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67bf7a0e50>

    async def test_completed_retry_chain_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        root_suffix = "20260706114500"
        retry_one_suffix = "20260706115000"
        retry_two_suffix = "20260706115500"
        rows = [
            retry_agent(
                name="chain",
                status="FAILED (RETRIED)",
                start_time=datetime(2026, 7, 6, 11, 45, 0),
                stop_time=datetime(2026, 7, 6, 11, 46, 0),
                raw_suffix=root_suffix,
                retry_chain_root_timestamp=root_suffix,
                retried_as_timestamp=retry_one_suffix,
                retry_terminal=True,
            ),
            retry_agent(
                name="chain",
                status="FAILED (RETRIED)",
                start_time=datetime(2026, 7, 6, 11, 50, 0),
                stop_time=datetime(2026, 7, 6, 11, 51, 0),
                raw_suffix=retry_one_suffix,
                retry_attempt=1,
                retry_of_timestamp=root_suffix,
                retry_chain_root_timestamp=root_suffix,
                retried_as_timestamp=retry_two_suffix,
                retry_terminal=True,
            ),
            retry_agent(
                name="chain",
                status="DONE",
                start_time=datetime(2026, 7, 6, 11, 55, 0),
                stop_time=datetime(2026, 7, 6, 11, 57, 0),
                raw_suffix=retry_two_suffix,
                retry_attempt=2,
                retry_of_timestamp=retry_one_suffix,
                retry_chain_root_timestamp=root_suffix,
            ),
        ]
        _apply_status_overrides(rows, classify_diff_badges=False)
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=3)
    
            await wait_for_svg_contains(page, "(RETRIED)")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "(RETRIED)")
            assert_page_svg_contains(page, "↳")
            assert_page_svg_contains(page, "↻1")
            assert_page_svg_contains(page, "↻2")
            assert_page_svg_contains(page, "DONE")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_completed_chain_120x40",
                title="ACE agents completed retry chain",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py:163: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_completed_chain_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x0e\xe6...08!\x84\x10B\x08!\x84\x10B\x0c?\x8eF\xaf\x9e\xe8\xf5\x1a\x89;\x936\xf8\xff`\xc9G\xa7gn(K\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_completed_chain_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_completed_retry_chain_png_snapshot/agents_retry_completed_chain_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_completed_retry_chain_png_snapshot/agents_retry_completed_chain_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_completed_retry_chain_png_snapshot/agents_retry_completed_chain_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_completed_retry_chain_png_snapshot/agents_retry_completed_chain_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________ test_agents_leader_jump_auto_expands_panel_png_snapshot ____________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...gents_panels.py', test_line=435, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5c981010>

    async def test_agents_leader_jump_auto_expands_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agents = _panel_auto_expand_agents()
        target = agents[2]
        patch_startup_loaders(monkeypatch, agents=agents)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
    
            await page.press("h")
            await page.press("k")
            assert page.app._panel_group.focused_key == "chop"
            await page.press("l")
            await page.wait_for(
                lambda _screen: (
                    not effective_panel_collapses(
                        page.app, page.app._panel_group.panel_keys
                    )
                )
            )
            await page.press("l")
            await page.press("j")
            assert page.app._agents[page.app.current_idx].identity == target.identity
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            page.app._unread_completed_agent_ids.add(target.identity)
    
            await page.press("comma")
            await page.press("j")
            await page.wait_for(lambda _screen: page.app._resolve_focused_panel() is None)
    
            assert page.app._agents[page.app.current_idx].identity == target.identity
            assert target.identity not in page.app._unread_completed_agent_ids
            focused_idx = page.app._panel_group.focused_idx
            widget_id = (
                "#agent-list-panel"
                if focused_idx == 0
                else f"#agent-list-panel-{focused_idx}"
            )
            target_widget = page.app.query_one(widget_id, AgentList)
            assert "❖" not in Text.from_markup(target_widget.border_title).plain
            assert target_widget.highlighted is not None
    
            assert page.app._restore_agents_jump_anchor() is True
            page.app._unread_completed_agent_ids.add(target.identity)
            await page.press("h")
            await page.wait_for(lambda _screen: "chop" in page.app._collapsed_panel_keys)
            assert page.app._panel_group.panel_keys == [None, "keep", "chop"]
    
            await page.press("comma")
            await page.press("j")
            await page.wait_for(
                lambda _screen: "chop" not in page.app._collapsed_panel_keys
            )
            await wait_for_visual_idle(page)
    
            assert page.app._panel_group.panel_keys == [None, "chop", "keep"]
            assert page.app._panel_group.focused_key == "chop"
            assert page.app.current_idx == 2
            assert page.app._agents[page.app.current_idx].identity == target.identity
            assert target.identity not in page.app._unread_completed_agent_ids
            target_widget = page.app.query_one("#agent-list-panel-1")
            assert target_widget.highlighted is not None
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_leader_jump_auto_expanded_panel_120x40",
                title="ACE agents leader jump auto-expanded panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:506: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_leader_jump_auto_expanded_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x05\x1a...4\x10B\x08!\x85\xc7y\xfd\xea\xd5\xaf\xf7\xb1q\xa7\xd7\x01\xff\x05B\xb2\xa6\x85\x02JM\xaa\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_leader_jump_auto_expanded_panel_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panels.py__test_agents_leader_jump_auto_expands_panel_png_snapshot/agents_leader_jump_auto_expanded_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panels.py__test_agents_leader_jump_auto_expands_panel_png_snapshot/agents_leader_jump_auto_expanded_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panels.py__test_agents_leader_jump_auto_expands_panel_png_snapshot/agents_leader_jump_auto_expanded_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_panels.py__test_agents_leader_jump_auto_expands_panel_png_snapshot/agents_leader_jump_auto_expanded_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________________ test_agents_commit_messages_panel_png_snapshot ________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...linked_repos.py', test_line=239, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060e13d940>

    async def test_agents_commit_messages_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_commit_diff_display_paths(monkeypatch)
        agent = _linked_repo_commits_agent()
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
            await _wait_for_commit_delta_summary(page, agent)
            for _ in range(6):
                await page.press("ctrl+f")
                await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "Deltas:")
            assert_page_svg_contains(page, "agent_deltas.py")
            assert_page_svg_contains(page, "file_panel.py")
            assert_page_svg_contains(page, "sase-core")
            assert_page_svg_contains(page, "files [1/3]")
            assert_page_svg_contains(page, "visual_project 1234567890ab")
            assert_page_svg_contains(page, "primary_001.diff")
>           ace_png_visual.assert_page_png(
                page,
                "agents_commit_messages_panel_120x40",
                title="ACE agents commit deltas and file panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:265: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_commit_messages_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02%\x84IDA...x00\x00\x80\xe1\xe7p\xf4\xe8\x8a\x1e/i\xe2\xce\xa4\x05\xfe\x7f\x0c\xc3\xe2<\xab/\xd0\xde\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_commit_messages_panel_120x40.png
E       Changed pixels: 2732/1520532 (0.179674%); materially changed pixels: 2731/1520532 (0.179608%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_commit_messages_panel_png_snapshot/agents_commit_messages_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_commit_messages_panel_png_snapshot/agents_commit_messages_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_commit_messages_panel_png_snapshot/agents_commit_messages_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_commit_messages_panel_png_snapshot/agents_commit_messages_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_____________________ test_retries_exhausted_png_snapshot ______________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_retry.py', test_line=170, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67d8a125f0>

    async def test_retries_exhausted_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        rows = [
            retry_agent(
                name="exhausted",
                status="FAILED",
                start_time=datetime(2026, 7, 6, 11, 50, 0),
                stop_time=datetime(2026, 7, 6, 11, 59, 0),
                raw_suffix="20260706115000",
                retry_count=3,
                max_retries=3,
                retry_terminal=True,
            )
        ]
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=1)
    
            await wait_for_svg_contains(page, "3/3")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "FAILED")
            assert_page_svg_contains(page, "Retries:")
            assert_page_svg_contains(page, "3/3")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_exhausted_120x40",
                title="ACE agents retries exhausted",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py:196: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_exhausted_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xa5\xff...x00\x00\x00\x00\x00\xec\x7fvv~\xb6u~~\x98\x8e;\xfb\r\xf0\xff\x07\xce\x04\xf7\n\x13y2\xf1\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_exhausted_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retries_exhausted_png_snapshot/agents_retry_exhausted_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retries_exhausted_png_snapshot/agents_retry_exhausted_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retries_exhausted_png_snapshot/agents_retry_exhausted_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retries_exhausted_png_snapshot/agents_retry_exhausted_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________ test_selected_clan_collapses_before_open_sibling_png_snapshot _________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...clan_collapse.py', test_line=84, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25f8bec10>

    async def test_selected_clan_collapses_before_open_sibling_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 22, 9, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_group_clan_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.press("o", "s")
            assert page.app._grouping_mode is GroupingMode.BY_STATUS
    
            clans = {
                agent.agent_clan: agent
                for agent in page.app._agents_with_children
                if agent.is_clan_container and agent.agent_clan in {"sase-8k", "sase-8l"}
            }
            selected_clan = clans["sase-8k"]
            sibling_clan = clans["sase-8l"]
            selected_key = agent_fold_key(selected_clan)
            sibling_key = agent_fold_key(sibling_clan)
            assert selected_key is not None and sibling_key is not None
            page.app._fold_manager.expand(selected_key)
            page.app._fold_manager.expand(sibling_key)
            page.app._refilter_agents(refresh_content_index=False)
    
            selected_member = next(
                agent for agent in page.app._agents if agent.cl_name == "sase-8k.plan"
            )
            page.app._panel_group.focused_idx = page.app._panel_group.panel_keys.index(
                "epic"
            )
            page.app._collapsed_panel_keys.discard("epic")
            page.app._expanded_panel_keys.add("epic")
            page.app._expanded_panel_focus = False
            page.app.current_idx = page.app._agents.index(selected_member)
            page.app._current_group_key = None
            page.app._refresh_agents_display(list_changed=True)
            await wait_for_visual_idle(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse clan") in footer._last_layout_inputs[0]
            registry = page.app._group_fold_registry.for_panel("epic")
            assert page.app._fold_manager.get(selected_key) is FoldLevel.EXPANDED
            assert page.app._fold_manager.get(sibling_key) is FoldLevel.EXPANDED
            assert not registry.is_collapsed(("Running",))
    
            await page.press("H")
            await wait_for_visual_idle(page)
    
            selected = page.app._agents[page.app.current_idx]
            assert selected.identity == selected_clan.identity
            assert page.app._fold_manager.get(selected_key) is FoldLevel.COLLAPSED
            assert page.app._fold_manager.get(sibling_key) is FoldLevel.EXPANDED
            assert not registry.is_collapsed(("Running",))
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse clans") in footer._last_layout_inputs[0]
>           ace_png_visual.assert_page_png(
                page,
                "agents_selected_clan_collapse_precedence_120x40",
                title="ACE selected clan collapse before sibling clans",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py:144: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_selected_clan_collapse_precedence_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x12"IDA...8!\x84\x10B\x081\xf68\x1c\xbd\x86\xa2\xd7\xab$\xeeL:\xe0\xff\x03W\xed\xda\r-\xa3\xa3\x84\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_selected_clan_collapse_precedence_120x40.png
E       Changed pixels: 2640/1520532 (0.173623%); materially changed pixels: 2636/1520532 (0.173360%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_selected_clan_collapses_before_open_sibling_png_snapshot/agents_selected_clan_collapse_precedence_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________ test_agent_pending_plan_status_colors_png_snapshot ______________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...pending_plans.py', test_line=40, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5e9cbb60>

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
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_pending_plan_status_colors_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x12\xfc...84\x10B\xca\x8f\x13\xfa\x13\xd3\x9f\xbd\x08\xdc\x19\x94\xe0\xff\x03&=\xac\xc3\xca\x08\t.\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_pending_plan_status_colors_120x40.png
E       Changed pixels: 2726/1520532 (0.179279%); materially changed pixels: 2722/1520532 (0.179016%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_pending_plans.py__test_agent_pending_plan_status_colors_png_snapshot/agents_pending_plan_status_colors_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_selected_retry_metadata_png_snapshot ___________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_retry.py', test_line=203, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67bca16580>

    async def test_selected_retry_metadata_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        history = [
            AttemptRecord(
                attempt_number=1,
                status="failed",
                start_epoch=datetime(2026, 7, 6, 11, 54, 0).timestamp(),
                end_epoch=datetime(2026, 7, 6, 11, 55, 0).timestamp(),
                model="gpt-5",
                used_fallback=False,
                error_snippet="provider capacity exhausted",
                error_full="provider capacity exhausted",
                live_reply_path="/workspace/sase/artifacts/attempts/1/live_reply.md",
                timestamps_path=(
                    "/workspace/sase/artifacts/attempts/1/live_reply_timestamps.jsonl"
                ),
            )
        ]
        rows = [
            retry_agent(
                name="metadata",
                status="RUNNING",
                start_time=datetime(2026, 7, 6, 11, 56, 0),
                raw_suffix="20260706115600",
                retry_status="running_retry",
                retry_count=1,
                max_retries=3,
                using_fallback=True,
                fallback_model="claude-sonnet-4-5",
                attempt_history=history,
            )
        ]
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=1)
    
            await wait_for_svg_contains(page, "Attempt 1")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "Retries:")
            assert_page_svg_contains(page, "1/3")
            assert_page_svg_contains(page, "Attempt 1")
            assert_page_svg_contains(page, "failed:")
            assert_page_svg_contains(page, "Fallback:")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_selected_detail_120x40",
                title="ACE agents selected retry metadata",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py:249: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_selected_detail_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xb8\x89...x00\x00\xcc=\x07\x8a\xaf\xfe\xe2\xeb\x91\x18\xb8\xb3\xd5\x04\xff\x7fw\x9dU\xe7\x1dP.\xd9\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_selected_detail_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_selected_retry_metadata_png_snapshot/agents_retry_selected_detail_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_selected_retry_metadata_png_snapshot/agents_retry_selected_detail_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_selected_retry_metadata_png_snapshot/agents_retry_selected_detail_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_selected_retry_metadata_png_snapshot/agents_retry_selected_detail_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________ test_group_clan_collapse_precedes_status_banner_png_snapshot _________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...lan_collapse.py', test_line=151, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24f868210>

    async def test_group_clan_collapse_precedes_status_banner_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 22, 9, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_group_clan_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.press("o", "s")
            assert page.app._grouping_mode is GroupingMode.BY_STATUS
    
            clans = {
                agent.agent_clan: agent
                for agent in page.app._agents_with_children
                if agent.is_clan_container and agent.agent_clan in {"sase-8k", "sase-8l"}
            }
            open_clan = clans["sase-8k"]
            selected_clan = clans["sase-8l"]
            open_key = agent_fold_key(open_clan)
            selected_key = agent_fold_key(selected_clan)
            assert open_key is not None and selected_key is not None
            page.app._fold_manager.expand(open_key)
            page.app._refilter_agents(refresh_content_index=False)
    
            selected_clan = next(
                agent
                for agent in page.app._agents
                if agent.is_clan_container and agent.agent_clan == "sase-8l"
            )
            selected_identity = selected_clan.identity
            page.app._panel_group.focused_idx = page.app._panel_group.panel_keys.index(
                "epic"
            )
            page.app._collapsed_panel_keys.discard("epic")
            page.app._expanded_panel_keys.add("epic")
            page.app._expanded_panel_focus = False
            page.app.current_idx = page.app._agents.index(selected_clan)
            page.app._current_group_key = None
            page.app._refresh_agents_display(list_changed=True)
            await wait_for_visual_idle(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse clans") in footer._last_layout_inputs[0]
            registry = page.app._group_fold_registry.for_panel("epic")
            assert page.app._fold_manager.get(open_key) is FoldLevel.EXPANDED
            assert page.app._fold_manager.get(selected_key) is FoldLevel.COLLAPSED
            assert not registry.is_collapsed(("Running",))
    
            await page.press("H")
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx].identity == selected_identity
            assert page.app._fold_manager.get(open_key) is FoldLevel.COLLAPSED
            assert page.app._fold_manager.get(selected_key) is FoldLevel.COLLAPSED
            assert not registry.is_collapsed(("Running",))
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse group") in footer._last_layout_inputs[0]
>           ace_png_visual.assert_page_png(
                page,
                "agents_group_clan_collapse_precedence_120x40",
                title="ACE group-wide clan collapse before status banner",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py:212: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_group_clan_collapse_precedence_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xd1\x9c...x00\x00\x00\x00\x00\x00p\xfb\x19\xb7?Y\xfbsQ\x0bw\x86\xed\xf0\x7fD\x96d\xab\x1b?\x99\x98\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_group_clan_collapse_precedence_120x40.png
E       Changed pixels: 2640/1520532 (0.173623%); materially changed pixels: 2636/1520532 (0.173360%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_group_clan_collapse_precedes_status_banner_png_snapshot/agents_group_clan_collapse_precedence_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_group_clan_collapse_precedes_status_banner_png_snapshot/agents_group_clan_collapse_precedence_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_group_clan_collapse_precedes_status_banner_png_snapshot/agents_group_clan_collapse_precedence_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_clan_collapse.py__test_group_clan_collapse_precedes_status_banner_png_snapshot/agents_group_clan_collapse_precedence_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_agent_workspace_tmux_modal_png_snapshot _________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...agents_modals.py', test_line=90, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060f625d30>

    async def test_agent_workspace_tmux_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=visual_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=(100, 28)) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            from sase.ace.tui.modals.agent_workspace_tmux_modal import (
                AgentWorkspaceTmuxModal,
            )
    
            page.app.push_screen(AgentWorkspaceTmuxModal(_workspace_tmux_choices()))
            await page.expect_modal("AgentWorkspaceTmuxModal")
            await wait_for_svg_contains(page, "Tmux Workspace")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "Tmux Workspace")
            assert_page_svg_contains(page, "CURRENT")
            assert_page_svg_contains(page, "LINKED")
            assert_page_svg_contains(page, "sase-core")
            assert_page_svg_contains(page, "Rust backend")
    
>           ace_png_visual.assert_page_png(
                page,
                "agent_workspace_tmux_modal_100x28",
                title="ACE agent workspace tmux modal",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_modals.py:118: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agent_workspace_tmux_modal_100x28'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\xd6\x00\x00\x02\xdd\x08\x06\x00\x00\x00\xe0b\xeeF\x00\x01\xe2-IDATx\...\r\x07\x0e\x1cx\xf1/\xfe\xc5\xbf\xc0:\xed\xdbHP\x9bM:\xe6\xff\x07\x19f\xdd\x9a\xa6jX\xb0\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agent_workspace_tmux_modal_100x28.png
E       Changed pixels: 1462/907454 (0.161110%); materially changed pixels: 1358/907454 (0.149649%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_agent_workspace_tmux_modal_png_snapshot/agent_workspace_tmux_modal_100x28/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_agent_workspace_tmux_modal_png_snapshot/agent_workspace_tmux_modal_100x28/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_agent_workspace_tmux_modal_png_snapshot/agent_workspace_tmux_modal_100x28/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_agent_workspace_tmux_modal_png_snapshot/agent_workspace_tmux_modal_100x28/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__ test_agents_proc_shell_list_png_snapshot[size0-agents_proc_shells_120x40] ___
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

size = (120, 40), snapshot_name = 'agents_proc_shells_120x40'
ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_proc_shells.py', test_line=77, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab59bc2900>

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "agents_proc_shells_120x40"),
            ((90, 30), "agents_proc_shells_90x30"),
        ],
    )
    async def test_agents_proc_shell_list_png_snapshot(
        size: tuple[int, int],
        snapshot_name: str,
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, PROC_SHELL_VISUAL_NOW)
        patch_proc_shell_project_names(monkeypatch)
        patch_startup_loaders(monkeypatch, agents=proc_shell_visual_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=size) as page:
            await _seeded_agents_tab(page)
    
            _assert_procs_are_top_level_rows(page)
            _assert_info_header_proc_badge(page)
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "❯")
            assert_page_svg_contains(page, "[bash]")
            assert_page_svg_contains(page, "[python]")
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title="ACE agents stand-alone proc shells",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_proc_shells.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_proc_shells_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02\x92\xf6...00\x000\xfd\xec*~z\x8b\x9f_G\xc7\x9d\xad\x06\xf8\x7f\x01\xe5\x8a\xe3\xf9\xa5\x10\xc5\x0c\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_proc_shells_120x40.png
E       Changed pixels: 2746/1520532 (0.180595%); materially changed pixels: 2743/1520532 (0.180397%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size0-agents_proc_shells_120x40/agents_proc_shells_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size0-agents_proc_shells_120x40/agents_proc_shells_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size0-agents_proc_shells_120x40/agents_proc_shells_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size0-agents_proc_shells_120x40/agents_proc_shells_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________ test_group_lane_collapse_precedes_status_banner_png_snapshot _________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...lane_collapse.py', test_line=31, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb25d484ad0>

    async def test_group_lane_collapse_precedes_status_banner_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 22, 7, 15, 0))
        patch_startup_loaders(
            monkeypatch,
            agents=group_lane_collapse_precedence_agents(),
        )
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.press("o", "s")
            assert page.app._grouping_mode is GroupingMode.BY_STATUS
    
            roots = {
                agent.agent_name: agent
                for agent in page.app._agents_with_children
                if agent.agent_name in {"hu", "ht", "hs"} and not agent.is_child_row
            }
            hu = roots["hu"]
            ht_key = agent_fold_key(roots["ht"])
            hs_key = agent_fold_key(roots["hs"])
            assert ht_key is not None and hs_key is not None
            page.app._fold_manager.expand(ht_key)
            page.app._fold_manager.expand(hs_key)
            page.app._fold_manager.expand(hs_key)
            page.app._refilter_agents(refresh_content_index=False)
            page.app.current_idx = page.app._agents.index(hu)
            page.app._current_group_key = None
            page.app._refresh_agents_display(list_changed=True)
            await page.expect_state("agent_count", 5)
            await wait_for_visual_idle(page)
    
            footer = page.app.query_one("#keybinding-footer", KeybindingFooter)
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse sase agents") in footer._last_layout_inputs[0]
    
            await page.press("H")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            assert page.app._agents[page.app.current_idx] is hu
            assert page.app._fold_manager.get(ht_key) is FoldLevel.COLLAPSED
            assert page.app._fold_manager.get(hs_key) is FoldLevel.COLLAPSED
            running_registry = page.app._group_fold_registry.for_panel(None)
            assert not running_registry.is_collapsed(("Running",))
            assert footer._last_layout_inputs is not None
            assert ("H", "collapse group") in footer._last_layout_inputs[0]
>           ace_png_visual.assert_page_png(
                page,
                "agents_group_lane_collapse_precedence_120x40",
                title="ACE group-wide lane collapse before status banner",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_group_lane_collapse.py:82: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_group_lane_collapse_precedence_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\x9f\xf0...0\x00\x00\x00`\xf6\xd9[<\xfa\x8b\xc7c\xd1qg\xab\x01\xfe\x7f\x9f\xc2\x17\xc5\x9a\x82\xa1T\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_group_lane_collapse_precedence_120x40.png
E       Changed pixels: 2611/1520532 (0.171716%); materially changed pixels: 2607/1520532 (0.171453%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_lane_collapse.py__test_group_lane_collapse_precedes_status_banner_png_snapshot/agents_group_lane_collapse_precedence_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_lane_collapse.py__test_group_lane_collapse_precedes_status_banner_png_snapshot/agents_group_lane_collapse_precedence_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_lane_collapse.py__test_group_lane_collapse_precedes_status_banner_png_snapshot/agents_group_lane_collapse_precedence_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_group_lane_collapse.py__test_group_lane_collapse_precedes_status_banner_png_snapshot/agents_group_lane_collapse_precedence_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___ test_agents_proc_shell_list_png_snapshot[size1-agents_proc_shells_90x30] ___
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

size = (90, 30), snapshot_name = 'agents_proc_shells_90x30'
ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...s_proc_shells.py', test_line=77, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab49a0b230>

    @pytest.mark.parametrize(
        ("size", "snapshot_name"),
        [
            ((120, 40), "agents_proc_shells_120x40"),
            ((90, 30), "agents_proc_shells_90x30"),
        ],
    )
    async def test_agents_proc_shell_list_png_snapshot(
        size: tuple[int, int],
        snapshot_name: str,
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, PROC_SHELL_VISUAL_NOW)
        patch_proc_shell_project_names(monkeypatch)
        patch_startup_loaders(monkeypatch, agents=proc_shell_visual_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=size) as page:
            await _seeded_agents_tab(page)
    
            _assert_procs_are_top_level_rows(page)
            _assert_info_header_proc_badge(page)
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "❯")
            assert_page_svg_contains(page, "[bash]")
            assert_page_svg_contains(page, "[python]")
    
>           ace_png_visual.assert_page_png(
                page,
                snapshot_name,
                title="ACE agents stand-alone proc shells",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_proc_shells.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_proc_shells_90x30'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\\\x00\x00\x03\x0e\x08\x06\x00\x00\x00#\x98\x12\xbb\x00\x02%\xa7IDATx...x84\x98%$\x93\x08!\xf2`\xdc\xbd\xc6\xdc\xeb\x14\x01r\xd3N\xf8?\x04W7\x08\x0c\x17\x0e\xd5\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_proc_shells_90x30.png
E       Changed pixels: 2497/872712 (0.286120%); materially changed pixels: 2494/872712 (0.285776%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size1-agents_proc_shells_90x30/agents_proc_shells_90x30/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size1-agents_proc_shells_90x30/agents_proc_shells_90x30/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size1-agents_proc_shells_90x30/agents_proc_shells_90x30/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_proc_shells.py__test_agents_proc_shell_list_png_snapshot_size1-agents_proc_shells_90x30/agents_proc_shells_90x30/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________ test_real_fakey_retry_countdown_png_snapshot _________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...nts_retry_e2e.py', test_line=64, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_fakey_retry_countdow0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67bca15fd0>

    async def test_real_fakey_retry_countdown_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        harness = FakeyRetryHarness(
            tmp_path,
            monkeypatch,
            wait_times=[30],
            expose_to_agent_loader=True,
            artifacts_timestamp="20260706115800",
            is_home_mode=True,
        )
        harness.seed_running_agent(started_at=datetime(2026, 7, 6, 11, 58, 0))
        harness.use_scenario(
            monkeypatch,
            [retryable_failure(), successful_attempt("retry recovered")],
        )
        retry_wait = harness.barrier("retry-wait")
        harness.hold_retry_wait(monkeypatch, retry_wait)
        patch_startup_loaders(monkeypatch, use_real_agent_loader=True)
    
        handle = harness.run_in_background()
        try:
            harness.wait_for_retry_state("retrying")
            retry_wait.wait_until_started()
            harness.normalize_visual_timestamps(_VISUAL_NOW, countdown_seconds=9)
            _patch_sentinel_pid_liveness(monkeypatch)
            monkeypatch.setattr(time, "time", lambda: _VISUAL_NOW.timestamp())
    
            async with AcePage(query='"fakey"', patches=patches()) as page:
                await _open_agents_tab(page, agent_count=1)
    
                loaded = page.app._agents[0]
                assert (loaded.status, loaded.retry_status) == ("RETRYING", "retrying")
                await wait_for_svg_contains(page, "RETRYING (9s)")
                await wait_for_visual_idle(page)
                assert_page_svg_contains(page, "RETRYING (9s)")
                assert_page_svg_contains(page, "Retries:")
                assert_page_svg_contains(page, "1/1")
>               ace_png_visual.assert_page_png(
                    page,
                    "agents_retry_e2e_countdown_120x40",
                    title="ACE real fakey retry countdown",
                )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_e2e_countdown_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02]\x11IDA...x00\x00\x00\x00\x00\x00`\xe4q$\xf9\xf4&\x9f\x97\xb5qg\xda\t\xff?\xa5\xab\']\xb1\xd7Z\xa8\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_e2e_countdown_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_retry_countdown_png_snapshot/agents_retry_e2e_countdown_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_retry_countdown_png_snapshot/agents_retry_e2e_countdown_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_retry_countdown_png_snapshot/agents_retry_e2e_countdown_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_retry_countdown_png_snapshot/agents_retry_e2e_countdown_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:278: AssertionError
----------------------------- Captured stdout call -----------------------------
╭────── 🤖 Workflow-Tmp_260917_213223-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

✅ Waiting for Fakey completed in 00:00╭─────── 🤖 Workflow-Tmp_260917_213223-Main [Big]_Error Agent - Prompt ────────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_213223-Main [Big]_Error Agent - Response ───────╮
│                                                                              │
│  Error running LLM provider command (exit code 1)                            │
│  stderr: FAKEY-RETRYABLE: temporary fakey outage                             │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_213229-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Your previous attempt hit a model context limit or transient provider       │
│  failure. Any file edits, new tests, and other on-disk changes you made are  │
│  preserved. Before making additional changes, run `git status` and `git      │
│  diff` to see what is already in place, then continue implementing the plan  │
│  from wherever you left off. Do not re-apply edits that are already          │
│  present.                                                                    │
│                                                                              │
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
retry recovered

✅ Waiting for Fakey completed in 00:00
Chat history saved to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_fakey_retry_countdow0/sase-home/chats/202607/fakey_e2e-ace_run-fakey_e2e-260706_115800.md
Preparing PDFs from Markdown... found 0, cap 10
[PDF] preparing Markdown PDFs (0 source(s), cap 10)
[PDF] complete: 0 generated, 0 skipped
[artifacts] default capture: stored=0 referenced=0 skipped=0 declared=0 cap_fired=false
Done marker written to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_fakey_retry_countdow0/sase-home/projects/home/artifacts/ace-run/20260706115800/done.json
----------------------------- Captured stderr call -----------------------------
FAKEY-RETRYABLE: temporary fakey outage
/home/bryan/bin/bam: line 3: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/home47/lib/bugyi.sh: No such file or directory
_____________ test_agents_linked_repo_diff_file_panel_png_snapshot _____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...linked_repos.py', test_line=209, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb24ed674d0>

    async def test_agents_linked_repo_diff_file_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        agent = _linked_repo_diff_agent()
        _seed_linked_repo_visual_delta(monkeypatch, agent)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "sase-core")
            assert_page_svg_contains(page, "linked repo")
            assert_page_svg_contains(page, "/workspace/sase-core_14")
            file_scroll = page.app.query_one("#agent-file-scroll", VerticalScroll)
            prompt_scroll = page.app.query_one("#agent-prompt-scroll", VerticalScroll)
            file_scroll.show_vertical_scrollbar = False
            prompt_scroll.show_vertical_scrollbar = False
            await wait_for_visual_idle(page)
>           ace_png_visual.assert_page_png(
                page,
                "agents_linked_repo_diff_file_panel_120x40",
                title="ACE agents linked repo diff file panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:232: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_linked_repo_diff_file_panel_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02T,IDATx\...\x00\x00\x00\x00\x80\xc1\xe7D\xf0j\x0f^o\xa9\xe3\xce\xa8\x01\xfe/\xb4~\xb4\x1d\xbd\x12?M\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_linked_repo_diff_file_panel_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_linked_repo_diff_file_panel_png_snapshot/agents_linked_repo_diff_file_panel_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_linked_repo_diff_file_panel_png_snapshot/agents_linked_repo_diff_file_panel_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_linked_repo_diff_file_panel_png_snapshot/agents_linked_repo_diff_file_panel_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_linked_repos.py__test_agents_linked_repo_diff_file_panel_png_snapshot/agents_linked_repo_diff_file_panel_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
_________________________ test_wait_modal_png_snapshot _________________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...gents_modals.py', test_line=125, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0622e97930>

    async def test_wait_modal_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=visual_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=(100, 32)) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            from sase.ace.tui.modals.wait_modal import WaitAgentCandidate, WaitModal
    
            page.app.push_screen(
                WaitModal(
                    current_wait_duration=300.0,
                    candidates=[
                        WaitAgentCandidate(
                            wait_name="visual.plan.review.contract.snapshot",
                            label="visual.plan.review.contract.snapshot",
                            status="RUNNING",
                            model="codex / gpt-5",
                            start_time="13:00",
                            duration="4m",
                            role="root",
                        ),
                        WaitAgentCandidate(
                            wait_name="visual.code.implementation.with.narrow.row",
                            label="visual.code.implementation.with.narrow.row",
                            status="DONE",
                            model="claude / sonnet",
                            start_time="13:08",
                            duration="4m30s",
                            tribe="@epic",
                        ),
                        WaitAgentCandidate(
                            wait_name="visual.verify.performance.and.polish",
                            label="visual.verify.performance.and.polish",
                            status="FAILED",
                            model="codex / gpt-5",
                            start_time="13:16",
                            duration="1m05s",
                            tribe="verification",
                        ),
                    ],
                )
            )
            await page.expect_modal("WaitModal")
            await wait_for_svg_contains(page, "visual.plan.revi")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "Wait")
            assert_page_svg_contains(page, "5m")
            assert_page_svg_contains(page, "visual.plan.revi")
    
>           ace_png_visual.assert_page_png(
                page,
                "wait_modal_100x32",
                title="ACE wait modal",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_modals.py:182: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'wait_modal_100x32'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\xd6\x00\x00\x03?\x08\x06\x00\x00\x00\x1d\x99_{\x00\x01\x85\x13IDATx\...00\x00\xb6\xa3\xedP\xf8\xa2\xca\xb4\x85H$\x92q\xc0\xcf\xff\x03\xfeS\x86\xd2\xa0 \xf8\xb0\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/wait_modal_100x32.png
E       Changed pixels: 760/1028778 (0.073874%); materially changed pixels: 712/1028778 (0.069208%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_png_snapshot/wait_modal_100x32/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_png_snapshot/wait_modal_100x32/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_png_snapshot/wait_modal_100x32/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_png_snapshot/wait_modal_100x32/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________ test_real_loader_plan_family_retry_countdown_png_snapshot ___________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_retry_e2e.py', test_line=125, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_loader_plan_family_r0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67c0930440>

    async def test_real_loader_plan_family_retry_countdown_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A failed coder attempt cannot conceal its live family's backoff."""
        sase_home = tmp_path / ".sase"
        monkeypatch.setenv("SASE_HOME", str(sase_home))
        now_epoch = _VISUAL_NOW.timestamp()
        build_retrying_plan_family(
            sase_home,
            next_retry_at_epoch=now_epoch + 9,
        )
        _patch_sentinel_pid_liveness(monkeypatch)
        monkeypatch.setattr(time, "time", lambda: now_epoch)
        monkeypatch.setattr(
            "sase.ace.tui.widgets.prompt_panel._agent_display_async."
            "should_refresh_detail_header_summary",
            lambda *_args: False,
        )
        patch_startup_loaders(monkeypatch, use_real_agent_loader=True)
    
        async with AcePage(query='"retry-family"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=1)
    
            loaded = page.app._agents[0]
            assert (loaded.status, loaded.retry_status) == ("RETRYING", "retrying")
            assert (loaded.retry_count, loaded.max_retries) == (2, 3)
            await wait_for_svg_contains(page, "RETRYING (9s)")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "RETRYING (9s)")
            assert_page_svg_contains(page, "Retries:")
            assert_page_svg_contains(page, "2/3")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_e2e_plan_family_countdown_120x40",
                title="ACE real-loader plan family retry countdown",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py:158: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_e2e_plan_family_countdown_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01\xfc"IDA...\x8a\xa2(\x8a2\xf48\xee\xbfz\xfd\xd7n\x12w\x86m\xf0\xff\x01\xf0\x85\xba\xb7\x96\x0c\xe12\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_e2e_plan_family_countdown_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_loader_plan_family_retry_countdown_png_snapshot/agents_retry_e2e_plan_family_countdown_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_loader_plan_family_retry_countdown_png_snapshot/agents_retry_e2e_plan_family_countdown_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_loader_plan_family_retry_countdown_png_snapshot/agents_retry_e2e_plan_family_countdown_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_loader_plan_family_retry_countdown_png_snapshot/agents_retry_e2e_plan_family_countdown_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
__________________ test_wait_modal_beads_focused_png_snapshot __________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...gents_modals.py', test_line=189, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0606622900>

    async def test_wait_modal_beads_focused_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=visual_agents())
    
        async with AcePage(query='"visual"', patches=patches(), size=(100, 32)) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 3)
            await wait_for_visual_idle(page)
    
            from textual.widgets import Input
    
            from sase.ace.tui.modals.wait_modal import WaitModal
            from sase.ace.tui.models.wait_bead_catalog import (
                WaitBeadCandidate,
                WaitBeadCatalog,
            )
    
            catalog = WaitBeadCatalog(
                candidates=(
                    WaitBeadCandidate(
                        bead_id="sase-91.3",
                        title="Add bead picker to Wait modal",
                        status="in_progress",
                        type_label="task",
                        created_at="2026-07-01T00:00:00",
                        updated_at="2026-08-10T00:00:00",
                    ),
                    WaitBeadCandidate(
                        bead_id="sase-91.4",
                        title="Regenerate wait modal snapshot",
                        status="ready",
                        type_label="task",
                        created_at="2026-07-02T00:00:00",
                        updated_at="2026-08-09T00:00:00",
                    ),
                    WaitBeadCandidate(
                        bead_id="sase-88",
                        title="Bead store performance sweep",
                        status="open",
                        type_label="plan",
                        created_at="2026-06-01T00:00:00",
                        updated_at="2026-08-05T00:00:00",
                    ),
                ),
                available=True,
            )
    
            modal = WaitModal(
                current_waiting_for_beads=["sase-91.3"],
                bead_project_key="visual-project",
                bead_catalog_loader=lambda project_key, **_: catalog,
            )
            page.app.push_screen(modal)
            await page.expect_modal("WaitModal")
            await wait_for_svg_contains(page, "Wait")
    
            beads_input = modal.query_one("#beads-input", Input)
            beads_input.focus()
            await wait_for_state(
                page,
                lambda: beads_input.has_focus,
                description="beads input focus",
            )
            # Trailing comma clears the active completion fragment so the full
            # candidate list renders, with "sase-91.3" still marked selected.
            beads_input.value = "sase-91.3, "
            await wait_for_svg_contains(page, "sase-91.4")
            await wait_for_visual_idle(page)
    
            assert_page_svg_contains(page, "sase-91.3")
            assert_page_svg_contains(page, "sase-91.4")
            assert_page_svg_contains(page, "selected")
    
>           ace_png_visual.assert_page_png(
                page,
                "wait_modal_beads_focused_100x32",
                title="ACE wait modal beads focused",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_modals.py:266: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'wait_modal_beads_focused_100x32'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x04\xd6\x00\x00\x03?\x08\x06\x00\x00\x00\x1d\x99_{\x00\x01\xa31IDATx\x9c...\x00\xc0Z\xb4\x16\n_T\x996\x13\x89D\xb2\x0e\xf8\xf9\xbf\x01\xf5\x1c\xe8C\x8a\xdd\xc1\x1d\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/wait_modal_beads_focused_100x32.png
E       Changed pixels: 760/1028778 (0.073874%); materially changed pixels: 712/1028778 (0.069208%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_beads_focused_png_snapshot/wait_modal_beads_focused_100x32/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_beads_focused_png_snapshot/wait_modal_beads_focused_100x32/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_beads_focused_png_snapshot/wait_modal_beads_focused_100x32/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_modals.py__test_wait_modal_beads_focused_png_snapshot/wait_modal_beads_focused_100x32/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
___________________ test_agents_neighbor_badge_png_snapshot ____________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_neighbors.py', test_line=229, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f060d64c440>

    async def test_agents_neighbor_badge_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=hood_neighbor_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_svg_contains(page, "neighbors: ")
            await wait_for_visual_idle(page)
            neighbor_index = page.app._agent_neighbor_index()
            assert neighbor_index.neighbor_count(page.app.current_idx) == 3
            assert_page_svg_contains(page, "neighbors: ")
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_neighbor_badge_120x40",
                title="ACE agents neighbor badge",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py:246: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_neighbor_badge_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02G\xbfIDA...10BH\xf1\xd1\xaf_\xbd\xfa\xf5\x1e\x16\xee\xf4\xdb\xe0\xff\x07\n\xb8Y\xec\x9f\xf5\x86\xa9\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_neighbor_badge_120x40.png
E       Changed pixels: 2745/1520532 (0.180529%); materially changed pixels: 2744/1520532 (0.180463%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_badge_png_snapshot/agents_neighbor_badge_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_badge_png_snapshot/agents_neighbor_badge_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_badge_png_snapshot/agents_neighbor_badge_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_neighbors.py__test_agents_neighbor_badge_png_snapshot/agents_neighbor_badge_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
______________________ test_retry_countdown_png_snapshot _______________________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..._agents_retry.py', test_line=39, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab5eab4fa0>

    async def test_retry_countdown_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        now_epoch = _VISUAL_NOW.timestamp()
        monkeypatch.setattr(time, "time", lambda: now_epoch)
        rows = [
            retry_agent(
                name="countdown",
                status="RETRYING",
                start_time=datetime(2026, 7, 6, 11, 58, 0),
                raw_suffix="20260706115800",
                retry_status="retrying",
                retry_count=1,
                max_retries=3,
                retry_next_at_epoch=now_epoch + 9,
            )
        ]
        patch_startup_loaders(monkeypatch, agents=rows)
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _open_agents_tab(page, agent_count=1)
    
            await wait_for_svg_contains(page, "RETRYING (9s)")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "RETRYING (9s)")
            assert_page_svg_contains(page, "Retries:")
            assert_page_svg_contains(page, "1/3")
>           ace_png_visual.assert_page_png(
                page,
                "agents_retry_countdown_120x40",
                title="ACE agents retry countdown",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py:67: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_countdown_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x01p\xaaIDA...\x00\x00\x00\x80\x89\xa7\'\xfa\xe9\x8a~^V\xc7\x9dI\x03\xfc_\xa4\x0c%\x81\xe6\x8f\x0e\xb6\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_countdown_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retry_countdown_png_snapshot/agents_retry_countdown_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retry_countdown_png_snapshot/agents_retry_countdown_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retry_countdown_png_snapshot/agents_retry_countdown_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry.py__test_retry_countdown_png_snapshot/agents_retry_countdown_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:278: AssertionError
________________ test_real_fakey_running_fallback_png_snapshot _________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac...ts_retry_e2e.py', test_line=165, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10'))
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_fakey_running_fallba0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67ab4922e0>

    async def test_real_fakey_running_fallback_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        harness = FakeyRetryHarness(
            tmp_path,
            monkeypatch,
            max_retries=1,
            wait_times=[0],
            fallback_model="fakey-small",
            expose_to_agent_loader=True,
            artifacts_timestamp="20260706115900",
            is_home_mode=True,
        )
        harness.seed_running_agent(started_at=datetime(2026, 7, 6, 11, 59, 0))
        fallback = harness.barrier("fallback")
        harness.use_scenario(
            monkeypatch,
            [
                retryable_failure("primary unavailable"),
                retryable_failure("primary still unavailable"),
                {
                    **successful_attempt("fallback recovered"),
                    "steps": fallback.steps(),
                },
            ],
        )
        patch_startup_loaders(monkeypatch, use_real_agent_loader=True)
    
        handle = harness.run_in_background()
        try:
            fallback.wait_until_started()
            state = harness.wait_for_retry_state("running_fallback")
            assert state.fallback_model == "fakey-small"
            harness.normalize_visual_timestamps(_VISUAL_NOW)
            _patch_sentinel_pid_liveness(monkeypatch)
    
            async with AcePage(query='"fakey"', patches=patches()) as page:
                await _open_agents_tab(page, agent_count=1)
    
                loaded = page.app._agents[0]
                assert (
                    loaded.status,
                    loaded.retry_count,
                    loaded.using_fallback,
                    loaded.fallback_model,
                ) == ("RUNNING", 1, True, "fakey-small")
                await wait_for_svg_contains(page, "fakey-small")
                await wait_for_visual_idle(page)
                assert_page_svg_contains(page, "RUNNING")
                assert_page_svg_contains(page, "↻1▸fakey")
                assert_page_svg_contains(page, "Fallback:")
                assert_page_svg_contains(page, "fakey-small")
>               ace_png_visual.assert_page_png(
                    page,
                    "agents_retry_e2e_running_fallback_120x40",
                    title="ACE real fakey running fallback",
                )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py:219: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:152: in assert_page_png
    self.assert_png(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:174: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_retry_e2e_running_fallback_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02_dIDATx\...x00\x00\x00\x00\x8c=\x03\xd1\xab/z\xbd\xa2\x81;\x93&\xf8\xff\x01\x96\x9b\x94\xebP\xd3A\n\x00\x00\x00\x00IEND\xaeB`\x82'

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
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/snapshots/png/agents_retry_e2e_running_fallback_120x40.png
E       Changed pixels: 2756/1520532 (0.181252%); materially changed pixels: 2753/1520532 (0.181055%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_running_fallback_png_snapshot/agents_retry_e2e_running_fallback_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_running_fallback_png_snapshot/agents_retry_e2e_running_fallback_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_running_fallback_png_snapshot/agents_retry_e2e_running_fallback_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_retry_e2e.py__test_real_fakey_running_fallback_png_snapshot/agents_retry_e2e_running_fallback_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/visual/png_diff.py:278: AssertionError
----------------------------- Captured stdout call -----------------------------
╭────── 🤖 Workflow-Tmp_260917_213237-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

✅ Waiting for Fakey completed in 00:00╭─────── 🤖 Workflow-Tmp_260917_213237-Main [Big]_Error Agent - Prompt ────────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_213237-Main [Big]_Error Agent - Response ───────╮
│                                                                              │
│  Error running LLM provider command (exit code 1)                            │
│  stderr: FAKEY-RETRYABLE: primary unavailable                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_213238-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Your previous attempt hit a model context limit or transient provider       │
│  failure. Any file edits, new tests, and other on-disk changes you made are  │
│  preserved. Before making additional changes, run `git status` and `git      │
│  diff` to see what is already in place, then continue implementing the plan  │
│  from wherever you left off. Do not re-apply edits that are already          │
│  present.                                                                    │
│                                                                              │
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

✅ Waiting for Fakey completed in 00:00╭─────── 🤖 Workflow-Tmp_260917_213238-Main [Big]_Error Agent - Prompt ────────╮
│                                                                              │
│  Your previous attempt hit a model context limit or transient provider       │
│  failure. Any file edits, new tests, and other on-disk changes you made are  │
│  preserved. Before making additional changes, run `git status` and `git      │
│  diff` to see what is already in place, then continue implementing the plan  │
│  from wherever you left off. Do not re-apply edits that are already          │
│  present.                                                                    │
│                                                                              │
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_213238-Main [Big]_Error Agent - Response ───────╮
│                                                                              │
│  Error running LLM provider command (exit code 1)                            │
│  stderr: FAKEY-RETRYABLE: primary still unavailable                          │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260917_213240-Main [Fakey-Small] Agent - Prompt ───────╮
│                                                                              │
│  Your previous attempt hit a model context limit or transient provider       │
│  failure. Any file edits, new tests, and other on-disk changes you made are  │
│  preserved. Before making additional changes, run `git status` and `git      │
│  diff` to see what is already in place, then continue implementing the plan  │
│  from wherever you left off. Do not re-apply edits that are already          │
│  present.                                                                    │
│                                                                              │
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
fallback recovered

✅ Waiting for Fakey completed in 00:06
Chat history saved to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_fakey_running_fallba0/sase-home/chats/202607/fakey_e2e-ace_run-fakey_e2e-260706_115900.md
Preparing PDFs from Markdown... found 0, cap 10
[PDF] preparing Markdown PDFs (0 source(s), cap 10)
[PDF] complete: 0 generated, 0 skipped
[artifacts] default capture: stored=0 referenced=0 skipped=0 declared=0 cap_fired=false
Done marker written to: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/test_real_fakey_running_fallba0/sase-home/projects/home/artifacts/ace-run/20260706115900/done.json
----------------------------- Captured stderr call -----------------------------
FAKEY-RETRYABLE: primary unavailable
FAKEY-RETRYABLE: primary still unavailable
/home/bryan/bin/bam: line 3: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-2/popen-gw3/home49/lib/bugyi.sh: No such file or directory
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
15.35s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
13.99s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
13.96s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
13.72s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot
13.68s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
13.66s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
13.58s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
13.10s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
12.62s call     tests/ace/tui/visual/test_ace_png_snapshots_model_alias_completion.py::test_model_alias_completion_full_menu_png_snapshot[textual-dark-prompt_model_alias_completion_full_dark_120x40-ACE prompt input \u2014 equals alias completion full menu, dark theme]
12.47s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_highlight_png_snapshot
12.42s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
12.38s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_ordered_highlight_solo_png_snapshot[textual-dark-prompt_ordered_highlight_solo_dark_120x40-ACE prompt input \u2014 ordered-marker highlighting, dark theme]
12.22s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_status_png_snapshot[loading]
12.07s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
11.96s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py::test_prompt_cursor_readout_stack_png_snapshot
11.95s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
11.89s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_new_png_snapshot
11.87s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_count_pill_png_snapshot[textual-dark-prompt_search_count_pill_dark_120x40-ACE prompt input - committed search count pill, dark theme]
11.80s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_jinja_invalid_png_snapshot
11.78s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_list_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_reverted_indicator_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_sase_plan_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_stopped_status_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_plan_handoff_status_colors_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_wait_rows_and_queue_detail_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_epic_phase_roadmap_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_reserved_tribe_wait_row_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_bead_context_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_task_bead_notes_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_capacity_budget_accent_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_partially_streamed_context_lanes_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_output_variables_multi_agent_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agents_selected_row_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_artifacts.py::test_agents_artifact_file_type_icons_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py::test_agents_auto_approve_icons_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py::test_agents_auto_approve_workflow_child_alignment_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py::test_agents_auto_approve_metadata_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_auto_approve.py::test_agents_auto_approve_xprompts_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_tools.py::test_agents_tools_panel_populated_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_single_bead_labels_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_hint_mode_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_tools.py::test_agents_tools_panel_detail_level_png_snapshots[1-agents_tools_panel_expanded_120x40-ACE agents tools panel expanded detail]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_single_bead_labels_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_tools.py::test_agents_tools_panel_detail_level_png_snapshots[2-agents_tools_panel_full_120x40-ACE agents tools panel full detail]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_logical_prompt_hint_mode_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_missing_target_row_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_tribe_target_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_queued_clan_counts_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_running_clan_runtime_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_tree_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_xprompt.py::test_agents_xprompt_panel_highlighting_png_snapshot[textual-dark-agents_xprompt_panel_highlighting_120x40-ACE agents xprompt panel highlighting]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_xprompt.py::test_agents_xprompt_panel_highlighting_png_snapshot[textual-light-agents_xprompt_panel_highlighting_light_120x40-ACE agents xprompt panel highlighting, light theme]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_unread_count_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_waiting_family_child_row_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_running_family_current_runtime_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_settled_monitor_lane_badge_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_python_step_parent_family_footer_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_zoom_context.py::test_agents_context_zoom_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_renamed_generic_family_root_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_parallel_family_root_omits_counts_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_zoom_context.py::test_agents_metadata_zoom_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_family_and_lone_planner_color_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_member_panel_shows_sibling_roster_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_two_digit_roster_and_pending_footer_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_family_gate_shells_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_selected_gate_shell_output_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_neighbor_jump_expands_target_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_section_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_link_rail.py::test_link_rail_agents_single_link_png_snapshots[size0-link_rail_agents_single_link_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_above_sase_context_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_family_lane_neighbors_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-90-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_cleanup.py::test_sase_agent_cleanup_confirmation_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py::test_agents_overflowing_panel_uses_full_height_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_filter_bar.py::test_agents_filter_bar_idle_readout_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panel_layout.py::test_agents_unread_highlight_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py::test_agents_fleet_followed_partial_offline_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_fleet.py::test_agents_fleet_keyboard_focus_and_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py::test_running_fallback_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py::test_completed_retry_chain_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_leader_jump_auto_expands_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py::test_retries_exhausted_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py::test_selected_clan_collapses_before_open_sibling_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_pending_plans.py::test_agent_pending_plan_status_colors_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py::test_selected_retry_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py::test_group_clan_collapse_precedes_status_banner_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_modals.py::test_agent_workspace_tmux_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_proc_shells.py::test_agents_proc_shell_list_png_snapshot[size0-agents_proc_shells_120x40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_group_lane_collapse.py::test_group_lane_collapse_precedes_status_banner_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_proc_shells.py::test_agents_proc_shell_list_png_snapshot[size1-agents_proc_shells_90x30]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_linked_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_modals.py::test_wait_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_loader_plan_family_retry_countdown_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_modals.py::test_wait_modal_beads_focused_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_neighbor_badge_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry.py::test_retry_countdown_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
====== 106 failed, 854 passed, 1 skipped, 9 warnings in 375.05s (0:06:15) ======
error: recipe `test-visual` failed on line 500 with exit code 1

