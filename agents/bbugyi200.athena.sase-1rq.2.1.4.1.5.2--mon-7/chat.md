# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-7)

- **TIMESTAMP:** 2026-11-08 19:30:35 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-7

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after bump thread_time and provider-timer Live.update repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 2697333, sampler pid 2697593 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-1661263-1794179303155836201.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 98 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.82 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 314.9G/45375860i tmp 28.7G/1002367i workspace 314.9G/45375860i | scratch used 0.0G in 13 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.1G pss 1.8G swap 0.0G majflt 212 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.0G pss 1.7G | host avail 30.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.52 cpu 13.39 | cgroup 1.9G/max oom_kill 0 | free scratch 314.9G/45374083i tmp 28.7G/1002367i workspace 314.9G/45374083i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 3.4G pss 3.0G swap 0.8G majflt 625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.3G pss 2.9G | host avail 29.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.59 cpu 16.32 | cgroup 3.1G/max oom_kill 0 | free scratch 314.9G/45374038i tmp 28.7G/1002356i workspace 314.9G/45374038i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +45s soak 28p/80t rss 4.5G pss 4.1G swap 1.0G majflt 630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.4G pss 4.0G | host avail 29.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.3 cpu 16.99 | cgroup 4.2G/max oom_kill 0 | free scratch 314.9G/45374008i tmp 28.7G/1002352i workspace 314.9G/45374008i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +61s soak 28p/86t rss 5.3G pss 4.8G swap 1.0G majflt 797 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.2G pss 4.8G | host avail 28.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.06 cpu 18.19 | cgroup 5.0G/max oom_kill 0 | free scratch 314.8G/45374004i tmp 28.7G/1000945i workspace 314.8G/45374004i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 29p/90t rss 6.0G pss 5.5G swap 1.1G majflt 874 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.9G pss 5.5G, 1 descendant rss 0.0G pss 0.0G | host avail 23.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.31 cpu 17.08 | cgroup 5.8G/max oom_kill 0 | free scratch 314.8G/45373996i tmp 28.7G/1000945i workspace 314.8G/45373996i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +91s soak 28p/90t rss 6.6G pss 6.1G swap 1.1G majflt 878 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.4G pss 6.0G | host avail 24.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.12/0.08 io 0.54 cpu 14.99 | cgroup 6.5G/max oom_kill 0 | free scratch 314.5G/45371767i tmp 28.7G/1000945i workspace 314.5G/45371767i | repeat-01 collected 22/26 workers (51557 items) tests 0 done 0 failed
contention shards: 26 workers collected 60624 items in total (2020-2558 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
........................................................................ [ 13%]
........................................................................ [ 16%]
........................................................................ [ 19%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
........................................................................ [ 33%]
.....................................................................[contention-diag] +106s soak 29p/109t rss 7.0G pss 6.4G swap 1.0G majflt 1786 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.8G pss 6.3G, 1 descendant rss 0.1G pss 0.1G | host avail 25.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 0.98 cpu 14.75 | cgroup 6.9G/max oom_kill 0 | free scratch 312.9G/45361326i tmp 28.7G/1000945i workspace 312.9G/45361326i | repeat-01 collected 26/26 workers (60624 items) tests 757 done 0 failed | 26 in flight, oldest 13s gw20 tests/ace/test_revert_agent_import_order.py::test_module_imports_first_in_a_fresh_interpreter[sase.ace.revert_agent_resolution]
... [ 36%]
........................................................................ [ 39%]
........................................................................ [ 43%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
..........[contention-diag] +121s soak 29p/143t rss 7.4G pss 6.8G swap 1.0G majflt 1909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.6G, 1 descendant rss 0.0G pss 0.0G | host avail 27.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 15.52 | cgroup 7.3G/max oom_kill 0 | free scratch 312.6G/45350115i tmp 28.7G/1002351i workspace 312.6G/45350115i | scratch used 0.0G in 3183 entries | repeat-01 collected 26/26 workers (60624 items) tests 1157 done 0 failed | 26 in flight, oldest 27s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.............................................................. [ 56%]
........................................................................ [ 59%]
........................................................................ [ 63%]
...............................[contention-diag] +137s soak 28p/159t rss 7.5G pss 7.0G swap 1.0G majflt 1996 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.8G | host avail 32.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 21.52 | cgroup 7.5G/max oom_kill 0 | free scratch 312.6G/45349500i tmp 28.7G/1002350i workspace 312.6G/45349500i | repeat-01 collected 26/26 workers (60624 items) tests 1391 done 0 failed | 26 in flight, oldest 43s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
......................................... [ 66%]
........................................................................ [ 69%]
........................................................................ [ 73%]
...........................[contention-diag] +152s soak 30p/164t rss 7.8G pss 7.2G swap 1.0G majflt 2029 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.5G pss 7.0G, 2 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.12 cpu 12.2 | cgroup 7.7G/max oom_kill 0 | free scratch 312.5G/45347934i tmp 28.7G/1002350i workspace 312.5G/45347934i | repeat-01 collected 26/26 workers (60624 items) tests 1607 done 0 failed | 26 in flight, oldest 58s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
............................................. [ 76%]
........................................................................ [ 79%]
........................................................................ [ 83%]
.........................................................[contention-diag] +167s soak 30p/172t rss 8.0G pss 7.4G swap 1.0G majflt 2101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.7G pss 7.1G, 2 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.92 cpu 15.34 | cgroup 7.9G/max oom_kill 0 | free scratch 312.5G/45335483i tmp 28.7G/1002350i workspace 312.5G/45335482i | repeat-01 collected 26/26 workers (60624 items) tests 1854 done 0 failed | 26 in flight, oldest 70s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
............... [ 86%]
........................................................................ [ 89%]
.................[contention-diag] +183s soak 34p/183t rss 8.1G pss 7.4G swap 1.0G majflt 2109 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.9G pss 7.3G, 6 descendant rss 0.1G pss 0.0G | host avail 26.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 20.99 cpu 8.82 | cgroup 8.0G/max oom_kill 0 | free scratch 312.2G/45318823i tmp 28.7G/1001815i workspace 312.2G/45318823i | repeat-01 collected 26/26 workers (60624 items) tests 1956 done 0 failed | 26 in flight, oldest 63s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [ 93%]
.............................................................[contention-diag] +198s soak 34p/225t rss 8.3G pss 7.6G swap 1.0G majflt 2196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.4G, 6 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 11.6 cpu 9.88 | cgroup 8.2G/max oom_kill 0 | free scratch 312.2G/45318643i tmp 28.7G/1002296i workspace 312.2G/45318643i | repeat-01 collected 26/26 workers (60624 items) tests 2071 done 0 failed | 26 in flight, oldest 78s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [ 96%]
........................................................................ [ 99%]
........................................................................ [103%]
........................................................................ [106%]
........................................................................ [109%]
.................[contention-diag] +213s soak 37p/215t rss 8.5G pss 7.8G swap 1.0G majflt 2124 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.5G, 9 descendant rss 0.2G pss 0.2G | host avail 30.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.63 cpu 21.5 | cgroup 8.4G/max oom_kill 0 | free scratch 312.2G/45317207i tmp 28.7G/1002300i workspace 312.2G/45317207i | repeat-01 collected 26/26 workers (60624 items) tests 2388 done 0 failed | 26 in flight, oldest 93s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [113%]
.....................................[contention-diag] +228s soak 35p/217t rss 8.7G pss 8.0G swap 1.0G majflt 2158 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.7G, 7 descendant rss 0.2G pss 0.2G | host avail 29.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.21 cpu 24.82 | cgroup 8.5G/max oom_kill 0 | free scratch 312.2G/45316847i tmp 28.7G/1002300i workspace 312.2G/45316847i | repeat-01 collected 26/26 workers (60624 items) tests 2479 done 0 failed | 26 in flight, oldest 109s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [116%]
........................................................................ [119%]
........................................................................ [123%]
.....................[contention-diag] +244s soak 35p/215t rss 9.0G pss 8.3G swap 1.0G majflt 2194 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.0G, 7 descendant rss 0.2G pss 0.2G | host avail 28.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.05 cpu 21.89 | cgroup 8.9G/max oom_kill 0 | free scratch 312.0G/45316467i tmp 28.7G/1002317i workspace 312.0G/45316467i | scratch used 0.0G in 7315 entries | repeat-01 collected 26/26 workers (60624 items) tests 2676 done 0 failed | 26 in flight, oldest 124s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................... [126%]
..........................................[contention-diag] +259s soak 36p/225t rss 8.8G pss 8.1G swap 1.0G majflt 2232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 8 descendant rss 0.2G pss 0.1G | host avail 27.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.51 cpu 13.65 | cgroup 8.7G/max oom_kill 0 | free scratch 312.2G/45316317i tmp 28.7G/1002328i workspace 312.2G/45316317i | repeat-01 collected 26/26 workers (60624 items) tests 2769 done 0 failed | 26 in flight, oldest 139s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................. [129%]
........................................................................ [133%]
........................................................................ [136%]
.................[contention-diag] +274s soak 37p/219t rss 9.0G pss 8.3G swap 1.0G majflt 2248 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 7.9G, 9 descendant rss 0.3G pss 0.2G | host avail 27.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.2 cpu 12.91 | cgroup 8.9G/max oom_kill 0 | free scratch 312.2G/45315675i tmp 28.7G/1002328i workspace 312.2G/45315675i | repeat-01 collected 26/26 workers (60624 items) tests 2965 done 0 failed | 26 in flight, oldest 154s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [139%]
........................................................................ [143%]
...............................................................[contention-diag] +290s soak 31p/231t rss 9.1G pss 8.4G swap 1.0G majflt 2317 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.0G, 3 descendant rss 0.2G pss 0.2G | host avail 27.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 0.39 cpu 19.78 | cgroup 9.0G/max oom_kill 0 | free scratch 312.2G/45315201i tmp 28.7G/1002328i workspace 312.2G/45315201i | repeat-01 collected 26/26 workers (60624 items) tests 3157 done 0 failed | 26 in flight, oldest 170s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......... [146%]
...............................................[contention-diag] +305s soak 33p/249t rss 9.0G pss 8.3G swap 0.9G majflt 2333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 28.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.07 cpu 23.89 | cgroup 8.9G/max oom_kill 0 | free scratch 312.2G/45314963i tmp 28.7G/1002328i workspace 312.2G/45314963i | repeat-01 collected 26/26 workers (60624 items) tests 3215 done 0 failed | 26 in flight, oldest 185s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................... [149%]
......[contention-diag] +320s soak 36p/249t rss 9.1G pss 8.3G swap 0.9G majflt 2334 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 8 descendant rss 0.1G pss 0.0G | host avail 25.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.01 cpu 19.12 | cgroup 9.0G/max oom_kill 0 | free scratch 312.2G/45314746i tmp 28.7G/1002328i workspace 312.2G/45314746i | repeat-01 collected 26/26 workers (60624 items) tests 3245 done 0 failed | 26 in flight, oldest 200s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................[contention-diag] +336s soak 35p/250t rss 9.2G pss 8.5G swap 1.0G majflt 2333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.2G, 7 descendant rss 0.2G pss 0.1G | host avail 26.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.49 | cgroup 9.2G/max oom_kill 0 | free scratch 312.2G/45314540i tmp 28.7G/1002328i workspace 312.2G/45314540i | repeat-01 collected 26/26 workers (60624 items) tests 3291 done 0 failed | 26 in flight, oldest 216s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................. [152%]
........................................................................ [156%]
..[contention-diag] +351s soak 34p/239t rss 9.3G pss 8.6G swap 1.0G majflt 2334 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 26.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.82 | cgroup 9.2G/max oom_kill 0 | free scratch 312.2G/45314159i tmp 28.7G/1002328i workspace 312.2G/45314159i | repeat-01 collected 26/26 workers (60624 items) tests 3385 done 0 failed | 26 in flight, oldest 231s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................................... [159%]
........................................................................ [162%]
...........................[contention-diag] +366s soak 35p/240t rss 9.3G pss 8.6G swap 0.9G majflt 2344 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.4G, 7 descendant rss 0.1G pss 0.0G | host avail 27.9G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 20.62 | cgroup 9.2G/max oom_kill 0 | free scratch 312.2G/45313650i tmp 28.7G/1002328i workspace 312.2G/45313650i | scratch used 0.1G in 10140 entries | repeat-01 collected 26/26 workers (60624 items) tests 3550 done 0 failed | 26 in flight, oldest 246s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................. [166%]
................................[contention-diag] +382s soak 36p/254t rss 9.4G pss 8.7G swap 0.9G majflt 2345 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 8 descendant rss 0.1G pss 0.1G | host avail 26.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.01 | cgroup 9.3G/max oom_kill 0 | free scratch 312.2G/45313268i tmp 28.7G/1002327i workspace 312.2G/45313268i | repeat-01 collected 26/26 workers (60624 items) tests 3629 done 0 failed | 26 in flight, oldest 262s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................[contention-diag] +397s soak 35p/266t rss 9.5G pss 8.8G swap 1.0G majflt 2346 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.5G, 7 descendant rss 0.2G pss 0.1G | host avail 24.5G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.31 | cgroup 9.4G/max oom_kill 0 | free scratch 312.2G/45313127i tmp 28.7G/1002326i workspace 312.2G/45313127i | repeat-01 collected 26/26 workers (60624 items) tests 3651 done 0 failed | 26 in flight, oldest 277s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............ [169%]
........................................................................ [172%]
......................[contention-diag] +412s soak 40p/262t rss 9.7G pss 8.9G swap 1.0G majflt 2346 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 12 descendant rss 0.3G pss 0.2G | host avail 22.8G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 15.59 | cgroup 9.5G/max oom_kill 0 | free scratch 312.1G/45312736i tmp 28.7G/1002327i workspace 312.1G/45312736i | repeat-01 collected 26/26 workers (60624 items) tests 3764 done 0 failed | 26 in flight, oldest 292s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................. [176%]
.......................[contention-diag] +428s soak 38p/245t rss 9.6G pss 8.8G swap 0.9G majflt 2346 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.6G, 10 descendant rss 0.1G pss 0.0G | host avail 24.3G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 15.86 | cgroup 9.5G/max oom_kill 0 | free scratch 312.2G/45312466i tmp 28.7G/1002327i workspace 312.2G/45312466i | repeat-01 collected 26/26 workers (60624 items) tests 3832 done 0 failed | 24 in flight, oldest 308s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................. [179%]
...................................................[contention-diag] +443s soak 39p/275t rss 9.6G pss 8.8G swap 0.9G majflt 2346 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.6G, 11 descendant rss 0.1G pss 0.1G | host avail 24.1G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.35 | cgroup 9.4G/max oom_kill 0 | free scratch 312.2G/45311955i tmp 28.7G/1002327i workspace 312.2G/45311955i | repeat-01 collected 26/26 workers (60624 items) tests 3937 done 0 failed | 26 in flight, oldest 323s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................... [182%]
..............................................[contention-diag] +458s soak 42p/284t rss 9.8G pss 9.0G swap 1.0G majflt 2347 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 14 descendant rss 0.3G pss 0.2G | host avail 21.0G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.0 cpu 16.38 | cgroup 9.5G/max oom_kill 0 | free scratch 312.6G/45311663i tmp 28.7G/1002327i workspace 312.6G/45311663i | repeat-01 collected 26/26 workers (60624 items) tests 4001 done 0 failed | 26 in flight, oldest 338s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................... [186%]
........................................................................ [189%]
........................[contention-diag] +474s soak 42p/250t rss 9.9G pss 9.1G swap 1.0G majflt 2347 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.7G, 14 descendant rss 0.3G pss 0.2G | host avail 21.7G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.07/0.01 io 1.1 cpu 16.29 | cgroup 9.6G/max oom_kill 0 | free scratch 313.4G/45394216i tmp 28.7G/1002325i workspace 313.4G/45394216i | repeat-01 collected 26/26 workers (60624 items) tests 4125 done 0 failed | 26 in flight, oldest 354s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................ [192%]
.................[contention-diag] +489s soak 36p/256t rss 9.7G pss 9.0G swap 1.0G majflt 2354 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 8 descendant rss 0.1G pss 0.1G | host avail 22.8G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.22 cpu 13.88 | cgroup 9.6G/max oom_kill 0 | free scratch 318.4G/45395197i tmp 28.7G/1002327i workspace 318.4G/45395197i | scratch used 0.1G in 12347 entries | repeat-01 collected 26/26 workers (60624 items) tests 4192 done 0 failed | 26 in flight, oldest 369s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [196%]
.........................[contention-diag] +504s soak 35p/276t rss 9.8G pss 9.1G swap 1.0G majflt 2396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 23.6G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 14.72 | cgroup 9.7G/max oom_kill 0 | free scratch 318.4G/45395624i tmp 28.7G/1002327i workspace 318.4G/45395624i | repeat-01 collected 26/26 workers (60624 items) tests 4270 done 0 failed | 26 in flight, oldest 385s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................[contention-diag] +520s soak 36p/278t rss 9.9G pss 9.2G swap 1.0G majflt 2441 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 8 descendant rss 0.2G pss 0.2G | host avail 22.5G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 16.0 | cgroup 9.8G/max oom_kill 0 | free scratch 318.3G/45395391i tmp 28.7G/1002325i workspace 318.3G/45395391i | repeat-01 collected 26/26 workers (60624 items) tests 4304 done 0 failed | 26 in flight, oldest 400s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............. [199%]
........................................................................ [202%]
............................................[contention-diag] +535s soak 30p/255t rss 9.9G pss 9.2G swap 1.0G majflt 2440 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.9G, 2 descendant rss 0.1G pss 0.1G | host avail 19.0G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.1 cpu 13.92 | cgroup 9.8G/max oom_kill 0 | free scratch 318.3G/45394936i tmp 28.7G/1002325i workspace 318.3G/45394936i | repeat-01 collected 26/26 workers (60624 items) tests 4433 done 0 failed | 26 in flight, oldest 415s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................[contention-diag] +550s soak 28p/244t rss 9.8G pss 9.1G swap 0.9G majflt 2441 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G | host avail 19.8G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 12.02 | cgroup 9.7G/max oom_kill 0 | free scratch 318.0G/45394753i tmp 28.7G/1002325i workspace 318.0G/45394753i | repeat-01 collected 26/26 workers (60624 items) tests 4453 done 0 failed | 26 in flight, oldest 124s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
........... [206%]
............................[contention-diag] +566s soak 29p/256t rss 9.8G pss 9.1G swap 0.9G majflt 2443 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 12.44 | cgroup 9.7G/max oom_kill 0 | free scratch 317.5G/45394566i tmp 28.7G/1002325i workspace 317.5G/45394566i | repeat-01 collected 26/26 workers (60624 items) tests 4492 done 0 failed | 26 in flight, oldest 64s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...................[contention-diag] +581s soak 29p/234t rss 9.9G pss 9.2G swap 0.9G majflt 2464 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.49 cpu 15.91 | cgroup 9.8G/max oom_kill 0 | free scratch 317.9G/45394451i tmp 28.7G/1002325i workspace 317.9G/45394451i | repeat-01 collected 26/26 workers (60624 items) tests 4506 done 0 failed | 26 in flight, oldest 79s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
....................[contention-diag] +596s soak 32p/240t rss 10.1G pss 9.3G swap 1.0G majflt 2486 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 4 descendant rss 0.2G pss 0.1G | host avail 30.8G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 1.34 cpu 16.29 | cgroup 10.0G/max oom_kill 0 | free scratch 317.9G/45394246i tmp 28.7G/1002323i workspace 317.9G/45394246i | repeat-01 collected 26/26 workers (60624 items) tests 4527 done 0 failed | 26 in flight, oldest 94s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
..... [209%]
........................................................................ [212%]
.........................[contention-diag] +612s soak 28p/234t rss 9.9G pss 9.2G swap 0.9G majflt 2464 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G | host avail 28.8G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 1.19 cpu 16.71 | cgroup 9.9G/max oom_kill 0 | free scratch 317.9G/45393801i tmp 28.7G/1002325i workspace 317.9G/45393801i | scratch used 0.1G in 14258 entries | repeat-01 collected 26/26 workers (60624 items) tests 4629 done 0 failed | 26 in flight, oldest 80s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
............................................... [216%]
..[contention-diag] +627s soak 28p/238t rss 10.0G pss 9.3G swap 0.9G majflt 2464 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G | host avail 28.4G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.45 cpu 18.45 | cgroup 10.0G/max oom_kill 0 | free scratch 317.9G/45393465i tmp 28.7G/1002325i workspace 317.9G/45393465i | repeat-01 collected 26/26 workers (60624 items) tests 4682 done 0 failed | 26 in flight, oldest 95s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
.............................[contention-diag] +642s soak 30p/241t rss 10.1G pss 9.3G swap 0.9G majflt 2465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G, 2 descendant rss 0.1G pss 0.1G | host avail 30.0G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.61 cpu 26.55 | cgroup 10.0G/max oom_kill 0 | free scratch 317.9G/45393255i tmp 28.7G/1002325i workspace 317.9G/45393255i | repeat-01 collected 26/26 workers (60624 items) tests 4705 done 0 failed | 26 in flight, oldest 51s gw19 tests/ace/tui/test_agent_grouping_picker.py::test_agents_default_oo_toggles_panel_layout_once_and_preserves_mode
......................................... [219%]
..[contention-diag] +658s soak 29p/237t rss 10.1G pss 9.4G swap 1.0G majflt 2465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 28.2G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.42 cpu 20.03 | cgroup 10.1G/max oom_kill 0 | free scratch 317.9G/45392992i tmp 28.7G/1002325i workspace 317.9G/45392992i | repeat-01 collected 26/26 workers (60624 items) tests 4752 done 0 failed | 26 in flight, oldest 57s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_K_warns_when_finished_and_confirms_when_running
.........................[contention-diag] +673s soak 28p/246t rss 10.1G pss 9.4G swap 0.9G majflt 2465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G | host avail 28.4G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.95 cpu 19.28 | cgroup 10.1G/max oom_kill 0 | free scratch 317.9G/45392819i tmp 28.7G/1002325i workspace 317.9G/45392819i | repeat-01 collected 26/26 workers (60624 items) tests 4772 done 0 failed | 26 in flight, oldest 53s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
..................[contention-diag] +688s soak 28p/255t rss 10.1G pss 9.4G swap 0.9G majflt 2465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G | host avail 27.2G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 13.16 | cgroup 10.1G/max oom_kill 0 | free scratch 317.7G/45391100i tmp 28.7G/1002325i workspace 317.7G/45391100i | repeat-01 collected 26/26 workers (60624 items) tests 4794 done 0 failed | 26 in flight, oldest 68s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
........................... [222%]
..................[contention-diag] +703s soak 30p/265t rss 10.2G pss 9.5G swap 0.9G majflt 2465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G, 2 descendant rss 0.1G pss 0.1G | host avail 26.9G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 16.83 | cgroup 10.2G/max oom_kill 0 | free scratch 317.6G/45390945i tmp 28.7G/1002325i workspace 317.6G/45390945i | repeat-01 collected 26/26 workers (60624 items) tests 4842 done 0 failed | 26 in flight, oldest 75s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
..........................[contention-diag] +719s soak 29p/226t rss 10.3G pss 9.5G swap 1.0G majflt 2475 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G, 1 descendant rss 0.1G pss 0.1G | host avail 25.6G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.86 cpu 18.56 | cgroup 10.3G/max oom_kill 0 | free scratch 317.0G/45387303i tmp 28.7G/1002325i workspace 317.0G/45387303i | repeat-01 collected 26/26 workers (60624 items) tests 4859 done 0 failed | 26 in flight, oldest 62s gw11 tests/ace/tui/test_agent_cleanup_panel_clan_sticky_e2e.py::test_cleanup_dismiss_folded_clan_unmounts_its_tribe_panel
.................[contention-diag] +734s soak 28p/239t rss 10.2G pss 9.5G swap 0.9G majflt 2475 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 24.3G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.33 cpu 15.18 | cgroup 10.3G/max oom_kill 0 | free scratch 316.4G/45383753i tmp 28.7G/1002325i workspace 316.4G/45383753i | scratch used 0.1G in 15766 entries | repeat-01 collected 26/26 workers (60624 items) tests 4884 done 0 failed | 26 in flight, oldest 64s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
........... [226%]
.[contention-diag] +750s soak 28p/244t rss 10.2G pss 9.5G swap 0.9G majflt 2478 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G | host avail 23.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 1.81 cpu 18.31 | cgroup 10.4G/max oom_kill 0 | free scratch 316.4G/45383596i tmp 28.7G/1002325i workspace 316.4G/45383596i | repeat-01 collected 26/26 workers (60624 items) tests 4897 done 0 failed | 26 in flight, oldest 57s gw25 tests/ace/tui/test_link_follow_entry_points.py::test_matrix_archived_plan_via_links_panel
............................................[contention-diag] +765s soak 31p/234t rss 10.4G pss 9.6G swap 0.9G majflt 2479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 3 descendant rss 0.1G pss 0.1G | host avail 25.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.93 cpu 20.53 | cgroup 10.4G/max oom_kill 0 | free scratch 316.3G/45383401i tmp 28.7G/1002325i workspace 316.3G/45383401i | repeat-01 collected 26/26 workers (60624 items) tests 4936 done 0 failed | 26 in flight, oldest 52s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
........................... [229%]
........................................................................ [232%]
.........................................[contention-diag] +780s soak 29p/226t rss 10.3G pss 9.6G swap 0.9G majflt 2479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.1 cpu 24.07 | cgroup 10.4G/max oom_kill 0 | free scratch 316.2G/45382966i tmp 28.7G/1002325i workspace 316.2G/45382966i | repeat-01 collected 26/26 workers (60624 items) tests 5079 done 0 failed | 26 in flight, oldest 60s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_panel_action_override_takes_effect_in_mounted_pilot
............................... [236%]
..........................................................[contention-diag] +796s soak 28p/222t rss 10.3G pss 9.6G swap 0.9G majflt 2479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G | host avail 22.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.26 cpu 20.55 | cgroup 10.5G/max oom_kill 0 | free scratch 316.2G/45382615i tmp 28.7G/1002325i workspace 316.2G/45382615i | repeat-01 collected 26/26 workers (60624 items) tests 5159 done 0 failed | 26 in flight, oldest 48s gw21 tests/ace/tui/test_commits_pane_filters.py::test_committed_project_key_alias_and_unknown_ref_canonicalization
.............. [239%]
........................................................................ [242%]
........................................................................ [246%]
........................................................................ [249%]
...............[contention-diag] +811s soak 28p/239t rss 10.3G pss 9.6G swap 0.9G majflt 2479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G | host avail 26.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.51 cpu 20.59 | cgroup 10.4G/max oom_kill 0 | free scratch 316.2G/45381939i tmp 28.7G/1002325i workspace 316.2G/45381939i | repeat-01 collected 26/26 workers (60624 items) tests 5411 done 0 failed | 26 in flight, oldest 57s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
......................................................... [252%]
[contention-diag] +826s soak 30p/275t rss 10.4G pss 9.7G swap 0.9G majflt 2482 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 2 descendant rss 0.1G pss 0.1G | host avail 28.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.91 cpu 25.03 | cgroup 10.5G/max oom_kill 0 | free scratch 316.2G/45381478i tmp 28.7G/1002325i workspace 316.2G/45381478i | repeat-01 collected 26/26 workers (60624 items) tests 5454 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
........................................................................ [256%]
..............................................[contention-diag] +841s soak 30p/246t rss 10.5G pss 9.8G swap 0.9G majflt 2489 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 2 descendant rss 0.1G pss 0.1G | host avail 29.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.43 cpu 29.15 | cgroup 10.6G/max oom_kill 0 | free scratch 316.2G/45381092i tmp 28.7G/1002325i workspace 316.2G/45381092i | repeat-01 collected 26/26 workers (60624 items) tests 5589 done 0 failed | 26 in flight, oldest 77s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.......................... [259%]
........[contention-diag] +857s soak 29p/253t rss 10.4G pss 9.7G swap 0.9G majflt 2494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 27.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.92 cpu 25.87 | cgroup 10.6G/max oom_kill 0 | free scratch 316.2G/45380921i tmp 28.7G/1002325i workspace 316.2G/45380921i | scratch used 0.1G in 18455 entries | repeat-01 collected 26/26 workers (60624 items) tests 5623 done 0 failed | 26 in flight, oldest 92s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.............................................[contention-diag] +872s soak 28p/259t rss 10.5G pss 9.8G swap 0.9G majflt 2494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G | host avail 27.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.18 cpu 21.38 | cgroup 10.6G/max oom_kill 0 | free scratch 316.2G/45380665i tmp 28.7G/1002325i workspace 316.2G/45380665i | repeat-01 collected 26/26 workers (60624 items) tests 5669 done 0 failed | 26 in flight, oldest 108s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................[contention-diag] +888s soak 32p/262t rss 10.7G pss 9.9G swap 0.9G majflt 2494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 4 descendant rss 0.1G pss 0.1G | host avail 26.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.65 cpu 24.03 | cgroup 10.7G/max oom_kill 0 | free scratch 316.7G/45380491i tmp 28.7G/1002325i workspace 316.7G/45380491i | repeat-01 collected 26/26 workers (60624 items) tests 5684 done 0 failed | 26 in flight, oldest 123s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
... [262%]
........................................................................ [266%]
..................[contention-diag] +903s soak 30p/273t rss 10.6G pss 9.9G swap 0.9G majflt 2494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 2 descendant rss 0.1G pss 0.0G | host avail 24.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 24.1 | cgroup 10.6G/max oom_kill 0 | free scratch 316.5G/45380163i tmp 28.7G/1002325i workspace 316.5G/45380163i | repeat-01 collected 26/26 workers (60624 items) tests 5767 done 0 failed | 26 in flight, oldest 138s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...................................................... [269%]
..................[contention-diag] +918s soak 28p/225t rss 10.6G pss 9.9G swap 0.9G majflt 2494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G | host avail 22.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.53/0.53 io 4.38 cpu 15.24 | cgroup 10.6G/max oom_kill 0 | free scratch 316.4G/45379964i tmp 28.7G/1002325i workspace 316.4G/45379964i | repeat-01 collected 26/26 workers (60624 items) tests 5841 done 0 failed | 26 in flight, oldest 81s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_toggle_clamps_container_and_restores_width
...................................................... [272%]
........................................................................ [276%]
........................................................................ [279%]
.[contention-diag] +934s soak 28p/221t rss 10.6G pss 9.9G swap 0.9G majflt 2495 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G | host avail 19.8G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.44/0.38 io 2.4 cpu 11.78 | cgroup 10.7G/max oom_kill 0 | free scratch 316.3G/45379179i tmp 28.7G/1002325i workspace 316.3G/45379179i | repeat-01 collected 26/26 workers (60624 items) tests 6045 done 0 failed | 26 in flight, oldest 62s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
....................................................................... [282%]
........................................................................ [286%]
.........................[contention-diag] +949s soak 31p/258t rss 10.7G pss 9.9G swap 1.0G majflt 2509 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 3 descendant rss 0.1G pss 0.1G | host avail 20.7G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.51/0.5 io 1.84 cpu 13.03 | cgroup 10.5G/max oom_kill 0 | free scratch 316.2G/45378702i tmp 28.7G/1002325i workspace 316.2G/45378702i | repeat-01 collected 26/26 workers (60624 items) tests 6210 done 0 failed | 26 in flight, oldest 77s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
............................................... [289%]
................................................................[contention-diag] +964s soak 28p/214t rss 10.6G pss 9.9G swap 1.0G majflt 2503 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 21.1G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 1.16 cpu 15.72 | cgroup 10.5G/max oom_kill 0 | free scratch 316.0G/45377891i tmp 28.7G/1002325i workspace 316.0G/45377891i | repeat-01 collected 26/26 workers (60624 items) tests 6322 done 0 failed | 26 in flight, oldest 50s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_install_hint_only_for_not_installed
........ [292%]
........................................................................ [295%]
.[contention-diag] +979s soak 28p/221t rss 10.7G pss 9.9G swap 1.0G majflt 2508 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 19.9G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 1.69 cpu 13.48 | cgroup 10.5G/max oom_kill 0 | free scratch 315.9G/45377677i tmp 28.7G/1002325i workspace 315.9G/45377677i | scratch used 0.1G in 21203 entries | repeat-01 collected 26/26 workers (60624 items) tests 6408 done 0 failed | 25 in flight, oldest 57s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
........................................................[contention-diag] +995s soak 30p/253t rss 10.8G pss 10.0G swap 1.0G majflt 2511 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 2 descendant rss 0.1G pss 0.1G | host avail 28.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.4/0.34 io 1.8 cpu 17.63 | cgroup 10.5G/max oom_kill 0 | free scratch 315.8G/45377378i tmp 28.7G/1002325i workspace 315.8G/45377378i | repeat-01 collected 26/26 workers (60624 items) tests 6457 done 0 failed | 26 in flight, oldest 72s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
............... [299%]
........................................................................ [302%]
................................................................[contention-diag] +1010s soak 31p/225t rss 10.8G pss 10.0G swap 1.0G majflt 2554 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 3 descendant rss 0.1G pss 0.1G | host avail 26.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.06 io 1.04 cpu 16.73 | cgroup 10.5G/max oom_kill 0 | free scratch 315.8G/45376938i tmp 28.7G/1002325i workspace 315.8G/45376938i | repeat-01 collected 26/26 workers (60624 items) tests 6615 done 0 failed | 26 in flight, oldest 49s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
........ [305%]
......................................[contention-diag] +1026s soak 29p/221t rss 10.8G pss 10.0G swap 1.0G majflt 2587 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G, 1 descendant rss 0.1G pss 0.0G | host avail 25.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.42 cpu 16.29 | cgroup 10.6G/max oom_kill 0 | free scratch 315.8G/45376688i tmp 28.7G/1002325i workspace 315.8G/45376688i | repeat-01 collected 26/26 workers (60624 items) tests 6660 done 0 failed | 26 in flight, oldest 52s gw24 tests/ace/tui/test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest
.................................. [309%]
...................................................[contention-diag] +1041s soak 29p/230t rss 10.8G pss 10.0G swap 1.0G majflt 2574 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 29.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.15 cpu 21.27 | cgroup 10.6G/max oom_kill 0 | free scratch 315.8G/45376412i tmp 28.7G/1002325i workspace 315.8G/45376412i | repeat-01 collected 26/26 workers (60624 items) tests 6739 done 0 failed | 26 in flight, oldest 50s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_ctrl_j_grows_limit_and_ctrl_k_returns_to_floor
..................... [312%]
.............[contention-diag] +1056s soak 30p/266t rss 10.9G pss 10.1G swap 1.0G majflt 2576 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G, 2 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.74 cpu 18.37 | cgroup 10.6G/max oom_kill 0 | free scratch 315.8G/45376071i tmp 28.7G/1002325i workspace 315.8G/45376071i | repeat-01 collected 26/26 workers (60624 items) tests 6780 done 0 failed | 26 in flight, oldest 55s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........................................................... [315%]
........................................................................ [319%]
.............................................[contention-diag] +1072s soak 30p/231t rss 10.9G pss 10.1G swap 1.0G majflt 2582 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G, 2 descendant rss 0.1G pss 0.0G | host avail 28.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.83 cpu 18.39 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45375551i tmp 28.7G/1002325i workspace 315.8G/45375551i | repeat-01 collected 26/26 workers (60624 items) tests 6946 done 0 failed | 26 in flight, oldest 70s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........................... [322%]
........................................................................ [325%]
.[contention-diag] +1087s soak 31p/218t rss 11.0G pss 10.2G swap 1.0G majflt 2590 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G, 3 descendant rss 0.1G pss 0.1G | host avail 28.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.2 cpu 19.96 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45375174i tmp 28.7G/1002325i workspace 315.8G/45375174i | repeat-01 collected 26/26 workers (60624 items) tests 7055 done 0 failed | 26 in flight, oldest 45s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_limit_all_then_ctrl_k_introduces_page_size
..........................[contention-diag] +1102s soak 31p/241t rss 11.0G pss 10.2G swap 1.0G majflt 2590 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 3 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.15 cpu 18.74 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45375023i tmp 28.7G/1002325i workspace 315.8G/45375023i | scratch used 0.2G in 23563 entries | repeat-01 collected 26/26 workers (60624 items) tests 7081 done 0 failed | 26 in flight, oldest 58s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
............................................. [329%]
...........................................[contention-diag] +1118s soak 29p/241t rss 10.9G pss 10.1G swap 1.0G majflt 2593 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.29 cpu 19.35 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45374691i tmp 28.7G/1002324i workspace 315.8G/45374691i | repeat-01 collected 26/26 workers (60624 items) tests 7159 done 0 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
............................. [332%]
........................................................................ [335%]
........................................................................ [339%]
.[contention-diag] +1133s soak 28p/212t rss 10.9G pss 10.1G swap 1.0G majflt 2600 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G | host avail 28.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.77 cpu 18.79 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45374227i tmp 28.7G/1002323i workspace 315.8G/45374227i | repeat-01 collected 26/26 workers (60624 items) tests 7335 done 0 failed | 26 in flight, oldest 58s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
.................................................................[contention-diag] +1148s soak 28p/233t rss 10.9G pss 10.1G swap 1.0G majflt 2600 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G | host avail 30.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.98 cpu 20.19 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45373835i tmp 28.7G/1002323i workspace 315.8G/45373835i | repeat-01 collected 26/26 workers (60624 items) tests 7410 done 0 failed | 26 in flight, oldest 44s gw15 tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_skips_lazy_latest_when_already_checked
...... [342%]
........................................................................ [345%]
........................................................................ [349%]
.........[contention-diag] +1164s soak 28p/236t rss 11.0G pss 10.2G swap 1.0G majflt 2609 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.0G | host avail 30.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.68 cpu 20.4 | cgroup 10.7G/max oom_kill 0 | free scratch 315.8G/45373358i tmp 28.7G/1002323i workspace 315.8G/45373358i | repeat-01 collected 26/26 workers (60624 items) tests 7563 done 0 failed | 26 in flight, oldest 43s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_real_mount_opens_existing_entry_in_unfocused_browse_mode
............................................................... [352%]
...................................................................[contention-diag] +1179s soak 28p/259t rss 11.0G pss 10.2G swap 1.0G majflt 2612 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.0G | host avail 28.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.42 cpu 20.44 | cgroup 10.8G/max oom_kill 0 | free scratch 315.8G/45372944i tmp 28.7G/1002325i workspace 315.8G/45372944i | repeat-01 collected 26/26 workers (60624 items) tests 7691 done 0 failed | 26 in flight, oldest 58s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
..... [355%]
................[contention-diag] +1195s soak 38p/279t rss 11.1G pss 10.2G swap 1.0G majflt 2612 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 27.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 1.31 cpu 16.31 | cgroup 10.8G/max oom_kill 0 | free scratch 315.7G/45372704i tmp 28.7G/1002324i workspace 315.7G/45372704i | repeat-01 collected 26/26 workers (60624 items) tests 7720 done 0 failed | 26 in flight, oldest 73s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......................[contention-diag] +1210s soak 38p/265t rss 11.1G pss 10.2G swap 1.0G majflt 2613 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 26.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.16 cpu 12.88 | cgroup 10.8G/max oom_kill 0 | free scratch 315.8G/45372373i tmp 28.7G/1002324i workspace 315.8G/45372373i | repeat-01 collected 26/26 workers (60624 items) tests 7743 done 0 failed | 26 in flight, oldest 89s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.........................[contention-diag] +1226s soak 39p/263t rss 11.1G pss 10.3G swap 1.0G majflt 2614 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 11 descendant rss 0.1G pss 0.0G | host avail 24.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 11.98 | cgroup 10.8G/max oom_kill 0 | free scratch 316.2G/45372192i tmp 28.7G/1002324i workspace 316.2G/45372192i | scratch used 0.2G in 25960 entries | repeat-01 collected 26/26 workers (60624 items) tests 7767 done 0 failed | 26 in flight, oldest 105s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
........ [359%]
......[contention-diag] +1242s soak 39p/272t rss 11.2G pss 10.3G swap 1.0G majflt 2627 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 11 descendant rss 0.1G pss 0.0G | host avail 20.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 1.71/1.44 io 2.8 cpu 11.72 | cgroup 10.8G/max oom_kill 0 | free scratch 316.6G/45375558i tmp 28.7G/1002324i workspace 316.6G/45375558i | repeat-01 collected 26/26 workers (60624 items) tests 7782 done 0 failed | 26 in flight, oldest 120s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.................................................................. [362%]
......[contention-diag] +1257s soak 30p/244t rss 11.1G pss 10.2G swap 1.0G majflt 2640 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 2 descendant rss 0.0G pss 0.0G | host avail 22.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.34/0.29 io 1.72 cpu 12.73 | cgroup 10.8G/max oom_kill 0 | free scratch 316.6G/45375277i tmp 28.7G/1002324i workspace 316.6G/45375277i | repeat-01 collected 26/26 workers (60624 items) tests 7853 done 0 failed | 26 in flight, oldest 74s gw18 tests/ace/tui/modals/test_saved_query_picker.py::test_picker_follows_active_query_pane_and_digits_switch_artifacts
......................................................[contention-diag] +1272s soak 38p/267t rss 11.2G pss 10.3G swap 1.0G majflt 2641 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 21.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.05 io 0.59 cpu 11.88 | cgroup 10.9G/max oom_kill 0 | free scratch 316.6G/45374998i tmp 28.7G/1002324i workspace 316.6G/45374998i | repeat-01 collected 26/26 workers (60624 items) tests 7903 done 0 failed | 26 in flight, oldest 74s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
............ [365%]
..............................................[contention-diag] +1288s soak 38p/247t rss 11.2G pss 10.3G swap 1.0G majflt 2642 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 20.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 0.54 cpu 12.84 | cgroup 10.9G/max oom_kill 0 | free scratch 316.6G/45374727i tmp 28.7G/1002322i workspace 316.6G/45374727i | repeat-01 collected 26/26 workers (60624 items) tests 7965 done 0 failed | 26 in flight, oldest 90s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
.......................... [369%]
.......................................................................[contention-diag] +1303s soak 38p/248t rss 11.2G pss 10.3G swap 1.0G majflt 2666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 19.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.53 cpu 13.39 | cgroup 10.9G/max oom_kill 0 | free scratch 316.5G/45374458i tmp 28.7G/1002324i workspace 316.5G/45374458i | repeat-01 collected 26/26 workers (60624 items) tests 8062 done 0 failed | 26 in flight, oldest 71s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
. [372%]
.........[contention-diag] +1318s soak 30p/256t rss 11.1G pss 10.3G swap 1.0G majflt 2668 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 2 descendant rss 0.0G pss 0.0G | host avail 21.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.13 cpu 14.62 | cgroup 10.9G/max oom_kill 0 | free scratch 316.2G/45374346i tmp 28.7G/1002324i workspace 316.2G/45374346i | repeat-01 collected 26/26 workers (60624 items) tests 8073 done 0 failed | 26 in flight, oldest 87s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
............................................................... [375%]
......................[contention-diag] +1334s soak 28p/216t rss 11.2G pss 10.3G swap 1.0G majflt 2669 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 20.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 14.62 | cgroup 10.9G/max oom_kill 0 | free scratch 316.0G/45374051i tmp 28.7G/1002324i workspace 316.0G/45374051i | repeat-01 collected 26/26 workers (60624 items) tests 8147 done 0 failed | 26 in flight, oldest 54s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................. [379%]
........................................................................ [382%]
......................[contention-diag] +1349s soak 28p/237t rss 11.2G pss 10.4G swap 1.0G majflt 2683 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 24.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.0 cpu 12.84 | cgroup 10.9G/max oom_kill 0 | free scratch 315.6G/45373629i tmp 28.7G/1002324i workspace 315.6G/45373629i | scratch used 0.2G in 27927 entries | repeat-01 collected 26/26 workers (60624 items) tests 8294 done 0 failed | 26 in flight, oldest 69s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................. [385%]
.........[contention-diag] +1365s soak 28p/238t rss 11.2G pss 10.4G swap 1.0G majflt 2683 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 25.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.39 cpu 9.81 | cgroup 10.9G/max oom_kill 0 | free scratch 316.1G/45372354i tmp 28.7G/1002324i workspace 316.1G/45372354i | repeat-01 collected 26/26 workers (60624 items) tests 8352 done 0 failed | 26 in flight, oldest 85s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................................... [389%]
........................................................................ [392%]
....................................[contention-diag] +1380s soak 28p/262t rss 11.2G pss 10.4G swap 1.0G majflt 2705 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 28.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.51 cpu 14.5 | cgroup 10.9G/max oom_kill 0 | free scratch 316.1G/45365514i tmp 28.7G/1002324i workspace 316.1G/45365514i | repeat-01 collected 26/26 workers (60624 items) tests 8531 done 0 failed | 26 in flight, oldest 100s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................... [395%]
...................................................................[contention-diag] +1396s soak 28p/254t rss 11.2G pss 10.4G swap 1.0G majflt 2835 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 23.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.96 cpu 11.49 | cgroup 11.0G/max oom_kill 0 | free scratch 315.9G/45346419i tmp 28.7G/1002093i workspace 315.9G/45346418i | repeat-01 collected 26/26 workers (60624 items) tests 8632 done 0 failed | 25 in flight, oldest 116s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..... [399%]
........................................................................ [402%]
........................................................................ [405%]
........................................................................ [409%]
.............[contention-diag] +1411s soak 30p/223t rss 11.3G pss 10.5G swap 1.0G majflt 2847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 2 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.97 cpu 13.3 | cgroup 11.1G/max oom_kill 0 | free scratch 315.9G/45343180i tmp 28.7G/1002270i workspace 315.9G/45343180i | repeat-01 collected 26/26 workers (60624 items) tests 8863 done 0 failed | 25 in flight, oldest 131s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................................................... [412%]
.........................................................[contention-diag] +1426s soak 29p/241t rss 11.3G pss 10.4G swap 1.0G majflt 2848 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 28.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.37 cpu 21.48 | cgroup 11.0G/max oom_kill 0 | free scratch 315.9G/45342715i tmp 28.7G/1002270i workspace 315.9G/45342715i | repeat-01 collected 26/26 workers (60624 items) tests 8983 done 0 failed | 26 in flight, oldest 146s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............... [415%]
................................................................[contention-diag] +1442s soak 29p/255t rss 11.3G pss 10.5G swap 1.0G majflt 2859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.54 cpu 26.82 | cgroup 11.1G/max oom_kill 0 | free scratch 315.9G/45342444i tmp 28.7G/1002270i workspace 315.9G/45342444i | repeat-01 collected 26/26 workers (60624 items) tests 9061 done 0 failed | 26 in flight, oldest 162s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........ [419%]
........................................................................ [422%]
....[contention-diag] +1457s soak 28p/265t rss 11.3G pss 10.5G swap 1.0G majflt 2868 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G | host avail 29.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.52 cpu 23.54 | cgroup 11.1G/max oom_kill 0 | free scratch 315.9G/45342438i tmp 28.7G/1002296i workspace 315.9G/45342438i | repeat-01 collected 26/26 workers (60624 items) tests 9146 done 0 failed | 26 in flight, oldest 177s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................[contention-diag] +1472s soak 28p/238t rss 11.3G pss 10.5G swap 1.0G majflt 2873 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G | host avail 29.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.56 cpu 18.44 | cgroup 11.1G/max oom_kill 0 | free scratch 315.9G/45342234i tmp 28.7G/1002298i workspace 315.9G/45342234i | scratch used 0.2G in 30514 entries | repeat-01 collected 26/26 workers (60624 items) tests 9171 done 0 failed | 26 in flight, oldest 85s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................................ [425%]
........[contention-diag] +1488s soak 28p/233t rss 11.4G pss 10.5G swap 1.0G majflt 2881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G | host avail 29.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.47/0.47 io 0.93 cpu 14.91 | cgroup 11.2G/max oom_kill 0 | free scratch 315.9G/45342137i tmp 28.7G/1002298i workspace 315.9G/45342137i | repeat-01 collected 26/26 workers (60624 items) tests 9221 done 0 failed | 26 in flight, oldest 101s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................[contention-diag] +1503s soak 28p/243t rss 11.4G pss 10.5G swap 1.0G majflt 2881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G | host avail 28.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 1.13 cpu 23.37 | cgroup 11.2G/max oom_kill 0 | free scratch 315.9G/45342011i tmp 28.7G/1002298i workspace 315.9G/45342011i | repeat-01 collected 26/26 workers (60624 items) tests 9254 done 0 failed | 26 in flight, oldest 116s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................[contention-diag] +1518s soak 28p/254t rss 11.4G pss 10.6G swap 1.0G majflt 2882 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G | host avail 28.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.34 cpu 23.05 | cgroup 11.2G/max oom_kill 0 | free scratch 315.6G/45341798i tmp 28.7G/1002298i workspace 315.6G/45341798i | repeat-01 collected 26/26 workers (60624 items) tests 9283 done 0 failed | 26 in flight, oldest 131s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.... [429%]
...............................................................[contention-diag] +1534s soak 29p/247t rss 11.4G pss 10.6G swap 1.0G majflt 2894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.27 cpu 21.47 | cgroup 11.2G/max oom_kill 0 | free scratch 315.8G/45341339i tmp 28.7G/1002299i workspace 315.8G/45341339i | repeat-01 collected 26/26 workers (60624 items) tests 9351 done 0 failed | 26 in flight, oldest 147s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
......... [432%]
........................................................................ [435%]
.......[contention-diag] +1549s soak 28p/230t rss 11.4G pss 10.6G swap 1.0G majflt 2899 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G | host avail 28.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.7 cpu 25.53 | cgroup 11.2G/max oom_kill 0 | free scratch 315.8G/45341213i tmp 28.7G/1002299i workspace 315.8G/45341213i | repeat-01 collected 26/26 workers (60624 items) tests 9436 done 0 failed | 26 in flight, oldest 162s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................................................[contention-diag] +1564s soak 29p/237t rss 11.4G pss 10.6G swap 1.0G majflt 2926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.3 cpu 24.26 | cgroup 11.3G/max oom_kill 0 | free scratch 315.8G/45340917i tmp 28.7G/1002299i workspace 315.8G/45340917i | repeat-01 collected 26/26 workers (60624 items) tests 9503 done 0 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
. [438%]
........................................................................ [442%]
......................................[contention-diag] +1580s soak 28p/234t rss 11.4G pss 10.6G swap 1.0G majflt 2949 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G | host avail 26.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.06 cpu 24.32 | cgroup 11.3G/max oom_kill 0 | free scratch 315.8G/45340593i tmp 28.7G/1002299i workspace 315.8G/45340593i | repeat-01 collected 26/26 workers (60624 items) tests 9605 done 0 failed | 26 in flight, oldest 79s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................. [445%]
.....................[contention-diag] +1595s soak 28p/242t rss 11.4G pss 10.6G swap 1.0G majflt 2949 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G | host avail 26.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.05 cpu 20.35 | cgroup 11.3G/max oom_kill 0 | free scratch 315.8G/45340396i tmp 28.7G/1002299i workspace 315.8G/45340396i | scratch used 0.2G in 32383 entries | repeat-01 collected 26/26 workers (60624 items) tests 9669 done 0 failed | 26 in flight, oldest 95s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................... [448%]
..............................................................[contention-diag] +1611s soak 28p/242t rss 11.5G pss 10.6G swap 1.0G majflt 2960 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 26.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.56 cpu 19.33 | cgroup 11.3G/max oom_kill 0 | free scratch 315.8G/45340075i tmp 28.7G/1002299i workspace 315.8G/45340075i | repeat-01 collected 26/26 workers (60624 items) tests 9772 done 0 failed | 26 in flight, oldest 111s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......... [452%]
.................................................................[contention-diag] +1626s soak 29p/232t rss 11.5G pss 10.6G swap 1.0G majflt 2974 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.83 cpu 22.56 | cgroup 11.3G/max oom_kill 0 | free scratch 315.8G/45339665i tmp 28.7G/1002299i workspace 315.8G/45339665i | repeat-01 collected 26/26 workers (60624 items) tests 9855 done 0 failed | 26 in flight, oldest 126s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....... [455%]
..........................................................[contention-diag] +1642s soak 29p/220t rss 11.5G pss 10.6G swap 1.0G majflt 2974 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 27.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.75 cpu 25.79 | cgroup 11.3G/max oom_kill 0 | free scratch 315.8G/45339509i tmp 28.7G/1002299i workspace 315.8G/45339510i | repeat-01 collected 26/26 workers (60624 items) tests 9913 done 0 failed | 26 in flight, oldest 141s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............. [458%]
........................................................................ [462%]
.............................................................[contention-diag] +1657s soak 28p/239t rss 11.5G pss 10.7G swap 1.0G majflt 2985 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 27.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 1.2/1.2 io 3.44 cpu 21.2 | cgroup 11.4G/max oom_kill 0 | free scratch 315.8G/45339037i tmp 28.7G/1002298i workspace 315.8G/45339037i | repeat-01 collected 26/26 workers (60624 items) tests 10069 done 0 failed | 26 in flight, oldest 157s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........... [465%]
.................[contention-diag] +1672s soak 28p/246t rss 11.5G pss 10.6G swap 1.0G majflt 3024 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 26.0G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 1.35/1.17 io 2.95 cpu 18.19 | cgroup 11.2G/max oom_kill 0 | free scratch 315.7G/45337821i tmp 28.7G/1002298i workspace 315.7G/45337821i | repeat-01 collected 26/26 workers (60624 items) tests 10092 done 0 failed | 26 in flight, oldest 172s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................................................... [468%]
..........[contention-diag] +1688s soak 30p/262t rss 11.6G pss 10.7G swap 1.0G majflt 3292 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 2 descendant rss 0.1G pss 0.1G | host avail 27.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.65/0.23 io 2.55 cpu 17.65 | cgroup 11.3G/max oom_kill 0 | free scratch 315.5G/45336863i tmp 28.7G/1002298i workspace 315.5G/45336863i | repeat-01 collected 26/26 workers (60624 items) tests 10160 done 0 failed | 26 in flight, oldest 187s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.....................[contention-diag] +1703s soak 29p/247t rss 11.6G pss 10.7G swap 1.0G majflt 3263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 26.7G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.34/0.05 io 3.18 cpu 21.86 | cgroup 11.2G/max oom_kill 0 | free scratch 315.3G/45336709i tmp 28.7G/1002298i workspace 315.3G/45336709i | repeat-01 collected 26/26 workers (60624 items) tests 10180 done 0 failed | 26 in flight, oldest 203s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................................... [472%]
...........................[contention-diag] +1718s soak 29p/285t rss 11.6G pss 10.7G swap 1.0G majflt 3315 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.1G pss 0.0G | host avail 25.7G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.01 io 5.64 cpu 20.19 | cgroup 11.3G/max oom_kill 0 | free scratch 315.3G/45336465i tmp 28.7G/1002298i workspace 315.3G/45336465i | scratch used 0.2G in 34520 entries | repeat-01 collected 26/26 workers (60624 items) tests 10242 done 0 failed | 26 in flight, oldest 218s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................. [475%]
......[contention-diag] +1734s soak 30p/248t rss 11.6G pss 10.7G swap 1.0G majflt 3309 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.15/0.1 io 5.83 cpu 18.6 | cgroup 11.3G/max oom_kill 0 | free scratch 315.2G/45336240i tmp 28.7G/1002297i workspace 315.2G/45336240i | repeat-01 collected 26/26 workers (60624 items) tests 10299 done 0 failed | 26 in flight, oldest 234s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................................. [478%]
........................................................................ [482%]
..[contention-diag] +1749s soak 29p/246t rss 11.7G pss 10.8G swap 1.0G majflt 3321 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 27.9G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 4.69 cpu 23.25 | cgroup 11.4G/max oom_kill 0 | free scratch 315.2G/45335818i tmp 28.7G/1002298i workspace 315.2G/45335818i | repeat-01 collected 26/26 workers (60624 items) tests 10438 done 0 failed | 26 in flight, oldest 249s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................................... [485%]
............................................................[contention-diag] +1764s soak 28p/272t rss 11.6G pss 10.8G swap 1.0G majflt 3325 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 30.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.74 cpu 26.92 | cgroup 11.3G/max oom_kill 0 | free scratch 315.2G/45335470i tmp 28.7G/1002298i workspace 315.2G/45335470i | repeat-01 collected 26/26 workers (60624 items) tests 10565 done 0 failed | 26 in flight, oldest 264s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............ [488%]
........................................................................ [492%]
.............................................[contention-diag] +1780s soak 28p/277t rss 11.7G pss 10.8G swap 1.0G majflt 3333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 28.8G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.46 cpu 27.42 | cgroup 11.4G/max oom_kill 0 | free scratch 315.2G/45334840i tmp 28.7G/1002298i workspace 315.2G/45334840i | repeat-01 collected 26/26 workers (60624 items) tests 10697 done 0 failed | 26 in flight, oldest 280s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................... [495%]
.............[contention-diag] +1795s soak 28p/273t rss 11.7G pss 10.8G swap 1.0G majflt 3337 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 27.4G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.6 cpu 23.48 | cgroup 11.4G/max oom_kill 0 | free scratch 315.4G/45334557i tmp 28.7G/1002298i workspace 315.4G/45334557i | repeat-01 collected 26/26 workers (60624 items) tests 10738 done 0 failed | 25 in flight, oldest 295s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................................................... [498%]
........................................................................ [502%]
.........[contention-diag] +1811s soak 28p/260t rss 11.7G pss 10.8G swap 1.0G majflt 3376 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 28.0G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.56 cpu 24.23 | cgroup 11.4G/max oom_kill 0 | free scratch 315.3G/45334441i tmp 28.7G/1002298i workspace 315.3G/45334441i | repeat-01 collected 26/26 workers (60624 items) tests 10876 done 0 failed | 25 in flight, oldest 310s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................................... [505%]
.............................................[contention-diag] +1826s soak 30p/271t rss 11.7G pss 10.8G swap 1.0G majflt 3392 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.55 cpu 21.03 | cgroup 11.4G/max oom_kill 0 | free scratch 315.3G/45334053i tmp 28.7G/1002298i workspace 315.3G/45334053i | repeat-01 collected 26/26 workers (60624 items) tests 10988 done 0 failed | 26 in flight, oldest 59s gw15 tests/ace/tui/test_statistics_pane_view_navigation.py::test_nine_view_keyboard_and_mouse_navigation_share_order
........................... [508%]
.........................[contention-diag] +1841s soak 30p/279t rss 11.7G pss 10.8G swap 1.0G majflt 3437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.29 cpu 20.28 | cgroup 11.4G/max oom_kill 0 | free scratch 315.1G/45333687i tmp 28.7G/1002297i workspace 315.1G/45333687i | scratch used 0.2G in 37221 entries | repeat-01 collected 26/26 workers (60624 items) tests 11034 done 0 failed | 26 in flight, oldest 58s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
................................[contention-diag] +1857s soak 30p/284t rss 11.7G pss 10.8G swap 1.0G majflt 3478 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.2 cpu 14.06 | cgroup 11.5G/max oom_kill 0 | free scratch 314.7G/45331669i tmp 28.7G/1002297i workspace 314.7G/45331669i | repeat-01 collected 26/26 workers (60624 items) tests 11072 done 0 failed | 26 in flight, oldest 73s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
............... [512%]
.............[contention-diag] +1872s soak 30p/289t rss 11.7G pss 10.8G swap 1.0G majflt 3480 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 24.9G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 1.2/1.2 io 2.15 cpu 16.5 | cgroup 11.5G/max oom_kill 0 | free scratch 314.6G/45331370i tmp 28.7G/1002297i workspace 314.6G/45331370i | repeat-01 collected 26/26 workers (60624 items) tests 11091 done 0 failed | 26 in flight, oldest 89s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........................................................... [515%]
........................................................................ [518%]
.[contention-diag] +1888s soak 32p/282t rss 11.8G pss 10.9G swap 1.0G majflt 3569 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 4 descendant rss 0.0G pss 0.0G | host avail 25.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.24/0.24 io 4.06 cpu 22.76 | cgroup 11.5G/max oom_kill 0 | free scratch 314.4G/45330944i tmp 28.7G/1002297i workspace 314.4G/45330944i | repeat-01 collected 26/26 workers (60624 items) tests 11230 done 0 failed | 26 in flight, oldest 104s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
....................................................................... [522%]
........................................................................ [525%]
..................[contention-diag] +1903s soak 31p/262t rss 11.8G pss 10.9G swap 1.0G majflt 3691 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 3 descendant rss 0.1G pss 0.0G | host avail 23.6G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 2.93 cpu 21.44 | cgroup 11.5G/max oom_kill 0 | free scratch 314.3G/45330483i tmp 28.7G/1002297i workspace 314.3G/45330483i | repeat-01 collected 26/26 workers (60624 items) tests 11391 done 0 failed | 26 in flight, oldest 65s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
...................................................... [528%]
.........................................................[contention-diag] +1919s soak 34p/271t rss 11.9G pss 11.0G swap 1.0G majflt 3702 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 6 descendant rss 0.1G pss 0.1G | host avail 22.8G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 3.55 cpu 20.36 | cgroup 11.7G/max oom_kill 0 | free scratch 314.2G/45330023i tmp 28.7G/1002297i workspace 314.2G/45330023i | repeat-01 collected 26/26 workers (60624 items) tests 11502 done 0 failed | 26 in flight, oldest 80s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
............... [532%]
..................................................................[contention-diag] +1934s soak 29p/264t rss 11.8G pss 10.9G swap 1.0G majflt 3704 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.6G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 2.73 cpu 17.94 | cgroup 11.6G/max oom_kill 0 | free scratch 314.0G/45329330i tmp 28.7G/1002297i workspace 314.0G/45329330i | repeat-01 collected 26/26 workers (60624 items) tests 11583 done 0 failed | 26 in flight, oldest 52s gw22 tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_ctrl_d_and_ctrl_u_scroll_detail_only
...... [535%]
........................[contention-diag] +1949s soak 32p/259t rss 11.8G pss 10.9G swap 1.0G majflt 3707 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 4 descendant rss 0.1G pss 0.0G | host avail 22.9G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 4.21 cpu 20.75 | cgroup 11.6G/max oom_kill 0 | free scratch 313.9G/45329160i tmp 28.7G/1002297i workspace 313.9G/45329160i | repeat-01 collected 26/26 workers (60624 items) tests 11614 done 0 failed | 26 in flight, oldest 49s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_summary_counts
................................................ [538%]
....................[contention-diag] +1964s soak 29p/257t rss 11.8G pss 10.9G swap 1.0G majflt 3712 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.1G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.89 cpu 20.62 | cgroup 11.5G/max oom_kill 0 | free scratch 313.9G/45328918i tmp 28.7G/1002294i workspace 313.9G/45328918i | scratch used 0.2G in 39653 entries | repeat-01 collected 26/26 workers (60624 items) tests 11671 done 0 failed | 26 in flight, oldest 57s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
.................................................... [542%]
...[contention-diag] +1981s soak 31p/274t rss 11.9G pss 11.0G swap 1.0G majflt 3727 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 3 descendant rss 0.1G pss 0.0G | host avail 26.3G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.55 cpu 17.94 | cgroup 11.6G/max oom_kill 0 | free scratch 313.5G/45327715i tmp 28.7G/1002294i workspace 313.5G/45327715i | repeat-01 collected 26/26 workers (60624 items) tests 11736 done 0 failed | 26 in flight, oldest 73s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
......................[contention-diag] +1996s soak 30p/252t rss 11.9G pss 11.0G swap 1.0G majflt 3728 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.1G pss 0.0G | host avail 25.6G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 3.84 cpu 17.0 | cgroup 11.6G/max oom_kill 0 | free scratch 313.2G/45327012i tmp 28.7G/1002294i workspace 313.2G/45327012i | repeat-01 collected 26/26 workers (60624 items) tests 11751 done 0 failed | 26 in flight, oldest 65s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree
............................................... [545%]
.................[contention-diag] +2012s soak 33p/258t rss 11.9G pss 11.0G swap 1.0G majflt 3737 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 5 descendant rss 0.1G pss 0.0G | host avail 23.7G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 3.26 cpu 17.14 | cgroup 11.6G/max oom_kill 0 | free scratch 313.2G/45326746i tmp 28.7G/1002294i workspace 313.2G/45326746i | repeat-01 collected 26/26 workers (60624 items) tests 11821 done 0 failed | 26 in flight, oldest 56s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
....................................................... [548%]
.....................................[contention-diag] +2027s soak 29p/261t rss 11.9G pss 11.0G swap 1.0G majflt 3750 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 23.5G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.13 cpu 20.35 | cgroup 11.6G/max oom_kill 0 | free scratch 312.9G/45326440i tmp 28.7G/1002294i workspace 312.9G/45326440i | repeat-01 collected 26/26 workers (60624 items) tests 11910 done 0 failed | 26 in flight, oldest 71s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................................... [552%]
...........................[contention-diag] +2042s soak 31p/268t rss 12.0G pss 11.0G swap 1.0G majflt 3759 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 22.7G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.97 cpu 16.35 | cgroup 11.6G/max oom_kill 0 | free scratch 312.6G/45325406i tmp 28.7G/1002294i workspace 312.6G/45325406i | repeat-01 collected 26/26 workers (60624 items) tests 11978 done 0 failed | 26 in flight, oldest 86s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
............................................. [555%]
.........................[contention-diag] +2058s soak 30p/254t rss 12.0G pss 11.1G swap 1.0G majflt 3761 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.1G pss 0.1G | host avail 20.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.75 cpu 14.09 | cgroup 11.6G/max oom_kill 0 | free scratch 312.3G/45324533i tmp 28.7G/1002295i workspace 312.3G/45324533i | repeat-01 collected 26/26 workers (60624 items) tests 12045 done 0 failed | 26 in flight, oldest 102s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
............................................... [558%]
........................................................................ [562%]
..................................................[contention-diag] +2073s soak 33p/266t rss 11.9G pss 11.0G swap 1.0G majflt 3777 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 5 descendant rss 0.0G pss 0.0G | host avail 18.3G/62.7G swapfree 52.9G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.0 cpu 14.46 | cgroup 11.6G/max oom_kill 0 | free scratch 312.0G/45323909i tmp 28.7G/1002295i workspace 312.0G/45323909i | repeat-01 collected 26/26 workers (60624 items) tests 12212 done 0 failed | 26 in flight, oldest 56s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
...................... [565%]
........................................................................ [568%]
........................................................................ [572%]
....[contention-diag] +2089s soak 30p/256t rss 12.0G pss 11.0G swap 1.0G majflt 3800 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.1G pss 0.1G | host avail 20.7G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 0.48 cpu 14.2 | cgroup 11.6G/max oom_kill 0 | free scratch 310.6G/45323264i tmp 28.7G/1002295i workspace 310.6G/45323264i | scratch used 0.2G in 42006 entries | repeat-01 collected 26/26 workers (60624 items) tests 12378 done 0 failed | 26 in flight, oldest 51s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_is_noop_while_filter_input_has_focus
.................................................................... [575%]
........................................................................ [578%]
......................................[contention-diag] +2104s soak 31p/240t rss 11.9G pss 11.0G swap 1.0G majflt 3833 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 18.9G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.79/0.45 io 2.21 cpu 14.52 | cgroup 11.6G/max oom_kill 0 | free scratch 310.2G/45322756i tmp 28.7G/1002295i workspace 310.2G/45322756i | repeat-01 collected 26/26 workers (60624 items) tests 12556 done 0 failed | 26 in flight, oldest 62s gw2 tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_opens_preview_modal
.................................. [581%]
........................................................................ [585%]
..[contention-diag] +2120s soak 30p/249t rss 11.9G pss 11.0G swap 1.0G majflt 3856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.11 io 2.8 cpu 13.43 | cgroup 11.6G/max oom_kill 0 | free scratch 310.0G/45319292i tmp 28.7G/1002295i workspace 310.0G/45319292i | repeat-01 collected 26/26 workers (60624 items) tests 12667 done 0 failed | 26 in flight, oldest 45s gw21 tests/ace/tui/test_plugins_browser_pane_inventory.py::test_install_mark_survives_filter_hiding_marked_row
...................................................................... [588%]
...................................................................[contention-diag] +2135s soak 32p/266t rss 12.0G pss 11.0G swap 1.0G majflt 3898 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 1.12 cpu 10.38 | cgroup 11.6G/max oom_kill 0 | free scratch 309.7G/45320044i tmp 28.7G/1000886i workspace 309.7G/45320044i | repeat-01 collected 26/26 workers (60624 items) tests 12810 done 0 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/test_macro_browser_filter.py::test_slash_reveals_filter_without_changing_selection
..... [591%]
........................................................................ [595%]
...................................[contention-diag] +2151s soak 30p/250t rss 12.0G pss 11.0G swap 1.0G majflt 3915 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 27.3G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.69 cpu 8.87 | cgroup 11.6G/max oom_kill 0 | free scratch 308.8G/45302116i tmp 28.7G/1000842i workspace 308.8G/45302113i | repeat-01 collected 26/26 workers (60624 items) tests 12916 done 0 failed | 26 in flight, oldest 53s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_all_skipped_toasts_reasons_and_cleans_up
..................................... [598%]
.........................................................[contention-diag] +2166s soak 30p/266t rss 12.0G pss 11.0G swap 1.0G majflt 4012 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 21.6G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 16.57 cpu 8.76 | cgroup 11.6G/max oom_kill 0 | free scratch 308.4G/45293116i tmp 28.6G/1000649i workspace 308.4G/45293116i | repeat-01 collected 26/26 workers (60624 items) tests 13013 done 0 failed | 26 in flight, oldest 57s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
............... [601%]
........................................................................ [605%]
........................................................................ [608%]
..................................[contention-diag] +2182s soak 29p/267t rss 12.1G pss 11.1G swap 1.0G majflt 4150 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 1 descendant rss 0.1G pss 0.1G | host avail 22.9G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 10.43 cpu 10.57 | cgroup 11.8G/max oom_kill 0 | free scratch 308.3G/45290164i tmp 28.6G/1000578i workspace 308.3G/45290164i | repeat-01 collected 26/26 workers (60624 items) tests 13200 done 0 failed | 26 in flight, oldest 72s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
...................................... [611%]
........................................................................ [615%]
....[contention-diag] +2197s soak 32p/244t rss 12.0G pss 11.0G swap 1.0G majflt 4265 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 5.58/4.62 io 6.86 cpu 16.81 | cgroup 11.5G/max oom_kill 0 | free scratch 308.3G/45289252i tmp 28.6G/999381i workspace 308.3G/45289252i | repeat-01 collected 26/26 workers (60624 items) tests 13320 done 0 failed | 26 in flight, oldest 87s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.................................................................... [618%]
........................[contention-diag] +2213s soak 31p/235t rss 12.0G pss 11.0G swap 1.0G majflt 4384 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 3 descendant rss 0.0G pss 0.0G | host avail 25.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 1.12/0.93 io 1.6 cpu 23.49 | cgroup 11.5G/max oom_kill 0 | free scratch 308.3G/45288729i tmp 28.5G/998643i workspace 308.3G/45288729i | scratch used 0.2G in 33857 entries (truncated) | repeat-01 collected 26/26 workers (60624 items) tests 13407 done 0 failed | 26 in flight, oldest 48s gw2 tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_disabled_when_not_uv_tool
................................................ [621%]
...............................[contention-diag] +2230s soak 31p/288t rss 12.2G pss 11.2G swap 1.0G majflt 4537 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 3 descendant rss 0.2G pss 0.2G | host avail 25.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.22/0.18 io 0.36 cpu 16.23 | cgroup 11.6G/max oom_kill 0 | free scratch 308.3G/45289289i tmp 28.4G/998368i workspace 308.3G/45289289i | repeat-01 collected 26/26 workers (60624 items) tests 13493 done 0 failed | 26 in flight, oldest 61s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
......................................... [625%]
........................................................................ [628%]
.........[contention-diag] +2245s soak 37p/282t rss 12.1G pss 11.2G swap 1.0G majflt 4469 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 9 descendant rss 0.1G pss 0.1G | host avail 28.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.03 io 0.66 cpu 16.3 | cgroup 11.6G/max oom_kill 0 | free scratch 308.3G/45288393i tmp 28.4G/998324i workspace 308.3G/45288393i | repeat-01 collected 26/26 workers (60624 items) tests 13607 done 0 failed | 26 in flight, oldest 77s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................................................... [631%]
........................................................[contention-diag] +2261s soak 29p/274t rss 12.1G pss 11.1G swap 1.0G majflt 4522 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 1 descendant rss 0.1G pss 0.0G | host avail 27.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 18.64 | cgroup 11.6G/max oom_kill 0 | free scratch 308.3G/45287363i tmp 28.4G/998318i workspace 308.3G/45287363i | repeat-01 collected 26/26 workers (60624 items) tests 13732 done 0 failed | 26 in flight, oldest 92s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
................ [635%]
..............................[contention-diag] +2276s soak 29p/274t rss 12.1G pss 11.1G swap 1.0G majflt 4673 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 1 descendant rss 0.1G pss 0.1G | host avail 27.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 22.01 | cgroup 11.8G/max oom_kill 0 | free scratch 308.3G/45287934i tmp 28.4G/998318i workspace 308.3G/45287934i | repeat-01 collected 26/26 workers (60624 items) tests 13775 done 0 failed | 26 in flight, oldest 107s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.......................................... [638%]
..................................................[contention-diag] +2291s soak 33p/288t rss 12.2G pss 11.2G swap 1.0G majflt 4747 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 5 descendant rss 0.1G pss 0.1G | host avail 28.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.53 | cgroup 11.9G/max oom_kill 0 | free scratch 308.3G/45287659i tmp 28.4G/998316i workspace 308.3G/45287659i | repeat-01 collected 26/26 workers (60624 items) tests 13872 done 0 failed | 26 in flight, oldest 123s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
...................... [641%]
........................................................................ [645%]
...........[contention-diag] +2307s soak 29p/249t rss 12.1G pss 11.1G swap 1.0G majflt 4764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.97 | cgroup 11.9G/max oom_kill 0 | free scratch 308.3G/45287250i tmp 28.4G/998254i workspace 308.3G/45287250i | repeat-01 collected 26/26 workers (60624 items) tests 13976 done 0 failed | 26 in flight, oldest 60s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_real_deck_keys_reach_actions_on_two_and_three_panels
............................................................. [648%]
........................................................................ [651%]
............[contention-diag] +2322s soak 29p/247t rss 12.1G pss 11.1G swap 1.0G majflt 4776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 26.19 | cgroup 11.8G/max oom_kill 0 | free scratch 308.3G/45286690i tmp 28.4G/998253i workspace 308.3G/45286690i | repeat-01 collected 26/26 workers (60624 items) tests 14118 done 0 failed | 26 in flight, oldest 64s gw23 tests/ace/tui/test_link_follow_planner.py::test_second_jump_while_lens_live_restores_original
............................................................ [655%]
........................................................................ [658%]
.....[contention-diag] +2337s soak 29p/262t rss 12.1G pss 11.1G swap 1.0G majflt 4785 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.1G pss 0.0G | host avail 28.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 24.37 | cgroup 11.9G/max oom_kill 0 | free scratch 308.3G/45286192i tmp 28.4G/998253i workspace 308.3G/45286192i | scratch used 0.3G in 48283 entries | repeat-01 collected 26/26 workers (60624 items) tests 14231 done 0 failed | 26 in flight, oldest 56s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
................................................................... [661%]
........................................................................ [665%]
.[contention-diag] +2354s soak 32p/261t rss 12.1G pss 11.1G swap 1.0G majflt 4819 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 4 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 21.73 | cgroup 11.9G/max oom_kill 0 | free scratch 308.3G/45285507i tmp 28.4G/998253i workspace 308.3G/45285507i | repeat-01 collected 26/26 workers (60624 items) tests 14388 done 0 failed | 26 in flight, oldest 73s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
....................................................................... [668%]
........[contention-diag] +2369s soak 29p/254t rss 12.1G pss 11.2G swap 1.0G majflt 4880 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 27.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 20.75 | cgroup 11.8G/max oom_kill 0 | free scratch 308.6G/45312715i tmp 28.4G/998252i workspace 308.6G/45312717i | repeat-01 collected 26/26 workers (60624 items) tests 14478 done 0 failed | 26 in flight, oldest 65s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
................................................................ [671%]
........................................................................ [675%]
.........................................[contention-diag] +2385s soak 34p/260t rss 12.2G pss 11.2G swap 1.0G majflt 4914 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 6 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 20.7 | cgroup 11.9G/max oom_kill 0 | free scratch 312.7G/45317648i tmp 28.3G/998251i workspace 312.7G/45317648i | repeat-01 collected 26/26 workers (60624 items) tests 14654 done 0 failed | 26 in flight, oldest 49s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_opens_edit_modal
............................... [678%]
........................................................................ [681%]
...[contention-diag] +2400s soak 31p/254t rss 12.2G pss 11.3G swap 1.0G majflt 4994 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 3 descendant rss 0.1G pss 0.0G | host avail 32.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 23.23 | cgroup 11.9G/max oom_kill 0 | free scratch 312.7G/45317053i tmp 28.4G/998253i workspace 312.7G/45317053i | repeat-01 collected 26/26 workers (60624 items) tests 14761 done 0 failed | 26 in flight, oldest 52s gw9 tests/ace/tui/test_projects_pane.py::test_new_project_palette_opener_is_one_shot
..................................................................... [685%]
........................................................................ [688%]
...................................[contention-diag] +2416s soak 32p/253t rss 12.3G pss 11.3G swap 1.0G majflt 5048 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 4 descendant rss 0.1G pss 0.1G | host avail 30.7G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 22.04 | cgroup 11.9G/max oom_kill 0 | free scratch 312.7G/45315930i tmp 28.4G/998253i workspace 312.7G/45315930i | repeat-01 collected 26/26 workers (60624 items) tests 14937 done 0 failed | 26 in flight, oldest 59s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
..................................... [691%]
........................................................................ [695%]
...........[contention-diag] +2431s soak 30p/256t rss 12.3G pss 11.3G swap 1.0G majflt 5128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 2 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 20.67 | cgroup 12.0G/max oom_kill 0 | free scratch 312.7G/45314980i tmp 28.4G/998253i workspace 312.7G/45314980i | repeat-01 collected 26/26 workers (60624 items) tests 15041 done 0 failed | 26 in flight, oldest 75s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
............................................................. [698%]
........................................................................ [701%]
........................................................................ [705%]
......[contention-diag] +2446s soak 30p/257t rss 12.3G pss 11.3G swap 1.0G majflt 5175 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 2 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 19.89 | cgroup 12.0G/max oom_kill 0 | free scratch 312.7G/45314025i tmp 28.4G/998253i workspace 312.7G/45314025i | repeat-01 collected 26/26 workers (60624 items) tests 15264 done 0 failed | 26 in flight, oldest 63s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
.................................................................. [708%]
........................................................................ [711%]
........................................................................ [715%]
......[contention-diag] +2462s soak 34p/265t rss 12.3G pss 11.3G swap 1.0G majflt 5234 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 6 descendant rss 0.0G pss 0.0G | host avail 26.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 20.76 | cgroup 12.0G/max oom_kill 0 | free scratch 312.7G/45312874i tmp 28.4G/998253i workspace 312.7G/45312874i | scratch used 0.3G in 54329 entries | repeat-01 collected 26/26 workers (60624 items) tests 15470 done 0 failed | 26 in flight, oldest 66s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................................. [718%]
..........[contention-diag] +2478s soak 33p/256t rss 12.4G pss 11.4G swap 0.9G majflt 5445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 28.0G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 21.03 | cgroup 12.1G/max oom_kill 0 | free scratch 312.7G/45312221i tmp 28.4G/998253i workspace 312.7G/45312221i | repeat-01 collected 26/26 workers (60624 items) tests 15560 done 0 failed | 26 in flight, oldest 82s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.............................................................. [721%]
..............................[contention-diag] +2493s soak 33p/270t rss 12.4G pss 11.4G swap 0.9G majflt 5489 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 26.2G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 22.04 | cgroup 12.2G/max oom_kill 0 | free scratch 312.8G/45317837i tmp 28.4G/998253i workspace 312.8G/45317837i | repeat-01 collected 26/26 workers (60624 items) tests 15642 done 0 failed | 26 in flight, oldest 97s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.......................................... [724%]
........................................................................ [728%]
...........[contention-diag] +2508s soak 31p/265t rss 12.4G pss 11.4G swap 0.9G majflt 5507 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 24.8G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 17.96 | cgroup 12.3G/max oom_kill 0 | free scratch 312.4G/45311229i tmp 28.4G/998253i workspace 312.4G/45311229i | repeat-01 collected 26/26 workers (60624 items) tests 15776 done 0 failed | 26 in flight, oldest 113s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............................................................. [731%]
........................................................................ [734%]
........................................................................ [738%]
........................................................................ [741%]
........................................................................ [744%]
....[contention-diag] +2524s soak 34p/237t rss 12.5G pss 11.4G swap 0.9G majflt 5572 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 6 descendant rss 0.2G pss 0.1G | host avail 30.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.52 cpu 19.18 | cgroup 12.2G/max oom_kill 0 | free scratch 311.2G/45310116i tmp 28.4G/998253i workspace 311.2G/45310116i | repeat-01 collected 26/26 workers (60624 items) tests 16125 done 0 failed | 25 in flight, oldest 128s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................................... [748%]
........................................................................ [751%]
........................................................................ [754%]
........................................................................ [758%]
.........................................................[contention-diag] +2539s soak 33p/255t rss 12.5G pss 11.5G swap 1.0G majflt 5599 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 5 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 25.08 | cgroup 12.2G/max oom_kill 0 | free scratch 311.2G/45309309i tmp 28.4G/998253i workspace 311.2G/45309309i | repeat-01 collected 26/26 workers (60624 items) tests 16459 done 0 failed | 25 in flight, oldest 143s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............... [761%]
........................................................................ [764%]
........................................................................ [768%]
........................................................................ [771%]
........................................................................ [774%]
....[contention-diag] +2554s soak 33p/257t rss 12.4G pss 11.4G swap 0.9G majflt 5633 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 5 descendant rss 0.1G pss 0.0G | host avail 28.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.24 cpu 23.08 | cgroup 12.2G/max oom_kill 0 | free scratch 311.2G/45308372i tmp 28.4G/998253i workspace 311.2G/45308372i | repeat-01 collected 26/26 workers (60624 items) tests 16777 done 0 failed | 26 in flight, oldest 159s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................................... [778%]
........................................................................ [781%]
........................................................................ [784%]
..........[contention-diag] +2570s soak 33p/275t rss 12.6G pss 11.5G swap 0.9G majflt 5753 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 5 descendant rss 0.1G pss 0.1G | host avail 29.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.75 cpu 26.61 | cgroup 12.3G/max oom_kill 0 | free scratch 311.2G/45309649i tmp 28.4G/998253i workspace 311.2G/45309649i | repeat-01 collected 26/26 workers (60624 items) tests 16997 done 0 failed | 26 in flight, oldest 123s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.............................................................. [788%]
........................................................................ [791%]
......................[contention-diag] +2585s soak 38p/264t rss 12.6G pss 11.6G swap 0.9G majflt 5780 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 10 descendant rss 0.2G pss 0.2G | host avail 29.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 26.56 | cgroup 12.4G/max oom_kill 0 | free scratch 311.2G/45308991i tmp 28.4G/998253i workspace 311.2G/45308991i | scratch used 0.3G in 58371 entries | repeat-01 collected 26/26 workers (60624 items) tests 17150 done 0 failed | 26 in flight, oldest 74s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cancel_saves_once_submit_path_quiet
.................................................. [794%]
....................................[contention-diag] +2601s soak 32p/255t rss 12.6G pss 11.5G swap 0.9G majflt 5986 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 4 descendant rss 0.1G pss 0.1G | host avail 27.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.51 cpu 22.38 | cgroup 12.4G/max oom_kill 0 | free scratch 311.1G/45308804i tmp 28.4G/998253i workspace 311.1G/45308804i | repeat-01 collected 26/26 workers (60624 items) tests 17231 done 0 failed | 25 in flight, oldest 57s gw18 tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
.................................... [798%]
........................................................................ [801%]
........................................................................ [804%]
...........................................[contention-diag] +2616s soak 31p/249t rss 12.5G pss 11.5G swap 0.9G majflt 6010 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 3 descendant rss 0.0G pss 0.0G | host avail 26.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 20.61 | cgroup 12.5G/max oom_kill 0 | free scratch 311.1G/45306595i tmp 28.4G/998253i workspace 311.1G/45306595i | repeat-01 collected 26/26 workers (60624 items) tests 17459 done 0 failed | 25 in flight, oldest 72s gw18 tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
............................. [808%]
........................................................................ [811%]
........................................................................ [814%]
........................................................................ [818%]
.....[contention-diag] +2632s soak 29p/253t rss 12.5G pss 11.5G swap 0.9G majflt 6031 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 1 descendant rss 0.0G pss 0.0G | host avail 24.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.01 cpu 21.09 | cgroup 12.3G/max oom_kill 0 | free scratch 311.1G/45305964i tmp 28.4G/998253i workspace 311.1G/45305964i | repeat-01 collected 26/26 workers (60624 items) tests 17713 done 0 failed | 25 in flight, oldest 76s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................................................................... [821%]
........................................................................ [824%]
........................................................................ [828%]
........................................................................ [831%]
....................................[contention-diag] +2647s soak 32p/276t rss 12.5G pss 11.5G swap 0.9G majflt 6058 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 4 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.44 cpu 24.46 | cgroup 12.3G/max oom_kill 0 | free scratch 311.1G/45305217i tmp 28.4G/998253i workspace 311.1G/45305217i | repeat-01 collected 26/26 workers (60624 items) tests 18027 done 0 failed | 26 in flight, oldest 92s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.................................... [834%]
........................................................................ [838%]
............[contention-diag] +2662s soak 31p/255t rss 12.6G pss 11.6G swap 0.9G majflt 6074 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 3 descendant rss 0.1G pss 0.1G | host avail 20.6G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.37/0.18 io 0.45 cpu 18.54 | cgroup 12.3G/max oom_kill 0 | free scratch 310.2G/45304789i tmp 28.4G/998253i workspace 310.2G/45304789i | repeat-01 collected 26/26 workers (60624 items) tests 18140 done 0 failed | 25 in flight, oldest 107s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................................ [841%]
........................................................................ [844%]
.............................[contention-diag] +2678s soak 31p/229t rss 12.5G pss 11.5G swap 0.9G majflt 6104 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 3 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.07/0.03 io 1.13 cpu 18.01 | cgroup 12.3G/max oom_kill 0 | free scratch 309.8G/45304095i tmp 28.4G/998253i workspace 309.8G/45304095i | repeat-01 collected 26/26 workers (60624 items) tests 18314 done 0 failed | 26 in flight, oldest 43s gw22 tests/ace/tui/test_statistics_pane_current_project_seed.py::test_seed_project_not_in_options_leaves_filter_unset
........................................... [848%]
.....................................................................[contention-diag] +2693s soak 32p/240t rss 12.5G pss 11.5G swap 0.9G majflt 6138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 4 descendant rss 0.0G pss 0.0G | host avail 25.2G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.94 cpu 18.25 | cgroup 12.3G/max oom_kill 0 | free scratch 310.3G/45303534i tmp 28.4G/998252i workspace 310.3G/45303534i | repeat-01 collected 26/26 workers (60624 items) tests 18425 done 0 failed | 26 in flight, oldest 36s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_reload_clears_freshness_while_in_progress
... [851%]
........................................................................ [854%]
......................................................................[contention-diag] +2709s soak 33p/252t rss 12.6G pss 11.5G swap 0.9G majflt 6154 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 5 descendant rss 0.0G pss 0.0G | host avail 25.0G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.18 cpu 17.07 | cgroup 12.3G/max oom_kill 0 | free scratch 310.1G/45303276i tmp 28.4G/998251i workspace 310.1G/45303276i | scratch used 0.3G in 61922 entries | repeat-01 collected 26/26 workers (60624 items) tests 18570 done 0 failed | 26 in flight, oldest 50s gw9 tests/ace/tui/test_projects_pane.py::test_configured_cycle_subtab_keys_bubble_and_forward
.. [858%]
........................................................................ [861%]
........................................................................ [864%]
........................................................................ [867%]
...[contention-diag] +2725s soak 33p/236t rss 12.6G pss 11.5G swap 0.9G majflt 6183 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 5 descendant rss 0.0G pss 0.0G | host avail 23.2G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 15.75 | cgroup 12.3G/max oom_kill 0 | free scratch 310.3G/45302197i tmp 28.4G/998251i workspace 310.3G/45302196i | repeat-01 collected 26/26 workers (60624 items) tests 18765 done 0 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
..................................................................... [871%]
........................................................................ [874%]
........................................................................ [877%]
...............................[contention-diag] +2741s soak 34p/251t rss 12.7G pss 11.6G swap 0.9G majflt 6214 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 6 descendant rss 0.1G pss 0.1G | host avail 21.6G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 12.79 | cgroup 12.4G/max oom_kill 0 | free scratch 310.1G/45302809i tmp 28.3G/998207i workspace 310.1G/45302810i | repeat-01 collected 26/26 workers (60624 items) tests 19030 done 0 failed | 26 in flight, oldest 71s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
......................................... [881%]
........................................................................ [884%]
...............................................................[contention-diag] +2756s soak 35p/247t rss 12.6G pss 11.6G swap 0.9G majflt 6237 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 7 descendant rss 0.0G pss 0.0G | host avail 20.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 18.54 | cgroup 12.5G/max oom_kill 0 | free scratch 310.1G/45303008i tmp 28.3G/998238i workspace 310.1G/45303008i | repeat-01 collected 26/26 workers (60624 items) tests 19204 done 0 failed | 26 in flight, oldest 86s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
......... [887%]
........................................................................ [891%]
........................................................................ [894%]
.................................................[contention-diag] +2772s soak 31p/248t rss 12.6G pss 11.6G swap 0.9G majflt 6352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 3 descendant rss 0.0G pss 0.0G | host avail 18.3G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 1.26/1.08 io 1.05 cpu 16.29 | cgroup 12.5G/max oom_kill 0 | free scratch 309.9G/45302213i tmp 28.3G/998238i workspace 309.9G/45302213i | repeat-01 collected 26/26 workers (60624 items) tests 19404 done 0 failed | 26 in flight, oldest 102s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
....................... [897%]
....s................................................................... [901%]
........................................................................ [904%]
........................................................................ [907%]
...........[contention-diag] +2787s soak 31p/244t rss 12.6G pss 11.6G swap 0.9G majflt 6529 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 3 descendant rss 0.0G pss 0.0G | host avail 21.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 3.98/2.64 io 5.54 cpu 13.31 | cgroup 12.4G/max oom_kill 0 | free scratch 309.4G/45301487i tmp 28.3G/998238i workspace 309.4G/45301487i | repeat-01 collected 26/26 workers (60624 items) tests 19654 done 0 failed | 26 in flight, oldest 117s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.....s..s.................................................... [911%]
...................................F[contention-failure] call tests/ace/tui/widgets/test_cycle_edit_coalesce.py::test_cycle_press_builds_highlight_map_once: async def test_cycle_press_builds_highlight_map_once() -> None:
        """One ``ctrl+p`` pays for a single synchronous highlight build."""
        app = _CoalesceApp(bar=True)
        async with app.run_test() as pilot:
            ta = app.query_one(PromptTextArea)
            ta.load_text("#git:foo")
            ta.move_cursor(ta._location_from_absolute(len("#git:foo")))
            ta.focus()
            await pilot.pause()
            patcher, calls = _terminal_build_counter()
            with (
                patcher,
                patch.object(
                    PromptTextArea,
                    "_schedule_jinja_diagnostics_refresh",
                    lambda self: None,
                ),
                _patched_mru(["#git:foo", "#git:bar"]),
            ):
                await pilot.press("ctrl+p")
                await pilot.pause()
            assert ta.text == "#git:bar "
>           assert len(calls) <= 1
E           assert 2 <= 1
E            +  where 2 = len([1, 1])

tests/ace/tui/widgets/test_cycle_edit_coalesce.py:79: AssertionError
.................................... [914%]
........................................................................ [917%]
........................................................................ [921%]
.....................[contention-diag] +2802s soak 30p/262t rss 12.6G pss 11.6G swap 0.9G majflt 6647 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 2 descendant rss 0.0G pss 0.0G | host avail 21.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.9/0.53 io 3.29 cpu 14.33 | cgroup 12.4G/max oom_kill 0 | free scratch 309.2G/45300659i tmp 28.4G/998251i workspace 309.2G/45300659i | repeat-01 collected 26/26 workers (60624 items) tests 19952 done 1 failed | 26 in flight, oldest 61s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
................................................... [924%]
........................................................................ [927%]
........................................................................ [931%]
.............................................................[contention-diag] +2818s soak 38p/275t rss 12.7G pss 11.6G swap 0.9G majflt 6725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.1G pss 0.0G | host avail 29.1G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.95/0.88 io 2.85 cpu 14.2 | cgroup 12.5G/max oom_kill 0 | free scratch 309.0G/45299965i tmp 28.4G/998249i workspace 309.0G/45299965i | repeat-01 collected 26/26 workers (60624 items) tests 20215 done 1 failed | 26 in flight, oldest 61s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_macro_focus_picker_all_clear_key_and_cancel
........... [934%]
........................................................................ [937%]
........................................................................ [941%]
................................................[contention-diag] +2833s soak 37p/262t rss 12.8G pss 11.7G swap 0.9G majflt 6858 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 9 descendant rss 0.1G pss 0.1G | host avail 29.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.23/0.21 io 3.78 cpu 17.43 | cgroup 12.5G/max oom_kill 0 | free scratch 309.0G/45299424i tmp 28.4G/998251i workspace 309.0G/45299424i | scratch used 0.3G in 48725 entries (truncated) | repeat-01 collected 26/26 workers (60624 items) tests 20353 done 1 failed | 25 in flight, oldest 47s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
........................ [944%]
........................................................................ [947%]
........................................................................ [951%]
..............................................[contention-diag] +2850s soak 39p/283t rss 12.7G pss 11.6G swap 0.9G majflt 6912 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 11 descendant rss 0.1G pss 0.0G | host avail 28.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 3.39 cpu 17.48 | cgroup 12.5G/max oom_kill 0 | free scratch 309.0G/45298702i tmp 28.4G/998251i workspace 309.0G/45298702i | repeat-01 collected 26/26 workers (60624 items) tests 20632 done 1 failed | 25 in flight, oldest 64s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
.......................... [954%]
........................................................................ [957%]
........................................................................ [961%]
..............................................................[contention-diag] +2866s soak 33p/264t rss 12.7G pss 11.6G swap 0.9G majflt 7017 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 5 descendant rss 0.1G pss 0.0G | host avail 30.3G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.23 cpu 18.68 | cgroup 12.5G/max oom_kill 0 | free scratch 309.0G/45298106i tmp 28.4G/998251i workspace 309.0G/45298106i | repeat-01 collected 26/26 workers (60624 items) tests 20852 done 1 failed | 26 in flight, oldest 54s gw13 tests/ace/tui/test_patch_filter_bar.py::test_patch_filter_save_slot_grammar_keeps_active_query
.......... [964%]
........................................................................ [967%]
....................................[contention-diag] +2881s soak 38p/271t rss 12.8G pss 11.7G swap 0.9G majflt 7048 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.2G pss 0.1G | host avail 30.0G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.82 cpu 27.22 | cgroup 12.6G/max oom_kill 0 | free scratch 309.0G/45297586i tmp 28.4G/998251i workspace 309.0G/45297586i | repeat-01 collected 26/26 workers (60624 items) tests 20981 done 1 failed | 26 in flight, oldest 64s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.................................... [971%]
........................................................................ [974%]
........................................................................ [977%]
...............[contention-diag] +2896s soak 38p/267t rss 13.0G pss 11.8G swap 0.9G majflt 7090 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.3G pss 0.2G | host avail 28.6G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.79 cpu 26.92 | cgroup 12.7G/max oom_kill 0 | free scratch 309.0G/45296767i tmp 28.4G/998251i workspace 309.0G/45296767i | repeat-01 collected 26/26 workers (60624 items) tests 21175 done 1 failed | 26 in flight, oldest 51s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
......................................................... [981%]
........................................................................ [984%]
........................................................................ [987%]
........................................................................ [991%]
........................................................................ [994%]
............................................................s[contention-diag] +2912s soak 38p/241t rss 13.0G pss 11.8G swap 1.0G majflt 7133 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.3G pss 0.3G | host avail 28.4G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 22.11 | cgroup 12.8G/max oom_kill 0 | free scratch 308.9G/45295263i tmp 28.4G/998251i workspace 308.9G/45295263i | repeat-01 collected 26/26 workers (60624 items) tests 21572 done 1 failed | 25 in flight, oldest 51s gw9 tests/ace/tui/test_projects_pane.py::test_show_new_project_key_clears_filter
........... [997%]
........................................................................ [1001%]
........................................................................ [1004%]
........................................s.[contention-diag] +2927s soak 34p/217t rss 12.9G pss 11.8G swap 0.9G majflt 7166 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 6 descendant rss 0.3G pss 0.2G | host avail 28.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 22.12 | cgroup 12.8G/max oom_kill 0 | free scratch 308.9G/45293540i tmp 28.4G/998251i workspace 308.9G/45293539i | repeat-01 collected 26/26 workers (60624 items) tests 21779 done 1 failed | 26 in flight, oldest 53s gw15 tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
.............................. [1007%]
........................................................................ [1010%]
........................................................................ [1014%]
...................[contention-diag] +2943s soak 36p/229t rss 12.9G pss 11.8G swap 0.9G majflt 7169 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 8 descendant rss 0.2G pss 0.2G | host avail 29.0G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 24.23 | cgroup 12.7G/max oom_kill 0 | free scratch 308.9G/45293439i tmp 28.4G/998251i workspace 308.9G/45293439i | repeat-01 collected 26/26 workers (60624 items) tests 21960 done 1 failed | 26 in flight, oldest 67s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
..................................................... [1017%]
........................................................................ [1020%]
........................................................................ [1024%]
........................................................................ [1027%]
..........[contention-diag] +2958s soak 39p/229t rss 13.0G pss 11.8G swap 0.9G majflt 7293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 11 descendant rss 0.3G pss 0.2G | host avail 29.3G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.99 cpu 23.65 | cgroup 12.8G/max oom_kill 0 | free scratch 308.9G/45293658i tmp 28.4G/998251i workspace 308.9G/45293658i | scratch used 0.4G in 73387 entries | repeat-01 collected 26/26 workers (60624 items) tests 22225 done 1 failed | 26 in flight, oldest 83s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.............................................................. [1030%]
........................................................................ [1034%]
........................................................................ [1037%]
........................................................................ [1040%]
..............................[contention-diag] +2975s soak 39p/227t rss 13.0G pss 11.8G swap 0.9G majflt 7402 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 11 descendant rss 0.3G pss 0.2G | host avail 28.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.65 cpu 26.22 | cgroup 12.8G/max oom_kill 0 | free scratch 308.9G/45293215i tmp 28.4G/998251i workspace 308.9G/45293215i | repeat-01 collected 26/26 workers (60624 items) tests 22560 done 1 failed | 26 in flight, oldest 99s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.......................................... [1044%]
........................................................................ [1047%]
........................................................................ [1050%]
........................................................................ [1054%]
........................................................................ [1057%]
.........[contention-diag] +2990s soak 37p/182t rss 12.9G pss 11.7G swap 0.9G majflt 7447 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 9 descendant rss 0.2G pss 0.1G | host avail 26.6G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 23.29 | cgroup 12.7G/max oom_kill 0 | free scratch 309.4G/45292136i tmp 28.4G/998251i workspace 309.4G/45292136i | repeat-01 collected 26/26 workers (60624 items) tests 22905 done 1 failed | 25 in flight, oldest 115s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............................................................... [1060%]
........................................................................ [1064%]
........................................................................ [1067%]
........................................................................ [1070%]
........................................................................ [1074%]
........................................................................ [1077%]
.......................[contention-diag] +3005s soak 37p/197t rss 12.9G pss 11.7G swap 0.9G majflt 7566 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 9 descendant rss 0.2G pss 0.1G | host avail 26.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.69 cpu 26.94 | cgroup 12.7G/max oom_kill 0 | free scratch 309.4G/45290889i tmp 28.4G/998251i workspace 309.4G/45290889i | repeat-01 collected 26/26 workers (60624 items) tests 23339 done 1 failed | 26 in flight, oldest 130s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
................................................. [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
........................................................................ [1090%]
........................................................................ [1094%]
........................................................................ [1097%]
.................................................[contention-diag] +3021s soak 37p/209t rss 13.0G pss 11.8G swap 0.9G majflt 7698 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 9 descendant rss 0.2G pss 0.2G | host avail 27.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.31 cpu 22.69 | cgroup 12.8G/max oom_kill 0 | free scratch 309.3G/45289784i tmp 28.4G/998251i workspace 309.3G/45289784i | repeat-01 collected 26/26 workers (60624 items) tests 23808 done 1 failed | 26 in flight, oldest 58s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
....................... [1100%]
........................................................................ [1104%]
........................................................................ [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
........................................................................ [1117%]
.........[contention-diag] +3036s soak 37p/201t rss 13.0G pss 11.9G swap 0.9G majflt 7760 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 9 descendant rss 0.3G pss 0.2G | host avail 27.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.21 cpu 22.69 | cgroup 12.9G/max oom_kill 0 | free scratch 309.3G/45288751i tmp 28.4G/998251i workspace 309.3G/45288751i | repeat-01 collected 26/26 workers (60624 items) tests 24200 done 1 failed | 26 in flight, oldest 73s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
............................................................... [1120%]
........................................................................ [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
...............[contention-diag] +3052s soak 47p/200t rss 13.3G pss 12.1G swap 1.1G majflt 7817 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 19 descendant rss 0.6G pss 0.4G | host avail 22.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 19.4 | cgroup 13.3G/max oom_kill 0 | free scratch 309.3G/45287739i tmp 28.4G/998251i workspace 309.3G/45287739i | repeat-01 collected 26/26 workers (60624 items) tests 24480 done 1 failed | 26 in flight, oldest 88s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
......................................................... [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
........................................................................ [1144%]
...............................[contention-diag] +3067s soak 37p/201t rss 13.1G pss 11.9G swap 0.9G majflt 9425 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 9 descendant rss 0.3G pss 0.3G | host avail 20.6G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.25 cpu 15.03 | cgroup 13.0G/max oom_kill 0 | free scratch 309.1G/45286791i tmp 28.4G/998251i workspace 309.1G/45286791i | repeat-01 collected 26/26 workers (60624 items) tests 24781 done 1 failed | 26 in flight, oldest 88s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
......................................... [1147%]
........................................................................ [1150%]
........................................................................ [1153%]
........................................................................ [1157%]
........................................................................ [1160%]
.............[contention-diag] +3082s soak 35p/184t rss 12.9G pss 11.8G swap 0.9G majflt 7947 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 7 descendant rss 0.1G pss 0.1G | host avail 30.1G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.59 cpu 16.78 | cgroup 13.1G/max oom_kill 0 | free scratch 308.9G/45285518i tmp 28.4G/998251i workspace 308.9G/45285518i | scratch used 0.4G in 80856 entries | repeat-01 collected 26/26 workers (60624 items) tests 25128 done 1 failed | 26 in flight, oldest 103s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........................................................... [1163%]
........................................................................ [1167%]
...........................................[contention-diag] +3099s soak 33p/204t rss 12.9G pss 11.8G swap 0.9G majflt 7967 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 27.2G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 16.85 | cgroup 13.1G/max oom_kill 0 | free scratch 308.9G/45284820i tmp 28.4G/998251i workspace 308.9G/45284820i | repeat-01 collected 26/26 workers (60624 items) tests 25311 done 1 failed | 26 in flight, oldest 120s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
............................. [1170%]
........................................................................ [1173%]
........................................................................ [1177%]
.........s.....................................................[contention-diag] +3114s soak 31p/167t rss 12.8G pss 11.7G swap 0.9G majflt 8010 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 3 descendant rss 0.0G pss 0.0G | host avail 29.4G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.07 cpu 17.42 | cgroup 13.1G/max oom_kill 0 | free scratch 308.9G/45284039i tmp 28.4G/998251i workspace 308.9G/45284039i | repeat-01 collected 26/26 workers (60624 items) tests 25546 done 1 failed | 26 in flight, oldest 135s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
......... [1180%]
........................................................................ [1183%]
........................................................................ [1187%]
........................................................................ [1190%]
.............[contention-diag] +3130s soak 33p/169t rss 12.9G pss 11.7G swap 0.9G majflt 8054 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 20.78 | cgroup 13.0G/max oom_kill 0 | free scratch 308.9G/45283602i tmp 28.4G/998251i workspace 308.9G/45283602i | repeat-01 collected 26/26 workers (60624 items) tests 25781 done 1 failed | 26 in flight, oldest 150s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........................................................... [1193%]
........................................................................ [1197%]
..........................[contention-diag] +3145s soak 37p/180t rss 12.9G pss 11.6G swap 0.9G majflt 8101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.3G, 9 descendant rss 0.1G pss 0.1G | host avail 28.6G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 18.53 | cgroup 13.2G/max oom_kill 0 | free scratch 308.9G/45283192i tmp 28.4G/998251i workspace 308.9G/45283192i | repeat-01 collected 26/26 workers (60624 items) tests 25942 done 1 failed | 26 in flight, oldest 166s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.............................................. [1200%]
........................................................................ [1203%]
......[contention-diag] +3160s soak 33p/169t rss 13.0G pss 11.8G swap 0.9G majflt 8152 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 27.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.55 cpu 20.76 | cgroup 13.1G/max oom_kill 0 | free scratch 308.9G/45282912i tmp 28.4G/998249i workspace 308.9G/45282912i | repeat-01 collected 26/26 workers (60624 items) tests 26067 done 1 failed | 25 in flight, oldest 181s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.................................................................. [1207%]
........................................................................ [1210%]
.........................................[contention-diag] +3176s soak 32p/173t rss 12.9G pss 11.8G swap 0.9G majflt 8181 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 4 descendant rss 0.1G pss 0.1G | host avail 31.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 26.46 | cgroup 13.2G/max oom_kill 0 | free scratch 308.9G/45283023i tmp 28.4G/998251i workspace 308.9G/45283023i | repeat-01 collected 26/26 workers (60624 items) tests 26237 done 1 failed | 25 in flight, oldest 196s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
............................... [1213%]
........................................................................ [1217%]
........................................................................ [1220%]
..................................................................[contention-diag] +3191s soak 35p/180t rss 13.0G pss 11.9G swap 0.9G majflt 8211 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 7 descendant rss 0.2G pss 0.1G | host avail 31.2G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 27.31 | cgroup 13.2G/max oom_kill 0 | free scratch 308.9G/45282438i tmp 28.4G/998251i workspace 308.9G/45282438i | repeat-01 collected 26/26 workers (60624 items) tests 26459 done 1 failed | 25 in flight, oldest 212s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...... [1223%]
........................................................................ [1227%]
........................................................................ [1230%]
........................................................................ [1233%]
........................................................................ [1237%]
........................................................................ [1240%]
......................................................[contention-diag] +3206s soak 34p/166t rss 12.9G pss 11.8G swap 0.9G majflt 8303 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 6 descendant rss 0.1G pss 0.0G | host avail 31.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.24/0.12 io 0.15 cpu 24.2 | cgroup 13.2G/max oom_kill 0 | free scratch 308.9G/45281350i tmp 28.4G/998251i workspace 308.9G/45281350i | scratch used 0.4G in 84971 entries | repeat-01 collected 26/26 workers (60624 items) tests 26865 done 1 failed | 25 in flight, oldest 227s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.................. [1243%]
........................................................................ [1247%]
........................................................................ [1250%]
........................................................................ [1253%]
........................................................................ [1257%]
......................[contention-diag] +3223s soak 39p/175t rss 13.1G pss 11.9G swap 0.9G majflt 8414 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 11 descendant rss 0.3G pss 0.2G | host avail 30.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.02 io 0.52 cpu 23.78 | cgroup 13.3G/max oom_kill 0 | free scratch 308.8G/45280284i tmp 28.4G/998251i workspace 308.8G/45280284i | repeat-01 collected 26/26 workers (60624 items) tests 27233 done 1 failed | 25 in flight, oldest 243s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.................................................. [1260%]
........................................................................ [1263%]
........................................................................ [1267%]
.................................................[contention-diag] +3238s soak 41p/169t rss 13.2G pss 12.0G swap 0.9G majflt 8499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 13 descendant rss 0.3G pss 0.2G | host avail 28.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.27 cpu 22.17 | cgroup 13.4G/max oom_kill 0 | free scratch 309.2G/45279432i tmp 28.4G/998251i workspace 309.2G/45279432i | repeat-01 collected 26/26 workers (60624 items) tests 27477 done 1 failed | 24 in flight, oldest 259s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
....................... [1270%]
........................................................................ [1273%]
........................................................................ [1277%]
........................................................................ [1280%]
......................[contention-diag] +3253s soak 34p/170t rss 13.1G pss 11.9G swap 0.9G majflt 8534 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 6 descendant rss 0.2G pss 0.1G | host avail 29.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 24.18 | cgroup 13.3G/max oom_kill 0 | free scratch 308.9G/45278582i tmp 28.4G/998251i workspace 308.9G/45278582i | repeat-01 collected 26/26 workers (60624 items) tests 27735 done 1 failed | 25 in flight, oldest 245s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................................. [1283%]
........................................................................ [1287%]
........................................................................ [1290%]
.[contention-diag] +3269s soak 38p/173t rss 13.1G pss 11.9G swap 0.9G majflt 8564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 10 descendant rss 0.3G pss 0.2G | host avail 28.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 19.63 | cgroup 13.4G/max oom_kill 0 | free scratch 308.9G/45277943i tmp 28.4G/998251i workspace 308.9G/45277943i | repeat-01 collected 26/26 workers (60624 items) tests 27925 done 1 failed | 24 in flight, oldest 260s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................................................... [1293%]
........................................................................ [1296%]
........................................................................ [1300%]
........................................................................ [1303%]
............[contention-diag] +3284s soak 37p/184t rss 13.2G pss 12.0G swap 0.9G majflt 8644 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 9 descendant rss 0.3G pss 0.2G | host avail 27.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 22.1 | cgroup 13.4G/max oom_kill 0 | free scratch 308.8G/45276748i tmp 28.4G/998251i workspace 308.8G/45276748i | repeat-01 collected 26/26 workers (60624 items) tests 28230 done 1 failed | 25 in flight, oldest 184s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................ [1306%]
........................................................................ [1310%]
........................................................................ [1313%]
.......................................................[contention-diag] +3299s soak 33p/178t rss 13.0G pss 11.9G swap 0.9G majflt 8656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 26.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 22.8 | cgroup 13.3G/max oom_kill 0 | free scratch 308.8G/45276061i tmp 28.4G/998251i workspace 308.8G/45276061i | repeat-01 collected 26/26 workers (60624 items) tests 28493 done 1 failed | 25 in flight, oldest 199s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................. [1316%]
........................................................................ [1320%]
........................................................................ [1323%]
.....................[contention-diag] +3315s soak 34p/170t rss 13.0G pss 11.9G swap 0.8G majflt 8704 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 26.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 24.35 | cgroup 13.3G/max oom_kill 0 | free scratch 308.8G/45275423i tmp 28.4G/998251i workspace 308.8G/45275423i | repeat-01 collected 26/26 workers (60624 items) tests 28664 done 1 failed | 25 in flight, oldest 215s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................... [1326%]
........................................................................ [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
........................................................................ [1340%]
..........................[contention-diag] +3330s soak 35p/168t rss 13.1G pss 11.9G swap 0.8G majflt 8728 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 26.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 23.6 | cgroup 13.4G/max oom_kill 0 | free scratch 308.8G/45273873i tmp 28.4G/998251i workspace 308.8G/45273873i | scratch used 0.5G in 92145 entries | repeat-01 collected 26/26 workers (60624 items) tests 29005 done 1 failed | 25 in flight, oldest 230s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................................. [1343%]
........................................................................ [1346%]
........................................................................ [1350%]
........................................................................ [1353%]
.....................................................................[contention-diag] +3347s soak 39p/166t rss 13.1G pss 11.9G swap 0.9G majflt 8782 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 11 descendant rss 0.1G pss 0.1G | host avail 23.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.75 cpu 19.94 | cgroup 13.3G/max oom_kill 0 | free scratch 308.8G/45273306i tmp 28.4G/998251i workspace 308.8G/45273306i | repeat-01 collected 26/26 workers (60624 items) tests 29369 done 1 failed | 25 in flight, oldest 247s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
... [1356%]
........................................................................ [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
.........................[contention-diag] +3362s soak 39p/171t rss 13.1G pss 11.9G swap 0.9G majflt 8849 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 11 descendant rss 0.2G pss 0.1G | host avail 20.8G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 14.98 | cgroup 13.4G/max oom_kill 0 | free scratch 308.5G/45272150i tmp 28.4G/998251i workspace 308.5G/45272150i | repeat-01 collected 26/26 workers (60624 items) tests 29612 done 1 failed | 25 in flight, oldest 262s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................... [1370%]
........................................................................ [1373%]
........................................................................ [1376%]
...............[contention-diag] +3377s soak 35p/169t rss 13.1G pss 11.9G swap 0.9G majflt 8884 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 27.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 18.74 | cgroup 13.3G/max oom_kill 0 | free scratch 308.8G/45271686i tmp 28.4G/998251i workspace 308.8G/45271686i | repeat-01 collected 26/26 workers (60624 items) tests 29813 done 1 failed | 25 in flight, oldest 277s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
......................................................... [1380%]
........................................................................ [1383%]
........................................................................ [1386%]
........................................................................ [1390%]
.................................................[contention-diag] +3393s soak 39p/173t rss 13.1G pss 11.9G swap 0.8G majflt 8934 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 11 descendant rss 0.2G pss 0.1G | host avail 28.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.46/0.46 io 0.51 cpu 18.49 | cgroup 13.4G/max oom_kill 0 | free scratch 308.8G/45271036i tmp 28.4G/998250i workspace 308.8G/45271036i | repeat-01 collected 26/26 workers (60624 items) tests 30142 done 1 failed | 25 in flight, oldest 293s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....................... [1393%]
........................................................................ [1396%]
........................................................................ [1400%]
........................................................................ [1403%]
........................................................................ [1406%]
........................................................................ [1410%]
..........[contention-diag] +3408s soak 32p/159t rss 13.1G pss 11.9G swap 0.8G majflt 8973 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 4 descendant rss 0.1G pss 0.1G | host avail 29.7G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 0.95 cpu 21.47 | cgroup 13.3G/max oom_kill 0 | free scratch 312.1G/45273764i tmp 28.4G/998250i workspace 312.1G/45273764i | repeat-01 collected 26/26 workers (60624 items) tests 30530 done 1 failed | 25 in flight, oldest 308s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................................................. [1413%]
........................................................................ [1416%]
........................................................................ [1420%]
........................................................................ [1423%]
.........................................................[contention-diag] +3424s soak 33p/172t rss 13.1G pss 11.9G swap 0.8G majflt 9065 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 5 descendant rss 0.1G pss 0.1G | host avail 28.7G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.76 cpu 19.82 | cgroup 13.4G/max oom_kill 0 | free scratch 312.1G/45272412i tmp 28.4G/998250i workspace 312.1G/45272412i | repeat-01 collected 26/26 workers (60624 items) tests 30873 done 1 failed | 25 in flight, oldest 324s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............... [1426%]
........................................................................ [1430%]
........................................................................ [1433%]
........................................................................ [1436%]
..[contention-diag] +3439s soak 37p/165t rss 13.2G pss 12.0G swap 0.9G majflt 9107 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 9 descendant rss 0.2G pss 0.1G | host avail 26.0G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 16.88 | cgroup 13.5G/max oom_kill 0 | free scratch 312.1G/45271433i tmp 28.4G/998250i workspace 312.1G/45271433i | repeat-01 collected 26/26 workers (60624 items) tests 31083 done 1 failed | 24 in flight, oldest 339s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................................................................... [1440%]
........................................................................ [1443%]
........................................................................ [1446%]
........................................................................ [1449%]
........................................................................ [1453%]
.........................[contention-diag] +3454s soak 33p/165t rss 13.1G pss 11.9G swap 0.8G majflt 9186 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 5 descendant rss 0.1G pss 0.1G | host avail 27.1G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.02 cpu 21.94 | cgroup 13.4G/max oom_kill 0 | free scratch 312.1G/45270684i tmp 28.4G/998250i workspace 312.1G/45270684i | scratch used 0.5G in 98837 entries | repeat-01 collected 26/26 workers (60624 items) tests 31422 done 1 failed | 25 in flight, oldest 354s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................... [1456%]
........................................................................ [1459%]
........................................................................ [1463%]
........................................................................ [1466%]
........................................[contention-diag] +3471s soak 35p/181t rss 13.2G pss 12.0G swap 0.8G majflt 9275 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 26.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.88 cpu 20.97 | cgroup 13.4G/max oom_kill 0 | free scratch 312.5G/45272908i tmp 28.4G/998250i workspace 312.5G/45272908i | repeat-01 collected 26/26 workers (60624 items) tests 31782 done 1 failed | 24 in flight, oldest 371s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................ [1469%]
........................................................................ [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1483%]
........................................................................ [1486%]
........................................................................ [1489%]
........................................................................ [1493%]
...............[contention-diag] +3486s soak 32p/158t rss 13.2G pss 12.0G swap 0.8G majflt 9314 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 4 descendant rss 0.1G pss 0.1G | host avail 25.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.92 cpu 21.68 | cgroup 13.4G/max oom_kill 0 | free scratch 312.5G/45272650i tmp 28.4G/998250i workspace 312.5G/45272650i | repeat-01 collected 26/26 workers (60624 items) tests 32326 done 1 failed | 24 in flight, oldest 310s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
......................................................... [1496%]
........................................................................ [1499%]
........................................................................ [1503%]
........................................................................ [1506%]
........................................................................ [1509%]
...........................[contention-diag] +3502s soak 32p/165t rss 13.2G pss 12.0G swap 0.9G majflt 9345 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 4 descendant rss 0.1G pss 0.1G | host avail 23.0G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 19.49 | cgroup 13.5G/max oom_kill 0 | free scratch 312.6G/45273431i tmp 28.4G/998250i workspace 312.6G/45273431i | repeat-01 collected 26/26 workers (60624 items) tests 32712 done 1 failed | 24 in flight, oldest 325s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................................. [1513%]
........................................................................ [1516%]
........................................................................ [1519%]
...............................................................[contention-diag] +3517s soak 35p/164t rss 13.1G pss 11.9G swap 0.8G majflt 9380 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 7 descendant rss 0.1G pss 0.0G | host avail 23.9G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 20.38 | cgroup 13.6G/max oom_kill 0 | free scratch 312.6G/45272612i tmp 28.4G/998250i workspace 312.6G/45272612i | repeat-01 collected 26/26 workers (60624 items) tests 32961 done 1 failed | 24 in flight, oldest 341s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
......... [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
.......[contention-diag] +3532s soak 36p/171t rss 13.2G pss 12.0G swap 0.8G majflt 9411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 8 descendant rss 0.2G pss 0.1G | host avail 21.7G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 22.01 | cgroup 13.6G/max oom_kill 0 | free scratch 312.5G/45271904i tmp 28.4G/998250i workspace 312.5G/45271904i | repeat-01 collected 26/26 workers (60624 items) tests 33123 done 1 failed | 23 in flight, oldest 356s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................................................................. [1533%]
........................................................................ [1536%]
........................................................................ [1539%]
............................................................[contention-diag] +3548s soak 37p/167t rss 13.3G pss 12.1G swap 0.8G majflt 9575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 9 descendant rss 0.2G pss 0.2G | host avail 21.1G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 16.88 | cgroup 13.6G/max oom_kill 0 | free scratch 312.2G/45270829i tmp 28.4G/998250i workspace 312.2G/45270829i | repeat-01 collected 26/26 workers (60624 items) tests 33391 done 1 failed | 22 in flight, oldest 371s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............ [1543%]
........................................................................ [1546%]
........................................................................ [1549%]
........................................................................ [1553%]
........................................................................ [1556%]
............................................[contention-diag] +3563s soak 33p/155t rss 13.4G pss 12.1G swap 0.9G majflt 9620 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 5 descendant rss 0.3G pss 0.2G | host avail 27.0G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 20.16 | cgroup 13.7G/max oom_kill 0 | free scratch 312.5G/45270211i tmp 28.4G/998250i workspace 312.5G/45270211i | repeat-01 collected 26/26 workers (60624 items) tests 33736 done 1 failed | 24 in flight, oldest 387s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................ [1559%]
........................................................................ [1563%]
........................................................................ [1566%]
........................................................................ [1569%]
........................................................................ [1573%]
..............[contention-diag] +3578s soak 35p/168t rss 13.4G pss 12.2G swap 0.9G majflt 9671 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 7 descendant rss 0.3G pss 0.2G | host avail 27.1G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.84 cpu 21.63 | cgroup 13.8G/max oom_kill 0 | free scratch 312.5G/45268788i tmp 28.4G/998248i workspace 312.5G/45268788i | scratch used 0.6G in 106074 entries | repeat-01 collected 26/26 workers (60624 items) tests 34041 done 1 failed | 23 in flight, oldest 402s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
.......................................................... [1576%]
........................................................................ [1579%]
........................................................................ [1583%]
........................................................................ [1586%]
....................................[contention-diag] +3595s soak 35p/159t rss 13.5G pss 12.2G swap 0.9G majflt 9688 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 7 descendant rss 0.4G pss 0.3G | host avail 24.5G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.67 cpu 17.42 | cgroup 13.7G/max oom_kill 0 | free scratch 312.5G/45268316i tmp 28.4G/998250i workspace 312.5G/45268316i | repeat-01 collected 26/26 workers (60624 items) tests 34364 done 1 failed | 24 in flight, oldest 419s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
.................................... [1589%]
........................................................................ [1592%]
........................................................................ [1596%]
........................................................................ [1599%]
............s......[contention-diag] +3611s soak 34p/165t rss 13.3G pss 12.1G swap 0.9G majflt 9714 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 6 descendant rss 0.2G pss 0.2G | host avail 25.5G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.44 cpu 17.97 | cgroup 13.7G/max oom_kill 0 | free scratch 312.5G/45267684i tmp 28.4G/998250i workspace 312.5G/45267684i | repeat-01 collected 26/26 workers (60624 items) tests 34646 done 1 failed | 24 in flight, oldest 434s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
..................................................... [1602%]
........................................................................ [1606%]
........................................................................ [1609%]
........................................................................ [1612%]
...............................................................[contention-diag] +3626s soak 35p/173t rss 13.2G pss 12.0G swap 0.8G majflt 9817 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 23.5G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 17.46 | cgroup 13.5G/max oom_kill 0 | free scratch 312.4G/45266220i tmp 28.4G/998250i workspace 312.4G/45266220i | repeat-01 collected 26/26 workers (60624 items) tests 34974 done 1 failed | 24 in flight, oldest 450s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
......... [1616%]
........................................................................ [1619%]
........................................................................ [1622%]
........................................................................ [1626%]
........................................................................ [1629%]
..................................[contention-diag] +3642s soak 35p/178t rss 13.2G pss 12.0G swap 0.8G majflt 9852 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 22.7G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 11.65 | cgroup 13.5G/max oom_kill 0 | free scratch 312.1G/45264117i tmp 28.4G/998250i workspace 312.1G/45264117i | repeat-01 collected 26/26 workers (60624 items) tests 35311 done 1 failed | 24 in flight, oldest 465s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
...................................... [1632%]
........................................................................ [1636%]
........................................................................ [1639%]
........................................................................ [1642%]
......................................................[contention-diag] +3657s soak 33p/179t rss 13.3G pss 12.0G swap 0.8G majflt 9874 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.1G pss 0.1G | host avail 25.9G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 16.64 | cgroup 13.6G/max oom_kill 0 | free scratch 311.8G/45263063i tmp 28.3G/998101i workspace 311.8G/45263063i | repeat-01 collected 26/26 workers (60624 items) tests 35593 done 1 failed | 23 in flight, oldest 313s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
.................. [1646%]
........................................................................ [1649%]
........................................................................ [1652%]
........................................................................ [1656%]
........................................................................ [1659%]
.........................................................[contention-diag] +3672s soak 30p/178t rss 13.2G pss 12.0G swap 0.8G majflt 9910 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 2 descendant rss 0.0G pss 0.0G | host avail 22.4G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 16.18 | cgroup 13.5G/max oom_kill 0 | free scratch 311.8G/45262017i tmp 28.3G/996837i workspace 311.8G/45262017i | repeat-01 collected 26/26 workers (60624 items) tests 35971 done 1 failed | 24 in flight, oldest 328s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
............... [1662%]
........................................................................ [1666%]
........................................................................ [1669%]
........................................................................ [1672%]
...............................................................[contention-diag] +3688s soak 33p/179t rss 13.3G pss 12.1G swap 0.9G majflt 9963 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.1G pss 0.1G | host avail 19.5G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 15.44 | cgroup 13.6G/max oom_kill 0 | free scratch 311.7G/45260821i tmp 28.3G/996803i workspace 311.7G/45260821i | repeat-01 collected 26/26 workers (60624 items) tests 36276 done 1 failed | 24 in flight, oldest 344s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
......... [1676%]
........................................................................ [1679%]
........................................................................ [1682%]
........................................................................ [1686%]
........................[contention-diag] +3703s soak 33p/184t rss 13.3G pss 12.0G swap 0.9G majflt 10050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.0G pss 0.0G | host avail 21.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 4.54/3.77 io 3.31 cpu 12.58 | cgroup 13.2G/max oom_kill 0 | free scratch 311.4G/45259899i tmp 28.3G/995388i workspace 311.4G/45259899i | scratch used 0.4G in 73988 entries (truncated) | repeat-01 collected 26/26 workers (60624 items) tests 36501 done 1 failed | 24 in flight, oldest 359s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
................................................ [1689%]
........................................................................ [1692%]
........................................................................ [1696%]
........................................................................ [1699%]
........................................................................ [1702%]
........................................................................ [1706%]
..............................................[contention-diag] +3721s soak 33p/181t rss 13.4G pss 12.2G swap 0.8G majflt 10075 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.1G pss 0.2G | host avail 20.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.75/0.62 io 0.99 cpu 19.84 | cgroup 13.3G/max oom_kill 0 | free scratch 311.8G/45258483i tmp 28.2G/995065i workspace 311.8G/45258483i | repeat-01 collected 26/26 workers (60624 items) tests 36967 done 1 failed | 24 in flight, oldest 377s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [1709%]
........................................................................ [1712%]
........................................................................ [1716%]
........................................................................ [1719%]
............................................[contention-diag] +3737s soak 31p/183t rss 13.3G pss 12.1G swap 0.8G majflt 10106 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 3 descendant rss 0.1G pss 0.1G | host avail 21.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.18/0.15 io 0.39 cpu 14.85 | cgroup 13.2G/max oom_kill 0 | free scratch 311.6G/45257220i tmp 28.1G/994350i workspace 311.6G/45257220i | repeat-01 collected 26/26 workers (60624 items) tests 37261 done 1 failed | 23 in flight, oldest 393s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1722%]
........................................................................ [1726%]
........................................................................ [1729%]
........................................................................ [1732%]
........................................................................ [1735%]
[contention-diag] +3752s soak 38p/187t rss 13.4G pss 12.1G swap 0.9G majflt 10140 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 10 descendant rss 0.2G pss 0.1G | host avail 26.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.43 cpu 15.45 | cgroup 13.3G/max oom_kill 0 | free scratch 311.2G/45256422i tmp 28.0G/994306i workspace 311.2G/45256422i | repeat-01 collected 26/26 workers (60624 items) tests 37580 done 1 failed | 23 in flight, oldest 408s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
........................................................................ [1739%]
........................................................................ [1742%]
........................................................................ [1745%]
........................................................................ [1749%]
.......................[contention-diag] +3768s soak 40p/187t rss 13.4G pss 12.1G swap 0.9G majflt 10164 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 12 descendant rss 0.1G pss 0.1G | host avail 23.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 0.82 cpu 18.72 | cgroup 13.3G/max oom_kill 0 | free scratch 311.1G/45255622i tmp 28.0G/994297i workspace 311.1G/45255622i | repeat-01 collected 26/26 workers (60624 items) tests 37876 done 1 failed | 24 in flight, oldest 424s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................................................. [1752%]
........................................................................ [1755%]
........................................................................ [1759%]
...............................[contention-diag] +3783s soak 37p/206t rss 13.5G pss 12.2G swap 0.9G majflt 10219 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 9 descendant rss 0.3G pss 0.2G | host avail 26.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.23/0.21 io 1.38 cpu 16.45 | cgroup 13.4G/max oom_kill 0 | free scratch 311.7G/45254935i tmp 28.0G/994298i workspace 311.7G/45254935i | repeat-01 collected 26/26 workers (60624 items) tests 38119 done 1 failed | 24 in flight, oldest 439s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
......................................... [1762%]
.................s...................................................... [1765%]
........................................................................ [1769%]
.............................[contention-diag] +3799s soak 35p/202t rss 13.6G pss 12.3G swap 0.9G majflt 10552 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 7 descendant rss 0.3G pss 0.2G | host avail 26.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.83 cpu 21.18 | cgroup 13.5G/max oom_kill 0 | free scratch 311.5G/45254163i tmp 28.0G/994297i workspace 311.5G/45254163i | repeat-01 collected 26/26 workers (60624 items) tests 38322 done 1 failed | 24 in flight, oldest 454s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.....s..................................... [1772%]
........................................................................ [1775%]
........................................................................ [1779%]
...........................[contention-diag] +3814s soak 37p/183t rss 13.6G pss 12.3G swap 0.9G majflt 10614 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.2G pss 0.1G | host avail 27.0G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.83 cpu 22.18 | cgroup 13.6G/max oom_kill 0 | free scratch 311.4G/45253528i tmp 28.0G/994232i workspace 311.4G/45253528i | repeat-01 collected 26/26 workers (60624 items) tests 38533 done 1 failed | 24 in flight, oldest 304s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................. [1782%]
........................................................................ [1785%]
........................................................................ [1789%]
........................................................................ [1792%]
........................................................................ [1795%]
...........................[contention-diag] +3829s soak 33p/177t rss 13.7G pss 12.4G swap 0.9G majflt 10699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 5 descendant rss 0.2G pss 0.1G | host avail 25.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.69/0.0 io 0.52 cpu 22.92 | cgroup 13.7G/max oom_kill 0 | free scratch 311.4G/45251126i tmp 28.0G/994232i workspace 311.4G/45251126i | scratch used 0.6G in 109736 entries (truncated) | repeat-01 collected 26/26 workers (60624 items) tests 38874 done 1 failed | 24 in flight, oldest 319s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................. [1799%]
........................................................................ [1802%]
........................................F[contention-failure] call tests/test_output.py::test_provider_timer_stops_background_thread: def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
>               timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:109: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {140536925804224, 140536934196928, 140536942589632, 140537858344640, 140538232362816}

    def _wait_for_provider_timer_thread(
        existing_ids: set[int | None],
        *,
        timeout: float = LOAD_TOLERANT_TIMEOUT,
    ) -> threading.Thread:
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            threads = _provider_timer_threads(existing_ids)
            if len(threads) == 1:
                return threads[0]
            time.sleep(0.01)  # sase-test-wait: provider timer thread start under soak
>       raise AssertionError(
            f"sase-provider-timer never appeared within {timeout}s; "
            f"live={_provider_timer_threads(existing_ids)!r}"
        )
E       AssertionError: sase-provider-timer never appeared within 60.0s; live=[]

tests/test_output.py:45: AssertionError
............................... [1805%]
........................................................................ [1809%]
......................................................[contention-diag] +3847s soak 38p/186t rss 13.7G pss 12.4G swap 0.9G majflt 10741 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 0.1G pss 0.1G | host avail 22.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.11/0.0 io 0.37 cpu 19.54 | cgroup 13.7G/max oom_kill 0 | free scratch 311.4G/45250040i tmp 28.0G/994232i workspace 311.4G/45250040i | repeat-01 collected 26/26 workers (60624 items) tests 39198 done 2 failed | 24 in flight, oldest 337s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................. [1812%]
........................................................................ [1815%]
........................................................................ [1819%]
........................................................................ [1822%]
...................................................[contention-diag] +3862s soak 36p/189t rss 13.8G pss 12.5G swap 0.9G majflt 11037 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 0.2G pss 0.2G | host avail 24.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.6 cpu 18.47 | cgroup 13.9G/max oom_kill 0 | free scratch 311.1G/45248949i tmp 28.0G/994232i workspace 311.1G/45248949i | repeat-01 collected 26/26 workers (60624 items) tests 39499 done 2 failed | 24 in flight, oldest 352s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..................... [1825%]
........................................................................ [1829%]
........................................................................ [1832%]
........................................................................ [1835%]
........................................................................ [1839%]
........[contention-diag] +3878s soak 31p/183t rss 13.4G pss 12.1G swap 0.9G majflt 10894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 3 descendant rss 0.0G pss 0.0G | host avail 27.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.07 cpu 20.67 | cgroup 13.6G/max oom_kill 0 | free scratch 311.0G/45248182i tmp 28.0G/994232i workspace 311.0G/45248181i | repeat-01 collected 26/26 workers (60624 items) tests 39800 done 2 failed | 24 in flight, oldest 367s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.........s...................................................... [1842%]
........................................................................ [1845%]
........................................................................ [1849%]
.....................................................[contention-diag] +3893s soak 35p/192t rss 13.5G pss 12.2G swap 0.9G majflt 10951 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 7 descendant rss 0.3G pss 0.2G | host avail 25.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 0.9 cpu 20.64 | cgroup 14.3G/max oom_kill 0 | free scratch 310.6G/45247087i tmp 28.0G/994232i workspace 310.6G/45247087i | repeat-01 collected 26/26 workers (60624 items) tests 40068 done 2 failed | 24 in flight, oldest 383s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................... [1852%]
........................................................................ [1855%]
........................................................................ [1859%]
....................................[contention-diag] +3908s soak 37p/189t rss 13.8G pss 12.4G swap 0.9G majflt 10998 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 9 descendant rss 0.5G pss 0.4G | host avail 26.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.98/0.0 io 1.88 cpu 22.85 | cgroup 14.5G/max oom_kill 0 | free scratch 310.6G/45246963i tmp 28.0G/994232i workspace 310.6G/45246963i | repeat-01 collected 26/26 workers (60624 items) tests 40279 done 2 failed | 24 in flight, oldest 398s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.........s.......................... [1862%]
........................................................................ [1865%]
........................................................................ [1869%]
........................................................................ [1872%]
[contention-diag] +3924s soak 44p/190t rss 13.7G pss 12.3G swap 0.9G majflt 11028 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 16 descendant rss 0.4G pss 0.3G | host avail 28.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.24/0.0 io 2.07 cpu 25.15 | cgroup 13.8G/max oom_kill 0 | free scratch 311.0G/45245573i tmp 28.0G/994232i workspace 311.0G/45245573i | repeat-01 collected 26/26 workers (60624 items) tests 40529 done 2 failed | 24 in flight, oldest 413s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........................................................................ [1875%]
........................................................................ [1878%]
........................................................................ [1882%]
...................................[contention-diag] +3939s soak 37p/192t rss 13.8G pss 12.4G swap 0.9G majflt 11077 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 9 descendant rss 0.5G pss 0.4G | host avail 26.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 1.53 cpu 24.79 | cgroup 13.8G/max oom_kill 0 | free scratch 311.4G/45245250i tmp 28.0G/994229i workspace 311.4G/45245250i | repeat-01 collected 26/26 workers (60624 items) tests 40778 done 2 failed | 24 in flight, oldest 429s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..................................... [1885%]
........................................................................ [1888%]
........................................................................ [1892%]
........................................................................ [1895%]
........................................................................ [1898%]
......................................................................[contention-diag] +3954s soak 41p/195t rss 13.9G pss 12.4G swap 0.9G majflt 11126 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 13 descendant rss 0.5G pss 0.4G | host avail 28.0G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.56 cpu 26.4 | cgroup 13.9G/max oom_kill 0 | free scratch 311.2G/45244283i tmp 28.0G/994229i workspace 311.2G/45244283i | scratch used 0.7G in 126591 entries | repeat-01 collected 26/26 workers (60624 items) tests 41126 done 2 failed | 23 in flight, oldest 444s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.. [1902%]
........................................................................ [1905%]
........................................................................ [1908%]
........................................................................ [1912%]
........................................................................ [1915%]
........................................................................ [1918%]
........................[contention-diag] +3971s soak 40p/188t rss 13.9G pss 12.5G swap 1.0G majflt 11201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 12 descendant rss 0.6G pss 0.5G | host avail 26.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.47 cpu 23.08 | cgroup 14.0G/max oom_kill 0 | free scratch 311.4G/45242445i tmp 28.0G/994228i workspace 311.4G/45242445i | repeat-01 collected 26/26 workers (60624 items) tests 41565 done 2 failed | 24 in flight, oldest 461s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................ [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
........................................................................ [1935%]
.......................[contention-diag] +3987s soak 39p/196t rss 13.7G pss 12.3G swap 0.9G majflt 11257 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 11 descendant rss 0.3G pss 0.3G | host avail 25.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.32 cpu 21.95 | cgroup 13.8G/max oom_kill 0 | free scratch 311.4G/45241028i tmp 28.0G/994225i workspace 311.4G/45241028i | repeat-01 collected 26/26 workers (60624 items) tests 41918 done 2 failed | 24 in flight, oldest 181s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................................................. [1938%]
........................................................................ [1942%]
........................................................................ [1945%]
........................................................................ [1948%]
..............................[contention-diag] +4002s soak 38p/186t rss 13.8G pss 12.4G swap 0.9G majflt 11343 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 10 descendant rss 0.5G pss 0.3G | host avail 27.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.51 cpu 25.75 | cgroup 14.1G/max oom_kill 0 | free scratch 311.4G/45240275i tmp 28.0G/994225i workspace 311.4G/45240275i | repeat-01 collected 26/26 workers (60624 items) tests 42212 done 2 failed | 23 in flight, oldest 196s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
.......................................... [1952%]
........................................................................ [1955%]
........................................................................ [1958%]
........................................................................ [1962%]
........................................................................ [1965%]
.............................................................[contention-diag] +4017s soak 37p/189t rss 13.8G pss 12.4G swap 1.0G majflt 11400 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 9 descendant rss 0.5G pss 0.4G | host avail 25.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.2 cpu 26.22 | cgroup 14.1G/max oom_kill 0 | free scratch 311.4G/45238898i tmp 28.0G/994225i workspace 311.4G/45238898i | repeat-01 collected 26/26 workers (60624 items) tests 42608 done 2 failed | 24 in flight, oldest 211s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........... [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
..............................................................[contention-diag] +4033s soak 47p/207t rss 13.8G pss 12.4G swap 1.0G majflt 11487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.7G, 19 descendant rss 0.5G pss 0.4G | host avail 25.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.07 cpu 23.25 | cgroup 14.1G/max oom_kill 0 | free scratch 311.4G/45237749i tmp 28.0G/994225i workspace 311.4G/45237749i | repeat-01 collected 26/26 workers (60624 items) tests 42824 done 2 failed | 24 in flight, oldest 227s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.......... [1978%]
........................................................................ [1982%]
......................................................................[contention-diag] +4048s soak 39p/201t rss 13.8G pss 12.4G swap 0.9G majflt 11530 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 11 descendant rss 0.5G pss 0.4G | host avail 23.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.68 cpu 20.94 | cgroup 14.1G/max oom_kill 0 | free scratch 311.4G/45236688i tmp 28.0G/994225i workspace 311.4G/45236688i | repeat-01 collected 26/26 workers (60624 items) tests 42977 done 2 failed | 24 in flight, oldest 242s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.. [1985%]
........................................................................ [1988%]
........................................................................ [1992%]
........................................................................ [1995%]
........................................................................ [1998%]
........[contention-diag] +4063s soak 39p/201t rss 13.9G pss 12.5G swap 0.9G majflt 11549 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 11 descendant rss 0.5G pss 0.4G | host avail 23.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.43 cpu 21.41 | cgroup 14.2G/max oom_kill 0 | free scratch 311.4G/45235527i tmp 28.0G/994225i workspace 311.4G/45235527i | repeat-01 collected 26/26 workers (60624 items) tests 43278 done 2 failed | 24 in flight, oldest 257s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................................................ [2002%]
........................................................................ [2005%]
........................................................................ [2008%]
........................................................................ [2012%]
........................................................................ [2015%]
........................................................................ [2018%]
.......................[contention-diag] +4079s soak 37p/175t rss 13.8G pss 12.5G swap 0.9G majflt 11575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 9 descendant rss 0.4G pss 0.4G | host avail 23.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.88 cpu 24.79 | cgroup 14.2G/max oom_kill 0 | free scratch 311.4G/45235064i tmp 28.0G/994224i workspace 311.4G/45235064i | scratch used 0.7G in 135839 entries | repeat-01 collected 26/26 workers (60624 items) tests 43648 done 2 failed | 24 in flight, oldest 273s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................................. [2021%]
........................................................................ [2025%]
........................................................................ [2028%]
........................................................................ [2031%]
.........................[contention-diag] +4096s soak 38p/198t rss 14.1G pss 12.7G swap 1.0G majflt 11777 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 10 descendant rss 0.7G pss 0.6G | host avail 19.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.78/0.0 io 0.74 cpu 16.75 | cgroup 14.4G/max oom_kill 0 | free scratch 311.2G/45233803i tmp 28.0G/994224i workspace 311.2G/45233803i | repeat-01 collected 26/26 workers (60624 items) tests 44001 done 2 failed | 24 in flight, oldest 290s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
............................................... [2035%]
........................................................................ [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
....................................................................[contention-diag] +4111s soak 37p/193t rss 14.0G pss 12.6G swap 0.9G majflt 11808 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 9 descendant rss 0.6G pss 0.5G | host avail 19.1G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.62/0.0 io 0.33 cpu 12.58 | cgroup 14.4G/max oom_kill 0 | free scratch 310.8G/45232831i tmp 28.0G/994224i workspace 310.8G/45232831i | repeat-01 collected 26/26 workers (60624 items) tests 44407 done 2 failed | 23 in flight, oldest 305s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.... [2051%]
........................................................................ [2055%]
........................................................................ [2058%]
........................................................................ [2061%]
........................................................................ [2065%]
........................................................................ [2068%]
...[contention-diag] +4127s soak 35p/196t rss 14.0G pss 12.6G swap 1.0G majflt 11846 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 7 descendant rss 0.6G pss 0.5G | host avail 24.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 2.55 cpu 17.1 | cgroup 14.3G/max oom_kill 0 | free scratch 311.0G/45231488i tmp 28.0G/994222i workspace 311.0G/45231488i | repeat-01 collected 26/26 workers (60624 items) tests 44779 done 2 failed | 23 in flight, oldest 267s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................................... [2071%]
........................................................................ [2075%]
........................................................................ [2078%]
........................................................................ [2081%]
...............[contention-diag] +4142s soak 38p/193t rss 14.2G pss 12.7G swap 0.9G majflt 11918 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 10 descendant rss 0.7G pss 0.6G | host avail 23.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 4.11 cpu 22.3 | cgroup 14.5G/max oom_kill 0 | free scratch 310.8G/45229797i tmp 28.0G/994222i workspace 310.8G/45229797i | repeat-01 collected 26/26 workers (60624 items) tests 45070 done 2 failed | 22 in flight, oldest 282s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......................................................... [2085%]
........................................................................ [2088%]
........................................................................ [2091%]
........................................................................ [2095%]
...................................................[contention-diag] +4157s soak 36p/189t rss 14.2G pss 12.7G swap 1.0G majflt 11953 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 8 descendant rss 0.7G pss 0.7G | host avail 22.8G/62.7G swapfree 52.9G/64.0G oom_kill +0 | psi10 mem 0.4/0.39 io 3.83 cpu 19.44 | cgroup 14.5G/max oom_kill 0 | free scratch 310.7G/45229026i tmp 28.0G/994222i workspace 310.7G/45229026i | repeat-01 collected 26/26 workers (60624 items) tests 45399 done 2 failed | 23 in flight, oldest 298s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...........s......... [2098%]
........................................................................ [2101%]
........................................................................ [2105%]
........................................................................ [2108%]
....................................................................[contention-diag] +4173s soak 41p/202t rss 14.3G pss 12.9G swap 1.0G majflt 12003 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 13 descendant rss 0.9G pss 0.8G | host avail 20.8G/62.7G swapfree 52.9G/64.0G oom_kill +0 | psi10 mem 0.08/0.07 io 3.11 cpu 19.08 | cgroup 14.7G/max oom_kill 0 | free scratch 310.6G/45228257i tmp 28.0G/994222i workspace 310.6G/45228257i | repeat-01 collected 26/26 workers (60624 items) tests 45705 done 2 failed | 22 in flight, oldest 313s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.... [2111%]
........................................................................ [2115%]
........................................................................ [2118%]
........................................................................ [2121%]
........................................................................ [2125%]
........................................................................ [2128%]
........................................................................ [2131%]
............[contention-diag] +4188s soak 36p/185t rss 14.1G pss 12.7G swap 1.0G majflt 12060 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 8 descendant rss 0.7G pss 0.6G | host avail 22.2G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 4.01 cpu 19.48 | cgroup 14.5G/max oom_kill 0 | free scratch 310.6G/45227683i tmp 28.0G/994222i workspace 310.6G/45227683i | repeat-01 collected 26/26 workers (60624 items) tests 46142 done 2 failed | 22 in flight, oldest 329s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................................ [2135%]
........................................................................ [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
................................................[contention-diag] +4204s soak 36p/189t rss 14.2G pss 12.8G swap 1.0G majflt 12105 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 8 descendant rss 0.7G pss 0.7G | host avail 22.5G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 3.7 cpu 24.64 | cgroup 14.6G/max oom_kill 0 | free scratch 310.6G/45226974i tmp 28.0G/994222i workspace 310.6G/45226974i | scratch used 0.7G in 142302 entries | repeat-01 collected 26/26 workers (60624 items) tests 46568 done 2 failed | 21 in flight, oldest 344s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................ [2155%]
........................................................................ [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
........................................................................ [2168%]
........................................................................ [2171%]
........................................................................ [2174%]
........................................................................ [2178%]
........................................................................ [2181%]
...........................................................[contention-diag] +4220s soak 35p/179t rss 14.2G pss 12.8G swap 1.0G majflt 12143 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 7 descendant rss 0.7G pss 0.7G | host avail 22.0G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.65 cpu 22.76 | cgroup 14.6G/max oom_kill 0 | free scratch 310.6G/45225462i tmp 28.0G/994222i workspace 310.6G/45225462i | repeat-01 collected 26/26 workers (60624 items) tests 47274 done 2 failed | 21 in flight, oldest 361s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............. [2184%]
........................................................................ [2188%]
........................................................................ [2191%]
.................................................[contention-diag] +4236s soak 37p/182t rss 14.5G pss 13.0G swap 1.0G majflt 12171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 9 descendant rss 1.0G pss 0.9G | host avail 25.2G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.35 cpu 19.83 | cgroup 14.9G/max oom_kill 0 | free scratch 310.5G/45222664i tmp 28.0G/994222i workspace 310.5G/45222664i | repeat-01 collected 26/26 workers (60624 items) tests 47488 done 2 failed | 21 in flight, oldest 376s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
....................... [2194%]
........................................................................ [2198%]
........................................................................ [2201%]
........................................................................ [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................[contention-diag] +4251s soak 37p/177t rss 14.5G pss 13.0G swap 1.0G majflt 12218 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 9 descendant rss 1.0G pss 0.9G | host avail 23.4G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.91 cpu 20.29 | cgroup 14.9G/max oom_kill 0 | free scratch 309.8G/45224031i tmp 28.0G/994222i workspace 309.8G/45224031i | repeat-01 collected 26/26 workers (60624 items) tests 47923 done 2 failed | 21 in flight, oldest 392s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................ [2214%]
........................................................................ [2218%]
........................................................................ [2221%]
........................................................................ [2224%]
........................................................................ [2228%]
........................................................................ [2231%]
........................................................................ [2234%]
...[contention-diag] +4266s soak 40p/183t rss 14.4G pss 13.0G swap 1.0G majflt 12280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 12 descendant rss 0.9G pss 0.8G | host avail 22.4G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.97 cpu 18.57 | cgroup 14.9G/max oom_kill 0 | free scratch 309.5G/45222560i tmp 28.0G/994222i workspace 309.5G/45222560i | repeat-01 collected 26/26 workers (60624 items) tests 48373 done 2 failed | 21 in flight, oldest 407s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................................... [2238%]
........................................................................ [2241%]
........................................................................ [2244%]
........................................................................ [2248%]
........................................................................ [2251%]
........................................................................ [2254%]
.........................[contention-diag] +4282s soak 37p/183t rss 14.5G pss 13.1G swap 1.0G majflt 12364 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 9 descendant rss 1.0G pss 0.9G | host avail 22.3G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.37 cpu 19.41 | cgroup 15.0G/max oom_kill 0 | free scratch 309.4G/45221994i tmp 28.0G/994222i workspace 309.4G/45221994i | repeat-01 collected 26/26 workers (60624 items) tests 48838 done 2 failed | 20 in flight, oldest 351s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................... [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
..............................................[contention-diag] +4297s soak 37p/187t rss 14.5G pss 13.0G swap 1.1G majflt 12451 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 11.7G, 9 descendant rss 1.1G pss 0.9G | host avail 22.2G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.83 cpu 17.41 | cgroup 14.9G/max oom_kill 0 | free scratch 309.3G/45221032i tmp 28.4G/998123i workspace 309.3G/45221032i | repeat-01 collected 26/26 workers (60624 items) tests 49217 done 2 failed | 19 in flight, oldest 366s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......................... [2274%]
........................................................................ [2278%]
........................................................................ [2281%]
........................................................................ [2284%]
..........................................[contention-diag] +4313s soak 42p/194t rss 14.5G pss 12.8G swap 1.3G majflt 12765 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.6G, 14 descendant rss 1.2G pss 0.9G | host avail 22.6G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.76/0.26 io 3.21 cpu 15.05 | cgroup 14.7G/max oom_kill 0 | free scratch 309.0G/45219632i tmp 28.4G/998123i workspace 309.0G/45219632i | repeat-01 collected 26/26 workers (60624 items) tests 49501 done 2 failed | 20 in flight, oldest 382s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................. [2288%]
........................................................................ [2291%]
........................................................................ [2294%]
........................................................................ [2298%]
........................................................................ [2301%]
...............[contention-diag] +4328s soak 42p/200t rss 14.4G pss 12.9G swap 1.3G majflt 12869 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.5G, 14 descendant rss 1.1G pss 1.0G | host avail 24.9G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.24/0.06 io 4.0 cpu 20.05 | cgroup 14.8G/max oom_kill 0 | free scratch 309.3G/45219701i tmp 28.4G/998123i workspace 309.3G/45219701i | scratch used 0.8G in 149396 entries | repeat-01 collected 26/26 workers (60624 items) tests 49802 done 2 failed | 19 in flight, oldest 397s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
......................................................... [2304%]
........................................................................ [2307%]
........................................................................ [2311%]
........................................................................ [2314%]
........................................................................ [2317%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
...................[contention-diag] +4345s soak 45p/207t rss 14.5G pss 13.0G swap 1.3G majflt 12939 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.5G, 17 descendant rss 1.2G pss 1.1G | host avail 24.0G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.9/0.87 io 2.68 cpu 20.76 | cgroup 14.8G/max oom_kill 0 | free scratch 309.3G/45218104i tmp 28.4G/998123i workspace 309.3G/45218104i | repeat-01 collected 26/26 workers (60624 items) tests 50415 done 2 failed | 17 in flight, oldest 415s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
..................................................... [2331%]
........................................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2341%]
........................................................................ [2344%]
........................................................................ [2347%]
........................................................................ [2351%]
........................................................................ [2354%]
.....................................................[contention-diag] +4361s soak 36p/173t rss 14.2G pss 12.8G swap 1.3G majflt 13073 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.6G, 8 descendant rss 0.9G pss 0.9G | host avail 21.1G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.3/0.17 io 3.48 cpu 14.69 | cgroup 14.5G/max oom_kill 0 | free scratch 309.1G/45216560i tmp 28.4G/998122i workspace 309.1G/45216560i | repeat-01 collected 26/26 workers (60624 items) tests 51016 done 2 failed | 18 in flight, oldest 430s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................... [2357%]
........................................................................ [2361%]
........................................................................ [2364%]
........................................................................ [2367%]
........................................................................ [2371%]
.................................................[contention-diag] +4376s soak 40p/180t rss 14.4G pss 12.9G swap 1.3G majflt 13174 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.5G, 12 descendant rss 1.1G pss 1.0G | host avail 24.3G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.07/0.04 io 2.87 cpu 16.23 | cgroup 14.7G/max oom_kill 0 | free scratch 308.3G/45215391i tmp 28.4G/998122i workspace 308.3G/45215391i | repeat-01 collected 26/26 workers (60624 items) tests 51380 done 2 failed | 17 in flight, oldest 445s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................... [2374%]
............................................s........................... [2377%]
........................................................................ [2381%]
..............................[contention-diag] +4392s soak 37p/181t rss 14.5G pss 12.9G swap 1.3G majflt 13244 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.6G, 9 descendant rss 1.1G pss 1.0G | host avail 26.7G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 3.58 cpu 18.34 | cgroup 14.9G/max oom_kill 0 | free scratch 308.5G/45214163i tmp 28.3G/998080i workspace 308.5G/45214163i | repeat-01 collected 26/26 workers (60624 items) tests 51581 done 2 failed | 18 in flight, oldest 461s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......................................... [2384%]
........................................................................ [2387%]
........................................................................ [2391%]
........................................................................ [2394%]
......................................................[contention-diag] +4407s soak 37p/168t rss 14.5G pss 13.0G swap 1.3G majflt 13372 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.6G, 9 descendant rss 1.2G pss 1.1G | host avail 27.3G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.15/0.0 io 5.63 cpu 19.84 | cgroup 15.0G/max oom_kill 0 | free scratch 308.5G/45213472i tmp 28.3G/998109i workspace 308.5G/45213472i | repeat-01 collected 26/26 workers (60624 items) tests 51894 done 2 failed | 18 in flight, oldest 476s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.................. [2397%]
........................................................................ [2401%]
........................................................................ [2404%]
........................................................................ [2407%]
........................................................................ [2411%]
........................................................................ [2414%]
........................[contention-diag] +4423s soak 40p/177t rss 14.5G pss 13.0G swap 1.3G majflt 13438 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.0G pss 11.6G, 12 descendant rss 1.2G pss 1.1G | host avail 26.7G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 3.65 cpu 21.89 | cgroup 15.0G/max oom_kill 0 | free scratch 308.5G/45212209i tmp 28.3G/998109i workspace 308.5G/45212209i | repeat-01 collected 26/26 workers (60624 items) tests 52287 done 2 failed | 17 in flight, oldest 492s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................ [2417%]
........................................................................ [2421%]
........................................................................ [2424%]
........................................................................ [2427%]
...........................s............................................ [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
........................................................................ [2441%]
.....................................................[contention-diag] +4438s soak 34p/166t rss 14.3G pss 12.8G swap 1.3G majflt 13489 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 6 descendant rss 0.9G pss 0.9G | host avail 26.3G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.27 cpu 20.67 | cgroup 14.9G/max oom_kill 0 | free scratch 308.5G/45210415i tmp 28.3G/998109i workspace 308.5G/45210415i | repeat-01 collected 26/26 workers (60624 items) tests 52879 done 2 failed | 18 in flight, oldest 507s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................... [2444%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2454%]
........................................................................ [2457%]
........................................................................ [2460%]
........................................................................ [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
........................[contention-diag] +4453s soak 38p/178t rss 14.4G pss 12.9G swap 1.3G majflt 13644 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 10 descendant rss 1.0G pss 1.0G | host avail 27.1G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.35 cpu 17.65 | cgroup 14.9G/max oom_kill 0 | free scratch 308.4G/45208433i tmp 28.4G/998122i workspace 308.4G/45208434i | scratch used 0.8G in 159490 entries | repeat-01 collected 26/26 workers (60624 items) tests 53398 done 2 failed | 17 in flight, oldest 522s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................................ [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
........................................................................ [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
.............................................................[contention-diag] +4470s soak 37p/167t rss 14.4G pss 13.0G swap 1.3G majflt 13695 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 9 descendant rss 1.1G pss 1.0G | host avail 26.2G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.84 cpu 14.23 | cgroup 15.0G/max oom_kill 0 | free scratch 308.3G/45206388i tmp 28.3G/998109i workspace 308.3G/45206388i | repeat-01 collected 26/26 workers (60624 items) tests 54242 done 2 failed | 15 in flight, oldest 540s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........... [2507%]
........................................................................ [2510%]
........................................................................ [2514%]
........................................................................ [2517%]
........................................................................ [2520%]
........................................................................ [2524%]
........................................................................ [2527%]
........................................................................ [2530%]
........................................................................ [2534%]
........................................................................ [2537%]
........................................................[contention-diag] +4486s soak 38p/176t rss 14.6G pss 13.1G swap 1.3G majflt 13740 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 10 descendant rss 1.2G pss 1.1G | host avail 24.5G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.41/0.26 io 3.06 cpu 16.39 | cgroup 15.1G/max oom_kill 0 | free scratch 308.1G/45204524i tmp 28.3G/998109i workspace 308.1G/45204524i | repeat-01 collected 26/26 workers (60624 items) tests 54961 done 2 failed | 16 in flight, oldest 555s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................ [2540%]
........................................................................ [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
........................................................................ [2554%]
........................................................................ [2557%]
........................................[contention-diag] +4501s soak 42p/186t rss 14.8G pss 13.2G swap 1.3G majflt 13834 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 14 descendant rss 1.4G pss 1.3G | host avail 23.6G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.08/0.05 io 2.37 cpu 18.11 | cgroup 15.2G/max oom_kill 0 | free scratch 308.0G/45204299i tmp 28.3G/998109i workspace 308.0G/45204299i | repeat-01 collected 26/26 workers (60624 items) tests 55402 done 2 failed | 16 in flight, oldest 570s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................ [2560%]
........................................................................ [2564%]
........................................................................ [2567%]
..............................................................[contention-diag] +4517s soak 40p/187t rss 15.0G pss 13.4G swap 1.3G majflt 13919 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 12 descendant rss 1.6G pss 1.5G | host avail 22.8G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 2.41 cpu 19.52 | cgroup 15.5G/max oom_kill 0 | free scratch 307.9G/45203339i tmp 28.3G/998109i workspace 307.9G/45203339i | repeat-01 collected 26/26 workers (60624 items) tests 55635 done 2 failed | 16 in flight, oldest 586s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......... [2570%]
........................................................................ [2574%]
........................................................................ [2577%]
........................................................................ [2580%]
........................................................................ [2584%]
...........................................[contention-diag] +4532s soak 42p/180t rss 13.7G pss 12.2G swap 1.3G majflt 13967 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 14 descendant rss 0.3G pss 0.3G | host avail 22.7G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 2.24 cpu 19.2 | cgroup 14.3G/max oom_kill 0 | free scratch 307.8G/45203688i tmp 28.4G/998122i workspace 307.8G/45203688i | repeat-01 collected 26/26 workers (60624 items) tests 55983 done 2 failed | 15 in flight, oldest 95s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............................. [2587%]
........................................................................ [2590%]
..................................................................s..... [2593%]
.....................................................[contention-diag] +4547s soak 43p/180t rss 13.8G pss 12.3G swap 1.2G majflt 14075 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.6G, 15 descendant rss 0.5G pss 0.4G | host avail 23.2G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.28/0.01 io 1.33 cpu 16.99 | cgroup 14.3G/max oom_kill 0 | free scratch 307.8G/45202589i tmp 28.4G/998122i workspace 307.8G/45202589i | repeat-01 collected 26/26 workers (60624 items) tests 56206 done 2 failed | 15 in flight, oldest 111s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
................... [2597%]
........................................................................ [2600%]
........................................................................ [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
.........................................................[contention-diag] +4563s soak 45p/190t rss 14.0G pss 12.4G swap 1.3G majflt 14103 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 17 descendant rss 0.6G pss 0.5G | host avail 22.1G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 1.05 cpu 19.82 | cgroup 14.4G/max oom_kill 0 | free scratch 307.7G/45202157i tmp 28.4G/998122i workspace 307.7G/45202157i | repeat-01 collected 26/26 workers (60624 items) tests 56643 done 2 failed | 14 in flight, oldest 126s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............... [2617%]
........................................................................ [2620%]
........................................................................ [2623%]
........................................................................ [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
........................................................................ [2637%]
........................................................................ [2640%]
.........................................[contention-diag] +4578s soak 38p/163t rss 13.5G pss 12.0G swap 1.2G majflt 14250 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 10 descendant rss 0.2G pss 0.1G | host avail 22.9G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.75 cpu 21.6 | cgroup 14.1G/max oom_kill 0 | free scratch 307.7G/45200739i tmp 28.4G/998122i workspace 307.7G/45200739i | scratch used 0.9G in 166537 entries (truncated) | repeat-01 collected 26/26 workers (60624 items) tests 57082 done 2 failed | 14 in flight, oldest 141s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............................... [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
........................................................................ [2657%]
........................................................................ [2660%]
........................................................................ [2663%]
............[contention-diag] +4596s soak 33p/161t rss 13.5G pss 12.0G swap 1.2G majflt 14365 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.21 cpu 15.77 | cgroup 14.1G/max oom_kill 0 | free scratch 307.6G/45199288i tmp 28.4G/998122i workspace 307.6G/45199288i | repeat-01 collected 26/26 workers (60624 items) tests 57684 done 2 failed | 13 in flight, oldest 72s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................................................ [2667%]
........................................................................ [2670%]
........................................................................ [2673%]
........................................................................ [2677%]
........................................................................ [2680%]
......................s............................F[contention-failure] call tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_owner_child_shares_wrappe0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd778ddf0b0>

    @NEEDS_POSIX
    @NEEDS_SASE
    def test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A TERM-ignoring child under an owner dies with the wrapper's group."""
    
        home = _home(monkeypatch, tmp_path)
        env = _env(home)
        env["SASE_MONITOR_ID"] = "fixture-owner"
        pidfile = tmp_path / "child.pid"
        wrapper = subprocess.Popen(
            [
                str(SASE),
                "tool",
                "run",
                "--",
                "sh",
                "-c",
                f'trap "" TERM; echo $$ > {pidfile}; exec sleep 60',
            ],
            env=env,
            cwd=tmp_path,
            start_new_session=True,
            stdout=subprocess.DEVNULL,
            stderr=subprocess.DEVNULL,
        )
        child_pid: int | None = None
        try:
            run = _wait_running(env)
            child_pid = _wait_pidfile(pidfile)
            # The child joins the wrapper's own process group so the owner's
            # killpg reaches the whole tree.
            assert os.getpgid(child_pid) == wrapper.pid
            observed = _wait_child_facts(str(run["run_id"]))
            assert observed["child_pgid"] == wrapper.pid
            os.killpg(wrapper.pid, signal.SIGTERM)
            time.sleep(1.0)  # sase-test-wait: TERM is ignored, nothing exits yet
            assert _alive(child_pid)
            assert wrapper.poll() is None
            # Pass the 5 s supervisor grace: the wrapper must skip its own
            # SIGKILL escalation under a live owner, so the child survives until
            # the owner itself escalates.
            time.sleep(4.5)  # sase-test-wait: outlast TERM_ESCALATE_SECONDS
            assert _alive(child_pid)
            assert wrapper.poll() is None
            os.killpg(wrapper.pid, signal.SIGKILL)
            wrapper.wait(timeout=5)
>           assert not _alive(child_pid)
E           assert not True
E            +  where True = _alive(413765)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_wrapper_fidelity.py:231: AssertionError
.................... [2683%]
........................................................................ [2687%]
................................[contention-diag] +4611s soak 34p/157t rss 13.5G pss 12.0G swap 1.2G majflt 14395 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 25.6G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.98 cpu 12.65 | cgroup 14.1G/max oom_kill 0 | free scratch 307.7G/45198069i tmp 28.4G/998122i workspace 307.7G/45198069i | repeat-01 collected 26/26 workers (60624 items) tests 58204 done 3 failed | 12 in flight, oldest 87s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
........................................ [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
........................................................................ [2700%]
........................................................................ [2703%]
........................................................................ [2707%]
........................................................................ [2710%]
........................................................................ [2713%]
................................[contention-diag] +4627s soak 32p/157t rss 13.4G pss 12.0G swap 1.2G majflt 14431 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 4 descendant rss 0.0G pss 0.0G | host avail 25.3G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.51 cpu 12.18 | cgroup 14.0G/max oom_kill 0 | free scratch 307.2G/45197801i tmp 28.4G/998122i workspace 307.2G/45197801i | repeat-01 collected 26/26 workers (60624 items) tests 58755 done 3 failed | 7 in flight, oldest 103s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
........................................ [2717%]
........................................................................ [2720%]
........................................................................ [2723%]
........................................................................ [2727%]
....[contention-diag] +4642s soak 33p/155t rss 13.5G pss 12.0G swap 1.2G majflt 14453 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 5 descendant rss 0.1G pss 0.0G | host avail 20.2G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.9/0.75 io 3.85 cpu 12.18 | cgroup 14.1G/max oom_kill 0 | free scratch 307.1G/45198540i tmp 28.4G/998122i workspace 307.1G/45198540i | repeat-01 collected 26/26 workers (60624 items) tests 59004 done 3 failed | 7 in flight, oldest 118s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.................................................................... [2730%]
........................................................................ [2733%]
........................................................................ [2736%]
........................................................................ [2740%]
........................................................................ [2743%]
........[contention-diag] +4658s soak 36p/162t rss 13.5G pss 12.0G swap 1.2G majflt 14506 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 8 descendant rss 0.1G pss 0.1G | host avail 21.1G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.22/0.19 io 5.17 cpu 12.68 | cgroup 14.1G/max oom_kill 0 | free scratch 307.0G/45198253i tmp 28.4G/998121i workspace 307.0G/45198253i | repeat-01 collected 26/26 workers (60624 items) tests 59405 done 3 failed | 6 in flight, oldest 19s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
................................................................ [2746%]
........................................................................ [2750%]
........................................................................ [2753%]
.....................................................................[contention-diag] +4673s soak 33p/156t rss 13.5G pss 12.0G swap 1.2G majflt 14541 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.6G, 5 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.22/0.21 io 3.7 cpu 13.18 | cgroup 13.7G/max oom_kill 0 | free scratch 306.9G/45197589i tmp 28.4G/998122i workspace 306.9G/45197589i | repeat-01 collected 26/26 workers (60624 items) tests 59681 done 3 failed | 6 in flight, oldest 35s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
... [2756%]
........................................................................ [2760%]
........................................................................ [2763%]
........................................................................ [2766%]
........................................................................ [2770%]
........................................................ssss.....[contention-diag] +4689s soak 33p/152t rss 13.9G pss 12.0G swap 1.3G majflt 14576 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.0G pss 11.4G, 5 descendant rss 0.5G pss 0.2G | host avail 20.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 5.54 cpu 13.8 | cgroup 13.6G/max oom_kill 0 | free scratch 306.9G/45197150i tmp 28.4G/998122i workspace 306.9G/45197150i | repeat-01 collected 26/26 workers (60624 items) tests 60017 done 3 failed | 5 in flight, oldest 2s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_stops_unjoined_run_when_starter_dies | 10 hazardous kill call(s)
....... [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
........................................................................ [2786%]
........................................................................ [2790%]
........................................................................ [2793%]
........................................................................ [2796%]
.................[contention-diag] +4704s soak 32p/150t rss 13.3G pss 11.8G swap 1.4G majflt 14735 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.8G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 18.0G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 4.44/3.93 io 8.13 cpu 8.78 | cgroup 13.0G/max oom_kill 0 | free scratch 306.9G/45197586i tmp 28.4G/998122i workspace 306.9G/45197586i | scratch used 0.1G in 19442 entries (truncated) | repeat-01 collected 26/26 workers (60624 items) tests 60501 done 3 failed | 2 in flight, oldest 2s gw20 tests/tool/test_handoff.py::test_handoff_secret_never_reaches_proc_row | 10 hazardous kill call(s)
....................................................... [2800%]
                                                                         [100%][contention-diag] +4721s soak 32p/138t rss 13.2G pss 11.7G swap 1.5G majflt 20859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.8G pss 11.3G, 4 descendant rss 0.0G pss 0.0G | host avail 22.6G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 5.39/1.01 io 5.23 cpu 10.53 | cgroup 13.0G/max oom_kill 0 | free scratch 306.8G/45199427i tmp 28.4G/998121i workspace 306.8G/45199427i | repeat-01 collected 26/26 workers (60624 items) tests 60598 done 3 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
__________________ test_cycle_press_builds_highlight_map_once __________________
[gw22] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

    async def test_cycle_press_builds_highlight_map_once() -> None:
        """One ``ctrl+p`` pays for a single synchronous highlight build."""
        app = _CoalesceApp(bar=True)
        async with app.run_test() as pilot:
            ta = app.query_one(PromptTextArea)
            ta.load_text("#git:foo")
            ta.move_cursor(ta._location_from_absolute(len("#git:foo")))
            ta.focus()
            await pilot.pause()
            patcher, calls = _terminal_build_counter()
            with (
                patcher,
                patch.object(
                    PromptTextArea,
                    "_schedule_jinja_diagnostics_refresh",
                    lambda self: None,
                ),
                _patched_mru(["#git:foo", "#git:bar"]),
            ):
                await pilot.press("ctrl+p")
                await pilot.pause()
            assert ta.text == "#git:bar "
>           assert len(calls) <= 1
E           assert 2 <= 1
E            +  where 2 = len([1, 1])

tests/ace/tui/widgets/test_cycle_edit_coalesce.py:79: AssertionError
_________________ test_provider_timer_stops_background_thread __________________
[gw5] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

    def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
>               timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:109: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {140536925804224, 140536934196928, 140536942589632, 140537858344640, 140538232362816}

    def _wait_for_provider_timer_thread(
        existing_ids: set[int | None],
        *,
        timeout: float = LOAD_TOLERANT_TIMEOUT,
    ) -> threading.Thread:
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            threads = _provider_timer_threads(existing_ids)
            if len(threads) == 1:
                return threads[0]
            time.sleep(0.01)  # sase-test-wait: provider timer thread start under soak
>       raise AssertionError(
            f"sase-provider-timer never appeared within {timeout}s; "
            f"live={_provider_timer_threads(existing_ids)!r}"
        )
E       AssertionError: sase-provider-timer never appeared within 60.0s; live=[]

tests/test_output.py:45: AssertionError
----------------------------- Captured stdout call -----------------------------
✅ Short operation completed in 01:00
___ test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors ___
[gw9] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_owner_child_shares_wrappe0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fd778ddf0b0>

    @NEEDS_POSIX
    @NEEDS_SASE
    def test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        """A TERM-ignoring child under an owner dies with the wrapper's group."""
    
        home = _home(monkeypatch, tmp_path)
        env = _env(home)
        env["SASE_MONITOR_ID"] = "fixture-owner"
        pidfile = tmp_path / "child.pid"
        wrapper = subprocess.Popen(
            [
                str(SASE),
                "tool",
                "run",
                "--",
                "sh",
                "-c",
                f'trap "" TERM; echo $$ > {pidfile}; exec sleep 60',
            ],
            env=env,
            cwd=tmp_path,
            start_new_session=True,
            stdout=subprocess.DEVNULL,
            stderr=subprocess.DEVNULL,
        )
        child_pid: int | None = None
        try:
            run = _wait_running(env)
            child_pid = _wait_pidfile(pidfile)
            # The child joins the wrapper's own process group so the owner's
            # killpg reaches the whole tree.
            assert os.getpgid(child_pid) == wrapper.pid
            observed = _wait_child_facts(str(run["run_id"]))
            assert observed["child_pgid"] == wrapper.pid
            os.killpg(wrapper.pid, signal.SIGTERM)
            time.sleep(1.0)  # sase-test-wait: TERM is ignored, nothing exits yet
            assert _alive(child_pid)
            assert wrapper.poll() is None
            # Pass the 5 s supervisor grace: the wrapper must skip its own
            # SIGKILL escalation under a live owner, so the child survives until
            # the owner itself escalates.
            time.sleep(4.5)  # sase-test-wait: outlast TERM_ESCALATE_SECONDS
            assert _alive(child_pid)
            assert wrapper.poll() is None
            os.killpg(wrapper.pid, signal.SIGKILL)
            wrapper.wait(timeout=5)
>           assert not _alive(child_pid)
E           assert not True
E            +  where True = _alive(413765)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_wrapper_fidelity.py:231: AssertionError
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    path = os.fspath(arg)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_pane_review.py::test_unreviewed_dots_only_newer_than_watermark
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:472: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    __dict__['method_calls'] = _CallList()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _recheck_grammar_key at 0x7f888dd45e00>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/weakref.py:369: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def remove(k, selfref=ref(self)):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _record_history_async.<locals>._record at 0x7f88999e5b40>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/compose.py:97: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    app._compose_stacks.pop()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_collapsed_panel_selection.py::test_focused_collapsed_panel_has_no_selected_agent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/_contention_progress.py:303: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    def __call__(self, event: str, args: tuple[Any, ...]) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_restore_proof.py::test_proof_single_restore_emits_one_toast_and_marks_overlay
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/content_layout.py:80: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    payload: Mapping[str, Any] = binding(
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

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2699041) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=2698326) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=2699794) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=2698632) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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
  <frozen os>:888: DeprecationWarning: This process (pid=2698326) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=2699902) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
599.52s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
468.38s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
461.31s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
455.42s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
422.45s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
417.93s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
370.67s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
340.98s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
333.72s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
317.10s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
313.79s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
266.66s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
265.54s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
205.94s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
199.02s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
187.30s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
173.55s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
167.90s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
156.14s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
150.47s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
=========================== short test summary info ============================
FAILED tests/ace/tui/widgets/test_cycle_edit_coalesce.py::test_cycle_press_builds_highlight_map_once
FAILED tests/test_output.py::test_provider_timer_stops_background_thread - As...
FAILED tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors
==== 3 failed, 60601 passed, 21 skipped, 111 warnings in 4723.01s (1:18:43) ====
[contention-diag] +4732s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 494 | 1 parent rss 0.0G pss 0.0G | host avail 31.5G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 2.95/1.1 io 4.89 cpu 4.69 | cgroup 1.2G/max oom_kill 0 | free scratch 307.2G/45199420i tmp 28.4G/998122i workspace 307.2G/45199420i | repeat-01 collected 26/26 workers (60624 items) tests 60624 done 3 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4732s, 307 samples, 0 signal(s); peaks: cgroup_current 15.5G, min_free_scratch 306.8G, min_free_tmp 28.0G, min_free_workspace 306.8G, min_inodes_scratch 45197150, min_inodes_tmp 994222, min_inodes_workspace 45197150, min_mem_available 18.0G, min_swap_free 51.3G, oom_kill_delta 0, pressure_memory_full 4.62, pswpin_delta 532106, pswpout_delta 2191291, scratch_bytes 0.9G, soak_procs 47, soak_pss 13.4G, soak_rss 15.0G, soak_swap 1.5G, soak_threads 289

contention tally: 3 node(s) failed across 1 repeat(s) in 4731.5s; red repeats: 1
  1/1  tests/ace/tui/widgets/test_cycle_edit_coalesce.py::test_cycle_press_builds_highlight_map_once  (repeats 1)
  1/1  tests/test_output.py::test_provider_timer_stops_background_thread  (repeats 1)
  1/1  tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

