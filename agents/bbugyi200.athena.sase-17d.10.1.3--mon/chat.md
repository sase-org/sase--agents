# Chat History - ace-run (sase-17d.10.1.3--mon)

- **TIMESTAMP:** 2026-09-24 15:24:19 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17d.10.1.3--mon

## Prompt

sase monitor start --command 'just fix-tui-screenshots' --reason 'cutover-goldens full golden regeneration for bead sase-17d.10.1.3'

## Response

sase tool run 64c4d33ec82d19352e0d805dc6f5cda3
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
created: 8/8 workers
8 workers [1021 items]

........................................................................ [  7%]
........................................................................ [ 14%]
........................................................................ [ 21%]
........................................F...................F........... [ 28%]
...............................F................F....................... [ 35%]
.......................................F................................ [ 42%]
........................................................................ [ 49%]
.........F..........................F................................... [ 56%]
..................F..................F........................F......... [ 63%]
....................F................................................... [ 70%]
......F....F............................................................ [ 77%]
......................F.......F.........F.......................F....... [ 84%]
....F....................F....................F........F..........F..... [ 91%]
......F......F....................F.......F..........F..........F....... [ 98%]
.............                                                            [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_agents_slow_tool_calls_fold_levels_png_snapshots _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fcf89febbf0>

    async def test_agents_slow_tool_calls_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(_agent_display_header, "DateTime", _FixedDateTime)
        monkeypatch.setattr(
            _agent_context_common,
            "get_timezone",
            lambda: ZoneInfo("UTC"),
        )
        pin_agents_visual_now(monkeypatch, _NOW.replace(tzinfo=None))
        tools_cache_module.tools_cache.clear()
        artifacts_dir = _VISUAL_SLOW_TOOLS_DIR
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
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
            await choose_agent_metadata_view(page)
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
>           await _focus_slow_tool_section(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:322: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fcf964c82f0>

    async def _focus_slow_tool_section(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(20):
            if panel.active_section_identity == "slow-tool-calls":
                await wait_for_state(
                    page,
                    lambda: _slow_tool_section_ready(panel),
                    description="active slow-tool section",
                )
                await wait_for_visual_idle(
                    page,
                    timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT,
                )
                if _slow_tool_section_ready(panel):
                    if await _slow_tool_section_top_aligned(page, panel):
                        return panel
                    continue
            await page.press("ctrl+j")
            # The first navigation request may enable the panel's layout reserve
            # and finish through a call-after-refresh retry. Let that retry and its
            # anchor paint converge before deciding whether another key is needed.
            await wait_for_visual_idle(page, timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT)
>       raise AssertionError("Timed out focusing slow-tool calls section")
E       AssertionError: Timed out focusing slow-tool calls section

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:210: AssertionError
________________ test_tribe_panel_clan_summaries_png_snapshots _________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fcf8d108250>

    async def test_tribe_panel_clan_summaries_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_clan_summary_agents())
    
        async with AcePage(query='"visual-"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 2)
            await wait_for_visual_idle(page)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _screen: "CLAN SUMMARIES" in prompt_header_and_body_text(panel),
                timeout=30.0,
            )
    
>           await _jump_to_clan_summaries(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py:120: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fcfb73b9810>

    async def _jump_to_clan_summaries(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(10):
            if panel.active_section_identity == "tribe:clan-summaries":
                break
            await page.press("ctrl+j")
>       assert panel.active_section_identity == "tribe:clan-summaries"
E       AssertionError: assert None == 'tribe:clan-summaries'
E        +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py:89: AssertionError
__________________ test_tribe_panel_four_level_png_snapshots ___________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fcf857e2990>

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
>           await _settle_tribe_visual(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:405: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:50: in _settle_tribe_visual
    scroll = page.app.query_one("#agent-prompt-scroll", VerticalScroll)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-prompt-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-prompt-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________________ test_tribe_panel_prompts_png_snapshots ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fcf81be4230>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw1/test_tribe_panel_prompts_png_s0')

    async def test_tribe_panel_prompts_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_prompt_agents(tmp_path))
    
        async with AcePage(query='"visual-prompts"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _screen: "PROMPTS" in prompt_header_and_body_text(panel),
                timeout=30.0,
            )
            assert page.app._member_jump_maps[("panel", "epic")].targets
    
>           await _jump_to_prompts(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py:212: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fcfa10705f0>

    async def _jump_to_prompts(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(10):
            if panel.active_section_identity == "tribe:prompts":
                break
            await page.press("ctrl+j")
>       assert panel.active_section_identity == "tribe:prompts"
E       AssertionError: assert None == 'tribe:prompts'
E        +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py:179: AssertionError
_____________ test_agents_waiting_unknown_zoom_modal_png_snapshot ______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fcf971b4ad0>

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
                await choose_agent_metadata_view(page)
                await page.press("Z")
                await page.expect_no_modal()
                await wait_for_svg_contains(page, "ghost")
>               await _wait_for_wait_bead_statuses(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:316: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:124: in _wait_for_wait_bead_statuses
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fcf83cfa8a0>
predicate = <function _wait_for_wait_bead_statuses.<locals>.has_status_badges at 0x7fcf7bdf62a0>
description = 'wait bead status badges', timeout = 15.0

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
E               AssertionError: Timed out after 15.00s waiting for wait bead status badges; last_frame_digest=5fc86948f88d; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-2991892322-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-2991892322-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-2991892322-r1 { fill: #c5c8c6 }\n.terminal-2991892322-r2 { fill: #fffcf0 }\n.terminal-2991892322-r3 { fill: #87d7ff;font-weight: bold }\n.terminal-2991892322-r4 { fill: #444444 }\n.terminal-2991892322-r5 { fill: #888888 }\n.terminal-2991892322-r6 { fill: #b1afa7 }\n.terminal-2991892322-r7 { fill: #ff8700;font-weight: bold }\n.terminal-2991892322-r8 { fill: #ffd700;font-weight: bold }\n.terminal-2991892322-r9 { fill: #ffffff;font-weight: bold }\n.terminal-2991892322-r10 { fill: #00d7af;font-weight: bold }\n.terminal-2991892322-r11 { fill: #af87ff;font-weight: bold }\n.terminal-2991892322-r12 { fill: #ff5f5f;font-weight: bold }\n.terminal-2991892322-r13 { fill: #5fd7ff;font-weight: bold }\n.terminal-2991892322-r14 { fill: #65c3ed;font-weight: bold }\n.terminal-2991892322-r15 { fill: #63d9b6 }\n.terminal-2991892322-r16 { fill: #877307 }\n.terminal-2991892322-r17 { fill: #757474 }\n.terminal-2991892322-r18 { fill: #ffd700 }\n.terminal-2991892322-r19 { fill: #adaba3 }\n.terminal-2991892322-r20 { fill: #87ff00;font-weight: bold }\n.terminal-2991892322-r21 { fill: #5faf00 }\n.terminal-2991892322-r22 { fill: #afff5f }\n.terminal-2991892322-r23 { fill: #af87ff }\n.terminal-2991892322-r24 { fill: #ff87d7 }\n.terminal-2991892322-r25 { fill: #5fd75f;font-weight: bold }\n.terminal-2991892322-r26 { fill: #ffaf5f;font-weight: bold }\n.terminal-2991892322-r27 { fill: #24837b }\n.terminal-2991892322-r28 { fill: #004578;font-weight: bold }\n.terminal-2991892322-r29 { fill: #100f0f;font-weight: bold }\n.terminal-2991892322-r30 { fill: #d7af5f;font-weight: bold;text-decoration: underline; }\n.terminal-2991892322-r31 { fill: #a4a3a3 }\n.terminal-2991892322-r32 { fill: #adaba3;font-style: italic; }\n.terminal-2991892322-r33 { fill: #1d5b56 }\n.terminal-2991892322-r34 { fill: #494846 }\n.terminal-2991892322-r35 { fill: #c4c5b5;font-weight: bold }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-2991892322-clip-terminal">\n      <rect x="0" y="0" width="1463.0" height="975.0" />\n    </clipPath>\n    <clipPath id="terminal-2991892322-line-0">\n    <rect x="0" y="1.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-1">\n    <rect x="0" y="25.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-2">\n    <rect x="0" y="50.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-3">\n    <rect x="0" y="74.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-4">\n    <rect x="0" y="99.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-5">\n    <rect x="0" y="123.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-6">\n    <rect x="0" y="147.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-7">\n    <rect x="0" y="172.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-8">\n    <rect x="0" y="196.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-9">\n    <rect x="0" y="221.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-10">\n    <rect x="0" y="245.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-11">\n    <rect x="0" y="269.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-12">\n    <rect x="0" y="294.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-13">\n    <rect x="0" y="318.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-14">\n    <rect x="0" y="343.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-15">\n    <rect x="0" y="367.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-16">\n    <rect x="0" y="391.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-17">\n    <rect x="0" y="416.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-18">\n    <rect x="0" y="440.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-19">\n    <rect x="0" y="465.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-20">\n    <rect x="0" y="489.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-21">\n    <rect x="0" y="513.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-22">\n    <rect x="0" y="538.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-23">\n    <rect x="0" y="562.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-24">\n    <rect x="0" y="587.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-25">\n    <rect x="0" y="611.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-26">\n    <rect x="0" y="635.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-27">\n    <rect x="0" y="660.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-28">\n    <rect x="0" y="684.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-29">\n    <rect x="0" y="709.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-30">\n    <rect x="0" y="733.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-31">\n    <rect x="0" y="757.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-32">\n    <rect x="0" y="782.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-33">\n    <rect x="0" y="806.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-34">\n    <rect x="0" y="831.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-35">\n    <rect x="0" y="855.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-36">\n    <rect x="0" y="879.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-37">\n    <rect x="0" y="904.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-38">\n    <rect x="0" y="928.7" width="1464" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="1480" height="1024" rx="8"/><text class="terminal-2991892322-title" fill="#c5c8c6" text-anchor="middle" x="740" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-2991892322-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="829.6" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="841.8" y="1.5" width="622.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1464" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="25.9" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="25.9" width="866.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1305.4" y="25.9" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1390.8" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1427.4" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="48.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="61" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="158.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="353.8" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="488" y="50.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="561.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="597.8" y="50.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="695.4" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="732" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="841.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="951.6" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="976" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1049.2" y="50.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1098" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1134.6" y="50.3" width="329.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="74.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="195.2" y="74.7" width="1268.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="99.1" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="134.2" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="170.8" y="99.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="99.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="305" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="99.1" width="1134.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="97.6" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="170.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="183" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="207.4" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="292.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="305" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="341.6" y="123.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="439.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="451.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="463.6" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="561.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="610" y="123.5" width="841.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="172.3" width="1439.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="196.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="196.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="146.4" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#004578" x="170.8" y="196.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="256.2" y="196.7" width="1207.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="221.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="245.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="245.5" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="207.4" y="245.5" width="1244.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="269.9" width="256.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="269.9" width="1134.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="294.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="318.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="318.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="343.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="367.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="391.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="416.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="440.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="465.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="489.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="489.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="513.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="513.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="538.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="538.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="562.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="562.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="587.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="587.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="611.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="611.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="635.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="635.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="660.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="660.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="684.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="684.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="709.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="709.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="733.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="733.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="757.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="757.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="782.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="782.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="806.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="806.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="831.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="831.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="855.5" width="1037" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1061.4" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1134.6" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1159" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1232.2" y="855.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1268.8" y="855.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1329.8" y="855.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1366.4" y="855.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="879.9" width="1464" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="97.6" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="904.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="904.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="427" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="904.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="671" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="904.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="939.4" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1061.4" y="904.3" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="1281" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="1342" y="904.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="928.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="158.6" y="928.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="928.7" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="928.7" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="928.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="928.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="928.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="928.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="928.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1146.8" y="928.7" width="317.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="953.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="122" y="953.1" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="953.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="953.1" width="988.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-2991892322-matrix">\n    <text class="terminal-2991892322-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-2991892322-line-0)">⭘</text><text class="terminal-2991892322-r2" x="622.2" y="20" textLength="207.4" clip-path="url(#terminal-2991892322-line-0)">sase&#160;tui&#160;(v0.7.1)</text><text class="terminal-2991892322-r1" x="1464" y="20" textLength="12.2" clip-path="url(#terminal-2991892322-line-0)">\n</text><text class="terminal-2991892322-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-2991892322-line-1)">&#160;Agents&#160;</text><text class="terminal-2991892322-r4" x="109.8" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">&#160;│&#160;</text><text class="terminal-2991892322-r5" x="146.4" y="44.4" textLength="134.2" clip-path="url(#terminal-2991892322-line-1)">&#160;Artifacts&#160;</text><text class="terminal-2991892322-r4" x="280.6" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">&#160;│&#160;</text><text class="terminal-2991892322-r5" x="317.2" y="44.4" textLength="122" clip-path="url(#terminal-2991892322-line-1)">&#160;Services&#160;</text><text class="terminal-2991892322-r6" x="1305.4" y="44.4" textLength="85.4" clip-path="url(#terminal-2991892322-line-1)">inbox:&#160;</text><text class="terminal-2991892322-r7" x="1390.8" y="44.4" textLength="24.4" clip-path="url(#terminal-2991892322-line-1)">⚑1</text><text class="terminal-2991892322-r8" x="1427.4" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">✉18</text><text class="terminal-2991892322-r1" x="1464" y="44.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-1)">\n</text><text class="terminal-2991892322-r9" x="12.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">4</text><text class="terminal-2991892322-r6" x="24.4" y="68.8" textLength="24.4" clip-path="url(#terminal-2991892322-line-2)">&#160;[</text><text class="terminal-2991892322-r10" x="48.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="61" y="68.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-2)">&#160;running</text><text class="terminal-2991892322-r6" x="158.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r11" x="195.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="207.4" y="68.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-2)">&#160;waiting</text><text class="terminal-2991892322-r6" x="305" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r12" x="341.6" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="353.8" y="68.8" textLength="85.4" clip-path="url(#terminal-2991892322-line-2)">&#160;failed</text><text class="terminal-2991892322-r6" x="439.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r13" x="475.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="488" y="68.8" textLength="61" clip-path="url(#terminal-2991892322-line-2)">&#160;done</text><text class="terminal-2991892322-r6" x="549" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">]</text><text class="terminal-2991892322-r6" x="561.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r8" x="597.8" y="68.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-2)">zoom</text><text class="terminal-2991892322-r6" x="646.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="683.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">Z</text><text class="terminal-2991892322-r6" x="695.4" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="732" y="68.8" textLength="73.2" clip-path="url(#terminal-2991892322-line-2)">nodes&#160;</text><text class="terminal-2991892322-r9" x="805.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">1/4</text><text class="terminal-2991892322-r6" x="841.8" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="878.4" y="68.8" textLength="73.2" clip-path="url(#terminal-2991892322-line-2)">Ctrl+S</text><text class="terminal-2991892322-r6" x="951.6" y="68.8" textLength="24.4" clip-path="url(#terminal-2991892322-line-2)">&#160;·</text><text class="terminal-2991892322-r14" x="1049.2" y="68.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-2)">0/10</text><text class="terminal-2991892322-r6" x="1098" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r15" x="1134.6" y="68.8" textLength="329.4" clip-path="url(#terminal-2991892322-line-2)">codex/visual-snapshot-model</text><text class="terminal-2991892322-r1" x="1464" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">\n</text><text class="terminal-2991892322-r8" x="0" y="93.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-3)">»</text><text class="terminal-2991892322-r16" x="24.4" y="93.2" textLength="36.6" clip-path="url(#terminal-2991892322-line-3)">╭─&#160;</text><text class="terminal-2991892322-r8" x="61" y="93.2" textLength="134.2" clip-path="url(#terminal-2991892322-line-3)">AGENT&#160;SHELL</text><text class="terminal-2991892322-r16" x="195.2" y="93.2" textLength="1268.8" clip-path="url(#terminal-2991892322-line-3)">&#160;──────────────────────────────────────────────────────────────────────────────────────────────────────╮</text><text class="terminal-2991892322-r1" x="1464" y="93.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-3)">\n</text><text class="terminal-2991892322-r17" x="0" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r16" x="24.4" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r18" x="61" y="117.6" textLength="73.2" clip-path="url(#terminal-2991892322-line-4)">waiter</text><text class="terminal-2991892322-r19" x="134.2" y="117.6" textLength="36.6" clip-path="url(#terminal-2991892322-line-4)">&#160;·&#160;</text><text class="terminal-2991892322-r20" x="170.8" y="117.6" textLength="61" clip-path="url(#terminal-2991892322-line-4)">CODEX</text><text class="terminal-2991892322-r21" x="231.8" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">(</text><text class="terminal-2991892322-r22" x="244" y="117.6" textLength="61" clip-path="url(#terminal-2991892322-line-4)">gpt-5</text><text class="terminal-2991892322-r21" x="305" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">)</text><text class="terminal-2991892322-r16" x="1451.8" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r1" x="1464" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">\n</text><text class="terminal-2991892322-r17" x="0" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r16" x="24.4" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r23" x="61" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">⏳&#160;</text><text class="terminal-2991892322-r24" x="97.6" y="142" textLength="61" clip-path="url(#terminal-2991892322-line-5)">coder</text><text class="terminal-2991892322-r25" x="170.8" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">✓</text><text class="terminal-2991892322-r24" x="183" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="207.4" y="142" textLength="85.4" clip-path="url(#terminal-2991892322-line-5)">builder</text><text class="terminal-2991892322-r8" x="305" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">▶</text><text class="terminal-2991892322-r24" x="317.2" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="341.6" y="142" textLength="97.6" clip-path="url(#terminal-2991892322-line-5)">reviewer</text><text class="terminal-2991892322-r12" x="451.4" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">✗</text><text class="terminal-2991892322-r24" x="463.6" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="488" y="142" textLength="61" clip-path="url(#terminal-2991892322-line-5)">ghost</text><text class="terminal-2991892322-r26" x="561.2" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">?</text><text class="terminal-2991892322-r19" x="573.4" y="142" textLength="36.6" clip-path="url(#terminal-2991892322-line-5)">&#160;+1</text><text class="terminal-2991892322-r16" x="1451.8" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r1" x="1464" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">\n</text><text class="terminal-2991892322-r17" x="0" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r16" x="24.4" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r16" x="1451.8" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r1" x="1464" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">\n</text><text class="terminal-2991892322-r17" x="0" y="190.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-7)">│</text><text class="terminal-2991892322-r16" x="24.4" y="190.8" textLength="1439.6" clip-path="url(#terminal-2991892322-line-7)">╰─────────────────────────────────────────────────────────────────────────────────────────────────────────&#160;▾&#160;d&#160;more&#160;─╯</text><text class="terminal-2991892322-r1" x="1464" y="190.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-7)">\n</text><text class="terminal-2991892322-r17" x="0" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">│</text><text class="terminal-2991892322-r27" x="24.4" y="215.2" textLength="36.6" clip-path="url(#terminal-2991892322-line-8)">┌─&#160;</text><text class="terminal-2991892322-r28" x="61" y="215.2" textLength="85.4" clip-path="url(#terminal-2991892322-line-8)">◆&#160;MAIN&#160;</text><text class="terminal-2991892322-r4" x="146.4" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">┃</text><text class="terminal-2991892322-r29" x="170.8" y="215.2" textLength="85.4" clip-path="url(#terminal-2991892322-line-8)">Context</text><text class="terminal-2991892322-r27" x="256.2" y="215.2" textLength="1207.8" clip-path="url(#terminal-2991892322-line-8)">&#160;─────────────────────────────────────────────────────────────────────────────────────────────────┐</text><text class="terminal-2991892322-r1" x="1464" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">\n</text><text class="terminal-2991892322-r8" x="0" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">┃</text><text class="terminal-2991892322-r27" x="24.4" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">│</text><text class="terminal-2991892322-r1" x="1464" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">\n</text><text class="terminal-2991892322-r8" x="0" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">┃</text><text class="terminal-2991892322-r27" x="24.4" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">│</text><text class="terminal-2991892322-r30" x="61" y="264" textLength="146.4" clip-path="url(#terminal-2991892322-line-10)">AGENT&#160;PROMPT</text><text class="terminal-2991892322-r27" x="1451.8" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">│</text><text class="terminal-2991892322-r1" x="1464" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">│</text><text class="terminal-2991892322-r32" x="61" y="288.4" textLength="256.2" clip-path="url(#terminal-2991892322-line-11)">No&#160;prompt&#160;file&#160;found.</text><text class="terminal-2991892322-r27" x="1451.8" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">│</text><text class="terminal-2991892322-r1" x="1464" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">│</text><text class="terminal-2991892322-r1" x="1464" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">│</text><text class="terminal-2991892322-r1" x="1464" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">│</text><text class="terminal-2991892322-r1" x="1464" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">│</text><text class="terminal-2991892322-r1" x="1464" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">│</text><text class="terminal-2991892322-r1" x="1464" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">│</text><text class="terminal-2991892322-r1" x="1464" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">│</text><text class="terminal-2991892322-r1" x="1464" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">│</text><text class="terminal-2991892322-r1" x="1464" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">│</text><text class="terminal-2991892322-r1" x="1464" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">│</text><text class="terminal-2991892322-r1" x="1464" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">│</text><text class="terminal-2991892322-r1" x="1464" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">│</text><text class="terminal-2991892322-r1" x="1464" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">│</text><text class="terminal-2991892322-r1" x="1464" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">│</text><text class="terminal-2991892322-r1" x="1464" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">│</text><text class="terminal-2991892322-r1" x="1464" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">│</text><text class="terminal-2991892322-r1" x="1464" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">│</text><text class="terminal-2991892322-r1" x="1464" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">│</text><text class="terminal-2991892322-r1" x="1464" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">│</text><text class="terminal-2991892322-r1" x="1464" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">│</text><text class="terminal-2991892322-r1" x="1464" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">│</text><text class="terminal-2991892322-r1" x="1464" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">│</text><text class="terminal-2991892322-r1" x="1464" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">│</text><text class="terminal-2991892322-r1" x="1464" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="874" textLength="1037" clip-path="url(#terminal-2991892322-line-35)">└───────────────────────────────────────────────────────────────────────────────────&#160;</text><text class="terminal-2991892322-r33" x="1061.4" y="874" textLength="73.2" clip-path="url(#terminal-2991892322-line-35)">spread</text><text class="terminal-2991892322-r28" x="1159" y="874" textLength="73.2" clip-path="url(#terminal-2991892322-line-35)">main&#160;1</text><text class="terminal-2991892322-r5" x="1232.2" y="874" textLength="36.6" clip-path="url(#terminal-2991892322-line-35)">&#160;·&#160;</text><text class="terminal-2991892322-r27" x="1268.8" y="874" textLength="61" clip-path="url(#terminal-2991892322-line-35)">files</text><text class="terminal-2991892322-r5" x="1329.8" y="874" textLength="36.6" clip-path="url(#terminal-2991892322-line-35)">&#160;·&#160;</text><text class="terminal-2991892322-r27" x="1366.4" y="874" textLength="97.6" clip-path="url(#terminal-2991892322-line-35)">tools&#160;─┘</text><text class="terminal-2991892322-r1" x="1464" y="874" textLength="12.2" clip-path="url(#terminal-2991892322-line-35)">\n</text><text class="terminal-2991892322-r34" x="0" y="898.4" textLength="1464" clip-path="url(#terminal-2991892322-line-36)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-2991892322-r1" x="1464" y="898.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-36)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="922.8" textLength="85.4" clip-path="url(#terminal-2991892322-line-37)">&lt;enter&gt;</text><text class="terminal-2991892322-r6" x="109.8" y="922.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-37)">go&#160;to&#160;PR</text><text class="terminal-2991892322-r10" x="256.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">A</text><text class="terminal-2991892322-r6" x="280.6" y="922.8" textLength="146.4" clip-path="url(#terminal-2991892322-line-37)">auto-approve</text><text class="terminal-2991892322-r10" x="500.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">h</text><text class="terminal-2991892322-r6" x="524.6" y="922.8" textLength="146.4" clip-path="url(#terminal-2991892322-line-37)">parent&#160;tribe</text><text class="terminal-2991892322-r10" x="744.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">H</text><text class="terminal-2991892322-r6" x="768.6" y="922.8" textLength="170.8" clip-path="url(#terminal-2991892322-line-37)">collapse&#160;group</text><text class="terminal-2991892322-r10" x="988.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">n</text><text class="terminal-2991892322-r6" x="1012.6" y="922.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-37)">name</text><text class="terminal-2991892322-r35" x="1281" y="922.8" textLength="61" clip-path="url(#terminal-2991892322-line-37)">&#160;SVC&#160;</text><text class="terminal-2991892322-r35" x="1342" y="922.8" textLength="109.8" clip-path="url(#terminal-2991892322-line-37)">&#160;STOPPED&#160;</text><text class="terminal-2991892322-r1" x="1464" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">N</text><text class="terminal-2991892322-r6" x="36.6" y="947.2" textLength="122" clip-path="url(#terminal-2991892322-line-38)">edit&#160;tribe</text><text class="terminal-2991892322-r10" x="256.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">R</text><text class="terminal-2991892322-r6" x="280.6" y="947.2" textLength="61" clip-path="url(#terminal-2991892322-line-38)">retry</text><text class="terminal-2991892322-r10" x="500.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">V</text><text class="terminal-2991892322-r6" x="524.6" y="947.2" textLength="97.6" clip-path="url(#terminal-2991892322-line-38)">metadata</text><text class="terminal-2991892322-r10" x="744.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">w</text><text class="terminal-2991892322-r6" x="768.6" y="947.2" textLength="109.8" clip-path="url(#terminal-2991892322-line-38)">edit&#160;wait</text><text class="terminal-2991892322-r10" x="988.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">W</text><text class="terminal-2991892322-r6" x="1012.6" y="947.2" textLength="134.2" clip-path="url(#terminal-2991892322-line-38)">new&#160;w/&#160;wait</text><text class="terminal-2991892322-r1" x="1464" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-39)">x</text><text class="terminal-2991892322-r6" x="36.6" y="971.6" textLength="85.4" clip-path="url(#terminal-2991892322-line-39)">dismiss</text><text class="terminal-2991892322-r10" x="256.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-39)">X</text><text class="terminal-2991892322-r6" x="280.6" y="971.6" textLength="195.2" clip-path="url(#terminal-2991892322-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
_ test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail] _
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f61232f2430>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw2/test_agents_llm_calls_panel_de0')
detail_level = <ToolDetailLevel.FULL: 2>
snapshot_name = 'agents_llm_calls_panel_full_120x40'
title = 'ACE agents LLM Calls panel full detail'

    @pytest.mark.parametrize(
        ("detail_level", "snapshot_name", "title"),
        [
            (
                ToolDetailLevel.EXPANDED,
                "agents_llm_calls_panel_expanded_120x40",
                "ACE agents LLM Calls panel expanded detail",
            ),
            (
                ToolDetailLevel.FULL,
                "agents_llm_calls_panel_full_120x40",
                "ACE agents LLM Calls panel full detail",
            ),
        ],
    )
    async def test_agents_llm_calls_panel_detail_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        detail_level: ToolDetailLevel,
        snapshot_name: str,
        title: str,
    ) -> None:
        _pin_llm_calls_panel_now(monkeypatch)
        _clear_llm_calls_cache()
    
        artifacts_dir = tmp_path / "ace-run" / "20260509100000"
        _populate_expanded_tool_calls(artifacts_dir)
        agent = _llm_calls_agent(artifacts_dir)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            panel = await _open_llm_calls_panel(page)
            assert panel.set_detail_level(detail_level) is True
            page.app._refresh_agent_footer_bindings_only()
            page.app.refresh(layout=True)
            await page.app.wait_for_refresh()
            if detail_level is ToolDetailLevel.FULL:
>               llm_calls_scroll = page.app.query_one("#agent-llm-calls-scroll")
                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py:438: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-llm-calls-scroll', expect_type = None

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-llm-calls-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b280a6e40>

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

page = <sase.ace.testing.ace_page.AcePage object at 0x7f9afffa8110>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_______________ test_config_center_plugins_loading_png_snapshot ________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2ed41e5470>

    async def test_config_center_plugins_loading_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Suppressing the worker keeps the pane in its initial loading state."""
        patch_startup_loaders(monkeypatch)
        _patch_xprompt_sources(monkeypatch)
        _patch_config_view(monkeypatch, _build_view(_config_schema(), _config_layers()))
        _patch_plugins_catalog(monkeypatch)
        monkeypatch.setattr(
            PluginsBrowserPane, "_start_load", lambda self, *, force=False: None
        )
    
>       async with AcePage(query='"visual"', patches=patches()) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py:560: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:308: in __aexit__
    await stack.__aexit__(exc_type, exc_val, exc_tb)
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:768: in __aexit__
    raise exc
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:751: in __aexit__
    cb_suppress = await cb(*exc_details)
                  ^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:595: in _pre_process
    await self._dispatch_message(events.Mount())
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PluginsBrowserPane(id='updates')

    def on_mount(self) -> None:
        from sase.ace.tui.util.debounce import DetailPanelDebouncer
    
        from .plugins_browser_loading import is_session_memo_usable
    
        self._detail_debouncer = DetailPanelDebouncer(self.app)
        self._sync_state_visibility()
        self._sync_header()
        if self._auto_load:
            memo = self._session_state.inventory
            automatic_status = getattr(self.app, "_automatic_update_status", None)
            if is_session_memo_usable(memo, automatic_status):
                self._apply_load_result(memo, restored=True)
            else:
>               self._start_load(force=False, cache_only=True)
E               TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() got an unexpected keyword argument 'cache_only'

src/sase/ace/tui/modals/plugins_browser_layout.py:139: TypeError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/ │
│ tui/modals/plugins_browser_layout.py:139 in on_mount                         │
│                                                                              │
│   136 │   │   │   if is_session_memo_usable(memo, automatic_status):         │
│   137 │   │   │   │   self._apply_load_result(memo, restored=True)           │
│   138 │   │   │   else:                                                      │
│ ❱ 139 │   │   │   │   self._start_load(force=False, cache_only=True)         │
│   140 │                                                                      │
│   141 │   def on_unmount(self) -> None:                                      │
│   142 │   │   if self._detail_debouncer is not None:                         │
│                                                                              │
│ ╭────────────────────── locals ───────────────────────╮                      │
│ │ automatic_status = None                             │                      │
│ │             memo = None                             │                      │
│ │             self = PluginsBrowserPane(id='updates') │                      │
│ ╰─────────────────────────────────────────────────────╯                      │
╰──────────────────────────────────────────────────────────────────────────────╯
TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() 
got an unexpected keyword argument 'cache_only'
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:375 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 595, in _pre_process
    await self._dispatch_message(events.Mount())
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/modals/plugins_browser_layout.py", line 139, in on_mount
    self._start_load(force=False, cache_only=True)
    ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() got an unexpected keyword argument 'cache_only'
_______________ test_agents_decks_single_main_reply_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b098d7b60>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_agents_decks_single_main_0')

    async def test_agents_decks_single_main_reply_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_reply_agent(tmp_path)])
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _goto_agents(page, 1)
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            await wait_for_state(
                page,
                lambda: set(detail._main_deck_document.card_ids) == {"context", "reply"},
                description="Main deck has Context and Reply cards",
            )
            await page.press("ctrl+j")
            await wait_for_visual_idle(page)
>           assert detail.deck_area.panel(0).main_view.active_card_id == "reply"
E           AssertionError: assert 'context' == 'reply'
E             
E             - reply
E             + context

tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py:109: AssertionError
____________ test_agents_decks_context_reply_no_files_png_snapshot _____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b1b4ad320>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_agents_decks_context_repl0')

    async def test_agents_decks_context_reply_no_files_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_reply_agent(tmp_path)])
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _goto_agents(page, 1)
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            await wait_for_state(
                page,
                lambda: set(detail._main_deck_document.card_ids) == {"context", "reply"},
                description="Main deck has Context and Reply cards",
            )
            # Force known no-files/no-tools so the new panel duplicates Main.
            detail.deck_area.panel(0)._availability = {
                DeckId.MAIN: DeckAvailability(True, 2),
                DeckId.FILES: DeckAvailability(False, 0),
                DeckId.TOOLS: DeckAvailability(False, 0),
            }
            await page.press("vertical_line")
            await wait_for_visual_idle(page)
            panel0 = detail.deck_area.panel(0)
            panel1 = detail.deck_area.panel(1)
            assert panel1.deck is DeckId.MAIN
>           assert panel0.main_view.active_card_id != panel1.main_view.active_card_id
E           AssertionError: assert 'context' != 'context'
E            +  where 'context' = MainDeckView().active_card_id
E            +    where MainDeckView() = DeckPanel(id='agent-deck-panel-0', classes='-unfocused deck-panel -deck-main').main_view
E            +  and   'context' = MainDeckView().active_card_id
E            +    where MainDeckView() = DeckPanel(id='agent-deck-panel-1', classes='deck-panel -deck-main -focused').main_view

tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py:192: AssertionError
____________ test_agents_external_repo_diff_file_panel_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b1b285630>

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
            await reveal_agent_file_view(page)
            await wait_for_svg_contains(page, "external repo")
    
            assert_page_svg_contains(page, "gh:pallets/click")
            assert_page_svg_contains(page, "external repo")
            assert_page_svg_contains(page, "sase/repos/external")
>           ace_png_visual.assert_page_png(
                page,
                "agents_external_repo_diff_file_panel_120x40",
                title="ACE agents external repo diff file panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:134: in assert_page_png
    assert_visual_frame_converged(page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f9b04d4de50>

    def assert_visual_frame_converged(page: AcePage) -> None:
        """Prove that *page* still renders the frame accepted by convergence.
    
        The canonical re-export and the caller's titled PNG export are both
        synchronous, so Textual cannot advance between this check and capture.
        """
        expected = getattr(page, _VISUAL_CONVERGED_SVG_ATTR, None)
        if expected is None:
            raise AssertionError(
                "ACE PNG capture requires wait_for_visual_idle(page) before "
                "assert_page_png()"
            )
    
        actual = page.export_svg(title=_VISUAL_CONVERGENCE_TITLE)
        if actual != expected:
            expected_digest = hashlib.sha256(expected.encode()).hexdigest()[:12]
            actual_digest = hashlib.sha256(actual.encode()).hexdigest()[:12]
>           raise AssertionError(
                "ACE PNG capture frame changed after visual convergence; make "
                "wait_for_visual_idle(page) the final await before capture "
                f"(converged_digest={expected_digest}, capture_digest={actual_digest})"
            )
E           AssertionError: ACE PNG capture frame changed after visual convergence; make wait_for_visual_idle(page) the final await before capture (converged_digest=4b0b9def1666, capture_digest=de7665535179)

tests/ace/tui/visual/_ace_png_snapshot_waits.py:126: AssertionError
_______ test_family_panel_fold_levels_and_member_override_png_snapshots ________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b0cabe740>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_family_panel_fold_levels_0')

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
>           assert panel.active_section_identity == "agent-xprompt"
E           AssertionError: assert None == 'agent-xprompt'
E            +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:65: AssertionError
_____________ test_agents_linked_repo_diff_file_panel_png_snapshot _____________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd96b1aea50>

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
            await reveal_agent_file_view(page)
            await wait_for_svg_contains(page, "linked repo")
    
            assert_page_svg_contains(page, "sase-core")
            assert_page_svg_contains(page, "linked repo")
            assert_page_svg_contains(page, "/workspace/sase-core_14")
>           file_scroll = page.app.query_one("#agent-file-scroll", VerticalScroll)
                          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:233: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-file-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-file-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
________________ test_agents_commit_messages_panel_png_snapshot ________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd9716e6190>

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
            await reveal_agent_file_view(page)
            # The sticky header panel shrinks the body viewport, so scroll
            # until every asserted row is visible instead of a fixed count.
            targets = (
                "Deltas:",
                "agent_deltas.py",
                "file_panel.py",
                "sase-core",
                "files [1/3]",
                "primary_001.diff",
            )
            for _ in range(14):
                visible = page_svg_text(page, title="ACE commit deltas scroll check")
                if all(target in visible for target in targets):
                    break
                await page.press("ctrl+f")
                await wait_for_visual_idle(page)
    
>           assert_page_svg_contains(page, "Deltas:")

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:278: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fd9681d1a90>
text = 'Deltas:'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
________ test_agents_metadata_search_typing_and_committed_png_snapshots ________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd9839bcde0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw7/test_agents_metadata_search_ty0')

    async def test_agents_metadata_search_typing_and_committed_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        agent = zoom_agent(tmp_path)
        agent.diff_path = None
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            initial_tab="agents",
        ) as page:
            await wait_for_startup(page)
            await page.expect_state("agent_count", 1)
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _state: "zoom.snapshot.agent" in prompt_header_and_body_text(panel),
            )
    
            # The sticky header keeps identity fields out of the search corpus,
            # so search a body term ("prompt" hits the section title and the
            # empty notice) rather than the detached agent name.
            await page.press("comma", "slash", "p", "r", "o", "m", "p", "t")
            await page.wait_for(
                lambda _state: (
                    page.app._agent_metadata_search.mode == "typing"
                    and len(page.app._agent_metadata_search.match_spans) > 1
                ),
            )
            await wait_for_visual_idle(page)
            ace_png_visual.assert_page_png(
                page,
                "agents_metadata_search_typing_120x40",
                title="ACE agents metadata search typing",
            )
    
            await page.press("enter", "n")
>           command = page.app.query_one("#agent-search-command", Static)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py:66: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-search-command'
expect_type = <class 'textual.widgets._static.Static'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-search-command' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
_________________ test_selected_gate_shell_output_png_snapshot _________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b28f78d00>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_selected_gate_shell_outpu0')

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
            # Document-level check: the jump footer panel now takes detail height,
            # so this title can sit below the first viewport even at scroll zero.
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            assert "Run deployment preview" in prompt_header_and_body_text(prompt)
>           scroll = page.query_one_widget("#agent-prompt-scroll", VerticalScroll)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:149: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:384: in query_one_widget
    return self._app.query_one(selector, widget_type)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-prompt-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-prompt-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
______ test_monitor_state_detail_png_snapshots[running-overrides0-120-40] ______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b247090f0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_0')
slug = 'running'
overrides = {'monitor_state': 'running', 'status': 'TESTING', 'output': 'collecting diagnostics...\n'}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
__ test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40] ___
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b1806c600>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_1')
slug = 'host_completed'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'all checks passed\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_ test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40] _
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b28f78d00>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_2')
slug = 'failed_diagnostics'
overrides = {'monitor_state': 'failed', 'status': 'TESTED', 'exit_code': 1, 'output': 'FAILED tests/monitor/test_delivery.py::test_case\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
______ test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40] ______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b19cc4280>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_3')
slug = 'timeout'
overrides = {'monitor_state': 'timeout', 'status': 'TESTED', 'exit_code': 124, 'output': 'timed out waiting for quiet shard\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
___________________ test_agents_collapsed_panel_png_snapshot ___________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd98506a350>

    async def test_agents_collapsed_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=_panel_collapse_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            container = page.app.query_one("#agent-list-container")
            assert "chop" not in page.app._collapsed_panel_keys
            assert "chop" not in page.app._expanded_panel_keys
            await page.press("J")
            assert page.app._panel_group.focused_key == "keep"
            await page.press("J")
            assert page.app._panel_group.focused_key is None
            await page.press("J")
            assert page.app._panel_group.focused_key == "keep"
            await page.press("h")
            await page.press("j")
            assert page.app._panel_group.focused_key == "chop"
            panel_focus = page.app._resolve_focused_panel()
            assert panel_focus is not None and panel_focus.collapsed
            await wait_for_svg_contains(page, "▸ ")
            await wait_for_visual_idle(page)
    
            assert page.app._panel_group.panel_keys[-1] == "chop"
            collapsed_widget = page.app.query_one(f"#{panel_widget_id_for_key('chop')}")
            assert collapsed_widget.option_count == 0
            assert collapsed_widget.styles.height is not None
            assert collapsed_widget.styles.height.value == 2.0
            assert (
                Text.from_markup(collapsed_widget.border_title).plain
                == "▸ † @job · 2 [R1 W1]"
            )
>           _assert_collapsed_panel_summary(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:266: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fd965c2e2d0>

    def _assert_collapsed_panel_summary(page: AcePage) -> None:
        """Assert the right pane represents ``@job``, not its hidden first row."""
        detail = page.app.query_one("#agent-detail-panel", AgentDetail)
        prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
        info = page.app.query_one("#agent-info-panel", AgentInfoPanel)
    
        assert detail._current_agent is None
        assert detail._current_tribe_identity == ("panel", "chop")
        assert page.app._get_selected_agent() is None
        snapshot = page.app._focused_tribe_summary()
        assert snapshot is not None
        assert snapshot.label == "† @job"
        rendered = prompt_header_and_body_text(prompt)
        assert "TRIBE\n" in rendered
        assert "Name: † @job" in rendered
        assert "Panel:" not in rendered
        assert "Fold: 1/4" in rendered
        assert "[R1 W1]" in rendered
        assert "TRIBE MEMBERS · 2" in rendered
        assert "visual.collapse.primary.with.a.deliberately.wide.row" in rendered
>       assert info._view_mode == "tribe"
               ^^^^^^^^^^^^^^^
E       AttributeError: 'AgentInfoPanel' object has no attribute '_view_mode'

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:151: AttributeError
_______ test_monitor_state_detail_png_snapshots[lost-overrides4-120-40] ________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b26a022e0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_4')
slug = 'lost'
overrides = {'monitor_state': 'lost', 'status': 'TESTED', 'output': 'last retained line before reboot\n', 'result_ref': 'artifact:lost-result'}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe877c6b0e0>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fe8816b38a0>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fe863e56610>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fe863e57b60>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fe895e016f0>, backoff_after_misses = 3
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
_____ test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40] ______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b280a6e40>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_5')
slug = 'degraded'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'checks passed, workspace fallback used\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
__ test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40] __
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b28d675b0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_monitor_state_detail_png_6')
slug = 'needs_attention'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'checks passed, continuation could not launch\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b1283e430>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_family_panel_shells_monit0')

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
            assert_page_svg_contains(page, "3 shells")
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "FAMILY SHELLS")
            combined = prompt_header_and_body_text(
                page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            )
            # At assertion width the monitor lane shows its command; at panel
            # width it wraps to the "why" reason continuation instead.
            assert "just check-full --include visual" in combined
            ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_monitor_120x40",
                title="ACE family panel shell metadata with monitor",
            )
    
            await page.press(".")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "FAMILY SHELLS")
            assert_page_svg_contains(page, "--plan")
            assert_page_svg_contains(page, "--mon")
            assert_page_svg_contains(page, "⚙ MONITOR")
>           assert_page_svg_contains(page, "just check")

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:308: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f9afffa6990>
text = 'just check'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b166215c0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-28/popen-gw0/test_family_conversation_monit0')

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
>           assert panel.active_section_identity == "agent-reply"
E           AssertionError: assert None == 'agent-reply'
E            +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:352: AssertionError
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe87b9fd010>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fe8826feb90>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fe8826fc300>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fe866872b90>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fe895e016f0>, backoff_after_misses = 3
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
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
35.62s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
23.61s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
20.19s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
16.61s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
16.53s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
16.39s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
15.89s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
15.74s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
15.06s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
15.04s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_expanded_png_snapshot
14.01s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
13.98s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
13.12s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_new_png_snapshot
13.10s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_stacked_pane_png_snapshot
13.05s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_markdown.py::test_prompt_ordered_highlight_solo_png_snapshot[textual-dark-prompt_ordered_highlight_solo_dark_120x40-ACE prompt input \u2014 ordered-marker highlighting, dark theme]
12.95s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_collapsed_two_digit_overflow_png_snapshot
12.95s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py::test_prompt_jinja_invalid_png_snapshot
12.93s call     tests/ace/tui/visual/test_ace_png_snapshots_model_alias_completion.py::test_model_alias_completion_full_menu_png_snapshot[textual-dark-prompt_model_alias_completion_full_dark_120x40-ACE prompt input \u2014 equals alias completion full menu, dark theme]
12.88s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_submit_choice_targeted_png_snapshot
12.64s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_full_menu_png_snapshot[light]
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_plugins_loading_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_reply_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_context_reply_no_files_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_linked_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py::test_agents_metadata_search_typing_and_committed_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_selected_gate_shell_output_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
====== 28 failed, 993 passed, 1 skipped, 8 warnings in 644.81s (0:10:44) =======
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 8/8 workers
8 workers [28 items]

FFFFFFFFFFFFFFFFFFFFFFFFFFFF                                             [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_______________ test_config_center_plugins_loading_png_snapshot ________________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb6d51ddd90>

    async def test_config_center_plugins_loading_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Suppressing the worker keeps the pane in its initial loading state."""
        patch_startup_loaders(monkeypatch)
        _patch_xprompt_sources(monkeypatch)
        _patch_config_view(monkeypatch, _build_view(_config_schema(), _config_layers()))
        _patch_plugins_catalog(monkeypatch)
        monkeypatch.setattr(
            PluginsBrowserPane, "_start_load", lambda self, *, force=False: None
        )
    
>       async with AcePage(query='"visual"', patches=patches()) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py:560: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:308: in __aexit__
    await stack.__aexit__(exc_type, exc_val, exc_tb)
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:768: in __aexit__
    raise exc
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:751: in __aexit__
    cb_suppress = await cb(*exc_details)
                  ^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:595: in _pre_process
    await self._dispatch_message(events.Mount())
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PluginsBrowserPane(id='updates')

    def on_mount(self) -> None:
        from sase.ace.tui.util.debounce import DetailPanelDebouncer
    
        from .plugins_browser_loading import is_session_memo_usable
    
        self._detail_debouncer = DetailPanelDebouncer(self.app)
        self._sync_state_visibility()
        self._sync_header()
        if self._auto_load:
            memo = self._session_state.inventory
            automatic_status = getattr(self.app, "_automatic_update_status", None)
            if is_session_memo_usable(memo, automatic_status):
                self._apply_load_result(memo, restored=True)
            else:
>               self._start_load(force=False, cache_only=True)
E               TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() got an unexpected keyword argument 'cache_only'

src/sase/ace/tui/modals/plugins_browser_layout.py:139: TypeError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/ │
│ tui/modals/plugins_browser_layout.py:139 in on_mount                         │
│                                                                              │
│   136 │   │   │   if is_session_memo_usable(memo, automatic_status):         │
│   137 │   │   │   │   self._apply_load_result(memo, restored=True)           │
│   138 │   │   │   else:                                                      │
│ ❱ 139 │   │   │   │   self._start_load(force=False, cache_only=True)         │
│   140 │                                                                      │
│   141 │   def on_unmount(self) -> None:                                      │
│   142 │   │   if self._detail_debouncer is not None:                         │
│                                                                              │
│ ╭────────────────────── locals ───────────────────────╮                      │
│ │ automatic_status = None                             │                      │
│ │             memo = None                             │                      │
│ │             self = PluginsBrowserPane(id='updates') │                      │
│ ╰─────────────────────────────────────────────────────╯                      │
╰──────────────────────────────────────────────────────────────────────────────╯
TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() 
got an unexpected keyword argument 'cache_only'
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:375 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 595, in _pre_process
    await self._dispatch_message(events.Mount())
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/modals/plugins_browser_layout.py", line 139, in on_mount
    self._start_load(force=False, cache_only=True)
    ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() got an unexpected keyword argument 'cache_only'
_____________ test_agents_linked_repo_diff_file_panel_png_snapshot _____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6ebc9cdd90>

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
            await reveal_agent_file_view(page)
            await wait_for_svg_contains(page, "linked repo")
    
            assert_page_svg_contains(page, "sase-core")
            assert_page_svg_contains(page, "linked repo")
            assert_page_svg_contains(page, "/workspace/sase-core_14")
>           file_scroll = page.app.query_one("#agent-file-scroll", VerticalScroll)
                          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:233: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-file-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-file-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________ test_agents_external_repo_diff_file_panel_png_snapshot ____________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f49f5acdd90>

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
            await reveal_agent_file_view(page)
            await wait_for_svg_contains(page, "external repo")
    
            assert_page_svg_contains(page, "gh:pallets/click")
            assert_page_svg_contains(page, "external repo")
            assert_page_svg_contains(page, "sase/repos/external")
>           ace_png_visual.assert_page_png(
                page,
                "agents_external_repo_diff_file_panel_120x40",
                title="ACE agents external repo diff file panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:134: in assert_page_png
    assert_visual_frame_converged(page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f49f5521010>

    def assert_visual_frame_converged(page: AcePage) -> None:
        """Prove that *page* still renders the frame accepted by convergence.
    
        The canonical re-export and the caller's titled PNG export are both
        synchronous, so Textual cannot advance between this check and capture.
        """
        expected = getattr(page, _VISUAL_CONVERGED_SVG_ATTR, None)
        if expected is None:
            raise AssertionError(
                "ACE PNG capture requires wait_for_visual_idle(page) before "
                "assert_page_png()"
            )
    
        actual = page.export_svg(title=_VISUAL_CONVERGENCE_TITLE)
        if actual != expected:
            expected_digest = hashlib.sha256(expected.encode()).hexdigest()[:12]
            actual_digest = hashlib.sha256(actual.encode()).hexdigest()[:12]
>           raise AssertionError(
                "ACE PNG capture frame changed after visual convergence; make "
                "wait_for_visual_idle(page) the final await before capture "
                f"(converged_digest={expected_digest}, capture_digest={actual_digest})"
            )
E           AssertionError: ACE PNG capture frame changed after visual convergence; make wait_for_visual_idle(page) the final await before capture (converged_digest=1bd05881ff3c, capture_digest=de7665535179)

tests/ace/tui/visual/_ace_png_snapshot_waits.py:126: AssertionError
__ test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40] __
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0f53739d90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw6/test_monitor_state_detail_png_0')
slug = 'needs_attention'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'checks passed, continuation could not launch\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b2003dd90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw1/test_family_conversation_monit0')

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
>           assert panel.active_section_identity == "agent-reply"
E           AssertionError: assert None == 'agent-reply'
E            +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:352: AssertionError
________________ test_tribe_panel_clan_summaries_png_snapshots _________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb3d0139d90>

    async def test_tribe_panel_clan_summaries_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_clan_summary_agents())
    
        async with AcePage(query='"visual-"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 2)
            await wait_for_visual_idle(page)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _screen: "CLAN SUMMARIES" in prompt_header_and_body_text(panel),
                timeout=30.0,
            )
    
>           await _jump_to_clan_summaries(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py:120: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fb3cfd9d160>

    async def _jump_to_clan_summaries(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(10):
            if panel.active_section_identity == "tribe:clan-summaries":
                break
            await page.press("ctrl+j")
>       assert panel.active_section_identity == "tribe:clan-summaries"
E       AssertionError: assert None == 'tribe:clan-summaries'
E        +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py:89: AssertionError
_ test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40] _
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff59c3c1d90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw5/test_monitor_state_detail_png_0')
slug = 'failed_diagnostics'
overrides = {'monitor_state': 'failed', 'status': 'TESTED', 'exit_code': 1, 'output': 'FAILED tests/monitor/test_delivery.py::test_case\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9f60dc1d90>

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

page = <sase.ace.testing.ace_page.AcePage object at 0x7f9f60829160>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
________ test_agents_metadata_search_typing_and_committed_png_snapshots ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6eb9000550>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw2/test_agents_metadata_search_ty0')

    async def test_agents_metadata_search_typing_and_committed_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        agent = zoom_agent(tmp_path)
        agent.diff_path = None
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            initial_tab="agents",
        ) as page:
            await wait_for_startup(page)
            await page.expect_state("agent_count", 1)
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _state: "zoom.snapshot.agent" in prompt_header_and_body_text(panel),
            )
    
            # The sticky header keeps identity fields out of the search corpus,
            # so search a body term ("prompt" hits the section title and the
            # empty notice) rather than the detached agent name.
            await page.press("comma", "slash", "p", "r", "o", "m", "p", "t")
            await page.wait_for(
                lambda _state: (
                    page.app._agent_metadata_search.mode == "typing"
                    and len(page.app._agent_metadata_search.match_spans) > 1
                ),
            )
            await wait_for_visual_idle(page)
            ace_png_visual.assert_page_png(
                page,
                "agents_metadata_search_typing_120x40",
                title="ACE agents metadata search typing",
            )
    
            await page.press("enter", "n")
>           command = page.app.query_one("#agent-search-command", Static)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py:66: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-search-command'
expect_type = <class 'textual.widgets._static.Static'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-search-command' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
_ test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail] _
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb6d4cd0a50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw4/test_agents_llm_calls_panel_de0')
detail_level = <ToolDetailLevel.FULL: 2>
snapshot_name = 'agents_llm_calls_panel_full_120x40'
title = 'ACE agents LLM Calls panel full detail'

    @pytest.mark.parametrize(
        ("detail_level", "snapshot_name", "title"),
        [
            (
                ToolDetailLevel.EXPANDED,
                "agents_llm_calls_panel_expanded_120x40",
                "ACE agents LLM Calls panel expanded detail",
            ),
            (
                ToolDetailLevel.FULL,
                "agents_llm_calls_panel_full_120x40",
                "ACE agents LLM Calls panel full detail",
            ),
        ],
    )
    async def test_agents_llm_calls_panel_detail_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        detail_level: ToolDetailLevel,
        snapshot_name: str,
        title: str,
    ) -> None:
        _pin_llm_calls_panel_now(monkeypatch)
        _clear_llm_calls_cache()
    
        artifacts_dir = tmp_path / "ace-run" / "20260509100000"
        _populate_expanded_tool_calls(artifacts_dir)
        agent = _llm_calls_agent(artifacts_dir)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            panel = await _open_llm_calls_panel(page)
            assert panel.set_detail_level(detail_level) is True
            page.app._refresh_agent_footer_bindings_only()
            page.app.refresh(layout=True)
            await page.app.wait_for_refresh()
            if detail_level is ToolDetailLevel.FULL:
>               llm_calls_scroll = page.app.query_one("#agent-llm-calls-scroll")
                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py:438: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-llm-calls-scroll', expect_type = None

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-llm-calls-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
__________________ test_tribe_panel_four_level_png_snapshots ___________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb3cfb4ba50>

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
>           await _settle_tribe_visual(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:405: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:50: in _settle_tribe_visual
    scroll = page.app.query_one("#agent-prompt-scroll", VerticalScroll)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-prompt-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-prompt-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________ test_agents_decks_context_reply_no_files_png_snapshot _____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9f5d842150>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw0/test_agents_decks_context_repl0')

    async def test_agents_decks_context_reply_no_files_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_reply_agent(tmp_path)])
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _goto_agents(page, 1)
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            await wait_for_state(
                page,
                lambda: set(detail._main_deck_document.card_ids) == {"context", "reply"},
                description="Main deck has Context and Reply cards",
            )
            # Force known no-files/no-tools so the new panel duplicates Main.
            detail.deck_area.panel(0)._availability = {
                DeckId.MAIN: DeckAvailability(True, 2),
                DeckId.FILES: DeckAvailability(False, 0),
                DeckId.TOOLS: DeckAvailability(False, 0),
            }
            await page.press("vertical_line")
            await wait_for_visual_idle(page)
            panel0 = detail.deck_area.panel(0)
            panel1 = detail.deck_area.panel(1)
            assert panel1.deck is DeckId.MAIN
>           assert panel0.main_view.active_card_id != panel1.main_view.active_card_id
E           AssertionError: assert 'context' != 'context'
E            +  where 'context' = MainDeckView().active_card_id
E            +    where MainDeckView() = DeckPanel(id='agent-deck-panel-0', classes='deck-panel -deck-main -unfocused').main_view
E            +  and   'context' = MainDeckView().active_card_id
E            +    where MainDeckView() = DeckPanel(id='agent-deck-panel-1', classes='-focused deck-panel -deck-main').main_view

tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py:192: AssertionError
___________________ test_agents_collapsed_panel_png_snapshot ___________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6eb9356b70>

    async def test_agents_collapsed_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=_panel_collapse_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            container = page.app.query_one("#agent-list-container")
            assert "chop" not in page.app._collapsed_panel_keys
            assert "chop" not in page.app._expanded_panel_keys
            await page.press("J")
            assert page.app._panel_group.focused_key == "keep"
            await page.press("J")
            assert page.app._panel_group.focused_key is None
            await page.press("J")
            assert page.app._panel_group.focused_key == "keep"
            await page.press("h")
            await page.press("j")
            assert page.app._panel_group.focused_key == "chop"
            panel_focus = page.app._resolve_focused_panel()
            assert panel_focus is not None and panel_focus.collapsed
            await wait_for_svg_contains(page, "▸ ")
            await wait_for_visual_idle(page)
    
            assert page.app._panel_group.panel_keys[-1] == "chop"
            collapsed_widget = page.app.query_one(f"#{panel_widget_id_for_key('chop')}")
            assert collapsed_widget.option_count == 0
            assert collapsed_widget.styles.height is not None
            assert collapsed_widget.styles.height.value == 2.0
            assert (
                Text.from_markup(collapsed_widget.border_title).plain
                == "▸ † @job · 2 [R1 W1]"
            )
>           _assert_collapsed_panel_summary(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:266: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f6ebbbd0550>

    def _assert_collapsed_panel_summary(page: AcePage) -> None:
        """Assert the right pane represents ``@job``, not its hidden first row."""
        detail = page.app.query_one("#agent-detail-panel", AgentDetail)
        prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
        info = page.app.query_one("#agent-info-panel", AgentInfoPanel)
    
        assert detail._current_agent is None
        assert detail._current_tribe_identity == ("panel", "chop")
        assert page.app._get_selected_agent() is None
        snapshot = page.app._focused_tribe_summary()
        assert snapshot is not None
        assert snapshot.label == "† @job"
        rendered = prompt_header_and_body_text(prompt)
        assert "TRIBE\n" in rendered
        assert "Name: † @job" in rendered
        assert "Panel:" not in rendered
        assert "Fold: 1/4" in rendered
        assert "[R1 W1]" in rendered
        assert "TRIBE MEMBERS · 2" in rendered
        assert "visual.collapse.primary.with.a.deliberately.wide.row" in rendered
>       assert info._view_mode == "tribe"
               ^^^^^^^^^^^^^^^
E       AttributeError: 'AgentInfoPanel' object has no attribute '_view_mode'

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:151: AttributeError
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b2034db50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw1/test_family_panel_shells_monit0')

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
            assert_page_svg_contains(page, "3 shells")
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "FAMILY SHELLS")
            combined = prompt_header_and_body_text(
                page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            )
            # At assertion width the monitor lane shows its command; at panel
            # width it wraps to the "why" reason continuation instead.
            assert "just check-full --include visual" in combined
            ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_monitor_120x40",
                title="ACE family panel shell metadata with monitor",
            )
    
            await page.press(".")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "FAMILY SHELLS")
            assert_page_svg_contains(page, "--plan")
            assert_page_svg_contains(page, "--mon")
            assert_page_svg_contains(page, "⚙ MONITOR")
