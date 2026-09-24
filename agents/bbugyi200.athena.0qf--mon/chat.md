# Chat History - ace-run (0qf--mon)

- **TIMESTAMP:** 2026-09-23 21:01:31 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0qf--mon

## Prompt

sase monitor start --command 'just fix-tui-screenshots' --reason 'Refresh top-bar PNG goldens for procs/monitors merge and updates arrow'

## Response

sase tool run 88ff6c6c78c96f5e4d061509925e0c6e
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [1011 items]

........................................................................ [  7%]
........................................................................ [ 14%]
........................................................................ [ 21%]
........................................................................ [ 28%]
........................................................................ [ 35%]
........................................................................ [ 42%]
........................................................................ [ 49%]
........................................................................ [ 56%]
........................................................................ [ 64%]
........................................F............................... [ 71%]
........................................................................ [ 78%]
........................................................................ [ 85%]
......................................................F................. [ 92%]
.....................................................F.................. [ 99%]
...                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0b7c9f6eb0>

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
>           assert_page_svg_contains(page, "--code")

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:310: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f0b733bd6d0>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:93: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9bc4427b60>

    async def test_top_bar_usage_attention_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        default_override = override("codex", "o3", effort="xhigh")
        alias_override = override("claude", "opus", effort="max")
        quiet_top_bar(
            monkeypatch,
            default_override=default_override,
            alias_overrides={
                launch_model_setting_override_key(DEFAULT_MODEL_FIELD): default_override,
                "medium": alias_override,
            },
            disables={"claude": disable("claude")},
            now=100.0,
        )
        patch_projection(
            monkeypatch,
            SimpleNamespace(
                entries=(
                    entry(
                        provider="grok",
                        remaining_percent=4.0,
                        vendor_state="rejected",
                        display_attention="rejected",
                    ),
                    entry(
                        provider="codex",
                        remaining_percent=12.0,
                        display_attention="low",
                    ),
                ),
                providers=(),
                generated_at=100.0,
            ),
        )
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            size=(80, 24),
        ) as page:
>           await wait_for_startup(page)

tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py:85: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_startup.py:454: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:503: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f9ba329d900>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f9ba329d9b0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f9ba9539590>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f9bd54b56f0>, backoff_after_misses = 3
backoff_seconds = 0.001

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fef29c4ae40>

    async def test_top_bar_usage_badges_crowded_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A 60-column bar keeps routing controls and degrades usage to a count."""
        patch_startup_loaders(monkeypatch)
        default_override = override("codex", "o3", effort="xhigh")
        quiet_top_bar(
            monkeypatch,
            default_override=default_override,
            disables={"claude": disable("claude")},
        )
    
        patch_projection(
            monkeypatch,
            _entries_projection(
                entry(provider="grok", remaining_percent=4.0, display_attention="very_low"),
                entry(provider="codex", remaining_percent=50.0),
                entry(provider="claude", remaining_percent=62.0),
            ),
        )
    
>       await _snapshot_top_bar(
            ace_png_visual,
            size=(60, 24),
            name="top_bar_usage_badges_crowded_60x24",
            title="ACE top bar with usage disclosure squeezed beside routing at 60 columns",
        )

tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py:297: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py:53: in _snapshot_top_bar
    await wait_for_startup(page)
tests/ace/tui/visual/_ace_png_snapshot_startup.py:454: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:503: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fef05f95010>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fef05f964b0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fef05f96350>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fef39ed96f0>, backoff_after_misses = 3
backoff_seconds = 0.001

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
39.15s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
39.15s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
23.99s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
17.73s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
16.83s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
16.59s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_new_png_snapshot
16.00s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
15.90s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_narrowed_png_snapshot
14.93s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_collapsed_two_digit_overflow_png_snapshot
14.91s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
14.61s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
13.70s call     tests/ace/tui/visual/test_ace_png_snapshots_xprompt_arg_completion.py::test_xprompt_arg_name_completion_png_snapshot[dark]
13.52s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_expanded_png_snapshot
12.84s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py::test_fork_target_completion_png_snapshot
12.79s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py::test_prompt_cursor_readout_stack_png_snapshot
12.69s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_new_and_clean_png_snapshots[False-mini_xprompt_pane_new_120x40-ACE mini-xprompt pane - new]
12.41s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_scoped_frontmatter_png_snapshot
12.27s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
12.21s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_compact_inactive_png_snapshot
12.11s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
====== 3 failed, 1008 passed, 1 skipped, 14 warnings in 281.68s (0:04:41) ======
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [3 items]

FFF                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1611803e30>

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
>           assert_page_svg_contains(page, "--code")

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:310: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f1610fcf8c0>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:93: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f160dd25650>

    async def test_top_bar_usage_attention_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        default_override = override("codex", "o3", effort="xhigh")
        alias_override = override("claude", "opus", effort="max")
        quiet_top_bar(
            monkeypatch,
            default_override=default_override,
            alias_overrides={
                launch_model_setting_override_key(DEFAULT_MODEL_FIELD): default_override,
                "medium": alias_override,
            },
            disables={"claude": disable("claude")},
            now=100.0,
        )
        patch_projection(
            monkeypatch,
            SimpleNamespace(
                entries=(
                    entry(
                        provider="grok",
                        remaining_percent=4.0,
                        vendor_state="rejected",
                        display_attention="rejected",
                    ),
                    entry(
                        provider="codex",
                        remaining_percent=12.0,
                        display_attention="low",
                    ),
                ),
                providers=(),
                generated_at=100.0,
            ),
        )
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            size=(80, 24),
        ) as page:
>           await wait_for_startup(page)

tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py:85: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_startup.py:454: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:503: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f160d6dcf60>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f160d6dfcc0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f160dc7f110>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f161ba716f0>, backoff_after_misses = 3
backoff_seconds = 0.001

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f160db0a210>

    async def test_top_bar_usage_badges_crowded_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A 60-column bar keeps routing controls and degrades usage to a count."""
        patch_startup_loaders(monkeypatch)
        default_override = override("codex", "o3", effort="xhigh")
        quiet_top_bar(
            monkeypatch,
            default_override=default_override,
            disables={"claude": disable("claude")},
        )
    
        patch_projection(
            monkeypatch,
            _entries_projection(
                entry(provider="grok", remaining_percent=4.0, display_attention="very_low"),
                entry(provider="codex", remaining_percent=50.0),
                entry(provider="claude", remaining_percent=62.0),
            ),
        )
    
>       await _snapshot_top_bar(
            ace_png_visual,
            size=(60, 24),
            name="top_bar_usage_badges_crowded_60x24",
            title="ACE top bar with usage disclosure squeezed beside routing at 60 columns",
        )

tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py:297: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py:53: in _snapshot_top_bar
    await wait_for_startup(page)
tests/ace/tui/visual/_ace_png_snapshot_startup.py:454: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:503: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f160dcf77f0>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f160dcf7c10>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f160dcf4b40>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f161ba716f0>, backoff_after_misses = 3
backoff_seconds = 0.001

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
============================= slowest 20 durations =============================
16.23s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
15.80s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
6.13s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
0.12s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots

(5 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
============================== 3 failed in 44.39s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [3 items]

FFF                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efff86e0710>

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
>           assert_page_svg_contains(page, "--code")

tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py:310: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7efff823b8c0>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:93: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efff8777450>

    async def test_top_bar_usage_attention_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        default_override = override("codex", "o3", effort="xhigh")
        alias_override = override("claude", "opus", effort="max")
        quiet_top_bar(
            monkeypatch,
            default_override=default_override,
            alias_overrides={
                launch_model_setting_override_key(DEFAULT_MODEL_FIELD): default_override,
                "medium": alias_override,
            },
            disables={"claude": disable("claude")},
            now=100.0,
        )
        patch_projection(
            monkeypatch,
            SimpleNamespace(
                entries=(
                    entry(
                        provider="grok",
                        remaining_percent=4.0,
                        vendor_state="rejected",
                        display_attention="rejected",
                    ),
                    entry(
                        provider="codex",
                        remaining_percent=12.0,
                        display_attention="low",
                    ),
                ),
                providers=(),
                generated_at=100.0,
            ),
        )
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            size=(80, 24),
        ) as page:
