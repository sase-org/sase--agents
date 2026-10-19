# Chat History - ace-run (sase-1m3.11--mon)

- **TIMESTAMP:** 2026-10-19 10:13:55 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1m3.11--mon

## Prompt

sase monitor start --command 'just fix-tui-screenshots -- tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py' --reason 'Regenerate Statistics PNG goldens after the Projects tab migration (sase-1m3.11)'

## Response

sase tool run 7b422d7409f0cfd64200f5aaa30b40c4
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: inline-snapshot-0.36.0, cov-7.1.0, anyio-4.15.1, platformdirs-4.13.3, xdist-3.8.0, mock-3.16.0, asyncio-1.4.0, hypothesis-6.168.3
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 5/5 workers
5 workers [23 items]

....................F..                                                  [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
______ test_config_center_statistics_projects_measuring_code_png_snapshot ______
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x72f7564e8980>

    async def test_config_center_statistics_projects_measuring_code_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_siblings(monkeypatch)
        release = _patch_statistics_projects_measuring_code(monkeypatch)
    
        try:
            async with AcePage(query='"visual"', patches=patches()) as page:
                await wait_for_startup(page)
                await page.press(page.artifacts_digit("patches"))
                await page.expect_state("artifacts_subtab", "patches")
                _, pane = await _open_statistics_modal(page)
                pane._set_view("projects")
>               await _wait_projects_report(page, pane, code_complete=False)

tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py:535: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py:421: in _wait_projects_report
    await wait_for_visual_idle(page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x72f7564c2f60>
timeout = 30.0

    async def wait_for_visual_idle(page: AcePage, *, timeout: float = 30.0) -> None:
        """Wait for finite work to finish and the rendered SVG frame to converge."""
        setattr(page, _VISUAL_CONVERGED_SVG_ATTR, None)
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
        previous_svg: str | None = None
        stable_frames = 0
        frame_digests: list[str] = []
        pending: tuple[list[str], list[str], list[str], list[str]] = ([], [], [], [])
    
        while True:
            # A zero-delay queue drain may return the same frame repeatedly simply
            # because a starved app has not been scheduled. Pilot's full pause
            # waits for the screen message counters and yields through its CPU-idle
            # heuristic, so every accepted sample is separated by actual scheduler
            # and Textual refresh progress. Five full pauses cost about the same as
            # the former fixed 100 ms quiet period when the app is already idle,
            # while naturally taking longer when CPU-bound work is still active.
            await page.pause()
            _clear_transient_button_state(page)
            if _disable_cursor_blink(page):
                # The refresh requested above must reach the compositor before
                # its frame is sampled. Under contention, exporting immediately
                # can reuse a line cached with the opposite caret state even
                # though _cursor_visible already matches focus.
                await page.pause()
            pending = _pending_visual_work(page)
    
            if any(pending):
                previous_svg = None
                stable_frames = 0
            else:
                # Exporting forces Textual to materialize the compositor's current
                # frame. Requiring the same result across separate idle/layout
                # cycles prevents a partially painted frame from reaching the PNG
                # comparator merely because a fixed number of pauses elapsed.
                svg = page.export_svg(title=_VISUAL_CONVERGENCE_TITLE)
                digest = hashlib.sha256(svg.encode()).hexdigest()[:12]
                frame_digests.append(digest)
                frame_digests = frame_digests[-4:]
                if svg == previous_svg:
                    stable_frames += 1
                else:
                    stable_frames = 1
                previous_svg = svg
                if stable_frames >= _VISUAL_STABLE_FRAME_COUNT:
                    setattr(page, _VISUAL_CONVERGED_SVG_ATTR, svg)
                    return
    
            if loop.time() >= deadline:
                debouncers, workers, timers, animations = pending
>               raise AssertionError(
                    "Timed out waiting for ACE visual render convergence "
                    f"after {timeout:.2f}s; stable_frames={stable_frames}/"
                    f"{_VISUAL_STABLE_FRAME_COUNT}; frame_digests={frame_digests}; "
                    f"pending_debouncers={debouncers}; pending_workers={workers}; "
                    f"pending_one_shot_timers={timers}; "
                    f"pending_animations={animations}"
                )
E               AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]

tests/ace/tui/visual/_ace_png_snapshot_waits.py:306: AssertionError
============================= slowest 20 durations =============================
38.09s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
12.06s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_patch_png_snapshot
11.21s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_repo_png_snapshot
11.12s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_model_png_snapshot
11.03s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_activity_png_snapshot
10.88s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_perf_narrow_png_snapshot
10.68s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_overview_png_snapshot
10.65s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_macros_narrow_png_snapshot
10.45s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_providers_png_snapshot
10.41s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_perf_png_snapshot
10.01s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_loading_png_snapshot
9.96s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_narrow_png_snapshot
9.80s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_macros_focus_png_snapshot
9.73s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_png_snapshot
9.28s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_macros_png_snapshot
9.19s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_empty_png_snapshot
9.14s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_help_png_snapshot
9.08s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_runners_png_snapshot
9.03s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_perf_degraded_png_snapshot
9.00s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_macros_model_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot - AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]
=================== 1 failed, 22 passed in 178.03s (0:02:58) ===================
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: inline-snapshot-0.36.0, cov-7.1.0, anyio-4.15.1, platformdirs-4.13.3, xdist-3.8.0, mock-3.16.0, asyncio-1.4.0, hypothesis-6.168.3
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