>           assert_page_svg_contains(page, "just check")

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:308: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f9b31db9810>
text = 'just check'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_______ test_family_panel_fold_levels_and_member_override_png_snapshots ________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f49f5647150>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw3/test_family_panel_fold_levels_0')

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
>           assert panel.active_section_identity == "agent-xprompt"
E           AssertionError: assert None == 'agent-xprompt'
E            +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:65: AssertionError
______ test_monitor_state_detail_png_snapshots[running-overrides0-120-40] ______
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0f5314dd50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw6/test_monitor_state_detail_png_1')
slug = 'running'
overrides = {'monitor_state': 'running', 'status': 'TESTING', 'output': 'collecting diagnostics...\n'}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
__ test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40] ___
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff59bdd1d50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw5/test_monitor_state_detail_png_1')
slug = 'host_completed'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'all checks passed\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_______________ test_agents_decks_single_main_reply_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9f5d93c9b0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw0/test_agents_decks_single_main_0')

    async def test_agents_decks_single_main_reply_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_reply_agent(tmp_path)])
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _goto_agents(page, 1)
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            await wait_for_state(
                page,
                lambda: set(detail._main_deck_document.card_ids) == {"context", "reply"},
                description="Main deck has Context and Reply cards",
            )
            await page.press("ctrl+j")
            await wait_for_visual_idle(page)
