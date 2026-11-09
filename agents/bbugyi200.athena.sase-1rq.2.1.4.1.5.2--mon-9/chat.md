# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-9)

- **TIMESTAMP:** 2026-11-09 01:27:37 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-9

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after archive pulse Enter, Beads slash wait, and paused stall-watchdog repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase tool run 42f03b2b7ac36ae59d88a90425538726
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 1141097, sampler pid 1141139 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-3683166-1794201071587564318.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 104 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 39.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 310.9G/45186524i tmp 28.3G/997945i workspace 310.9G/45186524i | scratch used 0.1G in 22247 entries (truncated) | progress none yet
[contention-diag] +17s soak 28p/80t rss 2.3G pss 2.0G swap 0.0G majflt 156 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.2G pss 1.9G | host avail 36.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 15.62 | cgroup 2.1G/max oom_kill 0 | free scratch 310.7G/45186414i tmp 28.3G/997945i workspace 310.7G/45186414i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 3.6G pss 3.2G swap 1.2G majflt 879 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.4G pss 3.1G | host avail 35.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.33 cpu 18.85 | cgroup 3.3G/max oom_kill 0 | free scratch 310.6G/45186426i tmp 28.3G/997945i workspace 310.6G/45186426i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +47s soak 28p/80t rss 4.6G pss 4.2G swap 1.3G majflt 884 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.5G pss 4.2G | host avail 33.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.16 cpu 22.32 | cgroup 4.4G/max oom_kill 0 | free scratch 310.5G/45186429i tmp 28.3G/997945i workspace 310.5G/45186429i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +62s soak 29p/89t rss 5.4G pss 5.0G swap 1.2G majflt 1276 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.3G pss 4.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.1/0.09 io 0.1 cpu 20.39 | cgroup 5.3G/max oom_kill 0 | free scratch 310.4G/45186432i tmp 28.3G/997945i workspace 310.4G/45186432i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/90t rss 6.1G pss 5.7G swap 1.2G majflt 1321 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.0G pss 5.6G | host avail 32.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.02 cpu 19.68 | cgroup 6.1G/max oom_kill 0 | free scratch 310.1G/45186015i tmp 28.3G/997945i workspace 310.1G/45186015i | repeat-01 collected 2/26 workers (4797 items) tests 0 done 0 failed
contention shards: 26 workers collected 60628 items in total (2020-2558 per worker)
26 workers [2465 items]