F                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
______ test_config_center_statistics_projects_measuring_code_png_snapshot ______
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7e7b80c57710>

    async def test_config_center_statistics_projects_measuring_code_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_siblings(monkeypatch)
        release = _patch_statistics_projects_measuring_code(monkeypatch)
    
        try:
            async with AcePage(query='"visual"', patches=patches()) as page:
                await wait_for_startup(page)
                await page.press(page.artifacts_digit("patches"))
                await page.expect_state("artifacts_subtab", "patches")
                _, pane = await _open_statistics_modal(page)
                pane._set_view("projects")
>               await _wait_projects_report(page, pane, code_complete=False)

tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py:535: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py:421: in _wait_projects_report
    await wait_for_visual_idle(page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7e7b80890500>
timeout = 30.0

    async def wait_for_visual_idle(page: AcePage, *, timeout: float = 30.0) -> None:
        """Wait for finite work to finish and the rendered SVG frame to converge."""
        setattr(page, _VISUAL_CONVERGED_SVG_ATTR, None)
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
        previous_svg: str | None = None
        stable_frames = 0
        frame_digests: list[str] = []
        pending: tuple[list[str], list[str], list[str], list[str]] = ([], [], [], [])
    
        while True:
            # A zero-delay queue drain may return the same frame repeatedly simply
            # because a starved app has not been scheduled. Pilot's full pause
            # waits for the screen message counters and yields through its CPU-idle
            # heuristic, so every accepted sample is separated by actual scheduler
            # and Textual refresh progress. Five full pauses cost about the same as
            # the former fixed 100 ms quiet period when the app is already idle,
            # while naturally taking longer when CPU-bound work is still active.
            await page.pause()
            _clear_transient_button_state(page)
            if _disable_cursor_blink(page):
                # The refresh requested above must reach the compositor before
                # its frame is sampled. Under contention, exporting immediately
                # can reuse a line cached with the opposite caret state even
                # though _cursor_visible already matches focus.
                await page.pause()
            pending = _pending_visual_work(page)
    
            if any(pending):
                previous_svg = None
                stable_frames = 0
            else:
                # Exporting forces Textual to materialize the compositor's current
                # frame. Requiring the same result across separate idle/layout
                # cycles prevents a partially painted frame from reaching the PNG
                # comparator merely because a fixed number of pauses elapsed.
                svg = page.export_svg(title=_VISUAL_CONVERGENCE_TITLE)
                digest = hashlib.sha256(svg.encode()).hexdigest()[:12]
                frame_digests.append(digest)
                frame_digests = frame_digests[-4:]
                if svg == previous_svg:
                    stable_frames += 1
                else:
                    stable_frames = 1
                previous_svg = svg
                if stable_frames >= _VISUAL_STABLE_FRAME_COUNT:
                    setattr(page, _VISUAL_CONVERGED_SVG_ATTR, svg)
                    return
    
            if loop.time() >= deadline:
                debouncers, workers, timers, animations = pending
>               raise AssertionError(
                    "Timed out waiting for ACE visual render convergence "
                    f"after {timeout:.2f}s; stable_frames={stable_frames}/"
                    f"{_VISUAL_STABLE_FRAME_COUNT}; frame_digests={frame_digests}; "
                    f"pending_debouncers={debouncers}; pending_workers={workers}; "
                    f"pending_one_shot_timers={timers}; "
                    f"pending_animations={animations}"
                )
E               AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]

tests/ace/tui/visual/_ace_png_snapshot_waits.py:306: AssertionError
============================= slowest 20 durations =============================
39.49s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
0.24s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot - AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]
============================== 1 failed in 53.56s ==============================
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: inline-snapshot-0.36.0, cov-7.1.0, anyio-4.15.1, platformdirs-4.13.3, xdist-3.8.0, mock-3.16.0, asyncio-1.4.0, hypothesis-6.168.3
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [1 item]

F                                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
______ test_config_center_statistics_projects_measuring_code_png_snapshot ______
[gw0] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7b2d5deb7b30>

    async def test_config_center_statistics_projects_measuring_code_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_siblings(monkeypatch)
        release = _patch_statistics_projects_measuring_code(monkeypatch)
    
        try:
            async with AcePage(query='"visual"', patches=patches()) as page:
                await wait_for_startup(page)
                await page.press(page.artifacts_digit("patches"))
                await page.expect_state("artifacts_subtab", "patches")
                _, pane = await _open_statistics_modal(page)
                pane._set_view("projects")
>               await _wait_projects_report(page, pane, code_complete=False)

tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py:535: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py:421: in _wait_projects_report
    await wait_for_visual_idle(page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7b2d5daf05f0>
timeout = 30.0

    async def wait_for_visual_idle(page: AcePage, *, timeout: float = 30.0) -> None:
        """Wait for finite work to finish and the rendered SVG frame to converge."""
        setattr(page, _VISUAL_CONVERGED_SVG_ATTR, None)
        loop = asyncio.get_running_loop()
        deadline = loop.time() + timeout
        previous_svg: str | None = None
        stable_frames = 0
        frame_digests: list[str] = []
        pending: tuple[list[str], list[str], list[str], list[str]] = ([], [], [], [])
    
        while True:
            # A zero-delay queue drain may return the same frame repeatedly simply
            # because a starved app has not been scheduled. Pilot's full pause
            # waits for the screen message counters and yields through its CPU-idle
            # heuristic, so every accepted sample is separated by actual scheduler
            # and Textual refresh progress. Five full pauses cost about the same as
            # the former fixed 100 ms quiet period when the app is already idle,
            # while naturally taking longer when CPU-bound work is still active.
            await page.pause()
            _clear_transient_button_state(page)
            if _disable_cursor_blink(page):
                # The refresh requested above must reach the compositor before
                # its frame is sampled. Under contention, exporting immediately
                # can reuse a line cached with the opposite caret state even
                # though _cursor_visible already matches focus.
                await page.pause()
            pending = _pending_visual_work(page)
    
            if any(pending):
                previous_svg = None
                stable_frames = 0
            else:
                # Exporting forces Textual to materialize the compositor's current
                # frame. Requiring the same result across separate idle/layout
                # cycles prevents a partially painted frame from reaching the PNG
                # comparator merely because a fixed number of pauses elapsed.
                svg = page.export_svg(title=_VISUAL_CONVERGENCE_TITLE)
                digest = hashlib.sha256(svg.encode()).hexdigest()[:12]
                frame_digests.append(digest)
                frame_digests = frame_digests[-4:]
                if svg == previous_svg:
                    stable_frames += 1
                else:
                    stable_frames = 1
                previous_svg = svg
                if stable_frames >= _VISUAL_STABLE_FRAME_COUNT:
                    setattr(page, _VISUAL_CONVERGED_SVG_ATTR, svg)
                    return
    
            if loop.time() >= deadline:
                debouncers, workers, timers, animations = pending
>               raise AssertionError(
                    "Timed out waiting for ACE visual render convergence "
                    f"after {timeout:.2f}s; stable_frames={stable_frames}/"
                    f"{_VISUAL_STABLE_FRAME_COUNT}; frame_digests={frame_digests}; "
                    f"pending_debouncers={debouncers}; pending_workers={workers}; "
                    f"pending_one_shot_timers={timers}; "
                    f"pending_animations={animations}"
                )
E               AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]

tests/ace/tui/visual/_ace_png_snapshot_waits.py:306: AssertionError
============================= slowest 20 durations =============================
48.15s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
0.69s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot - AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]
========================= 1 failed in 68.06s (0:01:08) =========================
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: inline-snapshot-0.36.0, cov-7.1.0, anyio-4.15.1, platformdirs-4.13.3, xdist-3.8.0, mock-3.16.0, asyncio-1.4.0, hypothesis-6.168.3
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 6/6 workers
6 workers [8 items]

........                                                                 [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


============================= slowest 20 durations =============================
12.21s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_model_png_snapshot
11.64s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_png_snapshot
11.41s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_help_png_snapshot
11.04s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_narrow_png_snapshot
10.43s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_overview_png_snapshot
10.17s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_narrow_png_snapshot
9.71s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_repo_png_snapshot
9.61s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_patch_png_snapshot
0.34s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_help_png_snapshot
0.31s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_overview_png_snapshot
0.30s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_narrow_png_snapshot
0.30s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_model_png_snapshot
0.28s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_png_snapshot
0.28s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_narrow_png_snapshot
0.04s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_narrow_png_snapshot
0.02s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_narrow_png_snapshot
0.02s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_repo_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_patch_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_model_png_snapshot
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_png_snapshot
============================== 8 passed in 35.37s ==============================
fix-tui-screenshots: update partial
scope: targeted
WARNING:
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608/capture.log, .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608/recover-1.log, .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py::test_config_center_statistics_projects_measuring_code_png_snapshot - AssertionError: Timed out waiting for ACE visual render convergence after 30.00s; stable_frames=0/5; frame_digests=[]; pending_debouncers=[]; pending_workers=['task']; pending_one_shot_timers=[]; pending_animations=[]))
  Those goldens were left unchanged and are not known to be current.
counts: created=4 updated=4 unchanged=14 stale=0
dirty-before:
  tests/ace/tui/visual/snapshots/png/config_center_statistics_projects_drilldown_120x40.png
manifest: .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608/manifest.json
run-dir: .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608
report: .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/42242bdb34df4871b21de919ff85f608/report/summary.md
update-groups:
  group-1: 1 member(s), tests/ace/tui/visual/snapshots/png/config_center_statistics_overview_120x40.png
succeeded  exit=0  duration=396398ms