>           await wait_for_startup(page)

tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py:85: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_startup.py:454: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:503: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7efff50cfd70>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7efff7eee1f0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7efff7eee2a0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f0006e016f0>, backoff_after_misses = 3
backoff_seconds = 0.001

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efff6d7e300>

    async def test_top_bar_usage_badges_crowded_narrow_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A 60-column bar keeps routing controls and degrades usage to a count."""
        patch_startup_loaders(monkeypatch)
        default_override = override("codex", "o3", effort="xhigh")
        quiet_top_bar(
            monkeypatch,
            default_override=default_override,
            disables={"claude": disable("claude")},
        )
    
        patch_projection(
            monkeypatch,
            _entries_projection(
                entry(provider="grok", remaining_percent=4.0, display_attention="very_low"),
                entry(provider="codex", remaining_percent=50.0),
                entry(provider="claude", remaining_percent=62.0),
            ),
        )
    
>       await _snapshot_top_bar(
            ace_png_visual,
            size=(60, 24),
            name="top_bar_usage_badges_crowded_60x24",
            title="ACE top bar with usage disclosure squeezed beside routing at 60 columns",
        )

tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py:297: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py:53: in _snapshot_top_bar
    await wait_for_startup(page)
tests/ace/tui/visual/_ace_png_snapshot_startup.py:454: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:503: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7efff6833b60>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7efff6bdde80>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7efff4831b10>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f0006e016f0>, backoff_after_misses = 3
backoff_seconds = 0.001

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
============================= slowest 20 durations =============================
16.16s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
15.90s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
5.14s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
0.10s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
0.01s teardown tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
============================== 3 failed in 42.97s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32
configfile: pyproject.toml
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [11 items]

...........                                                              [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
36.60s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
4.55s call     tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py::test_startup_update_toast_grouped_commits_png_snapshot
4.16s call     tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py::test_startup_update_toast_png_snapshot
3.10s call     tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_mixed_core_rebuild_png_snapshot
3.02s call     tests/ace/tui/visual/test_ace_png_snapshots_top_bar_indicators.py::test_top_bar_indicators_full_png_snapshot
2.90s call     tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_mixed_routine_png_snapshot
2.86s call     tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_with_neighbors_png_snapshot
2.80s call     tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_routine_png_snapshot
2.73s call     tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_agent_cli_only_png_snapshot
2.60s call     tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_core_rebuild_png_snapshot
2.59s call     tests/ace/tui/visual/test_ace_png_snapshots_top_bar_indicators.py::test_top_bar_indicators_compact_png_snapshot
0.15s setup    tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py::test_startup_update_toast_png_snapshot
0.13s setup    tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_with_neighbors_png_snapshot
0.13s setup    tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_core_rebuild_png_snapshot
0.12s setup    tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_mixed_core_rebuild_png_snapshot
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_routine_png_snapshot
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py::test_startup_update_toast_grouped_commits_png_snapshot
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_updates_indicator.py::test_updates_indicator_mixed_routine_png_snapshot
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_top_bar_indicators.py::test_top_bar_indicators_full_png_snapshot
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_top_bar_indicators.py::test_top_bar_indicators_compact_png_snapshot
============================= 11 passed in 42.68s ==============================
fix-tui-screenshots: update partial
scope: full
WARNING:
  capture evidence is incomplete for 3 node(s) (tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots, tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot, tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot); stale goldens were left in place
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/capture.log, .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/recover-1.log, .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/capture.log, .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/recover-1.log, .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/capture.log, .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/recover-1.log, .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot))
  Those goldens were left unchanged and are not known to be current.
counts: created=0 updated=11 unchanged=731 stale=0
manifest: .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/manifest.json
run-dir: .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf
report: .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/cb577a0b4de545f89fa23bb1f5ba21cf/report/summary.md
succeeded  exit=0  duration=461171ms