>           assert detail.deck_area.panel(0).main_view.active_card_id == "reply"
E           AssertionError: assert 'context' == 'reply'
E             
E             - reply
E             + context

tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py:109: AssertionError
_________________ test_selected_gate_shell_output_png_snapshot _________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f49f471e7b0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw3/test_selected_gate_shell_outpu0')

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
            # Document-level check: the jump footer panel now takes detail height,
            # so this title can sit below the first viewport even at scroll zero.
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            assert "Run deployment preview" in prompt_header_and_body_text(prompt)
>           scroll = page.query_one_widget("#agent-prompt-scroll", VerticalScroll)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:149: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:384: in query_one_widget
    return self._app.query_one(selector, widget_type)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-prompt-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-prompt-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________________ test_tribe_panel_prompts_png_snapshots ____________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb3ce944d70>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw7/test_tribe_panel_prompts_png_s0')

    async def test_tribe_panel_prompts_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_prompt_agents(tmp_path))
    
        async with AcePage(query='"visual-prompts"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _screen: "PROMPTS" in prompt_header_and_body_text(panel),
                timeout=30.0,
            )
            assert page.app._member_jump_maps[("panel", "epic")].targets
    
>           await _jump_to_prompts(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py:212: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fb3ccb2f390>

    async def _jump_to_prompts(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(10):
            if panel.active_section_identity == "tribe:prompts":
                break
            await page.press("ctrl+j")
>       assert panel.active_section_identity == "tribe:prompts"
E       AssertionError: assert None == 'tribe:prompts'
E        +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py:179: AssertionError
_____ test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40] ______
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9b1fcb6d50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw1/test_monitor_state_detail_png_0')
slug = 'degraded'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'checks passed, workspace fallback used\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
______ test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40] ______
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0f50193e30>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw6/test_monitor_state_detail_png_2')
slug = 'timeout'
overrides = {'monitor_state': 'timeout', 'status': 'TESTED', 'exit_code': 124, 'output': 'timed out waiting for quiet shard\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_______ test_monitor_state_detail_png_snapshots[lost-overrides4-120-40] ________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff598ce5220>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-29/popen-gw5/test_monitor_state_detail_png_2')
slug = 'lost'
overrides = {'monitor_state': 'lost', 'status': 'TESTED', 'output': 'last retained line before reboot\n', 'result_ref': 'artifact:lost-result'}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
____________ test_agents_slow_tool_calls_fold_levels_png_snapshots _____________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6ebaddd710>

    async def test_agents_slow_tool_calls_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(_agent_display_header, "DateTime", _FixedDateTime)
        monkeypatch.setattr(
            _agent_context_common,
            "get_timezone",
            lambda: ZoneInfo("UTC"),
        )
        pin_agents_visual_now(monkeypatch, _NOW.replace(tzinfo=None))
        tools_cache_module.tools_cache.clear()
        artifacts_dir = _VISUAL_SLOW_TOOLS_DIR
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
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
            await choose_agent_metadata_view(page)
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
>           await _focus_slow_tool_section(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:322: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f6eb94d9ba0>

    async def _focus_slow_tool_section(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(20):
            if panel.active_section_identity == "slow-tool-calls":
                await wait_for_state(
                    page,
                    lambda: _slow_tool_section_ready(panel),
                    description="active slow-tool section",
                )
                await wait_for_visual_idle(
                    page,
                    timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT,
                )
                if _slow_tool_section_ready(panel):
                    if await _slow_tool_section_top_aligned(page, panel):
                        return panel
                    continue
            await page.press("ctrl+j")
            # The first navigation request may enable the panel's layout reserve
            # and finish through a call-after-refresh retry. Let that retry and its
            # anchor paint converge before deciding whether another key is needed.
            await wait_for_visual_idle(page, timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT)
>       raise AssertionError("Timed out focusing slow-tool calls section")
E       AssertionError: Timed out focusing slow-tool calls section

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:210: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb6d1592b70>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb6d41ac720>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb6d3bf28d0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb6d3bf35e0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fb6dfb72090>, backoff_after_misses = 3
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
________________ test_agents_commit_messages_panel_png_snapshot ________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9f60f55160>

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
            await reveal_agent_file_view(page)
            # The sticky header panel shrinks the body viewport, so scroll
            # until every asserted row is visible instead of a fixed count.
            targets = (
                "Deltas:",
                "agent_deltas.py",
                "file_panel.py",
                "sase-core",
                "files [1/3]",
                "primary_001.diff",
            )
            for _ in range(14):
                visible = page_svg_text(page, title="ACE commit deltas scroll check")
                if all(target in visible for target in targets):
                    break
                await page.press("ctrl+f")
                await wait_for_visual_idle(page)
    
>           assert_page_svg_contains(page, "Deltas:")

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:278: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f9f6076afd0>
text = 'Deltas:'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_____________ test_agents_waiting_unknown_zoom_modal_png_snapshot ______________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb3cebefad0>

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
                await choose_agent_metadata_view(page)
                await page.press("Z")
                await page.expect_no_modal()
                await wait_for_svg_contains(page, "ghost")
>               await _wait_for_wait_bead_statuses(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:316: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:124: in _wait_for_wait_bead_statuses
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fb3cc92c8a0>
predicate = <function _wait_for_wait_bead_statuses.<locals>.has_status_badges at 0x7fb3ce973530>
description = 'wait bead status badges', timeout = 15.0

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
E               AssertionError: Timed out after 15.00s waiting for wait bead status badges; last_frame_digest=5fc86948f88d; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-2991892322-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-2991892322-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-2991892322-r1 { fill: #c5c8c6 }\n.terminal-2991892322-r2 { fill: #fffcf0 }\n.terminal-2991892322-r3 { fill: #87d7ff;font-weight: bold }\n.terminal-2991892322-r4 { fill: #444444 }\n.terminal-2991892322-r5 { fill: #888888 }\n.terminal-2991892322-r6 { fill: #b1afa7 }\n.terminal-2991892322-r7 { fill: #ff8700;font-weight: bold }\n.terminal-2991892322-r8 { fill: #ffd700;font-weight: bold }\n.terminal-2991892322-r9 { fill: #ffffff;font-weight: bold }\n.terminal-2991892322-r10 { fill: #00d7af;font-weight: bold }\n.terminal-2991892322-r11 { fill: #af87ff;font-weight: bold }\n.terminal-2991892322-r12 { fill: #ff5f5f;font-weight: bold }\n.terminal-2991892322-r13 { fill: #5fd7ff;font-weight: bold }\n.terminal-2991892322-r14 { fill: #65c3ed;font-weight: bold }\n.terminal-2991892322-r15 { fill: #63d9b6 }\n.terminal-2991892322-r16 { fill: #877307 }\n.terminal-2991892322-r17 { fill: #757474 }\n.terminal-2991892322-r18 { fill: #ffd700 }\n.terminal-2991892322-r19 { fill: #adaba3 }\n.terminal-2991892322-r20 { fill: #87ff00;font-weight: bold }\n.terminal-2991892322-r21 { fill: #5faf00 }\n.terminal-2991892322-r22 { fill: #afff5f }\n.terminal-2991892322-r23 { fill: #af87ff }\n.terminal-2991892322-r24 { fill: #ff87d7 }\n.terminal-2991892322-r25 { fill: #5fd75f;font-weight: bold }\n.terminal-2991892322-r26 { fill: #ffaf5f;font-weight: bold }\n.terminal-2991892322-r27 { fill: #24837b }\n.terminal-2991892322-r28 { fill: #004578;font-weight: bold }\n.terminal-2991892322-r29 { fill: #100f0f;font-weight: bold }\n.terminal-2991892322-r30 { fill: #d7af5f;font-weight: bold;text-decoration: underline; }\n.terminal-2991892322-r31 { fill: #a4a3a3 }\n.terminal-2991892322-r32 { fill: #adaba3;font-style: italic; }\n.terminal-2991892322-r33 { fill: #1d5b56 }\n.terminal-2991892322-r34 { fill: #494846 }\n.terminal-2991892322-r35 { fill: #c4c5b5;font-weight: bold }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-2991892322-clip-terminal">\n      <rect x="0" y="0" width="1463.0" height="975.0" />\n    </clipPath>\n    <clipPath id="terminal-2991892322-line-0">\n    <rect x="0" y="1.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-1">\n    <rect x="0" y="25.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-2">\n    <rect x="0" y="50.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-3">\n    <rect x="0" y="74.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-4">\n    <rect x="0" y="99.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-5">\n    <rect x="0" y="123.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-6">\n    <rect x="0" y="147.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-7">\n    <rect x="0" y="172.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-8">\n    <rect x="0" y="196.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-9">\n    <rect x="0" y="221.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-10">\n    <rect x="0" y="245.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-11">\n    <rect x="0" y="269.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-12">\n    <rect x="0" y="294.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-13">\n    <rect x="0" y="318.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-14">\n    <rect x="0" y="343.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-15">\n    <rect x="0" y="367.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-16">\n    <rect x="0" y="391.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-17">\n    <rect x="0" y="416.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-18">\n    <rect x="0" y="440.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-19">\n    <rect x="0" y="465.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-20">\n    <rect x="0" y="489.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-21">\n    <rect x="0" y="513.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-22">\n    <rect x="0" y="538.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-23">\n    <rect x="0" y="562.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-24">\n    <rect x="0" y="587.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-25">\n    <rect x="0" y="611.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-26">\n    <rect x="0" y="635.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-27">\n    <rect x="0" y="660.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-28">\n    <rect x="0" y="684.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-29">\n    <rect x="0" y="709.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-30">\n    <rect x="0" y="733.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-31">\n    <rect x="0" y="757.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-32">\n    <rect x="0" y="782.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-33">\n    <rect x="0" y="806.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-34">\n    <rect x="0" y="831.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-35">\n    <rect x="0" y="855.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-36">\n    <rect x="0" y="879.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-37">\n    <rect x="0" y="904.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-38">\n    <rect x="0" y="928.7" width="1464" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="1480" height="1024" rx="8"/><text class="terminal-2991892322-title" fill="#c5c8c6" text-anchor="middle" x="740" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-2991892322-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="829.6" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="841.8" y="1.5" width="622.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1464" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="25.9" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="25.9" width="866.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1305.4" y="25.9" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1390.8" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1427.4" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="48.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="61" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="158.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="353.8" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="488" y="50.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="561.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="597.8" y="50.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="695.4" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="732" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="841.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="951.6" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="976" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1049.2" y="50.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1098" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1134.6" y="50.3" width="329.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="74.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="195.2" y="74.7" width="1268.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="99.1" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="134.2" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="170.8" y="99.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="99.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="305" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="99.1" width="1134.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="97.6" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="170.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="183" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="207.4" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="292.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="305" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="341.6" y="123.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="439.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="451.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="463.6" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="561.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="610" y="123.5" width="841.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="172.3" width="1439.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="196.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="196.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="146.4" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#004578" x="170.8" y="196.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="256.2" y="196.7" width="1207.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="221.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="245.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="245.5" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="207.4" y="245.5" width="1244.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="269.9" width="256.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="269.9" width="1134.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="294.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="318.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="318.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="343.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="367.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="391.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="416.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="440.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="465.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="489.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="489.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="513.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="513.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="538.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="538.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="562.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="562.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="587.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="587.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="611.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="611.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="635.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="635.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="660.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="660.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="684.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="684.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="709.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="709.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="733.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="733.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="757.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="757.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="782.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="782.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="806.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="806.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="831.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="831.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="855.5" width="1037" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1061.4" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1134.6" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1159" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1232.2" y="855.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1268.8" y="855.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1329.8" y="855.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1366.4" y="855.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="879.9" width="1464" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="97.6" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="904.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="904.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="427" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="904.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="671" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="904.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="939.4" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1061.4" y="904.3" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="1281" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="1342" y="904.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="928.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="158.6" y="928.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="928.7" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="928.7" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="928.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="928.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="928.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="928.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="928.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1146.8" y="928.7" width="317.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="953.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="122" y="953.1" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="953.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="953.1" width="988.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-2991892322-matrix">\n    <text class="terminal-2991892322-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-2991892322-line-0)">⭘</text><text class="terminal-2991892322-r2" x="622.2" y="20" textLength="207.4" clip-path="url(#terminal-2991892322-line-0)">sase&#160;tui&#160;(v0.7.1)</text><text class="terminal-2991892322-r1" x="1464" y="20" textLength="12.2" clip-path="url(#terminal-2991892322-line-0)">\n</text><text class="terminal-2991892322-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-2991892322-line-1)">&#160;Agents&#160;</text><text class="terminal-2991892322-r4" x="109.8" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">&#160;│&#160;</text><text class="terminal-2991892322-r5" x="146.4" y="44.4" textLength="134.2" clip-path="url(#terminal-2991892322-line-1)">&#160;Artifacts&#160;</text><text class="terminal-2991892322-r4" x="280.6" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">&#160;│&#160;</text><text class="terminal-2991892322-r5" x="317.2" y="44.4" textLength="122" clip-path="url(#terminal-2991892322-line-1)">&#160;Services&#160;</text><text class="terminal-2991892322-r6" x="1305.4" y="44.4" textLength="85.4" clip-path="url(#terminal-2991892322-line-1)">inbox:&#160;</text><text class="terminal-2991892322-r7" x="1390.8" y="44.4" textLength="24.4" clip-path="url(#terminal-2991892322-line-1)">⚑1</text><text class="terminal-2991892322-r8" x="1427.4" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">✉18</text><text class="terminal-2991892322-r1" x="1464" y="44.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-1)">\n</text><text class="terminal-2991892322-r9" x="12.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">4</text><text class="terminal-2991892322-r6" x="24.4" y="68.8" textLength="24.4" clip-path="url(#terminal-2991892322-line-2)">&#160;[</text><text class="terminal-2991892322-r10" x="48.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="61" y="68.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-2)">&#160;running</text><text class="terminal-2991892322-r6" x="158.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r11" x="195.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="207.4" y="68.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-2)">&#160;waiting</text><text class="terminal-2991892322-r6" x="305" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r12" x="341.6" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="353.8" y="68.8" textLength="85.4" clip-path="url(#terminal-2991892322-line-2)">&#160;failed</text><text class="terminal-2991892322-r6" x="439.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r13" x="475.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="488" y="68.8" textLength="61" clip-path="url(#terminal-2991892322-line-2)">&#160;done</text><text class="terminal-2991892322-r6" x="549" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">]</text><text class="terminal-2991892322-r6" x="561.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r8" x="597.8" y="68.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-2)">zoom</text><text class="terminal-2991892322-r6" x="646.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="683.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">Z</text><text class="terminal-2991892322-r6" x="695.4" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="732" y="68.8" textLength="73.2" clip-path="url(#terminal-2991892322-line-2)">nodes&#160;</text><text class="terminal-2991892322-r9" x="805.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">1/4</text><text class="terminal-2991892322-r6" x="841.8" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="878.4" y="68.8" textLength="73.2" clip-path="url(#terminal-2991892322-line-2)">Ctrl+S</text><text class="terminal-2991892322-r6" x="951.6" y="68.8" textLength="24.4" clip-path="url(#terminal-2991892322-line-2)">&#160;·</text><text class="terminal-2991892322-r14" x="1049.2" y="68.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-2)">0/10</text><text class="terminal-2991892322-r6" x="1098" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r15" x="1134.6" y="68.8" textLength="329.4" clip-path="url(#terminal-2991892322-line-2)">codex/visual-snapshot-model</text><text class="terminal-2991892322-r1" x="1464" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">\n</text><text class="terminal-2991892322-r8" x="0" y="93.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-3)">»</text><text class="terminal-2991892322-r16" x="24.4" y="93.2" textLength="36.6" clip-path="url(#terminal-2991892322-line-3)">╭─&#160;</text><text class="terminal-2991892322-r8" x="61" y="93.2" textLength="134.2" clip-path="url(#terminal-2991892322-line-3)">AGENT&#160;SHELL</text><text class="terminal-2991892322-r16" x="195.2" y="93.2" textLength="1268.8" clip-path="url(#terminal-2991892322-line-3)">&#160;──────────────────────────────────────────────────────────────────────────────────────────────────────╮</text><text class="terminal-2991892322-r1" x="1464" y="93.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-3)">\n</text><text class="terminal-2991892322-r17" x="0" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r16" x="24.4" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r18" x="61" y="117.6" textLength="73.2" clip-path="url(#terminal-2991892322-line-4)">waiter</text><text class="terminal-2991892322-r19" x="134.2" y="117.6" textLength="36.6" clip-path="url(#terminal-2991892322-line-4)">&#160;·&#160;</text><text class="terminal-2991892322-r20" x="170.8" y="117.6" textLength="61" clip-path="url(#terminal-2991892322-line-4)">CODEX</text><text class="terminal-2991892322-r21" x="231.8" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">(</text><text class="terminal-2991892322-r22" x="244" y="117.6" textLength="61" clip-path="url(#terminal-2991892322-line-4)">gpt-5</text><text class="terminal-2991892322-r21" x="305" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">)</text><text class="terminal-2991892322-r16" x="1451.8" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r1" x="1464" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">\n</text><text class="terminal-2991892322-r17" x="0" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r16" x="24.4" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r23" x="61" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">⏳&#160;</text><text class="terminal-2991892322-r24" x="97.6" y="142" textLength="61" clip-path="url(#terminal-2991892322-line-5)">coder</text><text class="terminal-2991892322-r25" x="170.8" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">✓</text><text class="terminal-2991892322-r24" x="183" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="207.4" y="142" textLength="85.4" clip-path="url(#terminal-2991892322-line-5)">builder</text><text class="terminal-2991892322-r8" x="305" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">▶</text><text class="terminal-2991892322-r24" x="317.2" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="341.6" y="142" textLength="97.6" clip-path="url(#terminal-2991892322-line-5)">reviewer</text><text class="terminal-2991892322-r12" x="451.4" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">✗</text><text class="terminal-2991892322-r24" x="463.6" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="488" y="142" textLength="61" clip-path="url(#terminal-2991892322-line-5)">ghost</text><text class="terminal-2991892322-r26" x="561.2" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">?</text><text class="terminal-2991892322-r19" x="573.4" y="142" textLength="36.6" clip-path="url(#terminal-2991892322-line-5)">&#160;+1</text><text class="terminal-2991892322-r16" x="1451.8" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r1" x="1464" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">\n</text><text class="terminal-2991892322-r17" x="0" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r16" x="24.4" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r16" x="1451.8" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r1" x="1464" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">\n</text><text class="terminal-2991892322-r17" x="0" y="190.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-7)">│</text><text class="terminal-2991892322-r16" x="24.4" y="190.8" textLength="1439.6" clip-path="url(#terminal-2991892322-line-7)">╰─────────────────────────────────────────────────────────────────────────────────────────────────────────&#160;▾&#160;d&#160;more&#160;─╯</text><text class="terminal-2991892322-r1" x="1464" y="190.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-7)">\n</text><text class="terminal-2991892322-r17" x="0" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">│</text><text class="terminal-2991892322-r27" x="24.4" y="215.2" textLength="36.6" clip-path="url(#terminal-2991892322-line-8)">┌─&#160;</text><text class="terminal-2991892322-r28" x="61" y="215.2" textLength="85.4" clip-path="url(#terminal-2991892322-line-8)">◆&#160;MAIN&#160;</text><text class="terminal-2991892322-r4" x="146.4" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">┃</text><text class="terminal-2991892322-r29" x="170.8" y="215.2" textLength="85.4" clip-path="url(#terminal-2991892322-line-8)">Context</text><text class="terminal-2991892322-r27" x="256.2" y="215.2" textLength="1207.8" clip-path="url(#terminal-2991892322-line-8)">&#160;─────────────────────────────────────────────────────────────────────────────────────────────────┐</text><text class="terminal-2991892322-r1" x="1464" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">\n</text><text class="terminal-2991892322-r8" x="0" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">┃</text><text class="terminal-2991892322-r27" x="24.4" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">│</text><text class="terminal-2991892322-r1" x="1464" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">\n</text><text class="terminal-2991892322-r8" x="0" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">┃</text><text class="terminal-2991892322-r27" x="24.4" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">│</text><text class="terminal-2991892322-r30" x="61" y="264" textLength="146.4" clip-path="url(#terminal-2991892322-line-10)">AGENT&#160;PROMPT</text><text class="terminal-2991892322-r27" x="1451.8" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">│</text><text class="terminal-2991892322-r1" x="1464" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">│</text><text class="terminal-2991892322-r32" x="61" y="288.4" textLength="256.2" clip-path="url(#terminal-2991892322-line-11)">No&#160;prompt&#160;file&#160;found.</text><text class="terminal-2991892322-r27" x="1451.8" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">│</text><text class="terminal-2991892322-r1" x="1464" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">│</text><text class="terminal-2991892322-r1" x="1464" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">│</text><text class="terminal-2991892322-r1" x="1464" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">│</text><text class="terminal-2991892322-r1" x="1464" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">│</text><text class="terminal-2991892322-r1" x="1464" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">│</text><text class="terminal-2991892322-r1" x="1464" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">│</text><text class="terminal-2991892322-r1" x="1464" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">│</text><text class="terminal-2991892322-r1" x="1464" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">│</text><text class="terminal-2991892322-r1" x="1464" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">│</text><text class="terminal-2991892322-r1" x="1464" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">│</text><text class="terminal-2991892322-r1" x="1464" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">│</text><text class="terminal-2991892322-r1" x="1464" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">│</text><text class="terminal-2991892322-r1" x="1464" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">│</text><text class="terminal-2991892322-r1" x="1464" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">│</text><text class="terminal-2991892322-r1" x="1464" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">│</text><text class="terminal-2991892322-r1" x="1464" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">│</text><text class="terminal-2991892322-r1" x="1464" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">│</text><text class="terminal-2991892322-r1" x="1464" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">│</text><text class="terminal-2991892322-r1" x="1464" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">│</text><text class="terminal-2991892322-r1" x="1464" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">│</text><text class="terminal-2991892322-r1" x="1464" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">│</text><text class="terminal-2991892322-r1" x="1464" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">│</text><text class="terminal-2991892322-r1" x="1464" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">│</text><text class="terminal-2991892322-r1" x="1464" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="874" textLength="1037" clip-path="url(#terminal-2991892322-line-35)">└───────────────────────────────────────────────────────────────────────────────────&#160;</text><text class="terminal-2991892322-r33" x="1061.4" y="874" textLength="73.2" clip-path="url(#terminal-2991892322-line-35)">spread</text><text class="terminal-2991892322-r28" x="1159" y="874" textLength="73.2" clip-path="url(#terminal-2991892322-line-35)">main&#160;1</text><text class="terminal-2991892322-r5" x="1232.2" y="874" textLength="36.6" clip-path="url(#terminal-2991892322-line-35)">&#160;·&#160;</text><text class="terminal-2991892322-r27" x="1268.8" y="874" textLength="61" clip-path="url(#terminal-2991892322-line-35)">files</text><text class="terminal-2991892322-r5" x="1329.8" y="874" textLength="36.6" clip-path="url(#terminal-2991892322-line-35)">&#160;·&#160;</text><text class="terminal-2991892322-r27" x="1366.4" y="874" textLength="97.6" clip-path="url(#terminal-2991892322-line-35)">tools&#160;─┘</text><text class="terminal-2991892322-r1" x="1464" y="874" textLength="12.2" clip-path="url(#terminal-2991892322-line-35)">\n</text><text class="terminal-2991892322-r34" x="0" y="898.4" textLength="1464" clip-path="url(#terminal-2991892322-line-36)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-2991892322-r1" x="1464" y="898.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-36)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="922.8" textLength="85.4" clip-path="url(#terminal-2991892322-line-37)">&lt;enter&gt;</text><text class="terminal-2991892322-r6" x="109.8" y="922.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-37)">go&#160;to&#160;PR</text><text class="terminal-2991892322-r10" x="256.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">A</text><text class="terminal-2991892322-r6" x="280.6" y="922.8" textLength="146.4" clip-path="url(#terminal-2991892322-line-37)">auto-approve</text><text class="terminal-2991892322-r10" x="500.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">h</text><text class="terminal-2991892322-r6" x="524.6" y="922.8" textLength="146.4" clip-path="url(#terminal-2991892322-line-37)">parent&#160;tribe</text><text class="terminal-2991892322-r10" x="744.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">H</text><text class="terminal-2991892322-r6" x="768.6" y="922.8" textLength="170.8" clip-path="url(#terminal-2991892322-line-37)">collapse&#160;group</text><text class="terminal-2991892322-r10" x="988.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">n</text><text class="terminal-2991892322-r6" x="1012.6" y="922.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-37)">name</text><text class="terminal-2991892322-r35" x="1281" y="922.8" textLength="61" clip-path="url(#terminal-2991892322-line-37)">&#160;SVC&#160;</text><text class="terminal-2991892322-r35" x="1342" y="922.8" textLength="109.8" clip-path="url(#terminal-2991892322-line-37)">&#160;STOPPED&#160;</text><text class="terminal-2991892322-r1" x="1464" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">N</text><text class="terminal-2991892322-r6" x="36.6" y="947.2" textLength="122" clip-path="url(#terminal-2991892322-line-38)">edit&#160;tribe</text><text class="terminal-2991892322-r10" x="256.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">R</text><text class="terminal-2991892322-r6" x="280.6" y="947.2" textLength="61" clip-path="url(#terminal-2991892322-line-38)">retry</text><text class="terminal-2991892322-r10" x="500.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">V</text><text class="terminal-2991892322-r6" x="524.6" y="947.2" textLength="97.6" clip-path="url(#terminal-2991892322-line-38)">metadata</text><text class="terminal-2991892322-r10" x="744.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">w</text><text class="terminal-2991892322-r6" x="768.6" y="947.2" textLength="109.8" clip-path="url(#terminal-2991892322-line-38)">edit&#160;wait</text><text class="terminal-2991892322-r10" x="988.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">W</text><text class="terminal-2991892322-r6" x="1012.6" y="947.2" textLength="134.2" clip-path="url(#terminal-2991892322-line-38)">new&#160;w/&#160;wait</text><text class="terminal-2991892322-r1" x="1464" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-39)">x</text><text class="terminal-2991892322-r6" x="36.6" y="971.6" textLength="85.4" clip-path="url(#terminal-2991892322-line-39)">dismiss</text><text class="terminal-2991892322-r10" x="256.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-39)">X</text><text class="terminal-2991892322-r6" x="280.6" y="971.6" textLength="195.2" clip-path="url(#terminal-2991892322-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb6d45a4a10>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb6d40ac3b0>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb6d1974e00>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb6d13121f0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7fb6dfb72090>, backoff_after_misses = 3
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
18.71s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
16.77s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
16.13s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
11.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
11.82s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
9.16s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
7.35s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
7.32s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40]
7.26s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots
7.14s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40]
7.01s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40]
6.87s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots
6.84s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40]
6.83s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
6.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]
6.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40]
6.18s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40]
5.40s call     tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail]
5.28s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
4.05s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_plugins_loading_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_linked_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py::test_agents_metadata_search_typing_and_committed_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_context_reply_no_files_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_reply_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_selected_gate_shell_output_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
============================= 28 failed in 50.52s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 10/10 workers
10 workers [28 items]

