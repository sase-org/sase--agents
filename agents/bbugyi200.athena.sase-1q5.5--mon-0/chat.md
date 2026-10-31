# Chat History - ace-run (sase-1q5.5--mon-0)

- **TIMESTAMP:** 2026-10-30 20:53:31 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1q5.5--mon-0

## Prompt

sase monitor start --command '.venv/bin/pytest -s -m slow tests/ace/tui/bench_tui_jk.py' --reason 'Collect the after Agents j/k benchmark for sase-1q5.5'

## Response

sase tool run 11cf7245b09b1af591c5d121cb5b76c2
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
configfile: pyproject.toml
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 19 items

tests/ace/tui/bench_tui_jk.py 
Agents tab ]/[ switch at 500 roots:
  scenario                    n   p50_ms   p95_ms   max_ms
  agents_tab_switch          40   215.58   470.83   953.88

Agents tab j/k on AgentTabKey(kind='default', value=''):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       20    16.00    26.81    46.73
  prev                       20    19.97    26.09    59.71

Agents tab j/k on AgentTabKey(kind='named', value='sase'):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       20    20.53    37.30    54.39
  prev                       20    21.02    44.45    53.19
.
Archive j/k key-to-paint at 11k roots (event-level):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       61    10.58    15.71   542.62
  prev                       60    12.49    15.30    17.41
.
archive warm-open ms: cold(first)=214.7 warm median=117.4 warm samples=['104.0', '110.0', '141.2', '113.7', '136.2', '117.4', '124.1'] sync-open median=115.4 (budget 100 ms)
F
Agents tab j/k/J/K synthetic large-list baseline:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       19    24.13    69.57   168.56
  next_agent_panel           20    41.91    53.42    58.25
  prev                       19    17.01    42.82    43.18
  prev_agent_panel           20    65.84    76.48    94.60
.
Agents clan fold level 1:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       20    10.21    13.44    16.07
  prev                       20     9.77    15.94    23.23

Agents clan fold level 2:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       20     9.93    16.30    26.44
  prev                       20    11.18    14.11    14.91
F
Agents selected tribe fold level 1:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       40    68.28   108.28   109.50
  prev                       40    67.34   109.74   116.02
F
Block-cycle (paged):
  scenario                    n   p50_ms   p95_ms   max_ms
  cycle_block                20    39.27    46.51    63.50
.
sticky-Reply-blocks (SINGLE):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       40    28.54    62.06    70.73
  prev                       20    37.90    55.99    56.80

sticky-Reply-blocks (LEFT_RIGHT):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       40    55.59    86.79   101.08
  prev                       20    71.71    96.17   102.92
.
Agents tab j/k, Reply above Main (baseline):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       32    68.78    98.36    99.58
  prev                       32    64.89    89.31   105.18

Agents tab j/k, Reply above FINAL (triage loop):
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       32    41.16    57.60    60.85
  prev                       32    42.83    64.46    70.57
next: FINAL-pinned p95 delta -40.76 ms
prev: FINAL-pinned p95 delta -24.85 ms
.
Agents Fleet j/k fault scenario hung_host:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       80    15.44    40.30    56.54
  prev                       80    16.58    50.07    69.53
F
Agents Fleet j/k fault scenario reconnect_churn:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       80    15.90    37.48    73.93
  prev                       80    15.93    37.80    47.91
F
Agents Fleet j/k fault scenario event_burst:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       80    20.50    31.18    64.95
  prev                       80    17.43    39.78    74.21
Foff-loop subprocesses during the run (rule 1 compliant):
  asyncio_6: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'rev-parse', 'HEAD']
  asyncio_6: ('gh', 'api', '-X', 'GET', 'search/repositories?q=topic:sase--plugin&per_page=100&page=1')
  asyncio_6: ['npm', 'root', '-g']
  asyncio_6: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'rev-parse', '--show-toplevel']
  asyncio_2: ['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/bin/python', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/procs/supervisor_bootstrap.py', '--proc-id', 'cbp0sfekx4jr', '--pid-fd', '14']
  asyncio_3: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'config', '--get', 'remote.origin.url']
  asyncio_3: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'config', '--get', 'remote.origin.url']
  asyncio_3: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'config', '--get', 'remote.origin.url']
  asyncio_3: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'config', '--get', 'remote.origin.url']
  asyncio_3: ['git', '-C', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13', 'config', '--get', 'remote.origin.url']
  asyncio_1: ['git', 'config', '--get', 'remote.origin.url']
  asyncio_1: ['git', 'rev-parse', '--show-toplevel']
.
Agents tab j/k, rail absent:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       44    20.34    48.91    58.01
  prev                       44    17.12    43.29    47.87

Agents tab j/k, rail painting:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       44    21.54    44.17    53.88
  prev                       44    20.33    45.95    55.99
F
Axe tab cached j/k baseline:
  scenario                    n   p50_ms   p95_ms   max_ms
  next                       20    25.05    42.96    46.58
  prev                       20    33.19    43.09    50.04
F
Patches tab j/k baseline:
  scenario                    n   p50_ms   p95_ms   max_ms
  stitches.next              20     1.10     2.67    10.44
  stitches.prev              20     1.02     2.00     2.49
.
Unread ,u branch 'visible':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,u                         10    37.93    44.53    44.53

Unread ,u branch 'collapsed_panel':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,u                         10    29.85    36.00    36.00

Unread ,u branch 'collapsed_clan':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,u                         10    44.70    76.97    76.97

Unread ,u branch 'off_tab':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,u                         10    34.30    50.85    50.85
.
Unread ,j branch 'visible':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,j                         10    52.50    84.13    84.13

Unread ,j branch 'collapsed_panel':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,j                         10    50.65   104.88   104.88

Unread ,j branch 'collapsed_clan':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,j                         10    62.41   191.26   191.26

Unread ,j branch 'off_tab':
  scenario                    n   p50_ms   p95_ms   max_ms
  ,j                          8    73.25   180.45   180.45
  agents_tab_switch           2   169.23   178.81   178.81
.
deck j/k wall-clock ms: 2 panels p50=60.07 p95=80.52 | 3 panels p50=58.52 p95=80.63 (budget 16 ms)
.

=================================== FAILURES ===================================
__________________ test_bench_archive_warm_open_to_first_rows __________________

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1d06e01710>
tmp_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_archive_warm_open_t0')

    async def test_bench_archive_warm_open_to_first_rows(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        """Warm ``,a`` reopen shows first Archive rows within 100 ms (median)."""
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
        insert_archive_rows(tmp_path, _scale_index_rows())
        profile = agents_archive_profile()
        corpus = compile_agent_archive_corpus(
            root=tmp_path,
            index_status={"status": "ok"},
            timezone="UTC",
            link_facets={},
        )
        async with AcePage(initial_tab="agents") as page:
            await wait_for_startup(page)
            app = page.app
            _wire_real_corpus(app, corpus, profile)
            note_inbox_applied_for_archive(app, load_state=complete_load())
    
            # Cold open: no warm handle yet. Reported, not budgeted: the
            # corpus/facet build cost belongs to bench_agent_archive_corpus.
            _cold_sync_ms, cold_ms = await _open_to_first_rows_ms(app, page)
            first_keys = _run_row_keys(page)
            assert len(first_keys) > 100, "the Today banner must page its 11k roots"
            await _settle_revalidation(page)
            assert archive_corpus_snapshot(app).warm
    
            warm_sync: list[float] = []
            warm_ms: list[float] = []
            for _ in range(_WARM_REOPENS):
                close_agents_archive_view(app)
                await page.pause()
                sync_ms, rows_ms = await _open_to_first_rows_ms(app, page)
                warm_sync.append(sync_ms)
                warm_ms.append(rows_ms)
    
            # The budgeted number is first rows from held windows. Paint is
            # proved untimed by screen text, and the revalidation must
            # settle with rows still current.
            await _prove_rows_painted(page, "scale.")
            await _settle_revalidation(page)
            assert archive_corpus_snapshot(app).warm
            assert len(_run_row_keys(page)) > 100
    
            median_warm = statistics.median(warm_ms)
            median_sync = statistics.median(warm_sync)
            print(
                f"\narchive warm-open ms: cold(first)={cold_ms:.1f} "
                f"warm median={median_warm:.1f} warm samples="
                f"{[f'{v:.1f}' for v in warm_ms]} "
                f"sync-open median={median_sync:.1f} "
                f"(budget {_WARM_OPEN_BUDGET_MS:g} ms)"
            )
>           assert median_warm < _WARM_OPEN_BUDGET_MS, (
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                f"warm Archive open median {median_warm:.1f} ms exceeds "
                f"{_WARM_OPEN_BUDGET_MS:g} ms"
            )
E           AssertionError: warm Archive open median 117.4 ms exceeds 100 ms

tests/ace/tui/bench_tui_jk_archive.py:265: AssertionError
_________________ test_bench_clan_jk_at_each_panel_fold_level __________________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_clan_jk_at_each_pan0/tui_jk.jsonl')

    async def test_bench_clan_jk_at_each_panel_fold_level(
        _perf_jsonl: Path,
    ) -> None:
        """Keep clan key-to-paint p95 below budget at levels 1, 2, and 3."""
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        level_summaries: dict[FoldLevel, dict[str, dict[str, float]]] = {}
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("ctrl+l")
            await pilot.pause()
            _install_clan_agents_fixture(app)
            app._refresh_agents_display(list_changed=True, defer_detail=True)
            # Let the initial clan aggregation and the Textual layout pass settle;
            # the samples below measure steady-state navigation, not fixture mount.
            await pilot.pause(0.2)
            assert app._agents
            assert all(agent.is_clan_container for agent in app._agents)
    
            for index, level in enumerate(CLAN_FOLD_SCALE):
                assert app.panel_fold_level is level
                await _warm_agents_navigation(pilot)
                before = len(_read_samples(_perf_jsonl))
                for _ in range(_KEYS_PER_SCENARIO):
                    await pilot.press("j")
                    await pilot.pause(0.01)
                for _ in range(_KEYS_PER_SCENARIO):
                    await pilot.press("k")
                    await pilot.pause(0.01)
                samples = _read_samples(_perf_jsonl)[before:]
                summary = _summarize(samples)
                level_summaries[level] = summary
                _print_table(f"Agents clan fold level {index + 1}:", summary)
                assert samples
>               assert all(stats["p95"] < 16.0 for stats in summary.values()), (
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                    f"clan fold level {index + 1} exceeded 16 ms p95: {summary}"
                )
E               AssertionError: clan fold level 2 exceeded 16 ms p95: {'next': {'n': 20.0, 'p50': 9.930918575264513, 'p95': 16.30127616226673, 'max': 26.44100203178823}, 'prev': {'n': 20.0, 'p50': 11.184392496943474, 'p95': 14.106913935393095, 'max': 14.91191191598773}}

tests/ace/tui/bench_tui_jk_agents.py:103: AssertionError
_______________ test_bench_selected_tribe_jk_at_each_fold_level ________________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_selected_tribe_jk_a0/tui_jk.jsonl')

    async def test_bench_selected_tribe_jk_at_each_fold_level(
        _perf_jsonl: Path,
    ) -> None:
        """Keep selected-tribe panel cycling below budget at all four levels."""
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        level_summaries: dict[FoldLevel, dict[str, dict[str, float]]] = {}
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("ctrl+l")
            await pilot.pause()
            _install_agents_fixture(app, count=48)
            app._refresh_agents_display(list_changed=True, defer_detail=True)
            await pilot.pause(0.2)
            assert len(app._panel_group.panel_keys) == 4
            assert app._activate_focused_panel() is True
            assert app._resolve_focused_panel() is not None
    
            for index, level in enumerate(TRIBE_FOLD_SCALE):
                assert app.panel_fold_level is level
                assert (
                    len(app._panel_group.panel_keys),
                    app._agent_panels_grouped,
                ) == (4, False)
                assert app._resolve_focused_panel() is not None
                await _warm_agents_navigation(pilot)
                assert (
                    len(app._panel_group.panel_keys),
                    app._agent_panels_grouped,
                ) == (4, False)
                assert app._resolve_focused_panel() is not None
                before = len(_read_samples(_perf_jsonl))
                # Forty samples per direction keep the p95 meaningful when the
                # host occasionally delays one renderer frame.
                for _ in range(_SELECTED_TRIBE_KEYS_PER_SCENARIO):
                    await pilot.press("j")
                    await pilot.pause(0.01)
                for _ in range(_SELECTED_TRIBE_KEYS_PER_SCENARIO):
                    await pilot.press("k")
                    await pilot.pause(0.01)
                samples = _read_samples(_perf_jsonl)[before:]
                summary = _summarize(samples)
                level_summaries[level] = summary
                _print_table(f"Agents selected tribe fold level {index + 1}:", summary)
                assert samples
>               assert all(
                    stats["p95"] < _SELECTED_TRIBE_P95_BUDGET_MS
                    for stats in summary.values()
                ), (
                    f"tribe fold level {index + 1} exceeded "
                    f"{_SELECTED_TRIBE_P95_BUDGET_MS:g} ms p95: {summary}"
                )
E               AssertionError: tribe fold level 1 exceeded 40 ms p95: {'next': {'n': 40.0, 'p50': 68.27947509009391, 'p95': 108.28401404432952, 'max': 109.50264101848006}, 'prev': {'n': 40.0, 'p50': 67.33829143922776, 'p95': 109.73937390372157, 'max': 116.02296493947506}}

tests/ace/tui/bench_tui_jk_agents.py:182: AssertionError
____________ test_bench_agents_fleet_jk_fault_scenarios[hung_host] _____________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_agents_fleet_jk_fau0/tui_jk.jsonl')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1d1414b770>
scenario = 'hung_host'

    @pytest.mark.parametrize(
        "scenario",
        ("hung_host", "reconnect_churn", "event_burst"),
    )
    async def test_bench_agents_fleet_jk_fault_scenarios(
        _perf_jsonl: Path,
        monkeypatch: pytest.MonkeyPatch,
        scenario: str,
    ) -> None:
        """Keep Fleet j/k p95 below 16 ms while a live fault sequence lands."""
        apollo_id = fleet_installation_id("a")
        zeus_id = fleet_installation_id("b")
        config = fleet_config_for_hosts(("apollo", apollo_id), ("zeus", zeus_id))
        stable_response = _fleet_response(
            ("apollo", apollo_id, 18),
            ("zeus", zeus_id, 18),
        )
        fault_sequence = _fault_sequence(scenario, apollo_id=apollo_id, zeus_id=zeus_id)
        stable_facade = ScriptedFleetFacade(
            summary_response=stable_response,
            catalog_response=stable_response,
        )
        fault_facade = ScriptedFleetFacade(
            summary_response=fault_sequence[-1],
            catalog_response=fault_sequence[-1],
            scripts={"catalog": list(fault_sequence), "summary": list(fault_sequence)},
            delays={
                "catalog": _FLEET_FAULT_STEP_DELAY_SECONDS,
                "summary": _FLEET_FAULT_STEP_DELAY_SECONDS,
            },
        )
    
        monkeypatch.setattr(fleet_mod, "load_federation_config", lambda: config)
        monkeypatch.setattr(
            fleet_mod,
            "build_federation_facade",
            lambda _config: stable_facade,
        )
    
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("ctrl+l")
            await pilot.pause()
            _install_fleet_rows(app, stable_response, config=config)
            await pilot.pause(0.2)
            await _warm_agents_navigation(pilot)
    
            monkeypatch.setattr(
                fleet_mod,
                "build_federation_facade",
                lambda _config: fault_facade,
            )
            # Seed the same row shape the first fault-sequence step will confirm,
            # so the measured window below starts from a settled layout: any
            # paint-timing cost comes from faults landing mid-navigation, not
            # from a one-off structural repaint.
            _install_fleet_rows(app, fault_sequence[0], config=config)
            await pilot.pause(0.2)
            await _warm_agents_navigation(pilot)
    
            before = len(_read_samples(_perf_jsonl))
            fault_start = time.perf_counter()
            app._schedule_agents_fleet_refresh(source=f"bench_{scenario}", force=True)
            key_count = 0
            for direction in ("j", "k"):
                for _ in range(_FLEET_FAULT_KEYS_PER_DIRECTION):
                    await pilot.press(direction)
                    await pilot.pause()
                    key_count += 1
                    if key_count % _FLEET_FAULT_TRIGGER_EVERY_KEYS == 0:
                        app._schedule_agents_fleet_refresh(
                            source=f"bench_{scenario}", force=False
                        )
            await _wait_for_fleet_refresh(app)
            fault_end = time.perf_counter()
    
        samples = [
            sample
            for sample in _read_samples(_perf_jsonl)[before:]
            if sample.get("tab") == "agents" and sample.get("action") in {"next", "prev"}
        ]
        summary = _summarize(samples)
        _print_table(f"Agents Fleet j/k fault scenario {scenario}:", summary)
        assert set(summary) == {"next", "prev"}
>       assert all(
            stats["p95"] < _FLEET_FAULT_P95_BUDGET_MS for stats in summary.values()
        ), f"Fleet fault scenario {scenario} exceeded 16 ms p95: {summary}"
E       AssertionError: Fleet fault scenario hung_host exceeded 16 ms p95: {'next': {'n': 80.0, 'p50': 15.43625839985907, 'p95': 40.29822116717696, 'max': 56.5439579077065}, 'prev': {'n': 80.0, 'p50': 16.58015849534422, 'p95': 50.071647157892585, 'max': 69.52846003696322}}

tests/ace/tui/bench_tui_jk_fleet.py:136: AssertionError
_________ test_bench_agents_fleet_jk_fault_scenarios[reconnect_churn] __________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_agents_fleet_jk_fau1/tui_jk.jsonl')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1ca4ebe3c0>
scenario = 'reconnect_churn'

    @pytest.mark.parametrize(
        "scenario",
        ("hung_host", "reconnect_churn", "event_burst"),
    )
    async def test_bench_agents_fleet_jk_fault_scenarios(
        _perf_jsonl: Path,
        monkeypatch: pytest.MonkeyPatch,
        scenario: str,
    ) -> None:
        """Keep Fleet j/k p95 below 16 ms while a live fault sequence lands."""
        apollo_id = fleet_installation_id("a")
        zeus_id = fleet_installation_id("b")
        config = fleet_config_for_hosts(("apollo", apollo_id), ("zeus", zeus_id))
        stable_response = _fleet_response(
            ("apollo", apollo_id, 18),
            ("zeus", zeus_id, 18),
        )
        fault_sequence = _fault_sequence(scenario, apollo_id=apollo_id, zeus_id=zeus_id)
        stable_facade = ScriptedFleetFacade(
            summary_response=stable_response,
            catalog_response=stable_response,
        )
        fault_facade = ScriptedFleetFacade(
            summary_response=fault_sequence[-1],
            catalog_response=fault_sequence[-1],
            scripts={"catalog": list(fault_sequence), "summary": list(fault_sequence)},
            delays={
                "catalog": _FLEET_FAULT_STEP_DELAY_SECONDS,
                "summary": _FLEET_FAULT_STEP_DELAY_SECONDS,
            },
        )
    
        monkeypatch.setattr(fleet_mod, "load_federation_config", lambda: config)
        monkeypatch.setattr(
            fleet_mod,
            "build_federation_facade",
            lambda _config: stable_facade,
        )
    
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("ctrl+l")
            await pilot.pause()
            _install_fleet_rows(app, stable_response, config=config)
            await pilot.pause(0.2)
            await _warm_agents_navigation(pilot)
    
            monkeypatch.setattr(
                fleet_mod,
                "build_federation_facade",
                lambda _config: fault_facade,
            )
            # Seed the same row shape the first fault-sequence step will confirm,
            # so the measured window below starts from a settled layout: any
            # paint-timing cost comes from faults landing mid-navigation, not
            # from a one-off structural repaint.
            _install_fleet_rows(app, fault_sequence[0], config=config)
            await pilot.pause(0.2)
            await _warm_agents_navigation(pilot)
    
            before = len(_read_samples(_perf_jsonl))
            fault_start = time.perf_counter()
            app._schedule_agents_fleet_refresh(source=f"bench_{scenario}", force=True)
            key_count = 0
            for direction in ("j", "k"):
                for _ in range(_FLEET_FAULT_KEYS_PER_DIRECTION):
                    await pilot.press(direction)
                    await pilot.pause()
                    key_count += 1
                    if key_count % _FLEET_FAULT_TRIGGER_EVERY_KEYS == 0:
                        app._schedule_agents_fleet_refresh(
                            source=f"bench_{scenario}", force=False
                        )
            await _wait_for_fleet_refresh(app)
            fault_end = time.perf_counter()
    
        samples = [
            sample
            for sample in _read_samples(_perf_jsonl)[before:]
            if sample.get("tab") == "agents" and sample.get("action") in {"next", "prev"}
        ]
        summary = _summarize(samples)
        _print_table(f"Agents Fleet j/k fault scenario {scenario}:", summary)
        assert set(summary) == {"next", "prev"}
>       assert all(
            stats["p95"] < _FLEET_FAULT_P95_BUDGET_MS for stats in summary.values()
        ), f"Fleet fault scenario {scenario} exceeded 16 ms p95: {summary}"
E       AssertionError: Fleet fault scenario reconnect_churn exceeded 16 ms p95: {'next': {'n': 80.0, 'p50': 15.895214979536831, 'p95': 37.484906148165464, 'max': 73.92893498763442}, 'prev': {'n': 80.0, 'p50': 15.92973549850285, 'p95': 37.79892413876951, 'max': 47.913825837895274}}

tests/ace/tui/bench_tui_jk_fleet.py:136: AssertionError
___________ test_bench_agents_fleet_jk_fault_scenarios[event_burst] ____________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_agents_fleet_jk_fau2/tui_jk.jsonl')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1d07572dd0>
scenario = 'event_burst'

    @pytest.mark.parametrize(
        "scenario",
        ("hung_host", "reconnect_churn", "event_burst"),
    )
    async def test_bench_agents_fleet_jk_fault_scenarios(
        _perf_jsonl: Path,
        monkeypatch: pytest.MonkeyPatch,
        scenario: str,
    ) -> None:
        """Keep Fleet j/k p95 below 16 ms while a live fault sequence lands."""
        apollo_id = fleet_installation_id("a")
        zeus_id = fleet_installation_id("b")
        config = fleet_config_for_hosts(("apollo", apollo_id), ("zeus", zeus_id))
        stable_response = _fleet_response(
            ("apollo", apollo_id, 18),
            ("zeus", zeus_id, 18),
        )
        fault_sequence = _fault_sequence(scenario, apollo_id=apollo_id, zeus_id=zeus_id)
        stable_facade = ScriptedFleetFacade(
            summary_response=stable_response,
            catalog_response=stable_response,
        )
        fault_facade = ScriptedFleetFacade(
            summary_response=fault_sequence[-1],
            catalog_response=fault_sequence[-1],
            scripts={"catalog": list(fault_sequence), "summary": list(fault_sequence)},
            delays={
                "catalog": _FLEET_FAULT_STEP_DELAY_SECONDS,
                "summary": _FLEET_FAULT_STEP_DELAY_SECONDS,
            },
        )
    
        monkeypatch.setattr(fleet_mod, "load_federation_config", lambda: config)
        monkeypatch.setattr(
            fleet_mod,
            "build_federation_facade",
            lambda _config: stable_facade,
        )
    
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("ctrl+l")
            await pilot.pause()
            _install_fleet_rows(app, stable_response, config=config)
            await pilot.pause(0.2)
            await _warm_agents_navigation(pilot)
    
            monkeypatch.setattr(
                fleet_mod,
                "build_federation_facade",
                lambda _config: fault_facade,
            )
            # Seed the same row shape the first fault-sequence step will confirm,
            # so the measured window below starts from a settled layout: any
            # paint-timing cost comes from faults landing mid-navigation, not
            # from a one-off structural repaint.
            _install_fleet_rows(app, fault_sequence[0], config=config)
            await pilot.pause(0.2)
            await _warm_agents_navigation(pilot)
    
            before = len(_read_samples(_perf_jsonl))
            fault_start = time.perf_counter()
            app._schedule_agents_fleet_refresh(source=f"bench_{scenario}", force=True)
            key_count = 0
            for direction in ("j", "k"):
                for _ in range(_FLEET_FAULT_KEYS_PER_DIRECTION):
                    await pilot.press(direction)
                    await pilot.pause()
                    key_count += 1
                    if key_count % _FLEET_FAULT_TRIGGER_EVERY_KEYS == 0:
                        app._schedule_agents_fleet_refresh(
                            source=f"bench_{scenario}", force=False
                        )
            await _wait_for_fleet_refresh(app)
            fault_end = time.perf_counter()
    
        samples = [
            sample
            for sample in _read_samples(_perf_jsonl)[before:]
            if sample.get("tab") == "agents" and sample.get("action") in {"next", "prev"}
        ]
        summary = _summarize(samples)
        _print_table(f"Agents Fleet j/k fault scenario {scenario}:", summary)
        assert set(summary) == {"next", "prev"}
>       assert all(
            stats["p95"] < _FLEET_FAULT_P95_BUDGET_MS for stats in summary.values()
        ), f"Fleet fault scenario {scenario} exceeded 16 ms p95: {summary}"
E       AssertionError: Fleet fault scenario event_burst exceeded 16 ms p95: {'next': {'n': 80.0, 'p50': 20.50283388234675, 'p95': 31.179722864180803, 'max': 64.9468069896102}, 'prev': {'n': 80.0, 'p50': 17.425713129341602, 'p95': 39.77685421705246, 'max': 74.21162398532033}}

tests/ace/tui/bench_tui_jk_fleet.py:136: AssertionError
_____________ test_bench_agents_jk_with_and_without_the_link_rail ______________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_agents_jk_with_and_0/tui_jk.jsonl')

    async def test_bench_agents_jk_with_and_without_the_link_rail(
        _perf_jsonl: Path,
    ) -> None:
        """Keep the rail off the felt part of key-to-paint (``bead:sase-ug.6``).
    
        The rail is deliberately undebounced (``tui_perf`` rule 7), so it repaints
        on every highlight move. The absolute p95 on this scenario is dominated by
        the 240-row Agents list and varies with the host, so what is asserted here
        is the *delta*: the same warmed j/k run, in the same app, with a hidden
        rail and then with an index in which every agent has links -- far denser
        than the real graph, where 81.5% of linked entities have exactly one link
        and most entities have none.
    
        Two measurement hazards make the naive form of this A/B unusable, and both
        are worth keeping fixed:
    
        1. *Both* arms must install an index fixture. Leaving ``_link_index`` unset
           for the baseline makes the first measured keystroke schedule a real
           ``load_artifact_links_snapshot`` build against the host's live artifact
           index, charging that disk work -- and the repaint that lands when it
           finishes -- to the baseline. A chipless index hides the rail without
           scheduling anything.
        2. The arms must be *interleaved*, not run once each back to back. This
           host's absolute j/k p50 drifts between 12 ms and 20 ms across runs as
           background load changes, which is larger than the rail's own cost; two
           sequential arms sample that drift at two different times and hand the
           difference to the rail. Alternating short rounds and pooling their
           samples lets the drift land on both arms instead.
        """
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("ctrl+l")
            await pilot.pause()
            _install_agents_fixture(app)
            app._refresh_agents_display(list_changed=True, defer_detail=True)
            await pilot.pause()
            rail = app.query_one("#link-rail", LinkRail)
    
            async def _arm(*, painting: bool) -> list[dict[str, object]]:
                _install_link_index_fixture(app, links_per_agent=3 if painting else 0)
                app.refresh_link_rail()
                await pilot.pause()
                assert rail.display is painting, (
                    f"expected rail.display={painting} for this arm; a chipless "
                    "index must hide the rail and a populated one must paint it"
                )
                return await _collect_agents_jk(
                    pilot, _perf_jsonl, keys=_LINK_RAIL_KEYS_PER_ROUND
                )
    
            # Whichever arm goes first absorbs the one-time lazy Textual layout and
            # renderer work that `_warm_agents_navigation`'s 8 keys do not reach --
            # it shows up as a lone ~250 ms sample. Spend a discarded round on it so
            # no measured round is charged for it.
            await _arm(painting=False)
    
            absent_samples: list[dict[str, object]] = []
            present_samples: list[dict[str, object]] = []
            for _ in range(_LINK_RAIL_AB_ROUNDS):
                absent_samples += await _arm(painting=False)
                present_samples += await _arm(painting=True)
    
        absent = _summarize(absent_samples)
        present = _summarize(present_samples)
        _print_table("Agents tab j/k, rail absent:", absent)
        _print_table("Agents tab j/k, rail painting:", present)
        assert absent and present, "perf JSONL captured no samples"
        for scenario, stats in present.items():
            baseline = absent.get(scenario)
            assert baseline is not None, f"no rail-absent baseline for {scenario}"
            delta = stats["p95"] - baseline["p95"]
            assert delta < _LINK_RAIL_P95_DELTA_BUDGET_MS, (
                f"the rail added {delta:.2f} ms to {scenario} p95 "
                f"(absent {baseline['p95']:.2f} ms, present {stats['p95']:.2f} ms); "
                f"budget is {_LINK_RAIL_P95_DELTA_BUDGET_MS:g} ms"
            )
        stall_path = _perf_jsonl.with_name("tui_stalls.jsonl")
>       _assert_no_stall_rows(stall_path)

tests/ace/tui/bench_tui_jk_link_rail.py:122: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

stall_path = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_agents_jk_with_and_0/tui_stalls.jsonl')

    def _assert_no_stall_rows(stall_path: Path) -> None:
        """Activity capture shares this log; activity rows are not freezes."""
        rows = _read_samples(stall_path)
>       assert not [row for row in rows if row.get("event") != "prompt_activity"]
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/_bench_tui_jk_helpers.py:270: AssertionError
______________________________ test_bench_axe_jk _______________________________

_perf_jsonl = PosixPath('/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws13-261030_202121/pytest-of-bryan/pytest-1/test_bench_axe_jk0/tui_jk.jsonl')

    async def test_bench_axe_jk(_perf_jsonl: Path) -> None:
        """Measure cached j/k latency on the Axe tab with synthetic AXE rows."""
        app = AceApp(query="!!!", auto_start_axe=False, refresh_interval=0)
        async with app.run_test() as pilot:
            await _wait_for_startup(app, pilot)
            await pilot.press("tab")  # next_tab: agents -> patches
            await pilot.pause()
            await pilot.press("tab")  # next_tab: patches -> axe
            await pilot.pause()
            _install_axe_fixture(app)
            await pilot.pause(0.2)
            assert len(app._axe_items) > (_KEYS_PER_SCENARIO * 2)
            await _warm_axe_navigation(pilot)
            before = len(_read_samples(_perf_jsonl))
            for _ in range(_KEYS_PER_SCENARIO):
                await pilot.press("j")
                await pilot.pause(0.01)
            for _ in range(_KEYS_PER_SCENARIO):
                await pilot.press("k")
                await pilot.pause(0.01)
    
        samples = _read_samples(_perf_jsonl)[before:]
        summary = _summarize(samples)
        _print_table("Axe tab cached j/k baseline:", summary)
        assert samples, "perf JSONL captured no AXE samples; instrumentation may be broken"
>       assert {str(sample["tab"]) for sample in samples} == {"axe"}
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/bench_tui_jk_panes.py:91: AssertionError
============================= slowest 20 durations =============================
117.34s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_jk_with_final_pinned
60.20s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_tab_switch_at_500_roots
54.92s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_jk_with_and_without_the_link_rail
43.05s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_fleet_jk_fault_scenarios[hung_host]
42.56s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_fleet_jk_fault_scenarios[reconnect_churn]
39.25s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_fleet_jk_fault_scenarios[event_burst]
32.25s call     tests/ace/tui/bench_tui_jk.py::test_bench_sticky_reply_heavy_sessions
31.49s call     tests/ace/tui/bench_tui_jk.py::test_bench_unread_jump_branches
26.38s call     tests/ace/tui/bench_tui_jk.py::test_bench_archive_jk_at_scale
25.85s call     tests/ace/tui/bench_tui_jk.py::test_bench_selected_tribe_jk_at_each_fold_level
23.51s call     tests/ace/tui/bench_tui_jk.py::test_bench_agents_jk_and_panel_navigation
23.20s call     tests/ace/tui/bench_tui_jk.py::test_bench_unread_bulk_ack_branches
20.98s call     tests/ace/tui/bench_tui_jk.py::test_bench_clan_jk_at_each_panel_fold_level
14.60s call     tests/ace/tui/bench_tui_jk.py::test_bench_axe_jk
11.36s call     tests/ace/tui/bench_tui_jk.py::test_bench_keystroke_reaches_no_provider_discovery_or_subprocess
10.94s call     tests/ace/tui/bench_tui_jk.py::test_bench_archive_warm_open_to_first_rows
8.05s call     tests/ace/tui/bench_tui_jk.py::test_bench_patches_jk
6.47s call     tests/ace/tui/bench_tui_jk.py::test_bench_deck_jk_two_vs_three_panels
5.69s call     tests/ace/tui/bench_tui_jk.py::test_bench_block_cycle_paged
3.80s teardown tests/ace/tui/bench_tui_jk.py::test_bench_block_cycle_paged
=========================== short test summary info ============================
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_archive_warm_open_to_first_rows
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_clan_jk_at_each_panel_fold_level
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_selected_tribe_jk_at_each_fold_level
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_agents_fleet_jk_fault_scenarios[hung_host]
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_agents_fleet_jk_fault_scenarios[reconnect_churn]
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_agents_fleet_jk_fault_scenarios[event_burst]
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_agents_jk_with_and_without_the_link_rail
FAILED tests/ace/tui/bench_tui_jk.py::test_bench_axe_jk - AssertionError
=================== 8 failed, 11 passed in 614.51s (0:10:14) ===================
failed  exit=1  duration=636282ms

