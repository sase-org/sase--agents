# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-0)

- **TIMESTAMP:** 2026-11-08 05:46:08 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-0

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after hang-guard, rust-hint, and nested-isolation repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5670 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 241999, sampler pid 242037 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-3894635-1794130404291677896.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 46.0G/62.7G swapfree 55.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.25 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 330.8G/45685135i tmp 29.7G/1019834i workspace 330.8G/45685135i | scratch used 0.0G in 13 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.1G pss 1.8G swap 0.0G majflt 157 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.0G pss 1.7G | host avail 42.4G/62.7G swapfree 57.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.37 cpu 13.83 | cgroup 1.9G/max oom_kill 0 | free scratch 330.8G/45685018i tmp 29.7G/1019834i workspace 330.8G/45685018i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 3.4G pss 3.0G swap 1.1G majflt 1071 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.3G pss 3.0G | host avail 40.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.73 cpu 18.73 | cgroup 3.1G/max oom_kill 0 | free scratch 330.8G/45685008i tmp 29.7G/1019834i workspace 330.8G/45685008i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +45s soak 28p/80t rss 4.6G pss 4.2G swap 1.3G majflt 1081 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.5G pss 4.1G | host avail 41.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.07 cpu 25.44 | cgroup 4.3G/max oom_kill 0 | free scratch 330.6G/45684986i tmp 29.7G/1019834i workspace 330.6G/45684986i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +60s soak 28p/88t rss 5.4G pss 5.0G swap 1.3G majflt 1544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.3G pss 4.9G | host avail 39.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.23 cpu 26.01 | cgroup 5.1G/max oom_kill 0 | free scratch 330.8G/45684976i tmp 29.7G/1019834i workspace 330.8G/45684976i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 29p/90t rss 6.2G pss 5.8G swap 1.3G majflt 1623 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.0G pss 5.7G, 1 descendant rss 0.0G pss 0.0G | host avail 39.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.3 cpu 28.07 | cgroup 6.0G/max oom_kill 0 | free scratch 330.8G/45684977i tmp 29.7G/1019834i workspace 330.8G/45684977i | repeat-01 collected 1/26 workers (2379 items) tests 0 done 0 failed
contention shards: 26 workers collected 60602 items in total (2079-2555 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
........................................................................ [ 12%]
........................................................................ [ 15%]
.................[contention-diag] +91s soak 28p/101t rss 6.6G pss 6.2G swap 1.2G majflt 2585 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.5G pss 6.1G | host avail 37.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.06 cpu 23.43 | cgroup 6.5G/max oom_kill 0 | free scratch 330.8G/45683307i tmp 29.7G/1019832i workspace 330.8G/45683307i | repeat-01 collected 26/26 workers (60602 items) tests 332 done 0 failed | 26 in flight, oldest 3s gw15 tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
....................................................... [ 18%]
........................................................................ [ 21%]
........................................................................ [ 25%]
........................................................................ [ 28%]
........................................................................ [ 31%]
........................................................................ [ 34%]
........................................................................ [ 37%]
........................................................................ [ 40%]
........................................................................ [ 43%]
.........[contention-diag] +106s soak 30p/136t rss 7.2G pss 6.7G swap 1.2G majflt 3179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.0G pss 6.5G, 2 descendant rss 0.1G pss 0.1G | host avail 36.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.15 cpu 22.65 | cgroup 7.0G/max oom_kill 0 | free scratch 330.8G/45682095i tmp 29.7G/1019834i workspace 330.8G/45682095i | repeat-01 collected 26/26 workers (60602 items) tests 1007 done 0 failed | 26 in flight, oldest 17s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
............................................................... [ 47%]
........................................................................ [ 50%]
...............................................................[contention-diag] +121s soak 29p/158t rss 7.5G pss 6.9G swap 1.1G majflt 3360 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.8G, 1 descendant rss 0.1G pss 0.0G | host avail 42.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.42 cpu 29.71 | cgroup 7.2G/max oom_kill 0 | free scratch 330.8G/45681586i tmp 29.7G/1019834i workspace 330.8G/45681586i | scratch used 0.0G in 3421 entries | repeat-01 collected 26/26 workers (60602 items) tests 1209 done 0 failed | 26 in flight, oldest 32s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
......... [ 53%]
........................................................................ [ 56%]
........................................................................ [ 59%]
........................................................................ [ 62%]
.......................................[contention-diag] +136s soak 31p/174t rss 7.7G pss 7.2G swap 1.1G majflt 3528 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.9G, 3 descendant rss 0.1G pss 0.1G | host avail 40.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.77 cpu 30.96 | cgroup 7.5G/max oom_kill 0 | free scratch 330.8G/45680920i tmp 29.7G/1019834i workspace 330.8G/45680920i | repeat-01 collected 26/26 workers (60602 items) tests 1462 done 0 failed | 26 in flight, oldest 47s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
................................. [ 65%]
........................................................................ [ 69%]
........................................................................ [ 72%]
...........................[contention-diag] +152s soak 29p/166t rss 7.9G pss 7.3G swap 1.1G majflt 3734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 7.1G, 1 descendant rss 0.1G pss 0.1G | host avail 38.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.01 cpu 25.35 | cgroup 7.6G/max oom_kill 0 | free scratch 330.8G/45680350i tmp 29.7G/1019834i workspace 330.8G/45680350i | repeat-01 collected 26/26 workers (60602 items) tests 1670 done 0 failed | 26 in flight, oldest 60s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
............................................. [ 75%]
........................................................................ [ 78%]
........................................................................ [ 81%]
..[contention-diag] +167s soak 33p/181t rss 8.0G pss 7.4G swap 1.1G majflt 3760 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.2G, 5 descendant rss 0.1G pss 0.0G | host avail 39.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.98 cpu 24.4 | cgroup 7.7G/max oom_kill 0 | free scratch 330.8G/45679796i tmp 29.7G/1019834i workspace 330.8G/45679796i | repeat-01 collected 26/26 workers (60602 items) tests 1865 done 0 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................................... [ 84%]
........................................................................ [ 87%]
........................................................................ [ 91%]
....................................[contention-diag] +182s soak 35p/232t rss 8.2G pss 7.6G swap 1.1G majflt 3766 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.9G pss 7.4G, 7 descendant rss 0.1G pss 0.1G | host avail 40.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.3 cpu 27.47 | cgroup 7.9G/max oom_kill 0 | free scratch 330.8G/45677185i tmp 29.7G/1019834i workspace 330.8G/45677185i | repeat-01 collected 26/26 workers (60602 items) tests 2116 done 0 failed | 25 in flight, oldest 70s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................... [ 94%]
........................................................................ [ 97%]
........................................................................ [100%]
.............................[contention-diag] +197s soak 37p/196t rss 8.7G pss 8.0G swap 1.1G majflt 3914 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.2G pss 7.7G, 9 descendant rss 0.3G pss 0.2G | host avail 39.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.93 cpu 31.81 | cgroup 8.3G/max oom_kill 0 | free scratch 330.8G/45678263i tmp 29.7G/1019834i workspace 330.8G/45678263i | repeat-01 collected 26/26 workers (60602 items) tests 2315 done 0 failed | 26 in flight, oldest 86s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................... [103%]
........................................................................ [106%]
........................[contention-diag] +213s soak 30p/208t rss 8.5G pss 7.9G swap 1.1G majflt 3927 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.2G pss 7.7G, 2 descendant rss 0.1G pss 0.1G | host avail 37.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.84 cpu 24.6 | cgroup 8.3G/max oom_kill 0 | free scratch 330.8G/45680223i tmp 29.7G/1019834i workspace 330.8G/45680223i | repeat-01 collected 26/26 workers (60602 items) tests 2465 done 0 failed | 26 in flight, oldest 101s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................ [109%]
........................................................................ [113%]
............................[contention-diag] +228s soak 35p/229t rss 8.7G pss 8.1G swap 1.1G majflt 3951 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.8G, 7 descendant rss 0.2G pss 0.1G | host avail 36.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.14 cpu 25.39 | cgroup 8.4G/max oom_kill 0 | free scratch 330.8G/45679891i tmp 29.7G/1019834i workspace 330.8G/45679891i | repeat-01 collected 26/26 workers (60602 items) tests 2615 done 0 failed | 26 in flight, oldest 116s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................ [116%]
........................................................................ [119%]
........................................................................ [122%]
.......................................................[contention-diag] +243s soak 36p/205t rss 8.8G pss 8.2G swap 1.1G majflt 4005 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 8 descendant rss 0.2G pss 0.2G | host avail 39.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.16 cpu 29.12 | cgroup 8.5G/max oom_kill 0 | free scratch 330.8G/45679178i tmp 29.7G/1019834i workspace 330.8G/45679178i | scratch used 0.1G in 7922 entries | repeat-01 collected 26/26 workers (60602 items) tests 2861 done 0 failed | 26 in flight, oldest 131s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................. [125%]
........................................................................ [128%]
.........................[contention-diag] +258s soak 36p/215t rss 9.0G pss 8.3G swap 1.1G majflt 4111 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 8 descendant rss 0.3G pss 0.2G | host avail 38.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.64 cpu 33.93 | cgroup 8.7G/max oom_kill 0 | free scratch 330.8G/45678837i tmp 29.7G/1019834i workspace 330.8G/45678837i | repeat-01 collected 26/26 workers (60602 items) tests 2968 done 0 failed | 26 in flight, oldest 146s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................... [131%]
....[contention-diag] +274s soak 35p/239t rss 8.8G pss 8.2G swap 1.0G majflt 4165 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.0G, 7 descendant rss 0.1G pss 0.0G | host avail 38.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.67 cpu 28.85 | cgroup 8.5G/max oom_kill 0 | free scratch 330.8G/45678584i tmp 29.7G/1019834i workspace 330.8G/45678584i | repeat-01 collected 26/26 workers (60602 items) tests 3027 done 0 failed | 26 in flight, oldest 162s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................................... [135%]
...................................................................[contention-diag] +289s soak 36p/240t rss 9.0G pss 8.3G swap 1.0G majflt 4167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 8 descendant rss 0.1G pss 0.1G | host avail 37.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.82 cpu 29.46 | cgroup 8.6G/max oom_kill 0 | free scratch 330.8G/45678184i tmp 29.7G/1019834i workspace 330.8G/45678184i | repeat-01 collected 26/26 workers (60602 items) tests 3152 done 0 failed | 26 in flight, oldest 177s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [138%]
........................................................................ [141%]
........................................................................ [144%]
.....[contention-diag] +304s soak 35p/248t rss 9.1G pss 8.4G swap 1.0G majflt 4170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 7 descendant rss 0.1G pss 0.1G | host avail 38.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.93 cpu 34.66 | cgroup 8.8G/max oom_kill 0 | free scratch 330.8G/45677750i tmp 29.7G/1019834i workspace 330.8G/45677750i | repeat-01 collected 26/26 workers (60602 items) tests 3304 done 0 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................... [147%]
............................................................[contention-diag] +319s soak 34p/259t rss 9.1G pss 8.5G swap 1.1G majflt 4170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 38.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.88 cpu 30.72 | cgroup 8.8G/max oom_kill 0 | free scratch 330.8G/45677305i tmp 29.7G/1019834i workspace 330.8G/45677305i | repeat-01 collected 26/26 workers (60602 items) tests 3442 done 0 failed | 26 in flight, oldest 207s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............ [150%]
........................................................................ [153%]
........................................................................ [157%]
.....................................................[contention-diag] +334s soak 33p/245t rss 9.1G pss 8.5G swap 1.0G majflt 4175 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 5 descendant rss 0.1G pss 0.0G | host avail 36.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.69 cpu 31.12 | cgroup 8.8G/max oom_kill 0 | free scratch 330.8G/45676781i tmp 29.7G/1019834i workspace 330.8G/45676781i | repeat-01 collected 26/26 workers (60602 items) tests 3652 done 0 failed | 26 in flight, oldest 223s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [160%]
................................................................[contention-diag] +350s soak 33p/266t rss 9.2G pss 8.6G swap 1.0G majflt 4181 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 35.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.04 cpu 26.43 | cgroup 8.9G/max oom_kill 0 | free scratch 330.8G/45676492i tmp 29.7G/1019834i workspace 330.8G/45676492i | repeat-01 collected 26/26 workers (60602 items) tests 3734 done 0 failed | 26 in flight, oldest 238s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........ [163%]
...................................................................[contention-diag] +365s soak 36p/271t rss 9.5G pss 8.8G swap 1.1G majflt 4209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 8 descendant rss 0.2G pss 0.2G | host avail 37.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.65 cpu 30.7 | cgroup 9.1G/max oom_kill 0 | free scratch 330.8G/45676182i tmp 29.7G/1019834i workspace 330.8G/45676182i | scratch used 0.1G in 10921 entries | repeat-01 collected 26/26 workers (60602 items) tests 3807 done 0 failed | 26 in flight, oldest 253s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [166%]
.................................................................[contention-diag] +380s soak 39p/262t rss 9.5G pss 8.8G swap 1.1G majflt 4209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 11 descendant rss 0.2G pss 0.1G | host avail 37.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.48 cpu 35.96 | cgroup 9.1G/max oom_kill 0 | free scratch 330.8G/45675860i tmp 29.7G/1019835i workspace 330.8G/45675860i | repeat-01 collected 26/26 workers (60602 items) tests 3877 done 0 failed | 26 in flight, oldest 268s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....... [169%]
........................................................................ [172%]
........................................................................ [175%]
.................[contention-diag] +396s soak 39p/253t rss 9.5G pss 8.8G swap 1.0G majflt 4209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 11 descendant rss 0.2G pss 0.1G | host avail 37.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.51 cpu 35.12 | cgroup 9.1G/max oom_kill 0 | free scratch 330.8G/45675423i tmp 29.7G/1019835i workspace 330.8G/45675423i | repeat-01 collected 26/26 workers (60602 items) tests 4042 done 0 failed | 26 in flight, oldest 284s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...........................................[contention-diag] +411s soak 42p/288t rss 9.7G pss 9.0G swap 1.1G majflt 4209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 14 descendant rss 0.3G pss 0.2G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 30.66 | cgroup 9.3G/max oom_kill 0 | free scratch 330.8G/45675226i tmp 29.7G/1019835i workspace 330.8G/45675226i | repeat-01 collected 26/26 workers (60602 items) tests 4090 done 0 failed | 26 in flight, oldest 299s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............ [179%]
..................................................[contention-diag] +426s soak 42p/258t rss 9.9G pss 9.1G swap 1.1G majflt 4213 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 14 descendant rss 0.4G pss 0.3G | host avail 37.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 38.49 | cgroup 9.4G/max oom_kill 0 | free scratch 330.8G/45674992i tmp 29.7G/1019835i workspace 330.8G/45674992i | repeat-01 collected 26/26 workers (60602 items) tests 4147 done 0 failed | 26 in flight, oldest 314s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................... [182%]
........................................................................ [185%]
..................................................................[contention-diag] +441s soak 34p/262t rss 9.6G pss 8.9G swap 1.0G majflt 4294 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 6 descendant rss 0.1G pss 0.0G | host avail 37.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 41.71 | cgroup 9.3G/max oom_kill 0 | free scratch 330.8G/45674469i tmp 29.7G/1019835i workspace 330.8G/45674469i | repeat-01 collected 26/26 workers (60602 items) tests 4314 done 0 failed | 26 in flight, oldest 329s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...... [188%]
.........................[contention-diag] +456s soak 34p/264t rss 9.6G pss 9.0G swap 1.0G majflt 4311 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 6 descendant rss 0.1G pss 0.0G | host avail 36.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.82 | cgroup 9.3G/max oom_kill 0 | free scratch 330.5G/45674317i tmp 29.7G/1019835i workspace 330.5G/45674317i | repeat-01 collected 26/26 workers (60602 items) tests 4344 done 0 failed | 26 in flight, oldest 345s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................... [191%]
........................................................................ [194%]
..........................[contention-diag] +472s soak 29p/249t rss 9.7G pss 9.0G swap 1.0G majflt 4314 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 1 descendant rss 0.1G pss 0.0G | host avail 35.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.36 | cgroup 9.4G/max oom_kill 0 | free scratch 330.7G/45673908i tmp 29.7G/1019835i workspace 330.7G/45673908i | repeat-01 collected 26/26 workers (60602 items) tests 4483 done 0 failed | 26 in flight, oldest 360s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................. [197%]
................[contention-diag] +487s soak 30p/274t rss 9.8G pss 9.2G swap 1.1G majflt 4314 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.2G pss 0.1G | host avail 37.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.43 | cgroup 9.5G/max oom_kill 0 | free scratch 330.7G/45673649i tmp 29.7G/1019835i workspace 330.7G/45673649i | scratch used 0.1G in 13459 entries | repeat-01 collected 26/26 workers (60602 items) tests 4550 done 0 failed | 26 in flight, oldest 375s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................[contention-diag] +502s soak 29p/256t rss 9.8G pss 9.1G swap 1.0G majflt 4336 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.9G, 1 descendant rss 0.0G pss 0.0G | host avail 37.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 40.42 | cgroup 9.5G/max oom_kill 0 | free scratch 330.7G/45673427i tmp 29.7G/1019835i workspace 330.7G/45673427i | repeat-01 collected 26/26 workers (60602 items) tests 4568 done 0 failed | 26 in flight, oldest 100s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
..................[contention-diag] +518s soak 30p/240t rss 9.9G pss 9.2G swap 1.0G majflt 4336 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 37.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.51 | cgroup 9.6G/max oom_kill 0 | free scratch 330.7G/45673167i tmp 29.7G/1019835i workspace 330.7G/45673167i | repeat-01 collected 26/26 workers (60602 items) tests 4586 done 0 failed | 26 in flight, oldest 51s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
...................... [201%]
.........................[contention-diag] +533s soak 30p/244t rss 9.9G pss 9.3G swap 1.0G majflt 4336 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 36.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.03 | cgroup 9.6G/max oom_kill 0 | free scratch 330.7G/45672991i tmp 29.7G/1019835i workspace 330.7G/45672991i | repeat-01 collected 26/26 workers (60602 items) tests 4630 done 0 failed | 26 in flight, oldest 67s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
............................................... [204%]
.............................[contention-diag] +548s soak 28p/256t rss 9.8G pss 9.2G swap 1.0G majflt 4336 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 37.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.8 | cgroup 9.6G/max oom_kill 0 | free scratch 330.7G/45672680i tmp 29.7G/1019835i workspace 330.7G/45672681i | repeat-01 collected 26/26 workers (60602 items) tests 4708 done 0 failed | 26 in flight, oldest 82s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
........................................... [207%]
.......................[contention-diag] +563s soak 28p/261t rss 9.9G pss 9.2G swap 1.0G majflt 4369 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 37.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.94 | cgroup 9.6G/max oom_kill 0 | free scratch 330.7G/45672408i tmp 29.7G/1019835i workspace 330.7G/45672408i | repeat-01 collected 26/26 workers (60602 items) tests 4773 done 0 failed | 26 in flight, oldest 97s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
.....F[contention-failure] call tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb07b3af7d0>

    async def test_agent_first_page_paints_before_full_extension(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        from sase.feature_flags import override_flags
    
        with override_flags(artifacts_agent_pane_retired=False):
>           await _agent_first_page_paints_before_full_extension(monkeypatch)

tests/ace/tui/test_artifacts_agents_loading.py:26: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb07b3af7d0>

    async def _agent_first_page_paints_before_full_extension(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        first_rows = (
            make_agent_catalog_row("newest", started_at="2026-08-24T12:00:00+00:00"),
            make_agent_catalog_row("older", started_at="2026-08-24T11:00:00+00:00"),
        )
        full_rows = (
            *first_rows,
            make_agent_catalog_row("oldest", started_at="2026-08-24T10:00:00+00:00"),
        )
        full_started = Event()
        release_full = Event()
        requested_limits: list[int | None] = []
        indexed_row_counts: list[int] = []
    
        def load(project: str | None, limit: int | None = None) -> AgentsSnapshot:
            requested_limits.append(limit)
            if limit is None:
                full_started.set()
                assert release_full.wait(timeout=LOAD_TOLERANT_TIMEOUT)
                return AgentsSnapshot(
                    project=project,
                    rows=full_rows,
                    total_row_count=len(full_rows),
                    complete=True,
                )
            return AgentsSnapshot(
                project=project,
                rows=first_rows,
                total_row_count=len(full_rows),
                complete=False,
            )
    
        original_build = ArtifactsAgentsPane._build_agents_query_index
    
        def build_index(
            self: ArtifactsAgentsPane, snapshot: AgentsSnapshot, *, generation: int
        ):
            indexed_row_counts.append(len(snapshot.rows))
            return original_build(self, snapshot, generation=generation)
    
        monkeypatch.setattr(agents_pane, "load_agents_snapshot", load)
        monkeypatch.setattr(ArtifactsAgentsPane, "_build_agents_query_index", build_index)
    
        try:
            async with AcePage(initial_tab="patches", startup_policy="real") as page:
                await page.press(page.artifacts_digit("agents"))
                pane = page.query_one_widget(
                    "#artifacts-agents-pane",
                    ArtifactsAgentsPane,
                )
                await page.wait_for(
                    lambda _state: (
                        pane.snapshot is not None and len(pane.snapshot.rows) == 2
                    ),
                    timeout=LOAD_TOLERANT_TIMEOUT,
                )
    
                assert
......................[contention-diag] +578s soak 29p/253t rss 10.0G pss 9.3G swap 1.0G majflt 4410 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 1 descendant rss 0.1G pss 0.0G | host avail 37.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.74 | cgroup 9.9G/max oom_kill 0 | free scratch 330.7G/45672213i tmp 29.7G/1019835i workspace 330.7G/45672213i | repeat-01 collected 26/26 workers (60602 items) tests 4802 done 1 failed | 26 in flight, oldest 80s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
..................... [210%]
..........[contention-diag] +594s soak 29p/219t rss 10.0G pss 9.4G swap 1.0G majflt 4410 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 36.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.81 | cgroup 9.8G/max oom_kill 0 | free scratch 330.7G/45671939i tmp 29.7G/1019835i workspace 330.7G/45671939i | repeat-01 collected 26/26 workers (60602 items) tests 4832 done 1 failed | 26 in flight, oldest 52s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_K_warns_when_finished_and_confirms_when_running
.............................[contention-diag] +609s soak 28p/259t rss 10.0G pss 9.3G swap 1.0G majflt 4410 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 37.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.76 | cgroup 9.7G/max oom_kill 0 | free scratch 330.7G/45671737i tmp 29.7G/1019835i workspace 330.7G/45671737i | scratch used 0.1G in 15352 entries | repeat-01 collected 26/26 workers (60602 items) tests 4863 done 1 failed | 26 in flight, oldest 65s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
................................. [213%]
.......................[contention-diag] +624s soak 28p/270t rss 10.0G pss 9.4G swap 1.0G majflt 4424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 36.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.32 | cgroup 9.7G/max oom_kill 0 | free scratch 330.7G/45671529i tmp 29.7G/1019835i workspace 330.7G/45671529i | repeat-01 collected 26/26 workers (60602 items) tests 4908 done 1 failed | 26 in flight, oldest 65s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
................................................. [216%]
......................[contention-diag] +640s soak 32p/248t rss 10.1G pss 9.5G swap 1.0G majflt 4425 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G, 4 descendant rss 0.1G pss 0.1G | host avail 36.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.08 | cgroup 9.9G/max oom_kill 0 | free scratch 330.7G/45671217i tmp 29.7G/1019835i workspace 330.7G/45671217i | repeat-01 collected 26/26 workers (60602 items) tests 4986 done 1 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
.........[contention-diag] +655s soak 29p/253t rss 10.1G pss 9.4G swap 1.0G majflt 4425 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 36.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 32.34 | cgroup 9.9G/max oom_kill 0 | free scratch 330.7G/45671047i tmp 29.7G/1019835i workspace 330.7G/45671047i | repeat-01 collected 26/26 workers (60602 items) tests 4997 done 1 failed | 26 in flight, oldest 66s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_picker_acts_on_focused_split_panel
............................[contention-diag] +670s soak 29p/238t rss 10.2G pss 9.5G swap 1.0G majflt 4427 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 40.52 | cgroup 10.0G/max oom_kill 0 | free scratch 330.7G/45670840i tmp 29.7G/1019835i workspace 330.7G/45670840i | repeat-01 collected 26/26 workers (60602 items) tests 5026 done 1 failed | 26 in flight, oldest 44s gw9 tests/ace/tui/test_agent_collapsed_panel_kill.py::test_dismissing_focused_last_node_unmounts_its_tribe_panel
............. [219%]
............................[contention-diag] +685s soak 28p/233t rss 10.1G pss 9.5G swap 1.0G majflt 4427 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 35.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.97 | cgroup 10.0G/max oom_kill 0 | free scratch 330.7G/45670624i tmp 29.7G/1019835i workspace 330.7G/45670624i | repeat-01 collected 26/26 workers (60602 items) tests 5066 done 1 failed | 26 in flight, oldest 56s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_collapsed_rail_keeps_keymap_and_footer
............................................ [223%]
..............................................[contention-diag] +701s soak 31p/243t rss 10.3G pss 9.6G swap 1.0G majflt 4428 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 3 descendant rss 0.1G pss 0.1G | host avail 36.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.0 cpu 35.79 | cgroup 10.1G/max oom_kill 0 | free scratch 330.7G/45670270i tmp 29.7G/1019835i workspace 330.7G/45670270i | repeat-01 collected 26/26 workers (60602 items) tests 5154 done 1 failed | 26 in flight, oldest 54s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
.......................... [226%]
.............................................[contention-diag] +716s soak 28p/224t rss 10.2G pss 9.6G swap 1.0G majflt 4432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 35.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.0 cpu 34.13 | cgroup 10.0G/max oom_kill 0 | free scratch 330.7G/45669940i tmp 29.7G/1019835i workspace 330.7G/45669940i | repeat-01 collected 26/26 workers (60602 items) tests 5212 done 1 failed | 26 in flight, oldest 52s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
........................... [229%]
........................................................................ [232%]
........................................................................ [235%]
..[contention-diag] +731s soak 29p/238t rss 10.3G pss 9.6G swap 1.0G majflt 4432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.1G pss 0.0G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.03 | cgroup 10.0G/max oom_kill 0 | free scratch 330.7G/45669475i tmp 29.7G/1019835i workspace 330.7G/45669475i | scratch used 0.1G in 17622 entries | repeat-01 collected 26/26 workers (60602 items) tests 5399 done 1 failed | 26 in flight, oldest 49s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_block_nav_override_takes_effect_in_mounted_pilot
...................................................................... [238%]
........................................[contention-diag] +747s soak 29p/255t rss 10.3G pss 9.6G swap 1.0G majflt 4441 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.46 | cgroup 10.0G/max oom_kill 0 | free scratch 330.7G/45669078i tmp 29.7G/1019835i workspace 330.7G/45669078i | repeat-01 collected 26/26 workers (60602 items) tests 5510 done 1 failed | 26 in flight, oldest 52s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
................................ [241%]
................................................[contention-diag] +762s soak 30p/259t rss 10.4G pss 9.7G swap 1.0G majflt 4457 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G, 2 descendant rss 0.1G pss 0.1G | host avail 38.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.32 | cgroup 10.2G/max oom_kill 0 | free scratch 330.7G/45668685i tmp 29.7G/1019835i workspace 330.7G/45668685i | repeat-01 collected 26/26 workers (60602 items) tests 5587 done 1 failed | 25 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
........................ [245%]
...........................[contention-diag] +777s soak 30p/238t rss 10.3G pss 9.7G swap 1.0G majflt 4457 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 2 descendant rss 0.0G pss 0.0G | host avail 38.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.86 | cgroup 10.2G/max oom_kill 0 | free scratch 330.7G/45668431i tmp 29.7G/1019835i workspace 330.7G/45668431i | repeat-01 collected 26/26 workers (60602 items) tests 5643 done 1 failed | 26 in flight, oldest 74s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...........................[contention-diag] +792s soak 30p/261t rss 10.5G pss 9.8G swap 1.0G majflt 4457 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 38.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.6 | cgroup 10.3G/max oom_kill 0 | free scratch 330.7G/45668277i tmp 29.7G/1019835i workspace 330.7G/45668277i | repeat-01 collected 26/26 workers (60602 items) tests 5669 done 1 failed | 26 in flight, oldest 89s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................. [248%]
........................................................................ [251%]
[contention-diag] +808s soak 28p/259t rss 10.4G pss 9.8G swap 1.0G majflt 4457 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G | host avail 38.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 42.95 | cgroup 10.3G/max oom_kill 0 | free scratch 330.7G/45667926i tmp 29.7G/1019835i workspace 330.7G/45667926i | repeat-01 collected 26/26 workers (60602 items) tests 5758 done 1 failed | 26 in flight, oldest 104s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................................................ [254%]
....................[contention-diag] +823s soak 29p/256t rss 10.5G pss 9.8G swap 1.0G majflt 4457 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 1 descendant rss 0.1G pss 0.1G | host avail 37.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.27 | cgroup 10.3G/max oom_kill 0 | free scratch 330.7G/45667505i tmp 29.7G/1019835i workspace 330.7G/45667505i | repeat-01 collected 26/26 workers (60602 items) tests 5851 done 1 failed | 26 in flight, oldest 120s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................................................... [257%]
.......................[contention-diag] +838s soak 29p/247t rss 10.5G pss 9.9G swap 1.0G majflt 4460 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 1 descendant rss 0.1G pss 0.1G | host avail 37.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.83 | cgroup 10.3G/max oom_kill 0 | free scratch 330.7G/45667294i tmp 29.7G/1019835i workspace 330.7G/45667294i | repeat-01 collected 26/26 workers (60602 items) tests 5917 done 1 failed | 26 in flight, oldest 135s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................................................. [260%]
........................................................................ [263%]
..........[contention-diag] +854s soak 28p/230t rss 10.5G pss 9.9G swap 1.0G majflt 4468 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G | host avail 36.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 29.61 | cgroup 10.3G/max oom_kill 0 | free scratch 330.2G/45666802i tmp 29.7G/1019835i workspace 330.2G/45666802i | scratch used 0.1G in 20262 entries | repeat-01 collected 26/26 workers (60602 items) tests 6052 done 1 failed | 26 in flight, oldest 63s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
.............................................................. [267%]
........................................................................ [270%]
...............[contention-diag] +869s soak 30p/230t rss 10.6G pss 10.0G swap 1.0G majflt 4468 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G, 2 descendant rss 0.1G pss 0.1G | host avail 35.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.64 cpu 22.3 | cgroup 10.4G/max oom_kill 0 | free scratch 330.7G/45666411i tmp 29.7G/1019835i workspace 330.7G/45666411i | repeat-01 collected 26/26 workers (60602 items) tests 6201 done 1 failed | 26 in flight, oldest 79s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
......................................................... [273%]
........................................................................ [276%]
........................................................................ [279%]
.....................[contention-diag] +884s soak 28p/213t rss 10.6G pss 10.0G swap 1.0G majflt 4479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G | host avail 36.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.59 cpu 21.69 | cgroup 10.4G/max oom_kill 0 | free scratch 330.7G/45665794i tmp 29.7G/1019835i workspace 330.7G/45665794i | repeat-01 collected 26/26 workers (60602 items) tests 6423 done 1 failed | 26 in flight, oldest 50s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................................................... [282%]
........................................................................ [285%]
........................................................................ [289%]
......[contention-diag] +900s soak 28p/225t rss 10.6G pss 10.0G swap 1.0G majflt 4480 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 21.13 | cgroup 10.4G/max oom_kill 0 | free scratch 330.7G/45665242i tmp 29.7G/1019835i workspace 330.7G/45665242i | repeat-01 collected 26/26 workers (60602 items) tests 6627 done 1 failed | 25 in flight, oldest 65s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
.................................................................. [292%]
...................................[contention-diag] +915s soak 30p/245t rss 10.7G pss 10.1G swap 1.0G majflt 4542 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 2 descendant rss 0.1G pss 0.1G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.11 cpu 23.61 | cgroup 10.5G/max oom_kill 0 | free scratch 330.7G/45664920i tmp 29.7G/1019835i workspace 330.7G/45664920i | repeat-01 collected 26/26 workers (60602 items) tests 6729 done 1 failed | 26 in flight, oldest 80s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
..................................... [295%]
.........................................[contention-diag] +930s soak 28p/224t rss 10.7G pss 10.0G swap 1.0G majflt 4542 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G | host avail 36.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 32.09 | cgroup 10.5G/max oom_kill 0 | free scratch 330.7G/45664569i tmp 29.7G/1019835i workspace 330.7G/45664569i | repeat-01 collected 26/26 workers (60602 items) tests 6808 done 1 failed | 26 in flight, oldest 43s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
...........................[contention-diag] +945s soak 30p/240t rss 10.8G pss 10.1G swap 1.0G majflt 4556 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G, 2 descendant rss 0.1G pss 0.0G | host avail 36.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.4 | cgroup 10.6G/max oom_kill 0 | free scratch 330.7G/45664373i tmp 29.7G/1019835i workspace 330.7G/45664373i | repeat-01 collected 26/26 workers (60602 items) tests 6835 done 1 failed | 26 in flight, oldest 46s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_toggle_install_mark_noops_for_installed
.... [298%]
......................................[contention-diag] +961s soak 31p/242t rss 10.8G pss 10.2G swap 1.0G majflt 4556 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 3 descendant rss 0.1G pss 0.1G | host avail 36.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.05 | cgroup 10.6G/max oom_kill 0 | free scratch 330.7G/45664162i tmp 29.7G/1019835i workspace 330.7G/45664162i | repeat-01 collected 26/26 workers (60602 items) tests 6876 done 1 failed | 26 in flight, oldest 45s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_ctrl_j_grows_limit_and_ctrl_k_returns_to_floor
.................................. [301%]
................................................................[contention-diag] +976s soak 28p/219t rss 10.8G pss 10.1G swap 1.0G majflt 4556 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 10.0G | host avail 37.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.37 | cgroup 10.6G/max oom_kill 0 | free scratch 330.7G/45663921i tmp 29.7G/1019835i workspace 330.7G/45663921i | scratch used 0.2G in 23248 entries | repeat-01 collected 26/26 workers (60602 items) tests 6930 done 1 failed | 25 in flight, oldest 58s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........ [304%]
........................................................................ [307%]
.......................................................................[contention-diag] +993s soak 29p/224t rss 10.9G pss 10.2G swap 1.0G majflt 4556 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 36.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 32.56 | cgroup 10.7G/max oom_kill 0 | free scratch 330.7G/45663421i tmp 29.7G/1019835i workspace 330.7G/45663421i | repeat-01 collected 26/26 workers (60602 items) tests 7118 done 1 failed | 26 in flight, oldest 42s gw4 tests/ace/tui/test_artifacts_files_loading.py::test_hydrate_ref_reports_absent_for_unknown_logical_id
. [310%]
........................................................................ [314%]
...................[contention-diag] +1008s soak 30p/223t rss 10.9G pss 10.2G swap 1.0G majflt 4557 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 36.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 36.9 | cgroup 10.8G/max oom_kill 0 | free scratch 330.7G/45663026i tmp 29.7G/1019835i workspace 330.7G/45663026i | repeat-01 collected 26/26 workers (60602 items) tests 7217 done 1 failed | 26 in flight, oldest 45s gw10 tests/ace/tui/test_agents_onboarding.py::test_agents_onboarding_hides_after_first_agent_arrives
..................................................... [317%]
........................................................................ [320%]
........................[contention-diag] +1023s soak 29p/240t rss 10.9G pss 10.2G swap 1.0G majflt 4557 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 36.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.32 | cgroup 10.8G/max oom_kill 0 | free scratch 330.7G/45662627i tmp 29.7G/1019835i workspace 330.7G/45662627i | repeat-01 collected 26/26 workers (60602 items) tests 7342 done 1 failed | 25 in flight, oldest 57s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................................................ [323%]
........................................................................ [326%]
........................................................................ [329%]
................................[contention-diag] +1038s soak 29p/244t rss 10.9G pss 10.2G swap 1.0G majflt 4557 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.47 | cgroup 10.8G/max oom_kill 0 | free scratch 330.7G/45662043i tmp 29.7G/1019835i workspace 330.7G/45662043i | repeat-01 collected 26/26 workers (60602 items) tests 7582 done 1 failed | 26 in flight, oldest 72s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
........................................ [332%]
....................................[contention-diag] +1054s soak 38p/254t rss 11.0G pss 10.3G swap 1.0G majflt 4557 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 36.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.11 | cgroup 10.8G/max oom_kill 0 | free scratch 330.7G/45661737i tmp 29.7G/1019835i workspace 330.7G/45661737i | repeat-01 collected 26/26 workers (60602 items) tests 7668 done 1 failed | 26 in flight, oldest 69s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
.................................... [336%]
.....[contention-diag] +1069s soak 38p/268t rss 11.0G pss 10.3G swap 1.0G majflt 4562 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 36.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 42.19 | cgroup 10.8G/max oom_kill 0 | free scratch 330.7G/45661519i tmp 29.7G/1019835i workspace 330.7G/45661519i | repeat-01 collected 26/26 workers (60602 items) tests 7709 done 1 failed | 26 in flight, oldest 53s gw20 tests/ace/tui/test_link_follow_seam.py::test_closed_phase_follow_selects_without_hanging
........................................[contention-diag] +1084s soak 41p/255t rss 11.1G pss 10.3G swap 1.0G majflt 4562 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 13 descendant rss 0.1G pss 0.0G | host avail 35.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.16 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45661274i tmp 29.7G/1019835i workspace 330.7G/45661274i | repeat-01 collected 26/26 workers (60602 items) tests 7748 done 1 failed | 26 in flight, oldest 52s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
......[contention-diag] +1100s soak 38p/270t rss 11.0G pss 10.3G swap 1.0G majflt 4563 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 36.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.0 cpu 34.94 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45661128i tmp 29.7G/1019835i workspace 330.7G/45661128i | scratch used 0.2G in 25972 entries | repeat-01 collected 26/26 workers (60602 items) tests 7754 done 1 failed | 26 in flight, oldest 68s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
........[contention-diag] +1115s soak 38p/282t rss 11.1G pss 10.3G swap 1.0G majflt 4563 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 35.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.0 cpu 35.18 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45660974i tmp 29.7G/1019835i workspace 330.7G/45660974i | repeat-01 collected 26/26 workers (60602 items) tests 7762 done 1 failed | 26 in flight, oldest 83s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
............. [339%]
................................................[contention-diag] +1130s soak 38p/257t rss 11.1G pss 10.3G swap 1.0G majflt 4563 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.01 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45660754i tmp 29.7G/1019835i workspace 330.7G/45660754i | repeat-01 collected 26/26 workers (60602 items) tests 7818 done 1 failed | 26 in flight, oldest 77s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_from_rail_is_flush_and_restores_rail
........................ [342%]
......[contention-diag] +1146s soak 39p/252t rss 11.1G pss 10.3G swap 1.0G majflt 4563 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 11 descendant rss 0.1G pss 0.0G | host avail 35.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.67 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45660588i tmp 29.7G/1019835i workspace 330.7G/45660588i | repeat-01 collected 26/26 workers (60602 items) tests 7853 done 1 failed | 26 in flight, oldest 88s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
............................................................[contention-diag] +1161s soak 32p/272t rss 11.0G pss 10.3G swap 1.0G majflt 4565 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 4 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.92 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45660339i tmp 29.7G/1019833i workspace 330.7G/45660339i | repeat-01 collected 26/26 workers (60602 items) tests 7904 done 1 failed | 26 in flight, oldest 103s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
...... [345%]
........................................................................ [348%]
........................................................................ [351%]
..................................[contention-diag] +1176s soak 28p/256t rss 11.0G pss 10.4G swap 1.0G majflt 4572 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 35.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.38 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45659773i tmp 29.7G/1019835i workspace 330.7G/45659773i | repeat-01 collected 26/26 workers (60602 items) tests 8090 done 1 failed | 26 in flight, oldest 118s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
...........................[contention-diag] +1191s soak 28p/240t rss 11.1G pss 10.4G swap 1.0G majflt 4581 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 35.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 41.0 | cgroup 10.9G/max oom_kill 0 | free scratch 330.7G/45659605i tmp 29.7G/1019835i workspace 330.7G/45659605i | repeat-01 collected 26/26 workers (60602 items) tests 8125 done 1 failed | 26 in flight, oldest 73s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
........... [354%]
.............................................................[contention-diag] +1207s soak 28p/245t rss 11.1G pss 10.4G swap 1.0G majflt 4584 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 43.26 | cgroup 11.0G/max oom_kill 0 | free scratch 330.7G/45659337i tmp 29.7G/1019835i workspace 330.7G/45659337i | repeat-01 collected 26/26 workers (60602 items) tests 8195 done 1 failed | 26 in flight, oldest 73s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
........... [358%]
........................................................................ [361%]
................................................................[contention-diag] +1222s soak 28p/221t rss 11.1G pss 10.4G swap 1.0G majflt 4597 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.3G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.49 | cgroup 11.0G/max oom_kill 0 | free scratch 330.7G/45658925i tmp 29.7G/1019835i workspace 330.7G/45658925i | scratch used 0.2G in 28174 entries | repeat-01 collected 26/26 workers (60602 items) tests 8339 done 1 failed | 26 in flight, oldest 57s gw7 tests/ace/tui/test_config_hub_pane.py::test_opening_config_constructs_only_the_active_child
........ [364%]
..........................................[contention-diag] +1237s soak 28p/237t rss 11.1G pss 10.4G swap 1.0G majflt 4597 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.3G | host avail 35.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.4 | cgroup 11.0G/max oom_kill 0 | free scratch 330.7G/45658765i tmp 29.7G/1019835i workspace 330.7G/45658765i | repeat-01 collected 26/26 workers (60602 items) tests 8391 done 1 failed | 26 in flight, oldest 67s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
.............................. [367%]
........................................................................ [370%]
........................................................................ [373%]
................[contention-diag] +1253s soak 30p/256t rss 11.2G pss 10.5G swap 1.0G majflt 4721 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 2 descendant rss 0.1G pss 0.1G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.0 | cgroup 11.1G/max oom_kill 0 | free scratch 330.7G/45658245i tmp 29.7G/1019835i workspace 330.7G/45658245i | repeat-01 collected 26/26 workers (60602 items) tests 8582 done 1 failed | 26 in flight, oldest 73s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................................................ [376%]
........................................................................ [380%]
........................................................................ [383%]
........................................................................ [386%]
....[contention-diag] +1268s soak 29p/227t rss 11.2G pss 10.5G swap 1.0G majflt 4742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.09 | cgroup 11.1G/max oom_kill 0 | free scratch 330.7G/45657578i tmp 29.7G/1019835i workspace 330.7G/45657578i | repeat-01 collected 26/26 workers (60602 items) tests 8858 done 1 failed | 26 in flight, oldest 88s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................................... [389%]
......................................................................[contention-diag] +1283s soak 28p/235t rss 11.2G pss 10.5G swap 1.0G majflt 4742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 35.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.84 | cgroup 11.1G/max oom_kill 0 | free scratch 330.6G/45657192i tmp 29.7G/1019835i workspace 330.6G/45657192i | repeat-01 collected 26/26 workers (60602 items) tests 8993 done 1 failed | 26 in flight, oldest 104s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.. [392%]
........................................................................ [395%]
......................................[contention-diag] +1298s soak 28p/251t rss 11.2G pss 10.5G swap 1.0G majflt 4742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 33.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.96 | cgroup 11.1G/max oom_kill 0 | free scratch 330.6G/45656851i tmp 29.7G/1019835i workspace 330.6G/45656851i | repeat-01 collected 26/26 workers (60602 items) tests 9094 done 1 failed | 26 in flight, oldest 119s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................. [398%]
..................................................................[contention-diag] +1314s soak 28p/234t rss 11.3G pss 10.5G swap 1.0G majflt 4742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G | host avail 35.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.52 | cgroup 11.1G/max oom_kill 0 | free scratch 330.6G/45656508i tmp 29.7G/1019835i workspace 330.6G/45656508i | repeat-01 collected 26/26 workers (60602 items) tests 9208 done 1 failed | 24 in flight, oldest 134s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
...... [402%]
........................................................................ [405%]
.............[contention-diag] +1329s soak 28p/257t rss 11.3G pss 10.6G swap 1.0G majflt 4742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G | host avail 35.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 41.23 | cgroup 11.2G/max oom_kill 0 | free scratch 330.6G/45656229i tmp 29.7G/1019835i workspace 330.6G/45656229i | repeat-01 collected 26/26 workers (60602 items) tests 9299 done 1 failed | 26 in flight, oldest 149s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..........................................................[contention-diag] +1344s soak 28p/260t rss 11.3G pss 10.6G swap 1.0G majflt 4758 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G | host avail 34.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 42.13 | cgroup 11.2G/max oom_kill 0 | free scratch 330.6G/45655996i tmp 29.7G/1019835i workspace 330.6G/45655996i | scratch used 0.2G in 31112 entries | repeat-01 collected 26/26 workers (60602 items) tests 9359 done 1 failed | 26 in flight, oldest 165s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
. [408%]
..................................[contention-diag] +1360s soak 29p/250t rss 11.3G pss 10.6G swap 1.0G majflt 4768 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 33.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.43 | cgroup 11.2G/max oom_kill 0 | free scratch 330.6G/45655803i tmp 29.7G/1019835i workspace 330.6G/45655803i | repeat-01 collected 26/26 workers (60602 items) tests 9394 done 1 failed | 26 in flight, oldest 76s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
...................................... [411%]
........[contention-diag] +1375s soak 29p/265t rss 11.4G pss 10.6G swap 0.9G majflt 4830 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 34.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.08 | cgroup 11.2G/max oom_kill 0 | free scratch 330.6G/45655485i tmp 29.7G/1019835i workspace 330.6G/45655485i | repeat-01 collected 26/26 workers (60602 items) tests 9438 done 1 failed | 26 in flight, oldest 91s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.....................................................[contention-diag] +1390s soak 28p/264t rss 11.4G pss 10.6G swap 0.9G majflt 4831 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 36.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.03 | cgroup 11.2G/max oom_kill 0 | free scratch 330.6G/45655386i tmp 29.7G/1019835i workspace 330.6G/45655386i | repeat-01 collected 26/26 workers (60602 items) tests 9488 done 1 failed | 26 in flight, oldest 106s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
........... [414%]
.....................[contention-diag] +1406s soak 28p/241t rss 11.4G pss 10.7G swap 0.9G majflt 4832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 37.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.64 | cgroup 11.3G/max oom_kill 0 | free scratch 330.6G/45655180i tmp 29.7G/1019835i workspace 330.6G/45655180i | repeat-01 collected 26/26 workers (60602 items) tests 9525 done 1 failed | 26 in flight, oldest 122s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................................... [417%]
...........[contention-diag] +1421s soak 28p/246t rss 11.4G pss 10.7G swap 0.9G majflt 4869 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 37.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.31/0.31 io 0.0 cpu 34.42 | cgroup 11.3G/max oom_kill 0 | free scratch 330.6G/45654894i tmp 29.7G/1019835i workspace 330.6G/45654894i | repeat-01 collected 26/26 workers (60602 items) tests 9585 done 1 failed | 26 in flight, oldest 137s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..........................................[contention-diag] +1436s soak 29p/257t rss 11.4G pss 10.7G swap 0.9G majflt 4884 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 36.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.0 cpu 30.04 | cgroup 11.3G/max oom_kill 0 | free scratch 330.6G/45654672i tmp 29.7G/1019835i workspace 330.6G/45654672i | repeat-01 collected 26/26 workers (60602 items) tests 9628 done 1 failed | 26 in flight, oldest 152s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................... [420%]
.[contention-diag] +1452s soak 28p/240t rss 11.4G pss 10.7G swap 0.9G majflt 4888 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 37.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 41.4 | cgroup 11.3G/max oom_kill 0 | free scratch 330.6G/45654503i tmp 29.7G/1019835i workspace 330.6G/45654503i | repeat-01 collected 26/26 workers (60602 items) tests 9649 done 1 failed | 26 in flight, oldest 75s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...............................................................[contention-diag] +1467s soak 28p/257t rss 11.4G pss 10.7G swap 0.9G majflt 4890 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.6G | host avail 37.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.08 | cgroup 11.4G/max oom_kill 0 | free scratch 330.6G/45654264i tmp 29.7G/1019835i workspace 330.6G/45654264i | scratch used 0.2G in 32835 entries | repeat-01 collected 26/26 workers (60602 items) tests 9704 done 1 failed | 25 in flight, oldest 90s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........ [424%]
........................................................................ [427%]
........................................................................ [430%]
..................[contention-diag] +1482s soak 28p/253t rss 11.5G pss 10.8G swap 0.9G majflt 4890 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 36.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.7 | cgroup 11.4G/max oom_kill 0 | free scratch 330.6G/45653876i tmp 29.7G/1019835i workspace 330.6G/45653876i | repeat-01 collected 26/26 workers (60602 items) tests 9877 done 1 failed | 26 in flight, oldest 106s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................... [433%]
........................................................................ [436%]
..............................................................[contention-diag] +1498s soak 28p/235t rss 11.5G pss 10.7G swap 0.9G majflt 4915 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 36.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.03 | cgroup 11.4G/max oom_kill 0 | free scratch 330.6G/45653124i tmp 29.7G/1019835i workspace 330.6G/45653124i | repeat-01 collected 26/26 workers (60602 items) tests 10068 done 1 failed | 26 in flight, oldest 121s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......... [439%]
..........................................................[contention-diag] +1513s soak 29p/265t rss 11.5G pss 10.8G swap 1.0G majflt 4917 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 35.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.41 | cgroup 11.5G/max oom_kill 0 | free scratch 330.6G/45653062i tmp 29.7G/1019835i workspace 330.6G/45653062i | repeat-01 collected 26/26 workers (60602 items) tests 10137 done 1 failed | 26 in flight, oldest 136s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............. [442%]
.......................[contention-diag] +1528s soak 28p/284t rss 11.5G pss 10.8G swap 0.9G majflt 4969 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 35.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.77 | cgroup 11.5G/max oom_kill 0 | free scratch 330.6G/45652866i tmp 29.7G/1019835i workspace 330.6G/45652866i | repeat-01 collected 26/26 workers (60602 items) tests 10173 done 1 failed | 26 in flight, oldest 152s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................. [446%]
..........[contention-diag] +1544s soak 28p/269t rss 11.5G pss 10.8G swap 0.9G majflt 4969 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 35.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.91 | cgroup 11.5G/max oom_kill 0 | free scratch 330.6G/45652643i tmp 29.7G/1019835i workspace 330.6G/45652643i | repeat-01 collected 26/26 workers (60602 items) tests 10231 done 1 failed | 26 in flight, oldest 167s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................................. [449%]
..........[contention-diag] +1559s soak 29p/266t rss 11.6G pss 10.9G swap 1.0G majflt 4975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.72 | cgroup 11.6G/max oom_kill 0 | free scratch 330.6G/45652375i tmp 29.7G/1019835i workspace 330.6G/45652375i | repeat-01 collected 26/26 workers (60602 items) tests 10305 done 1 failed | 26 in flight, oldest 182s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................................. [452%]
...............................................[contention-diag] +1574s soak 28p/251t rss 11.6G pss 10.9G swap 0.9G majflt 4975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 36.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.9 | cgroup 11.6G/max oom_kill 0 | free scratch 330.6G/45652069i tmp 29.7G/1019835i workspace 330.6G/45652069i | repeat-01 collected 26/26 workers (60602 items) tests 10408 done 1 failed | 26 in flight, oldest 197s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................... [455%]
........................................................................ [458%]
.....................[contention-diag] +1589s soak 28p/260t rss 11.6G pss 10.9G swap 0.9G majflt 4975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 36.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 40.45 | cgroup 11.6G/max oom_kill 0 | free scratch 330.6G/45651677i tmp 29.7G/1019835i workspace 330.6G/45651677i | scratch used 0.2G in 35431 entries | repeat-01 collected 26/26 workers (60602 items) tests 10533 done 1 failed | 26 in flight, oldest 213s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................................[contention-diag] +1605s soak 28p/275t rss 11.6G pss 10.9G swap 0.9G majflt 4975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 36.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 44.31 | cgroup 11.6G/max oom_kill 0 | free scratch 330.6G/45651505i tmp 29.7G/1019835i workspace 330.6G/45651505i | repeat-01 collected 26/26 workers (60602 items) tests 10570 done 1 failed | 26 in flight, oldest 228s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............. [461%]
.......................[contention-diag] +1620s soak 29p/285t rss 11.7G pss 11.0G swap 0.9G majflt 4975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.17 | cgroup 11.7G/max oom_kill 0 | free scratch 330.6G/45651343i tmp 29.7G/1019835i workspace 330.6G/45651343i | repeat-01 collected 26/26 workers (60602 items) tests 10605 done 1 failed | 26 in flight, oldest 244s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................[contention-diag] +1636s soak 29p/267t rss 11.6G pss 10.9G swap 0.9G majflt 4998 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.4 | cgroup 11.6G/max oom_kill 0 | free scratch 330.6G/45651047i tmp 29.7G/1019835i workspace 330.6G/45651047i | repeat-01 collected 26/26 workers (60602 items) tests 10640 done 1 failed | 26 in flight, oldest 259s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............. [464%]
............................[contention-diag] +1651s soak 28p/269t rss 11.6G pss 10.9G swap 0.9G majflt 5000 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 33.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.65 | cgroup 11.7G/max oom_kill 0 | free scratch 330.6G/45650919i tmp 29.7G/1019835i workspace 330.6G/45650919i | repeat-01 collected 26/26 workers (60602 items) tests 10682 done 1 failed | 26 in flight, oldest 274s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................ [468%]
...................................................................[contention-diag] +1666s soak 33p/283t rss 11.7G pss 10.9G swap 0.9G majflt 5038 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 5 descendant rss 0.0G pss 0.0G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 33.73 | cgroup 11.7G/max oom_kill 0 | free scratch 330.6G/45650490i tmp 29.7G/1019835i workspace 330.6G/45650490i | repeat-01 collected 26/26 workers (60602 items) tests 10795 done 1 failed | 26 in flight, oldest 289s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..... [471%]
........................................................................ [474%]
........................................................................ [477%]
.............................................................[contention-diag] +1681s soak 29p/269t rss 11.7G pss 11.0G swap 0.9G majflt 5046 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 38.17 | cgroup 11.7G/max oom_kill 0 | free scratch 330.6G/45649891i tmp 29.7G/1019835i workspace 330.6G/45649891i | repeat-01 collected 26/26 workers (60602 items) tests 11002 done 1 failed | 26 in flight, oldest 61s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........... [480%]
........................................................................ [483%]
..........................................[contention-diag] +1697s soak 30p/293t rss 11.8G pss 11.0G swap 0.9G majflt 5093 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 2 descendant rss 0.1G pss 0.0G | host avail 33.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 37.67 | cgroup 11.8G/max oom_kill 0 | free scratch 330.6G/45649561i tmp 29.7G/1019835i workspace 330.6G/45649561i | repeat-01 collected 26/26 workers (60602 items) tests 11129 done 1 failed | 26 in flight, oldest 76s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.........[contention-diag] +1712s soak 31p/296t rss 11.8G pss 11.0G swap 0.9G majflt 5138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 35.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.36 | cgroup 11.7G/max oom_kill 0 | free scratch 330.6G/45649319i tmp 29.7G/1019835i workspace 330.6G/45649319i | scratch used 0.2G in 37781 entries | repeat-01 collected 26/26 workers (60602 items) tests 11135 done 1 failed | 26 in flight, oldest 91s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
..................... [486%]
........................................................................ [490%]
........................................................................ [493%]
................................[contention-diag] +1727s soak 31p/261t rss 11.7G pss 11.0G swap 0.9G majflt 5138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 0.09 cpu 41.41 | cgroup 11.7G/max oom_kill 0 | free scratch 330.6G/45648799i tmp 29.7G/1019835i workspace 330.6G/45648799i | repeat-01 collected 26/26 workers (60602 items) tests 11326 done 1 failed | 26 in flight, oldest 82s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
........................................ [496%]
.....................................[contention-diag] +1743s soak 30p/269t rss 11.8G pss 11.0G swap 0.9G majflt 5142 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.02 cpu 34.16 | cgroup 11.8G/max oom_kill 0 | free scratch 330.6G/45648558i tmp 29.7G/1019835i workspace 330.6G/45648558i | repeat-01 collected 26/26 workers (60602 items) tests 11413 done 1 failed | 26 in flight, oldest 42s gw25 tests/ace/tui/test_saved_query_slot_keys.py::test_zero_then_empty_slot_leaves_query_unchanged
................................... [499%]
..............................[contention-diag] +1758s soak 30p/278t rss 11.8G pss 11.0G swap 0.9G majflt 5145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 33.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.66 | cgroup 11.8G/max oom_kill 0 | free scratch 330.6G/45648231i tmp 29.7G/1019835i workspace 330.6G/45648231i | repeat-01 collected 26/26 workers (60602 items) tests 11476 done 1 failed | 26 in flight, oldest 40s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
.......................................... [502%]
................................................[contention-diag] +1773s soak 31p/250t rss 11.8G pss 11.1G swap 0.9G majflt 5145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.27 | cgroup 11.8G/max oom_kill 0 | free scratch 330.6G/45647999i tmp 29.7G/1019835i workspace 330.6G/45647999i | repeat-01 collected 26/26 workers (60602 items) tests 11563 done 1 failed | 25 in flight, oldest 55s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
........................ [505%]
........................................................................ [508%]
...............................................................[contention-diag] +1789s soak 28p/233t rss 11.8G pss 11.0G swap 0.9G majflt 5208 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.26 | cgroup 11.9G/max oom_kill 0 | free scratch 330.6G/45647327i tmp 29.7G/1019835i workspace 330.6G/45647327i | repeat-01 collected 26/26 workers (60602 items) tests 11717 done 1 failed | 26 in flight, oldest 41s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_action_show_artifacts_prs_and_switch_helper_land_on_patches
......... [512%]
........................[contention-diag] +1804s soak 29p/273t rss 11.8G pss 11.1G swap 0.9G majflt 5210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.45 | cgroup 11.9G/max oom_kill 0 | free scratch 330.6G/45647204i tmp 29.7G/1019835i workspace 330.6G/45647204i | repeat-01 collected 26/26 workers (60602 items) tests 11758 done 1 failed | 26 in flight, oldest 56s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
................................................ [515%]
.............................................[contention-diag] +1819s soak 31p/263t rss 11.9G pss 11.1G swap 0.9G majflt 5210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 3 descendant rss 0.1G pss 0.0G | host avail 33.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.41 | cgroup 11.9G/max oom_kill 0 | free scratch 330.6G/45646847i tmp 29.7G/1019835i workspace 330.6G/45646847i | repeat-01 collected 26/26 workers (60602 items) tests 11853 done 1 failed | 26 in flight, oldest 71s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
........................... [518%]
...................................................[contention-diag] +1834s soak 32p/247t rss 11.9G pss 11.1G swap 0.9G majflt 5210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 4 descendant rss 0.1G pss 0.0G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.61 | cgroup 11.9G/max oom_kill 0 | free scratch 330.6G/45646529i tmp 29.7G/1019835i workspace 330.6G/45646529i | scratch used 0.2G in 40579 entries | repeat-01 collected 26/26 workers (60602 items) tests 11925 done 1 failed | 26 in flight, oldest 51s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
..................... [521%]
................[contention-diag] +1850s soak 29p/259t rss 11.9G pss 11.1G swap 0.9G majflt 5225 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 38.41 | cgroup 11.9G/max oom_kill 0 | free scratch 330.6G/45646337i tmp 29.7G/1019835i workspace 330.6G/45646337i | repeat-01 collected 26/26 workers (60602 items) tests 11962 done 1 failed | 26 in flight, oldest 67s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
........................................................ [524%]
............................................[contention-diag] +1865s soak 32p/249t rss 11.8G pss 11.1G swap 0.9G majflt 5225 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 4 descendant rss 0.0G pss 0.0G | host avail 35.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 40.72 | cgroup 11.9G/max oom_kill 0 | free scratch 330.6G/45645897i tmp 29.7G/1019835i workspace 330.6G/45645897i | repeat-01 collected 26/26 workers (60602 items) tests 12058 done 1 failed | 25 in flight, oldest 82s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
............................ [527%]
........................................................................ [530%]
..................[contention-diag] +1881s soak 30p/252t rss 11.9G pss 11.1G swap 0.9G majflt 5225 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 33.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.57 | cgroup 12.0G/max oom_kill 0 | free scratch 330.6G/45645403i tmp 29.7G/1019835i workspace 330.6G/45645403i | repeat-01 collected 26/26 workers (60602 items) tests 12184 done 1 failed | 26 in flight, oldest 49s gw9 tests/ace/tui/test_projects_pane.py::test_projects_session_round_trips_current_project_display
...................................................... [534%]
........................................................................ [537%]
............[contention-diag] +1896s soak 32p/250t rss 12.0G pss 11.2G swap 0.9G majflt 5232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 4 descendant rss 0.1G pss 0.1G | host avail 34.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.8 | cgroup 12.1G/max oom_kill 0 | free scratch 330.6G/45645256i tmp 29.7G/1019835i workspace 330.6G/45645256i | repeat-01 collected 26/26 workers (60602 items) tests 12312 done 1 failed | 26 in flight, oldest 40s gw24 tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_scrolls_both_regions_in_reading_order
............................................................ [540%]
........................................................................ [543%]
....................[contention-diag] +1911s soak 30p/245t rss 11.9G pss 11.1G swap 0.8G majflt 5248 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.81 | cgroup 12.0G/max oom_kill 0 | free scratch 330.6G/45644723i tmp 29.7G/1019835i workspace 330.6G/45644723i | repeat-01 collected 26/26 workers (60602 items) tests 12468 done 1 failed | 26 in flight, oldest 55s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
.................................................... [546%]
........................................................................ [549%]
........................................................................ [552%]
............[contention-diag] +1927s soak 29p/251t rss 11.9G pss 11.1G swap 0.8G majflt 5250 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 33.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.69 | cgroup 12.0G/max oom_kill 0 | free scratch 330.6G/45644189i tmp 29.7G/1019835i workspace 330.6G/45644189i | repeat-01 collected 26/26 workers (60602 items) tests 12675 done 1 failed | 25 in flight, oldest 39s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_digit_owns_hidden_member_jump_state[None]
............................................................ [556%]
..................[contention-diag] +1942s soak 31p/268t rss 11.9G pss 11.2G swap 0.8G majflt 5250 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.6 | cgroup 12.0G/max oom_kill 0 | free scratch 330.6G/45643904i tmp 29.7G/1019835i workspace 330.6G/45643904i | repeat-01 collected 26/26 workers (60602 items) tests 12761 done 1 failed | 26 in flight, oldest 48s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
...................................................... [559%]
........................................................................ [562%]
........................................................................ [565%]
......[contention-diag] +1957s soak 28p/250t rss 11.9G pss 11.2G swap 0.8G majflt 5251 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G | host avail 32.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.52 | cgroup 12.0G/max oom_kill 0 | free scratch 330.6G/45643503i tmp 29.7G/1019833i workspace 330.6G/45643503i | scratch used 0.2G in 43634 entries | repeat-01 collected 26/26 workers (60602 items) tests 12927 done 1 failed | 25 in flight, oldest 50s gw25 tests/ace/tui/test_statistics_perf.py::test_perf_tiles_are_plain_and_do_not_navigate
.................................................................. [568%]
........................................................................ [571%]
............................................[contention-diag] +1973s soak 28p/255t rss 11.9G pss 11.2G swap 0.8G majflt 5254 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.65 | cgroup 12.1G/max oom_kill 0 | free scratch 330.6G/45642946i tmp 29.7G/1019835i workspace 330.6G/45642946i | repeat-01 collected 26/26 workers (60602 items) tests 13131 done 1 failed | 26 in flight, oldest 61s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
............................ [574%]
........................................................................ [578%]
........................................................................ [581%]
..................................................[contention-diag] +1988s soak 29p/264t rss 12.0G pss 11.2G swap 0.8G majflt 5259 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.16 | cgroup 12.1G/max oom_kill 0 | free scratch 330.6G/45642380i tmp 29.7G/1019835i workspace 330.6G/45642380i | repeat-01 collected 26/26 workers (60602 items) tests 13361 done 1 failed | 26 in flight, oldest 53s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
...................... [584%]
.......................................................................[contention-diag] +2003s soak 30p/261t rss 12.1G pss 11.3G swap 0.8G majflt 5259 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 2 descendant rss 0.1G pss 0.0G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 40.3 | cgroup 12.1G/max oom_kill 0 | free scratch 330.6G/45641964i tmp 29.7G/1019835i workspace 330.6G/45641964i | repeat-01 collected 26/26 workers (60602 items) tests 13460 done 1 failed | 26 in flight, oldest 60s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
. [587%]
.......................................................................[contention-diag] +2019s soak 36p/263t rss 12.1G pss 11.4G swap 0.8G majflt 5570 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 8 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.28 | cgroup 12.2G/max oom_kill 0 | free scratch 330.6G/45641620i tmp 29.7G/1019835i workspace 330.6G/45641620i | repeat-01 collected 26/26 workers (60602 items) tests 13530 done 1 failed | 26 in flight, oldest 45s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycles_ranked_projects_and_survives_range_change
. [590%]
...............................[contention-diag] +2034s soak 33p/275t rss 12.1G pss 11.4G swap 0.8G majflt 5264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 38.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.37 | cgroup 12.2G/max oom_kill 0 | free scratch 330.6G/45641330i tmp 29.7G/1019835i workspace 330.6G/45641330i | repeat-01 collected 26/26 workers (60602 items) tests 13566 done 1 failed | 26 in flight, oldest 60s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycles_ranked_projects_and_survives_range_change
......................................... [593%]
........................................................................ [596%]
.....................[contention-diag] +2049s soak 32p/283t rss 12.1G pss 11.3G swap 0.8G majflt 5264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 4 descendant rss 0.1G pss 0.1G | host avail 37.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.05 | cgroup 12.3G/max oom_kill 0 | free scratch 330.6G/45640778i tmp 29.7G/1019835i workspace 330.6G/45640778i | repeat-01 collected 26/26 workers (60602 items) tests 13685 done 1 failed | 25 in flight, oldest 69s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
................................................... [600%]
..........................................[contention-diag] +2065s soak 30p/275t rss 12.1G pss 11.3G swap 0.8G majflt 5264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 2 descendant rss 0.0G pss 0.0G | host avail 37.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.87 | cgroup 12.4G/max oom_kill 0 | free scratch 330.6G/45640494i tmp 29.7G/1019835i workspace 330.6G/45640494i | repeat-01 collected 26/26 workers (60602 items) tests 13785 done 1 failed | 26 in flight, oldest 85s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
.............................. [603%]
........................................................................ [606%]
.........[contention-diag] +2080s soak 32p/244t rss 12.2G pss 11.4G swap 0.8G majflt 5264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 4 descendant rss 0.1G pss 0.1G | host avail 36.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.25 | cgroup 12.4G/max oom_kill 0 | free scratch 330.6G/45640070i tmp 29.7G/1019835i workspace 330.6G/45640070i | scratch used 0.3G in 47043 entries | repeat-01 collected 26/26 workers (60602 items) tests 13881 done 1 failed | 26 in flight, oldest 95s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................................................... [609%]
......................................................[contention-diag] +2096s soak 31p/246t rss 12.1G pss 11.3G swap 0.8G majflt 5282 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 3 descendant rss 0.0G pss 0.0G | host avail 37.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.52 | cgroup 12.4G/max oom_kill 0 | free scratch 330.6G/45639595i tmp 29.7G/1019835i workspace 330.6G/45639595i | repeat-01 collected 26/26 workers (60602 items) tests 14021 done 1 failed | 26 in flight, oldest 40s gw6 tests/ace/tui/test_macro_browser_filter.py::test_cached_reactivation_restores_open_filter_or_list
.................. [612%]
........................................................................ [615%]
................................................[contention-diag] +2111s soak 28p/250t rss 12.1G pss 11.3G swap 0.8G majflt 5287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G | host avail 36.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.52 | cgroup 12.5G/max oom_kill 0 | free scratch 330.6G/45638773i tmp 29.7G/1019835i workspace 330.6G/45638773i | repeat-01 collected 26/26 workers (60602 items) tests 14154 done 1 failed | 26 in flight, oldest 49s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle
........................ [618%]
........................................................................ [621%]
........................................................................ [625%]
..........................[contention-diag] +2126s soak 31p/268t rss 12.1G pss 11.3G swap 0.8G majflt 5304 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G, 3 descendant rss 0.0G pss 0.0G | host avail 36.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.35 | cgroup 12.5G/max oom_kill 0 | free scratch 330.6G/45638620i tmp 29.7G/1019835i workspace 330.6G/45638620i | repeat-01 collected 26/26 workers (60602 items) tests 14345 done 1 failed | 26 in flight, oldest 49s gw9 tests/ace/tui/test_projects_pane.py::test_projects_filter_yields_tab_to_admin_center
.............................................. [628%]
........................................................................ [631%]
............................................................[contention-diag] +2142s soak 32p/244t rss 12.2G pss 11.4G swap 0.8G majflt 5354 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 4 descendant rss 0.0G pss 0.0G | host avail 36.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.84 | cgroup 12.4G/max oom_kill 0 | free scratch 330.5G/45638112i tmp 29.7G/1019835i workspace 330.5G/45638112i | repeat-01 collected 26/26 workers (60602 items) tests 14528 done 1 failed | 26 in flight, oldest 51s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
............ [634%]
........................................................................ [637%]
........................................................................ [640%]
...................[contention-diag] +2157s soak 30p/245t rss 12.2G pss 11.4G swap 0.8G majflt 5421 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 2 descendant rss 0.0G pss 0.0G | host avail 35.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 31.0 | cgroup 12.5G/max oom_kill 0 | free scratch 330.5G/45637514i tmp 29.7G/1019835i workspace 330.5G/45637514i | repeat-01 collected 26/26 workers (60602 items) tests 14697 done 1 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
..................................................... [643%]
....................................................[contention-diag] +2172s soak 30p/244t rss 12.2G pss 11.4G swap 0.8G majflt 5438 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 2 descendant rss 0.0G pss 0.0G | host avail 35.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 34.42 | cgroup 12.5G/max oom_kill 0 | free scratch 330.5G/45636626i tmp 29.7G/1019835i workspace 330.5G/45636626i | repeat-01 collected 26/26 workers (60602 items) tests 14809 done 1 failed | 26 in flight, oldest 66s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_deck_close_each_and_erase_through_keys
.................... [647%]
........................................................................ [650%]
.....................................................................[contention-diag] +2187s soak 29p/243t rss 12.2G pss 11.4G swap 0.8G majflt 5448 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 1 descendant rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 29.88 | cgroup 12.5G/max oom_kill 0 | free scratch 330.5G/45635589i tmp 29.7G/1019835i workspace 330.5G/45635589i | repeat-01 collected 26/26 workers (60602 items) tests 14967 done 1 failed | 25 in flight, oldest 39s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_filter_no_matches
... [653%]
........................................................................ [656%]
........................................................................ [659%]
........................................................................ [662%]
....................[contention-diag] +2203s soak 31p/270t rss 12.3G pss 11.5G swap 0.8G majflt 5456 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 35.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.13 cpu 34.59 | cgroup 12.5G/max oom_kill 0 | free scratch 330.5G/45634456i tmp 29.7G/1019835i workspace 330.5G/45634456i | scratch used 0.3G in 52625 entries | repeat-01 collected 26/26 workers (60602 items) tests 15188 done 1 failed | 25 in flight, oldest 49s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_brackets_cycle_config_subtabs_from_macro_list_and_filter
.................................................... [665%]
........................................................................ [669%]
........................................................................ [672%]
.......................................................................[contention-diag] +2218s soak 32p/265t rss 12.4G pss 11.6G swap 0.8G majflt 5472 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 4 descendant rss 0.1G pss 0.1G | host avail 35.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 34.71 | cgroup 12.6G/max oom_kill 0 | free scratch 330.5G/45633308i tmp 29.7G/1019835i workspace 330.5G/45633308i | repeat-01 collected 26/26 workers (60602 items) tests 15465 done 1 failed | 26 in flight, oldest 61s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
. [675%]
........................................................................ [678%]
........................................................................ [681%]
[contention-diag] +2234s soak 34p/248t rss 12.3G pss 11.5G swap 0.8G majflt 5481 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 6 descendant rss 0.0G pss 0.0G | host avail 35.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.8 cpu 37.96 | cgroup 12.6G/max oom_kill 0 | free scratch 330.5G/45632498i tmp 29.7G/1019835i workspace 330.5G/45632498i | repeat-01 collected 26/26 workers (60602 items) tests 15623 done 1 failed | 26 in flight, oldest 77s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................................................ [684%]
....................................................................[contention-diag] +2249s soak 33p/246t rss 12.5G pss 11.7G swap 0.8G majflt 5483 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 5 descendant rss 0.2G pss 0.1G | host avail 35.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.9 cpu 37.48 | cgroup 12.7G/max oom_kill 0 | free scratch 330.5G/45631764i tmp 29.7G/1019835i workspace 330.5G/45631764i | repeat-01 collected 26/26 workers (60602 items) tests 15759 done 1 failed | 25 in flight, oldest 92s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.... [687%]
........................................................................ [691%]
........................................................................ [694%]
........................................................................ [697%]
....................[contention-diag] +2264s soak 31p/250t rss 12.4G pss 11.6G swap 0.8G majflt 5484 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 3 descendant rss 0.1G pss 0.1G | host avail 35.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 42.34 | cgroup 12.6G/max oom_kill 0 | free scratch 330.5G/45630799i tmp 29.7G/1019835i workspace 330.5G/45630799i | repeat-01 collected 26/26 workers (60602 items) tests 15976 done 1 failed | 26 in flight, oldest 107s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................... [700%]
........................................................................ [703%]
........................................................................ [706%]
........................................................................ [709%]
...........................[contention-diag] +2280s soak 33p/245t rss 12.4G pss 11.6G swap 0.7G majflt 5506 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 5 descendant rss 0.1G pss 0.0G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 33.27 | cgroup 12.7G/max oom_kill 0 | free scratch 330.5G/45629954i tmp 29.7G/1019835i workspace 330.5G/45629954i | repeat-01 collected 26/26 workers (60602 items) tests 16289 done 1 failed | 25 in flight, oldest 122s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............................................. [713%]
........................................................................ [716%]
........................................................................ [719%]
.................................................................[contention-diag] +2295s soak 36p/248t rss 12.5G pss 11.7G swap 0.7G majflt 5515 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 8 descendant rss 0.1G pss 0.1G | host avail 34.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 33.61 | cgroup 12.7G/max oom_kill 0 | free scratch 330.5G/45628641i tmp 29.7G/1019835i workspace 330.5G/45628641i | repeat-01 collected 26/26 workers (60602 items) tests 16536 done 1 failed | 26 in flight, oldest 138s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
....... [722%]
........................................................................ [725%]
........................................................................ [728%]
......................................................[contention-diag] +2310s soak 32p/251t rss 12.4G pss 11.6G swap 0.7G majflt 5536 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 4 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.68 cpu 35.73 | cgroup 12.7G/max oom_kill 0 | free scratch 330.5G/45627912i tmp 29.7G/1019835i workspace 330.5G/45627912i | repeat-01 collected 26/26 workers (60602 items) tests 16750 done 1 failed | 26 in flight, oldest 153s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................. [731%]
........................................................................ [735%]
........................................................................ [738%]
..........................[contention-diag] +2326s soak 34p/255t rss 12.5G pss 11.6G swap 0.7G majflt 5575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 6 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 34.01 | cgroup 12.8G/max oom_kill 0 | free scratch 330.5G/45629595i tmp 29.7G/1019835i workspace 330.5G/45629595i | scratch used 0.3G in 57522 entries | repeat-01 collected 26/26 workers (60602 items) tests 16941 done 1 failed | 26 in flight, oldest 69s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.............................................. [741%]
........................................................................ [744%]
[contention-diag] +2341s soak 35p/266t rss 12.4G pss 11.6G swap 0.7G majflt 5585 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.4G, 7 descendant rss 0.0G pss 0.0G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.05 cpu 37.04 | cgroup 12.8G/max oom_kill 0 | free scratch 330.5G/45629215i tmp 29.7G/1019835i workspace 330.5G/45629215i | repeat-01 collected 26/26 workers (60602 items) tests 17056 done 1 failed | 26 in flight, oldest 85s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
........................................................................ [747%]
........................................................................ [750%]
........................................................................ [753%]
........................................................................ [757%]
....................................................[contention-diag] +2357s soak 33p/278t rss 12.5G pss 11.7G swap 0.7G majflt 5602 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 5 descendant rss 0.1G pss 0.1G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.25 cpu 29.57 | cgroup 12.9G/max oom_kill 0 | free scratch 330.5G/45628154i tmp 29.7G/1019835i workspace 330.5G/45628154i | repeat-01 collected 26/26 workers (60602 items) tests 17396 done 1 failed | 26 in flight, oldest 100s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.................... [760%]
........................................................................ [763%]
........................................................................ [766%]
.....[contention-diag] +2372s soak 33p/270t rss 12.5G pss 11.7G swap 0.7G majflt 5619 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 5 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.18 cpu 30.92 | cgroup 12.9G/max oom_kill 0 | free scratch 330.5G/45627703i tmp 29.7G/1019835i workspace 330.5G/45627703i | repeat-01 collected 26/26 workers (60602 items) tests 17559 done 1 failed | 25 in flight, oldest 116s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
................................................................... [769%]
........................................................................ [772%]
..................F[contention-failure] call tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe47df99a90>

    async def test_startup_update_toast_appears_once_in_tui(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        status = _status()
        # Commit previews (git and GitHub queries against the installed
        # components) and the Rust prebuild are not what this test asserts; left
        # on, they ran real subprocesses and network calls on the toast path.
        monkeypatch.setattr(
            update_toast,
            "_load_update_toast_config",
            lambda: update_toast._UpdateToastConfig(
                startup_toast=True, incoming_commits_enabled=False, prebuild_rust=False
            ),
        )
        monkeypatch.setattr(
            update_toast,
            "get_cached_update_status",
            lambda **_kwargs: status,
        )
    
        async with AcePage(query='"toast"', startup_policy="real") as page:
            # Hang guard for a whole real startup: the toast lands only after the
            # deferred maintenance chain, about 3 CPU-seconds from test start
            # unloaded -- 50-90 s at the contention soak's CPU share, past the
            # single-wait default.
            await page.wait_for(
                lambda _s: bool(list(page.app._notifications)),
                timeout=_REAL_STARTUP_TOAST_TIMEOUT,
            )
            notifications = list(page.app._notifications)
            assert len(notifications) == 1
            assert notifications[0].title == f"{UPDATE_GLYPH} Updates available"
            assert "Press" in notifications[0].message
    
            page.app._show_startup_update_toast(status)
            await page.pause()
>           assert len(list(page.app._notifications)) == 1
E           AssertionError: assert 0 == 1
E            +  where 0 = len([])
E            +    where [] = list(<textual.notifications.Notifications object at 0x7fe4aff3a0c0>)
E            +      where <textual.notifications.Notifications object at 0x7fe4aff3a0c0> = AceApp(title='sase tui (v0.18.1+442.gdde1ada13)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})._notifications
E            +        where AceApp(title='sase tui (v0.18.1+442.gdde1ada13)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'}) = <sase.ace.testing.ace_page.AcePage object at 0x7fe4ae9b8620>.app

tests/ace/tui/test_update_toast_startup.py:189: AssertionError
........................[contention-diag] +2387s soak 32p/238t rss 12.4G pss 11.6G swap 0.7G majflt 5634 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 36.53 | cgroup 12.7G/max oom_kill 0 | free scratch 330.5G/45627041i tmp 29.7G/1019835i workspace 330.5G/45627041i | repeat-01 collected 26/26 workers (60602 items) tests 17749 done 2 failed | 26 in flight, oldest 126s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
............................. [775%]
........................................................................ [779%]
........................................................................ [782%]
........................................................................ [785%]
...................................[contention-diag] +2403s soak 35p/244t rss 12.5G pss 11.6G swap 0.7G majflt 5641 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 7 descendant rss 0.1G pss 0.0G | host avail 34.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 35.26 | cgroup 12.8G/max oom_kill 0 | free scratch 330.5G/45626428i tmp 29.7G/1019835i workspace 330.5G/45626428i | repeat-01 collected 26/26 workers (60602 items) tests 18031 done 2 failed | 26 in flight, oldest 38s gw21 tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
..................................... [788%]
........................................................................ [791%]
......................................................................[contention-diag] +2418s soak 32p/250t rss 12.5G pss 11.5G swap 0.7G majflt 5645 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 4 descendant rss 0.1G pss 0.1G | host avail 34.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 35.58 | cgroup 12.8G/max oom_kill 0 | free scratch 330.5G/45625900i tmp 29.7G/1019835i workspace 330.5G/45625900i | repeat-01 collected 26/26 workers (60602 items) tests 18210 done 2 failed | 26 in flight, oldest 53s gw21 tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
.. [794%]
........................................................................ [797%]
....................................................................[contention-diag] +2433s soak 33p/240t rss 12.5G pss 11.7G swap 0.7G majflt 5650 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 5 descendant rss 0.1G pss 0.0G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.09/0.0 io 0.73 cpu 39.76 | cgroup 12.9G/max oom_kill 0 | free scratch 330.5G/45625274i tmp 29.7G/1019835i workspace 330.5G/45625274i | repeat-01 collected 26/26 workers (60602 items) tests 18350 done 2 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.... [801%]
........................................................................ [804%]
........................................................................ [807%]
.......................................[contention-diag] +2449s soak 37p/250t rss 12.6G pss 11.8G swap 0.7G majflt 5650 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.5G, 9 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.4 cpu 32.56 | cgroup 12.9G/max oom_kill 0 | free scratch 330.5G/45624566i tmp 29.7G/1019835i workspace 330.5G/45624566i | scratch used 0.3G in 62707 entries | repeat-01 collected 26/26 workers (60602 items) tests 18538 done 2 failed | 26 in flight, oldest 71s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................................. [810%]
........................................................................ [813%]
........................................................................ [816%]
........................................................................ [819%]
.................[contention-diag] +2464s soak 39p/237t rss 12.5G pss 11.7G swap 0.7G majflt 5653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 11 descendant rss 0.0G pss 0.0G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 35.7 | cgroup 12.9G/max oom_kill 0 | free scratch 330.5G/45623999i tmp 29.7G/1019835i workspace 330.5G/45623999i | repeat-01 collected 26/26 workers (60602 items) tests 18807 done 2 failed | 26 in flight, oldest 87s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
....................................................... [823%]
........................................................................ [826%]
........................................................................ [829%]
........................................................................ [832%]
........................................................................ [835%]
.........[contention-diag] +2480s soak 34p/235t rss 12.7G pss 11.8G swap 0.7G majflt 5663 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 33.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 35.65 | cgroup 12.9G/max oom_kill 0 | free scratch 330.5G/45623312i tmp 29.7G/1019835i workspace 330.5G/45623312i | repeat-01 collected 26/26 workers (60602 items) tests 19137 done 2 failed | 25 in flight, oldest 38s gw16 tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_already_absent_toasts
............................................................... [838%]
........................................................................ [841%]
..........................................................s............. [845%]
........................................................................ [848%]
.................[contention-diag] +2495s soak 38p/257t rss 12.6G pss 11.8G swap 0.7G majflt 5663 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 10 descendant rss 0.1G pss 0.0G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 30.06 | cgroup 13.0G/max oom_kill 0 | free scratch 330.5G/45622567i tmp 29.7G/1019835i workspace 330.5G/45622567i | repeat-01 collected 26/26 workers (60602 items) tests 19445 done 2 failed | 24 in flight, oldest 47s gw1 tests/test_command_palette_e2e.py::test_colon_opens_command_line_from_axe_tab
....................................................... [851%]
s..s.................................................................... [854%]
...............[contention-diag] +2510s soak 41p/260t rss 12.8G pss 11.9G swap 0.7G majflt 5667 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 13 descendant rss 0.2G pss 0.1G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 40.67 | cgroup 13.0G/max oom_kill 0 | free scratch 330.5G/45621817i tmp 29.7G/1019835i workspace 330.5G/45621817i | repeat-01 collected 26/26 workers (60602 items) tests 19593 done 2 failed | 26 in flight, oldest 62s gw1 tests/test_command_palette_e2e.py::test_colon_opens_command_line_from_axe_tab
......................................................... [857%]
........................................................................ [860%]
........................................................................ [863%]
.....................................................................[contention-diag] +2526s soak 39p/247t rss 12.8G pss 11.9G swap 0.7G majflt 5674 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 11 descendant rss 0.2G pss 0.1G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 35.36 | cgroup 13.1G/max oom_kill 0 | free scratch 330.5G/45620783i tmp 29.7G/1019835i workspace 330.5G/45620783i | repeat-01 collected 26/26 workers (60602 items) tests 19862 done 2 failed | 26 in flight, oldest 63s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
... [867%]
........................................................................ [870%]
........................................................................ [873%]
.s................................................................[contention-diag] +2541s soak 34p/244t rss 12.8G pss 11.9G swap 0.7G majflt 5678 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 33.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 35.56 | cgroup 13.1G/max oom_kill 0 | free scratch 330.5G/45620560i tmp 29.7G/1019835i workspace 330.5G/45620560i | repeat-01 collected 26/26 workers (60602 items) tests 20079 done 2 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
...... [876%]
........................................................................ [879%]
........................................................................ [882%]
........................................................................ [885%]
...........................[contention-diag] +2556s soak 34p/266t rss 12.8G pss 11.9G swap 0.7G majflt 5703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 32.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 34.17 | cgroup 13.1G/max oom_kill 0 | free scratch 330.5G/45619947i tmp 29.7G/1019835i workspace 330.5G/45619947i | repeat-01 collected 26/26 workers (60602 items) tests 20313 done 2 failed | 26 in flight, oldest 80s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............................................. [889%]
........................................................................ [892%]
.................................[contention-diag] +2572s soak 35p/262t rss 12.8G pss 11.9G swap 0.7G majflt 5707 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 37.95 | cgroup 13.2G/max oom_kill 0 | free scratch 330.5G/45619334i tmp 29.7G/1019835i workspace 330.5G/45619334i | scratch used 0.4G in 67765 entries | repeat-01 collected 26/26 workers (60602 items) tests 20478 done 2 failed | 26 in flight, oldest 95s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
....................................... [895%]
..................................................................[contention-diag] +2588s soak 34p/272t rss 12.7G pss 11.8G swap 0.7G majflt 5712 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 6 descendant rss 0.2G pss 0.1G | host avail 32.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 31.74 | cgroup 13.1G/max oom_kill 0 | free scratch 330.5G/45618873i tmp 29.7G/1019835i workspace 330.5G/45618873i | repeat-01 collected 26/26 workers (60602 items) tests 20578 done 2 failed | 26 in flight, oldest 111s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
...... [898%]
........................................................................ [901%]
........................................................................ [904%]
.....................................[contention-diag] +2603s soak 32p/268t rss 12.6G pss 11.8G swap 0.7G majflt 5714 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 4 descendant rss 0.1G pss 0.0G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.04 cpu 38.59 | cgroup 13.0G/max oom_kill 0 | free scratch 330.5G/45618056i tmp 29.7G/1019835i workspace 330.5G/45618056i | repeat-01 collected 26/26 workers (60602 items) tests 20767 done 2 failed | 26 in flight, oldest 69s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
................................... [907%]
........................................................................ [910%]
......[contention-diag] +2618s soak 36p/281t rss 12.7G pss 11.8G swap 0.7G majflt 5722 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 8 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 31.91 | cgroup 13.0G/max oom_kill 0 | free scratch 330.5G/45617737i tmp 29.7G/1019833i workspace 330.5G/45617737i | repeat-01 collected 26/26 workers (60602 items) tests 20879 done 2 failed | 26 in flight, oldest 48s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_agents_tab
.................................................................. [914%]
....................................................................[contention-diag] +2634s soak 34p/277t rss 12.7G pss 11.9G swap 0.7G majflt 5730 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 34.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.05 cpu 33.9 | cgroup 13.1G/max oom_kill 0 | free scratch 330.4G/45616235i tmp 29.7G/1019833i workspace 330.4G/45616235i | repeat-01 collected 26/26 workers (60602 items) tests 21014 done 2 failed | 26 in flight, oldest 35s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_pending_perf_load_cannot_restore_stale_rail
.... [917%]
........................................................................ [920%]
........................................................................ [923%]
............................................................[contention-diag] +2649s soak 40p/251t rss 12.9G pss 12.0G swap 0.7G majflt 5732 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 12 descendant rss 0.3G pss 0.2G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.07 cpu 29.97 | cgroup 13.2G/max oom_kill 0 | free scratch 330.4G/45616588i tmp 29.7G/1019833i workspace 330.4G/45616588i | repeat-01 collected 26/26 workers (60602 items) tests 21222 done 2 failed | 25 in flight, oldest 48s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
............ [926%]
........................................................................ [929%]
........................................................................ [932%]
........................................................................ [936%]
........................................................................ [939%]
..............................[contention-diag] +2664s soak 35p/238t rss 12.8G pss 12.0G swap 0.7G majflt 5733 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 7 descendant rss 0.2G pss 0.2G | host avail 33.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.05 cpu 29.31 | cgroup 13.2G/max oom_kill 0 | free scratch 330.4G/45615849i tmp 29.7G/1019833i workspace 330.4G/45615848i | repeat-01 collected 26/26 workers (60602 items) tests 21552 done 2 failed | 25 in flight, oldest 59s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
.......................................... [942%]
........................................................................ [945%]
........................................................................ [948%]
........................................................................ [951%]
........................................................................ [954%]
........................................................................ [958%]
s.........................................................[contention-diag] +2680s soak 33p/187t rss 12.7G pss 11.9G swap 0.7G majflt 5750 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 36.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.7/0.7 io 2.07 cpu 26.73 | cgroup 13.1G/max oom_kill 0 | free scratch 330.4G/45613322i tmp 29.7G/1019833i workspace 330.4G/45613322i | repeat-01 collected 26/26 workers (60602 items) tests 22015 done 2 failed | 25 in flight, oldest 35s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail
.............. [961%]
........................................................................ [964%]
........................................................................ [967%]
............................s........................................... [970%]
........................................................................ [973%]
........................................................................ [976%]
.......................[contention-diag] +2695s soak 33p/208t rss 12.8G pss 11.9G swap 0.7G majflt 5754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 37.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.17/0.17 io 1.56 cpu 28.78 | cgroup 13.1G/max oom_kill 0 | free scratch 330.4G/45613762i tmp 29.7G/1019833i workspace 330.4G/45613762i | scratch used 0.4G in 73359 entries | repeat-01 collected 26/26 workers (60602 items) tests 22318 done 2 failed | 25 in flight, oldest 51s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail
................................................. [980%]
........................................................................ [983%]
........................................................................ [986%]
........................................................................ [989%]
........................................................................ [992%]
........................................................................ [995%]
........................................................................ [998%]
....[contention-diag] +2711s soak 34p/186t rss 12.8G pss 11.9G swap 0.7G majflt 5764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.26 cpu 29.26 | cgroup 13.1G/max oom_kill 0 | free scratch 330.4G/45612486i tmp 29.7G/1019833i workspace 330.4G/45612486i | repeat-01 collected 26/26 workers (60602 items) tests 22888 done 2 failed | 26 in flight, oldest 36s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
.................................................................... [1002%]
........................................................................ [1005%]
........................................................................ [1008%]
................................................................[contention-diag] +2726s soak 41p/210t rss 12.9G pss 12.0G swap 0.7G majflt 5801 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 13 descendant rss 0.2G pss 0.2G | host avail 35.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.57 cpu 27.75 | cgroup 13.2G/max oom_kill 0 | free scratch 330.4G/45611774i tmp 29.7G/1019833i workspace 330.4G/45611774i | repeat-01 collected 26/26 workers (60602 items) tests 23159 done 2 failed | 26 in flight, oldest 51s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
........ [1011%]
........................................................................ [1014%]
........................................................................ [1017%]
........................................................................ [1020%]
....................................................................[contention-diag] +2741s soak 35p/202t rss 12.9G pss 11.9G swap 0.7G majflt 5781 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.47 cpu 27.49 | cgroup 13.2G/max oom_kill 0 | free scratch 330.4G/45610523i tmp 29.7G/1019833i workspace 330.4G/45610523i | repeat-01 collected 26/26 workers (60602 items) tests 23451 done 2 failed | 26 in flight, oldest 67s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
.... [1024%]
........................................................................ [1027%]
........................................................................ [1030%]
........................................................................ [1033%]
........................................................................ [1036%]
........................................................................ [1039%]
...........................[contention-diag] +2757s soak 41p/204t rss 13.1G pss 12.1G swap 0.7G majflt 5792 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 13 descendant rss 0.4G pss 0.3G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 2.07/1.34 io 1.1 cpu 27.56 | cgroup 13.4G/max oom_kill 0 | free scratch 330.4G/45609623i tmp 29.7G/1019833i workspace 330.4G/45609623i | repeat-01 collected 26/26 workers (60602 items) tests 23843 done 2 failed | 25 in flight, oldest 60s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_refresh_and_hidden_tab_keep_the_active_view_rail
............................................. [1042%]
........................................................................ [1046%]
........................................................................ [1049%]
............................[contention-diag] +2772s soak 33p/206t rss 12.9G pss 12.0G swap 0.7G majflt 5792 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 5 descendant rss 0.2G pss 0.1G | host avail 35.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.46/0.31 io 2.64 cpu 31.48 | cgroup 13.2G/max oom_kill 0 | free scratch 330.4G/45608912i tmp 29.7G/1019833i workspace 330.4G/45608912i | repeat-01 collected 26/26 workers (60602 items) tests 24076 done 2 failed | 25 in flight, oldest 64s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
............................................ [1052%]
........................................................................ [1055%]
........................................................................ [1058%]
...................................[contention-diag] +2787s soak 42p/216t rss 13.0G pss 12.1G swap 0.7G majflt 5795 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 14 descendant rss 0.3G pss 0.2G | host avail 35.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.09/0.06 io 2.42 cpu 28.74 | cgroup 13.4G/max oom_kill 0 | free scratch 330.4G/45608219i tmp 29.7G/1019833i workspace 330.4G/45608219i | repeat-01 collected 26/26 workers (60602 items) tests 24292 done 2 failed | 25 in flight, oldest 79s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
..................................... [1061%]
........................................................................ [1064%]
........................................................................ [1068%]
........................................................................ [1071%]
...........[contention-diag] +2803s soak 44p/201t rss 13.1G pss 12.1G swap 0.7G majflt 5796 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 16 descendant rss 0.4G pss 0.3G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 4.12 cpu 28.67 | cgroup 13.6G/max oom_kill 0 | free scratch 330.4G/45607371i tmp 29.7G/1019833i workspace 330.4G/45607371i | repeat-01 collected 26/26 workers (60602 items) tests 24554 done 2 failed | 26 in flight, oldest 95s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
............................................................. [1074%]
........................................................................ [1077%]
........................................................................ [1080%]
...................[contention-diag] +2818s soak 33p/184t rss 12.8G pss 11.9G swap 0.7G majflt 5797 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 5 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.99 cpu 28.4 | cgroup 13.3G/max oom_kill 0 | free scratch 330.4G/45606725i tmp 29.7G/1019833i workspace 330.4G/45606725i | scratch used 0.4G in 80402 entries | repeat-01 collected 26/26 workers (60602 items) tests 24773 done 2 failed | 26 in flight, oldest 110s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
..................................................... [1083%]
........................................................................ [1086%]
........................................................................ [1090%]
................................................................[contention-diag] +2834s soak 35p/197t rss 12.9G pss 11.9G swap 0.7G majflt 5808 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 7 descendant rss 0.2G pss 0.0G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.46 cpu 29.97 | cgroup 13.3G/max oom_kill 0 | free scratch 330.4G/45605975i tmp 29.7G/1019833i workspace 330.4G/45605976i | repeat-01 collected 26/26 workers (60602 items) tests 25043 done 2 failed | 26 in flight, oldest 126s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........ [1093%]
........................................................................ [1096%]
........................................................................ [1099%]
........................................................................ [1102%]
....................[contention-diag] +2849s soak 36p/186t rss 13.0G pss 12.1G swap 0.7G majflt 5812 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 8 descendant rss 0.2G pss 0.2G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.14 cpu 26.87 | cgroup 13.4G/max oom_kill 0 | free scratch 330.4G/45605280i tmp 29.7G/1019833i workspace 330.4G/45605280i | repeat-01 collected 26/26 workers (60602 items) tests 25285 done 2 failed | 25 in flight, oldest 141s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.................................................s.. [1105%]
........................................................................ [1108%]
........................................................................ [1112%]
........................................................................ [1115%]
........................................................................ [1118%]
........................[contention-diag] +2865s soak 36p/191t rss 13.0G pss 12.0G swap 0.7G majflt 5812 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 8 descendant rss 0.2G pss 0.1G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 1.61 cpu 28.24 | cgroup 13.4G/max oom_kill 0 | free scratch 330.4G/45604346i tmp 29.7G/1019833i workspace 330.4G/45604346i | repeat-01 collected 26/26 workers (60602 items) tests 25640 done 2 failed | 26 in flight, oldest 157s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................................................ [1121%]
........................................................................ [1124%]
........................................................................ [1127%]
.................................................[contention-diag] +2880s soak 33p/180t rss 13.0G pss 12.0G swap 0.7G majflt 5816 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 5 descendant rss 0.2G pss 0.1G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.59 cpu 29.75 | cgroup 13.4G/max oom_kill 0 | free scratch 330.4G/45603564i tmp 29.7G/1019833i workspace 330.4G/45603564i | repeat-01 collected 26/26 workers (60602 items) tests 25894 done 2 failed | 26 in flight, oldest 172s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
....................... [1130%]
........................................................................ [1134%]
........................................................................ [1137%]
........................................................[contention-diag] +2895s soak 32p/178t rss 12.8G pss 11.9G swap 0.6G majflt 5834 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 4 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 3.13 cpu 27.99 | cgroup 13.3G/max oom_kill 0 | free scratch 330.4G/45602616i tmp 29.7G/1019833i workspace 330.4G/45602615i | repeat-01 collected 26/26 workers (60602 items) tests 26102 done 2 failed | 25 in flight, oldest 187s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................ [1140%]
........................................................................ [1143%]
........................................................................ [1146%]
........................................................................ [1149%]
........................................................................ [1152%]
........................................................................ [1156%]
........................................................................ [1159%]
........................................................................ [1162%]
..[contention-diag] +2911s soak 30p/160t rss 12.8G pss 11.9G swap 0.6G majflt 5838 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 2 descendant rss 0.0G pss 0.0G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.67 cpu 31.07 | cgroup 13.4G/max oom_kill 0 | free scratch 330.4G/45602576i tmp 29.7G/1019833i workspace 330.4G/45602576i | repeat-01 collected 26/26 workers (60602 items) tests 26616 done 2 failed | 25 in flight, oldest 202s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...................................................................... [1165%]
........................................................................ [1168%]
.....................................................................[contention-diag] +2926s soak 33p/162t rss 13.0G pss 12.0G swap 0.7G majflt 5839 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 5 descendant rss 0.2G pss 0.1G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.19 cpu 30.72 | cgroup 13.5G/max oom_kill 0 | free scratch 330.4G/45601867i tmp 29.7G/1019832i workspace 330.4G/45601867i | repeat-01 collected 26/26 workers (60602 items) tests 26831 done 2 failed | 23 in flight, oldest 162s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
... [1171%]
........................................................................ [1174%]
........................................................................ [1178%]
........................................................................ [1181%]
........................................................................ [1184%]
..........................................[contention-diag] +2941s soak 36p/177t rss 13.0G pss 12.1G swap 0.7G majflt 5840 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.7G, 8 descendant rss 0.2G pss 0.1G | host avail 33.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.26 cpu 29.03 | cgroup 13.6G/max oom_kill 0 | free scratch 330.4G/45600966i tmp 29.7G/1019833i workspace 330.4G/45600965i | scratch used 0.5G in 86314 entries | repeat-01 collected 26/26 workers (60602 items) tests 27158 done 2 failed | 25 in flight, oldest 177s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.............................. [1187%]
........................................................................ [1190%]
........................................................................ [1193%]
........................................................................ [1196%]
........................................................................ [1200%]
....[contention-diag] +2958s soak 36p/173t rss 13.2G pss 12.2G swap 0.7G majflt 5858 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 8 descendant rss 0.3G pss 0.3G | host avail 32.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.06 cpu 25.95 | cgroup 13.6G/max oom_kill 0 | free scratch 330.4G/45599585i tmp 29.7G/1019833i workspace 330.4G/45599585i | repeat-01 collected 26/26 workers (60602 items) tests 27505 done 2 failed | 25 in flight, oldest 193s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................................................... [1203%]
........................................................................ [1206%]
........................................................................ [1209%]
........................................................................ [1212%]
....[contention-diag] +2973s soak 39p/174t rss 13.1G pss 12.1G swap 0.7G majflt 5840 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 11 descendant rss 0.2G pss 0.1G | host avail 32.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.2 cpu 27.74 | cgroup 13.6G/max oom_kill 0 | free scratch 330.4G/45599284i tmp 29.7G/1019833i workspace 330.4G/45599284i | repeat-01 collected 26/26 workers (60602 items) tests 27794 done 2 failed | 24 in flight, oldest 209s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.....................F[contention-failure] call tests/ace/tui/widgets/test_auto_macro_completion.py::test_vcs_tag_project_namespace_opens_project_macro_menu: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw7/test_vcs_tag_project_namespace0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f468b1d6720>

    async def test_vcs_tag_project_namespace_opens_project_macro_menu(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Reported regression: ``#git:proj #proj/`` must offer project macros.
    
        The VCS tag names the project the user-facing way while the catalog knows
        it by its ProjectSpec directory key, so the menu stayed empty until both
        spellings were normalized to the canonical namespace.
        """
        app = CatalogCompletionTestApp()
        with registered_project_macros(
            tmp_path,
            monkeypatch,
            project_key="gh_org__proj",
            project_name="proj",
            macros={"reads": "Reads body", "sync": "Sync body"},
        ):
            async with app.run_test() as pilot:
                ta = app.query_one(PromptTextArea)
                ta.load_text("#git:proj #proj")
                ta.cursor_location = (0, len("#git:proj #proj"))
    
                await pilot.press("/")
    
                menu_text = ta.text
                menu_candidates = [c.insertion for c in ta._file_completion_candidates]
                menu_active = ta._file_completion_active
                menu_kind = ta._completion_kind
    
                # The directory-key spelling is not a real reference, so it must
                # not be offered either.
                ta.load_text("#git:proj #gh_org__proj")
                ta.cursor_location = (0, len("#git:proj #gh_org__proj"))
    
                await pilot.press("/")
    
                key_candidates = [c.insertion for c in ta._file_completion_candidates]
    
        assert menu_text == "#git:proj #proj/"
        assert menu_active is True
        assert menu_kind == "macro"
        assert menu_candidates == ["#proj/reads", "#proj/sync"]
        assert key_candidates == []
>       assert app.requested_projects == ["proj"] * len(app.requested_projects)
E       AssertionError: assert [None, 'proj'..., 'proj', ...] == ['proj', 'pro..., 'proj', ...]
E         
E         At index 0 diff: None != 'proj'
E         Use -v to get more diff

tests/ace/tui/widgets/test_auto_macro_completion.py:442: AssertionError
.............................................. [1215%]
........................................................................ [1218%]
........................................................................ [1221%]
........................................................................ [1225%]
..........[contention-diag] +2988s soak 32p/173t rss 13.0G pss 12.1G swap 0.7G majflt 5840 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 4 descendant rss 0.2G pss 0.1G | host avail 33.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 0.34 cpu 24.69 | cgroup 13.6G/max oom_kill 0 | free scratch 330.4G/45598214i tmp 29.7G/1019831i workspace 330.4G/45598214i | repeat-01 collected 26/26 workers (60602 items) tests 28081 done 3 failed | 25 in flight, oldest 224s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.............................................................. [1228%]
........................................................................ [1231%]
.................................................................[contention-diag] +3004s soak 34p/179t rss 13.0G pss 12.0G swap 0.7G majflt 5840 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.04 cpu 28.52 | cgroup 13.5G/max oom_kill 0 | free scratch 330.3G/45597655i tmp 29.7G/1019833i workspace 330.3G/45597655i | repeat-01 collected 26/26 workers (60602 items) tests 28287 done 3 failed | 25 in flight, oldest 239s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....... [1234%]
........................................................................ [1237%]
........................................................................ [1240%]
........................................................................ [1243%]
.................................................................[contention-diag] +3019s soak 37p/174t rss 13.1G pss 12.1G swap 0.6G majflt 5840 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 9 descendant rss 0.2G pss 0.1G | host avail 32.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 26.13 | cgroup 13.6G/max oom_kill 0 | free scratch 330.3G/45597124i tmp 29.7G/1019833i workspace 330.3G/45597124i | repeat-01 collected 26/26 workers (60602 items) tests 28577 done 3 failed | 25 in flight, oldest 193s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....... [1247%]
........................................................................ [1250%]
........................................................................ [1253%]
........................................................................ [1256%]
........................................................................ [1259%]
.............................................[contention-diag] +3034s soak 38p/174t rss 13.0G pss 12.1G swap 0.6G majflt 5843 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 10 descendant rss 0.1G pss 0.1G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 1.67 cpu 28.7 | cgroup 13.5G/max oom_kill 0 | free scratch 330.3G/45595078i tmp 29.7G/1019833i workspace 330.3G/45595078i | repeat-01 collected 26/26 workers (60602 items) tests 28887 done 3 failed | 24 in flight, oldest 209s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................... [1262%]
........................................................................ [1265%]
........................................................................ [1269%]
........................................................................ [1272%]
......[contention-diag] +3050s soak 38p/180t rss 13.1G pss 12.1G swap 0.7G majflt 5843 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 10 descendant rss 0.1G pss 0.1G | host avail 34.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 1.3 cpu 32.27 | cgroup 13.5G/max oom_kill 0 | free scratch 330.3G/45595124i tmp 29.7G/1019833i workspace 330.3G/45595124i | repeat-01 collected 26/26 workers (60602 items) tests 29161 done 3 failed | 25 in flight, oldest 224s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................................................................. [1275%]
........................................................................ [1278%]
..................................[contention-diag] +3065s soak 36p/174t rss 13.2G pss 12.2G swap 0.6G majflt 5843 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 8 descendant rss 0.2G pss 0.2G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.77 cpu 31.45 | cgroup 13.6G/max oom_kill 0 | free scratch 330.3G/45594560i tmp 29.7G/1019833i workspace 330.3G/45594560i | scratch used 0.5G in 92748 entries | repeat-01 collected 26/26 workers (60602 items) tests 29324 done 3 failed | 25 in flight, oldest 239s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................................... [1281%]
........................................................................ [1284%]
........................................................................ [1287%]
........................................................................ [1291%]
.............................[contention-diag] +3081s soak 35p/161t rss 13.1G pss 12.2G swap 0.7G majflt 5844 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 7 descendant rss 0.2G pss 0.1G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 2.79/1.59 io 2.7 cpu 27.18 | cgroup 13.3G/max oom_kill 0 | free scratch 330.3G/45594199i tmp 29.7G/1019833i workspace 330.3G/45594199i | repeat-01 collected 26/26 workers (60602 items) tests 29607 done 3 failed | 25 in flight, oldest 256s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................... [1294%]
........................................................................ [1297%]
........................................................................ [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
........................................................................ [1309%]
.....................................[contention-diag] +3096s soak 34p/166t rss 13.1G pss 12.1G swap 0.6G majflt 5874 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.6/0.36 io 2.71 cpu 30.0 | cgroup 13.3G/max oom_kill 0 | free scratch 330.3G/45593022i tmp 29.7G/1019833i workspace 330.3G/45593022i | repeat-01 collected 26/26 workers (60602 items) tests 30043 done 3 failed | 24 in flight, oldest 271s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................... [1313%]
........................................................................ [1316%]
........................................................................ [1319%]
........................................................................ [1322%]
........................................................................ [1325%]
........................................................................ [1328%]
.................[contention-diag] +3112s soak 35p/162t rss 13.1G pss 12.1G swap 0.6G majflt 5881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 7 descendant rss 0.1G pss 0.1G | host avail 33.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.12/0.07 io 2.39 cpu 29.06 | cgroup 13.3G/max oom_kill 0 | free scratch 330.3G/45591658i tmp 29.7G/1019833i workspace 330.3G/45591658i | repeat-01 collected 26/26 workers (60602 items) tests 30472 done 3 failed | 25 in flight, oldest 286s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....................................................... [1331%]
........................................................................ [1335%]
........................................................................ [1338%]
........................................................................ [1341%]
......................................[contention-diag] +3127s soak 32p/163t rss 13.1G pss 12.2G swap 0.6G majflt 5882 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.11/0.09 io 0.97 cpu 26.91 | cgroup 13.4G/max oom_kill 0 | free scratch 330.3G/45590440i tmp 29.7G/1019833i workspace 330.3G/45590440i | repeat-01 collected 26/26 workers (60602 items) tests 30754 done 3 failed | 25 in flight, oldest 301s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................................. [1344%]
........................................................................ [1347%]
........................................................................ [1350%]
........................................................................ [1353%]
........................................................................ [1357%]
................[contention-diag] +3142s soak 35p/166t rss 13.2G pss 12.2G swap 0.6G majflt 5888 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 7 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 1.7 cpu 27.97 | cgroup 13.5G/max oom_kill 0 | free scratch 330.3G/45589208i tmp 29.7G/1019833i workspace 330.3G/45589208i | repeat-01 collected 26/26 workers (60602 items) tests 31111 done 3 failed | 25 in flight, oldest 317s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................ [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
........................................................................ [1369%]
..........................................[contention-diag] +3158s soak 37p/176t rss 13.2G pss 12.2G swap 0.6G majflt 5892 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.1G pss 0.1G | host avail 33.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.98 cpu 24.35 | cgroup 13.4G/max oom_kill 0 | free scratch 330.3G/45587612i tmp 29.7G/1019833i workspace 330.3G/45587612i | repeat-01 collected 26/26 workers (60602 items) tests 31411 done 3 failed | 25 in flight, oldest 314s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.............................. [1372%]
........................................................................ [1375%]
........................................................................ [1379%]
........................................................................ [1382%]
........................................................................ [1385%]
......................................................[contention-diag] +3173s soak 36p/172t rss 13.2G pss 12.2G swap 0.6G majflt 5893 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 8 descendant rss 0.2G pss 0.2G | host avail 34.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.23 cpu 30.92 | cgroup 13.5G/max oom_kill 0 | free scratch 330.3G/45587043i tmp 29.7G/1019833i workspace 330.3G/45587043i | repeat-01 collected 26/26 workers (60602 items) tests 31789 done 3 failed | 25 in flight, oldest 329s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.................. [1388%]
........................................................................ [1391%]
........................................................................ [1394%]
........................................................................ [1397%]
........................................................................ [1401%]
............[contention-diag] +3188s soak 36p/173t rss 13.3G pss 12.2G swap 0.6G majflt 5893 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 8 descendant rss 0.2G pss 0.2G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.29 cpu 32.16 | cgroup 13.5G/max oom_kill 0 | free scratch 330.3G/45586402i tmp 29.7G/1019833i workspace 330.3G/45586402i | scratch used 0.5G in 100947 entries | repeat-01 collected 26/26 workers (60602 items) tests 32091 done 3 failed | 25 in flight, oldest 344s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................................................ [1404%]
........................................................................ [1407%]
........................................................................ [1410%]
.....................................................................[contention-diag] +3205s soak 34p/197t rss 13.4G pss 12.3G swap 0.7G majflt 5896 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 6 descendant rss 0.3G pss 0.2G | host avail 33.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.32 cpu 31.55 | cgroup 13.6G/max oom_kill 0 | free scratch 330.3G/45585676i tmp 29.7G/1019833i workspace 330.3G/45585676i | repeat-01 collected 26/26 workers (60602 items) tests 32385 done 3 failed | 25 in flight, oldest 361s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
... [1413%]
........................................................................ [1416%]
........................................................................ [1419%]
........................................................................ [1423%]
........................................................................ [1426%]
.........................................[contention-diag] +3220s soak 40p/184t rss 13.4G pss 12.4G swap 0.7G majflt 5903 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 12 descendant rss 0.4G pss 0.3G | host avail 32.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 27.32 | cgroup 13.9G/max oom_kill 0 | free scratch 330.3G/45584966i tmp 29.7G/1019833i workspace 330.3G/45584966i | repeat-01 collected 26/26 workers (60602 items) tests 32721 done 3 failed | 25 in flight, oldest 376s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................... [1429%]
........................................................................ [1432%]
........................................................................ [1435%]
........................................................................ [1438%]
........................................................................ [1441%]
............................................[contention-diag] +3236s soak 41p/196t rss 13.5G pss 12.4G swap 0.7G majflt 5904 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 13 descendant rss 0.4G pss 0.3G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.84 cpu 29.65 | cgroup 13.8G/max oom_kill 0 | free scratch 330.3G/45583373i tmp 29.7G/1019833i workspace 330.3G/45583373i | repeat-01 collected 26/26 workers (60602 items) tests 33084 done 3 failed | 25 in flight, oldest 392s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................ [1445%]
........................................................................ [1448%]
........................................................................ [1451%]
........................................................................ [1454%]
........................................................................ [1457%]
........................................................................ [1460%]
........................................................................ [1463%]
........................................................................ [1467%]
.................[contention-diag] +3251s soak 35p/189t rss 13.3G pss 12.3G swap 0.6G majflt 5912 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 7 descendant rss 0.2G pss 0.2G | host avail 33.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.25 cpu 26.93 | cgroup 13.7G/max oom_kill 0 | free scratch 330.3G/45581899i tmp 29.7G/1019833i workspace 330.3G/45581899i | repeat-01 collected 26/26 workers (60602 items) tests 33631 done 3 failed | 25 in flight, oldest 407s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
....................................................... [1470%]
........................................................................ [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1482%]
........................................................................ [1485%]
........................................................................ [1489%]
.......................................[contention-diag] +3266s soak 37p/182t rss 13.2G pss 12.2G swap 0.6G majflt 5997 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 9 descendant rss 0.1G pss 0.1G | host avail 33.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 21.03 | cgroup 13.8G/max oom_kill 0 | free scratch 330.3G/45580327i tmp 29.7G/1019833i workspace 330.3G/45580327i | repeat-01 collected 26/26 workers (60602 items) tests 34159 done 3 failed | 25 in flight, oldest 422s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
................................. [1492%]
........................................................................ [1495%]
........................................................................ [1498%]
..................................................[contention-diag] +3282s soak 38p/183t rss 13.4G pss 12.4G swap 0.7G majflt 5999 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 10 descendant rss 0.3G pss 0.2G | host avail 33.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.24 cpu 24.33 | cgroup 13.9G/max oom_kill 0 | free scratch 330.3G/45579467i tmp 29.7G/1019833i workspace 330.3G/45579467i | repeat-01 collected 26/26 workers (60602 items) tests 34378 done 3 failed | 25 in flight, oldest 369s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
...................... [1501%]
........................................................................ [1504%]
........................................................................ [1507%]
........................................................................ [1510%]
........................................................................ [1514%]
........................................................................ [1517%]
..........................[contention-diag] +3297s soak 34p/175t rss 13.3G pss 12.0G swap 0.6G majflt 6003 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 6 descendant rss 0.2G pss 0.1G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.07 cpu 29.56 | cgroup 13.7G/max oom_kill 0 | free scratch 330.3G/45578548i tmp 29.7G/1019833i workspace 330.3G/45578548i | repeat-01 collected 26/26 workers (60602 items) tests 34770 done 3 failed | 25 in flight, oldest 385s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
.............................................. [1520%]
........................................................................ [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1532%]
.............................................[contention-diag] +3312s soak 35p/182t rss 13.4G pss 12.3G swap 0.6G majflt 6008 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 7 descendant rss 0.2G pss 0.2G | host avail 36.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.22 cpu 33.37 | cgroup 13.8G/max oom_kill 0 | free scratch 330.2G/45576969i tmp 29.7G/1019833i workspace 330.2G/45576969i | scratch used 0.6G in 110397 entries | repeat-01 collected 26/26 workers (60602 items) tests 35151 done 3 failed | 25 in flight, oldest 400s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
........................... [1536%]
........................................................................ [1539%]
........................................[contention-diag] +3329s soak 35p/187t rss 13.4G pss 12.3G swap 0.7G majflt 6008 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 7 descendant rss 0.2G pss 0.2G | host avail 36.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 3.73 cpu 32.66 | cgroup 13.9G/max oom_kill 0 | free scratch 330.2G/45576448i tmp 29.7G/1019833i workspace 330.2G/45576448i | repeat-01 collected 26/26 workers (60602 items) tests 35314 done 3 failed | 24 in flight, oldest 416s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................................ [1542%]
........................................................................ [1545%]
........................................................................ [1548%]
........................................................................ [1551%]
........................................................................ [1554%]
...................[contention-diag] +3344s soak 33p/195t rss 13.3G pss 12.3G swap 0.6G majflt 6061 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 35.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.16 cpu 28.37 | cgroup 13.8G/max oom_kill 0 | free scratch 330.2G/45576081i tmp 29.7G/1019833i workspace 330.2G/45576081i | repeat-01 collected 26/26 workers (60602 items) tests 35652 done 3 failed | 25 in flight, oldest 161s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
..................................................... [1558%]
.s...................................................................... [1561%]
........................................................................ [1564%]
........................................................................ [1567%]
...............................................................[contention-diag] +3360s soak 34p/191t rss 13.5G pss 12.5G swap 0.6G majflt 6158 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 6 descendant rss 0.3G pss 0.3G | host avail 36.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.54 cpu 30.13 | cgroup 14.4G/max oom_kill 0 | free scratch 330.2G/45575961i tmp 29.7G/1019833i workspace 330.2G/45575961i | repeat-01 collected 26/26 workers (60602 items) tests 35976 done 3 failed | 24 in flight, oldest 176s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
......... [1570%]
........................................................................ [1573%]
........................................................................ [1576%]
........................................................................ [1580%]
.....................................................................[contention-diag] +3375s soak 37p/179t rss 13.4G pss 12.4G swap 0.6G majflt 6022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.2G pss 0.2G | host avail 35.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.46/0.46 io 2.62 cpu 28.09 | cgroup 14.5G/max oom_kill 0 | free scratch 329.9G/45574866i tmp 29.7G/1019834i workspace 329.9G/45574866i | repeat-01 collected 26/26 workers (60602 items) tests 36276 done 3 failed | 24 in flight, oldest 192s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
... [1583%]
........................................................................ [1586%]
........................................................................ [1589%]
[contention-diag] +3390s soak 37p/186t rss 13.5G pss 12.4G swap 0.6G majflt 6022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.3G pss 0.2G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 2.81 cpu 27.14 | cgroup 14.5G/max oom_kill 0 | free scratch 329.6G/45573948i tmp 29.7G/1019834i workspace 329.6G/45573948i | repeat-01 collected 26/26 workers (60602 items) tests 36426 done 3 failed | 24 in flight, oldest 207s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
........................................................................ [1592%]
........................................................................ [1595%]
........................................................................ [1598%]
........................................................................ [1602%]
....................[contention-diag] +3406s soak 35p/202t rss 13.4G pss 12.4G swap 0.6G majflt 6022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.2G pss 0.2G | host avail 34.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 4.02 cpu 26.53 | cgroup 13.9G/max oom_kill 0 | free scratch 330.2G/45573399i tmp 29.7G/1019834i workspace 330.2G/45573399i | repeat-01 collected 26/26 workers (60602 items) tests 36722 done 3 failed | 24 in flight, oldest 222s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
.................................................... [1605%]
........................................................................ [1608%]
........................................................................ [1611%]
........................................................................ [1614%]
........................................................[contention-diag] +3421s soak 36p/211t rss 13.5G pss 12.4G swap 0.6G majflt 6022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 8 descendant rss 0.3G pss 0.2G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.54 cpu 27.33 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45572126i tmp 29.7G/1019834i workspace 330.2G/45572126i | repeat-01 collected 26/26 workers (60602 items) tests 37062 done 3 failed | 24 in flight, oldest 238s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
................ [1617%]
........................................................................ [1620%]
........................................................................ [1624%]
........................................................................ [1627%]
........................................................................ [1630%]
..................................[contention-diag] +3436s soak 37p/192t rss 13.5G pss 12.5G swap 0.6G majflt 6024 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.3G pss 0.2G | host avail 34.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.57 cpu 28.29 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45571342i tmp 29.7G/1019834i workspace 330.2G/45571342i | scratch used 0.6G in 115980 entries | repeat-01 collected 26/26 workers (60602 items) tests 37357 done 3 failed | 24 in flight, oldest 253s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
...................................... [1633%]
........................................................................ [1636%]
........................................................................ [1639%]
....................[contention-diag] +3453s soak 39p/186t rss 13.5G pss 12.4G swap 0.6G majflt 6024 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 11 descendant rss 0.2G pss 0.2G | host avail 34.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.55 cpu 31.94 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45570447i tmp 29.7G/1019834i workspace 330.2G/45570447i | repeat-01 collected 26/26 workers (60602 items) tests 37601 done 3 failed | 24 in flight, oldest 270s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
.................................................... [1642%]
........................................................................ [1646%]
........................................................................ [1649%]
............................[contention-diag] +3468s soak 34p/189t rss 13.5G pss 12.4G swap 0.6G majflt 6026 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 6 descendant rss 0.2G pss 0.1G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.24 cpu 30.21 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45570292i tmp 29.7G/1019834i workspace 330.2G/45570292i | repeat-01 collected 26/26 workers (60602 items) tests 37823 done 3 failed | 24 in flight, oldest 285s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
............................................ [1652%]
........................................................................ [1655%]
........................................................................ [1658%]
........................................................................ [1661%]
........................................................................ [1664%]
..................................................................[contention-diag] +3483s soak 35p/188t rss 13.5G pss 12.4G swap 0.6G majflt 6031 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.2G pss 0.1G | host avail 33.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.82 cpu 29.18 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45569415i tmp 29.7G/1019834i workspace 330.2G/45569415i | repeat-01 collected 26/26 workers (60602 items) tests 38207 done 3 failed | 24 in flight, oldest 300s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 8 hazardous kill call(s)
.....s [1668%]
........................................................................ [1671%]
........................................................................ [1674%]
........................................................................ [1677%]
........................................................................ [1680%]
........................................................................ [1683%]
...........[contention-diag] +3499s soak 35p/185t rss 13.4G pss 12.4G swap 0.6G majflt 6032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.1G pss 0.1G | host avail 34.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.97 cpu 30.46 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45567767i tmp 29.7G/1019834i workspace 330.2G/45567767i | repeat-01 collected 26/26 workers (60602 items) tests 38599 done 3 failed | 23 in flight, oldest 316s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 8 hazardous kill call(s)
............................................................. [1686%]
........................................................................ [1690%]
........................................................................ [1693%]
........................................................................ [1696%]
...............................................................[contention-diag] +3514s soak 35p/175t rss 13.5G pss 12.4G swap 0.6G majflt 6057 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.2G pss 0.2G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.4 cpu 30.2 | cgroup 14.1G/max oom_kill 0 | free scratch 330.2G/45567133i tmp 29.7G/1019834i workspace 330.2G/45567133i | repeat-01 collected 26/26 workers (60602 items) tests 38914 done 3 failed | 23 in flight, oldest 306s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
......... [1699%]
........................................................................ [1702%]
........................................................................ [1705%]
........................................................................ [1708%]
.................................................................[contention-diag] +3529s soak 31p/180t rss 13.4G pss 12.3G swap 0.6G majflt 6068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.1G pss 0.1G | host avail 35.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 4.37 cpu 27.59 | cgroup 14.0G/max oom_kill 0 | free scratch 330.2G/45565966i tmp 29.7G/1019834i workspace 330.2G/45565966i | repeat-01 collected 26/26 workers (60602 items) tests 39212 done 3 failed | 24 in flight, oldest 256s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....... [1712%]
........................................................................ [1715%]
........................................................................ [1718%]
........................................................................ [1721%]
........................................................................ [1724%]
............................[contention-diag] +3545s soak 36p/192t rss 13.6G pss 12.5G swap 0.6G majflt 6068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 8 descendant rss 0.3G pss 0.2G | host avail 34.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 6.53 cpu 27.96 | cgroup 14.1G/max oom_kill 0 | free scratch 330.2G/45565082i tmp 29.7G/1019834i workspace 330.2G/45565082i | repeat-01 collected 26/26 workers (60602 items) tests 39551 done 3 failed | 24 in flight, oldest 271s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................ [1727%]
........................................................................ [1730%]
........................................................................ [1734%]
...................................................[contention-diag] +3560s soak 41p/197t rss 13.7G pss 12.6G swap 0.6G majflt 6068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 13 descendant rss 0.4G pss 0.3G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 5.19 cpu 29.3 | cgroup 14.3G/max oom_kill 0 | free scratch 330.2G/45564140i tmp 29.7G/1019834i workspace 330.2G/45564140i | scratch used 0.7G in 123117 entries | repeat-01 collected 26/26 workers (60602 items) tests 39779 done 3 failed | 24 in flight, oldest 286s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..................... [1737%]
........................................................................ [1740%]
........................................................................ [1743%]
........................................................................ [1746%]
........................................................................ [1749%]
.......................[contention-diag] +3576s soak 41p/189t rss 13.6G pss 12.5G swap 0.6G majflt 6068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 13 descendant rss 0.3G pss 0.2G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 4.02 cpu 27.52 | cgroup 14.2G/max oom_kill 0 | free scratch 330.2G/45562868i tmp 29.7G/1019834i workspace 330.2G/45562868i | repeat-01 collected 26/26 workers (60602 items) tests 40127 done 3 failed | 23 in flight, oldest 303s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................. [1752%]
........................................................................ [1756%]
........................................................................ [1759%]
........................................................................ [1762%]
........................................................................ [1765%]
........................................................................ [1768%]
........................................................................ [1771%]
.............[contention-diag] +3592s soak 33p/181t rss 13.7G pss 12.6G swap 0.6G majflt 6119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 5 descendant rss 0.3G pss 0.3G | host avail 34.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 6.02 cpu 29.57 | cgroup 14.3G/max oom_kill 0 | free scratch 330.2G/45561694i tmp 29.7G/1019834i workspace 330.2G/45561694i | repeat-01 collected 26/26 workers (60602 items) tests 40619 done 3 failed | 24 in flight, oldest 318s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........................................................... [1774%]
........................................................................ [1778%]
........................................................................ [1781%]
........................................................................ [1784%]
........................................................................ [1787%]
........................................................................ [1790%]
..........................................................[contention-diag] +3607s soak 35p/190t rss 13.6G pss 12.5G swap 0.6G majflt 6121 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 7 descendant rss 0.3G pss 0.2G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.88 cpu 28.51 | cgroup 14.3G/max oom_kill 0 | free scratch 330.1G/45560060i tmp 29.7G/1019834i workspace 330.1G/45560060i | repeat-01 collected 26/26 workers (60602 items) tests 41093 done 3 failed | 24 in flight, oldest 333s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............. [1793%]
........................................................................ [1796%]
........................................................................ [1800%]
.........................................................s.............. [1803%]
........................................................................ [1806%]
.....[contention-diag] +3622s soak 33p/199t rss 13.6G pss 12.5G swap 0.6G majflt 6120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 5 descendant rss 0.2G pss 0.2G | host avail 33.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 5.52 cpu 29.37 | cgroup 14.5G/max oom_kill 0 | free scratch 330.1G/45559420i tmp 29.7G/1019834i workspace 330.1G/45559420i | repeat-01 collected 26/26 workers (60602 items) tests 41398 done 3 failed | 23 in flight, oldest 349s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................................... [1809%]
........................................................................ [1812%]
................s....................................................... [1815%]
........................................................................ [1818%]
........................................................................ [1821%]
.................................[contention-diag] +3638s soak 33p/185t rss 13.6G pss 12.5G swap 0.6G majflt 6120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 5 descendant rss 0.2G pss 0.1G | host avail 33.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 6.12 cpu 28.5 | cgroup 14.4G/max oom_kill 0 | free scratch 330.1G/45558239i tmp 29.7G/1019834i workspace 330.1G/45558239i | repeat-01 collected 26/26 workers (60602 items) tests 41788 done 3 failed | 24 in flight, oldest 364s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....................................... [1825%]
........................................................................ [1828%]
........................................................................ [1831%]
........................................................................ [1834%]
........................................................................ [1837%]
........[contention-diag] +3653s soak 35p/191t rss 13.7G pss 12.3G swap 0.6G majflt 6120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 7 descendant rss 0.3G pss 0.2G | host avail 32.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.83 cpu 24.37 | cgroup 14.3G/max oom_kill 0 | free scratch 330.1G/45557038i tmp 29.7G/1019834i workspace 330.1G/45557038i | repeat-01 collected 26/26 workers (60602 items) tests 42120 done 3 failed | 23 in flight, oldest 379s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
................................................................ [1840%]
........................................................................ [1843%]
........................................................................ [1847%]
........................................................................ [1850%]
..............................................................[contention-diag] +3668s soak 38p/197t rss 13.7G pss 12.6G swap 0.6G majflt 6122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 10 descendant rss 0.3G pss 0.2G | host avail 33.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.93 cpu 27.56 | cgroup 14.5G/max oom_kill 0 | free scratch 330.1G/45556559i tmp 29.7G/1019834i workspace 330.1G/45556559i | repeat-01 collected 26/26 workers (60602 items) tests 42446 done 3 failed | 24 in flight, oldest 395s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
.......... [1853%]
........................................................................ [1856%]
........................................................................ [1859%]
........................................................................ [1862%]
........................................................................ [1865%]
...........................................................[contention-diag] +3684s soak 39p/186t rss 13.7G pss 12.6G swap 0.6G majflt 6122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 11 descendant rss 0.3G pss 0.2G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.65/0.65 io 7.37 cpu 26.31 | cgroup 14.4G/max oom_kill 0 | free scratch 330.1G/45555199i tmp 29.7G/1019832i workspace 330.1G/45555199i | scratch used 0.7G in 132050 entries | repeat-01 collected 26/26 workers (60602 items) tests 42774 done 3 failed | 24 in flight, oldest 410s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
............. [1869%]
........................................................................ [1872%]
........................................................................ [1875%]
........................................................................ [1878%]
..........................................[contention-diag] +3700s soak 35p/174t rss 13.8G pss 12.6G swap 0.6G majflt 6124 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 7 descendant rss 0.3G pss 0.3G | host avail 33.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 7.02 cpu 30.12 | cgroup 14.5G/max oom_kill 0 | free scratch 330.1G/45553907i tmp 29.7G/1019832i workspace 330.1G/45553907i | repeat-01 collected 26/26 workers (60602 items) tests 43094 done 3 failed | 24 in flight, oldest 238s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.............................. [1881%]
........................................................................ [1884%]
........................................................................ [1887%]
........................................................................ [1891%]
........................................................................ [1894%]
........................................................................ [1897%]
........................................................................ [1900%]
..................[contention-diag] +3716s soak 37p/183t rss 13.7G pss 12.6G swap 0.6G majflt 6126 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 9 descendant rss 0.2G pss 0.2G | host avail 34.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 7.52 cpu 31.33 | cgroup 14.4G/max oom_kill 0 | free scratch 330.1G/45552310i tmp 29.7G/1019832i workspace 330.1G/45552310i | repeat-01 collected 26/26 workers (60602 items) tests 43562 done 3 failed | 23 in flight, oldest 253s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................................... [1903%]
........................................................................ [1906%]
........................................................................ [1909%]
........................................................................ [1913%]
........................................................................ [1916%]
................................................................[contention-diag] +3731s soak 39p/194t rss 13.9G pss 12.8G swap 0.6G majflt 6134 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.1G, 11 descendant rss 0.4G pss 0.4G | host avail 33.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.38 cpu 31.4 | cgroup 14.7G/max oom_kill 0 | free scratch 330.1G/45551169i tmp 29.7G/1019832i workspace 330.1G/45551169i | repeat-01 collected 26/26 workers (60602 items) tests 43982 done 3 failed | 22 in flight, oldest 268s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........ [1919%]
........................................................................ [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
..............[contention-diag] +3746s soak 40p/190t rss 13.9G pss 12.8G swap 0.6G majflt 6136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.1G, 12 descendant rss 0.4G pss 0.4G | host avail 32.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.54 cpu 32.54 | cgroup 14.7G/max oom_kill 0 | free scratch 330.1G/45549902i tmp 29.7G/1019833i workspace 330.1G/45549902i | repeat-01 collected 26/26 workers (60602 items) tests 44214 done 3 failed | 23 in flight, oldest 284s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................................... [1931%]
........................................................................ [1935%]
........................................................................ [1938%]
........................................................................ [1941%]
..........................................................[contention-diag] +3762s soak 39p/188t rss 14.0G pss 12.9G swap 0.6G majflt 6154 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.1G, 11 descendant rss 0.5G pss 0.5G | host avail 33.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.23/0.23 io 1.04 cpu 33.94 | cgroup 14.9G/max oom_kill 0 | free scratch 330.1G/45549784i tmp 29.7G/1019833i workspace 330.1G/45549784i | repeat-01 collected 26/26 workers (60602 items) tests 44550 done 3 failed | 23 in flight, oldest 299s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.............. [1944%]
........................................................................ [1947%]
........................................................................ [1950%]
........................................................................ [1953%]
........................................................................ [1957%]
..[contention-diag] +3777s soak 41p/212t rss 14.1G pss 13.0G swap 0.6G majflt 6154 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.1G, 13 descendant rss 0.6G pss 0.5G | host avail 32.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.43 cpu 29.25 | cgroup 14.9G/max oom_kill 0 | free scratch 330.1G/45548575i tmp 29.7G/1019833i workspace 330.1G/45548575i | repeat-01 collected 26/26 workers (60602 items) tests 44841 done 3 failed | 23 in flight, oldest 314s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................................................... [1960%]
........................................................................ [1963%]
........................................................................ [1966%]
.............................................[contention-diag] +3792s soak 39p/212t rss 14.2G pss 13.1G swap 0.6G majflt 6156 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.1G, 11 descendant rss 0.7G pss 0.6G | host avail 32.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.57 cpu 27.99 | cgroup 14.9G/max oom_kill 0 | free scratch 330.1G/45546821i tmp 29.7G/1019833i workspace 330.1G/45546821i | repeat-01 collected 26/26 workers (60602 items) tests 45097 done 3 failed | 23 in flight, oldest 330s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................... [1969%]
........................................................................ [1972%]
........................................................................ [1975%]
..............[contention-diag] +3808s soak 46p/205t rss 14.3G pss 13.2G swap 0.6G majflt 6156 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.1G, 18 descendant rss 0.8G pss 0.7G | host avail 31.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.78 cpu 33.91 | cgroup 15.1G/max oom_kill 0 | free scratch 330.1G/45546707i tmp 29.7G/1019833i workspace 330.1G/45546707i | scratch used 0.7G in 140612 entries | repeat-01 collected 26/26 workers (60602 items) tests 45258 done 3 failed | 23 in flight, oldest 345s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................................... [1979%]
........................................................................ [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
........................................................................ [1991%]
....[contention-diag] +3825s soak 36p/185t rss 14.3G pss 13.1G swap 0.6G majflt 6157 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 0.7G pss 0.6G | host avail 32.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.56 cpu 32.32 | cgroup 15.0G/max oom_kill 0 | free scratch 330.1G/45547417i tmp 29.7G/1019833i workspace 330.1G/45547417i | repeat-01 collected 26/26 workers (60602 items) tests 45642 done 3 failed | 22 in flight, oldest 362s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................................................... [1994%]
........................................................................ [1997%]
........................................................................ [2001%]
........................................................................ [2004%]
........................................................................ [2007%]
........................................................................ [2010%]
.........[contention-diag] +3840s soak 35p/179t rss 14.2G pss 13.1G swap 0.6G majflt 6157 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 7 descendant rss 0.7G pss 0.6G | host avail 32.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.63 cpu 38.02 | cgroup 15.0G/max oom_kill 0 | free scratch 330.1G/45546085i tmp 29.7G/1019833i workspace 330.1G/45546085i | repeat-01 collected 26/26 workers (60602 items) tests 46080 done 3 failed | 21 in flight, oldest 377s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................................... [2013%]
........................................................................ [2016%]
........................................................................ [2019%]
........................................................................ [2023%]
........................................................................ [2026%]
...............................................................[contention-diag] +3856s soak 35p/183t rss 14.1G pss 13.0G swap 0.6G majflt 6157 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.6G pss 0.5G | host avail 32.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.63 cpu 38.25 | cgroup 14.9G/max oom_kill 0 | free scratch 330.1G/45546084i tmp 29.7G/1019833i workspace 330.1G/45546084i | repeat-01 collected 26/26 workers (60602 items) tests 46490 done 3 failed | 20 in flight, oldest 393s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......... [2029%]
........................................................................ [2032%]
........................................................................ [2035%]
........................................................................ [2038%]
............................................................[contention-diag] +3871s soak 38p/183t rss 14.3G pss 13.1G swap 0.6G majflt 6158 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 0.7G pss 0.6G | host avail 31.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.03 cpu 37.87 | cgroup 15.1G/max oom_kill 0 | free scratch 330.1G/45546457i tmp 29.7G/1019833i workspace 330.1G/45546457i | repeat-01 collected 26/26 workers (60602 items) tests 46770 done 3 failed | 18 in flight, oldest 408s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
........................................................................ [2054%]
........................................................................ [2057%]
........................................................................ [2060%]
........................................................................ [2063%]
.....[contention-diag] +3886s soak 39p/176t rss 14.4G pss 13.2G swap 0.6G majflt 6158 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 0.8G pss 0.7G | host avail 30.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.94 cpu 31.3 | cgroup 15.2G/max oom_kill 0 | free scratch 330.1G/45544777i tmp 29.7G/1019833i workspace 330.1G/45544777i | repeat-01 collected 26/26 workers (60602 items) tests 47289 done 3 failed | 19 in flight, oldest 240s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................... [2067%]
........................................................................ [2070%]
........................................................................ [2073%]
........................................................................ [2076%]
........................................................................ [2079%]
..................................[contention-diag] +3902s soak 38p/180t rss 14.5G pss 13.3G swap 0.6G majflt 6159 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 0.9G pss 0.8G | host avail 30.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.86 cpu 30.42 | cgroup 15.3G/max oom_kill 0 | free scratch 330.1G/45543665i tmp 29.7G/1019833i workspace 330.1G/45543665i | repeat-01 collected 26/26 workers (60602 items) tests 47697 done 3 failed | 19 in flight, oldest 256s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................... [2082%]
........................................................................ [2085%]
........................................................................ [2089%]
........................................................................ [2092%]
.....................[contention-diag] +3917s soak 36p/184t rss 14.3G pss 13.2G swap 0.6G majflt 6160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 0.7G pss 0.7G | host avail 32.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.39 cpu 30.55 | cgroup 15.2G/max oom_kill 0 | free scratch 330.1G/45542665i tmp 29.7G/1019833i workspace 330.1G/45542665i | repeat-01 collected 26/26 workers (60602 items) tests 47972 done 3 failed | 19 in flight, oldest 271s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................................... [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
........................................................................ [2104%]
........................................................................ [2107%]
........................................................................ [2110%]
...........................[contention-diag] +3932s soak 38p/177t rss 14.4G pss 13.2G swap 0.6G majflt 6160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 0.8G pss 0.7G | host avail 32.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.3 cpu 35.87 | cgroup 15.2G/max oom_kill 0 | free scratch 330.1G/45541987i tmp 29.7G/1019833i workspace 330.1G/45541987i | scratch used 0.8G in 145277 entries | repeat-01 collected 26/26 workers (60602 items) tests 48317 done 3 failed | 19 in flight, oldest 286s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................................. [2114%]
........................................................................ [2117%]
........................................................................ [2120%]
........................................................................ [2123%]
........................................................................ [2126%]
...........................................[contention-diag] +3949s soak 37p/173t rss 14.4G pss 13.3G swap 0.6G majflt 6160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.8G pss 0.8G | host avail 34.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 32.18 | cgroup 15.3G/max oom_kill 0 | free scratch 330.1G/45540944i tmp 29.7G/1019833i workspace 330.1G/45540944i | repeat-01 collected 26/26 workers (60602 items) tests 48743 done 3 failed | 19 in flight, oldest 303s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................. [2129%]
........................................................................ [2132%]
........................................................................ [2136%]
........................................................................ [2139%]
........................................................................ [2142%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
.............................................[contention-diag] +3964s soak 37p/187t rss 14.6G pss 13.4G swap 0.6G majflt 6160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.9G pss 0.9G | host avail 34.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 37.37 | cgroup 15.4G/max oom_kill 0 | free scratch 330.1G/45540302i tmp 29.7G/1019833i workspace 330.1G/45540302i | repeat-01 collected 26/26 workers (60602 items) tests 49341 done 3 failed | 18 in flight, oldest 318s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................... [2154%]
........................................................................ [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
..............................s......................................... [2167%]
........................................................................ [2170%]
........................................................................ [2173%]
........................................................................ [2176%]
......................................................................[contention-diag] +3980s soak 39p/183t rss 14.7G pss 13.5G swap 0.6G majflt 6201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.1G pss 1.0G | host avail 34.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 37.35 | cgroup 15.6G/max oom_kill 0 | free scratch 330.0G/45537979i tmp 29.7G/1019833i workspace 330.0G/45537979i | repeat-01 collected 26/26 workers (60602 items) tests 49946 done 3 failed | 18 in flight, oldest 334s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.. [2180%]
........................................................................ [2183%]
........................................................................ [2186%]
........................................................................ [2189%]
........................................................................ [2192%]
........................................................................ [2195%]
.......................................................[contention-diag] +3995s soak 37p/180t rss 14.7G pss 13.5G swap 0.7G majflt 6204 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 1.0G pss 1.0G | host avail 34.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 38.18 | cgroup 15.6G/max oom_kill 0 | free scratch 330.0G/45536486i tmp 29.7G/1019833i workspace 330.0G/45536486i | repeat-01 collected 26/26 workers (60602 items) tests 50354 done 3 failed | 18 in flight, oldest 349s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................. [2198%]
........................................................................ [2202%]
........................................................................ [2205%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2217%]
........................................................................ [2220%]
........................................................................ [2224%]
........................................................................ [2227%]
...........................................[contention-diag] +4010s soak 42p/183t rss 14.8G pss 13.6G swap 0.7G majflt 6163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.2G, 14 descendant rss 1.1G pss 1.0G | host avail 33.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.98 cpu 34.4 | cgroup 15.6G/max oom_kill 0 | free scratch 330.0G/45534826i tmp 29.7G/1019833i workspace 330.0G/45534826i | repeat-01 collected 26/26 workers (60602 items) tests 51068 done 3 failed | 17 in flight, oldest 364s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................. [2230%]
........................................................................ [2233%]
....................................................s................... [2236%]
........................................................................ [2239%]
........................................................................ [2242%]
........................................................................ [2246%]
........................................................................ [2249%]
........................................................................ [2252%]
........................................................................ [2255%]
.....................................................[contention-diag] +4026s soak 35p/178t rss 14.6G pss 13.4G swap 0.6G majflt 6163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.9G pss 0.9G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.57 cpu 31.99 | cgroup 15.7G/max oom_kill 0 | free scratch 330.0G/45532792i tmp 29.7G/1019833i workspace 330.0G/45532792i | repeat-01 collected 26/26 workers (60602 items) tests 51735 done 3 failed | 17 in flight, oldest 380s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................... [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
...............................................................[contention-diag] +4041s soak 40p/182t rss 14.8G pss 13.6G swap 0.6G majflt 6167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 12 descendant rss 1.2G pss 1.1G | host avail 32.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.82 cpu 30.56 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45531947i tmp 29.7G/1019833i workspace 330.0G/45531947i | repeat-01 collected 26/26 workers (60602 items) tests 52088 done 3 failed | 18 in flight, oldest 395s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
......... [2274%]
........................................................................ [2277%]
........................................................................ [2280%]
........................................................................ [2283%]
........................................................................ [2286%]
........................................................................ [2290%]
........................................................................ [2293%]
........................................................................ [2296%]
........................................................................ [2299%]
..............................[contention-diag] +4056s soak 37p/179t rss 14.7G pss 13.5G swap 0.6G majflt 6167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 1.0G pss 0.9G | host avail 33.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.52 cpu 29.52 | cgroup 15.8G/max oom_kill 0 | free scratch 330.0G/45530726i tmp 29.7G/1019833i workspace 330.0G/45530726i | scratch used 0.8G in 156691 entries | repeat-01 collected 26/26 workers (60602 items) tests 52628 done 3 failed | 18 in flight, oldest 411s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......................................... [2302%]
........................................................................ [2305%]
........................................................................ [2308%]
........................................................................ [2312%]
........................................................................ [2315%]
........................................................................ [2318%]
............................................[contention-diag] +4073s soak 41p/186t rss 14.7G pss 13.5G swap 0.6G majflt 6167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 13 descendant rss 1.1G pss 1.0G | host avail 32.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 32.65 | cgroup 15.8G/max oom_kill 0 | free scratch 330.0G/45529238i tmp 29.7G/1019833i workspace 330.0G/45529238i | repeat-01 collected 26/26 workers (60602 items) tests 53172 done 3 failed | 18 in flight, oldest 427s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2330%]
........................................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2340%]
........................................................................ [2343%]
........................................................................ [2346%]
....................................................................[contention-diag] +4089s soak 37p/175t rss 14.7G pss 13.5G swap 0.6G majflt 6167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 1.0G pss 0.9G | host avail 33.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.48 cpu 33.83 | cgroup 15.8G/max oom_kill 0 | free scratch 330.0G/45528375i tmp 29.7G/1019833i workspace 330.0G/45528375i | repeat-01 collected 26/26 workers (60602 items) tests 53831 done 3 failed | 17 in flight, oldest 443s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.... [2349%]
........................................................................ [2352%]
........................................................................ [2356%]
........................................................................ [2359%]
........................................................................ [2362%]
........................................................................ [2365%]
........................................................................ [2368%]
........................................................................ [2371%]
........................................................................ [2374%]
........................................................................ [2378%]
.......................................[contention-diag] +4104s soak 38p/178t rss 14.8G pss 13.5G swap 0.6G majflt 6170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 1.1G pss 1.0G | host avail 32.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 40.97 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45526766i tmp 29.7G/1019833i workspace 330.0G/45526766i | repeat-01 collected 26/26 workers (60602 items) tests 54522 done 3 failed | 15 in flight, oldest 458s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................. [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
........................................................................ [2390%]
........................................................................ [2393%]
.................................[contention-diag] +4119s soak 41p/178t rss 14.7G pss 13.5G swap 0.6G majflt 6170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 13 descendant rss 1.1G pss 1.0G | host avail 32.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.1 cpu 39.61 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45526615i tmp 29.7G/1019833i workspace 330.0G/45526615i | repeat-01 collected 26/26 workers (60602 items) tests 54891 done 3 failed | 15 in flight, oldest 473s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
....................................... [2396%]
........................................................................ [2400%]
........................................................................ [2403%]
...................................................................[contention-diag] +4135s soak 36p/161t rss 14.7G pss 13.5G swap 0.6G majflt 6170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 1.0G pss 1.0G | host avail 32.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.78 cpu 37.86 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45526662i tmp 29.7G/1019833i workspace 330.0G/45526662i | repeat-01 collected 26/26 workers (60602 items) tests 55138 done 3 failed | 14 in flight, oldest 489s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
..... [2406%]
........................................................................ [2409%]
........................................................................ [2412%]
........................................................................ [2415%]
........................................................................ [2418%]
........................................................................ [2421%]
..................................................................[contention-diag] +4150s soak 38p/170t rss 14.7G pss 13.5G swap 0.6G majflt 6170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 1.0G pss 1.0G | host avail 31.8G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 29.77 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45525649i tmp 29.7G/1019833i workspace 330.0G/45525649i | repeat-01 collected 26/26 workers (60602 items) tests 55560 done 3 failed | 12 in flight, oldest 504s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
...... [2425%]
........................................................................ [2428%]
..............................................................s......... [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
........................................................................ [2440%]
.........................................................[contention-diag] +4166s soak 35p/162t rss 14.7G pss 13.5G swap 0.6G majflt 6170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 1.0G pss 1.0G | host avail 32.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.29 cpu 34.59 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45525282i tmp 29.7G/1019833i workspace 330.0G/45525282i | repeat-01 collected 26/26 workers (60602 items) tests 55986 done 3 failed | 13 in flight, oldest 520s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............... [2443%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2453%]
........................................................................ [2456%]
........................................................................ [2459%]
........................................................................ [2462%]
.................................................................[contention-diag] +4181s soak 34p/161t rss 13.9G pss 12.7G swap 0.6G majflt 6171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 0.2G pss 0.2G | host avail 31.5G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 28.12 | cgroup 15.1G/max oom_kill 0 | free scratch 330.0G/45525203i tmp 29.7G/1019833i workspace 330.0G/45525203i | scratch used 0.8G in 162081 entries | repeat-01 collected 26/26 workers (60602 items) tests 56459 done 3 failed | 10 in flight, oldest 67s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
....... [2465%]
........................................................................ [2469%]
........................................................................ [2472%]
........................................................................ [2475%]
........................................................................ [2478%]
........................................................................ [2481%]
............................................[contention-diag] +4198s soak 35p/159t rss 13.9G pss 12.7G swap 0.6G majflt 6172 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.2G pss 0.2G | host avail 33.0G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.36 cpu 32.3 | cgroup 15.1G/max oom_kill 0 | free scratch 330.0G/45524660i tmp 29.7G/1019833i workspace 330.0G/45524660i | repeat-01 collected 26/26 workers (60602 items) tests 56912 done 3 failed | 9 in flight, oldest 84s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................ [2484%]
........................................................................ [2487%]
........................................................................ [2491%]
........................................................................ [2494%]
...............s........................................................ [2497%]
........................................................................ [2500%]
.....................................................................[contention-diag] +4213s soak 33p/162t rss 13.8G pss 12.6G swap 0.6G majflt 6172 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 5 descendant rss 0.1G pss 0.0G | host avail 32.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 33.68 | cgroup 15.0G/max oom_kill 0 | free scratch 330.0G/45523345i tmp 29.7G/1019833i workspace 330.0G/45523345i | repeat-01 collected 26/26 workers (60602 items) tests 57366 done 3 failed | 10 in flight, oldest 100s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
... [2503%]
........................................................................ [2506%]
........................................................................ [2509%]
........................................................................ [2513%]
........................................................................ [2516%]
........................................................................ [2519%]
........................................................................ [2522%]
........................................................................ [2525%]
........................................................................ [2528%]
.......................[contention-diag] +4228s soak 34p/160t rss 13.7G pss 12.6G swap 0.6G majflt 6175 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 0.0G pss 0.0G | host avail 33.3G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.81 cpu 36.48 | cgroup 15.0G/max oom_kill 0 | free scratch 330.0G/45522187i tmp 29.7G/1019833i workspace 330.0G/45522187i | repeat-01 collected 26/26 workers (60602 items) tests 57977 done 3 failed | 9 in flight, oldest 11s gw9 tests/test_provider_usage_indicator_widget.py::test_click_opens_provider_usage_when_groups_exist | 10 hazardous kill call(s)
................................................. [2531%]
........................................................................ [2535%]
........................................................................ [2538%]
........................................................................ [2541%]
........................................................................ [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
........................................................................ [2553%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2563%]
..............................................[contention-diag] +4244s soak 35p/164t rss 13.9G pss 12.7G swap 0.6G majflt 6176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 7 descendant rss 0.2G pss 0.1G | host avail 33.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 40.22 | cgroup 15.2G/max oom_kill 0 | free scratch 329.9G/45519178i tmp 29.7G/1019833i workspace 329.9G/45519178i | repeat-01 collected 26/26 workers (60602 items) tests 58792 done 3 failed | 9 in flight, oldest 13s gw9 tests/test_provider_usage_indicator_widget.py::test_theme_switch_repaints_usage_gaps_with_identical_plain_text | 10 hazardous kill call(s)
.......................... [2566%]
........................................................................ [2569%]
........................................................................ [2572%]
........................................................................ [2575%]
........................................................................ [2579%]
.......................................................[contention-diag] +4259s soak 34p/158t rss 13.9G pss 12.7G swap 0.6G majflt 6176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 6 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 41.04 | cgroup 15.1G/max oom_kill 0 | free scratch 329.9G/45518312i tmp 29.7G/1019833i workspace 329.9G/45518312i | repeat-01 collected 26/26 workers (60602 items) tests 59165 done 3 failed | 8 in flight, oldest 4s gw9 tests/test_provider_usage_indicator_widget.py::test_initial_cache_renders_after_header_budget | 10 hazardous kill call(s)
................. [2582%]
........................................................................ [2585%]
........................................................................ [2588%]
........................................................................ [2591%]
........................................................................ [2594%]
...........[contention-diag] +4274s soak 37p/162t rss 13.8G pss 12.6G swap 0.6G majflt 6176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.2G, 9 descendant rss 0.1G pss 0.0G | host avail 33.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.98 cpu 34.18 | cgroup 15.1G/max oom_kill 0 | free scratch 329.9G/45519059i tmp 29.7G/1019833i workspace 329.9G/45519059i | repeat-01 collected 26/26 workers (60602 items) tests 59451 done 3 failed | 7 in flight, oldest 19s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
............................................................. [2597%]
...............s........................................................ [2601%]
........................................................................ [2604%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
........................................................................ [2616%]
........................................................................ [2619%]
........................................................................ [2623%]
........................................................................ [2626%]
............................................[contention-diag] +4290s soak 37p/166t rss 13.9G pss 12.7G swap 0.6G majflt 6176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.2G, 9 descendant rss 0.2G pss 0.1G | host avail 33.4G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 34.61 | cgroup 15.2G/max oom_kill 0 | free scratch 329.9G/45518669i tmp 29.7G/1019833i workspace 329.9G/45518669i | repeat-01 collected 26/26 workers (60602 items) tests 60212 done 3 failed | 5 in flight, oldest 34s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
............................ [2629%]
........................................ssss............................ [2632%]
...............[contention-diag] +4305s soak 36p/158t rss 14.2G pss 13.0G swap 0.7G majflt 6176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.2G, 8 descendant rss 0.5G pss 0.4G | host avail 31.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 34.16 | cgroup 15.5G/max oom_kill 0 | free scratch 329.9G/45518419i tmp 29.7G/1019833i workspace 329.9G/45518419i | scratch used 0.9G in 168892 entries | repeat-01 collected 26/26 workers (60602 items) tests 60316 done 3 failed | 5 in flight, oldest 50s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
......................................................... [2635%]
........................................................................ [2638%]
........................................................................ [2641%]
.......[contention-diag] +4322s soak 33p/153t rss 13.8G pss 12.6G swap 0.6G majflt 6183 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 5 descendant rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.49 | cgroup 15.1G/max oom_kill 0 | free scratch 329.9G/45520705i tmp 29.7G/1019833i workspace 329.9G/45520705i | repeat-01 collected 26/26 workers (60602 items) tests 60553 done 3 failed | 1 in flight, oldest 0s gw9 tests/tool/test_demand_runs.py::test_instant_child_records_nonzero_tree_peak_from_rusage_floor | 10 hazardous kill call(s)
..........................[contention-diag] +4338s soak 34p/153t rss 13.8G pss 12.7G swap 0.6G majflt 6183 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 6 descendant rss 0.1G pss 0.1G | host avail 32.9G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 4.34 | cgroup 15.1G/max oom_kill 0 | free scratch 329.9G/45520629i tmp 29.7G/1019833i workspace 329.9G/45520629i | repeat-01 collected 26/26 workers (60602 items) tests 60577 done 3 failed | 1 in flight, oldest 6s gw9 tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors | 10 hazardous kill call(s)
.................                       [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________ test_agent_first_page_paints_before_full_extension ______________
[gw22] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb07b3af7d0>

    async def test_agent_first_page_paints_before_full_extension(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        from sase.feature_flags import override_flags
    
        with override_flags(artifacts_agent_pane_retired=False):
>           await _agent_first_page_paints_before_full_extension(monkeypatch)

tests/ace/tui/test_artifacts_agents_loading.py:26: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb07b3af7d0>

    async def _agent_first_page_paints_before_full_extension(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        first_rows = (
            make_agent_catalog_row("newest", started_at="2026-08-24T12:00:00+00:00"),
            make_agent_catalog_row("older", started_at="2026-08-24T11:00:00+00:00"),
        )
        full_rows = (
            *first_rows,
            make_agent_catalog_row("oldest", started_at="2026-08-24T10:00:00+00:00"),
        )
        full_started = Event()
        release_full = Event()
        requested_limits: list[int | None] = []
        indexed_row_counts: list[int] = []
    
        def load(project: str | None, limit: int | None = None) -> AgentsSnapshot:
            requested_limits.append(limit)
            if limit is None:
                full_started.set()
                assert release_full.wait(timeout=LOAD_TOLERANT_TIMEOUT)
                return AgentsSnapshot(
                    project=project,
                    rows=full_rows,
                    total_row_count=len(full_rows),
                    complete=True,
                )
            return AgentsSnapshot(
                project=project,
                rows=first_rows,
                total_row_count=len(full_rows),
                complete=False,
            )
    
        original_build = ArtifactsAgentsPane._build_agents_query_index
    
        def build_index(
            self: ArtifactsAgentsPane, snapshot: AgentsSnapshot, *, generation: int
        ):
            indexed_row_counts.append(len(snapshot.rows))
            return original_build(self, snapshot, generation=generation)
    
        monkeypatch.setattr(agents_pane, "load_agents_snapshot", load)
        monkeypatch.setattr(ArtifactsAgentsPane, "_build_agents_query_index", build_index)
    
        try:
            async with AcePage(initial_tab="patches", startup_policy="real") as page:
                await page.press(page.artifacts_digit("agents"))
                pane = page.query_one_widget(
                    "#artifacts-agents-pane",
                    ArtifactsAgentsPane,
                )
                await page.wait_for(
                    lambda _state: (
                        pane.snapshot is not None and len(pane.snapshot.rows) == 2
                    ),
                    timeout=LOAD_TOLERANT_TIMEOUT,
                )
    
                assert pane.snapshot is not None
                assert pane.snapshot.complete is False
                assert pane._query_index is None
                assert requested_limits[0] == AGENTS_FIRST_PAGE_LIMIT
                assert indexed_row_counts == []
    
                pane._commit_agents_query("role:code limit:100")
                _filtered, exact, pending, _truncated, match_count = (
                    pane._filtered_agents_snapshot()
                )
                assert exact is False
                assert pending is True
                assert match_count is None
    
>               assert full_started.wait(timeout=LOAD_TOLERANT_TIMEOUT)
E               assert False
E                +  where False = wait(timeout=60.0)
E                +    where wait = <threading.Event at 0x7fb07b3add30: unset>.wait

tests/ace/tui/test_artifacts_agents_loading.py:102: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:241 TUI event loop stall detected: 5.290s pid=243558
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:295 TUI message pump stall detected: 5.107s pid=243558
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:267 TUI event loop recovered after 60.102s
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:241 TUI event loop stall detected: 6.752s pid=243558
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:321 TUI message pump recovered after 66.797s
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:267 TUI event loop recovered after 9.261s
________________ test_startup_update_toast_appears_once_in_tui _________________
[gw23] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fe47df99a90>

    async def test_startup_update_toast_appears_once_in_tui(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        status = _status()
        # Commit previews (git and GitHub queries against the installed
        # components) and the Rust prebuild are not what this test asserts; left
        # on, they ran real subprocesses and network calls on the toast path.
        monkeypatch.setattr(
            update_toast,
            "_load_update_toast_config",
            lambda: update_toast._UpdateToastConfig(
                startup_toast=True, incoming_commits_enabled=False, prebuild_rust=False
            ),
        )
        monkeypatch.setattr(
            update_toast,
            "get_cached_update_status",
            lambda **_kwargs: status,
        )
    
        async with AcePage(query='"toast"', startup_policy="real") as page:
            # Hang guard for a whole real startup: the toast lands only after the
            # deferred maintenance chain, about 3 CPU-seconds from test start
            # unloaded -- 50-90 s at the contention soak's CPU share, past the
            # single-wait default.
            await page.wait_for(
                lambda _s: bool(list(page.app._notifications)),
                timeout=_REAL_STARTUP_TOAST_TIMEOUT,
            )
            notifications = list(page.app._notifications)
            assert len(notifications) == 1
            assert notifications[0].title == f"{UPDATE_GLYPH} Updates available"
            assert "Press" in notifications[0].message
    
            page.app._show_startup_update_toast(status)
            await page.pause()
>           assert len(list(page.app._notifications)) == 1
E           AssertionError: assert 0 == 1
E            +  where 0 = len([])
E            +    where [] = list(<textual.notifications.Notifications object at 0x7fe4aff3a0c0>)
E            +      where <textual.notifications.Notifications object at 0x7fe4aff3a0c0> = AceApp(title='sase tui (v0.18.1+442.gdde1ada13)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'})._notifications
E            +        where AceApp(title='sase tui (v0.18.1+442.gdde1ada13)', classes={'-dark-mode'}, pseudo_classes={'dark', 'focus'}) = <sase.ace.testing.ace_page.AcePage object at 0x7fe4ae9b8620>.app

tests/ace/tui/test_update_toast_startup.py:189: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:241 TUI event loop stall detected: 9.513s pid=243599
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:295 TUI message pump stall detected: 9.339s pid=243599
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:267 TUI event loop recovered after 10.297s
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:321 TUI message pump recovered after 10.123s
___________ test_vcs_tag_project_namespace_opens_project_macro_menu ____________
[gw7] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw7/test_vcs_tag_project_namespace0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f468b1d6720>

    async def test_vcs_tag_project_namespace_opens_project_macro_menu(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Reported regression: ``#git:proj #proj/`` must offer project macros.
    
        The VCS tag names the project the user-facing way while the catalog knows
        it by its ProjectSpec directory key, so the menu stayed empty until both
        spellings were normalized to the canonical namespace.
        """
        app = CatalogCompletionTestApp()
        with registered_project_macros(
            tmp_path,
            monkeypatch,
            project_key="gh_org__proj",
            project_name="proj",
            macros={"reads": "Reads body", "sync": "Sync body"},
        ):
            async with app.run_test() as pilot:
                ta = app.query_one(PromptTextArea)
                ta.load_text("#git:proj #proj")
                ta.cursor_location = (0, len("#git:proj #proj"))
    
                await pilot.press("/")
    
                menu_text = ta.text
                menu_candidates = [c.insertion for c in ta._file_completion_candidates]
                menu_active = ta._file_completion_active
                menu_kind = ta._completion_kind
    
                # The directory-key spelling is not a real reference, so it must
                # not be offered either.
                ta.load_text("#git:proj #gh_org__proj")
                ta.cursor_location = (0, len("#git:proj #gh_org__proj"))
    
                await pilot.press("/")
    
                key_candidates = [c.insertion for c in ta._file_completion_candidates]
    
        assert menu_text == "#git:proj #proj/"
        assert menu_active is True
        assert menu_kind == "macro"
        assert menu_candidates == ["#proj/reads", "#proj/sync"]
        assert key_candidates == []
>       assert app.requested_projects == ["proj"] * len(app.requested_projects)
E       AssertionError: assert [None, 'proj'..., 'proj', ...] == ['proj', 'pro..., 'proj', ...]
E         
E         At index 0 diff: None != 'proj'
E         Use -v to get more diff

tests/ace/tui/widgets/test_auto_macro_completion.py:442: AssertionError
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

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/typing.py:2187: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    def cast(typ, val):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_new_project_create_execution.py::test_create_review_renders_danger_heading_and_keep_notice
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/css/tokenizer.py:302: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for name, value in zip(expect.names, match.groups()[1:]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/geometry.py:221: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    @property
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/typing.py:2187: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def cast(typ, val):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_display_group_fold_repaint.py::test_expand_repaints_and_restores_rows
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/core/content_layout_wire.py:330: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    formats=tuple(str(item) for item in raw.get("formats", [])),
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_tabs_launch_view.py::test_apply_launch_view_tab_inserts_from_named_view
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    payload = binding(
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=242481) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=243489) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=242128) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=242155) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:888: DeprecationWarning: This process (pid=242128) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=243558) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
522.89s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
433.30s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
431.57s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
424.47s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
410.99s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
380.79s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
326.54s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
324.22s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
318.74s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
308.47s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
300.17s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
242.63s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
214.34s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
189.63s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
185.37s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
172.14s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
168.43s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
161.84s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
156.07s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
140.16s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
=========================== short test summary info ============================
FAILED tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
FAILED tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
FAILED tests/ace/tui/widgets/test_auto_macro_completion.py::test_vcs_tag_project_namespace_opens_project_macro_menu
==== 3 failed, 60579 passed, 21 skipped, 111 warnings in 4351.46s (1:12:31) ====
[contention-diag] +4352s soak 2p/2t rss 0.5G pss 0.5G swap 0.0G majflt 155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 44.2G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.8 | cgroup 2.9G/max oom_kill 0 | free scratch 329.9G/45521339i tmp 29.7G/1019833i workspace 329.9G/45521339i | repeat-01 collected 26/26 workers (60602 items) tests 60602 done 3 failed | 10 hazardous kill call(s)
[contention-diag] +4358s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G | host avail 46.1G/62.7G swapfree 57.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 14.62 | cgroup 2.5G/max oom_kill 0 | free scratch 329.9G/45521342i tmp 29.7G/1019833i workspace 329.9G/45521342i | repeat-01 collected 26/26 workers (60602 items) tests 60602 done 3 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4358s, 285 samples, 0 signal(s); peaks: cgroup_current 15.9G, min_free_scratch 329.6G, min_free_tmp 29.7G, min_free_workspace 329.6G, min_inodes_scratch 45518312, min_inodes_tmp 1019831, min_inodes_workspace 45518312, min_mem_available 30.9G, min_swap_free 55.4G, oom_kill_delta 0, pressure_memory_full 1.59, pswpin_delta 199733, pswpout_delta 28123, scratch_bytes 0.9G, soak_procs 46, soak_pss 13.6G, soak_rss 14.8G, soak_swap 1.3G, soak_threads 296

contention tally: 3 node(s) failed across 1 repeat(s) in 4357.6s; red repeats: 1
  1/1  tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension  (repeats 1)
  1/1  tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui  (repeats 1)
  1/1  tests/ace/tui/widgets/test_auto_macro_completion.py::test_vcs_tag_project_namespace_opens_project_macro_menu  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