FFFFFFFFFFFFFFFFFFFFFFFFFFFF                                             [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_agents_linked_repo_diff_file_panel_png_snapshot _____________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fbc9b695d90>

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
            await reveal_agent_file_view(page)
            await wait_for_svg_contains(page, "linked repo")
    
            assert_page_svg_contains(page, "sase-core")
            assert_page_svg_contains(page, "linked repo")
            assert_page_svg_contains(page, "/workspace/sase-core_14")
>           file_scroll = page.app.query_one("#agent-file-scroll", VerticalScroll)
                          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:233: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-file-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-file-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
_______________ test_agents_decks_single_main_reply_png_snapshot _______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f586b235d90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw0/test_agents_decks_single_main_0')

    async def test_agents_decks_single_main_reply_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_reply_agent(tmp_path)])
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _goto_agents(page, 1)
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            await wait_for_state(
                page,
                lambda: set(detail._main_deck_document.card_ids) == {"context", "reply"},
                description="Main deck has Context and Reply cards",
            )
            await page.press("ctrl+j")
            await wait_for_visual_idle(page)
>           assert detail.deck_area.panel(0).main_view.active_card_id == "reply"
E           AssertionError: assert 'context' == 'reply'
E             
E             - reply
E             + context

tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py:109: AssertionError
_ test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail] _
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9373031d90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw9/test_agents_llm_calls_panel_de0')
detail_level = <ToolDetailLevel.FULL: 2>
snapshot_name = 'agents_llm_calls_panel_full_120x40'
title = 'ACE agents LLM Calls panel full detail'

    @pytest.mark.parametrize(
        ("detail_level", "snapshot_name", "title"),
        [
            (
                ToolDetailLevel.EXPANDED,
                "agents_llm_calls_panel_expanded_120x40",
                "ACE agents LLM Calls panel expanded detail",
            ),
            (
                ToolDetailLevel.FULL,
                "agents_llm_calls_panel_full_120x40",
                "ACE agents LLM Calls panel full detail",
            ),
        ],
    )
    async def test_agents_llm_calls_panel_detail_level_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        detail_level: ToolDetailLevel,
        snapshot_name: str,
        title: str,
    ) -> None:
        _pin_llm_calls_panel_now(monkeypatch)
        _clear_llm_calls_cache()
    
        artifacts_dir = tmp_path / "ace-run" / "20260509100000"
        _populate_expanded_tool_calls(artifacts_dir)
        agent = _llm_calls_agent(artifacts_dir)
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            panel = await _open_llm_calls_panel(page)
            assert panel.set_detail_level(detail_level) is True
            page.app._refresh_agent_footer_bindings_only()
            page.app.refresh(layout=True)
            await page.app.wait_for_refresh()
            if detail_level is ToolDetailLevel.FULL:
