# Chat History - ace-run (0q9.f2.f0--mon)

- **TIMESTAMP:** 2026-09-23 18:57:11 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0q9.f2.f0--mon

## Prompt

sase monitor start --command 'just fix-tui-screenshots' --reason 'Refresh TUI PNG goldens for the stash-chip contrast fix (plan 202609/stash_chip_contrast.md)'

## Response

sase tool run c3b022a6197b3a6c47c77c0adefb59b7
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix-tui-screenshots      │
└───────────────────────────────────────────────────────┘

---------- Running TUI screenshot maintenance... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [1006 items]

........................................................................ [  7%]
........................................................................ [ 14%]
........................................................................ [ 21%]
........................................................................ [ 28%]
........................................................................ [ 35%]
........................................................................ [ 42%]
........................................................................ [ 50%]
........................................................................ [ 57%]
........................................................................ [ 64%]
........................................................................ [ 71%]
........F...........F................................................... [ 78%]
........................................................................ [ 85%]
........................................................F............... [ 93%]
......................................................................   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f67449a3150>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f6731283270>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f6730c241a0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f6730c26fb0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f675c8656f0>, backoff_after_misses = 3
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
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6d26858130>

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

page = <sase.ace.testing.ace_page.AcePage object at 0x7f6d0f22b410>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:93: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f10067473f0>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f0fd5e64040>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f0fd5e678a0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f0fd7874040>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f10032656f0>, backoff_after_misses = 3
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
33.68s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
25.96s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
20.03s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
17.71s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
16.17s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
16.09s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
15.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_above_sase_context_png_snapshot
15.08s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
14.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_collapsed_two_digit_overflow_png_snapshot
13.98s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_expanded_png_snapshot
13.87s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_submit_choice_single_pane_png_snapshot
13.81s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_narrowed_png_snapshot
13.68s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_ordered_highlight_solo_png_snapshot[textual-dark-prompt_ordered_highlight_solo_dark_120x40-ACE prompt input \u2014 ordered-marker highlighting, dark theme]
13.64s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
13.01s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_mixed_menu_png_snapshot
12.75s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_scoped_frontmatter_png_snapshot
12.51s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
12.30s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_vim_cursor_normal_png_snapshot
12.30s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
12.22s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
====== 3 failed, 1003 passed, 1 skipped, 14 warnings in 301.45s (0:05:01) ======
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
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
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4b4ad23d10>

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

page = <sase.ace.testing.ace_page.AcePage object at 0x7f4b4a313620>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:93: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4b453a3e50>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f4b4530c0f0>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f4b48f737f0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f4b48f735e0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f4b58dd16f0>, backoff_after_misses = 3
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
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4b490fc6e0>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f4b48c538a0>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f4b48c524b0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f4b48c500f0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f4b58dd16f0>, backoff_after_misses = 3
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
16.25s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
15.88s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
6.05s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots

(5 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
============================== 3 failed in 44.22s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
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
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fdce9b6bd10>

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

page = <sase.ace.testing.ace_page.AcePage object at 0x7fdce8ea7620>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:93: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fdce8b30850>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fdce5ddd640>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fdce5b0c3b0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fdce7966f00>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fdcf38616f0>, backoff_after_misses = 3
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
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fdce79877a0>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fdce7443a00>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fdce79dcb40>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fdce79dcca0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fdcf38616f0>, backoff_after_misses = 3
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
16.02s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
6.66s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
0.11s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots

(5 durations < 0.005s hidden.  Use -vv to show these durations.)
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
============================== 3 failed in 44.99s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [664 items]

........................................................................ [ 10%]
........................................................................ [ 21%]
........................................................................ [ 32%]
........................................................................ [ 43%]
........................................................................ [ 54%]
........................................................................ [ 65%]
........................................................................ [ 75%]
........................................................................ [ 86%]
........................................................................ [ 97%]
................                                                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
34.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
26.13s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
15.39s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
15.12s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_expanded_png_snapshot
14.57s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
13.47s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
13.39s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_collapsed_two_digit_overflow_png_snapshot
12.83s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_search_operator.py::test_prompt_search_operator_yank_reverse_png_snapshot
12.81s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
12.76s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_stale_png_snapshot
12.62s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_count_pill_png_snapshot[textual-light-prompt_search_count_pill_light_120x40-ACE prompt input - committed search count pill, light theme]
12.55s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_alias_only_menu_png_snapshot
12.50s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_scoped_frontmatter_png_snapshot
12.31s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
12.26s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_count_pill_png_snapshot[textual-dark-prompt_search_count_pill_dark_120x40-ACE prompt input - committed search count pill, dark theme]
12.02s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
11.68s call     tests/ace/tui/visual/test_ace_png_snapshots_model_alias_completion.py::test_model_alias_completion_full_menu_png_snapshot[textual-dark-prompt_model_alias_completion_full_dark_120x40-ACE prompt input \u2014 equals alias completion full menu, dark theme]
11.62s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_highlight_png_snapshot
11.57s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_narrowed_png_snapshot
11.33s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_mixed_menu_png_snapshot
======================= 664 passed in 236.09s (0:03:56) ========================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [2 items]

..                                                                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
3.30s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_agent_clis_history_empty_png_snapshot
3.20s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_agent_clis_history_all_png_snapshot
0.08s setup    tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_agent_clis_history_all_png_snapshot

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 2 passed in 11.53s ==============================
fix-tui-screenshots: update partial
scope: full
WARNING:
  capture evidence is incomplete for 3 node(s) (tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots, tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot, tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot); stale goldens were left in place
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/capture.log, .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/recover-1.log, .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/capture.log, .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/recover-1.log, .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/capture.log, .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/recover-1.log, .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot))
  Those goldens were left unchanged and are not known to be current.
counts: created=0 updated=697 unchanged=40 stale=0
manifest: .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/manifest.json
run-dir: .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114
report: .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/ef149610d8d94aa5892d5413422d1114/report/summary.md
update-groups:
  group-1: 1 member(s), tests/ace/tui/visual/snapshots/png/config_center_procs_tab_monitors_90x40.png
  group-2: 10 member(s), tests/ace/tui/visual/snapshots/png/agents_artifact_type_icons_120x40.png
succeeded  exit=0  duration=1045687ms