........................................................................ [  3%]
..............................................................[contention-diag] +93s soak 28p/81t rss 6.6G pss 6.1G swap 1.2G majflt 1652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.4G pss 6.0G | host avail 30.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.58 cpu 17.49 | cgroup 6.7G/max oom_kill 0 | free scratch 310.1G/45185151i tmp 28.3G/997945i workspace 310.1G/45185151i | repeat-01 collected 26/26 workers (60628 items) tests 102 done 0 failed | 23 in flight, oldest 1s gw20 tests/ace/test_revert_agent_import_order.py::test_module_imports_first_in_a_fresh_interpreter[sase.ace.revert_agent_resolution]
.......... [  6%]
........................................................................ [  9%]
........................................................................ [ 13%]
........................................................................ [ 16%]
........................................................................ [ 19%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
........................................................................ [ 33%]
........................................................................ [ 36%]
........................................................................ [ 39%]
...............................................................[contention-diag] +108s soak 29p/134t rss 7.1G pss 6.6G swap 1.1G majflt 2403 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.9G pss 6.4G, 1 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.31 cpu 19.62 | cgroup 7.2G/max oom_kill 0 | free scratch 310.0G/45183076i tmp 28.3G/997945i workspace 310.0G/45183076i | repeat-01 collected 26/26 workers (60628 items) tests 921 done 0 failed | 26 in flight, oldest 15s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
......... [ 43%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
........................................................................ [ 56%]
...........................[contention-diag] +124s soak 30p/147t rss 7.5G pss 7.0G swap 1.1G majflt 2528 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.7G, 2 descendant rss 0.2G pss 0.2G | host avail 32.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.32 cpu 24.9 | cgroup 7.6G/max oom_kill 0 | free scratch 310.3G/45182299i tmp 28.3G/997945i workspace 310.3G/45182299i | scratch used 0.3G in 45928 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 1225 done 0 failed | 26 in flight, oldest 31s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
............................................. [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 69%]
.................................................[contention-diag] +141s soak 30p/168t rss 7.7G pss 7.1G swap 1.1G majflt 2598 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.9G, 2 descendant rss 0.1G pss 0.1G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 21.74 | cgroup 7.8G/max oom_kill 0 | free scratch 310.3G/45181462i tmp 28.3G/997945i workspace 310.3G/45181462i | repeat-01 collected 26/26 workers (60628 items) tests 1543 done 0 failed | 26 in flight, oldest 48s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
....................... [ 73%]
........................................................................ [ 76%]
........................................................................ [ 79%]
........................................................................ [ 83%]
..[contention-diag] +156s soak 30p/171t rss 7.9G pss 7.3G swap 1.1G majflt 2707 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 7.1G, 2 descendant rss 0.1G pss 0.1G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 19.51 | cgroup 8.0G/max oom_kill 0 | free scratch 310.3G/45180798i tmp 28.3G/997945i workspace 310.3G/45180798i | repeat-01 collected 26/26 workers (60628 items) tests 1781 done 0 failed | 25 in flight, oldest 60s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
...................................................................... [ 86%]
.....................................................................[contention-diag] +171s soak 33p/196t rss 8.0G pss 7.4G swap 1.0G majflt 2716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.3G, 5 descendant rss 0.1G pss 0.0G | host avail 29.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 20.04 | cgroup 8.1G/max oom_kill 0 | free scratch 310.3G/45180351i tmp 28.3G/997945i workspace 310.3G/45180351i | repeat-01 collected 26/26 workers (60628 items) tests 1939 done 0 failed | 26 in flight, oldest 75s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
... [ 89%]
........................................................................ [ 93%]
.....................................................................[contention-diag] +187s soak 38p/229t rss 8.4G pss 7.7G swap 1.0G majflt 2716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.9G pss 7.4G, 10 descendant rss 0.3G pss 0.1G | host avail 27.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 17.88 | cgroup 8.3G/max oom_kill 0 | free scratch 310.2G/45179930i tmp 28.3G/997945i workspace 310.2G/45179930i | repeat-01 collected 26/26 workers (60628 items) tests 2080 done 0 failed | 25 in flight, oldest 70s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
... [ 96%]
........................................................................ [ 99%]
........................................................................ [103%]
........................................................................ [106%]
........................................................................ [109%]
........................[contention-diag] +202s soak 37p/218t rss 8.4G pss 7.8G swap 1.0G majflt 2738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.5G, 9 descendant rss 0.2G pss 0.2G | host avail 27.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.0 cpu 15.01 | cgroup 8.5G/max oom_kill 0 | free scratch 310.0G/45179134i tmp 28.3G/997945i workspace 310.0G/45179134i | repeat-01 collected 26/26 workers (60628 items) tests 2388 done 0 failed | 26 in flight, oldest 85s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................ [113%]
............................................................[contention-diag] +217s soak 35p/214t rss 8.6G pss 7.9G swap 1.1G majflt 2773 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.2G pss 7.7G, 7 descendant rss 0.2G pss 0.2G | host avail 26.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.12 cpu 16.51 | cgroup 8.6G/max oom_kill 0 | free scratch 309.5G/45178596i tmp 28.3G/997945i workspace 309.5G/45178596i | repeat-01 collected 26/26 workers (60628 items) tests 2500 done 0 failed | 26 in flight, oldest 100s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............ [116%]
........................................................................ [119%]
........................................................................ [123%]
......[contention-diag] +232s soak 30p/212t rss 8.8G pss 8.2G swap 1.0G majflt 2824 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 2 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 16.48 | cgroup 9.0G/max oom_kill 0 | free scratch 309.1G/45178156i tmp 28.3G/997945i workspace 309.1G/45178156i | repeat-01 collected 26/26 workers (60628 items) tests 2654 done 0 failed | 26 in flight, oldest 115s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................................. [126%]
..........................................[contention-diag] +248s soak 35p/225t rss 8.7G pss 8.0G swap 1.0G majflt 2858 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.9G, 7 descendant rss 0.1G pss 0.1G | host avail 33.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 11.72 | cgroup 8.8G/max oom_kill 0 | free scratch 309.6G/45176769i tmp 28.3G/997945i workspace 309.6G/45176769i | scratch used 0.3G in 61527 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 2761 done 0 failed | 26 in flight, oldest 131s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................. [129%]
........................................................................ [133%]
...............................................................[contention-diag] +265s soak 37p/228t rss 9.0G pss 8.4G swap 1.1G majflt 2888 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 9 descendant rss 0.4G pss 0.3G | host avail 35.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.02 cpu 17.44 | cgroup 9.2G/max oom_kill 0 | free scratch 309.5G/45160531i tmp 28.3G/997941i workspace 309.5G/45160533i | repeat-01 collected 26/26 workers (60628 items) tests 2927 done 0 failed | 26 in flight, oldest 148s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......... [136%]
........................................................................ [139%]
.....................[contention-diag] +280s soak 36p/226t rss 9.0G pss 8.3G swap 1.0G majflt 2912 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.0G, 8 descendant rss 0.2G pss 0.2G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.52/0.44 io 11.53 cpu 12.25 | cgroup 9.2G/max oom_kill 0 | free scratch 309.3G/45149590i tmp 28.3G/997721i workspace 309.3G/45149590i | repeat-01 collected 26/26 workers (60628 items) tests 3044 done 0 failed | 26 in flight, oldest 163s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................... [143%]
........................................................................ [146%]
................................[contention-diag] +296s soak 29p/231t rss 8.8G pss 8.2G swap 1.0G majflt 2931 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 1 descendant rss 0.0G pss 0.0G | host avail 34.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.1/0.08 io 4.73 cpu 22.83 | cgroup 9.1G/max oom_kill 0 | free scratch 309.3G/45147587i tmp 28.3G/997891i workspace 309.3G/45147587i | repeat-01 collected 26/26 workers (60628 items) tests 3193 done 0 failed | 26 in flight, oldest 179s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................ [149%]
.[contention-diag] +311s soak 36p/254t rss 9.0G pss 8.3G swap 1.0G majflt 2932 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 8 descendant rss 0.1G pss 0.0G | host avail 34.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.16 cpu 24.47 | cgroup 9.2G/max oom_kill 0 | free scratch 309.3G/45147255i tmp 28.3G/997891i workspace 309.3G/45147255i | repeat-01 collected 26/26 workers (60628 items) tests 3241 done 0 failed | 26 in flight, oldest 194s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................[contention-diag] +326s soak 35p/241t rss 9.2G pss 8.5G swap 1.0G majflt 2931 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.3G, 7 descendant rss 0.2G pss 0.1G | host avail 35.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 29.01 | cgroup 9.3G/max oom_kill 0 | free scratch 309.3G/45147169i tmp 28.3G/997891i workspace 309.3G/45147169i | repeat-01 collected 26/26 workers (60628 items) tests 3256 done 0 failed | 26 in flight, oldest 209s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................... [152%]
..................[contention-diag] +342s soak 34p/250t rss 9.2G pss 8.6G swap 1.0G majflt 2933 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 34.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 24.32 | cgroup 9.4G/max oom_kill 0 | free scratch 309.3G/45146335i tmp 28.3G/997917i workspace 309.3G/45146335i | repeat-01 collected 26/26 workers (60628 items) tests 3327 done 0 failed | 26 in flight, oldest 225s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................... [156%]
........................................................................ [159%]
............................................................[contention-diag] +357s soak 34p/237t rss 9.2G pss 8.6G swap 1.0G majflt 2937 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 6 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.76 cpu 19.15 | cgroup 9.4G/max oom_kill 0 | free scratch 309.3G/45146611i tmp 28.3G/997917i workspace 309.3G/45146611i | repeat-01 collected 26/26 workers (60628 items) tests 3515 done 0 failed | 26 in flight, oldest 240s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............ [162%]
........................................................................ [166%]
..........................[contention-diag] +372s soak 34p/259t rss 9.3G pss 8.6G swap 1.0G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.5G, 6 descendant rss 0.1G pss 0.0G | host avail 34.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 14.77 | cgroup 9.5G/max oom_kill 0 | free scratch 309.3G/45146237i tmp 28.3G/997917i workspace 309.3G/45146237i | scratch used 0.4G in 79696 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 3599 done 0 failed | 26 in flight, oldest 255s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................. [169%]
....................................................[contention-diag] +389s soak 36p/260t rss 9.5G pss 8.8G swap 1.0G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 8 descendant rss 0.3G pss 0.2G | host avail 34.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.87 cpu 20.62 | cgroup 9.7G/max oom_kill 0 | free scratch 309.3G/45145894i tmp 28.3G/997917i workspace 309.3G/45145894i | repeat-01 collected 26/26 workers (60628 items) tests 3712 done 0 failed | 26 in flight, oldest 272s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................... [172%]
.....................[contention-diag] +404s soak 34p/270t rss 9.5G pss 8.8G swap 1.0G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 6 descendant rss 0.1G pss 0.1G | host avail 35.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.43 cpu 25.13 | cgroup 9.7G/max oom_kill 0 | free scratch 309.3G/45145709i tmp 28.3G/997917i workspace 309.3G/45145709i | repeat-01 collected 26/26 workers (60628 items) tests 3763 done 0 failed | 26 in flight, oldest 288s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................... [176%]
..........................................[contention-diag] +420s soak 38p/262t rss 9.5G pss 8.8G swap 1.0G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 10 descendant rss 0.1G pss 0.0G | host avail 34.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 26.78 | cgroup 9.8G/max oom_kill 0 | free scratch 309.3G/45145354i tmp 28.3G/997917i workspace 309.3G/45145354i | repeat-01 collected 26/26 workers (60628 items) tests 3856 done 0 failed | 26 in flight, oldest 303s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................. [179%]
.............................................................[contention-diag] +435s soak 41p/274t rss 9.6G pss 8.9G swap 1.0G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 13 descendant rss 0.2G pss 0.1G | host avail 34.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.14 cpu 28.3 | cgroup 9.8G/max oom_kill 0 | free scratch 309.3G/45145093i tmp 28.3G/997917i workspace 309.3G/45145093i | repeat-01 collected 26/26 workers (60628 items) tests 3946 done 0 failed | 26 in flight, oldest 318s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [182%]
........................................................................ [186%]
....[contention-diag] +450s soak 44p/297t rss 9.9G pss 9.1G swap 1.0G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 16 descendant rss 0.4G pss 0.2G | host avail 33.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 22.83 | cgroup 10.0G/max oom_kill 0 | free scratch 309.3G/45144820i tmp 28.3G/997917i workspace 309.3G/45144820i | repeat-01 collected 26/26 workers (60628 items) tests 4030 done 0 failed | 26 in flight, oldest 333s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................................... [189%]
...................................[contention-diag] +466s soak 41p/236t rss 9.8G pss 9.1G swap 1.0G majflt 2943 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 13 descendant rss 0.2G pss 0.1G | host avail 31.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 22.74 | cgroup 10.0G/max oom_kill 0 | free scratch 309.7G/45144481i tmp 28.3G/997917i workspace 309.7G/45144481i | repeat-01 collected 26/26 workers (60628 items) tests 4127 done 0 failed | 25 in flight, oldest 349s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................... [192%]
...........................................................[contention-diag] +481s soak 35p/267t rss 9.8G pss 9.1G swap 1.0G majflt 2972 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 31.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.94 cpu 25.13 | cgroup 10.0G/max oom_kill 0 | free scratch 309.7G/45144181i tmp 28.3G/997917i workspace 309.7G/45144181i | repeat-01 collected 26/26 workers (60628 items) tests 4227 done 0 failed | 26 in flight, oldest 364s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............. [196%]
................................[contention-diag] +496s soak 36p/284t rss 9.9G pss 9.2G swap 1.0G majflt 2990 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 8 descendant rss 0.2G pss 0.2G | host avail 31.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.82 cpu 23.22 | cgroup 10.1G/max oom_kill 0 | free scratch 309.7G/45143990i tmp 28.3G/997917i workspace 309.7G/45143990i | scratch used 0.5G in 95286 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 4268 done 0 failed | 26 in flight, oldest 379s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................ [199%]
........................................................................ [202%]
.......[contention-diag] +514s soak 30p/239t rss 9.8G pss 9.2G swap 1.0G majflt 2992 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.1G pss 0.1G | host avail 30.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 2.07 cpu 22.25 | cgroup 10.1G/max oom_kill 0 | free scratch 309.7G/45143529i tmp 28.3G/997917i workspace 309.7G/45143529i | repeat-01 collected 26/26 workers (60628 items) tests 4395 done 0 failed | 25 in flight, oldest 397s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................................................[contention-diag] +529s soak 28p/207t rss 9.8G pss 9.1G swap 1.0G majflt 2992 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G | host avail 29.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.23 cpu 19.47 | cgroup 10.1G/max oom_kill 0 | free scratch 309.5G/45143276i tmp 28.3G/997917i workspace 309.5G/45143276i | repeat-01 collected 26/26 workers (60628 items) tests 4454 done 0 failed | 26 in flight, oldest 41s gw3 tests/ace/tui/command_line/test_chrome_layout.py::test_popup_clamps_inside_a_narrow_frame
.......... [206%]
.[contention-diag] +544s soak 29p/246t rss 9.8G pss 9.2G swap 1.0G majflt 2993 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 32.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 2.67 cpu 21.08 | cgroup 10.1G/max oom_kill 0 | free scratch 309.2G/45143132i tmp 28.3G/997917i workspace 309.2G/45143132i | repeat-01 collected 26/26 workers (60628 items) tests 4464 done 0 failed | 26 in flight, oldest 48s gw17 tests/ace/tui/command_line/test_transcript_scroll.py::test_block_nav_scrolls_selection_into_view
..................................................[contention-diag] +560s soak 31p/252t rss 10.0G pss 9.3G swap 1.0G majflt 3016 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 3 descendant rss 0.2G pss 0.1G | host avail 32.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.45 cpu 25.56 | cgroup 10.3G/max oom_kill 0 | free scratch 309.2G/45142821i tmp 28.3G/997917i workspace 309.2G/45142821i | repeat-01 collected 26/26 workers (60628 items) tests 4510 done 0 failed | 26 in flight, oldest 61s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
..................... [209%]
..................................................[contention-diag] +575s soak 30p/244t rss 10.0G pss 9.3G swap 1.0G majflt 3015 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 2 descendant rss 0.1G pss 0.1G | host avail 33.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.15 cpu 21.69 | cgroup 10.3G/max oom_kill 0 | free scratch 309.2G/45142525i tmp 28.3G/997917i workspace 309.2G/45142525i | repeat-01 collected 26/26 workers (60628 items) tests 4581 done 0 failed | 26 in flight, oldest 76s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...................... [212%]
................................................[contention-diag] +590s soak 28p/239t rss 9.9G pss 9.2G swap 1.0G majflt 3014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 32.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 1.89 cpu 22.69 | cgroup 10.2G/max oom_kill 0 | free scratch 309.2G/45142254i tmp 28.3G/997915i workspace 309.2G/45142254i | repeat-01 collected 26/26 workers (60628 items) tests 4645 done 0 failed | 26 in flight, oldest 92s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
........................ [216%]
....[contention-diag] +606s soak 29p/232t rss 9.9G pss 9.3G swap 1.0G majflt 3014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 1 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 1.79 cpu 22.07 | cgroup 10.3G/max oom_kill 0 | free scratch 309.0G/45142050i tmp 28.3G/997917i workspace 309.0G/45142050i | repeat-01 collected 26/26 workers (60628 items) tests 4682 done 0 failed | 26 in flight, oldest 80s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
....................................................[contention-diag] +621s soak 29p/239t rss 10.0G pss 9.4G swap 1.0G majflt 3022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 28.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 1.96 cpu 22.61 | cgroup 10.3G/max oom_kill 0 | free scratch 308.7G/45141846i tmp 28.3G/997917i workspace 308.7G/45141846i | scratch used 0.6G in 108034 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 4729 done 0 failed | 26 in flight, oldest 59s gw25 tests/ace/tui/test_link_follow_entry_points.py::test_matrix_links_panel_key_path_follows_first_chip
................ [219%]
...................[contention-diag] +638s soak 29p/253t rss 10.1G pss 9.4G swap 1.0G majflt 3022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 29.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.29 cpu 20.13 | cgroup 10.5G/max oom_kill 0 | free scratch 308.5G/45141411i tmp 28.3G/997917i workspace 308.5G/45141411i | repeat-01 collected 26/26 workers (60628 items) tests 4770 done 0 failed | 26 in flight, oldest 56s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_K_warns_when_finished_and_confirms_when_running
.......................................[contention-diag] +653s soak 29p/248t rss 10.1G pss 9.4G swap 1.0G majflt 3022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G, 1 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.9 cpu 20.4 | cgroup 10.4G/max oom_kill 0 | free scratch 308.3G/45141182i tmp 28.3G/997917i workspace 308.3G/45141182i | repeat-01 collected 26/26 workers (60628 items) tests 4808 done 0 failed | 26 in flight, oldest 54s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
.............. [222%]
........[contention-diag] +669s soak 29p/266t rss 10.1G pss 9.5G swap 1.0G majflt 3022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 21.74 | cgroup 10.5G/max oom_kill 0 | free scratch 308.3G/45141021i tmp 28.3G/997917i workspace 308.3G/45141021i | repeat-01 collected 26/26 workers (60628 items) tests 4830 done 0 failed | 26 in flight, oldest 69s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
...................[contention-diag] +684s soak 29p/251t rss 10.1G pss 9.5G swap 1.0G majflt 3033 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.9 cpu 19.15 | cgroup 10.5G/max oom_kill 0 | free scratch 308.3G/45140851i tmp 28.3G/997917i workspace 308.3G/45140851i | repeat-01 collected 26/26 workers (60628 items) tests 4849 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...............................[contention-diag] +699s soak 28p/244t rss 10.1G pss 9.5G swap 1.0G majflt 3033 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G | host avail 29.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 23.0 | cgroup 10.6G/max oom_kill 0 | free scratch 308.3G/45140626i tmp 28.3G/997917i workspace 308.3G/45140626i | repeat-01 collected 26/26 workers (60628 items) tests 4882 done 0 failed | 26 in flight, oldest 66s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_picker_acts_on_focused_split_panel
.............[contention-diag] +714s soak 28p/236t rss 10.2G pss 9.5G swap 0.9G majflt 3034 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 29.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.02 cpu 23.48 | cgroup 10.7G/max oom_kill 0 | free scratch 308.3G/45140477i tmp 28.3G/997917i workspace 308.3G/45140477i | repeat-01 collected 26/26 workers (60628 items) tests 4893 done 0 failed | 26 in flight, oldest 47s gw8 tests/ace/tui/test_artifacts_split_modes.py::test_patch_list_content_width_obeys_split_cap
. [226%]
..............................[contention-diag] +730s soak 29p/248t rss 10.2G pss 9.6G swap 0.9G majflt 3035 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 28.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 1.12 cpu 24.45 | cgroup 10.6G/max oom_kill 0 | free scratch 308.3G/45140334i tmp 28.3G/997917i workspace 308.3G/45140334i | repeat-01 collected 26/26 workers (60628 items) tests 4918 done 0 failed | 26 in flight, oldest 58s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
.......................................... [229%]
..............................................[contention-diag] +745s soak 30p/228t rss 10.3G pss 9.7G swap 1.0G majflt 3067 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 2 descendant rss 0.1G pss 0.1G | host avail 26.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.83 cpu 21.63 | cgroup 10.7G/max oom_kill 0 | free scratch 308.3G/45140051i tmp 28.3G/997917i workspace 308.3G/45140051i | scratch used 0.7G in 120669 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 4990 done 0 failed | 26 in flight, oldest 56s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_panel_action_override_takes_effect_in_mounted_pilot
.......................... [232%]
........................................................................ [236%]
............................................................[contention-diag] +762s soak 28p/219t rss 10.3G pss 9.6G swap 0.9G majflt 3035 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 27.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.23 cpu 18.98 | cgroup 10.8G/max oom_kill 0 | free scratch 307.9G/45139521i tmp 28.3G/997917i workspace 307.9G/45139521i | repeat-01 collected 26/26 workers (60628 items) tests 5150 done 0 failed | 26 in flight, oldest 50s gw21 tests/ace/tui/test_commits_pane_filters.py::test_committed_project_key_alias_and_unknown_ref_canonicalization
............ [239%]
........................................................................ [242%]
...................................................................[contention-diag] +778s soak 28p/239t rss 10.3G pss 9.6G swap 0.9G majflt 3035 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.45 cpu 14.05 | cgroup 10.9G/max oom_kill 0 | free scratch 308.2G/45137452i tmp 28.3G/997917i workspace 308.2G/45137450i | repeat-01 collected 26/26 workers (60628 items) tests 5322 done 0 failed | 26 in flight, oldest 48s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..... [246%]
........................................................................ [249%]
.............................[contention-diag] +793s soak 29p/234t rss 10.3G pss 9.7G swap 0.9G majflt 3038 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.78 cpu 16.33 | cgroup 10.8G/max oom_kill 0 | free scratch 308.3G/45137691i tmp 28.3G/997917i workspace 308.3G/45137691i | repeat-01 collected 26/26 workers (60628 items) tests 5425 done 0 failed | 26 in flight, oldest 63s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................... [252%]
........................................................................ [256%]
.....[contention-diag] +809s soak 29p/267t rss 10.4G pss 9.8G swap 1.0G majflt 3042 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 1 descendant rss 0.1G pss 0.1G | host avail 31.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.71 cpu 12.75 | cgroup 10.9G/max oom_kill 0 | free scratch 308.0G/45110769i tmp 28.3G/997415i workspace 308.0G/45110769i | repeat-01 collected 26/26 workers (60628 items) tests 5542 done 0 failed | 26 in flight, oldest 78s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....................................[contention-diag] +824s soak 32p/261t rss 10.4G pss 9.8G swap 0.9G majflt 3046 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 4 descendant rss 0.1G pss 0.0G | host avail 33.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.78 cpu 10.96 | cgroup 11.0G/max oom_kill 0 | free scratch 308.0G/45109137i tmp 28.3G/997842i workspace 308.0G/45109137i | repeat-01 collected 26/26 workers (60628 items) tests 5584 done 0 failed | 26 in flight, oldest 94s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............................... [259%]
...................[contention-diag] +839s soak 29p/250t rss 10.4G pss 9.8G swap 0.9G majflt 3050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 34.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.28 cpu 24.56 | cgroup 10.8G/max oom_kill 0 | free scratch 308.0G/45108756i tmp 28.3G/997862i workspace 308.0G/45108756i | repeat-01 collected 26/26 workers (60628 items) tests 5633 done 0 failed | 26 in flight, oldest 109s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..............................[contention-diag] +854s soak 29p/258t rss 10.5G pss 9.8G swap 0.9G majflt 3050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 34.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.79 cpu 30.03 | cgroup 11.0G/max oom_kill 0 | free scratch 308.0G/45108524i tmp 28.3G/997863i workspace 308.0G/45108524i | repeat-01 collected 26/26 workers (60628 items) tests 5664 done 0 failed | 26 in flight, oldest 124s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....................... [262%]
........................................................................ [266%]
......[contention-diag] +870s soak 29p/255t rss 10.5G pss 9.8G swap 0.9G majflt 3050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 33.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.75 cpu 25.61 | cgroup 11.0G/max oom_kill 0 | free scratch 308.0G/45108336i tmp 28.3G/997876i workspace 308.0G/45108336i | scratch used 0.7G in 131712 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 5763 done 0 failed | 26 in flight, oldest 140s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................[contention-diag] +887s soak 31p/265t rss 10.6G pss 9.9G swap 0.9G majflt 3050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 3 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.03 cpu 17.6 | cgroup 11.0G/max oom_kill 0 | free scratch 308.0G/45108231i tmp 28.3G/997891i workspace 308.0G/45108231i | repeat-01 collected 26/26 workers (60628 items) tests 5782 done 0 failed | 26 in flight, oldest 157s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................................................. [269%]
................[contention-diag] +902s soak 31p/242t rss 10.6G pss 9.9G swap 0.9G majflt 3050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 3 descendant rss 0.1G pss 0.0G | host avail 32.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.39 cpu 14.08 | cgroup 11.1G/max oom_kill 0 | free scratch 308.0G/45108008i tmp 28.3G/997891i workspace 308.0G/45108008i | repeat-01 collected 26/26 workers (60628 items) tests 5846 done 0 failed | 26 in flight, oldest 55s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
........................................................ [272%]
........................................................................ [276%]
........................................................................ [279%]
..................[contention-diag] +918s soak 29p/244t rss 10.7G pss 10.0G swap 1.0G majflt 3051 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G, 1 descendant rss 0.1G pss 0.1G | host avail 32.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.87 cpu 20.6 | cgroup 11.1G/max oom_kill 0 | free scratch 308.0G/45107449i tmp 28.3G/997891i workspace 308.0G/45107449i | repeat-01 collected 26/26 workers (60628 items) tests 6037 done 0 failed | 25 in flight, oldest 70s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
...................................................... [282%]
........................................................................ [286%]
............................................................[contention-diag] +933s soak 28p/212t rss 10.6G pss 10.0G swap 0.9G majflt 3059 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G | host avail 34.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.29 cpu 25.75 | cgroup 11.1G/max oom_kill 0 | free scratch 308.0G/45106872i tmp 28.3G/997891i workspace 308.0G/45106872i | repeat-01 collected 26/26 workers (60628 items) tests 6241 done 0 failed | 26 in flight, oldest 46s gw24 tests/ace/tui/test_config_center_resume.py::test_persisted_tab_seeds_home_and_repeated_opener_resume
............ [289%]
........................................................................ [292%]
.....................................................[contention-diag] +948s soak 28p/233t rss 10.6G pss 10.0G swap 0.9G majflt 3063 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 33.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.27 cpu 25.56 | cgroup 11.1G/max oom_kill 0 | free scratch 308.0G/45106443i tmp 28.3G/997891i workspace 308.0G/45106443i | repeat-01 collected 26/26 workers (60628 items) tests 6386 done 0 failed | 26 in flight, oldest 54s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................... [295%]
...................[contention-diag] +964s soak 29p/235t rss 10.7G pss 10.0G swap 0.9G majflt 3063 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 32.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.2 cpu 23.41 | cgroup 11.2G/max oom_kill 0 | free scratch 308.0G/45106249i tmp 28.3G/997891i workspace 308.0G/45106249i | repeat-01 collected 26/26 workers (60628 items) tests 6426 done 0 failed | 25 in flight, oldest 70s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
..................................................... [299%]
................[contention-diag] +979s soak 28p/209t rss 10.7G pss 10.0G swap 0.9G majflt 3063 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G | host avail 33.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.32 cpu 26.31 | cgroup 11.2G/max oom_kill 0 | free scratch 308.0G/45105968i tmp 28.3G/997891i workspace 308.0G/45105968i | repeat-01 collected 26/26 workers (60628 items) tests 6487 done 0 failed | 26 in flight, oldest 56s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
........................................................ [302%]
........................................................................ [305%]
........................................[contention-diag] +994s soak 28p/221t rss 10.7G pss 10.1G swap 0.9G majflt 3104 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G | host avail 33.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 27.8 | cgroup 11.2G/max oom_kill 0 | free scratch 308.0G/45105529i tmp 28.3G/997891i workspace 308.0G/45105529i | scratch used 0.8G in 142136 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 6647 done 0 failed | 26 in flight, oldest 70s gw0 tests/ace/tui/test_plan_decision_ace_render_rail.py::test_compact_verdict_stays_inside_rail_with_stylesheet
................................ [309%]
..........................................................[contention-diag] +1012s soak 29p/226t rss 10.8G pss 10.1G swap 0.9G majflt 3111 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.1G pss 0.0G | host avail 33.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.86 cpu 28.62 | cgroup 11.3G/max oom_kill 0 | free scratch 308.0G/45105119i tmp 28.3G/997891i workspace 308.0G/45105119i | repeat-01 collected 26/26 workers (60628 items) tests 6754 done 0 failed | 26 in flight, oldest 56s gw15 tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_scroll_keys_move_detail_not_selection
.............. [312%]
...................[contention-diag] +1027s soak 30p/223t rss 10.9G pss 10.2G swap 1.0G majflt 3111 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.15/0.07 io 0.44 cpu 25.17 | cgroup 11.4G/max oom_kill 0 | free scratch 308.0G/45104945i tmp 28.3G/997891i workspace 308.0G/45104945i | repeat-01 collected 26/26 workers (60628 items) tests 6787 done 0 failed | 26 in flight, oldest 49s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
..................................................... [315%]
................................................................[contention-diag] +1042s soak 28p/229t rss 10.8G pss 10.2G swap 0.9G majflt 3113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G | host avail 33.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 0.41 cpu 27.55 | cgroup 11.3G/max oom_kill 0 | free scratch 308.0G/45104613i tmp 28.3G/997891i workspace 308.0G/45104613i | repeat-01 collected 26/26 workers (60628 items) tests 6901 done 0 failed | 26 in flight, oldest 65s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........ [319%]
........................................................................ [322%]
................................................................[contention-diag] +1058s soak 31p/219t rss 10.9G pss 10.2G swap 0.9G majflt 3113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 3 descendant rss 0.1G pss 0.1G | host avail 32.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 26.14 | cgroup 11.4G/max oom_kill 0 | free scratch 308.0G/45104141i tmp 28.3G/997891i workspace 308.0G/45104141i | repeat-01 collected 26/26 workers (60628 items) tests 7046 done 0 failed | 25 in flight, oldest 43s gw4 tests/ace/tui/test_artifacts_files_loading.py::test_hydrate_ref_reports_absent_for_unknown_logical_id
........ [325%]
................................[contention-diag] +1073s soak 30p/215t rss 11.0G pss 10.3G swap 0.9G majflt 3113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.1/0.09 io 0.58 cpu 26.49 | cgroup 11.4G/max oom_kill 0 | free scratch 308.0G/45103932i tmp 28.3G/997891i workspace 308.0G/45103932i | repeat-01 collected 26/26 workers (60628 items) tests 7086 done 0 failed | 26 in flight, oldest 38s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
........................................ [329%]
.......................................................[contention-diag] +1088s soak 29p/239t rss 10.9G pss 10.3G swap 1.0G majflt 3113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 32.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.46 cpu 20.98 | cgroup 11.4G/max oom_kill 0 | free scratch 308.0G/45103630i tmp 28.3G/997891i workspace 308.0G/45103630i | repeat-01 collected 26/26 workers (60628 items) tests 7175 done 0 failed | 26 in flight, oldest 54s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................. [332%]
.......................................................................[contention-diag] +1104s soak 29p/231t rss 11.0G pss 10.3G swap 1.0G majflt 3115 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G, 1 descendant rss 0.1G pss 0.0G | host avail 31.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 19.83 | cgroup 11.5G/max oom_kill 0 | free scratch 308.0G/45103272i tmp 28.3G/997891i workspace 308.0G/45103272i | repeat-01 collected 26/26 workers (60628 items) tests 7266 done 0 failed | 26 in flight, oldest 69s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
. [335%]
........................................................................ [339%]
........................................................................ [342%]
........................................................................ [345%]
........................................................................ [349%]
..............[contention-diag] +1119s soak 28p/215t rss 10.9G pss 10.2G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G | host avail 32.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 0.24 cpu 19.78 | cgroup 11.4G/max oom_kill 0 | free scratch 308.0G/45102649i tmp 28.3G/997891i workspace 308.0G/45102649i | scratch used 0.8G in 150922 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 7511 done 0 failed | 26 in flight, oldest 69s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
.......................................................... [352%]
........................................................................ [355%]
..[contention-diag] +1136s soak 38p/244t rss 11.1G pss 10.3G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 32.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.59 cpu 25.11 | cgroup 11.5G/max oom_kill 0 | free scratch 308.0G/45102074i tmp 28.3G/997891i workspace 308.0G/45102074i | repeat-01 collected 26/26 workers (60628 items) tests 7706 done 0 failed | 26 in flight, oldest 44s gw12 tests/ace/tui/test_artifacts_plans_interactions.py::test_plans_pane_navigates_three_document_sections
......[contention-diag] +1151s soak 38p/265t rss 11.1G pss 10.3G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.51 cpu 28.03 | cgroup 11.6G/max oom_kill 0 | free scratch 308.0G/45101982i tmp 28.3G/997891i workspace 308.0G/45101982i | repeat-01 collected 26/26 workers (60628 items) tests 7712 done 0 failed | 26 in flight, oldest 55s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.........[contention-diag] +1167s soak 39p/282t rss 11.1G pss 10.3G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 11 descendant rss 0.1G pss 0.0G | host avail 30.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.58 cpu 22.45 | cgroup 11.6G/max oom_kill 0 | free scratch 308.4G/45105612i tmp 28.3G/997891i workspace 308.4G/45105612i | repeat-01 collected 26/26 workers (60628 items) tests 7721 done 0 failed | 26 in flight, oldest 70s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.....................[contention-diag] +1182s soak 38p/275t rss 11.1G pss 10.3G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 30.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.47 cpu 17.49 | cgroup 11.6G/max oom_kill 0 | free scratch 308.4G/45105379i tmp 28.3G/997891i workspace 308.4G/45105379i | repeat-01 collected 26/26 workers (60628 items) tests 7742 done 0 failed | 26 in flight, oldest 85s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.............[contention-diag] +1198s soak 38p/269t rss 11.1G pss 10.4G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 29.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.62/0.62 io 1.27 cpu 17.49 | cgroup 11.6G/max oom_kill 0 | free scratch 308.4G/45105113i tmp 28.3G/997891i workspace 308.4G/45105113i | repeat-01 collected 26/26 workers (60628 items) tests 7749 done 0 failed | 26 in flight, oldest 101s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
..................... [359%]
...[contention-diag] +1213s soak 39p/256t rss 11.2G pss 10.4G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.2G, 11 descendant rss 0.1G pss 0.1G | host avail 30.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 1.74 cpu 17.94 | cgroup 11.7G/max oom_kill 0 | free scratch 308.4G/45104894i tmp 28.3G/997891i workspace 308.4G/45104894i | repeat-01 collected 26/26 workers (60628 items) tests 7777 done 0 failed | 26 in flight, oldest 55s gw18 tests/ace/tui/modals/test_saved_query_picker.py::test_picker_follows_active_query_pane_and_digits_switch_artifacts
................................[contention-diag] +1228s soak 38p/244t rss 11.2G pss 10.4G swap 0.9G majflt 3114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 29.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.0 cpu 19.31 | cgroup 11.7G/max oom_kill 0 | free scratch 308.4G/45104693i tmp 28.3G/997891i workspace 308.4G/45104693i | repeat-01 collected 26/26 workers (60628 items) tests 7806 done 0 failed | 26 in flight, oldest 67s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
..................................... [362%]
........................................................................ [365%]
.......................[contention-diag] +1244s soak 38p/257t rss 11.2G pss 10.4G swap 0.9G majflt 3122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 29.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 19.9 | cgroup 11.7G/max oom_kill 0 | free scratch 308.4G/45104243i tmp 28.3G/997891i workspace 308.4G/45104243i | scratch used 0.9G in 158966 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 7912 done 0 failed | 26 in flight, oldest 82s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
................................................. [369%]
........................................................................ [372%]
..........[contention-diag] +1261s soak 28p/248t rss 11.1G pss 10.4G swap 0.9G majflt 3137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 30.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.02 cpu 18.57 | cgroup 11.7G/max oom_kill 0 | free scratch 315.2G/45207388i tmp 28.3G/997892i workspace 315.2G/45207388i | repeat-01 collected 26/26 workers (60628 items) tests 8071 done 0 failed | 26 in flight, oldest 60s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_space_dispatches_repeat_agent_from_every_subtab
..............[contention-diag] +1276s soak 28p/238t rss 11.1G pss 10.4G swap 0.9G majflt 3137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 31.3G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.98 cpu 18.45 | cgroup 11.7G/max oom_kill 0 | free scratch 314.8G/45203837i tmp 28.3G/997892i workspace 314.8G/45203837i | repeat-01 collected 26/26 workers (60628 items) tests 8088 done 0 failed | 26 in flight, oldest 71s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
..........................[contention-diag] +1292s soak 29p/243t rss 11.1G pss 10.4G swap 0.9G majflt 3137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.44/0.44 io 2.79 cpu 16.19 | cgroup 11.7G/max oom_kill 0 | free scratch 314.8G/45203496i tmp 28.3G/997892i workspace 314.8G/45203496i | repeat-01 collected 26/26 workers (60628 items) tests 8106 done 0 failed | 25 in flight, oldest 59s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_after_tools_returns_to_main_then_tools
...................... [375%]
........................................................................ [379%]
.............................................[contention-diag] +1307s soak 28p/249t rss 11.1G pss 10.4G swap 0.9G majflt 3140 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.3G | host avail 32.2G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 4.17 cpu 24.94 | cgroup 11.8G/max oom_kill 0 | free scratch 314.8G/45203165i tmp 28.3G/997892i workspace 314.8G/45203165i | repeat-01 collected 26/26 workers (60628 items) tests 8252 done 0 failed | 26 in flight, oldest 62s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
........................... [382%]
........................................................................ [385%]
...........[contention-diag] +1322s soak 28p/229t rss 11.2G pss 10.5G swap 0.9G majflt 3140 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 33.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 3.66 cpu 26.42 | cgroup 11.8G/max oom_kill 0 | free scratch 314.8G/45202825i tmp 28.3G/997892i workspace 314.8G/45202825i | repeat-01 collected 26/26 workers (60628 items) tests 8357 done 0 failed | 26 in flight, oldest 77s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
............................................................. [389%]
........................................................................ [392%]
........................[contention-diag] +1338s soak 31p/251t rss 11.2G pss 10.5G swap 0.9G majflt 3154 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 3 descendant rss 0.1G pss 0.0G | host avail 32.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.3 cpu 23.11 | cgroup 11.8G/max oom_kill 0 | free scratch 314.8G/45202414i tmp 28.3G/997892i workspace 314.8G/45202414i | repeat-01 collected 26/26 workers (60628 items) tests 8516 done 0 failed | 26 in flight, oldest 75s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................................ [395%]
........................................................................ [399%]
........................................................................ [402%]
............[contention-diag] +1353s soak 28p/255t rss 11.2G pss 10.5G swap 0.9G majflt 3223 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 32.5G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.97 cpu 23.0 | cgroup 11.8G/max oom_kill 0 | free scratch 314.8G/45201893i tmp 28.3G/997892i workspace 314.8G/45201893i | repeat-01 collected 26/26 workers (60628 items) tests 8719 done 0 failed | 26 in flight, oldest 91s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................................ [405%]
........................................................................ [409%]
....................................[contention-diag] +1368s soak 28p/237t rss 11.2G pss 10.5G swap 0.9G majflt 3224 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.4G | host avail 33.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.9 cpu 29.82 | cgroup 11.8G/max oom_kill 0 | free scratch 314.8G/45201422i tmp 28.3G/997892i workspace 314.8G/45201422i | scratch used 0.9G in 162047 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 8876 done 0 failed | 26 in flight, oldest 106s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................... [412%]
.........................[contention-diag] +1385s soak 28p/247t rss 11.3G pss 10.5G swap 0.9G majflt 3230 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 33.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.85 cpu 30.21 | cgroup 11.9G/max oom_kill 0 | free scratch 314.8G/45201163i tmp 28.3G/997892i workspace 314.8G/45201163i | repeat-01 collected 26/26 workers (60628 items) tests 8940 done 0 failed | 26 in flight, oldest 123s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................... [415%]
........................................................................ [419%]
.....[contention-diag] +1401s soak 28p/247t rss 11.3G pss 10.6G swap 0.9G majflt 3234 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 33.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.54 cpu 28.09 | cgroup 11.9G/max oom_kill 0 | free scratch 314.8G/45200801i tmp 28.3G/997892i workspace 314.8G/45200801i | repeat-01 collected 26/26 workers (60628 items) tests 9073 done 0 failed | 26 in flight, oldest 139s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................................................... [422%]
.............[contention-diag] +1416s soak 29p/249t rss 11.3G pss 10.6G swap 0.9G majflt 3234 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 35.9G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.74 cpu 25.2 | cgroup 12.0G/max oom_kill 0 | free scratch 314.8G/45200586i tmp 28.3G/997892i workspace 314.8G/45200586i | repeat-01 collected 26/26 workers (60628 items) tests 9155 done 0 failed | 26 in flight, oldest 154s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..................................[contention-diag] +1431s soak 29p/236t rss 11.4G pss 10.7G swap 0.9G majflt 3237 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 35.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.28 cpu 32.95 | cgroup 12.0G/max oom_kill 0 | free scratch 314.8G/45200392i tmp 28.3G/997892i workspace 314.8G/45200392i | repeat-01 collected 26/26 workers (60628 items) tests 9189 done 0 failed | 26 in flight, oldest 169s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
....................[contention-diag] +1447s soak 28p/248t rss 11.4G pss 10.7G swap 0.9G majflt 3244 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 35.2G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.62 cpu 31.56 | cgroup 12.0G/max oom_kill 0 | free scratch 314.8G/45200267i tmp 28.3G/997892i workspace 314.8G/45200267i | repeat-01 collected 26/26 workers (60628 items) tests 9211 done 0 failed | 26 in flight, oldest 93s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..... [425%]
...............................................................[contention-diag] +1462s soak 28p/262t rss 11.4G pss 10.7G swap 0.9G majflt 3244 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 33.5G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.04 cpu 23.91 | cgroup 12.0G/max oom_kill 0 | free scratch 314.8G/45200021i tmp 28.3G/997892i workspace 314.8G/45200021i | repeat-01 collected 26/26 workers (60628 items) tests 9277 done 0 failed | 26 in flight, oldest 109s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
......... [429%]
.....................................................................[contention-diag] +1478s soak 29p/231t rss 11.4G pss 10.7G swap 0.9G majflt 3250 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.53 cpu 21.99 | cgroup 12.1G/max oom_kill 0 | free scratch 314.8G/45199584i tmp 28.3G/997892i workspace 314.8G/45199584i | repeat-01 collected 26/26 workers (60628 items) tests 9355 done 0 failed | 26 in flight, oldest 124s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
... [432%]
.........................................[contention-diag] +1493s soak 28p/255t rss 11.4G pss 10.7G swap 0.9G majflt 3250 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 34.9G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.55 cpu 29.02 | cgroup 12.1G/max oom_kill 0 | free scratch 314.8G/45199531i tmp 28.3G/997892i workspace 314.8G/45199531i | scratch used 0.9G in 169232 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 9400 done 0 failed | 26 in flight, oldest 139s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................... [435%]
......................................................[contention-diag] +1510s soak 29p/237t rss 11.4G pss 10.7G swap 0.9G majflt 3251 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 34.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.64 cpu 33.18 | cgroup 12.1G/max oom_kill 0 | free scratch 314.8G/45199244i tmp 28.3G/997892i workspace 314.8G/45199244i | repeat-01 collected 26/26 workers (60628 items) tests 9481 done 0 failed | 25 in flight, oldest 157s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................. [438%]
....................[contention-diag] +1526s soak 28p/237t rss 11.4G pss 10.7G swap 0.9G majflt 3276 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.6G | host avail 33.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.21 cpu 26.48 | cgroup 12.1G/max oom_kill 0 | free scratch 314.8G/45199017i tmp 28.3G/997892i workspace 314.8G/45199017i | repeat-01 collected 26/26 workers (60628 items) tests 9524 done 0 failed | 26 in flight, oldest 57s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...............[contention-diag] +1541s soak 28p/235t rss 11.5G pss 10.7G swap 0.9G majflt 3283 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 34.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.33 cpu 24.57 | cgroup 12.1G/max oom_kill 0 | free scratch 314.8G/45198827i tmp 28.3G/997892i workspace 314.8G/45198827i | repeat-01 collected 26/26 workers (60628 items) tests 9539 done 0 failed | 26 in flight, oldest 72s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................... [442%]
........................................................................ [445%]
.......[contention-diag] +1556s soak 29p/250t rss 11.5G pss 10.8G swap 0.9G majflt 3288 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 33.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.39 cpu 24.72 | cgroup 12.2G/max oom_kill 0 | free scratch 314.8G/45198481i tmp 28.3G/997892i workspace 314.8G/45198481i | repeat-01 collected 26/26 workers (60628 items) tests 9653 done 0 failed | 25 in flight, oldest 87s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................................. [448%]
........................................................................ [452%]
...........................................[contention-diag] +1571s soak 28p/266t rss 11.5G pss 10.8G swap 0.9G majflt 3291 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 32.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.44 cpu 20.54 | cgroup 12.2G/max oom_kill 0 | free scratch 314.8G/45197947i tmp 28.3G/997892i workspace 314.8G/45197947i | repeat-01 collected 26/26 workers (60628 items) tests 9829 done 0 failed | 26 in flight, oldest 103s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................. [455%]
............................................[contention-diag] +1587s soak 29p/232t rss 11.5G pss 10.8G swap 0.9G majflt 3294 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 33.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.76 cpu 17.73 | cgroup 12.2G/max oom_kill 0 | free scratch 314.8G/45197719i tmp 28.3G/997892i workspace 314.8G/45197719i | repeat-01 collected 26/26 workers (60628 items) tests 9907 done 0 failed | 26 in flight, oldest 118s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................ [458%]
........................................................................ [462%]
....................[contention-diag] +1602s soak 28p/226t rss 11.5G pss 10.8G swap 0.9G majflt 3294 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 32.3G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.59/0.59 io 6.62 cpu 15.89 | cgroup 12.2G/max oom_kill 0 | free scratch 314.8G/45197365i tmp 28.3G/997890i workspace 314.8G/45197365i | repeat-01 collected 26/26 workers (60628 items) tests 10023 done 0 failed | 26 in flight, oldest 133s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..........................[contention-diag] +1617s soak 29p/265t rss 11.5G pss 10.8G swap 0.9G majflt 3304 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 5.0 cpu 18.18 | cgroup 12.2G/max oom_kill 0 | free scratch 314.8G/45197116i tmp 28.3G/997893i workspace 314.8G/45197116i | scratch used 0.2G in 32390 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 10051 done 0 failed | 26 in flight, oldest 148s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................... [465%]
........................................................[contention-diag] +1635s soak 29p/258t rss 11.6G pss 10.9G swap 0.9G majflt 3321 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 32.3G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 8.89 cpu 22.26 | cgroup 12.3G/max oom_kill 0 | free scratch 314.8G/45196812i tmp 28.3G/997893i workspace 314.8G/45196812i | repeat-01 collected 26/26 workers (60628 items) tests 10135 done 0 failed | 26 in flight, oldest 166s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [468%]
........................................................[contention-diag] +1650s soak 30p/256t rss 11.6G pss 10.9G swap 0.9G majflt 4209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 32.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 13.67 cpu 17.24 | cgroup 12.3G/max oom_kill 0 | free scratch 314.8G/45196485i tmp 28.3G/997893i workspace 314.8G/45196485i | repeat-01 collected 26/26 workers (60628 items) tests 10200 done 0 failed | 26 in flight, oldest 181s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [472%]
....................................................[contention-diag] +1665s soak 29p/255t rss 11.6G pss 10.9G swap 0.9G majflt 3352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 31.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 25.1 cpu 13.87 | cgroup 12.3G/max oom_kill 0 | free scratch 314.8G/45196282i tmp 28.3G/997892i workspace 314.8G/45196282i | repeat-01 collected 26/26 workers (60628 items) tests 10274 done 0 failed | 26 in flight, oldest 196s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................... [475%]
........................................................................ [478%]
..........................[contention-diag] +1681s soak 29p/251t rss 11.7G pss 10.9G swap 0.9G majflt 3352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.1G pss 0.0G | host avail 30.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 24.14 cpu 14.07 | cgroup 12.4G/max oom_kill 0 | free scratch 314.8G/45195956i tmp 28.3G/997893i workspace 314.8G/45195956i | repeat-01 collected 26/26 workers (60628 items) tests 10386 done 0 failed | 26 in flight, oldest 212s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................. [482%]
........................................................................ [485%]
....................................[contention-diag] +1696s soak 28p/253t rss 11.6G pss 10.9G swap 0.9G majflt 3352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 32.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 18.33 cpu 15.45 | cgroup 12.4G/max oom_kill 0 | free scratch 314.8G/45195390i tmp 28.3G/997893i workspace 314.8G/45195390i | repeat-01 collected 26/26 workers (60628 items) tests 10547 done 0 failed | 26 in flight, oldest 227s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................[contention-diag] +1711s soak 30p/266t rss 11.7G pss 10.9G swap 0.9G majflt 3352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.8 cpu 14.7 | cgroup 12.4G/max oom_kill 0 | free scratch 314.8G/45195305i tmp 28.3G/997890i workspace 314.8G/45195305i | repeat-01 collected 26/26 workers (60628 items) tests 10578 done 0 failed | 26 in flight, oldest 243s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.... [488%]
..............................................[contention-diag] +1727s soak 29p/261t rss 11.6G pss 10.9G swap 0.9G majflt 3352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 10.09 cpu 13.95 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45269286i tmp 28.3G/997890i workspace 319.4G/45269286i | repeat-01 collected 26/26 workers (60628 items) tests 10628 done 0 failed | 26 in flight, oldest 258s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................... [492%]
............[contention-diag] +1742s soak 29p/268t rss 11.7G pss 10.9G swap 0.9G majflt 3352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.2/0.2 io 7.14 cpu 14.43 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45269124i tmp 28.3G/997890i workspace 319.4G/45269124i | scratch used 0.2G in 24656 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 10664 done 0 failed | 26 in flight, oldest 273s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................................ [495%]
................................................................[contention-diag] +1759s soak 28p/255t rss 11.7G pss 10.9G swap 0.9G majflt 3358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G | host avail 32.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.17/0.14 io 6.26 cpu 16.06 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45268443i tmp 28.3G/997890i workspace 319.4G/45268443i | repeat-01 collected 26/26 workers (60628 items) tests 10781 done 0 failed | 26 in flight, oldest 290s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........ [498%]
........................................................................ [502%]
....[contention-diag] +1775s soak 28p/258t rss 11.7G pss 10.9G swap 0.9G majflt 3369 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G | host avail 32.3G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 6.9 cpu 16.77 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45268350i tmp 28.3G/997890i workspace 319.4G/45268350i | repeat-01 collected 26/26 workers (60628 items) tests 10871 done 0 failed | 26 in flight, oldest 306s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................................... [505%]
........................................................................ [508%]
............................[contention-diag] +1790s soak 31p/278t rss 11.7G pss 11.0G swap 0.9G majflt 3393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.19 cpu 17.86 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45267787i tmp 28.3G/997889i workspace 319.4G/45267787i | repeat-01 collected 26/26 workers (60628 items) tests 11040 done 0 failed | 26 in flight, oldest 321s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..........................[contention-diag] +1805s soak 31p/293t rss 11.7G pss 11.0G swap 0.8G majflt 3411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.31 cpu 21.14 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45267470i tmp 28.3G/997890i workspace 319.4G/45267470i | repeat-01 collected 26/26 workers (60628 items) tests 11069 done 0 failed | 26 in flight, oldest 55s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.................. [512%]
..............[contention-diag] +1820s soak 31p/294t rss 11.8G pss 11.0G swap 0.8G majflt 3412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 33.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.78 cpu 24.03 | cgroup 12.6G/max oom_kill 0 | free scratch 319.4G/45267338i tmp 28.3G/997890i workspace 319.4G/45267338i | repeat-01 collected 26/26 workers (60628 items) tests 11099 done 0 failed | 26 in flight, oldest 70s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.......................................................... [515%]
.......................................................[contention-diag] +1836s soak 32p/272t rss 11.8G pss 11.0G swap 0.8G majflt 3411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 4 descendant rss 0.1G pss 0.0G | host avail 31.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.58 cpu 23.36 | cgroup 12.6G/max oom_kill 0 | free scratch 319.4G/45266956i tmp 28.3G/997890i workspace 319.4G/45266956i | repeat-01 collected 26/26 workers (60628 items) tests 11188 done 0 failed | 26 in flight, oldest 85s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
................. [518%]
........................................................................ [522%]
......................[contention-diag] +1851s soak 30p/266t rss 11.8G pss 11.0G swap 0.8G majflt 3411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 32.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.1 cpu 19.15 | cgroup 12.6G/max oom_kill 0 | free scratch 319.4G/45266697i tmp 28.3G/997890i workspace 319.4G/45266697i | repeat-01 collected 26/26 workers (60628 items) tests 11325 done 0 failed | 26 in flight, oldest 51s gw15 tests/ace/tui/test_statistics_pane_view_navigation.py::test_every_view_selection_path_keeps_heading_tab_rail_and_view_aligned
.................................................. [525%]
..................................[contention-diag] +1866s soak 31p/270t rss 11.8G pss 11.0G swap 0.8G majflt 3411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.1G pss 0.0G | host avail 30.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.18 cpu 23.2 | cgroup 12.6G/max oom_kill 0 | free scratch 319.4G/45266440i tmp 28.3G/997890i workspace 319.4G/45266440i | scratch used 0.4G in 72911 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 11387 done 0 failed | 26 in flight, oldest 42s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
...................................... [528%]
........................................................................ [532%]
..................[contention-diag] +1884s soak 28p/257t rss 11.8G pss 11.0G swap 0.8G majflt 3413 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G | host avail 31.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.21 cpu 23.4 | cgroup 12.6G/max oom_kill 0 | free scratch 319.4G/45265873i tmp 28.3G/997890i workspace 319.4G/45265873i | repeat-01 collected 26/26 workers (60628 items) tests 11530 done 0 failed | 26 in flight, oldest 57s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
...................................................... [535%]
......................................[contention-diag] +1899s soak 29p/249t rss 11.8G pss 11.1G swap 0.8G majflt 3415 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.62 cpu 19.53 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45265407i tmp 28.3G/997890i workspace 319.4G/45265407i | repeat-01 collected 26/26 workers (60628 items) tests 11626 done 0 failed | 25 in flight, oldest 50s gw8 tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_mutation_completion_while_covered_starts_no_catalog_load
.................................. [538%]
.............................[contention-diag] +1914s soak 29p/252t rss 11.9G pss 11.1G swap 0.8G majflt 3415 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 32.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 8.18 cpu 22.62 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45265232i tmp 28.3G/997889i workspace 319.4G/45265232i | repeat-01 collected 26/26 workers (60628 items) tests 11690 done 0 failed | 26 in flight, oldest 40s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_preview_back_retains_sparse_draft_and_running_primary_restarts
...............................[contention-diag] +1930s soak 30p/278t rss 11.9G pss 11.1G swap 0.9G majflt 3415 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 32.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 9.73 cpu 26.26 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45265066i tmp 28.3G/997890i workspace 319.4G/45265066i | repeat-01 collected 26/26 workers (60628 items) tests 11724 done 0 failed | 26 in flight, oldest 56s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_preview_back_retains_sparse_draft_and_running_primary_restarts
............ [542%]
................[contention-diag] +1945s soak 31p/252t rss 11.9G pss 11.2G swap 0.9G majflt 3416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 3 descendant rss 0.1G pss 0.1G | host avail 32.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 9.16 cpu 25.25 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45264934i tmp 28.3G/997890i workspace 319.4G/45264934i | repeat-01 collected 26/26 workers (60628 items) tests 11749 done 0 failed | 26 in flight, oldest 67s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
........................................................ [545%]
.....................[contention-diag] +1960s soak 30p/262t rss 11.9G pss 11.1G swap 0.8G majflt 3415 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.51 cpu 20.68 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45264682i tmp 28.3G/997890i workspace 319.4G/45264682i | repeat-01 collected 26/26 workers (60628 items) tests 11824 done 0 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
................................................... [548%]
............[contention-diag] +1976s soak 30p/273t rss 11.9G pss 11.2G swap 0.8G majflt 3417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 2 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.04 cpu 22.56 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45264439i tmp 28.3G/997890i workspace 319.4G/45264439i | repeat-01 collected 26/26 workers (60628 items) tests 11892 done 0 failed | 26 in flight, oldest 48s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_stages_declared_inputs_into_frontmatter
............................................................ [552%]
........................................................................ [555%]
..[contention-diag] +1991s soak 28p/236t rss 11.9G pss 11.1G swap 0.8G majflt 3417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G | host avail 31.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.57 cpu 22.2 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45264120i tmp 28.3G/997890i workspace 319.4G/45264120i | scratch used 1.0G in 178621 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 12002 done 0 failed | 26 in flight, oldest 62s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
...................................................[contention-diag] +2008s soak 30p/250t rss 11.9G pss 11.2G swap 0.8G majflt 3418 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 30.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.24/0.12 io 5.33 cpu 21.97 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45263766i tmp 28.3G/997890i workspace 319.4G/45263766i | repeat-01 collected 26/26 workers (60628 items) tests 12076 done 0 failed | 26 in flight, oldest 78s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................... [558%]
........................................................................ [562%]
........................................................................ [565%]
.........[contention-diag] +2024s soak 29p/258t rss 11.9G pss 11.2G swap 0.8G majflt 3417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.04/0.02 io 6.31 cpu 23.41 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45263083i tmp 28.3G/997890i workspace 319.4G/45263083i | repeat-01 collected 26/26 workers (60628 items) tests 12247 done 0 failed | 26 in flight, oldest 93s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
............................................................... [568%]
..............[contention-diag] +2039s soak 29p/248t rss 11.9G pss 11.2G swap 0.9G majflt 3422 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 1 descendant rss 0.1G pss 0.0G | host avail 34.3G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.5 cpu 22.51 | cgroup 12.4G/max oom_kill 0 | free scratch 319.4G/45262867i tmp 28.3G/997890i workspace 319.4G/45262867i | repeat-01 collected 26/26 workers (60628 items) tests 12325 done 0 failed | 26 in flight, oldest 52s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_digit_owns_hidden_member_jump_state[None]
.......................................................... [572%]
........................................................................ [575%]
........................................................................ [578%]
............................[contention-diag] +2054s soak 33p/254t rss 12.0G pss 11.2G swap 0.8G majflt 3437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 5 descendant rss 0.1G pss 0.0G | host avail 34.5G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.73 cpu 23.07 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45262448i tmp 28.3G/997890i workspace 319.4G/45262448i | repeat-01 collected 26/26 workers (60628 items) tests 12555 done 0 failed | 26 in flight, oldest 59s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
............................................ [581%]
........................................................................ [585%]
........................................................................ [588%]
...................................[contention-diag] +2070s soak 31p/260t rss 11.9G pss 11.2G swap 0.8G majflt 3430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.58 cpu 25.46 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45261948i tmp 28.3G/997890i workspace 319.4G/45261948i | repeat-01 collected 26/26 workers (60628 items) tests 12772 done 0 failed | 25 in flight, oldest 61s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree
..................................... [591%]
........................................................................ [595%]
........................................................................ [598%]
....[contention-diag] +2085s soak 31p/258t rss 12.0G pss 11.2G swap 0.8G majflt 3445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.43 cpu 23.92 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45261400i tmp 28.3G/997890i workspace 319.4G/45261400i | repeat-01 collected 26/26 workers (60628 items) tests 12962 done 0 failed | 26 in flight, oldest 47s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hint_line_switches_to_jump_variant
.................................................................... [601%]
........................................................................ [605%]
.......[contention-diag] +2100s soak 33p/268t rss 12.0G pss 11.2G swap 0.8G majflt 3445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 5 descendant rss 0.0G pss 0.0G | host avail 33.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.14 cpu 21.0 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45260946i tmp 28.3G/997890i workspace 319.4G/45260946i | repeat-01 collected 26/26 workers (60628 items) tests 13101 done 0 failed | 26 in flight, oldest 45s gw6 tests/ace/tui/test_macro_browser_filter.py::test_slash_reveals_filter_without_changing_selection
................................................................. [608%]
........................................................................ [611%]
...............................[contention-diag] +2116s soak 29p/244t rss 12.0G pss 11.2G swap 0.8G majflt 3445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 33.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.68 cpu 22.56 | cgroup 12.5G/max oom_kill 0 | free scratch 319.4G/45260598i tmp 28.3G/997890i workspace 319.4G/45260598i | scratch used 1.0G in 182369 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 13257 done 0 failed | 26 in flight, oldest 49s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
......................................... [615%]
............[contention-diag] +2133s soak 30p/246t rss 12.0G pss 11.2G swap 0.8G majflt 3452 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 32.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.34 cpu 22.52 | cgroup 12.5G/max oom_kill 0 | free scratch 319.3G/45260185i tmp 28.3G/997890i workspace 319.3G/45260185i | repeat-01 collected 26/26 workers (60628 items) tests 13326 done 0 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
............................................................ [618%]
.................................[contention-diag] +2148s soak 30p/248t rss 12.0G pss 11.2G swap 0.8G majflt 3459 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 32.6G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.28 cpu 22.41 | cgroup 12.5G/max oom_kill 0 | free scratch 319.3G/45259525i tmp 28.3G/997888i workspace 319.3G/45259525i | repeat-01 collected 26/26 workers (60628 items) tests 13422 done 0 failed | 26 in flight, oldest 47s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
....................................... [621%]
.............................................................[contention-diag] +2164s soak 30p/251t rss 12.1G pss 11.3G swap 0.8G majflt 3921 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 2 descendant rss 0.1G pss 0.1G | host avail 33.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.03 cpu 25.35 | cgroup 12.6G/max oom_kill 0 | free scratch 319.3G/45259541i tmp 28.3G/997890i workspace 319.3G/45259541i | repeat-01 collected 26/26 workers (60628 items) tests 13523 done 0 failed | 26 in flight, oldest 62s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
........... [625%]
........................................................................ [628%]
...............[contention-diag] +2179s soak 32p/265t rss 12.2G pss 11.4G swap 0.8G majflt 6054 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 4 descendant rss 0.1G pss 0.1G | host avail 33.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.8 cpu 24.45 | cgroup 12.8G/max oom_kill 0 | free scratch 319.3G/45259130i tmp 28.3G/997890i workspace 319.3G/45259130i | repeat-01 collected 26/26 workers (60628 items) tests 13614 done 0 failed | 26 in flight, oldest 77s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
......................................................... [631%]
...................................................[contention-diag] +2194s soak 33p/294t rss 12.2G pss 11.4G swap 0.8G majflt 3504 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.06 io 8.19 cpu 22.49 | cgroup 12.9G/max oom_kill 0 | free scratch 319.3G/45258614i tmp 28.3G/997890i workspace 319.3G/45258614i | repeat-01 collected 26/26 workers (60628 items) tests 13723 done 0 failed | 26 in flight, oldest 92s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
..................... [635%]
..............................................................[contention-diag] +2210s soak 29p/275t rss 12.1G pss 11.4G swap 0.8G majflt 3706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 1 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.21/0.2 io 8.55 cpu 19.38 | cgroup 13.0G/max oom_kill 0 | free scratch 319.3G/45258211i tmp 28.3G/997888i workspace 319.3G/45258211i | repeat-01 collected 26/26 workers (60628 items) tests 13803 done 0 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
.......... [638%]
........................................................................ [641%]
........................................................................ [645%]
................................................................[contention-diag] +2225s soak 30p/279t rss 12.2G pss 11.4G swap 0.8G majflt 3485 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G, 2 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.04 io 8.0 cpu 23.31 | cgroup 13.2G/max oom_kill 0 | free scratch 319.3G/45257589i tmp 28.3G/997890i workspace 319.3G/45257589i | repeat-01 collected 26/26 workers (60628 items) tests 14027 done 0 failed | 26 in flight, oldest 76s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
........ [648%]
........................................................................ [651%]
........................................................................ [655%]
........................................[contention-diag] +2240s soak 28p/248t rss 12.1G pss 11.3G swap 0.8G majflt 3488 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G | host avail 33.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.33/0.33 io 11.61 cpu 24.05 | cgroup 13.2G/max oom_kill 0 | free scratch 319.3G/45257054i tmp 28.3G/997890i workspace 319.3G/45257054i | scratch used 0.6G in 117153 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 14177 done 0 failed | 25 in flight, oldest 47s gw9 tests/ace/tui/test_projects_pane.py::test_projects_filter_yields_tab_to_admin_center
................................ [658%]
........................................................................ [661%]
...................[contention-diag] +2258s soak 29p/273t rss 12.2G pss 11.4G swap 0.8G majflt 3493 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 1 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 7.78 cpu 21.84 | cgroup 13.2G/max oom_kill 0 | free scratch 319.3G/45256542i tmp 28.3G/997890i workspace 319.3G/45256542i | repeat-01 collected 26/26 workers (60628 items) tests 14341 done 0 failed | 26 in flight, oldest 60s gw6 tests/ace/tui/test_macro_browser_filter.py::test_cached_reactivation_restores_open_filter_or_list
..................................................... [665%]
............................[contention-diag] +2273s soak 28p/270t rss 12.1G pss 11.4G swap 0.8G majflt 3494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G | host avail 33.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 7.73 cpu 23.54 | cgroup 13.2G/max oom_kill 0 | free scratch 319.3G/45256014i tmp 28.3G/997890i workspace 319.3G/45256014i | repeat-01 collected 26/26 workers (60628 items) tests 14425 done 0 failed | 26 in flight, oldest 49s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
............................................ [668%]
........[contention-diag] +2288s soak 35p/263t rss 12.3G pss 11.3G swap 0.8G majflt 3496 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 7 descendant rss 0.1G pss 0.1G | host avail 32.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.14 cpu 24.13 | cgroup 13.2G/max oom_kill 0 | free scratch 319.3G/45255914i tmp 28.3G/997890i workspace 319.3G/45255914i | repeat-01 collected 26/26 workers (60628 items) tests 14473 done 0 failed | 26 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
................................................................ [671%]
.................................................[contention-diag] +2304s soak 35p/257t rss 12.2G pss 11.4G swap 0.8G majflt 3517 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 7 descendant rss 0.0G pss 0.0G | host avail 32.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 7.0 cpu 22.86 | cgroup 13.3G/max oom_kill 0 | free scratch 319.3G/45254891i tmp 28.3G/997890i workspace 319.3G/45254891i | repeat-01 collected 26/26 workers (60628 items) tests 14577 done 0 failed | 26 in flight, oldest 80s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
....................... [675%]
........................................................................ [678%]
........................................................................ [681%]
...........[contention-diag] +2319s soak 29p/258t rss 12.2G pss 11.4G swap 0.8G majflt 3531 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 1 descendant rss 0.0G pss 0.0G | host avail 32.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 7.1 cpu 20.33 | cgroup 13.3G/max oom_kill 0 | free scratch 319.3G/45254653i tmp 28.3G/997890i workspace 319.3G/45254653i | repeat-01 collected 26/26 workers (60628 items) tests 14745 done 0 failed | 25 in flight, oldest 79s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
............................................................. [685%]
........................................................................ [688%]
.................[contention-diag] +2334s soak 31p/260t rss 12.3G pss 11.5G swap 0.8G majflt 3544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 2.0/2.0 io 11.66 cpu 17.72 | cgroup 13.3G/max oom_kill 0 | free scratch 319.3G/45254080i tmp 28.3G/997890i workspace 319.3G/45254080i | repeat-01 collected 26/26 workers (60628 items) tests 14913 done 0 failed | 25 in flight, oldest 46s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_opens_edit_modal
....................................................... [691%]
........................................................................ [695%]
......................[contention-diag] +2350s soak 37p/265t rss 12.3G pss 11.5G swap 0.7G majflt 3559 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 9 descendant rss 0.1G pss 0.0G | host avail 32.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 1.05/1.05 io 10.19 cpu 18.59 | cgroup 13.3G/max oom_kill 0 | free scratch 319.3G/45252953i tmp 28.3G/997890i workspace 319.3G/45252953i | repeat-01 collected 26/26 workers (60628 items) tests 15066 done 0 failed | 26 in flight, oldest 45s gw23 tests/ace/tui/test_notification_jump_to_agent_reveal.py::test_real_app_notification_jump_expands_collapsed_clan
.................................................. [698%]
........................................................................ [701%]
..............................................................[contention-diag] +2365s soak 34p/258t rss 12.4G pss 11.6G swap 0.7G majflt 3563 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 6 descendant rss 0.2G pss 0.1G | host avail 32.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.25/0.25 io 11.41 cpu 23.79 | cgroup 13.4G/max oom_kill 0 | free scratch 319.3G/45252103i tmp 28.3G/997889i workspace 319.3G/45252104i | scratch used 1.0G in 190797 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 15221 done 0 failed | 25 in flight, oldest 59s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
.......... [705%]
........................................................................ [708%]
........................................................................ [711%]
..............................[contention-diag] +2382s soak 33p/254t rss 12.4G pss 11.6G swap 0.8G majflt 3567 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 5 descendant rss 0.2G pss 0.1G | host avail 32.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 10.74 cpu 23.09 | cgroup 13.5G/max oom_kill 0 | free scratch 319.3G/45251100i tmp 28.3G/997890i workspace 319.3G/45251100i | repeat-01 collected 26/26 workers (60628 items) tests 15437 done 0 failed | 26 in flight, oldest 62s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
.......................................... [715%]
........................................................................ [718%]
.............................[contention-diag] +2398s soak 33p/254t rss 12.4G pss 11.6G swap 0.7G majflt 3569 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 5 descendant rss 0.1G pss 0.0G | host avail 32.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.27 cpu 24.06 | cgroup 13.4G/max oom_kill 0 | free scratch 319.3G/45250371i tmp 28.3G/997890i workspace 319.3G/45250371i | repeat-01 collected 26/26 workers (60628 items) tests 15579 done 0 failed | 26 in flight, oldest 72s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................... [721%]
..........................[contention-diag] +2413s soak 34p/274t rss 12.5G pss 11.6G swap 0.7G majflt 3577 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 6 descendant rss 0.1G pss 0.1G | host avail 32.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.23 cpu 24.08 | cgroup 13.5G/max oom_kill 0 | free scratch 319.3G/45249782i tmp 28.3G/997890i workspace 319.3G/45249782i | repeat-01 collected 26/26 workers (60628 items) tests 15649 done 0 failed | 26 in flight, oldest 87s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.............................................. [724%]
........................................................................ [728%]
.........[contention-diag] +2428s soak 32p/269t rss 12.4G pss 11.6G swap 0.8G majflt 3577 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 4 descendant rss 0.1G pss 0.0G | host avail 31.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.02 cpu 22.83 | cgroup 13.5G/max oom_kill 0 | free scratch 319.3G/45248898i tmp 28.3G/997890i workspace 319.3G/45248898i | repeat-01 collected 26/26 workers (60628 items) tests 15760 done 0 failed | 26 in flight, oldest 102s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............................................................... [731%]
........................................................................ [734%]
........................................................................ [738%]
........................................................................ [741%]
........[contention-diag] +2444s soak 31p/254t rss 12.4G pss 11.6G swap 0.7G majflt 3627 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 3 descendant rss 0.1G pss 0.1G | host avail 30.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.39/0.39 io 9.71 cpu 21.79 | cgroup 13.6G/max oom_kill 0 | free scratch 319.3G/45248270i tmp 28.3G/997890i workspace 319.3G/45248270i | repeat-01 collected 26/26 workers (60628 items) tests 16041 done 0 failed | 25 in flight, oldest 118s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................................ [744%]
........................................................................ [748%]
........................................................................ [751%]
........................................................................ [754%]
........................................................................ [758%]
........................................................................ [761%]
.[contention-diag] +2459s soak 35p/241t rss 12.5G pss 11.7G swap 0.8G majflt 3639 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 7 descendant rss 0.2G pss 0.1G | host avail 31.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 11.62 cpu 21.34 | cgroup 13.6G/max oom_kill 0 | free scratch 319.3G/45246860i tmp 28.3G/997890i workspace 319.3G/45246860i | repeat-01 collected 26/26 workers (60628 items) tests 16481 done 0 failed | 26 in flight, oldest 133s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
....................................................................... [764%]
........................................................................ [768%]
..............................................[contention-diag] +2474s soak 33p/259t rss 12.4G pss 11.6G swap 0.7G majflt 3641 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.4G, 5 descendant rss 0.1G pss 0.0G | host avail 31.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 9.27 cpu 20.39 | cgroup 13.6G/max oom_kill 0 | free scratch 319.3G/45246183i tmp 28.3G/997890i workspace 319.3G/45246183i | repeat-01 collected 26/26 workers (60628 items) tests 16671 done 0 failed | 26 in flight, oldest 148s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.......................... [771%]
........................................................................ [774%]
........................................................................ [778%]
.....................[contention-diag] +2490s soak 34p/263t rss 12.6G pss 11.7G swap 0.7G majflt 3649 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 6 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 10.1 cpu 21.43 | cgroup 13.7G/max oom_kill 0 | free scratch 319.3G/45245209i tmp 28.3G/997890i workspace 319.3G/45245209i | scratch used 1.1G in 197824 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 16862 done 0 failed | 26 in flight, oldest 164s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................... [781%]
........................................................................ [784%]
........................................................................ [788%]
........................................................................ [791%]
..[contention-diag] +2507s soak 34p/276t rss 12.5G pss 11.7G swap 0.7G majflt 3651 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 6 descendant rss 0.1G pss 0.1G | host avail 31.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 11.39 cpu 22.11 | cgroup 13.8G/max oom_kill 0 | free scratch 319.3G/45244749i tmp 28.3G/997890i workspace 319.3G/45244749i | repeat-01 collected 26/26 workers (60628 items) tests 17130 done 0 failed | 26 in flight, oldest 181s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................................................................... [794%]
........................................................................ [798%]
............................................[contention-diag] +2522s soak 33p/273t rss 12.6G pss 11.8G swap 0.7G majflt 3664 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 5 descendant rss 0.1G pss 0.1G | host avail 31.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.49 cpu 21.3 | cgroup 13.7G/max oom_kill 0 | free scratch 319.3G/45245834i tmp 28.3G/997890i workspace 319.3G/45245834i | repeat-01 collected 26/26 workers (60628 items) tests 17316 done 0 failed | 26 in flight, oldest 124s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
............................ [801%]
........................................................................ [804%]
........................................................................ [808%]
........................................................................ [811%]
........................................................................ [814%]
........[contention-diag] +2538s soak 32p/221t rss 12.5G pss 11.7G swap 0.7G majflt 3686 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.03 cpu 22.63 | cgroup 13.7G/max oom_kill 0 | free scratch 319.3G/45245071i tmp 28.3G/997890i workspace 319.3G/45245071i | repeat-01 collected 26/26 workers (60628 items) tests 17638 done 0 failed | 25 in flight, oldest 51s gw9 tests/ace/tui/test_projects_pane.py::test_inventory_escape_clears_project_before_closing_admin_center
................................................................ [818%]
........................................................................ [821%]
..............[contention-diag] +2553s soak 32p/231t rss 12.5G pss 11.7G swap 0.7G majflt 3697 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 4 descendant rss 0.1G pss 0.0G | host avail 32.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.7 cpu 25.19 | cgroup 13.7G/max oom_kill 0 | free scratch 319.3G/45244806i tmp 28.3G/997890i workspace 319.3G/45244806i | repeat-01 collected 26/26 workers (60628 items) tests 17790 done 0 failed | 26 in flight, oldest 43s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.......................................................... [824%]
....................................................................[contention-diag] +2568s soak 32p/253t rss 12.5G pss 11.7G swap 0.7G majflt 3698 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.26/0.26 io 7.58 cpu 20.89 | cgroup 13.7G/max oom_kill 0 | free scratch 319.3G/45244308i tmp 28.3G/997890i workspace 319.3G/45244308i | repeat-01 collected 26/26 workers (60628 items) tests 17921 done 0 failed | 26 in flight, oldest 58s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.... [828%]
........................................................................ [831%]
........................................................................ [834%]
........................[contention-diag] +2584s soak 35p/261t rss 12.5G pss 11.7G swap 0.7G majflt 3699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 7 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 7.8 cpu 24.14 | cgroup 13.7G/max oom_kill 0 | free scratch 319.3G/45244233i tmp 28.3G/997890i workspace 319.3G/45244233i | repeat-01 collected 26/26 workers (60628 items) tests 18087 done 0 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................................................ [838%]
........................................................................ [841%]
...............................[contention-diag] +2599s soak 31p/245t rss 12.6G pss 11.8G swap 0.7G majflt 3703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 3 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 7.51 cpu 21.06 | cgroup 13.8G/max oom_kill 0 | free scratch 319.3G/45243667i tmp 28.3G/997891i workspace 319.3G/45243667i | repeat-01 collected 26/26 workers (60628 items) tests 18242 done 0 failed | 26 in flight, oldest 89s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
......................................... [844%]
........................................................................ [848%]
........................................................................ [851%]
...........[contention-diag] +2614s soak 39p/250t rss 12.6G pss 11.7G swap 0.7G majflt 3705 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 11 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.74 cpu 21.45 | cgroup 13.8G/max oom_kill 0 | free scratch 319.3G/45243413i tmp 28.3G/997891i workspace 319.3G/45243413i | scratch used 1.1G in 199305 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 18390 done 0 failed | 25 in flight, oldest 104s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................................. [854%]
........................................................................ [858%]
........................................................................ [861%]
........................................................................ [864%]
........................................................................ [867%]
...[contention-diag] +2632s soak 32p/230t rss 12.6G pss 11.7G swap 0.7G majflt 3709 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 13.05 cpu 25.96 | cgroup 13.7G/max oom_kill 0 | free scratch 319.2G/45241764i tmp 28.3G/997891i workspace 319.2G/45241764i | repeat-01 collected 26/26 workers (60628 items) tests 18786 done 0 failed | 26 in flight, oldest 41s gw8 tests/ace/tui/test_usage_header.py::test_pilot_clicks_open_usage_without_expanding_header
..................................................................... [871%]
......................................................[contention-diag] +2647s soak 40p/254t rss 12.6G pss 11.8G swap 0.7G majflt 3720 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 12 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.15 cpu 26.43 | cgroup 13.8G/max oom_kill 0 | free scratch 319.2G/45241186i tmp 28.3G/997891i workspace 319.2G/45241186i | repeat-01 collected 26/26 workers (60628 items) tests 18914 done 0 failed | 26 in flight, oldest 47s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_agents_tab
.................. [874%]
........................................................................ [877%]
.......................................[contention-diag] +2662s soak 34p/241t rss 12.6G pss 11.8G swap 0.7G majflt 3723 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 6 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.18 cpu 24.39 | cgroup 13.8G/max oom_kill 0 | free scratch 319.2G/45240579i tmp 28.3G/997891i workspace 319.2G/45240579i | repeat-01 collected 26/26 workers (60628 items) tests 19044 done 0 failed | 26 in flight, oldest 48s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
................................. [881%]
........................................................................ [884%]
........................................................................ [887%]
..........s............................................................. [891%]
...................[contention-diag] +2678s soak 33p/246t rss 12.6G pss 11.8G swap 0.7G majflt 3729 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 33.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.12 cpu 20.35 | cgroup 13.8G/max oom_kill 0 | free scratch 319.2G/45240470i tmp 28.3G/997891i workspace 319.2G/45240470i | repeat-01 collected 26/26 workers (60628 items) tests 19295 done 0 failed | 26 in flight, oldest 63s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
..................................................... [894%]
........................................................................ [897%]
...........................................s..s......................... [901%]
........................................................................ [904%]
.............................[contention-diag] +2693s soak 32p/254t rss 12.6G pss 11.8G swap 0.7G majflt 3747 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 4 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.8 cpu 20.44 | cgroup 13.8G/max oom_kill 0 | free scratch 319.2G/45239795i tmp 28.3G/997891i workspace 319.2G/45239795i | repeat-01 collected 26/26 workers (60628 items) tests 19603 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................................... [907%]
........................................................................ [911%]
........................................................................ [914%]
................................................[contention-diag] +2708s soak 34p/269t rss 12.7G pss 11.8G swap 0.7G majflt 3776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 6 descendant rss 0.1G pss 0.0G | host avail 33.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.12 cpu 23.06 | cgroup 13.9G/max oom_kill 0 | free scratch 319.2G/45239102i tmp 28.3G/997891i workspace 319.2G/45239102i | repeat-01 collected 26/26 workers (60628 items) tests 19839 done 0 failed | 26 in flight, oldest 84s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................ [917%]
........................................................................ [921%]
........................................................................ [924%]
........................................................................ [927%]
...................................[contention-diag] +2724s soak 32p/255t rss 12.7G pss 11.8G swap 0.7G majflt 3777 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 4 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.62 cpu 22.04 | cgroup 13.9G/max oom_kill 0 | free scratch 319.2G/45238360i tmp 28.3G/997891i workspace 319.2G/45238360i | repeat-01 collected 26/26 workers (60628 items) tests 20121 done 0 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
..................................... [931%]
........................................................................ [934%]
........................................................................ [937%]
.................................[contention-diag] +2739s soak 38p/278t rss 12.8G pss 11.9G swap 0.7G majflt 3781 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 10 descendant rss 0.1G pss 0.1G | host avail 33.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.39 cpu 22.12 | cgroup 13.9G/max oom_kill 0 | free scratch 319.2G/45237579i tmp 28.3G/997891i workspace 319.2G/45237579i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 20290 done 0 failed | 26 in flight, oldest 114s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
....................................... [941%]
........................................................................ [944%]
................................[contention-diag] +2756s soak 33p/267t rss 12.8G pss 11.9G swap 0.7G majflt 3787 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 5 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 12.95 cpu 22.2 | cgroup 13.9G/max oom_kill 0 | free scratch 319.2G/45236960i tmp 28.3G/997891i workspace 319.2G/45236960i | repeat-01 collected 26/26 workers (60628 items) tests 20477 done 0 failed | 26 in flight, oldest 68s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
........................................ [947%]
........................................................................ [951%]
..........................................[contention-diag] +2772s soak 36p/277t rss 12.9G pss 12.0G swap 0.7G majflt 3794 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 8 descendant rss 0.2G pss 0.1G | host avail 33.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.81 cpu 26.05 | cgroup 14.0G/max oom_kill 0 | free scratch 319.2G/45236571i tmp 28.3G/997891i workspace 319.2G/45236571i | repeat-01 collected 26/26 workers (60628 items) tests 20631 done 0 failed | 26 in flight, oldest 61s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
.............................. [954%]
........................................................................ [957%]
........................................................................ [961%]
........................................................................ [964%]
..................................................[contention-diag] +2787s soak 34p/275t rss 12.8G pss 11.9G swap 0.7G majflt 3807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 13.65 cpu 25.18 | cgroup 13.9G/max oom_kill 0 | free scratch 319.2G/45235358i tmp 28.3G/997891i workspace 319.2G/45235358i | repeat-01 collected 26/26 workers (60628 items) tests 20917 done 0 failed | 26 in flight, oldest 60s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
...................... [967%]
........................................................................ [971%]
........................................................................ [974%]
........................................................................ [977%]
........................................................................ [981%]
........................................................................ [984%]
........[contention-diag] +2802s soak 33p/256t rss 12.7G pss 11.8G swap 0.7G majflt 3807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 5 descendant rss 0.1G pss 0.0G | host avail 33.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.02 cpu 22.66 | cgroup 13.9G/max oom_kill 0 | free scratch 319.2G/45234470i tmp 28.3G/997891i workspace 319.2G/45234470i | repeat-01 collected 26/26 workers (60628 items) tests 21312 done 0 failed | 25 in flight, oldest 38s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
.......................s........................................ [987%]
................................................................[contention-diag] +2818s soak 37p/242t rss 12.8G pss 11.9G swap 0.7G majflt 3807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 9 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.54 cpu 22.39 | cgroup 14.0G/max oom_kill 0 | free scratch 319.2G/45232810i tmp 28.3G/997891i workspace 319.2G/45232810i | repeat-01 collected 26/26 workers (60628 items) tests 21442 done 0 failed | 26 in flight, oldest 54s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
........ [991%]
........................................................................ [994%]
......................................................................[contention-diag] +2833s soak 43p/245t rss 13.0G pss 12.0G swap 0.7G majflt 3807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 15 descendant rss 0.3G pss 0.2G | host avail 33.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.14 cpu 23.95 | cgroup 14.1G/max oom_kill 0 | free scratch 319.2G/45233293i tmp 28.3G/997891i workspace 319.2G/45233293i | repeat-01 collected 26/26 workers (60628 items) tests 21593 done 0 failed | 26 in flight, oldest 46s gw9 tests/ace/tui/test_projects_pane.py::test_show_new_project_key_clears_filter
.. [997%]
........................................................................ [1001%]
........................................................................ [1004%]
..........................................................[contention-diag] +2849s soak 42p/222t rss 13.0G pss 12.1G swap 0.7G majflt 3808 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 14 descendant rss 0.3G pss 0.2G | host avail 32.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.68 cpu 20.49 | cgroup 14.1G/max oom_kill 0 | free scratch 319.2G/45232226i tmp 28.3G/997891i workspace 319.2G/45232226i | repeat-01 collected 26/26 workers (60628 items) tests 21799 done 0 failed | 26 in flight, oldest 53s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail
.............. [1007%]
................................................s....................... [1010%]
........................................................................ [1014%]
........................................................................ [1017%]
........................................................................ [1020%]
[contention-diag] +2864s soak 39p/224t rss 13.2G pss 12.2G swap 0.8G majflt 3808 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 11 descendant rss 0.4G pss 0.3G | host avail 31.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.29/0.14 io 9.19 cpu 21.21 | cgroup 14.2G/max oom_kill 0 | free scratch 319.2G/45231703i tmp 28.3G/997891i workspace 319.2G/45231703i | scratch used 1.1G in 199291 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 22040 done 0 failed | 26 in flight, oldest 56s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
........................................................................ [1024%]
........................................................................ [1027%]
........................................................................ [1030%]
..........[contention-diag] +2881s soak 37p/227t rss 13.1G pss 12.2G swap 0.7G majflt 3817 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 9 descendant rss 0.4G pss 0.3G | host avail 32.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.85/0.83 io 13.01 cpu 23.52 | cgroup 14.2G/max oom_kill 0 | free scratch 319.2G/45231171i tmp 28.3G/997889i workspace 319.2G/45231171i | repeat-01 collected 26/26 workers (60628 items) tests 22322 done 0 failed | 26 in flight, oldest 74s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.............................................................. [1034%]
........................................................................ [1037%]
........................................................................ [1040%]
......................................................................[contention-diag] +2897s soak 39p/204t rss 13.0G pss 12.0G swap 0.7G majflt 3828 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 11 descendant rss 0.3G pss 0.2G | host avail 32.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.17/0.16 io 11.73 cpu 21.98 | cgroup 14.1G/max oom_kill 0 | free scratch 319.2G/45230470i tmp 28.3G/997891i workspace 319.2G/45230470i | repeat-01 collected 26/26 workers (60628 items) tests 22606 done 0 failed | 26 in flight, oldest 89s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.. [1044%]
........................................................................ [1047%]
........................................................................ [1050%]
........................................................................ [1054%]
........................................................................ [1057%]
......................................................................[contention-diag] +2912s soak 37p/206t rss 13.1G pss 12.1G swap 0.7G majflt 3828 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 9 descendant rss 0.3G pss 0.2G | host avail 32.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 11.18 cpu 23.93 | cgroup 14.2G/max oom_kill 0 | free scratch 319.2G/45229683i tmp 28.3G/997891i workspace 319.2G/45229683i | repeat-01 collected 26/26 workers (60628 items) tests 22948 done 0 failed | 26 in flight, oldest 105s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.. [1060%]
........................................................................ [1064%]
........................................................................ [1067%]
........................................................................ [1070%]
........................................................................ [1074%]
...........................[contention-diag] +2927s soak 35p/181t rss 13.1G pss 12.2G swap 0.8G majflt 3837 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 7 descendant rss 0.4G pss 0.3G | host avail 31.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.14 cpu 22.08 | cgroup 14.3G/max oom_kill 0 | free scratch 319.2G/45228793i tmp 28.3G/997890i workspace 319.2G/45228793i | repeat-01 collected 26/26 workers (60628 items) tests 23262 done 0 failed | 25 in flight, oldest 120s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............................................. [1077%]
........................................................................ [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
........................................................................ [1090%]
........................................................................ [1094%]
........................................................................ [1097%]
...............................................................[contention-diag] +2943s soak 35p/182t rss 12.9G pss 12.0G swap 0.7G majflt 3848 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 7 descendant rss 0.1G pss 0.1G | host avail 32.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.34 cpu 24.64 | cgroup 14.1G/max oom_kill 0 | free scratch 319.2G/45227482i tmp 28.3G/997890i workspace 319.2G/45227482i | repeat-01 collected 26/26 workers (60628 items) tests 23781 done 0 failed | 26 in flight, oldest 48s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
......... [1100%]
........................................................................ [1104%]
........................................................................ [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
........................................................................ [1117%]
........................................................................ [1120%]
......................................[contention-diag] +2958s soak 34p/190t rss 12.9G pss 12.0G swap 0.7G majflt 3852 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.07 cpu 22.06 | cgroup 14.1G/max oom_kill 0 | free scratch 319.2G/45226083i tmp 28.3G/997888i workspace 319.2G/45226083i | repeat-01 collected 26/26 workers (60628 items) tests 24298 done 0 failed | 26 in flight, oldest 63s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.................................. [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
........................................................................ [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
................................................[contention-diag] +2974s soak 31p/174t rss 12.9G pss 12.0G swap 0.7G majflt 3854 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 3 descendant rss 0.0G pss 0.0G | host avail 32.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.54/0.36 io 8.61 cpu 22.54 | cgroup 14.1G/max oom_kill 0 | free scratch 319.2G/45225141i tmp 28.3G/997890i workspace 319.2G/45225141i | repeat-01 collected 26/26 workers (60628 items) tests 24740 done 0 failed | 26 in flight, oldest 79s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........................ [1144%]
........................................................................ [1147%]
........................................................................ [1150%]
........................................................................ [1153%]
........................................................................ [1157%]
....................................................[contention-diag] +2989s soak 42p/197t rss 13.1G pss 12.2G swap 0.7G majflt 3907 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 14 descendant rss 0.3G pss 0.2G | host avail 31.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.1/0.07 io 10.27 cpu 23.03 | cgroup 14.2G/max oom_kill 0 | free scratch 319.2G/45224100i tmp 28.3G/997890i workspace 319.2G/45224100i | scratch used 1.0G in 183892 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 25072 done 0 failed | 26 in flight, oldest 94s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.................... [1160%]
...................................................s.................... [1163%]
........................................................................ [1167%]
........................................................................ [1170%]
...............................................[contention-diag] +3006s soak 31p/171t rss 12.9G pss 12.0G swap 0.7G majflt 3864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 3 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 11.12 cpu 24.48 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45223086i tmp 28.3G/997890i workspace 319.1G/45223086i | repeat-01 collected 26/26 workers (60628 items) tests 25383 done 0 failed | 26 in flight, oldest 112s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
......................... [1173%]
........................................................................ [1177%]
..................................................................[contention-diag] +3022s soak 33p/186t rss 12.9G pss 12.0G swap 0.6G majflt 3870 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 5 descendant rss 0.1G pss 0.0G | host avail 31.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.56 cpu 25.11 | cgroup 14.2G/max oom_kill 0 | free scratch 319.2G/45222516i tmp 28.3G/997890i workspace 319.2G/45222516i | repeat-01 collected 26/26 workers (60628 items) tests 25550 done 0 failed | 26 in flight, oldest 127s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
...... [1180%]
........................................................................ [1183%]
.....................................................[contention-diag] +3037s soak 35p/177t rss 12.9G pss 12.0G swap 0.6G majflt 3873 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 31.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.34 cpu 22.37 | cgroup 14.2G/max oom_kill 0 | free scratch 319.2G/45222025i tmp 28.3G/997890i workspace 319.2G/45222025i | repeat-01 collected 26/26 workers (60628 items) tests 25679 done 0 failed | 26 in flight, oldest 142s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................... [1187%]
........................................................................ [1190%]
........................................................................ [1193%]
........................................................................ [1197%]
........................................................................ [1200%]
..[contention-diag] +3052s soak 33p/167t rss 12.9G pss 12.0G swap 0.6G majflt 3877 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 5 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 9.63 cpu 22.68 | cgroup 14.2G/max oom_kill 0 | free scratch 319.1G/45221452i tmp 28.3G/997890i workspace 319.1G/45221452i | repeat-01 collected 26/26 workers (60628 items) tests 25981 done 0 failed | 26 in flight, oldest 158s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...................................................................... [1203%]
........................................................................ [1207%]
........................................................................ [1210%]
........................................................................ [1213%]
........................................................................ [1217%]
...........................................[contention-diag] +3068s soak 32p/168t rss 12.9G pss 12.0G swap 0.6G majflt 3877 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 4 descendant rss 0.1G pss 0.0G | host avail 31.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 10.36 cpu 23.34 | cgroup 14.2G/max oom_kill 0 | free scratch 319.1G/45220179i tmp 28.3G/997890i workspace 319.1G/45220179i | repeat-01 collected 26/26 workers (60628 items) tests 26388 done 0 failed | 25 in flight, oldest 173s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
............................. [1220%]
........................................................................ [1223%]
........................................................................ [1227%]
.....................................................[contention-diag] +3083s soak 38p/169t rss 13.0G pss 12.1G swap 0.6G majflt 3878 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 10 descendant rss 0.1G pss 0.1G | host avail 30.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.79 cpu 22.4 | cgroup 14.3G/max oom_kill 0 | free scratch 319.1G/45219370i tmp 28.3G/997888i workspace 319.1G/45219370i | repeat-01 collected 26/26 workers (60628 items) tests 26610 done 0 failed | 26 in flight, oldest 188s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................... [1230%]
........................................................................ [1233%]
........................................................................ [1237%]
............................................[contention-diag] +3098s soak 39p/172t rss 13.2G pss 12.2G swap 0.7G majflt 3885 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 11 descendant rss 0.3G pss 0.2G | host avail 31.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.36 cpu 19.59 | cgroup 14.4G/max oom_kill 0 | free scratch 319.1G/45218546i tmp 28.3G/997890i workspace 319.1G/45218546i | repeat-01 collected 26/26 workers (60628 items) tests 26826 done 0 failed | 26 in flight, oldest 204s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
............................ [1240%]
........................................................................ [1243%]
........................................................................ [1247%]
........................................................................ [1250%]
....................................................................[contention-diag] +3114s soak 37p/177t rss 13.1G pss 12.1G swap 0.7G majflt 3885 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 9 descendant rss 0.2G pss 0.1G | host avail 32.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 1.1/0.41 io 10.19 cpu 20.95 | cgroup 14.3G/max oom_kill 0 | free scratch 319.1G/45218976i tmp 28.3G/997890i workspace 319.1G/45218976i | scratch used 1.0G in 190395 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 27124 done 0 failed | 25 in flight, oldest 219s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.... [1253%]
........................................................................ [1257%]
........................................................................ [1260%]
.........[contention-diag] +3131s soak 38p/171t rss 13.2G pss 12.2G swap 0.7G majflt 3886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 10 descendant rss 0.3G pss 0.2G | host avail 30.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.3/0.06 io 8.23 cpu 20.45 | cgroup 14.4G/max oom_kill 0 | free scratch 319.1G/45218445i tmp 28.3G/997890i workspace 319.1G/45218445i | repeat-01 collected 26/26 workers (60628 items) tests 27287 done 0 failed | 25 in flight, oldest 169s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................................... [1263%]
........................................................................ [1267%]
................................................................[contention-diag] +3146s soak 33p/162t rss 13.2G pss 12.2G swap 0.7G majflt 3888 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 5 descendant rss 0.2G pss 0.2G | host avail 30.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.73/0.08 io 9.99 cpu 21.67 | cgroup 14.2G/max oom_kill 0 | free scratch 319.1G/45217744i tmp 28.3G/997891i workspace 319.1G/45217744i | repeat-01 collected 26/26 workers (60628 items) tests 27463 done 0 failed | 23 in flight, oldest 184s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........ [1270%]
........................................................................ [1273%]
........................................................................ [1277%]
........................................................................ [1280%]
........................................................................ [1283%]
..................................[contention-diag] +3162s soak 35p/170t rss 13.1G pss 12.2G swap 0.7G majflt 3886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 7 descendant rss 0.2G pss 0.1G | host avail 31.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.49/0.01 io 9.96 cpu 22.13 | cgroup 14.2G/max oom_kill 0 | free scratch 319.1G/45216582i tmp 28.3G/997891i workspace 319.1G/45216582i | repeat-01 collected 26/26 workers (60628 items) tests 27817 done 0 failed | 25 in flight, oldest 200s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
...................................... [1287%]
........................................................................ [1290%]
........................................................................ [1293%]
........................................................................ [1296%]
...................................[contention-diag] +3177s soak 35p/172t rss 13.1G pss 12.1G swap 0.7G majflt 3888 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 7 descendant rss 0.1G pss 0.1G | host avail 31.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.69/0.0 io 8.75 cpu 20.77 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45215905i tmp 28.3G/997890i workspace 319.1G/45215905i | repeat-01 collected 26/26 workers (60628 items) tests 28091 done 0 failed | 25 in flight, oldest 215s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..................................... [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
........................................................................ [1310%]
.................................................[contention-diag] +3193s soak 36p/166t rss 13.1G pss 12.1G swap 0.7G majflt 3891 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 8 descendant rss 0.2G pss 0.1G | host avail 31.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.75/0.08 io 10.66 cpu 26.01 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45215090i tmp 28.3G/997890i workspace 319.1G/45215090i | repeat-01 collected 26/26 workers (60628 items) tests 28407 done 0 failed | 25 in flight, oldest 231s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................... [1313%]
........................................................................ [1316%]
........................................................................ [1320%]
........................................................................ [1323%]
........................................................................ [1326%]
........[contention-diag] +3208s soak 33p/177t rss 13.0G pss 12.0G swap 0.7G majflt 3894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 5 descendant rss 0.1G pss 0.1G | host avail 32.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 1.27/0.37 io 12.07 cpu 23.38 | cgroup 14.0G/max oom_kill 0 | free scratch 319.1G/45214078i tmp 28.3G/997890i workspace 319.1G/45214078i | repeat-01 collected 26/26 workers (60628 items) tests 28716 done 0 failed | 24 in flight, oldest 246s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................................ [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
........................................................................ [1340%]
..................................................................[contention-diag] +3223s soak 32p/163t rss 13.0G pss 12.1G swap 0.7G majflt 3897 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 4 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.35/0.07 io 10.8 cpu 23.01 | cgroup 14.0G/max oom_kill 0 | free scratch 319.1G/45213304i tmp 28.3G/997890i workspace 319.1G/45213304i | repeat-01 collected 26/26 workers (60628 items) tests 29077 done 0 failed | 23 in flight, oldest 179s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...... [1343%]
........................................................................ [1346%]
........................................................................ [1350%]
........................................................................ [1353%]
........................................................................ [1356%]
........................................................................ [1360%]
........................[contention-diag] +3239s soak 33p/178t rss 13.1G pss 12.1G swap 0.7G majflt 3912 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 5 descendant rss 0.2G pss 0.1G | host avail 30.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.08/0.01 io 11.52 cpu 22.26 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45212127i tmp 28.3G/997890i workspace 319.1G/45212127i | scratch used 1.0G in 185024 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 29415 done 0 failed | 25 in flight, oldest 195s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................ [1363%]
........................................................................ [1366%]
........................................................................ [1370%]
........................................................................ [1373%]
............................[contention-diag] +3256s soak 35p/173t rss 13.2G pss 12.1G swap 0.7G majflt 3917 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 7 descendant rss 0.2G pss 0.1G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.0 io 13.05 cpu 23.2 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45210449i tmp 28.3G/997890i workspace 319.1G/45210449i | repeat-01 collected 26/26 workers (60628 items) tests 29745 done 0 failed | 25 in flight, oldest 212s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................ [1376%]
........................................................................ [1380%]
........................................................................ [1383%]
........................................................................ [1386%]
........................................................................ [1390%]
..........................[contention-diag] +3272s soak 33p/165t rss 13.1G pss 12.1G swap 0.7G majflt 3923 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 5 descendant rss 0.1G pss 0.1G | host avail 30.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.18/0.0 io 10.07 cpu 20.73 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45209481i tmp 28.3G/997890i workspace 319.1G/45209481i | repeat-01 collected 26/26 workers (60628 items) tests 30100 done 0 failed | 24 in flight, oldest 228s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................................. [1393%]
........................................................................ [1396%]
........................................................................ [1400%]
........................................................................ [1403%]
..............[contention-diag] +3287s soak 38p/172t rss 13.2G pss 12.1G swap 0.7G majflt 3926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 10 descendant rss 0.2G pss 0.1G | host avail 30.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 10.86 cpu 22.15 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45209337i tmp 28.3G/997890i workspace 319.1G/45209336i | repeat-01 collected 26/26 workers (60628 items) tests 30386 done 0 failed | 25 in flight, oldest 243s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.......................................................... [1406%]
........................................................................ [1410%]
........................................................................ [1413%]
......................................................[contention-diag] +3302s soak 31p/159t rss 13.1G pss 12.1G swap 0.7G majflt 3943 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 3 descendant rss 0.1G pss 0.1G | host avail 34.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 12.71 cpu 23.08 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45208496i tmp 28.3G/997890i workspace 319.1G/45208496i | repeat-01 collected 26/26 workers (60628 items) tests 30636 done 0 failed | 25 in flight, oldest 258s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................. [1416%]
........................................................................ [1420%]
........................................................................ [1423%]
................................[contention-diag] +3318s soak 31p/161t rss 13.1G pss 12.1G swap 0.7G majflt 3954 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 3 descendant rss 0.1G pss 0.0G | host avail 34.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 13.21 cpu 21.82 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45207565i tmp 28.3G/997890i workspace 319.1G/45207565i | repeat-01 collected 26/26 workers (60628 items) tests 30847 done 0 failed | 25 in flight, oldest 274s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................ [1426%]
........................................................................ [1430%]
........................................................................ [1433%]
........................................................................ [1436%]
........................................................................ [1440%]
........................................................................ [1443%]
[contention-diag] +3333s soak 37p/179t rss 13.2G pss 12.1G swap 0.7G majflt 3961 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.2G pss 0.1G | host avail 33.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 12.15 cpu 21.26 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45207035i tmp 28.3G/997890i workspace 319.1G/45207035i | repeat-01 collected 26/26 workers (60628 items) tests 31210 done 0 failed | 25 in flight, oldest 289s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................................ [1446%]
........................................................................ [1449%]
........................................................................ [1453%]
........................................................................ [1456%]
........................................................................ [1459%]
........................................................................ [1463%]
................................[contention-diag] +3348s soak 37p/176t rss 13.2G pss 12.1G swap 0.7G majflt 3966 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 12.66 cpu 21.6 | cgroup 14.1G/max oom_kill 0 | free scratch 319.1G/45204826i tmp 28.3G/997890i workspace 319.1G/45204826i | repeat-01 collected 26/26 workers (60628 items) tests 31698 done 0 failed | 25 in flight, oldest 305s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................ [1466%]
........................................................................ [1469%]
........................................................................ [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
....................................................[contention-diag] +3364s soak 38p/174t rss 13.2G pss 12.2G swap 0.7G majflt 3971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 10 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 13.58 cpu 25.55 | cgroup 14.2G/max oom_kill 0 | free scratch 319.1G/45203851i tmp 28.3G/997890i workspace 319.1G/45203851i | scratch used 1.0G in 189913 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 31994 done 0 failed | 23 in flight, oldest 320s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................... [1483%]
........................................................................ [1486%]
........................................................................ [1489%]
........................................................................ [1493%]
........................................................................ [1496%]
........................................................................ [1499%]
.........................................................[contention-diag] +3381s soak 40p/164t rss 13.3G pss 12.2G swap 0.7G majflt 4009 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 12 descendant rss 0.2G pss 0.1G | host avail 33.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 12.9 cpu 22.41 | cgroup 14.2G/max oom_kill 0 | free scratch 319.0G/45202419i tmp 28.3G/997890i workspace 319.0G/45202419i | repeat-01 collected 26/26 workers (60628 items) tests 32519 done 0 failed | 25 in flight, oldest 278s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............... [1503%]
........................................................................ [1506%]
........................................................................ [1509%]
........................................................................ [1513%]
........................................................................ [1516%]
........................................................................ [1519%]
................................[contention-diag] +3396s soak 32p/154t rss 13.2G pss 12.1G swap 0.7G majflt 4018 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 32.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 11.69 cpu 21.71 | cgroup 14.1G/max oom_kill 0 | free scratch 319.0G/45202364i tmp 28.3G/997890i workspace 319.0G/45202364i | repeat-01 collected 26/26 workers (60628 items) tests 32901 done 0 failed | 24 in flight, oldest 293s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................................ [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1533%]
................................................................[contention-diag] +3412s soak 33p/170t rss 13.3G pss 12.2G swap 0.7G majflt 4023 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 31.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.61 cpu 20.27 | cgroup 14.2G/max oom_kill 0 | free scratch 319.0G/45201151i tmp 28.3G/997890i workspace 319.0G/45201151i | repeat-01 collected 26/26 workers (60628 items) tests 33247 done 0 failed | 24 in flight, oldest 309s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........ [1536%]
........................................................................ [1539%]
........................................................................ [1543%]
........................................................................ [1546%]
........................................................................ [1549%]
........................[contention-diag] +3427s soak 37p/176t rss 13.4G pss 12.2G swap 0.7G majflt 4028 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 9 descendant rss 0.3G pss 0.1G | host avail 30.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.25 cpu 21.61 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45200016i tmp 28.3G/997890i workspace 319.0G/45200016i | repeat-01 collected 26/26 workers (60628 items) tests 33572 done 0 failed | 24 in flight, oldest 324s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................................................ [1553%]
........................................................................ [1556%]
........................................................................ [1559%]
.[contention-diag] +3442s soak 39p/177t rss 13.4G pss 12.2G swap 0.7G majflt 4118 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 11 descendant rss 0.3G pss 0.1G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 12.23 cpu 21.41 | cgroup 14.4G/max oom_kill 0 | free scratch 319.0G/45199934i tmp 28.3G/997890i workspace 319.0G/45199934i | repeat-01 collected 26/26 workers (60628 items) tests 33762 done 0 failed | 24 in flight, oldest 340s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
....................................................................... [1563%]
.......................................................[contention-diag] +3458s soak 40p/184t rss 13.5G pss 12.4G swap 0.7G majflt 4122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 12 descendant rss 0.4G pss 0.3G | host avail 30.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 12.72 cpu 19.69 | cgroup 14.4G/max oom_kill 0 | free scratch 319.0G/45199455i tmp 28.3G/997890i workspace 319.0G/45199455i | repeat-01 collected 26/26 workers (60628 items) tests 33891 done 0 failed | 24 in flight, oldest 355s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................. [1566%]
........................................................................ [1569%]
........................................................................ [1573%]
........................s............................................... [1576%]
........................................................................ [1579%]
.......................[contention-diag] +3473s soak 36p/173t rss 13.5G pss 12.4G swap 0.8G majflt 4123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 8 descendant rss 0.4G pss 0.3G | host avail 32.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.65 cpu 20.36 | cgroup 14.5G/max oom_kill 0 | free scratch 319.0G/45198487i tmp 28.3G/997890i workspace 319.0G/45198487i | repeat-01 collected 26/26 workers (60628 items) tests 34219 done 0 failed | 23 in flight, oldest 370s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................................................. [1583%]
........................................................................ [1586%]
........................................................................ [1589%]
.................................................[contention-diag] +3489s soak 34p/172t rss 13.4G pss 12.3G swap 0.7G majflt 4124 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 6 descendant rss 0.3G pss 0.2G | host avail 32.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.37 cpu 23.58 | cgroup 14.6G/max oom_kill 0 | free scratch 319.0G/45198240i tmp 28.3G/997890i workspace 319.0G/45198240i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 34421 done 0 failed | 24 in flight, oldest 386s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
....................... [1592%]
........................................................................ [1596%]
........................................................................ [1599%]
........................................................................ [1602%]
........................................................................ [1606%]
........................................................................ [1609%]
............[contention-diag] +3506s soak 33p/161t rss 13.3G pss 12.2G swap 0.7G majflt 4123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 5 descendant rss 0.1G pss 0.1G | host avail 32.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 14.83 cpu 24.84 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45197290i tmp 28.3G/997890i workspace 319.0G/45197290i | repeat-01 collected 26/26 workers (60628 items) tests 34834 done 0 failed | 23 in flight, oldest 403s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
............................................................ [1612%]
........................................................................ [1616%]
........................................................................ [1619%]
........................................................................ [1622%]
........................................................................ [1626%]
......................[contention-diag] +3521s soak 33p/162t rss 13.3G pss 12.2G swap 0.7G majflt 4228 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 5 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.37/0.18 io 12.48 cpu 21.52 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45196248i tmp 28.3G/997888i workspace 319.0G/45196248i | repeat-01 collected 26/26 workers (60628 items) tests 35210 done 0 failed | 24 in flight, oldest 418s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
.................................................. [1629%]
........................................................................ [1632%]
........................................................................ [1636%]
.................................[contention-diag] +3537s soak 32p/171t rss 13.3G pss 12.2G swap 0.7G majflt 4525 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 4 descendant rss 0.1G pss 0.0G | host avail 32.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 1.27/0.03 io 9.31 cpu 20.75 | cgroup 14.2G/max oom_kill 0 | free scratch 319.0G/45195416i tmp 28.3G/997890i workspace 319.0G/45195416i | repeat-01 collected 26/26 workers (60628 items) tests 35452 done 0 failed | 23 in flight, oldest 434s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
....................................... [1639%]
........................................................................ [1642%]
........................................................................ [1646%]
........................................................................ [1649%]
........................................................................ [1652%]
..........................................................[contention-diag] +3552s soak 32p/172t rss 13.2G pss 12.1G swap 0.7G majflt 4734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 4 descendant rss 0.0G pss 0.0G | host avail 32.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.83/0.0 io 10.05 cpu 23.5 | cgroup 14.2G/max oom_kill 0 | free scratch 319.0G/45194327i tmp 28.3G/997890i workspace 319.0G/45194327i | repeat-01 collected 26/26 workers (60628 items) tests 35832 done 0 failed | 24 in flight, oldest 294s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
.............. [1656%]
........................................................................ [1659%]
........................................................................ [1662%]
........................................................................ [1666%]
........................................................................ [1669%]
........................................................................ [1672%]
................................................................[contention-diag] +3567s soak 32p/180t rss 13.3G pss 12.2G swap 0.7G majflt 4881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 4 descendant rss 0.1G pss 0.0G | host avail 31.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.38/0.0 io 10.4 cpu 22.96 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45193177i tmp 28.3G/997890i workspace 319.0G/45193177i | repeat-01 collected 26/26 workers (60628 items) tests 36265 done 0 failed | 21 in flight, oldest 310s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
........ [1676%]
........................................................................ [1679%]
........................................................................ [1682%]
........................................................................ [1686%]
........................................................................ [1689%]
........................................................................ [1692%]
........................................................................ [1696%]
..........................................[contention-diag] +3583s soak 31p/182t rss 13.3G pss 12.2G swap 0.7G majflt 4964 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.25/0.0 io 9.6 cpu 19.8 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45191254i tmp 28.3G/997890i workspace 319.0G/45191254i | repeat-01 collected 26/26 workers (60628 items) tests 36750 done 0 failed | 24 in flight, oldest 325s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.............................. [1699%]
........................................................................ [1702%]
........................................................................ [1706%]
........................................................................ [1709%]
........................................................................ [1712%]
..[contention-diag] +3598s soak 33p/178t rss 13.3G pss 12.2G swap 0.7G majflt 4973 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 5 descendant rss 0.1G pss 0.0G | host avail 31.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 8.42 cpu 18.32 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45190120i tmp 28.3G/997890i workspace 319.0G/45190120i | repeat-01 collected 26/26 workers (60628 items) tests 37071 done 0 failed | 21 in flight, oldest 341s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...................................................................... [1716%]
........................................................................ [1719%]
........................................................................ [1722%]
......[contention-diag] +3614s soak 31p/193t rss 13.3G pss 12.2G swap 0.7G majflt 4980 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.11/0.09 io 9.28 cpu 22.07 | cgroup 14.3G/max oom_kill 0 | free scratch 319.0G/45189594i tmp 28.3G/997890i workspace 319.0G/45189594i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 37261 done 0 failed | 24 in flight, oldest 356s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.................................................................. [1726%]
........................................................................ [1729%]
........................................................................ [1732%]
........................................................................ [1735%]
.................[contention-diag] +3631s soak 32p/175t rss 13.3G pss 12.3G swap 0.7G majflt 4985 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 32.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 12.96 cpu 25.42 | cgroup 14.4G/max oom_kill 0 | free scratch 319.0G/45188126i tmp 28.3G/997890i workspace 319.0G/45188126i | repeat-01 collected 26/26 workers (60628 items) tests 37584 done 0 failed | 24 in flight, oldest 373s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...............................................s....... [1739%]
........................................................................ [1742%]
........................................................................ [1745%]
........................................................................ [1749%]
........................................................................ [1752%]
............................................[contention-diag] +3646s soak 37p/178t rss 13.3G pss 12.2G swap 0.7G majflt 4992 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.1G pss 0.1G | host avail 32.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 13.0 cpu 24.89 | cgroup 14.4G/max oom_kill 0 | free scratch 319.0G/45186513i tmp 28.3G/997890i workspace 319.0G/45186513i | repeat-01 collected 26/26 workers (60628 items) tests 37972 done 0 failed | 23 in flight, oldest 389s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1755%]
........................................................................ [1759%]
........................................................................ [1762%]
........................................................................ [1765%]
............[contention-diag] +3662s soak 39p/200t rss 13.4G pss 12.3G swap 0.7G majflt 4999 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 11 descendant rss 0.2G pss 0.1G | host avail 31.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.03 cpu 21.38 | cgroup 14.4G/max oom_kill 0 | free scratch 319.0G/45186542i tmp 28.3G/997890i workspace 319.0G/45186542i | repeat-01 collected 26/26 workers (60628 items) tests 38241 done 0 failed | 24 in flight, oldest 404s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................................................ [1769%]
........................................................................ [1772%]
...................s....................................[contention-diag] +3677s soak 35p/211t rss 13.5G pss 12.3G swap 0.7G majflt 5023 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.2G pss 0.1G | host avail 32.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.09/0.0 io 10.64 cpu 22.66 | cgroup 14.5G/max oom_kill 0 | free scratch 319.0G/45186005i tmp 28.3G/997890i workspace 319.0G/45186005i | repeat-01 collected 26/26 workers (60628 items) tests 38419 done 0 failed | 24 in flight, oldest 419s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................ [1775%]
........................................................................ [1779%]
........................................................................ [1782%]
........................................................................ [1785%]
..........s................................[contention-diag] +3692s soak 37p/191t rss 13.6G pss 12.4G swap 0.7G majflt 5120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 9 descendant rss 0.3G pss 0.2G | host avail 30.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 12.37 cpu 24.72 | cgroup 14.6G/max oom_kill 0 | free scratch 319.0G/45185308i tmp 28.3G/997890i workspace 319.0G/45185308i | repeat-01 collected 26/26 workers (60628 items) tests 38687 done 0 failed | 24 in flight, oldest 320s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................. [1789%]
........................................................................ [1792%]
........................................................................ [1795%]
.................................[contention-diag] +3708s soak 34p/180t rss 13.6G pss 12.5G swap 0.7G majflt 5087 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 6 descendant rss 0.3G pss 0.2G | host avail 30.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.74 cpu 23.01 | cgroup 14.6G/max oom_kill 0 | free scratch 318.9G/45184708i tmp 28.3G/997890i workspace 318.9G/45184708i | repeat-01 collected 26/26 workers (60628 items) tests 38910 done 0 failed | 24 in flight, oldest 336s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....................................... [1799%]
........................................................................ [1802%]
........................................................................ [1805%]
........................................................................ [1809%]
........................................................................ [1812%]
........................................................................ [1815%]
.............................................................[contention-diag] +3723s soak 33p/190t rss 13.6G pss 12.5G swap 0.7G majflt 5095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 5 descendant rss 0.3G pss 0.2G | host avail 31.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.77 cpu 20.56 | cgroup 14.6G/max oom_kill 0 | free scratch 318.9G/45183424i tmp 28.3G/997890i workspace 318.9G/45183424i | repeat-01 collected 26/26 workers (60628 items) tests 39370 done 0 failed | 24 in flight, oldest 351s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........... [1819%]
........................................................................ [1822%]
........................................................................ [1825%]
...........................[contention-diag] +3738s soak 40p/197t rss 13.7G pss 12.5G swap 0.7G majflt 5100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 12 descendant rss 0.3G pss 0.3G | host avail 30.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.87 cpu 16.65 | cgroup 14.7G/max oom_kill 0 | free scratch 318.9G/45182732i tmp 28.3G/997890i workspace 318.9G/45182732i | scratch used 1.0G in 191830 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 39517 done 0 failed | 23 in flight, oldest 366s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................. [1829%]
........................................................................ [1832%]
........................................................................ [1835%]
........................................................................ [1839%]
....................................................................[contention-diag] +3756s soak 35p/188t rss 13.7G pss 12.6G swap 0.7G majflt 5123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 7 descendant rss 0.3G pss 0.3G | host avail 32.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.21 cpu 22.77 | cgroup 14.8G/max oom_kill 0 | free scratch 318.9G/45181629i tmp 28.3G/997890i workspace 318.9G/45181629i | repeat-01 collected 26/26 workers (60628 items) tests 39873 done 0 failed | 24 in flight, oldest 384s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.... [1842%]
........................................................................ [1845%]
........................................................................ [1849%]
........................................................................ [1852%]
........................................................................ [1855%]
.......................[contention-diag] +3771s soak 33p/174t rss 13.6G pss 12.5G swap 0.7G majflt 5128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 5 descendant rss 0.3G pss 0.2G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 12.08 cpu 24.16 | cgroup 15.0G/max oom_kill 0 | free scratch 318.9G/45180767i tmp 28.3G/997890i workspace 318.9G/45180767i | repeat-01 collected 26/26 workers (60628 items) tests 40197 done 0 failed | 24 in flight, oldest 399s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................. [1859%]
........................................................................ [1862%]
........................................................................ [1865%]
....................[contention-diag] +3786s soak 38p/192t rss 13.6G pss 12.4G swap 0.7G majflt 5131 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 10 descendant rss 0.2G pss 0.2G | host avail 30.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 1.71/1.71 io 13.51 cpu 22.28 | cgroup 15.4G/max oom_kill 0 | free scratch 318.6G/45179683i tmp 28.3G/997890i workspace 318.6G/45179683i | repeat-01 collected 26/26 workers (60628 items) tests 40404 done 0 failed | 24 in flight, oldest 414s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................................................... [1869%]
........................................................................ [1872%]
........................[contention-diag] +3802s soak 38p/198t rss 13.7G pss 12.6G swap 0.7G majflt 5138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 10 descendant rss 0.4G pss 0.3G | host avail 28.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.42/0.42 io 8.86 cpu 14.18 | cgroup 15.6G/max oom_kill 0 | free scratch 317.9G/45177184i tmp 28.3G/997890i workspace 317.9G/45177184i | repeat-01 collected 26/26 workers (60628 items) tests 40547 done 0 failed | 23 in flight, oldest 100s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
................................................ [1875%]
................................s....................................... [1878%]
........................................................................ [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
.....................................[contention-diag] +3818s soak 39p/194t rss 13.8G pss 12.6G swap 0.7G majflt 5141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 11 descendant rss 0.4G pss 0.3G | host avail 29.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.28/0.16 io 8.95 cpu 17.62 | cgroup 15.0G/max oom_kill 0 | free scratch 318.2G/45176054i tmp 28.3G/997890i workspace 318.2G/45176054i | repeat-01 collected 26/26 workers (60628 items) tests 40918 done 0 failed | 24 in flight, oldest 116s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
................................... [1892%]
........................................................................ [1895%]
........................................................................ [1898%]
........................................................................ [1902%]
........................................................................ [1905%]
.....................................................[contention-diag] +3833s soak 40p/195t rss 13.9G pss 12.7G swap 0.7G majflt 5148 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 12 descendant rss 0.6G pss 0.4G | host avail 29.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.05/0.03 io 4.16 cpu 21.74 | cgroup 15.0G/max oom_kill 0 | free scratch 318.2G/45175151i tmp 28.3G/997890i workspace 318.2G/45175151i | repeat-01 collected 26/26 workers (60628 items) tests 41298 done 0 failed | 24 in flight, oldest 131s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
................... [1908%]
........................................................................ [1912%]
........................................................................ [1915%]
........................................................................ [1918%]
.......................[contention-diag] +3848s soak 38p/179t rss 13.8G pss 12.7G swap 0.7G majflt 5150 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 10 descendant rss 0.4G pss 0.4G | host avail 28.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 5.05 cpu 20.68 | cgroup 15.0G/max oom_kill 0 | free scratch 318.2G/45174045i tmp 28.3G/997891i workspace 318.2G/45174045i | repeat-01 collected 26/26 workers (60628 items) tests 41555 done 0 failed | 24 in flight, oldest 146s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
................................................. [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
........................................................................ [1935%]
.................................................[contention-diag] +3864s soak 41p/187t rss 13.9G pss 12.7G swap 0.7G majflt 5157 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 13 descendant rss 0.5G pss 0.4G | host avail 27.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 5.44 cpu 23.8 | cgroup 15.1G/max oom_kill 0 | free scratch 318.2G/45172565i tmp 28.3G/997891i workspace 318.2G/45172565i | scratch used 0.9G in 170437 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 41916 done 0 failed | 23 in flight, oldest 162s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
....................... [1938%]
........................................................................ [1942%]
........................................................................ [1945%]
........................................................................ [1948%]
.............................[contention-diag] +3881s soak 41p/191t rss 13.9G pss 12.7G swap 0.7G majflt 5160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 13 descendant rss 0.5G pss 0.4G | host avail 26.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.17/0.17 io 4.12 cpu 21.11 | cgroup 15.2G/max oom_kill 0 | free scratch 318.2G/45171435i tmp 28.3G/997891i workspace 318.2G/45171435i | repeat-01 collected 26/26 workers (60628 items) tests 42213 done 0 failed | 23 in flight, oldest 179s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
........................................... [1952%]
........................................................................ [1955%]
........................................................................ [1958%]
........................................................................ [1962%]
........................................................................ [1965%]
.........................................................[contention-diag] +3896s soak 38p/188t rss 13.9G pss 12.7G swap 0.7G majflt 5168 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 10 descendant rss 0.5G pss 0.4G | host avail 30.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 5.05 cpu 24.57 | cgroup 15.1G/max oom_kill 0 | free scratch 318.2G/45169776i tmp 28.3G/997889i workspace 318.2G/45169776i | repeat-01 collected 26/26 workers (60628 items) tests 42595 done 0 failed | 23 in flight, oldest 195s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............... [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
........................................................................ [1978%]
........................................................................ [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
.....[contention-diag] +3912s soak 45p/205t rss 14.0G pss 12.8G swap 0.7G majflt 5171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 17 descendant rss 0.5G pss 0.5G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.67 cpu 27.53 | cgroup 15.1G/max oom_kill 0 | free scratch 318.1G/45168858i tmp 28.3G/997891i workspace 318.1G/45168858i | repeat-01 collected 26/26 workers (60628 items) tests 43056 done 0 failed | 24 in flight, oldest 210s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................................................... [1992%]
........................................................................ [1995%]
........................................................................ [1998%]
........................................................................ [2002%]
........................................................................ [2005%]
........................................................................ [2008%]
................................................................[contention-diag] +3927s soak 45p/209t rss 14.0G pss 12.8G swap 0.7G majflt 5191 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 17 descendant rss 0.6G pss 0.5G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.13 cpu 31.2 | cgroup 15.3G/max oom_kill 0 | free scratch 318.1G/45167452i tmp 28.3G/997891i workspace 318.1G/45167452i | repeat-01 collected 26/26 workers (60628 items) tests 43536 done 0 failed | 24 in flight, oldest 225s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........ [2012%]
........................................................................ [2015%]
........................................................................ [2018%]
................[contention-diag] +3942s soak 44p/206t rss 14.3G pss 13.0G swap 0.8G majflt 5194 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 16 descendant rss 0.8G pss 0.7G | host avail 32.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.39 cpu 26.44 | cgroup 15.5G/max oom_kill 0 | free scratch 318.1G/45166265i tmp 28.3G/997891i workspace 318.1G/45166265i | repeat-01 collected 26/26 workers (60628 items) tests 43715 done 0 failed | 24 in flight, oldest 241s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................................ [2021%]
........................................................................ [2025%]
........................................................................ [2028%]
........................................................................ [2031%]
....................[contention-diag] +3958s soak 40p/197t rss 14.2G pss 13.0G swap 0.7G majflt 5196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 12 descendant rss 0.8G pss 0.7G | host avail 31.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.22 cpu 23.92 | cgroup 15.5G/max oom_kill 0 | free scratch 318.1G/45165553i tmp 28.3G/997889i workspace 318.1G/45165553i | repeat-01 collected 26/26 workers (60628 items) tests 44008 done 0 failed | 24 in flight, oldest 256s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................................... [2035%]
........................................................................ [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........[contention-diag] +3973s soak 39p/197t rss 14.1G pss 12.8G swap 0.7G majflt 5198 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 11 descendant rss 0.6G pss 0.5G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.44 cpu 22.63 | cgroup 15.4G/max oom_kill 0 | free scratch 318.1G/45165731i tmp 28.3G/997889i workspace 318.1G/45165731i | repeat-01 collected 26/26 workers (60628 items) tests 44356 done 0 failed | 23 in flight, oldest 271s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................................................ [2051%]
........................................................................ [2055%]
........................................................................ [2058%]
........................................................................ [2061%]
........................................................................ [2065%]
..............................................................[contention-diag] +3989s soak 36p/183t rss 14.1G pss 12.9G swap 0.7G majflt 5199 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 8 descendant rss 0.6G pss 0.5G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.46 cpu 23.43 | cgroup 15.4G/max oom_kill 0 | free scratch 318.1G/45164568i tmp 28.3G/997889i workspace 318.1G/45164568i | scratch used 1.0G in 185092 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 44706 done 0 failed | 23 in flight, oldest 287s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......... [2068%]
........................................................................ [2071%]
........................................................................ [2075%]
........................................................................ [2078%]
................................................[contention-diag] +4006s soak 39p/185t rss 14.0G pss 12.9G swap 0.7G majflt 5202 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 11 descendant rss 0.6G pss 0.5G | host avail 32.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.42 cpu 21.92 | cgroup 15.4G/max oom_kill 0 | free scratch 318.1G/45164338i tmp 28.3G/997889i workspace 318.1G/45164338i | repeat-01 collected 26/26 workers (60628 items) tests 45042 done 0 failed | 22 in flight, oldest 304s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................ [2081%]
........................................................................ [2085%]
........................................................................ [2088%]
........................................................................ [2091%]
.....................................[contention-diag] +4021s soak 37p/199t rss 14.3G pss 13.1G swap 0.7G majflt 5213 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 9 descendant rss 0.8G pss 0.7G | host avail 30.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.65 cpu 21.17 | cgroup 15.6G/max oom_kill 0 | free scratch 318.1G/45163377i tmp 28.3G/997889i workspace 318.1G/45163377i | repeat-01 collected 26/26 workers (60628 items) tests 45323 done 0 failed | 22 in flight, oldest 319s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................... [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
........................................................................ [2105%]
........................................................................ [2108%]
.............................[contention-diag] +4037s soak 35p/177t rss 14.3G pss 13.1G swap 0.7G majflt 5218 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 7 descendant rss 0.8G pss 0.7G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.82 cpu 22.47 | cgroup 15.6G/max oom_kill 0 | free scratch 318.1G/45162564i tmp 28.3G/997889i workspace 318.1G/45162564i | repeat-01 collected 26/26 workers (60628 items) tests 45656 done 0 failed | 21 in flight, oldest 335s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................... [2111%]
........................................................................ [2115%]
......s................................................................. [2118%]
........................................................................ [2121%]
........................................................................ [2125%]
......................................[contention-diag] +4052s soak 36p/195t rss 14.4G pss 13.2G swap 0.7G majflt 5234 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 8 descendant rss 0.9G pss 0.8G | host avail 31.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.3 cpu 20.09 | cgroup 15.7G/max oom_kill 0 | free scratch 318.1G/45161119i tmp 28.3G/997889i workspace 318.1G/45161119i | repeat-01 collected 26/26 workers (60628 items) tests 46019 done 0 failed | 21 in flight, oldest 350s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................. [2128%]
........................................................................ [2131%]
........................................................................ [2135%]
........................................................................ [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........................................................................ [2155%]
.....................................................[contention-diag] +4068s soak 36p/182t rss 14.3G pss 13.2G swap 0.7G majflt 5237 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.0G, 8 descendant rss 0.8G pss 0.8G | host avail 31.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.69 cpu 24.53 | cgroup 15.7G/max oom_kill 0 | free scratch 318.1G/45160213i tmp 28.3G/997889i workspace 318.1G/45160213i | repeat-01 collected 26/26 workers (60628 items) tests 46656 done 0 failed | 21 in flight, oldest 366s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................... [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
........................................................................ [2168%]
........................................................................ [2171%]
........................................................................ [2174%]
........................................................................ [2178%]
........................................................................ [2181%]
........................................................................ [2184%]
............[contention-diag] +4083s soak 36p/189t rss 14.3G pss 13.1G swap 0.7G majflt 5241 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 8 descendant rss 0.8G pss 0.7G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.83 cpu 23.74 | cgroup 15.7G/max oom_kill 0 | free scratch 318.1G/45158734i tmp 28.3G/997889i workspace 318.1G/45158734i | repeat-01 collected 26/26 workers (60628 items) tests 47292 done 0 failed | 22 in flight, oldest 381s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................................ [2188%]
........................................................................ [2191%]
........................................................................ [2194%]
........................................................................ [2198%]
........................................................................ [2201%]
......................................[contention-diag] +4098s soak 37p/177t rss 14.5G pss 13.3G swap 0.7G majflt 5246 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.9G pss 0.9G | host avail 29.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 9.56 cpu 22.43 | cgroup 15.9G/max oom_kill 0 | free scratch 318.1G/45157325i tmp 28.3G/997889i workspace 318.1G/45157326i | repeat-01 collected 26/26 workers (60628 items) tests 47671 done 0 failed | 22 in flight, oldest 396s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................. [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2218%]
........................................................................ [2221%]
........................................................................ [2224%]
........................................................................ [2228%]
........................................................................ [2231%]
..............[contention-diag] +4114s soak 38p/188t rss 14.6G pss 13.4G swap 0.7G majflt 5284 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 1.0G pss 0.9G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 8.63 cpu 22.66 | cgroup 16.0G/max oom_kill 0 | free scratch 318.1G/45156345i tmp 28.3G/997889i workspace 318.1G/45156345i | scratch used 1.0G in 182079 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 48266 done 0 failed | 21 in flight, oldest 412s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................................... [2234%]
........................................................................ [2238%]
........................................................................ [2241%]
........................................................................ [2244%]
........................................................................ [2248%]
........................................................................ [2251%]
........................................................................ [2254%]
......................................................................[contention-diag] +4131s soak 40p/184t rss 14.6G pss 13.3G swap 0.7G majflt 5293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 12 descendant rss 1.0G pss 0.9G | host avail 30.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.21 cpu 24.84 | cgroup 16.0G/max oom_kill 0 | free scratch 318.1G/45154606i tmp 28.3G/997889i workspace 318.1G/45154606i | repeat-01 collected 26/26 workers (60628 items) tests 48850 done 0 failed | 21 in flight, oldest 356s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.. [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
................................................................[contention-diag] +4146s soak 39p/177t rss 14.6G pss 13.4G swap 0.7G majflt 5260 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.0G pss 0.9G | host avail 31.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 10.51 cpu 21.37 | cgroup 16.1G/max oom_kill 0 | free scratch 318.1G/45154519i tmp 28.3G/997889i workspace 318.1G/45154519i | repeat-01 collected 26/26 workers (60628 items) tests 49155 done 0 failed | 20 in flight, oldest 371s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........ [2271%]
........................................................................ [2274%]
........................................................................ [2278%]
........................................................................ [2281%]
........................................................................ [2284%]
........................................................................ [2288%]
.........................[contention-diag] +4162s soak 39p/181t rss 14.8G pss 13.6G swap 0.7G majflt 5268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.2G pss 1.1G | host avail 30.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.99/0.99 io 9.63 cpu 21.73 | cgroup 16.3G/max oom_kill 0 | free scratch 318.1G/45153379i tmp 28.3G/997889i workspace 318.1G/45153379i | repeat-01 collected 26/26 workers (60628 items) tests 49546 done 0 failed | 20 in flight, oldest 386s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................... [2291%]
........................................................................ [2294%]
........................................................................ [2298%]
.................................................................[contention-diag] +4177s soak 41p/185t rss 14.9G pss 13.6G swap 0.7G majflt 5269 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 13 descendant rss 1.3G pss 1.2G | host avail 31.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 9.35 cpu 21.38 | cgroup 16.4G/max oom_kill 0 | free scratch 318.1G/45153052i tmp 28.3G/997889i workspace 318.1G/45153052i | repeat-01 collected 26/26 workers (60628 items) tests 49799 done 0 failed | 19 in flight, oldest 402s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....... [2301%]
........................................................................ [2304%]
........................................................................ [2307%]
........................................................................ [2311%]
........................................................................ [2314%]
.............................[contention-diag] +4193s soak 38p/191t rss 14.8G pss 13.6G swap 0.7G majflt 5271 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 1.2G pss 1.1G | host avail 31.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 10.29 cpu 25.25 | cgroup 16.3G/max oom_kill 0 | free scratch 318.1G/45152064i tmp 28.3G/997889i workspace 318.1G/45152064i | repeat-01 collected 26/26 workers (60628 items) tests 50132 done 0 failed | 19 in flight, oldest 417s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................... [2317%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2331%]
........................................................................ [2334%]
....[contention-diag] +4208s soak 37p/181t rss 14.5G pss 13.4G swap 0.7G majflt 5273 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.9G pss 0.9G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 11.2 cpu 26.69 | cgroup 16.1G/max oom_kill 0 | free scratch 318.1G/45151067i tmp 28.3G/997889i workspace 318.1G/45151067i | repeat-01 collected 26/26 workers (60628 items) tests 50528 done 0 failed | 19 in flight, oldest 433s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.................................................................... [2337%]
.....................s.................................................. [2341%]
........................................................................ [2344%]
........................................................................ [2347%]
........................................................................ [2351%]
........................................................................ [2354%]
.........................................................[contention-diag] +4223s soak 38p/178t rss 14.7G pss 13.5G swap 0.7G majflt 5279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 1.1G pss 1.0G | host avail 29.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.22 cpu 24.03 | cgroup 16.4G/max oom_kill 0 | free scratch 318.1G/45149727i tmp 28.3G/997889i workspace 318.1G/45149727i | repeat-01 collected 26/26 workers (60628 items) tests 51019 done 0 failed | 19 in flight, oldest 448s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............... [2357%]
........................................................................ [2361%]
........................................................................ [2364%]
........................................................................ [2367%]
........................................................................ [2371%]
........................................................................ [2374%]
........................................................................ [2377%]
.......................................................................[contention-diag] +4239s soak 40p/180t rss 14.8G pss 13.5G swap 0.7G majflt 5285 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 12 descendant rss 1.1G pss 1.1G | host avail 29.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.66 cpu 20.77 | cgroup 16.5G/max oom_kill 0 | free scratch 318.1G/45148963i tmp 28.3G/997889i workspace 318.1G/45148963i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 51501 done 0 failed | 18 in flight, oldest 463s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
. [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
........................................................................ [2391%]
........................................................................ [2394%]
........................................................................ [2397%]
........................................................................ [2401%]
........................................................................ [2404%]
............[contention-diag] +4256s soak 39p/178t rss 14.9G pss 13.6G swap 0.7G majflt 5287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.2G pss 1.2G | host avail 29.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 9.82 cpu 22.87 | cgroup 16.6G/max oom_kill 0 | free scratch 318.0G/45147347i tmp 28.3G/997889i workspace 318.0G/45147347i | repeat-01 collected 26/26 workers (60628 items) tests 52055 done 0 failed | 18 in flight, oldest 481s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................ [2407%]
........................................................................ [2411%]
........................................................................ [2414%]
........................................................................ [2417%]
..................................................................[contention-diag] +4272s soak 40p/179t rss 14.8G pss 13.5G swap 0.7G majflt 5290 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 12 descendant rss 1.2G pss 1.1G | host avail 29.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.27 cpu 22.43 | cgroup 16.5G/max oom_kill 0 | free scratch 318.0G/45145805i tmp 28.3G/997889i workspace 318.0G/45145805i | repeat-01 collected 26/26 workers (60628 items) tests 52398 done 0 failed | 18 in flight, oldest 496s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...... [2421%]
........................................................................ [2424%]
........................................................................ [2427%]
........................................................................ [2431%]
........................................................................ [2434%]
.................................[contention-diag] +4287s soak 39p/174t rss 14.7G pss 13.5G swap 0.7G majflt 5297 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.1G pss 1.0G | host avail 30.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.89 cpu 20.79 | cgroup 16.5G/max oom_kill 0 | free scratch 318.0G/45145302i tmp 28.3G/997889i workspace 318.0G/45145302i | repeat-01 collected 26/26 workers (60628 items) tests 52720 done 0 failed | 17 in flight, oldest 511s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................................... [2437%]
........................................................................ [2441%]
........................................................................ [2444%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2454%]
................................................[contention-diag] +4302s soak 36p/169t rss 14.6G pss 13.4G swap 0.7G majflt 5298 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 1.0G pss 0.9G | host avail 29.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.32 cpu 22.79 | cgroup 16.4G/max oom_kill 0 | free scratch 318.0G/45143959i tmp 28.3G/997889i workspace 318.0G/45143959i | repeat-01 collected 26/26 workers (60628 items) tests 53159 done 0 failed | 17 in flight, oldest 527s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................ [2457%]
........................................................................ [2460%]
........................................................................ [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
........................................................................ [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
........................................................................ [2494%]
.............................[contention-diag] +4318s soak 34p/164t rss 14.6G pss 13.4G swap 0.7G majflt 5315 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 6 descendant rss 1.0G pss 0.9G | host avail 29.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 7.26 cpu 20.89 | cgroup 16.4G/max oom_kill 0 | free scratch 318.0G/45141831i tmp 28.3G/997889i workspace 318.0G/45141831i | repeat-01 collected 26/26 workers (60628 items) tests 53993 done 0 failed | 17 in flight, oldest 542s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................................... [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
........................................................................ [2507%]
..................s..................................................... [2510%]
........................................................................ [2514%]
........................................................................ [2517%]
........................................................................ [2520%]
........................................................................ [2524%]
...............................................................[contention-diag] +4333s soak 36p/162t rss 14.7G pss 13.3G swap 0.7G majflt 5317 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 11.9G, 8 descendant rss 1.1G pss 1.0G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 11.88 cpu 26.04 | cgroup 16.5G/max oom_kill 0 | free scratch 318.0G/45140162i tmp 28.3G/997889i workspace 318.0G/45140162i | repeat-01 collected 26/26 workers (60628 items) tests 54676 done 0 failed | 16 in flight, oldest 558s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
......... [2527%]
........................................................................ [2530%]
........................................................................ [2534%]
........................................................................ [2537%]
........................................................................ [2540%]
........................................................................ [2544%]
........................................................................ [2547%]
......................................................[contention-diag] +4349s soak 39p/173t rss 14.9G pss 13.6G swap 0.7G majflt 5319 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.2G pss 1.1G | host avail 30.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.42 cpu 25.87 | cgroup 16.6G/max oom_kill 0 | free scratch 318.0G/45139168i tmp 28.3G/997889i workspace 318.0G/45139168i | repeat-01 collected 26/26 workers (60628 items) tests 55204 done 0 failed | 17 in flight, oldest 573s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................. [2550%]
........................................................................ [2554%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2564%]
........................................................................ [2567%]
........................................................................ [2570%]
..................[contention-diag] +4364s soak 43p/171t rss 14.9G pss 13.6G swap 0.7G majflt 5320 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 15 descendant rss 1.2G pss 1.1G | host avail 29.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.44 cpu 21.47 | cgroup 16.6G/max oom_kill 0 | free scratch 318.0G/45138952i tmp 28.3G/997889i workspace 318.0G/45138952i | scratch used 1.0G in 191411 entries (truncated) | repeat-01 collected 26/26 workers (60628 items) tests 55624 done 0 failed | 16 in flight, oldest 589s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
...................................................... [2574%]
........................................................................ [2577%]
........................................................................ [2580%]
........................................................................ [2584%]
........................................................................ [2587%]
s.....................................................[contention-diag] +4381s soak 38p/180t rss 14.1G pss 12.9G swap 0.7G majflt 5325 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 0.4G pss 0.4G | host avail 28.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.89 cpu 20.52 | cgroup 16.0G/max oom_kill 0 | free scratch 318.0G/45138775i tmp 28.3G/997889i workspace 318.0G/45138775i | repeat-01 collected 26/26 workers (60628 items) tests 56056 done 0 failed | 14 in flight, oldest 111s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.................. [2590%]
........................................................................ [2593%]
........................................................................ [2597%]
........................................................................ [2600%]
.............................................[contention-diag] +4397s soak 46p/206t rss 14.7G pss 13.4G swap 0.7G majflt 5325 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 18 descendant rss 1.0G pss 0.8G | host avail 29.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 10.41 cpu 26.04 | cgroup 16.4G/max oom_kill 0 | free scratch 317.8G/45137601i tmp 28.3G/997889i workspace 317.8G/45137601i | repeat-01 collected 26/26 workers (60628 items) tests 56347 done 0 failed | 15 in flight, oldest 126s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
........................... [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
...........[contention-diag] +4412s soak 37p/170t rss 14.1G pss 12.8G swap 0.7G majflt 5330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.4G pss 0.3G | host avail 30.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 9.59 cpu 23.33 | cgroup 15.9G/max oom_kill 0 | free scratch 318.0G/45145810i tmp 28.3G/997889i workspace 318.0G/45145810i | repeat-01 collected 26/26 workers (60628 items) tests 56524 done 0 failed | 15 in flight, oldest 141s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............................................................. [2613%]
........................................................................ [2617%]
........................................................................ [2620%]
........................................................................ [2623%]
........................................................................ [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
........................................................................ [2637%]
........................................................................ [2640%]
..........................................................[contention-diag] +4428s soak 40p/171t rss 14.1G pss 12.8G swap 0.7G majflt 5335 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 12 descendant rss 0.4G pss 0.3G | host avail 31.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.51 cpu 23.1 | cgroup 15.8G/max oom_kill 0 | free scratch 318.3G/45201212i tmp 28.3G/997889i workspace 318.3G/45201212i | repeat-01 collected 26/26 workers (60628 items) tests 57225 done 0 failed | 14 in flight, oldest 48s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.............. [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
........................................................................ [2657%]
........................................................................ [2660%]
........................................................................ [2663%]
........................................................................ [2667%]
........................................................................ [2670%]
.........................................................[contention-diag] +4443s soak 37p/164t rss 14.0G pss 12.8G swap 0.7G majflt 5342 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.3G pss 0.3G | host avail 30.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.51 cpu 23.94 | cgroup 15.9G/max oom_kill 0 | free scratch 318.6G/45254475i tmp 28.3G/997889i workspace 318.6G/45254475i | repeat-01 collected 26/26 workers (60628 items) tests 57869 done 0 failed | 14 in flight, oldest 63s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
............... [2673%]
........................................................................ [2677%]
........................................................................ [2680%]
........................................................................ [2683%]
........................................................................ [2687%]
......................s................................................. [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
..................................................................[contention-diag] +4458s soak 37p/169t rss 13.9G pss 12.6G swap 0.7G majflt 5345 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.2G pss 0.1G | host avail 29.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.45 cpu 22.0 | cgroup 15.7G/max oom_kill 0 | free scratch 318.8G/45297283i tmp 28.3G/997889i workspace 318.8G/45297283i | repeat-01 collected 26/26 workers (60628 items) tests 58452 done 0 failed | 11 in flight, oldest 79s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
...... [2700%]
........................................................................ [2703%]
........................................................................ [2707%]
........................................................................ [2710%]
........................................................................ [2713%]
.........................................................[contention-diag] +4474s soak 39p/165t rss 13.8G pss 12.6G swap 0.7G majflt 5348 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 0.2G pss 0.1G | host avail 28.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.96 cpu 23.01 | cgroup 15.7G/max oom_kill 0 | free scratch 318.8G/45300361i tmp 28.3G/997888i workspace 318.8G/45300361i | repeat-01 collected 26/26 workers (60628 items) tests 58796 done 0 failed | 10 in flight, oldest 56s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............... [2717%]
........................................................................ [2720%]
........................................................................ [2723%]
........................................................................ [2727%]
........................................................................ [2730%]
........................................................................ [2733%]
.............................[contention-diag] +4489s soak 38p/162t rss 14.0G pss 12.7G swap 0.7G majflt 5354 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 0.3G pss 0.2G | host avail 29.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 7.14 cpu 18.43 | cgroup 15.8G/max oom_kill 0 | free scratch 318.8G/45300640i tmp 28.3G/997889i workspace 318.8G/45300640i | scratch used 0.9G in 167958 entries | repeat-01 collected 26/26 workers (60628 items) tests 59184 done 0 failed | 8 in flight, oldest 72s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
........................................... [2736%]
........................................................................ [2740%]
........................................[contention-diag] +4506s soak 33p/154t rss 13.8G pss 12.6G swap 0.7G majflt 5356 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 5 descendant rss 0.1G pss 0.0G | host avail 28.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.53/0.53 io 5.75 cpu 19.16 | cgroup 15.6G/max oom_kill 0 | free scratch 318.8G/45301734i tmp 28.3G/997889i workspace 318.8G/45301734i | repeat-01 collected 26/26 workers (60628 items) tests 59342 done 0 failed | 6 in flight, oldest 89s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................................ [2743%]
........................................................................ [2746%]
........................................................................ [2750%]
.............[contention-diag] +4521s soak 35p/157t rss 13.7G pss 12.5G swap 0.7G majflt 5359 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.0G pss 0.0G | host avail 26.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.64/0.64 io 5.56 cpu 19.95 | cgroup 15.4G/max oom_kill 0 | free scratch 318.8G/45301213i tmp 28.3G/997889i workspace 318.8G/45301213i | repeat-01 collected 26/26 workers (60628 items) tests 59557 done 0 failed | 6 in flight, oldest 62s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
...............................................ssss........ [2753%]
........................................................................ [2756%]
........................................................................ [2760%]
........................................................................ [2763%]
........................................................................ [2766%]
........................................................................ [2770%]
......................................................................[contention-diag] +4537s soak 34p/153t rss 13.8G pss 12.5G swap 0.7G majflt 5364 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 0.1G pss 0.0G | host avail 26.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 6.41 cpu 18.77 | cgroup 15.6G/max oom_kill 0 | free scratch 318.8G/45301035i tmp 28.3G/997887i workspace 318.8G/45301035i | repeat-01 collected 26/26 workers (60628 items) tests 60044 done 0 failed | 4 in flight, oldest 4s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
.. [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
........................................................................ [2786%]
.................................................[contention-diag] +4552s soak 34p/150t rss 13.8G pss 12.5G swap 0.8G majflt 5380 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 6 descendant rss 0.1G pss 0.1G | host avail 25.8G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 8.35 cpu 11.67 | cgroup 15.3G/max oom_kill 0 | free scratch 318.8G/45301788i tmp 28.3G/997889i workspace 318.8G/45301788i | repeat-01 collected 26/26 workers (60628 items) tests 60385 done 0 failed | 2 in flight, oldest 0s gw21 tests/test_run_agent_wait_name_refresh_recovery.py::test_generated_bead_waiter_reconciles_registry_only_owner_after_refresh | 10 hazardous kill call(s)
....................... [2790%]
........................................................................ [2793%]
........................................................................ [2796%]
........................................................................ [2800%]
....                                                                     [100%][contention-diag] +4567s soak 2p/2t rss 0.4G pss 0.4G swap 0.0G majflt 191 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 40.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 6.22 cpu 13.56 | cgroup 3.2G/max oom_kill 0 | free scratch 318.9G/45353685i tmp 28.3G/997889i workspace 318.9G/45353687i | repeat-01 collected 26/26 workers (60628 items) tests 60628 done 0 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
../../../../../../../../../tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_view_foundation.py::test_hidden_inbox_refresh_repaints
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    path = os.fspath(arg)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_new_project_create_execution.py::test_create_review_compact_heading_stays_visible
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/css/tokenizer.py:302: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for name, value in zip(expect.names, match.groups()[1:]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/css/model.py:189: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for selector, next_selector in zip(self.selectors, self.selectors[1:]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/css/tokenizer.py:302: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    for name, value in zip(expect.names, match.groups()[1:]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/cache.py:60: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    super().__init__()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_collapsed_panel_selection.py::test_focused_collapsed_panel_has_no_selected_agent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_restore_proof.py::test_proof_dimmed_restored_row_render
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/binding.py:134: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    bindings = list(bindings)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=1141309) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1141528) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=1142261) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1141353) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:888: DeprecationWarning: This process (pid=1141309) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1142277) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
595.91s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
436.35s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
430.24s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
425.57s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
420.29s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
402.70s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
329.53s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
321.40s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
316.74s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
308.29s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
307.44s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
250.30s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
220.43s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
190.44s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
180.70s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
176.95s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
174.62s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
164.37s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
160.60s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
159.86s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
========= 60608 passed, 21 skipped, 111 warnings in 4570.78s (1:16:10) =========
[contention-diag] +4577s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 460 | 1 parent rss 0.0G pss 0.0G | host avail 43.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 7.61 cpu 4.99 | cgroup 2.5G/max oom_kill 0 | free scratch 319.2G/45468636i tmp 28.3G/997889i workspace 319.2G/45468636i | repeat-01 collected 26/26 workers (60628 items) tests 60628 done 0 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4577s, 295 samples, 0 signal(s); peaks: cgroup_current 16.6G, min_free_scratch 307.9G, min_free_tmp 28.3G, min_free_workspace 307.9G, min_inodes_scratch 45101982, min_inodes_tmp 997415, min_inodes_workspace 45101982, min_mem_available 25.8G, min_swap_free 53.8G, oom_kill_delta 0, pressure_memory_full 2.0, pswpin_delta 97494, pswpout_delta 162182, scratch_bytes 1.1G, soak_procs 46, soak_pss 13.6G, soak_rss 14.9G, soak_swap 1.3G, soak_threads 297

contention tally: 0 node(s) failed across 1 repeat(s) in 4577.3s; red repeats: none
  no node failed in any repeat
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
succeeded  exit=0  duration=4578138ms