>               llm_calls_scroll = page.app.query_one("#agent-llm-calls-scroll")
                                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py:438: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-llm-calls-scroll', expect_type = None

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-llm-calls-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________ test_family_panel_shells_monitor_metadata_png_snapshot ____________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f7186e6dfd0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw4/test_family_panel_shells_monit0')

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
            assert_page_svg_contains(page, "3 shells")
            assert_page_svg_contains(page, "⚙")
            assert_page_svg_contains(page, "FAMILY SHELLS")
            combined = prompt_header_and_body_text(
                page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            )
            # At assertion width the monitor lane shows its command; at panel
            # width it wraps to the "why" reason continuation instead.
            assert "just check-full --include visual" in combined
            ace_png_visual.assert_page_png(
                page,
                "agents_family_panel_shells_monitor_120x40",
                title="ACE family panel shell metadata with monitor",
            )
    
            await page.press(".")
            await wait_for_visual_idle(page)
            assert_page_svg_contains(page, "FAMILY SHELLS")
            assert_page_svg_contains(page, "--plan")
            assert_page_svg_contains(page, "--mon")
            assert_page_svg_contains(page, "⚙ MONITOR")
>           assert_page_svg_contains(page, "just check")

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:308: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f7186acd160>
text = 'just check'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_____________________ test_swarm_clan_panel_png_snapshots ______________________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f96d98c9d90>

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

page = <sase.ace.testing.ace_page.AcePage object at 0x7f96d932d160>
text = '--code'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_______ test_family_panel_fold_levels_and_member_override_png_snapshots ________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc44843dd90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw2/test_family_panel_fold_levels_0')

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
>           assert panel.active_section_identity == "agent-xprompt"
E           AssertionError: assert None == 'agent-xprompt'
E            +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py:65: AssertionError
__ test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40] ___
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f83b3aa1d90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw5/test_monitor_state_detail_png_0')
slug = 'host_completed'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'all checks passed\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
____________________ test_tribe_panel_prompts_png_snapshots ____________________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f05b6341d90>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw8/test_tribe_panel_prompts_png_s0')

    async def test_tribe_panel_prompts_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_prompt_agents(tmp_path))
    
        async with AcePage(query='"visual-prompts"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _screen: "PROMPTS" in prompt_header_and_body_text(panel),
                timeout=30.0,
            )
            assert page.app._member_jump_maps[("panel", "epic")].targets
    
>           await _jump_to_prompts(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py:212: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f05b5fa9160>

    async def _jump_to_prompts(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(10):
            if panel.active_section_identity == "tribe:prompts":
                break
            await page.press("ctrl+j")
>       assert panel.active_section_identity == "tribe:prompts"
E       AssertionError: assert None == 'tribe:prompts'
E        +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py:179: AssertionError
______ test_monitor_state_detail_png_snapshots[running-overrides0-120-40] ______
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f83b2645fd0>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw6/test_monitor_state_detail_png_0')
slug = 'running'
overrides = {'monitor_state': 'running', 'status': 'TESTING', 'output': 'collecting diagnostics...\n'}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
____________ test_agents_external_repo_diff_file_panel_png_snapshot ____________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5865ecef50>

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
            await reveal_agent_file_view(page)
            await wait_for_svg_contains(page, "external repo")
    
            assert_page_svg_contains(page, "gh:pallets/click")
            assert_page_svg_contains(page, "external repo")
            assert_page_svg_contains(page, "sase/repos/external")
>           ace_png_visual.assert_page_png(
                page,
                "agents_external_repo_diff_file_panel_120x40",
                title="ACE agents external repo diff file panel",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py:104: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:134: in assert_page_png
    assert_visual_frame_converged(page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f58655087d0>

    def assert_visual_frame_converged(page: AcePage) -> None:
        """Prove that *page* still renders the frame accepted by convergence.
    
        The canonical re-export and the caller's titled PNG export are both
        synchronous, so Textual cannot advance between this check and capture.
        """
        expected = getattr(page, _VISUAL_CONVERGED_SVG_ATTR, None)
        if expected is None:
            raise AssertionError(
                "ACE PNG capture requires wait_for_visual_idle(page) before "
                "assert_page_png()"
            )
    
        actual = page.export_svg(title=_VISUAL_CONVERGENCE_TITLE)
        if actual != expected:
            expected_digest = hashlib.sha256(expected.encode()).hexdigest()[:12]
            actual_digest = hashlib.sha256(actual.encode()).hexdigest()[:12]
>           raise AssertionError(
                "ACE PNG capture frame changed after visual convergence; make "
                "wait_for_visual_idle(page) the final await before capture "
                f"(converged_digest={expected_digest}, capture_digest={actual_digest})"
            )
E           AssertionError: ACE PNG capture frame changed after visual convergence; make wait_for_visual_idle(page) the final await before capture (converged_digest=4b0b9def1666, capture_digest=de7665535179)

tests/ace/tui/visual/_ace_png_snapshot_waits.py:126: AssertionError
________ test_agents_metadata_search_typing_and_committed_png_snapshots ________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fbc9b20f150>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw7/test_agents_metadata_search_ty0')

    async def test_agents_metadata_search_typing_and_committed_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        agent = zoom_agent(tmp_path)
        agent.diff_path = None
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(
            query='"visual"',
            patches=patches(),
            initial_tab="agents",
        ) as page:
            await wait_for_startup(page)
            await page.expect_state("agent_count", 1)
            panel = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _state: "zoom.snapshot.agent" in prompt_header_and_body_text(panel),
            )
    
            # The sticky header keeps identity fields out of the search corpus,
            # so search a body term ("prompt" hits the section title and the
            # empty notice) rather than the detached agent name.
            await page.press("comma", "slash", "p", "r", "o", "m", "p", "t")
            await page.wait_for(
                lambda _state: (
                    page.app._agent_metadata_search.mode == "typing"
                    and len(page.app._agent_metadata_search.match_spans) > 1
                ),
            )
            await wait_for_visual_idle(page)
            ace_png_visual.assert_page_png(
                page,
                "agents_metadata_search_typing_120x40",
                title="ACE agents metadata search typing",
            )
    
            await page.press("enter", "n")
>           command = page.app.query_one("#agent-search-command", Static)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py:66: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#agent-search-command'
expect_type = <class 'textual.widgets._static.Static'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-search-command' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________ test_agents_decks_context_reply_no_files_png_snapshot _____________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f96d92ddd50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw3/test_agents_decks_context_repl0')

    async def test_agents_decks_context_reply_no_files_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_reply_agent(tmp_path)])
        async with AcePage(query='"visual"', patches=patches()) as page:
            await _goto_agents(page, 1)
            detail = page.app.query_one("#agent-detail-panel", AgentDetail)
            await wait_for_state(
                page,
                lambda: set(detail._main_deck_document.card_ids) == {"context", "reply"},
                description="Main deck has Context and Reply cards",
            )
            # Force known no-files/no-tools so the new panel duplicates Main.
            detail.deck_area.panel(0)._availability = {
                DeckId.MAIN: DeckAvailability(True, 2),
                DeckId.FILES: DeckAvailability(False, 0),
                DeckId.TOOLS: DeckAvailability(False, 0),
            }
            await page.press("vertical_line")
            await wait_for_visual_idle(page)
            panel0 = detail.deck_area.panel(0)
            panel1 = detail.deck_area.panel(1)
            assert panel1.deck is DeckId.MAIN
>           assert panel0.main_view.active_card_id != panel1.main_view.active_card_id
E           AssertionError: assert 'context' != 'context'
E            +  where 'context' = MainDeckView().active_card_id
E            +    where MainDeckView() = DeckPanel(id='agent-deck-panel-0', classes='deck-panel -deck-main -unfocused').main_view
E            +  and   'context' = MainDeckView().active_card_id
E            +    where MainDeckView() = DeckPanel(id='agent-deck-panel-1', classes='deck-panel -deck-main -focused').main_view

tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py:192: AssertionError
_________________ test_selected_gate_shell_output_png_snapshot _________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc4481bb150>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw2/test_selected_gate_shell_outpu0')

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
            # Document-level check: the jump footer panel now takes detail height,
            # so this title can sit below the first viewport even at scroll zero.
            prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
            assert "Run deployment preview" in prompt_header_and_body_text(prompt)
>           scroll = page.query_one_widget("#agent-prompt-scroll", VerticalScroll)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py:149: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:384: in query_one_widget
    return self._app.query_one(selector, widget_type)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-prompt-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-prompt-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
____________ test_agents_slow_tool_calls_fold_levels_png_snapshots _____________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd864bc9d90>

    async def test_agents_slow_tool_calls_fold_levels_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setattr(_agent_display_header, "DateTime", _FixedDateTime)
        monkeypatch.setattr(
            _agent_context_common,
            "get_timezone",
            lambda: ZoneInfo("UTC"),
        )
        pin_agents_visual_now(monkeypatch, _NOW.replace(tzinfo=None))
        tools_cache_module.tools_cache.clear()
        artifacts_dir = _VISUAL_SLOW_TOOLS_DIR
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
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
            await choose_agent_metadata_view(page)
            await wait_for_svg_contains(page, "SLOW TOOL CALLS")
>           await _focus_slow_tool_section(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:322: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fd8646212b0>

    async def _focus_slow_tool_section(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(20):
            if panel.active_section_identity == "slow-tool-calls":
                await wait_for_state(
                    page,
                    lambda: _slow_tool_section_ready(panel),
                    description="active slow-tool section",
                )
                await wait_for_visual_idle(
                    page,
                    timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT,
                )
                if _slow_tool_section_ready(panel):
                    if await _slow_tool_section_top_aligned(page, panel):
                        return panel
                    continue
            await page.press("ctrl+j")
            # The first navigation request may enable the panel's layout reserve
            # and finish through a call-after-refresh retry. Let that retry and its
            # anchor paint converge before deciding whether another key is needed.
            await wait_for_visual_idle(page, timeout=_SLOW_TOOLS_VISUAL_IDLE_TIMEOUT)
>       raise AssertionError("Timed out focusing slow-tool calls section")
E       AssertionError: Timed out focusing slow-tool calls section

tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py:210: AssertionError
_____ test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40] ______
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f7186be7150>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw4/test_monitor_state_detail_png_0')
slug = 'degraded'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'checks passed, workspace fallback used\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
___________________ test_agents_collapsed_panel_png_snapshot ___________________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fbc98160aa0>

    async def test_agents_collapsed_panel_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=_panel_collapse_agents())
    
        async with AcePage(query='"visual"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 4)
            await wait_for_visual_idle(page)
    
            container = page.app.query_one("#agent-list-container")
            assert "chop" not in page.app._collapsed_panel_keys
            assert "chop" not in page.app._expanded_panel_keys
            await page.press("J")
            assert page.app._panel_group.focused_key == "keep"
            await page.press("J")
            assert page.app._panel_group.focused_key is None
            await page.press("J")
            assert page.app._panel_group.focused_key == "keep"
            await page.press("h")
            await page.press("j")
            assert page.app._panel_group.focused_key == "chop"
            panel_focus = page.app._resolve_focused_panel()
            assert panel_focus is not None and panel_focus.collapsed
            await wait_for_svg_contains(page, "▸ ")
            await wait_for_visual_idle(page)
    
            assert page.app._panel_group.panel_keys[-1] == "chop"
            collapsed_widget = page.app.query_one(f"#{panel_widget_id_for_key('chop')}")
            assert collapsed_widget.option_count == 0
            assert collapsed_widget.styles.height is not None
            assert collapsed_widget.styles.height.value == 2.0
            assert (
                Text.from_markup(collapsed_widget.border_title).plain
                == "▸ † @job · 2 [R1 W1]"
            )
>           _assert_collapsed_panel_summary(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:266: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fbc9a586ad0>

    def _assert_collapsed_panel_summary(page: AcePage) -> None:
        """Assert the right pane represents ``@job``, not its hidden first row."""
        detail = page.app.query_one("#agent-detail-panel", AgentDetail)
        prompt = page.app.query_one("#agent-prompt-panel", AgentPromptPanel)
        info = page.app.query_one("#agent-info-panel", AgentInfoPanel)
    
        assert detail._current_agent is None
        assert detail._current_tribe_identity == ("panel", "chop")
        assert page.app._get_selected_agent() is None
        snapshot = page.app._focused_tribe_summary()
        assert snapshot is not None
        assert snapshot.label == "† @job"
        rendered = prompt_header_and_body_text(prompt)
        assert "TRIBE\n" in rendered
        assert "Name: † @job" in rendered
        assert "Panel:" not in rendered
        assert "Fold: 1/4" in rendered
        assert "[R1 W1]" in rendered
        assert "TRIBE MEMBERS · 2" in rendered
        assert "visual.collapse.primary.with.a.deliberately.wide.row" in rendered
>       assert info._view_mode == "tribe"
               ^^^^^^^^^^^^^^^
E       AttributeError: 'AgentInfoPanel' object has no attribute '_view_mode'

tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py:151: AttributeError
_______ test_monitor_state_detail_png_snapshots[lost-overrides4-120-40] ________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f83b361af50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw5/test_monitor_state_detail_png_1')
slug = 'lost'
overrides = {'monitor_state': 'lost', 'status': 'TESTED', 'output': 'last retained line before reboot\n', 'result_ref': 'artifact:lost-result'}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
_____________ test_family_conversation_monitor_phase_png_snapshot ______________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5869b9d040>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw0/test_family_conversation_monit0')

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
>           assert panel.active_section_identity == "agent-reply"
E           AssertionError: assert None == 'agent-reply'
E            +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:352: AssertionError
______ test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40] ______
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f83aca3ab50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw6/test_monitor_state_detail_png_1')
slug = 'timeout'
overrides = {'monitor_state': 'timeout', 'status': 'TESTED', 'exit_code': 124, 'output': 'timed out waiting for quiet shard\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
__ test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40] __
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f96d9498f50>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw3/test_monitor_state_detail_png_0')
slug = 'needs_attention'
overrides = {'monitor_state': 'completed', 'status': 'TESTED', 'exit_code': 0, 'output': 'checks passed, continuation could not launch\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
________________ test_tribe_panel_clan_summaries_png_snapshots _________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd8616d8750>

    async def test_tribe_panel_clan_summaries_png_snapshots(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        pin_agents_visual_now(monkeypatch, datetime(2026, 7, 18, 15, 0, 0))
        patch_startup_loaders(monkeypatch, agents=_tribe_clan_summary_agents())
    
        async with AcePage(query='"visual-"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 2)
            await wait_for_visual_idle(page)
    
            await page.press("J")
            assert page.app._panel_group.focused_key == "epic"
            await page.press("h")
            await page.wait_for(
                lambda _screen: page.app._resolve_focused_panel() is not None
            )
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await page.wait_for(
                lambda _screen: "CLAN SUMMARIES" in prompt_header_and_body_text(panel),
                timeout=30.0,
            )
    
>           await _jump_to_clan_summaries(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py:120: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fd876bbd810>

    async def _jump_to_clan_summaries(page: AcePage) -> AgentPromptPanel:
        panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
        for _ in range(10):
            if panel.active_section_identity == "tribe:clan-summaries":
                break
            await page.press("ctrl+j")
>       assert panel.active_section_identity == "tribe:clan-summaries"
E       AssertionError: assert None == 'tribe:clan-summaries'
E        +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py:89: AssertionError
_ test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40] _
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f7185739400>
tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-30/popen-gw4/test_monitor_state_detail_png_1')
slug = 'failed_diagnostics'
overrides = {'monitor_state': 'failed', 'status': 'TESTED', 'exit_code': 1, 'output': 'FAILED tests/monitor/test_delivery.py::test_case\n', ...}
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
>               assert panel.active_section_identity == "monitor"
E               AssertionError: assert None == 'monitor'
E                +  where None = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source').active_section_identity

tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py:231: AssertionError
__________________ test_tribe_panel_four_level_png_snapshots ___________________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f83b04cb4d0>

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
>           await _settle_tribe_visual(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:405: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py:50: in _settle_tribe_visual
    scroll = page.app.query_one("#agent-prompt-scroll", VerticalScroll)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.7.1)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})
selector = '#agent-prompt-scroll'
expect_type = <class 'textual.containers.VerticalScroll'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#agent-prompt-scroll' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
________________ test_agents_commit_messages_panel_png_snapshot ________________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc446d64500>

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
            await reveal_agent_file_view(page)
            # The sticky header panel shrinks the body viewport, so scroll
            # until every asserted row is visible instead of a fixed count.
            targets = (
                "Deltas:",
                "agent_deltas.py",
                "file_panel.py",
                "sase-core",
                "files [1/3]",
                "primary_001.diff",
            )
            for _ in range(14):
                visible = page_svg_text(page, title="ACE commit deltas scroll check")
                if all(target in visible for target in targets):
                    break
                await page.press("ctrl+f")
                await wait_for_visual_idle(page)
    
>           assert_page_svg_contains(page, "Deltas:")

tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py:278: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fc4472c0550>
text = 'Deltas:'

    def assert_page_svg_contains(page: AcePage, text: str) -> None:
        svg = page.export_svg(title="ACE visual assertion")
        svg_plain = _page_svg_text(svg)
>       assert text in svg_plain
               ^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py:67: AssertionError
_______________ test_top_bar_usage_attention_narrow_png_snapshot _______________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9372a49550>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f93718b8460>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f93718b8bf0>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f9371a86090>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f9381b02090>, backoff_after_misses = 3
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
_____________ test_agents_waiting_unknown_zoom_modal_png_snapshot ______________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f05b60bf150>

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
                await choose_agent_metadata_view(page)
                await page.press("Z")
                await page.expect_no_modal()
                await wait_for_svg_contains(page, "ghost")
>               await _wait_for_wait_bead_statuses(page)

tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:316: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py:124: in _wait_for_wait_bead_statuses
    await wait_for_state(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7f05b0731e50>
predicate = <function _wait_for_wait_bead_statuses.<locals>.has_status_badges at 0x7f05b5cf4720>
description = 'wait bead status badges', timeout = 15.0

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
E               AssertionError: Timed out after 15.00s waiting for wait bead status badges; last_frame_digest=5fc86948f88d; last_frame_svg='<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Rich https://www.textualize.io -->\n    <style>\n\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Regular"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Regular.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Regular.woff") format("woff");\n        font-style: normal;\n        font-weight: 400;\n    }\n    @font-face {\n        font-family: "Fira Code";\n        src: local("FiraCode-Bold"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff2/FiraCode-Bold.woff2") format("woff2"),\n                url("https://cdnjs.cloudflare.com/ajax/libs/firacode/6.2.0/woff/FiraCode-Bold.woff") format("woff");\n        font-style: bold;\n        font-weight: 700;\n    }\n\n    .terminal-2991892322-matrix {\n        font-family: Fira Code, monospace;\n        font-size: 20px;\n        line-height: 24.4px;\n        font-variant-east-asian: full-width;\n    }\n\n    .terminal-2991892322-title {\n        font-size: 18px;\n        font-weight: bold;\n        font-family: arial;\n    }\n\n    .terminal-2991892322-r1 { fill: #c5c8c6 }\n.terminal-2991892322-r2 { fill: #fffcf0 }\n.terminal-2991892322-r3 { fill: #87d7ff;font-weight: bold }\n.terminal-2991892322-r4 { fill: #444444 }\n.terminal-2991892322-r5 { fill: #888888 }\n.terminal-2991892322-r6 { fill: #b1afa7 }\n.terminal-2991892322-r7 { fill: #ff8700;font-weight: bold }\n.terminal-2991892322-r8 { fill: #ffd700;font-weight: bold }\n.terminal-2991892322-r9 { fill: #ffffff;font-weight: bold }\n.terminal-2991892322-r10 { fill: #00d7af;font-weight: bold }\n.terminal-2991892322-r11 { fill: #af87ff;font-weight: bold }\n.terminal-2991892322-r12 { fill: #ff5f5f;font-weight: bold }\n.terminal-2991892322-r13 { fill: #5fd7ff;font-weight: bold }\n.terminal-2991892322-r14 { fill: #65c3ed;font-weight: bold }\n.terminal-2991892322-r15 { fill: #63d9b6 }\n.terminal-2991892322-r16 { fill: #877307 }\n.terminal-2991892322-r17 { fill: #757474 }\n.terminal-2991892322-r18 { fill: #ffd700 }\n.terminal-2991892322-r19 { fill: #adaba3 }\n.terminal-2991892322-r20 { fill: #87ff00;font-weight: bold }\n.terminal-2991892322-r21 { fill: #5faf00 }\n.terminal-2991892322-r22 { fill: #afff5f }\n.terminal-2991892322-r23 { fill: #af87ff }\n.terminal-2991892322-r24 { fill: #ff87d7 }\n.terminal-2991892322-r25 { fill: #5fd75f;font-weight: bold }\n.terminal-2991892322-r26 { fill: #ffaf5f;font-weight: bold }\n.terminal-2991892322-r27 { fill: #24837b }\n.terminal-2991892322-r28 { fill: #004578;font-weight: bold }\n.terminal-2991892322-r29 { fill: #100f0f;font-weight: bold }\n.terminal-2991892322-r30 { fill: #d7af5f;font-weight: bold;text-decoration: underline; }\n.terminal-2991892322-r31 { fill: #a4a3a3 }\n.terminal-2991892322-r32 { fill: #adaba3;font-style: italic; }\n.terminal-2991892322-r33 { fill: #1d5b56 }\n.terminal-2991892322-r34 { fill: #494846 }\n.terminal-2991892322-r35 { fill: #c4c5b5;font-weight: bold }\n    </style>\n\n    <defs>\n    <clipPath id="terminal-2991892322-clip-terminal">\n      <rect x="0" y="0" width="1463.0" height="975.0" />\n    </clipPath>\n    <clipPath id="terminal-2991892322-line-0">\n    <rect x="0" y="1.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-1">\n    <rect x="0" y="25.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-2">\n    <rect x="0" y="50.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-3">\n    <rect x="0" y="74.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-4">\n    <rect x="0" y="99.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-5">\n    <rect x="0" y="123.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-6">\n    <rect x="0" y="147.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-7">\n    <rect x="0" y="172.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-8">\n    <rect x="0" y="196.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-9">\n    <rect x="0" y="221.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-10">\n    <rect x="0" y="245.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-11">\n    <rect x="0" y="269.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-12">\n    <rect x="0" y="294.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-13">\n    <rect x="0" y="318.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-14">\n    <rect x="0" y="343.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-15">\n    <rect x="0" y="367.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-16">\n    <rect x="0" y="391.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-17">\n    <rect x="0" y="416.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-18">\n    <rect x="0" y="440.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-19">\n    <rect x="0" y="465.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-20">\n    <rect x="0" y="489.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-21">\n    <rect x="0" y="513.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-22">\n    <rect x="0" y="538.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-23">\n    <rect x="0" y="562.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-24">\n    <rect x="0" y="587.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-25">\n    <rect x="0" y="611.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-26">\n    <rect x="0" y="635.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-27">\n    <rect x="0" y="660.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-28">\n    <rect x="0" y="684.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-29">\n    <rect x="0" y="709.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-30">\n    <rect x="0" y="733.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-31">\n    <rect x="0" y="757.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-32">\n    <rect x="0" y="782.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-33">\n    <rect x="0" y="806.7" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-34">\n    <rect x="0" y="831.1" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-35">\n    <rect x="0" y="855.5" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-36">\n    <rect x="0" y="879.9" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-37">\n    <rect x="0" y="904.3" width="1464" height="24.65"/>\n            </clipPath>\n<clipPath id="terminal-2991892322-line-38">\n    <rect x="0" y="928.7" width="1464" height="24.65"/>\n            </clipPath>\n    </defs>\n\n    <rect fill="#292929" stroke="rgba(255,255,255,0.35)" stroke-width="1" x="1" y="1" width="1480" height="1024" rx="8"/><text class="terminal-2991892322-title" fill="#c5c8c6" text-anchor="middle" x="740" y="27">ACE&#160;visual&#160;state&#160;timeout</text>\n            <g transform="translate(26,22)">\n            <circle cx="0" cy="0" r="7" fill="#ff5f57"/>\n            <circle cx="22" cy="0" r="7" fill="#febc2e"/>\n            <circle cx="44" cy="0" r="7" fill="#28c840"/>\n            </g>\n        \n    <g transform="translate(9, 41)" clip-path="url(#terminal-2991892322-clip-terminal)">\n    <rect fill="#282726" x="0" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="12.2" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="24.4" y="1.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="85.4" y="1.5" width="536.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="622.2" y="1.5" width="207.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="829.6" y="1.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="841.8" y="1.5" width="622.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#282726" x="1464" y="1.5" width="0" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="25.9" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="146.4" y="25.9" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="317.2" y="25.9" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="25.9" width="866.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1305.4" y="25.9" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1390.8" y="25.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1415.2" y="25.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1427.4" y="25.9" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="48.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="61" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="158.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="195.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="50.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="305" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="353.8" y="50.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="439.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="488" y="50.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="549" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="561.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="597.8" y="50.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="646.6" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="683.2" y="50.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="695.4" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="732" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="805.2" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="841.8" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="951.6" y="50.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="976" y="50.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1049.2" y="50.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1098" y="50.3" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1134.6" y="50.3" width="329.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="74.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="74.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="74.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="195.2" y="74.7" width="1268.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="99.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="99.1" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="134.2" y="99.1" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="170.8" y="99.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="231.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="244" y="99.1" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="305" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="99.1" width="1134.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="99.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="97.6" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="170.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="183" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="207.4" y="123.5" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="292.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="305" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="341.6" y="123.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="439.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="451.4" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="463.6" y="123.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="488" y="123.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="549" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="561.2" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="573.4" y="123.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="610" y="123.5" width="841.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="123.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="147.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="147.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="172.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="172.3" width="1439.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="196.7" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="196.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="146.4" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="158.6" y="196.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#004578" x="170.8" y="196.7" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="256.2" y="196.7" width="1207.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="221.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="221.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="245.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="245.5" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="207.4" y="245.5" width="1244.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="245.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="269.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="61" y="269.9" width="256.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="317.2" y="269.9" width="1134.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="269.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="294.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="294.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="294.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="318.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="318.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="318.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="343.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="343.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="343.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="367.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="367.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="367.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="391.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="391.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="391.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="416.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="416.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="416.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="440.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="440.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="440.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="465.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="465.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="465.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="489.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="489.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="489.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="513.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="513.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="513.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="538.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="538.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="538.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="562.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="562.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="562.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="587.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="587.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="587.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="611.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="611.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="611.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="635.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="635.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="635.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="660.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="660.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="660.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="684.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="684.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="684.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="709.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="709.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="709.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="733.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="733.5" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="733.5" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="757.9" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="757.9" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="757.9" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="782.3" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="782.3" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="782.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="806.7" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="806.7" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="806.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="831.1" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="36.6" y="831.1" width="1415.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1451.8" y="831.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="24.4" y="855.5" width="1037" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1061.4" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1134.6" y="855.5" width="24.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1159" y="855.5" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1232.2" y="855.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1268.8" y="855.5" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1329.8" y="855.5" width="36.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#100f0f" x="1366.4" y="855.5" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="879.9" width="1464" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="904.3" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="97.6" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="109.8" y="904.3" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="207.4" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="904.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="427" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="904.3" width="146.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="671" y="904.3" width="73.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="904.3" width="170.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="939.4" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="904.3" width="48.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1061.4" y="904.3" width="219.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#44475a" x="1281" y="904.3" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#f4005f" x="1342" y="904.3" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1451.8" y="904.3" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="928.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="158.6" y="928.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="928.7" width="61" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="341.6" y="928.7" width="158.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="500.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="512.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="524.6" y="928.7" width="97.6" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="622.2" y="928.7" width="122" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="744.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="756.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="768.6" y="928.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="878.4" y="928.7" width="109.8" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="988.2" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1000.4" y="928.7" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1012.6" y="928.7" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="1146.8" y="928.7" width="317.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="0" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="12.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="24.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="36.6" y="953.1" width="85.4" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="122" y="953.1" width="134.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="256.2" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="268.4" y="953.1" width="12.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="280.6" y="953.1" width="195.2" height="24.65" shape-rendering="crispEdges"/><rect fill="#1c1b1a" x="475.8" y="953.1" width="988.2" height="24.65" shape-rendering="crispEdges"/>\n    <g class="terminal-2991892322-matrix">\n    <text class="terminal-2991892322-r2" x="12.2" y="20" textLength="12.2" clip-path="url(#terminal-2991892322-line-0)">⭘</text><text class="terminal-2991892322-r2" x="622.2" y="20" textLength="207.4" clip-path="url(#terminal-2991892322-line-0)">sase&#160;tui&#160;(v0.7.1)</text><text class="terminal-2991892322-r1" x="1464" y="20" textLength="12.2" clip-path="url(#terminal-2991892322-line-0)">\n</text><text class="terminal-2991892322-r3" x="12.2" y="44.4" textLength="97.6" clip-path="url(#terminal-2991892322-line-1)">&#160;Agents&#160;</text><text class="terminal-2991892322-r4" x="109.8" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">&#160;│&#160;</text><text class="terminal-2991892322-r5" x="146.4" y="44.4" textLength="134.2" clip-path="url(#terminal-2991892322-line-1)">&#160;Artifacts&#160;</text><text class="terminal-2991892322-r4" x="280.6" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">&#160;│&#160;</text><text class="terminal-2991892322-r5" x="317.2" y="44.4" textLength="122" clip-path="url(#terminal-2991892322-line-1)">&#160;Services&#160;</text><text class="terminal-2991892322-r6" x="1305.4" y="44.4" textLength="85.4" clip-path="url(#terminal-2991892322-line-1)">inbox:&#160;</text><text class="terminal-2991892322-r7" x="1390.8" y="44.4" textLength="24.4" clip-path="url(#terminal-2991892322-line-1)">⚑1</text><text class="terminal-2991892322-r8" x="1427.4" y="44.4" textLength="36.6" clip-path="url(#terminal-2991892322-line-1)">✉18</text><text class="terminal-2991892322-r1" x="1464" y="44.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-1)">\n</text><text class="terminal-2991892322-r9" x="12.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">4</text><text class="terminal-2991892322-r6" x="24.4" y="68.8" textLength="24.4" clip-path="url(#terminal-2991892322-line-2)">&#160;[</text><text class="terminal-2991892322-r10" x="48.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="61" y="68.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-2)">&#160;running</text><text class="terminal-2991892322-r6" x="158.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r11" x="195.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="207.4" y="68.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-2)">&#160;waiting</text><text class="terminal-2991892322-r6" x="305" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r12" x="341.6" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="353.8" y="68.8" textLength="85.4" clip-path="url(#terminal-2991892322-line-2)">&#160;failed</text><text class="terminal-2991892322-r6" x="439.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r13" x="475.8" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">1</text><text class="terminal-2991892322-r6" x="488" y="68.8" textLength="61" clip-path="url(#terminal-2991892322-line-2)">&#160;done</text><text class="terminal-2991892322-r6" x="549" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">]</text><text class="terminal-2991892322-r6" x="561.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r8" x="597.8" y="68.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-2)">zoom</text><text class="terminal-2991892322-r6" x="646.6" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="683.2" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">Z</text><text class="terminal-2991892322-r6" x="695.4" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="732" y="68.8" textLength="73.2" clip-path="url(#terminal-2991892322-line-2)">nodes&#160;</text><text class="terminal-2991892322-r9" x="805.2" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">1/4</text><text class="terminal-2991892322-r6" x="841.8" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r6" x="878.4" y="68.8" textLength="73.2" clip-path="url(#terminal-2991892322-line-2)">Ctrl+S</text><text class="terminal-2991892322-r6" x="951.6" y="68.8" textLength="24.4" clip-path="url(#terminal-2991892322-line-2)">&#160;·</text><text class="terminal-2991892322-r14" x="1049.2" y="68.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-2)">0/10</text><text class="terminal-2991892322-r6" x="1098" y="68.8" textLength="36.6" clip-path="url(#terminal-2991892322-line-2)">&#160;·&#160;</text><text class="terminal-2991892322-r15" x="1134.6" y="68.8" textLength="329.4" clip-path="url(#terminal-2991892322-line-2)">codex/visual-snapshot-model</text><text class="terminal-2991892322-r1" x="1464" y="68.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-2)">\n</text><text class="terminal-2991892322-r8" x="0" y="93.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-3)">»</text><text class="terminal-2991892322-r16" x="24.4" y="93.2" textLength="36.6" clip-path="url(#terminal-2991892322-line-3)">╭─&#160;</text><text class="terminal-2991892322-r8" x="61" y="93.2" textLength="134.2" clip-path="url(#terminal-2991892322-line-3)">AGENT&#160;SHELL</text><text class="terminal-2991892322-r16" x="195.2" y="93.2" textLength="1268.8" clip-path="url(#terminal-2991892322-line-3)">&#160;──────────────────────────────────────────────────────────────────────────────────────────────────────╮</text><text class="terminal-2991892322-r1" x="1464" y="93.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-3)">\n</text><text class="terminal-2991892322-r17" x="0" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r16" x="24.4" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r18" x="61" y="117.6" textLength="73.2" clip-path="url(#terminal-2991892322-line-4)">waiter</text><text class="terminal-2991892322-r19" x="134.2" y="117.6" textLength="36.6" clip-path="url(#terminal-2991892322-line-4)">&#160;·&#160;</text><text class="terminal-2991892322-r20" x="170.8" y="117.6" textLength="61" clip-path="url(#terminal-2991892322-line-4)">CODEX</text><text class="terminal-2991892322-r21" x="231.8" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">(</text><text class="terminal-2991892322-r22" x="244" y="117.6" textLength="61" clip-path="url(#terminal-2991892322-line-4)">gpt-5</text><text class="terminal-2991892322-r21" x="305" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">)</text><text class="terminal-2991892322-r16" x="1451.8" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">│</text><text class="terminal-2991892322-r1" x="1464" y="117.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-4)">\n</text><text class="terminal-2991892322-r17" x="0" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r16" x="24.4" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r23" x="61" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">⏳&#160;</text><text class="terminal-2991892322-r24" x="97.6" y="142" textLength="61" clip-path="url(#terminal-2991892322-line-5)">coder</text><text class="terminal-2991892322-r25" x="170.8" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">✓</text><text class="terminal-2991892322-r24" x="183" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="207.4" y="142" textLength="85.4" clip-path="url(#terminal-2991892322-line-5)">builder</text><text class="terminal-2991892322-r8" x="305" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">▶</text><text class="terminal-2991892322-r24" x="317.2" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="341.6" y="142" textLength="97.6" clip-path="url(#terminal-2991892322-line-5)">reviewer</text><text class="terminal-2991892322-r12" x="451.4" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">✗</text><text class="terminal-2991892322-r24" x="463.6" y="142" textLength="24.4" clip-path="url(#terminal-2991892322-line-5)">,&#160;</text><text class="terminal-2991892322-r24" x="488" y="142" textLength="61" clip-path="url(#terminal-2991892322-line-5)">ghost</text><text class="terminal-2991892322-r26" x="561.2" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">?</text><text class="terminal-2991892322-r19" x="573.4" y="142" textLength="36.6" clip-path="url(#terminal-2991892322-line-5)">&#160;+1</text><text class="terminal-2991892322-r16" x="1451.8" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">│</text><text class="terminal-2991892322-r1" x="1464" y="142" textLength="12.2" clip-path="url(#terminal-2991892322-line-5)">\n</text><text class="terminal-2991892322-r17" x="0" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r16" x="24.4" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r16" x="1451.8" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">│</text><text class="terminal-2991892322-r1" x="1464" y="166.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-6)">\n</text><text class="terminal-2991892322-r17" x="0" y="190.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-7)">│</text><text class="terminal-2991892322-r16" x="24.4" y="190.8" textLength="1439.6" clip-path="url(#terminal-2991892322-line-7)">╰─────────────────────────────────────────────────────────────────────────────────────────────────────────&#160;▾&#160;d&#160;more&#160;─╯</text><text class="terminal-2991892322-r1" x="1464" y="190.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-7)">\n</text><text class="terminal-2991892322-r17" x="0" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">│</text><text class="terminal-2991892322-r27" x="24.4" y="215.2" textLength="36.6" clip-path="url(#terminal-2991892322-line-8)">┌─&#160;</text><text class="terminal-2991892322-r28" x="61" y="215.2" textLength="85.4" clip-path="url(#terminal-2991892322-line-8)">◆&#160;MAIN&#160;</text><text class="terminal-2991892322-r4" x="146.4" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">┃</text><text class="terminal-2991892322-r29" x="170.8" y="215.2" textLength="85.4" clip-path="url(#terminal-2991892322-line-8)">Context</text><text class="terminal-2991892322-r27" x="256.2" y="215.2" textLength="1207.8" clip-path="url(#terminal-2991892322-line-8)">&#160;─────────────────────────────────────────────────────────────────────────────────────────────────┐</text><text class="terminal-2991892322-r1" x="1464" y="215.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-8)">\n</text><text class="terminal-2991892322-r8" x="0" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">┃</text><text class="terminal-2991892322-r27" x="24.4" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">│</text><text class="terminal-2991892322-r1" x="1464" y="239.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-9)">\n</text><text class="terminal-2991892322-r8" x="0" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">┃</text><text class="terminal-2991892322-r27" x="24.4" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">│</text><text class="terminal-2991892322-r30" x="61" y="264" textLength="146.4" clip-path="url(#terminal-2991892322-line-10)">AGENT&#160;PROMPT</text><text class="terminal-2991892322-r27" x="1451.8" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">│</text><text class="terminal-2991892322-r1" x="1464" y="264" textLength="12.2" clip-path="url(#terminal-2991892322-line-10)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">│</text><text class="terminal-2991892322-r32" x="61" y="288.4" textLength="256.2" clip-path="url(#terminal-2991892322-line-11)">No&#160;prompt&#160;file&#160;found.</text><text class="terminal-2991892322-r27" x="1451.8" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">│</text><text class="terminal-2991892322-r1" x="1464" y="288.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-11)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">│</text><text class="terminal-2991892322-r1" x="1464" y="312.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-12)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">│</text><text class="terminal-2991892322-r1" x="1464" y="337.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-13)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">│</text><text class="terminal-2991892322-r1" x="1464" y="361.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-14)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">│</text><text class="terminal-2991892322-r1" x="1464" y="386" textLength="12.2" clip-path="url(#terminal-2991892322-line-15)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">│</text><text class="terminal-2991892322-r1" x="1464" y="410.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-16)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">│</text><text class="terminal-2991892322-r1" x="1464" y="434.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-17)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">│</text><text class="terminal-2991892322-r1" x="1464" y="459.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-18)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">│</text><text class="terminal-2991892322-r1" x="1464" y="483.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-19)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">│</text><text class="terminal-2991892322-r1" x="1464" y="508" textLength="12.2" clip-path="url(#terminal-2991892322-line-20)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">│</text><text class="terminal-2991892322-r1" x="1464" y="532.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-21)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">│</text><text class="terminal-2991892322-r1" x="1464" y="556.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-22)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">│</text><text class="terminal-2991892322-r1" x="1464" y="581.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-23)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">│</text><text class="terminal-2991892322-r1" x="1464" y="605.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-24)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">│</text><text class="terminal-2991892322-r1" x="1464" y="630" textLength="12.2" clip-path="url(#terminal-2991892322-line-25)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">│</text><text class="terminal-2991892322-r1" x="1464" y="654.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-26)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">│</text><text class="terminal-2991892322-r1" x="1464" y="678.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-27)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">│</text><text class="terminal-2991892322-r1" x="1464" y="703.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-28)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">│</text><text class="terminal-2991892322-r1" x="1464" y="727.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-29)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">│</text><text class="terminal-2991892322-r1" x="1464" y="752" textLength="12.2" clip-path="url(#terminal-2991892322-line-30)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">│</text><text class="terminal-2991892322-r1" x="1464" y="776.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-31)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">│</text><text class="terminal-2991892322-r1" x="1464" y="800.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-32)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">│</text><text class="terminal-2991892322-r1" x="1464" y="825.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-33)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">│</text><text class="terminal-2991892322-r27" x="1451.8" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">│</text><text class="terminal-2991892322-r1" x="1464" y="849.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-34)">\n</text><text class="terminal-2991892322-r27" x="24.4" y="874" textLength="1037" clip-path="url(#terminal-2991892322-line-35)">└───────────────────────────────────────────────────────────────────────────────────&#160;</text><text class="terminal-2991892322-r33" x="1061.4" y="874" textLength="73.2" clip-path="url(#terminal-2991892322-line-35)">spread</text><text class="terminal-2991892322-r28" x="1159" y="874" textLength="73.2" clip-path="url(#terminal-2991892322-line-35)">main&#160;1</text><text class="terminal-2991892322-r5" x="1232.2" y="874" textLength="36.6" clip-path="url(#terminal-2991892322-line-35)">&#160;·&#160;</text><text class="terminal-2991892322-r27" x="1268.8" y="874" textLength="61" clip-path="url(#terminal-2991892322-line-35)">files</text><text class="terminal-2991892322-r5" x="1329.8" y="874" textLength="36.6" clip-path="url(#terminal-2991892322-line-35)">&#160;·&#160;</text><text class="terminal-2991892322-r27" x="1366.4" y="874" textLength="97.6" clip-path="url(#terminal-2991892322-line-35)">tools&#160;─┘</text><text class="terminal-2991892322-r1" x="1464" y="874" textLength="12.2" clip-path="url(#terminal-2991892322-line-35)">\n</text><text class="terminal-2991892322-r34" x="0" y="898.4" textLength="1464" clip-path="url(#terminal-2991892322-line-36)">▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔</text><text class="terminal-2991892322-r1" x="1464" y="898.4" textLength="12.2" clip-path="url(#terminal-2991892322-line-36)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="922.8" textLength="85.4" clip-path="url(#terminal-2991892322-line-37)">&lt;enter&gt;</text><text class="terminal-2991892322-r6" x="109.8" y="922.8" textLength="97.6" clip-path="url(#terminal-2991892322-line-37)">go&#160;to&#160;PR</text><text class="terminal-2991892322-r10" x="256.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">A</text><text class="terminal-2991892322-r6" x="280.6" y="922.8" textLength="146.4" clip-path="url(#terminal-2991892322-line-37)">auto-approve</text><text class="terminal-2991892322-r10" x="500.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">h</text><text class="terminal-2991892322-r6" x="524.6" y="922.8" textLength="146.4" clip-path="url(#terminal-2991892322-line-37)">parent&#160;tribe</text><text class="terminal-2991892322-r10" x="744.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">H</text><text class="terminal-2991892322-r6" x="768.6" y="922.8" textLength="170.8" clip-path="url(#terminal-2991892322-line-37)">collapse&#160;group</text><text class="terminal-2991892322-r10" x="988.2" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">n</text><text class="terminal-2991892322-r6" x="1012.6" y="922.8" textLength="48.8" clip-path="url(#terminal-2991892322-line-37)">name</text><text class="terminal-2991892322-r35" x="1281" y="922.8" textLength="61" clip-path="url(#terminal-2991892322-line-37)">&#160;SVC&#160;</text><text class="terminal-2991892322-r35" x="1342" y="922.8" textLength="109.8" clip-path="url(#terminal-2991892322-line-37)">&#160;STOPPED&#160;</text><text class="terminal-2991892322-r1" x="1464" y="922.8" textLength="12.2" clip-path="url(#terminal-2991892322-line-37)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">N</text><text class="terminal-2991892322-r6" x="36.6" y="947.2" textLength="122" clip-path="url(#terminal-2991892322-line-38)">edit&#160;tribe</text><text class="terminal-2991892322-r10" x="256.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">R</text><text class="terminal-2991892322-r6" x="280.6" y="947.2" textLength="61" clip-path="url(#terminal-2991892322-line-38)">retry</text><text class="terminal-2991892322-r10" x="500.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">V</text><text class="terminal-2991892322-r6" x="524.6" y="947.2" textLength="97.6" clip-path="url(#terminal-2991892322-line-38)">metadata</text><text class="terminal-2991892322-r10" x="744.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">w</text><text class="terminal-2991892322-r6" x="768.6" y="947.2" textLength="109.8" clip-path="url(#terminal-2991892322-line-38)">edit&#160;wait</text><text class="terminal-2991892322-r10" x="988.2" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">W</text><text class="terminal-2991892322-r6" x="1012.6" y="947.2" textLength="134.2" clip-path="url(#terminal-2991892322-line-38)">new&#160;w/&#160;wait</text><text class="terminal-2991892322-r1" x="1464" y="947.2" textLength="12.2" clip-path="url(#terminal-2991892322-line-38)">\n</text><text class="terminal-2991892322-r10" x="12.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-39)">x</text><text class="terminal-2991892322-r6" x="36.6" y="971.6" textLength="85.4" clip-path="url(#terminal-2991892322-line-39)">dismiss</text><text class="terminal-2991892322-r10" x="256.2" y="971.6" textLength="12.2" clip-path="url(#terminal-2991892322-line-39)">X</text><text class="terminal-2991892322-r6" x="280.6" y="971.6" textLength="195.2" clip-path="url(#terminal-2991892322-line-39)">cleanup&#160;(2&#160;done)</text>\n    </g>\n    </g>\n</svg>\n'

tests/ace/tui/visual/_ace_png_snapshot_waits.py:42: AssertionError
_______________ test_config_center_plugins_loading_png_snapshot ________________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f05b075e7b0>

    async def test_config_center_plugins_loading_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Suppressing the worker keeps the pane in its initial loading state."""
        patch_startup_loaders(monkeypatch)
        _patch_xprompt_sources(monkeypatch)
        _patch_config_view(monkeypatch, _build_view(_config_schema(), _config_layers()))
        _patch_plugins_catalog(monkeypatch)
        monkeypatch.setattr(
            PluginsBrowserPane, "_start_load", lambda self, *, force=False: None
        )
    
>       async with AcePage(query='"visual"', patches=patches()) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py:560: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:308: in __aexit__
    await stack.__aexit__(exc_type, exc_val, exc_tb)
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:768: in __aexit__
    raise exc
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:751: in __aexit__
    cb_suppress = await cb(*exc_details)
                  ^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:595: in _pre_process
    await self._dispatch_message(events.Mount())
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PluginsBrowserPane(id='updates')

    def on_mount(self) -> None:
        from sase.ace.tui.util.debounce import DetailPanelDebouncer
    
        from .plugins_browser_loading import is_session_memo_usable
    
        self._detail_debouncer = DetailPanelDebouncer(self.app)
        self._sync_state_visibility()
        self._sync_header()
        if self._auto_load:
            memo = self._session_state.inventory
            automatic_status = getattr(self.app, "_automatic_update_status", None)
            if is_session_memo_usable(memo, automatic_status):
                self._apply_load_result(memo, restored=True)
            else:
>               self._start_load(force=False, cache_only=True)
E               TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() got an unexpected keyword argument 'cache_only'

src/sase/ace/tui/modals/plugins_browser_layout.py:139: TypeError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/ │
│ tui/modals/plugins_browser_layout.py:139 in on_mount                         │
│                                                                              │
│   136 │   │   │   if is_session_memo_usable(memo, automatic_status):         │
│   137 │   │   │   │   self._apply_load_result(memo, restored=True)           │
│   138 │   │   │   else:                                                      │
│ ❱ 139 │   │   │   │   self._start_load(force=False, cache_only=True)         │
│   140 │                                                                      │
│   141 │   def on_unmount(self) -> None:                                      │
│   142 │   │   if self._detail_debouncer is not None:                         │
│                                                                              │
│ ╭────────────────────── locals ───────────────────────╮                      │
│ │ automatic_status = None                             │                      │
│ │             memo = None                             │                      │
│ │             self = PluginsBrowserPane(id='updates') │                      │
│ ╰─────────────────────────────────────────────────────╯                      │
╰──────────────────────────────────────────────────────────────────────────────╯
TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() 
got an unexpected keyword argument 'cache_only'
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:375 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 595, in _pre_process
    await self._dispatch_message(events.Mount())
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/modals/plugins_browser_layout.py", line 139, in on_mount
    self._start_load(force=False, cache_only=True)
    ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
TypeError: test_config_center_plugins_loading_png_snapshot.<locals>.<lambda>() got an unexpected keyword argument 'cache_only'
____________ test_top_bar_usage_badges_crowded_narrow_png_snapshot _____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/ac..., pager=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/pager/visual/snapshots/png'))))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9372c9f020>

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

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f936dcb3740>
is_success = <class 'bool'>
settle = <function AcePage.wait_for.<locals>.<lambda> at 0x7f936dcb1640>
timeout = 15.0
timeout_message = <function AcePage.wait_for.<locals>.<lambda> at 0x7f936dcb35e0>
clock = <bound method BaseEventLoop.time of <_UnixSelectorEventLoop running=False closed=False debug=False>>
sleep = <function sleep at 0x7f9381b02090>, backoff_after_misses = 3
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
18.81s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
16.63s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
16.00s call     tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
11.66s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
9.56s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
8.22s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40]
7.62s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots
7.22s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40]
6.93s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
6.91s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40]
6.62s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40]
6.45s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
6.25s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]
6.22s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40]
6.21s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40]
6.00s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots
5.83s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
5.83s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
5.16s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
5.10s call     tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail]
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_linked_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_reply_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py::test_agents_metadata_search_typing_and_committed_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_context_reply_no_files_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_selected_gate_shell_output_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40]
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_plugins_loading_png_snapshot
FAILED tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot
============================= 28 failed in 45.06s ==============================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 11/11 workers
11 workers [122 items]

........................................................................ [ 59%]
..................................................                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
32.37s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
20.03s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot
16.43s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
13.93s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
13.75s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_expanded_png_snapshot
12.57s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_narrowed_png_snapshot
12.48s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_above_sase_context_png_snapshot
12.26s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_partially_streamed_context_lanes_png_snapshot
11.97s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_stacked_pane_png_snapshot
11.63s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
10.81s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_jump_panel.py::test_jump_panel_collapsed_two_digit_overflow_png_snapshot
10.77s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_full_menu_png_snapshot[dark]
10.70s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_tree_fold_levels_png_snapshots
10.29s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_running_clan_runtime_png_snapshots
9.70s call     tests/ace/tui/visual/test_ace_png_snapshots_model_alias_completion.py::test_model_alias_completion_filtered_preview_png_snapshot
9.66s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_filtered_preview_png_snapshot
9.50s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_epic_clan_panel_png_snapshots
9.44s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_advisory_png_snapshot
9.27s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_full_menu_png_snapshot[light]
8.81s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_narrow_scoped_png_snapshot
======================== 122 passed in 97.97s (0:01:37) ========================
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 1/1 worker
1 worker [8 items]

........                                                                 [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


============================= slowest 20 durations =============================
13.33s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_neighbors.py::test_agents_lane_neighbors_above_sase_context_png_snapshot
8.38s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_running_clan_runtime_png_snapshots
6.21s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_group_clan_collapse.py::test_selected_clan_collapses_before_open_sibling_png_snapshot
5.23s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_artifacts.py::test_agents_artifact_file_type_icons_png_snapshot
4.30s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_running_family_current_runtime_png_snapshots
3.73s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_list_png_snapshot
3.20s call     tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_updates_core_update_available_png_snapshot
3.08s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_partially_streamed_context_lanes_png_snapshot
0.08s setup    tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_agent_list_png_snapshot

(11 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 8 passed in 55.07s ==============================
fix-tui-screenshots: update partial
scope: full
WARNING:
  capture evidence is incomplete for 28 node(s) (tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots, tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_context_reply_no_files_png_snapshot, tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_reply_png_snapshot, tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot, tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots); stale goldens were left in place
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_context_reply_no_files_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_reply_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_reply_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_external_repos.py::test_agents_external_repo_diff_file_panel_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_gate.py::test_selected_gate_shell_output_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_conversation_monitor_phase_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_family_panel_shells_monitor_metadata_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[degraded-overrides5-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[failed_diagnostics-overrides2-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[host_completed-overrides1-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[lost-overrides4-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[needs_attention-overrides6-120-40]))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[running-overrides0-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel_monitor.py::test_monitor_state_detail_png_snapshots[timeout-overrides3-120-40] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_commit_messages_panel_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_linked_repo_diff_file_panel_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_linked_repos.py::test_agents_linked_repo_diff_file_panel_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py::test_agents_metadata_search_typing_and_committed_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_panels.py::test_agents_collapsed_panel_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_clan_summaries.py::test_tribe_panel_clan_summaries_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_prompts.py::test_tribe_panel_prompts_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_waiting.py::test_agents_waiting_unknown_zoom_modal_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_plugins_loading_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_plugins_loading_png_snapshot))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail] after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_llm_calls.py::test_agents_llm_calls_panel_detail_level_png_snapshots[2-agents_llm_calls_panel_full_120x40-ACE agents LLM Calls panel full detail]))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator.py::test_top_bar_usage_attention_narrow_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  skipped test_failed node tests/ace/tui/visual/test_ace_png_snapshots_provider_usage_indicator_states.py::test_top_bar_usage_badges_crowded_narrow_png_snapshot after 3 attempt(s); see .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/capture.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-1.log, .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/recover-2.log (test failed or was lost and never recovered after 3 attempt(s); existing goldens left untouched (FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots))
  Those goldens were left unchanged and are not known to be current.
counts: created=0 updated=138 unchanged=574 stale=0
manifest: .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/manifest.json
run-dir: .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55
report: .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/report/visual-failure-report.html
report-summary: .pytest_cache/sase-visual/runs/cef1aa0085014698970f70bdee8e0f55/report/summary.md
succeeded  exit=0  duration=1108972ms

