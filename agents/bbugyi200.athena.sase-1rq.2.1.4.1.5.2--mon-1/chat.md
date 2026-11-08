# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-1)

- **TIMESTAMP:** 2026-11-08 07:32:05 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-1

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after TUI pump, toast-timeout, and catalog-namespace repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5670 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 1458131, sampler pid 1458203 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-1057937-1794136446656720318.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 96 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 41.5G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 323.2G/45495373i tmp 29.7G/1019825i workspace 323.2G/45495373i | scratch used 0.1G in 18249 entries (truncated) | progress none yet
[contention-diag] +17s soak 28p/80t rss 2.3G pss 2.0G swap 0.0G majflt 155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.2G pss 1.9G | host avail 42.7G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 15.62 | cgroup 2.1G/max oom_kill 0 | free scratch 323.3G/45495223i tmp 29.7G/1019825i workspace 323.3G/45495223i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 3.6G pss 3.2G swap 1.2G majflt 500 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.5G pss 3.1G | host avail 39.7G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 17.33 | cgroup 3.3G/max oom_kill 0 | free scratch 323.3G/45495176i tmp 29.7G/1019825i workspace 323.3G/45495176i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +48s soak 28p/82t rss 4.7G pss 4.3G swap 1.2G majflt 644 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.5G pss 4.2G | host avail 37.3G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 18.12 | cgroup 4.4G/max oom_kill 0 | free scratch 323.7G/45519037i tmp 29.7G/1019825i workspace 323.7G/45519037i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +63s soak 28p/88t rss 5.4G pss 5.0G swap 1.2G majflt 865 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.3G pss 4.9G | host avail 36.1G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.4 cpu 22.38 | cgroup 5.2G/max oom_kill 0 | free scratch 323.5G/45507731i tmp 29.7G/1019825i workspace 323.5G/45507731i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/89t rss 6.2G pss 5.8G swap 1.2G majflt 948 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.1G pss 5.7G | host avail 35.9G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.2 cpu 25.22 | cgroup 6.0G/max oom_kill 0 | free scratch 323.5G/45507740i tmp 29.7G/1019825i workspace 323.5G/45507740i | repeat-01 collected 4/26 workers (9277 items) tests 0 done 0 failed
contention shards: 26 workers collected 60602 items in total (2079-2555 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
........................................................................ [ 12%]
........................................................................ [ 15%]
.....................................................[contention-diag] +93s soak 28p/101t rss 6.7G pss 6.2G swap 1.1G majflt 1675 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.5G pss 6.1G | host avail 36.4G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 22.91 | cgroup 6.5G/max oom_kill 0 | free scratch 323.5G/45506273i tmp 29.7G/1019825i workspace 323.5G/45506273i | repeat-01 collected 26/26 workers (60602 items) tests 337 done 0 failed | 24 in flight, oldest 3s gw15 tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
................... [ 18%]
........................................................................ [ 21%]
........................................................................ [ 25%]
........................................................................ [ 28%]
........................................................................ [ 31%]
........................................................................ [ 34%]
........................................................................ [ 37%]
........................................................................ [ 40%]
.......................................................................[contention-diag] +109s soak 30p/131t rss 7.2G pss 6.7G swap 1.1G majflt 2093 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.0G pss 6.5G, 2 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 20.78 | cgroup 7.0G/max oom_kill 0 | free scratch 323.5G/45504914i tmp 29.7G/1019825i workspace 323.5G/45504914i | repeat-01 collected 26/26 workers (60602 items) tests 996 done 0 failed | 26 in flight, oldest 16s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
. [ 43%]
........................................................................ [ 47%]
........................................................................ [ 50%]
.......................................................[contention-diag] +124s soak 30p/162t rss 7.5G pss 6.9G swap 1.0G majflt 2086 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.8G, 2 descendant rss 0.1G pss 0.1G | host avail 34.8G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.08 cpu 22.99 | cgroup 7.2G/max oom_kill 0 | free scratch 323.5G/45504468i tmp 29.7G/1019825i workspace 323.5G/45504468i | scratch used 0.1G in 25428 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 1171 done 0 failed | 26 in flight, oldest 31s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
................. [ 53%]
........................................................................ [ 56%]
........................................................................ [ 59%]
........................................................................ [ 62%]
..........................................[contention-diag] +141s soak 31p/183t rss 7.8G pss 7.2G swap 1.0G majflt 2171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.5G pss 6.9G, 3 descendant rss 0.1G pss 0.1G | host avail 36.9G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.19 cpu 33.66 | cgroup 7.6G/max oom_kill 0 | free scratch 323.5G/45503718i tmp 29.7G/1019825i workspace 323.5G/45503718i | repeat-01 collected 26/26 workers (60602 items) tests 1479 done 0 failed | 26 in flight, oldest 49s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.............................. [ 65%]
........................................................................ [ 69%]
........................................................................ [ 72%]
................[contention-diag] +156s soak 29p/177t rss 7.9G pss 7.3G swap 1.0G majflt 2245 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.7G pss 7.1G, 1 descendant rss 0.1G pss 0.1G | host avail 34.4G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 31.24 | cgroup 7.7G/max oom_kill 0 | free scratch 323.5G/45503186i tmp 29.7G/1019825i workspace 323.5G/45503186i | repeat-01 collected 26/26 workers (60602 items) tests 1668 done 0 failed | 26 in flight, oldest 63s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
........................................................ [ 75%]
........................................................................ [ 78%]
........................................................................ [ 81%]
.......[contention-diag] +171s soak 33p/188t rss 8.0G pss 7.5G swap 1.0G majflt 2252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.3G, 5 descendant rss 0.1G pss 0.0G | host avail 34.7G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.3 | cgroup 7.8G/max oom_kill 0 | free scratch 323.5G/45502591i tmp 29.7G/1019825i workspace 323.5G/45502591i | repeat-01 collected 26/26 workers (60602 items) tests 1879 done 0 failed | 26 in flight, oldest 56s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................. [ 84%]
........................................................................ [ 87%]
........................................................................ [ 91%]
.................................................[contention-diag] +187s soak 35p/223t rss 8.3G pss 7.6G swap 1.0G majflt 2257 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.4G, 7 descendant rss 0.1G pss 0.1G | host avail 35.8G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.63 cpu 25.95 | cgroup 8.0G/max oom_kill 0 | free scratch 323.5G/45498945i tmp 29.7G/1019823i workspace 323.5G/45498945i | repeat-01 collected 26/26 workers (60602 items) tests 2125 done 0 failed | 26 in flight, oldest 71s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................... [ 94%]
........................................................................ [ 97%]
........................................................................ [100%]
...................................................................[contention-diag] +202s soak 37p/208t rss 8.8G pss 8.1G swap 1.1G majflt 2312 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.7G, 9 descendant rss 0.3G pss 0.2G | host avail 35.3G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.2 cpu 27.64 | cgroup 8.5G/max oom_kill 0 | free scratch 323.5G/45500857i tmp 29.7G/1019823i workspace 323.5G/45500857i | repeat-01 collected 26/26 workers (60602 items) tests 2358 done 0 failed | 26 in flight, oldest 86s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [103%]
........................................................................ [106%]
......................................[contention-diag] +217s soak 36p/229t rss 8.7G pss 8.1G swap 1.0G majflt 2314 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.7G, 8 descendant rss 0.2G pss 0.2G | host avail 35.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.2 cpu 30.63 | cgroup 8.4G/max oom_kill 0 | free scratch 323.5G/45500523i tmp 29.7G/1019823i workspace 323.5G/45500523i | repeat-01 collected 26/26 workers (60602 items) tests 2478 done 0 failed | 26 in flight, oldest 101s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................. [109%]
........................................................................ [113%]
.........................................[contention-diag] +232s soak 36p/240t rss 8.6G pss 8.0G swap 1.0G majflt 2326 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 8 descendant rss 0.1G pss 0.1G | host avail 34.8G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.86 cpu 27.85 | cgroup 8.4G/max oom_kill 0 | free scratch 323.5G/45500097i tmp 29.7G/1019823i workspace 323.5G/45500097i | repeat-01 collected 26/26 workers (60602 items) tests 2631 done 0 failed | 26 in flight, oldest 117s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................... [116%]
........................................................................ [119%]
........................................................................ [122%]
.....................................................................[contention-diag] +248s soak 37p/212t rss 8.9G pss 8.2G swap 1.0G majflt 2346 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 9 descendant rss 0.3G pss 0.2G | host avail 34.4G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 1.75 cpu 25.76 | cgroup 8.7G/max oom_kill 0 | free scratch 323.5G/45499371i tmp 29.7G/1019823i workspace 323.5G/45499371i | scratch used 0.3G in 48258 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 2866 done 0 failed | 26 in flight, oldest 132s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
... [125%]
........................................................................ [128%]
..............................................[contention-diag] +265s soak 36p/214t rss 9.0G pss 8.3G swap 1.0G majflt 2396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.0G, 8 descendant rss 0.3G pss 0.2G | host avail 35.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 1.64 cpu 26.84 | cgroup 8.8G/max oom_kill 0 | free scratch 323.5G/45499046i tmp 29.7G/1019823i workspace 323.5G/45499046i | repeat-01 collected 26/26 workers (60602 items) tests 2996 done 0 failed | 26 in flight, oldest 149s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................... [131%]
.........[contention-diag] +280s soak 35p/246t rss 9.0G pss 8.3G swap 0.9G majflt 2411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 7 descendant rss 0.1G pss 0.0G | host avail 34.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.19 cpu 29.57 | cgroup 8.8G/max oom_kill 0 | free scratch 323.4G/45498827i tmp 29.7G/1019823i workspace 323.4G/45498827i | repeat-01 collected 26/26 workers (60602 items) tests 3033 done 0 failed | 26 in flight, oldest 164s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................... [135%]
........................................................................ [138%]
..............................[contention-diag] +295s soak 34p/239t rss 9.0G pss 8.3G swap 0.9G majflt 2411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 6 descendant rss 0.1G pss 0.0G | host avail 33.9G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 3.82 cpu 26.63 | cgroup 8.8G/max oom_kill 0 | free scratch 323.4G/45498350i tmp 29.7G/1019823i workspace 323.4G/45498350i | repeat-01 collected 26/26 workers (60602 items) tests 3182 done 0 failed | 26 in flight, oldest 180s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................................... [141%]
........................................................................ [144%]
................[contention-diag] +310s soak 37p/254t rss 9.2G pss 8.5G swap 0.9G majflt 2413 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 9 descendant rss 0.2G pss 0.1G | host avail 34.8G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.55/0.55 io 1.44 cpu 27.35 | cgroup 9.0G/max oom_kill 0 | free scratch 323.4G/45497944i tmp 29.7G/1019823i workspace 323.4G/45497944i | repeat-01 collected 26/26 workers (60602 items) tests 3325 done 0 failed | 26 in flight, oldest 195s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................................ [147%]
........................................................................ [150%]
.............................[contention-diag] +326s soak 34p/245t rss 9.2G pss 8.5G swap 1.0G majflt 2414 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.74 cpu 24.21 | cgroup 9.0G/max oom_kill 0 | free scratch 323.4G/45497435i tmp 29.7G/1019823i workspace 323.4G/45497435i | repeat-01 collected 26/26 workers (60602 items) tests 3450 done 0 failed | 26 in flight, oldest 210s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................... [153%]
........................................................................ [157%]
.........................................................[contention-diag] +341s soak 33p/250t rss 9.2G pss 8.5G swap 0.9G majflt 2417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 35.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.29 cpu 24.99 | cgroup 9.0G/max oom_kill 0 | free scratch 323.4G/45496998i tmp 29.7G/1019823i workspace 323.4G/45496998i | repeat-01 collected 26/26 workers (60602 items) tests 3654 done 0 failed | 26 in flight, oldest 225s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............... [160%]
........................................................................ [163%]
.........[contention-diag] +356s soak 34p/262t rss 9.3G pss 8.6G swap 0.9G majflt 2434 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.5G, 6 descendant rss 0.1G pss 0.0G | host avail 34.5G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.25 cpu 25.37 | cgroup 9.1G/max oom_kill 0 | free scratch 323.4G/45496647i tmp 29.7G/1019823i workspace 323.4G/45496647i | repeat-01 collected 26/26 workers (60602 items) tests 3752 done 0 failed | 26 in flight, oldest 241s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..........................................................[contention-diag] +371s soak 36p/283t rss 9.5G pss 8.8G swap 1.0G majflt 2434 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 8 descendant rss 0.2G pss 0.2G | host avail 34.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.92 cpu 27.43 | cgroup 9.3G/max oom_kill 0 | free scratch 323.4G/45496412i tmp 29.7G/1019823i workspace 323.4G/45496412i | scratch used 0.4G in 64075 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 3807 done 0 failed | 26 in flight, oldest 256s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [166%]
........................................................................ [169%]
.............[contention-diag] +389s soak 40p/260t rss 9.6G pss 8.8G swap 1.0G majflt 2424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 12 descendant rss 0.2G pss 0.1G | host avail 34.4G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.85 cpu 27.62 | cgroup 9.4G/max oom_kill 0 | free scratch 323.4G/45496062i tmp 29.7G/1019823i workspace 323.4G/45496062i | repeat-01 collected 26/26 workers (60602 items) tests 3897 done 0 failed | 26 in flight, oldest 273s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................................... [172%]
......................................................................[contention-diag] +404s soak 39p/279t rss 9.6G pss 8.9G swap 0.9G majflt 2424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 11 descendant rss 0.2G pss 0.1G | host avail 34.1G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 3.0 cpu 28.33 | cgroup 9.4G/max oom_kill 0 | free scratch 323.4G/45495769i tmp 29.7G/1019823i workspace 323.4G/45495769i | repeat-01 collected 26/26 workers (60602 items) tests 4029 done 0 failed | 26 in flight, oldest 288s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.. [175%]
........................................................................ [179%]
................[contention-diag] +419s soak 41p/274t rss 9.7G pss 9.0G swap 1.0G majflt 2424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 13 descendant rss 0.3G pss 0.2G | host avail 33.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.64 cpu 27.87 | cgroup 9.6G/max oom_kill 0 | free scratch 323.4G/45495448i tmp 29.7G/1019823i workspace 323.4G/45495448i | repeat-01 collected 26/26 workers (60602 items) tests 4118 done 0 failed | 26 in flight, oldest 304s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................[contention-diag] +434s soak 41p/257t rss 9.7G pss 9.0G swap 0.9G majflt 2424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 13 descendant rss 0.2G pss 0.1G | host avail 32.5G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.06 cpu 26.13 | cgroup 9.6G/max oom_kill 0 | free scratch 323.4G/45495219i tmp 29.7G/1019823i workspace 323.4G/45495219i | repeat-01 collected 26/26 workers (60602 items) tests 4163 done 0 failed | 26 in flight, oldest 319s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........ [182%]
........................................................................ [185%]
.......................................................[contention-diag] +450s soak 34p/261t rss 9.6G pss 9.0G swap 0.9G majflt 2426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 6 descendant rss 0.1G pss 0.0G | host avail 33.0G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 25.62 | cgroup 9.6G/max oom_kill 0 | free scratch 323.4G/45494777i tmp 29.7G/1019823i workspace 323.4G/45494777i | repeat-01 collected 26/26 workers (60602 items) tests 4293 done 0 failed | 26 in flight, oldest 334s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................. [188%]
.........................[contention-diag] +465s soak 34p/268t rss 9.7G pss 9.0G swap 0.9G majflt 2462 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 6 descendant rss 0.1G pss 0.0G | host avail 32.4G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.38 cpu 24.06 | cgroup 9.6G/max oom_kill 0 | free scratch 323.4G/45494568i tmp 29.7G/1019823i workspace 323.4G/45494568i | repeat-01 collected 26/26 workers (60602 items) tests 4343 done 0 failed | 26 in flight, oldest 349s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................... [191%]
.....................................[contention-diag] +480s soak 30p/252t rss 9.7G pss 9.1G swap 0.9G majflt 2464 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.12 cpu 21.33 | cgroup 9.7G/max oom_kill 0 | free scratch 323.4G/45494317i tmp 29.7G/1019823i workspace 323.4G/45494317i | repeat-01 collected 26/26 workers (60602 items) tests 4415 done 0 failed | 25 in flight, oldest 365s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [194%]
........................................................................ [197%]
..............[contention-diag] +496s soak 30p/261t rss 9.9G pss 9.2G swap 1.0G majflt 2464 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 1.53 cpu 24.73 | cgroup 9.8G/max oom_kill 0 | free scratch 323.4G/45493886i tmp 29.7G/1019823i workspace 323.4G/45493886i | scratch used 0.5G in 81866 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 4543 done 0 failed | 26 in flight, oldest 380s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................[contention-diag] +513s soak 28p/242t rss 9.8G pss 9.1G swap 0.9G majflt 2465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G | host avail 31.4G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.33/0.2 io 1.41 cpu 24.26 | cgroup 9.7G/max oom_kill 0 | free scratch 323.8G/45493679i tmp 29.7G/1019823i workspace 323.8G/45493679i | repeat-01 collected 26/26 workers (60602 items) tests 4573 done 0 failed | 26 in flight, oldest 103s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
.............[contention-diag] +528s soak 29p/236t rss 9.9G pss 9.2G swap 0.9G majflt 2489 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 29.8G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.16/0.13 io 2.31 cpu 22.69 | cgroup 9.8G/max oom_kill 0 | free scratch 323.8G/45493500i tmp 29.7G/1019823i workspace 323.8G/45493500i | repeat-01 collected 26/26 workers (60602 items) tests 4583 done 0 failed | 26 in flight, oldest 48s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
...................... [201%]
.......................[contention-diag] +543s soak 31p/238t rss 10.0G pss 9.4G swap 0.9G majflt 2766 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 3 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 2.09 cpu 22.16 | cgroup 10.0G/max oom_kill 0 | free scratch 323.8G/45493290i tmp 29.7G/1019823i workspace 323.8G/45493290i | repeat-01 collected 26/26 workers (60602 items) tests 4629 done 0 failed | 26 in flight, oldest 63s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
................................................. [204%]
...................................[contention-diag] +559s soak 29p/241t rss 10.0G pss 9.3G swap 1.0G majflt 2487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 1 descendant rss 0.1G pss 0.1G | host avail 29.7G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.7 cpu 18.0 | cgroup 10.0G/max oom_kill 0 | free scratch 323.8G/45492917i tmp 29.7G/1019823i workspace 323.8G/45492917i | repeat-01 collected 26/26 workers (60602 items) tests 4704 done 0 failed | 26 in flight, oldest 58s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
..................................... [207%]
.................[contention-diag] +574s soak 28p/256t rss 9.9G pss 9.3G swap 0.9G majflt 2487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G | host avail 28.8G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 14.82 | cgroup 10.0G/max oom_kill 0 | free scratch 323.8G/45492664i tmp 29.7G/1019823i workspace 323.8G/45492664i | repeat-01 collected 26/26 workers (60602 items) tests 4766 done 0 failed | 26 in flight, oldest 73s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
..................................[contention-diag] +589s soak 29p/247t rss 10.0G pss 9.4G swap 0.9G majflt 2487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 58.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.02 cpu 12.15 | cgroup 10.1G/max oom_kill 0 | free scratch 323.2G/45492326i tmp 29.7G/1019823i workspace 323.2G/45492326i | repeat-01 collected 26/26 workers (60602 items) tests 4801 done 0 failed | 26 in flight, oldest 86s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...................[contention-diag] +604s soak 30p/223t rss 10.0G pss 9.4G swap 0.9G majflt 2487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 2 descendant rss 0.1G pss 0.0G | host avail 29.8G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 0.53/0.39 io 0.99 cpu 12.71 | cgroup 10.1G/max oom_kill 0 | free scratch 323.4G/45492126i tmp 29.7G/1019823i workspace 323.4G/45492126i | repeat-01 collected 26/26 workers (60602 items) tests 4818 done 0 failed | 25 in flight, oldest 46s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
.. [210%]
..................................[contention-diag] +620s soak 28p/256t rss 10.0G pss 9.4G swap 0.9G majflt 2487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 27.6G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 0.13/0.09 io 1.06 cpu 13.64 | cgroup 10.1G/max oom_kill 0 | free scratch 323.3G/45491929i tmp 29.7G/1019823i workspace 323.3G/45491929i | scratch used 0.5G in 90349 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 4854 done 0 failed | 26 in flight, oldest 61s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
...................................... [213%]
....[contention-diag] +637s soak 28p/256t rss 10.1G pss 9.4G swap 0.9G majflt 2487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G | host avail 30.2G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 1.26 cpu 15.07 | cgroup 10.2G/max oom_kill 0 | free scratch 323.3G/45491439i tmp 29.7G/1019823i workspace 323.3G/45491439i | repeat-01 collected 26/26 workers (60602 items) tests 4893 done 0 failed | 26 in flight, oldest 61s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
.................................................................... [216%]
................[contention-diag] +652s soak 30p/246t rss 10.2G pss 9.5G swap 0.9G majflt 2497 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 2 descendant rss 0.1G pss 0.1G | host avail 30.5G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.2 cpu 15.72 | cgroup 10.3G/max oom_kill 0 | free scratch 323.4G/45492726i tmp 29.7G/1019823i workspace 323.4G/45492726i | repeat-01 collected 26/26 workers (60602 items) tests 4983 done 0 failed | 26 in flight, oldest 76s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
............[contention-diag] +668s soak 29p/231t rss 10.2G pss 9.5G swap 0.9G majflt 2508 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 28.7G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.49 cpu 15.58 | cgroup 10.3G/max oom_kill 0 | free scratch 323.2G/45490827i tmp 29.7G/1019823i workspace 323.2G/45490827i | repeat-01 collected 26/26 workers (60602 items) tests 4994 done 0 failed | 26 in flight, oldest 81s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...........................[contention-diag] +683s soak 28p/227t rss 10.2G pss 9.5G swap 0.9G majflt 2511 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 30.0G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.49 cpu 14.1 | cgroup 10.4G/max oom_kill 0 | free scratch 322.7G/45476952i tmp 29.7G/1019822i workspace 322.7G/45476952i | repeat-01 collected 26/26 workers (60602 items) tests 5020 done 0 failed | 26 in flight, oldest 54s gw25 tests/ace/tui/test_link_follow_entry_points.py::test_matrix_archived_plan_via_links_panel
.............[contention-diag] +698s soak 29p/235t rss 10.3G pss 9.6G swap 0.9G majflt 2511 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.1G pss 0.0G | host avail 26.8G/62.7G swapfree 58.5G/64.0G oom_kill +0 | psi10 mem 1.2/1.05 io 2.03 cpu 11.73 | cgroup 10.3G/max oom_kill 0 | free scratch 322.5G/45476635i tmp 29.7G/1019822i workspace 322.5G/45476635i | repeat-01 collected 26/26 workers (60602 items) tests 5035 done 0 failed | 26 in flight, oldest 55s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_collapsed_rail_keeps_keymap_and_footer
.... [219%]
.............................................................[contention-diag] +714s soak 29p/226t rss 10.3G pss 9.6G swap 0.9G majflt 2511 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 24.9G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.38/0.25 io 2.2 cpu 10.2 | cgroup 10.3G/max oom_kill 0 | free scratch 322.3G/45472657i tmp 29.7G/1019822i workspace 322.3G/45472657i | repeat-01 collected 26/26 workers (60602 items) tests 5100 done 0 failed | 26 in flight, oldest 51s gw24 tests/ace/tui/test_config_center_resume.py::test_switching_changes_resume_target_and_home_only_close_retains_it
........... [223%]
.............................................[contention-diag] +729s soak 29p/228t rss 10.3G pss 9.6G swap 0.9G majflt 2512 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 24.4G/62.7G swapfree 58.1G/64.0G oom_kill +0 | psi10 mem 0.07/0.05 io 2.34 cpu 10.6 | cgroup 10.3G/max oom_kill 0 | free scratch 322.2G/45470197i tmp 29.7G/1019822i workspace 322.2G/45470197i | repeat-01 collected 26/26 workers (60602 items) tests 5152 done 0 failed | 26 in flight, oldest 61s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
........................... [226%]
..................................................................[contention-diag] +744s soak 28p/239t rss 10.3G pss 9.6G swap 1.0G majflt 2514 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 24.1G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.52/0.39 io 2.72 cpu 11.78 | cgroup 10.4G/max oom_kill 0 | free scratch 321.4G/45461919i tmp 29.7G/1019822i workspace 321.4G/45461919i | scratch used 0.2G in 34754 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 5200 done 0 failed | 25 in flight, oldest 68s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
...... [229%]
........................................................................ [232%]
........................................................................ [235%]
.......................[contention-diag] +762s soak 29p/240t rss 10.3G pss 9.7G swap 1.0G majflt 2514 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 20.6G/62.7G swapfree 57.0G/64.0G oom_kill +0 | psi10 mem 1.52/1.08 io 8.38 cpu 12.92 | cgroup 10.2G/max oom_kill 0 | free scratch 321.4G/45461302i tmp 29.7G/1019822i workspace 321.4G/45461302i | repeat-01 collected 26/26 workers (60602 items) tests 5422 done 0 failed | 26 in flight, oldest 52s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_block_nav_override_takes_effect_in_mounted_pilot
................................................. [238%]
..................................................[contention-diag] +777s soak 28p/243t rss 10.3G pss 9.7G swap 1.0G majflt 2522 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G | host avail 24.9G/62.7G swapfree 57.0G/64.0G oom_kill +0 | psi10 mem 0.37/0.26 io 4.99 cpu 14.7 | cgroup 10.2G/max oom_kill 0 | free scratch 320.8G/45455958i tmp 29.7G/1019822i workspace 320.8G/45455958i | repeat-01 collected 26/26 workers (60602 items) tests 5511 done 0 failed | 26 in flight, oldest 65s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
...................... [241%]
.................................................................[contention-diag] +792s soak 30p/270t rss 10.5G pss 9.8G swap 1.0G majflt 2531 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 57.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.05 io 2.46 cpu 16.01 | cgroup 10.3G/max oom_kill 0 | free scratch 320.8G/45454031i tmp 29.7G/1019822i workspace 320.8G/45454031i | repeat-01 collected 26/26 workers (60602 items) tests 5607 done 0 failed | 26 in flight, oldest 80s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
....... [245%]
...................................[contention-diag] +807s soak 30p/253t rss 10.4G pss 9.8G swap 1.0G majflt 2530 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.0G pss 0.0G | host avail 25.2G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 3.32 cpu 18.56 | cgroup 10.4G/max oom_kill 0 | free scratch 320.8G/45453752i tmp 29.7G/1019822i workspace 320.8G/45453752i | repeat-01 collected 26/26 workers (60602 items) tests 5649 done 0 failed | 26 in flight, oldest 77s gw9 tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version
........................[contention-diag] +823s soak 29p/238t rss 10.4G pss 9.8G swap 1.0G majflt 2527 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.5 cpu 20.34 | cgroup 10.3G/max oom_kill 0 | free scratch 320.8G/45453605i tmp 29.7G/1019822i workspace 320.8G/45453605i | repeat-01 collected 26/26 workers (60602 items) tests 5671 done 0 failed | 25 in flight, oldest 92s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............. [248%]
...........................................................[contention-diag] +838s soak 28p/275t rss 10.4G pss 9.7G swap 1.2G majflt 2531 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G | host avail 25.1G/62.7G swapfree 56.3G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 3.05 cpu 18.28 | cgroup 10.3G/max oom_kill 0 | free scratch 320.8G/45453336i tmp 29.7G/1019822i workspace 320.8G/45453336i | repeat-01 collected 26/26 workers (60602 items) tests 5747 done 0 failed | 26 in flight, oldest 107s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............. [251%]
........................................................................ [254%]
................[contention-diag] +853s soak 31p/271t rss 10.5G pss 9.7G swap 1.2G majflt 2539 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 3 descendant rss 0.1G pss 0.1G | host avail 24.8G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 2.48 cpu 13.92 | cgroup 10.2G/max oom_kill 0 | free scratch 320.8G/45453483i tmp 29.7G/1019822i workspace 320.8G/45453483i | repeat-01 collected 26/26 workers (60602 items) tests 5847 done 0 failed | 26 in flight, oldest 123s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................................ [257%]
.........................[contention-diag] +869s soak 29p/238t rss 10.2G pss 9.5G swap 1.5G majflt 2652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G, 1 descendant rss 0.1G pss 0.1G | host avail 24.7G/62.7G swapfree 55.7G/64.0G oom_kill +0 | psi10 mem 0.62/0.34 io 2.17 cpu 14.95 | cgroup 9.9G/max oom_kill 0 | free scratch 320.8G/45452661i tmp 29.7G/1019822i workspace 320.8G/45452661i | scratch used 0.3G in 46914 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 5912 done 0 failed | 26 in flight, oldest 138s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............................................... [260%]
...............................[contention-diag] +886s soak 32p/247t rss 10.3G pss 9.5G swap 1.5G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 4 descendant rss 0.1G pss 0.1G | host avail 23.2G/62.7G swapfree 55.7G/64.0G oom_kill +0 | psi10 mem 0.23/0.19 io 1.63 cpu 14.75 | cgroup 10.1G/max oom_kill 0 | free scratch 320.7G/45450572i tmp 29.7G/1019822i workspace 320.7G/45450572i | repeat-01 collected 26/26 workers (60602 items) tests 6002 done 0 failed | 26 in flight, oldest 73s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
......................................... [263%]
................[contention-diag] +901s soak 29p/231t rss 10.3G pss 9.5G swap 1.5G majflt 7940 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G, 1 descendant rss 0.1G pss 0.0G | host avail 21.8G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 1.05/0.75 io 1.58 cpu 15.33 | cgroup 10.0G/max oom_kill 0 | free scratch 320.7G/45450503i tmp 29.7G/1019822i workspace 320.7G/45450503i | repeat-01 collected 26/26 workers (60602 items) tests 6056 done 0 failed | 26 in flight, oldest 59s gw19 tests/ace/tui/test_agents_pane_mount.py::test_agents_pane_mounts_activates_and_loads
........................................................ [267%]
........................................................................ [270%]
.......................................................................[contention-diag] +916s soak 28p/240t rss 10.2G pss 9.4G swap 1.6G majflt 10776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G | host avail 22.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.31/0.18 io 4.44 cpu 15.46 | cgroup 10.0G/max oom_kill 0 | free scratch 320.7G/45449569i tmp 29.7G/1019822i workspace 320.7G/45449569i | repeat-01 collected 26/26 workers (60602 items) tests 6260 done 0 failed | 26 in flight, oldest 49s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
. [273%]
........................................................................ [276%]
........................................................................ [279%]
........................................................................ [282%]
.......................[contention-diag] +932s soak 29p/227t rss 10.2G pss 9.4G swap 1.7G majflt 11579 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.39/0.21 io 2.68 cpu 15.78 | cgroup 9.9G/max oom_kill 0 | free scratch 320.7G/45448633i tmp 29.7G/1019822i workspace 320.7G/45448633i | repeat-01 collected 26/26 workers (60602 items) tests 6495 done 0 failed | 26 in flight, oldest 64s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................................................. [285%]
.......................[contention-diag] +947s soak 28p/239t rss 10.2G pss 9.4G swap 1.7G majflt 11846 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G | host avail 21.6G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.76/0.45 io 2.66 cpu 14.98 | cgroup 9.7G/max oom_kill 0 | free scratch 320.4G/45447312i tmp 29.7G/1019822i workspace 320.4G/45447312i | repeat-01 collected 26/26 workers (60602 items) tests 6575 done 0 failed | 26 in flight, oldest 80s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................................................. [289%]
........................................................................ [292%]
...............................................[contention-diag] +962s soak 28p/232t rss 10.2G pss 9.4G swap 1.7G majflt 12108 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G | host avail 27.4G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.15/0.09 io 2.12 cpu 18.35 | cgroup 9.7G/max oom_kill 0 | free scratch 321.1G/45445180i tmp 29.7G/1019822i workspace 321.1G/45445180i | repeat-01 collected 26/26 workers (60602 items) tests 6742 done 0 failed | 26 in flight, oldest 68s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
......................... [295%]
..........................................[contention-diag] +978s soak 28p/231t rss 10.2G pss 9.4G swap 1.7G majflt 12604 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G | host avail 26.3G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 1.08 cpu 19.77 | cgroup 9.7G/max oom_kill 0 | free scratch 321.1G/45444861i tmp 29.7G/1019822i workspace 321.1G/45444861i | repeat-01 collected 26/26 workers (60602 items) tests 6810 done 0 failed | 26 in flight, oldest 50s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
.............................. [298%]
.....................[contention-diag] +993s soak 31p/238t rss 10.4G pss 9.5G swap 1.7G majflt 13235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.4G, 3 descendant rss 0.1G pss 0.0G | host avail 25.6G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.48 cpu 18.04 | cgroup 9.9G/max oom_kill 0 | free scratch 321.1G/45444636i tmp 29.7G/1019822i workspace 321.1G/45444636i | scratch used 0.2G in 40066 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 6854 done 0 failed | 26 in flight, oldest 40s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_toggle_install_mark_noops_for_installed
................................................... [301%]
........................................................................ [304%]
..................................................[contention-diag] +1010s soak 29p/221t rss 10.4G pss 9.5G swap 1.6G majflt 13739 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 25.3G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.59 cpu 19.68 | cgroup 10.0G/max oom_kill 0 | free scratch 321.0G/45443726i tmp 29.7G/1019822i workspace 321.0G/45443726i | repeat-01 collected 26/26 workers (60602 items) tests 7019 done 0 failed | 26 in flight, oldest 54s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
...................... [307%]
........................................................................ [310%]
..................[contention-diag] +1025s soak 29p/227t rss 10.4G pss 9.6G swap 1.6G majflt 14031 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.42/0.12 io 3.85 cpu 16.53 | cgroup 10.0G/max oom_kill 0 | free scratch 320.9G/45442699i tmp 29.7G/1019822i workspace 320.9G/45442699i | repeat-01 collected 26/26 workers (60602 items) tests 7136 done 0 failed | 26 in flight, oldest 69s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
....................[contention-diag] +1041s soak 30p/231t rss 10.5G pss 9.6G swap 1.6G majflt 14142 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G, 2 descendant rss 0.1G pss 0.1G | host avail 26.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.1/0.02 io 1.39 cpu 18.86 | cgroup 10.0G/max oom_kill 0 | free scratch 320.6G/45442009i tmp 29.7G/1019819i workspace 320.6G/45442009i | repeat-01 collected 26/26 workers (60602 items) tests 7164 done 0 failed | 26 in flight, oldest 43s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_limit_all_then_ctrl_k_introduces_page_size
.................................. [314%]
.............................................[contention-diag] +1056s soak 29p/229t rss 10.5G pss 9.6G swap 1.6G majflt 14578 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 1 descendant rss 0.1G pss 0.0G | host avail 27.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 2.19 cpu 19.47 | cgroup 10.0G/max oom_kill 0 | free scratch 320.2G/45441814i tmp 29.7G/1019819i workspace 320.2G/45441814i | repeat-01 collected 26/26 workers (60602 items) tests 7230 done 0 failed | 25 in flight, oldest 40s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
........................... [317%]
........................................................................ [320%]
..........................................[contention-diag] +1071s soak 28p/251t rss 10.4G pss 9.6G swap 1.6G majflt 14730 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G | host avail 27.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.78 cpu 17.85 | cgroup 10.0G/max oom_kill 0 | free scratch 319.5G/45417655i tmp 29.7G/1019819i workspace 319.5G/45417655i | repeat-01 collected 26/26 workers (60602 items) tests 7385 done 0 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
.............................. [323%]
........................................................................ [326%]
................................[contention-diag] +1087s soak 29p/225t rss 10.5G pss 9.6G swap 1.6G majflt 14816 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 29.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.26/0.26 io 5.65 cpu 18.34 | cgroup 10.0G/max oom_kill 0 | free scratch 319.4G/45414924i tmp 29.7G/1019819i workspace 319.4G/45414924i | repeat-01 collected 26/26 workers (60602 items) tests 7510 done 0 failed | 26 in flight, oldest 59s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
........................................ [329%]
........................................[contention-diag] +1102s soak 28p/236t rss 10.5G pss 9.6G swap 1.6G majflt 14903 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G | host avail 28.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 3.27 cpu 23.23 | cgroup 10.0G/max oom_kill 0 | free scratch 319.4G/45414660i tmp 29.7G/1019819i workspace 319.4G/45414660i | repeat-01 collected 26/26 workers (60602 items) tests 7592 done 0 failed | 26 in flight, oldest 48s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_archived_plan_reveals_through_path_context_after_scan
................................ [332%]
........................................................................ [336%]
...................................[contention-diag] +1117s soak 38p/266t rss 10.6G pss 9.7G swap 1.6G majflt 14951 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 10 descendant rss 0.1G pss 0.0G | host avail 26.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 3.12 cpu 25.24 | cgroup 10.1G/max oom_kill 0 | free scratch 319.4G/45414238i tmp 29.7G/1019819i workspace 319.4G/45414238i | scratch used 0.4G in 68597 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 7718 done 0 failed | 26 in flight, oldest 45s gw5 tests/ace/tui/test_artifacts_plans_filtering.py::test_changing_project_scope_keeps_idle_plan_bar_in_sync
...........[contention-diag] +1134s soak 38p/265t rss 10.6G pss 9.7G swap 1.6G majflt 15026 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 10 descendant rss 0.1G pss 0.0G | host avail 26.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 1.9 cpu 17.54 | cgroup 10.2G/max oom_kill 0 | free scratch 319.4G/45413992i tmp 29.7G/1019819i workspace 319.4G/45413992i | repeat-01 collected 26/26 workers (60602 items) tests 7750 done 0 failed | 26 in flight, oldest 54s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_for_other_panels_deck_changes_nothing
........[contention-diag] +1150s soak 38p/275t rss 10.6G pss 9.7G swap 1.6G majflt 15087 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 10 descendant rss 0.1G pss 0.0G | host avail 25.5G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.02 io 2.05 cpu 19.66 | cgroup 10.2G/max oom_kill 0 | free scratch 319.4G/45413827i tmp 29.7G/1019819i workspace 319.4G/45413827i | repeat-01 collected 26/26 workers (60602 items) tests 7756 done 0 failed | 26 in flight, oldest 62s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
....[contention-diag] +1165s soak 38p/296t rss 10.6G pss 9.6G swap 1.7G majflt 15119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 10 descendant rss 0.1G pss 0.0G | host avail 24.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.71 cpu 17.62 | cgroup 10.1G/max oom_kill 0 | free scratch 319.4G/45413723i tmp 29.7G/1019820i workspace 319.4G/45413723i | repeat-01 collected 26/26 workers (60602 items) tests 7762 done 0 failed | 26 in flight, oldest 78s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
.............. [339%]
...................................................[contention-diag] +1180s soak 38p/266t rss 10.6G pss 9.7G swap 1.7G majflt 15272 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 10 descendant rss 0.1G pss 0.0G | host avail 25.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 17.46 | cgroup 10.1G/max oom_kill 0 | free scratch 319.4G/45413444i tmp 29.7G/1019820i workspace 319.4G/45413444i | repeat-01 collected 26/26 workers (60602 items) tests 7827 done 0 failed | 26 in flight, oldest 82s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_from_rail_is_flush_and_restores_rail
..................... [342%]
...............[contention-diag] +1196s soak 38p/258t rss 10.6G pss 9.7G swap 1.7G majflt 15325 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 10 descendant rss 0.1G pss 0.0G | host avail 24.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.37 cpu 19.2 | cgroup 10.2G/max oom_kill 0 | free scratch 319.8G/45435049i tmp 29.7G/1019817i workspace 319.8G/45435049i | repeat-01 collected 26/26 workers (60602 items) tests 7861 done 0 failed | 26 in flight, oldest 89s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
......................................................... [345%]
........................................................................ [348%]
..........[contention-diag] +1211s soak 39p/271t rss 10.7G pss 9.7G swap 1.7G majflt 15504 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.6G, 11 descendant rss 0.1G pss 0.1G | host avail 23.3G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.54 cpu 16.62 | cgroup 10.2G/max oom_kill 0 | free scratch 319.5G/45423352i tmp 29.7G/1019815i workspace 319.5G/45423352i | repeat-01 collected 26/26 workers (60602 items) tests 8002 done 0 failed | 26 in flight, oldest 104s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.............................................................. [351%]
...................[contention-diag] +1226s soak 38p/270t rss 10.7G pss 9.7G swap 1.7G majflt 15604 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.6G, 10 descendant rss 0.1G pss 0.0G | host avail 26.1G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.38 cpu 14.17 | cgroup 10.2G/max oom_kill 0 | free scratch 319.2G/45422972i tmp 29.7G/1019815i workspace 319.2G/45422972i | repeat-01 collected 26/26 workers (60602 items) tests 8083 done 0 failed | 26 in flight, oldest 120s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................................................[contention-diag] +1242s soak 28p/244t rss 10.6G pss 9.7G swap 1.6G majflt 15679 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.6G | host avail 28.0G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.93 cpu 25.09 | cgroup 10.2G/max oom_kill 0 | free scratch 319.6G/45422780i tmp 29.7G/1019814i workspace 319.6G/45422780i | scratch used 0.4G in 74898 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 8124 done 0 failed | 26 in flight, oldest 91s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
..... [354%]
.................................................[contention-diag] +1259s soak 28p/249t rss 10.6G pss 9.7G swap 1.6G majflt 15792 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.6G | host avail 27.2G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.02 cpu 20.54 | cgroup 10.3G/max oom_kill 0 | free scratch 319.6G/45422494i tmp 29.7G/1019812i workspace 319.6G/45422494i | repeat-01 collected 26/26 workers (60602 items) tests 8181 done 0 failed | 26 in flight, oldest 78s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
....................... [358%]
........................................................................ [361%]
......................[contention-diag] +1274s soak 28p/233t rss 10.6G pss 9.8G swap 1.6G majflt 15874 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.7G | host avail 29.1G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.42 cpu 25.42 | cgroup 10.3G/max oom_kill 0 | free scratch 319.6G/45422171i tmp 29.7G/1019812i workspace 319.6G/45422171i | repeat-01 collected 26/26 workers (60602 items) tests 8298 done 0 failed | 26 in flight, oldest 45s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................. [364%]
...............................[contention-diag] +1290s soak 30p/243t rss 10.7G pss 9.8G swap 1.6G majflt 15936 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.7G, 2 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.99 cpu 25.58 | cgroup 10.3G/max oom_kill 0 | free scratch 319.6G/45421950i tmp 29.7G/1019809i workspace 319.6G/45421950i | repeat-01 collected 26/26 workers (60602 items) tests 8383 done 0 failed | 26 in flight, oldest 61s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
......................................... [367%]
........................................................................ [370%]
........................................[contention-diag] +1305s soak 29p/263t rss 10.8G pss 9.9G swap 1.6G majflt 16147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.1G pss 0.1G | host avail 25.4G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 4.38 cpu 18.14 | cgroup 10.5G/max oom_kill 0 | free scratch 320.1G/45421442i tmp 29.7G/1019213i workspace 320.1G/45421442i | repeat-01 collected 26/26 workers (60602 items) tests 8529 done 0 failed | 26 in flight, oldest 76s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................ [373%]
........................................................................ [376%]
........................................................................ [380%]
........................................................................ [383%]
........................................................................ [386%]
...........[contention-diag] +1320s soak 29p/233t rss 10.7G pss 9.9G swap 1.6G majflt 16534 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 25.8G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 3.32 cpu 15.35 | cgroup 10.4G/max oom_kill 0 | free scratch 320.0G/45420629i tmp 29.7G/1019116i workspace 320.0G/45420629i | repeat-01 collected 26/26 workers (60602 items) tests 8863 done 0 failed | 26 in flight, oldest 91s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
...............................................[contention-diag] +1336s soak 28p/224t rss 10.8G pss 9.9G swap 1.6G majflt 16575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G | host avail 24.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.05 cpu 15.64 | cgroup 10.4G/max oom_kill 0 | free scratch 320.0G/45420396i tmp 29.7G/1018625i workspace 320.0G/45420396i | repeat-01 collected 26/26 workers (60602 items) tests 8914 done 0 failed | 26 in flight, oldest 107s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............. [389%]
........................................................................ [392%]
...........[contention-diag] +1351s soak 28p/241t rss 10.7G pss 9.9G swap 1.7G majflt 17008 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G | host avail 23.5G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.7 cpu 15.1 | cgroup 10.5G/max oom_kill 0 | free scratch 319.9G/45418366i tmp 29.7G/1018039i workspace 319.9G/45418366i | repeat-01 collected 26/26 workers (60602 items) tests 9002 done 0 failed | 26 in flight, oldest 122s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................................. [395%]
........................................................................ [398%]
.........................................[contention-diag] +1366s soak 29p/267t rss 10.7G pss 9.9G swap 1.7G majflt 17235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 22.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.9/0.48 io 3.74 cpu 14.27 | cgroup 10.3G/max oom_kill 0 | free scratch 319.9G/45417880i tmp 29.7G/1018039i workspace 319.9G/45417880i | scratch used 0.2G in 33260 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 9172 done 0 failed | 25 in flight, oldest 138s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................... [402%]
....................................................[contention-diag] +1384s soak 29p/242t rss 10.8G pss 9.9G swap 1.7G majflt 17441 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.18/0.09 io 3.18 cpu 15.27 | cgroup 10.3G/max oom_kill 0 | free scratch 319.5G/45417552i tmp 29.7G/1018038i workspace 319.5G/45417552i | repeat-01 collected 26/26 workers (60602 items) tests 9254 done 0 failed | 26 in flight, oldest 155s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................... [405%]
...........................................[contention-diag] +1399s soak 28p/259t rss 10.8G pss 9.9G swap 1.7G majflt 17794 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G | host avail 25.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 3.01 cpu 16.04 | cgroup 10.4G/max oom_kill 0 | free scratch 319.5G/45417340i tmp 29.7G/1018038i workspace 319.5G/45417340i | repeat-01 collected 26/26 workers (60602 items) tests 9329 done 0 failed | 26 in flight, oldest 170s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................. [408%]
..[contention-diag] +1414s soak 30p/262t rss 10.8G pss 9.9G swap 1.7G majflt 18027 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G, 2 descendant rss 0.0G pss 0.0G | host avail 22.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.39 cpu 13.95 | cgroup 10.4G/max oom_kill 0 | free scratch 319.5G/45416865i tmp 29.7G/1018038i workspace 319.5G/45416865i | repeat-01 collected 26/26 workers (60602 items) tests 9361 done 0 failed | 26 in flight, oldest 186s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.......................[contention-diag] +1430s soak 28p/259t rss 10.8G pss 9.9G swap 1.7G majflt 18298 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G | host avail 23.8G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.31 cpu 14.07 | cgroup 10.4G/max oom_kill 0 | free scratch 319.5G/45416583i tmp 29.7G/1018038i workspace 319.5G/45416583i | repeat-01 collected 26/26 workers (60602 items) tests 9384 done 0 failed | 26 in flight, oldest 90s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..........................................[contention-diag] +1445s soak 29p/263t rss 10.8G pss 10.0G swap 1.7G majflt 18429 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 22.6G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.89 cpu 13.19 | cgroup 10.4G/max oom_kill 0 | free scratch 319.5G/45416187i tmp 29.7G/1018038i workspace 319.5G/45416187i | repeat-01 collected 26/26 workers (60602 items) tests 9426 done 0 failed | 26 in flight, oldest 106s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..... [411%]
...........................................[contention-diag] +1460s soak 28p/260t rss 10.8G pss 10.0G swap 1.7G majflt 18532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G | host avail 20.5G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 1.88/1.61 io 3.97 cpu 11.28 | cgroup 10.4G/max oom_kill 0 | free scratch 319.4G/45415882i tmp 29.7G/1018038i workspace 319.4G/45415882i | repeat-01 collected 26/26 workers (60602 items) tests 9468 done 0 failed | 25 in flight, oldest 121s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................. [414%]
......................................[contention-diag] +1476s soak 29p/258t rss 10.7G pss 9.8G swap 1.9G majflt 19238 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 24.4G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.59/0.53 io 3.52 cpu 11.78 | cgroup 10.3G/max oom_kill 0 | free scratch 319.3G/45415522i tmp 29.7G/1018035i workspace 319.3G/45415522i | repeat-01 collected 26/26 workers (60602 items) tests 9529 done 0 failed | 26 in flight, oldest 136s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..........................[contention-diag] +1491s soak 28p/243t rss 10.7G pss 9.8G swap 1.9G majflt 19402 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G | host avail 24.5G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.16/0.1 io 2.52 cpu 11.39 | cgroup 10.3G/max oom_kill 0 | free scratch 319.2G/45415265i tmp 29.7G/1018035i workspace 319.2G/45415265i | scratch used 0.3G in 47588 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 9566 done 0 failed | 26 in flight, oldest 152s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
........ [417%]
.................[contention-diag] +1508s soak 29p/238t rss 10.7G pss 9.8G swap 1.9G majflt 19676 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 2.65 cpu 11.15 | cgroup 10.3G/max oom_kill 0 | free scratch 319.1G/45415033i tmp 29.7G/1018035i workspace 319.1G/45415033i | repeat-01 collected 26/26 workers (60602 items) tests 9592 done 0 failed | 26 in flight, oldest 169s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.......................................[contention-diag] +1524s soak 29p/243t rss 10.9G pss 10.0G swap 1.9G majflt 20066 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 1 descendant rss 0.1G pss 0.1G | host avail 24.7G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.48/0.48 io 3.65 cpu 13.1 | cgroup 10.5G/max oom_kill 0 | free scratch 319.0G/45414686i tmp 29.7G/1018035i workspace 319.0G/45414686i | repeat-01 collected 26/26 workers (60602 items) tests 9630 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [420%]
.............................................................[contention-diag] +1539s soak 29p/251t rss 10.8G pss 9.9G swap 1.9G majflt 20209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 26.2G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 2.54 cpu 14.36 | cgroup 10.4G/max oom_kill 0 | free scratch 318.7G/45413925i tmp 29.7G/1018034i workspace 318.7G/45413925i | repeat-01 collected 26/26 workers (60602 items) tests 9708 done 0 failed | 26 in flight, oldest 83s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........... [424%]
...................................................................[contention-diag] +1554s soak 29p/254t rss 10.8G pss 9.9G swap 1.9G majflt 20338 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 24.5G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.09 cpu 13.64 | cgroup 10.5G/max oom_kill 0 | free scratch 318.7G/45413488i tmp 29.7G/1018034i workspace 318.7G/45413488i | repeat-01 collected 26/26 workers (60602 items) tests 9771 done 0 failed | 25 in flight, oldest 99s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..... [427%]
........................................................................ [430%]
........................................................................ [433%]
........................................................................ [436%]
...[contention-diag] +1570s soak 29p/253t rss 10.8G pss 9.9G swap 1.9G majflt 20515 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 25.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.0 io 3.29 cpu 15.51 | cgroup 10.5G/max oom_kill 0 | free scratch 318.7G/45412991i tmp 29.7G/1018032i workspace 318.7G/45412991i | repeat-01 collected 26/26 workers (60602 items) tests 10008 done 0 failed | 26 in flight, oldest 114s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..........................................[contention-diag] +1585s soak 28p/259t rss 10.8G pss 9.9G swap 1.9G majflt 20767 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G | host avail 25.7G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 2.25 cpu 12.07 | cgroup 10.5G/max oom_kill 0 | free scratch 318.5G/45411027i tmp 29.7G/1018034i workspace 318.5G/45411027i | repeat-01 collected 26/26 workers (60602 items) tests 10050 done 0 failed | 26 in flight, oldest 129s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................... [439%]
...................................................................[contention-diag] +1600s soak 29p/253t rss 10.9G pss 10.0G swap 1.9G majflt 21360 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 32.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.48 cpu 14.0 | cgroup 10.5G/max oom_kill 0 | free scratch 318.4G/45411319i tmp 29.7G/1018034i workspace 318.4G/45411319i | repeat-01 collected 26/26 workers (60602 items) tests 10146 done 0 failed | 26 in flight, oldest 145s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..... [442%]
.......................[contention-diag] +1617s soak 28p/281t rss 10.9G pss 10.0G swap 1.8G majflt 21731 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G | host avail 29.6G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.1/0.0 io 4.19 cpu 13.81 | cgroup 10.6G/max oom_kill 0 | free scratch 318.1G/45383360i tmp 29.7G/1017516i workspace 318.1G/45383361i | scratch used 0.3G in 51403 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 10174 done 0 failed | 26 in flight, oldest 161s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................[contention-diag] +1634s soak 28p/285t rss 10.9G pss 10.0G swap 1.8G majflt 21848 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G | host avail 29.6G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 4.5 cpu 11.1 | cgroup 10.6G/max oom_kill 0 | free scratch 318.1G/45383233i tmp 29.7G/1017978i workspace 318.1G/45383233i | repeat-01 collected 26/26 workers (60602 items) tests 10207 done 0 failed | 26 in flight, oldest 178s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............... [446%]
.....................[contention-diag] +1649s soak 29p/268t rss 10.9G pss 10.0G swap 1.8G majflt 21906 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G, 1 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.22 cpu 12.85 | cgroup 10.6G/max oom_kill 0 | free scratch 318.1G/45382936i tmp 29.7G/1017978i workspace 318.1G/45382936i | repeat-01 collected 26/26 workers (60602 items) tests 10242 done 0 failed | 26 in flight, oldest 194s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................... [449%]
....................................[contention-diag] +1665s soak 28p/261t rss 10.9G pss 10.0G swap 1.8G majflt 22192 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G | host avail 30.6G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.58 cpu 15.37 | cgroup 10.6G/max oom_kill 0 | free scratch 318.1G/45382536i tmp 29.7G/1017978i workspace 318.1G/45382536i | repeat-01 collected 26/26 workers (60602 items) tests 10331 done 0 failed | 26 in flight, oldest 209s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................... [452%]
....................................[contention-diag] +1680s soak 28p/284t rss 10.9G pss 10.0G swap 1.8G majflt 22312 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G | host avail 30.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.07 cpu 16.07 | cgroup 10.7G/max oom_kill 0 | free scratch 318.1G/45382642i tmp 29.7G/1018004i workspace 318.1G/45382642i | repeat-01 collected 26/26 workers (60602 items) tests 10399 done 0 failed | 26 in flight, oldest 224s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................... [455%]
......................................................[contention-diag] +1695s soak 28p/254t rss 11.0G pss 10.1G swap 1.8G majflt 22634 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G | host avail 28.1G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.02 cpu 12.62 | cgroup 10.7G/max oom_kill 0 | free scratch 318.1G/45382452i tmp 29.7G/1018006i workspace 318.1G/45382452i | repeat-01 collected 26/26 workers (60602 items) tests 10493 done 0 failed | 26 in flight, oldest 240s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [458%]
.....................................[contention-diag] +1710s soak 29p/267t rss 11.0G pss 10.1G swap 1.8G majflt 23134 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 2.6 cpu 15.16 | cgroup 10.8G/max oom_kill 0 | free scratch 318.1G/45381351i tmp 29.7G/1018006i workspace 318.1G/45381351i | repeat-01 collected 26/26 workers (60602 items) tests 10547 done 0 failed | 26 in flight, oldest 255s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................... [461%]
...................................[contention-diag] +1726s soak 28p/282t rss 11.0G pss 10.1G swap 1.8G majflt 23492 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G | host avail 31.3G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.25 cpu 22.35 | cgroup 10.7G/max oom_kill 0 | free scratch 318.1G/45381966i tmp 29.7G/1018006i workspace 318.1G/45381966i | repeat-01 collected 26/26 workers (60602 items) tests 10618 done 0 failed | 26 in flight, oldest 270s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................[contention-diag] +1741s soak 28p/279t rss 11.0G pss 10.1G swap 1.8G majflt 23800 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G | host avail 30.8G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.23 cpu 22.87 | cgroup 10.7G/max oom_kill 0 | free scratch 318.1G/45381831i tmp 29.7G/1018007i workspace 318.1G/45381831i | scratch used 0.5G in 89375 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 10642 done 0 failed | 26 in flight, oldest 285s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......... [464%]
........................................................................ [468%]
..........................................[contention-diag] +1758s soak 30p/255t rss 11.0G pss 10.1G swap 1.8G majflt 23916 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 2 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 21.49 | cgroup 10.8G/max oom_kill 0 | free scratch 318.1G/45381370i tmp 29.7G/1018007i workspace 318.1G/45381370i | repeat-01 collected 26/26 workers (60602 items) tests 10762 done 0 failed | 26 in flight, oldest 303s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................. [471%]
............................[contention-diag] +1774s soak 28p/260t rss 11.0G pss 10.1G swap 1.8G majflt 24171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G | host avail 31.0G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.18/0.0 io 0.15 cpu 26.14 | cgroup 10.8G/max oom_kill 0 | free scratch 318.1G/45380970i tmp 29.7G/1018007i workspace 318.1G/45380970i | repeat-01 collected 26/26 workers (60602 items) tests 10819 done 0 failed | 26 in flight, oldest 318s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................ [474%]
........................................................................ [477%]
........................................................[contention-diag] +1789s soak 28p/275t rss 11.0G pss 10.1G swap 1.8G majflt 24621 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.1G | host avail 30.5G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.11/0.0 io 0.11 cpu 26.77 | cgroup 10.8G/max oom_kill 0 | free scratch 318.1G/45380649i tmp 29.7G/1018005i workspace 318.1G/45380649i | repeat-01 collected 26/26 workers (60602 items) tests 10999 done 0 failed | 26 in flight, oldest 333s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [480%]
........................................................................ [483%]
.....................................................[contention-diag] +1804s soak 31p/280t rss 11.2G pss 10.1G swap 1.8G majflt 24880 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 3 descendant rss 0.1G pss 0.0G | host avail 28.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.12 cpu 25.17 | cgroup 10.9G/max oom_kill 0 | free scratch 318.1G/45380188i tmp 29.7G/1018005i workspace 318.1G/45380188i | repeat-01 collected 26/26 workers (60602 items) tests 11121 done 0 failed | 25 in flight, oldest 61s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
................... [486%]
........................................................................ [490%]
...............................[contention-diag] +1820s soak 31p/282t rss 11.1G pss 10.2G swap 1.7G majflt 32677 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 3 descendant rss 0.0G pss 0.0G | host avail 29.0G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 2.25/0.0 io 0.12 cpu 22.23 | cgroup 10.9G/max oom_kill 0 | free scratch 318.1G/45379825i tmp 29.7G/1018004i workspace 318.1G/45379825i | repeat-01 collected 26/26 workers (60602 items) tests 11261 done 0 failed | 25 in flight, oldest 76s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
......................................... [493%]
...............................................................[contention-diag] +1835s soak 30p/250t rss 11.1G pss 10.2G swap 1.7G majflt 33064 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 2 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.45/0.0 io 0.35 cpu 22.51 | cgroup 10.8G/max oom_kill 0 | free scratch 317.9G/45368942i tmp 29.7G/1018003i workspace 317.9G/45368942i | repeat-01 collected 26/26 workers (60602 items) tests 11365 done 0 failed | 26 in flight, oldest 57s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
......... [496%]
...............................................[contention-diag] +1850s soak 30p/262t rss 11.2G pss 10.3G swap 1.7G majflt 33556 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 2 descendant rss 0.0G pss 0.0G | host avail 30.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.11/0.0 io 0.08 cpu 18.73 | cgroup 11.0G/max oom_kill 0 | free scratch 317.9G/45368732i tmp 29.7G/1018003i workspace 317.9G/45368732i | repeat-01 collected 26/26 workers (60602 items) tests 11419 done 0 failed | 26 in flight, oldest 72s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
......................... [499%]
...........................................[contention-diag] +1866s soak 29p/245t rss 11.2G pss 10.3G swap 1.7G majflt 33761 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.19 cpu 15.92 | cgroup 11.0G/max oom_kill 0 | free scratch 317.9G/45368425i tmp 29.7G/1018003i workspace 317.9G/45368425i | scratch used 0.4G in 72751 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 11486 done 0 failed | 26 in flight, oldest 46s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_preview_back_retains_sparse_draft_and_running_primary_restarts
............................. [502%]
........................................................................ [505%]
...............[contention-diag] +1883s soak 28p/254t rss 11.2G pss 10.3G swap 1.7G majflt 34135 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 27.1G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.59 cpu 17.59 | cgroup 11.0G/max oom_kill 0 | free scratch 317.9G/45367989i tmp 29.7G/1018003i workspace 317.9G/45367989i | repeat-01 collected 26/26 workers (60602 items) tests 11607 done 0 failed | 26 in flight, oldest 53s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
......................................................... [508%]
........................................................................ [512%]
........[contention-diag] +1899s soak 29p/252t rss 11.2G pss 10.3G swap 1.7G majflt 34373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.14 cpu 19.63 | cgroup 11.0G/max oom_kill 0 | free scratch 317.8G/45367367i tmp 29.7G/1018003i workspace 317.8G/45367367i | repeat-01 collected 26/26 workers (60602 items) tests 11736 done 0 failed | 26 in flight, oldest 47s gw23 tests/ace/tui/test_feature_flags_pane_journeys.py::test_toggle_commits_saved_state_before_restart_runs
.................................................[contention-diag] +1914s soak 34p/267t rss 11.2G pss 10.3G swap 1.7G majflt 34465 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 6 descendant rss 0.1G pss 0.0G | host avail 25.9G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.01 io 0.26 cpu 19.65 | cgroup 10.8G/max oom_kill 0 | free scratch 317.8G/45367236i tmp 29.7G/1018003i workspace 317.8G/45367236i | repeat-01 collected 26/26 workers (60602 items) tests 11793 done 0 failed | 26 in flight, oldest 51s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_enter_loads_raw_definition_and_binds_source
............... [515%]
........................................................................ [518%]
.............[contention-diag] +1929s soak 30p/259t rss 11.1G pss 10.2G swap 1.7G majflt 34581 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 2 descendant rss 0.0G pss 0.0G | host avail 24.9G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.11/0.0 io 1.82 cpu 17.26 | cgroup 10.7G/max oom_kill 0 | free scratch 317.6G/45366470i tmp 29.7G/1018003i workspace 317.6G/45366470i | repeat-01 collected 26/26 workers (60602 items) tests 11892 done 0 failed | 26 in flight, oldest 60s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
....................................[contention-diag] +1945s soak 31p/265t rss 11.3G pss 10.3G swap 1.8G majflt 34961 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 3 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.12 io 0.67 cpu 14.79 | cgroup 10.8G/max oom_kill 0 | free scratch 318.2G/45366322i tmp 29.7G/1018003i workspace 318.2G/45366322i | repeat-01 collected 26/26 workers (60602 items) tests 11927 done 0 failed | 26 in flight, oldest 75s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
......................F [521%]
[contention-failure] call tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fad21b285c0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw6/test_gated_muse_stream_reaches0')

    @pytest.mark.asyncio
    async def test_gated_muse_stream_reaches_mounted_session_current_turn_reply(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        container, _old, current = _build_mounted_session_agents(tmp_path)
        stream_dir = Path(current.artifacts_dir or "")
        monkeypatch.setenv("SASE_ARTIFACTS_DIR", str(stream_dir))
        patch_startup_loaders(monkeypatch, agents=[container])
    
        async with AcePage(
            query='"sess-stream"',
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
            await page.press("j")
            await wait_for_visual_idle(page)
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await wait_for_page(
                page,
                lambda: panel._live_reply_source is not None,
                "selected live reply source setup",
            )
            assert panel._live_reply_source is not None
            assert panel._live_reply_source.reply_identity == current.identity
>           await exercise_gated_stream(
                page,
                panel,
                monkeypatch,
                tmp_path,
                stream_dir,
                expected_identity=current.identity,
                expected_dir=stream_dir,
                # Session Reply cards also render per-turn phase dividers that
                # match the timestamp-divider pattern, so exact divider counts
                # are asserted on the single-agent shapes above. Here the
                # older/newer text singleton counts prove clean concatenation.
                expected_dividers=None,
                old_text="older completed turn text",
            )

tests/ace/tui/test_live_reply_follow_mounted_session.py:143: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fac871804d0>
panel = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fad21b285c0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw6/test_gated_muse_stream_reaches0')
stream_dir = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw6/test_gated_muse_stream_reaches0/sess/current')

    async def exercise_gated_stream(
        page: AcePage,
        panel: AgentPromptPanel,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        stream_dir: Path,
        *,
        expected_identity: Any,
        expected_dir: 
................[contention-diag] +1960s soak 30p/277t rss 11.3G pss 10.3G swap 1.7G majflt 35191 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 2 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.55 cpu 17.21 | cgroup 10.8G/max oom_kill 0 | free scratch 318.2G/45366240i tmp 29.7G/1018003i workspace 318.2G/45366240i | repeat-01 collected 26/26 workers (60602 items) tests 11965 done 1 failed | 26 in flight, oldest 90s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
........................................................ [524%]
........................................................................ [527%]
............................................................[contention-diag] +1975s soak 31p/254t rss 11.3G pss 10.3G swap 1.7G majflt 36095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 3 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.18 cpu 20.29 | cgroup 11.0G/max oom_kill 0 | free scratch 318.2G/45365447i tmp 29.7G/1018003i workspace 318.2G/45365447i | repeat-01 collected 26/26 workers (60602 items) tests 12154 done 1 failed | 26 in flight, oldest 57s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
............ [530%]
........................................................................ [534%]
........................................................................ [537%]
..............[contention-diag] +1990s soak 29p/236t rss 11.3G pss 10.3G swap 1.7G majflt 36344 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 28.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.26 cpu 21.81 | cgroup 10.9G/max oom_kill 0 | free scratch 318.2G/45365207i tmp 29.7G/1018003i workspace 318.2G/45365207i | scratch used 0.3G in 58123 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 12288 done 1 failed | 26 in flight, oldest 48s gw9 tests/ace/tui/test_projects_pane.py::test_projects_session_round_trips_current_project_display
.......................................................... [540%]
..[contention-diag] +2008s soak 30p/235t rss 11.3G pss 10.4G swap 1.7G majflt 36528 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 2 descendant rss 0.1G pss 0.0G | host avail 24.8G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 19.06 | cgroup 11.0G/max oom_kill 0 | free scratch 318.2G/45364911i tmp 29.7G/1018003i workspace 318.2G/45364911i | repeat-01 collected 26/26 workers (60602 items) tests 12384 done 1 failed | 26 in flight, oldest 38s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_is_inert_for_yaml_backed_rows
...............................................................[contention-diag] +2023s soak 30p/245t rss 11.3G pss 10.4G swap 1.7G majflt 36691 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 2 descendant rss 0.1G pss 0.0G | host avail 26.7G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.87 cpu 17.16 | cgroup 11.0G/max oom_kill 0 | free scratch 317.9G/45364682i tmp 29.7G/1018002i workspace 317.9G/45364682i | repeat-01 collected 26/26 workers (60602 items) tests 12445 done 1 failed | 25 in flight, oldest 53s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
....... [543%]
........................................................................ [546%]
........................................................................ [549%]
......................................................................[contention-diag] +2039s soak 28p/245t rss 11.3G pss 10.3G swap 1.7G majflt 37297 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G | host avail 28.9G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 17.43 | cgroup 11.0G/max oom_kill 0 | free scratch 317.7G/45364249i tmp 29.7G/1018002i workspace 317.7G/45364249i | repeat-01 collected 26/26 workers (60602 items) tests 12666 done 1 failed | 26 in flight, oldest 47s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_all_skipped_toasts_reasons_and_cleans_up
.. [552%]
........................................................................ [556%]
........................................................................ [559%]
..............[contention-diag] +2054s soak 29p/237t rss 11.4G pss 10.4G swap 1.6G majflt 37949 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.6 cpu 16.46 | cgroup 11.0G/max oom_kill 0 | free scratch 317.7G/45362261i tmp 29.7G/1017982i workspace 317.7G/45362261i | repeat-01 collected 26/26 workers (60602 items) tests 12821 done 1 failed | 26 in flight, oldest 47s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_core_panel_drops_cta_when_not_uv_tool
.......................................................... [562%]
.............................................................[contention-diag] +2069s soak 29p/278t rss 11.3G pss 10.4G swap 1.6G majflt 38437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 29.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.79 cpu 17.53 | cgroup 11.0G/max oom_kill 0 | free scratch 317.7G/45361749i tmp 29.7G/1018001i workspace 317.7G/45361749i | repeat-01 collected 26/26 workers (60602 items) tests 12934 done 1 failed | 25 in flight, oldest 54s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_tab_switches_admin_center_tab_on_eligible_row
........... [565%]
........................................................................ [568%]
...................................................................[contention-diag] +2085s soak 32p/277t rss 11.4G pss 10.4G swap 1.6G majflt 39411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 4 descendant rss 0.0G pss 0.0G | host avail 25.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.2 cpu 17.37 | cgroup 11.1G/max oom_kill 0 | free scratch 317.7G/45360720i tmp 29.7G/1018002i workspace 317.7G/45360720i | repeat-01 collected 26/26 workers (60602 items) tests 13097 done 1 failed | 26 in flight, oldest 55s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
..... [571%]
........................................................................ [574%]
........................................................................ [578%]
........................................................................ [581%]
............................[contention-diag] +2100s soak 30p/250t rss 11.5G pss 10.5G swap 1.6G majflt 40301 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 2 descendant rss 0.1G pss 0.1G | host avail 25.7G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.94 cpu 19.41 | cgroup 11.1G/max oom_kill 0 | free scratch 317.1G/45358643i tmp 29.7G/1018002i workspace 317.1G/45358643i | repeat-01 collected 26/26 workers (60602 items) tests 13337 done 1 failed | 26 in flight, oldest 63s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
............................................ [584%]
........................................................................ [587%]
.........................................[contention-diag] +2116s soak 32p/255t rss 11.5G pss 10.6G swap 1.6G majflt 41485 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 4 descendant rss 0.1G pss 0.1G | host avail 26.1G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.38 cpu 18.75 | cgroup 11.3G/max oom_kill 0 | free scratch 318.0G/45358834i tmp 29.7G/1018001i workspace 318.0G/45358834i | scratch used 0.5G in 82466 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 13501 done 1 failed | 26 in flight, oldest 44s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_shift_tab_switches_admin_center_tab_on_yaml_backed_row
....................[contention-diag] +2133s soak 34p/266t rss 11.5G pss 10.5G swap 1.6G majflt 40506 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 6 descendant rss 0.1G pss 0.1G | host avail 27.9G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.94 cpu 17.96 | cgroup 11.4G/max oom_kill 0 | free scratch 317.7G/45355427i tmp 29.7G/1018001i workspace 317.7G/45355427i | repeat-01 collected 26/26 workers (60602 items) tests 13524 done 1 failed | 26 in flight, oldest 59s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
........... [590%]
...................[contention-diag] +2148s soak 35p/279t rss 11.6G pss 10.7G swap 1.6G majflt 40823 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 7 descendant rss 0.2G pss 0.2G | host avail 28.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 14.08 | cgroup 11.4G/max oom_kill 0 | free scratch 317.8G/45357299i tmp 29.7G/1018001i workspace 317.8G/45357299i | repeat-01 collected 26/26 workers (60602 items) tests 13550 done 1 failed | 26 in flight, oldest 53s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
..................................................... [593%]
........................[contention-diag] +2164s soak 33p/277t rss 11.5G pss 10.5G swap 1.6G majflt 41047 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 5 descendant rss 0.1G pss 0.0G | host avail 28.5G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.73 cpu 14.45 | cgroup 11.4G/max oom_kill 0 | free scratch 317.7G/45333493i tmp 29.7G/1017523i workspace 317.7G/45333494i | repeat-01 collected 26/26 workers (60602 items) tests 13631 done 1 failed | 26 in flight, oldest 68s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
..........................................[contention-diag] +2179s soak 31p/243t rss 11.5G pss 10.5G swap 1.6G majflt 41113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 3 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.58/0.46 io 5.93 cpu 12.54 | cgroup 11.5G/max oom_kill 0 | free scratch 317.5G/45328957i tmp 29.7G/1017875i workspace 317.5G/45328957i | repeat-01 collected 26/26 workers (60602 items) tests 13666 done 1 failed | 26 in flight, oldest 84s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
...... [596%]
........................................................................ [600%]
...........................................[contention-diag] +2194s soak 35p/254t rss 11.5G pss 10.5G swap 1.6G majflt 41190 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 7 descendant rss 0.0G pss 0.0G | host avail 28.7G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.11/0.09 io 2.09 cpu 19.48 | cgroup 11.5G/max oom_kill 0 | free scratch 317.5G/45327535i tmp 29.7G/1017942i workspace 317.5G/45327535i | repeat-01 collected 26/26 workers (60602 items) tests 13787 done 1 failed | 26 in flight, oldest 99s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................. [603%]
..........................................................[contention-diag] +2210s soak 28p/246t rss 11.5G pss 10.5G swap 1.6G majflt 41547 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G | host avail 28.6G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.5/0.18 io 1.0 cpu 22.84 | cgroup 11.4G/max oom_kill 0 | free scratch 317.5G/45327223i tmp 29.7G/1017943i workspace 317.5G/45327223i | repeat-01 collected 26/26 workers (60602 items) tests 13880 done 1 failed | 26 in flight, oldest 114s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.............. [606%]
........................................................................ [609%]
..........................[contention-diag] +2225s soak 31p/246t rss 11.5G pss 10.6G swap 1.6G majflt 41739 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 3 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.47/0.03 io 0.38 cpu 31.7 | cgroup 11.5G/max oom_kill 0 | free scratch 317.4G/45326733i tmp 29.7G/1017943i workspace 317.4G/45326733i | repeat-01 collected 26/26 workers (60602 items) tests 13982 done 1 failed | 26 in flight, oldest 70s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[p-sase-SASE]
.............................................. [612%]
................................[contention-diag] +2240s soak 31p/262t rss 11.5G pss 10.6G swap 1.6G majflt 41803 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 3 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.09/0.0 io 0.07 cpu 20.72 | cgroup 11.5G/max oom_kill 0 | free scratch 317.4G/45325889i tmp 29.7G/1017970i workspace 317.4G/45325889i | scratch used 0.2G in 28239 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 14065 done 1 failed | 26 in flight, oldest 40s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
........................................ [615%]
........................................................................ [618%]
.......................................[contention-diag] +2258s soak 33p/271t rss 11.6G pss 10.5G swap 1.6G majflt 41886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 5 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.19 cpu 15.87 | cgroup 11.5G/max oom_kill 0 | free scratch 317.3G/45325661i tmp 29.7G/1017970i workspace 317.3G/45325661i | repeat-01 collected 26/26 workers (60602 items) tests 14218 done 1 failed | 26 in flight, oldest 57s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
................................. [621%]
........................................................................ [625%]
........................................................................ [628%]
................................................[contention-diag] +2273s soak 33p/258t rss 11.7G pss 10.7G swap 1.6G majflt 42234 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 5 descendant rss 0.1G pss 0.1G | host avail 25.5G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 11.62 | cgroup 11.6G/max oom_kill 0 | free scratch 316.7G/45323578i tmp 29.7G/1017970i workspace 316.7G/45323578i | repeat-01 collected 26/26 workers (60602 items) tests 14442 done 1 failed | 26 in flight, oldest 72s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
........................ [631%]
........................................................................ [634%]
........................................................................ [637%]
........................................................................ [640%]
...............[contention-diag] +2288s soak 33p/253t rss 11.6G pss 10.7G swap 1.6G majflt 42559 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 5 descendant rss 0.0G pss 0.0G | host avail 26.1G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 22.69 | cgroup 11.7G/max oom_kill 0 | free scratch 316.7G/45322948i tmp 29.7G/1017970i workspace 316.7G/45322948i | repeat-01 collected 26/26 workers (60602 items) tests 14682 done 1 failed | 26 in flight, oldest 34s gw2 tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_managed_confirm_closes_admin_center
......................................................... [643%]
........................................................................ [647%]
..................[contention-diag] +2304s soak 32p/264t rss 11.6G pss 10.7G swap 1.5G majflt 43263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 4 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 23.86 | cgroup 11.6G/max oom_kill 0 | free scratch 316.7G/45321893i tmp 29.7G/1017970i workspace 316.7G/45321893i | repeat-01 collected 26/26 workers (60602 items) tests 14836 done 1 failed | 26 in flight, oldest 48s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_filter_types_brackets_and_tab_switches_main_tab
...................................................... [650%]
........................................................................ [653%]
.....................................[contention-diag] +2319s soak 31p/254t rss 11.7G pss 10.7G swap 1.5G majflt 43411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 3 descendant rss 0.0G pss 0.0G | host avail 25.0G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 21.44 | cgroup 11.6G/max oom_kill 0 | free scratch 316.7G/45321133i tmp 29.7G/1017970i workspace 316.7G/45321133i | repeat-01 collected 26/26 workers (60602 items) tests 15011 done 1 failed | 26 in flight, oldest 48s gw23 tests/ace/tui/test_notification_jump_to_agent_reveal.py::test_real_app_notification_jump_expands_collapsed_clan
................................... [656%]
........................................................................ [659%]
...........................................[contention-diag] +2334s soak 32p/247t rss 11.7G pss 10.7G swap 1.6G majflt 43648 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 4 descendant rss 0.1G pss 0.1G | host avail 23.6G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 19.8 | cgroup 11.6G/max oom_kill 0 | free scratch 316.7G/45320172i tmp 29.7G/1017970i workspace 316.7G/45320172i | repeat-01 collected 26/26 workers (60602 items) tests 15153 done 1 failed | 26 in flight, oldest 57s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
............................. [662%]
........................................................................ [665%]
........................................................................ [669%]
..[contention-diag] +2349s soak 31p/254t rss 11.7G pss 10.7G swap 1.6G majflt 44069 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.6G, 3 descendant rss 0.1G pss 0.0G | host avail 29.6G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 19.13 | cgroup 11.7G/max oom_kill 0 | free scratch 316.7G/45319448i tmp 29.7G/1017970i workspace 316.7G/45319448i | repeat-01 collected 26/26 workers (60602 items) tests 15334 done 1 failed | 26 in flight, oldest 73s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
...................................................................... [672%]
........................................................................ [675%]
........................................................................ [678%]
.......................[contention-diag] +2365s soak 30p/240t rss 11.7G pss 10.7G swap 1.6G majflt 44138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 15.57 | cgroup 11.6G/max oom_kill 0 | free scratch 316.7G/45318557i tmp 29.7G/1017966i workspace 316.7G/45318557i | scratch used 0.3G in 58565 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 15551 done 1 failed | 26 in flight, oldest 73s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................. [681%]
........................................................................ [684%]
..................................[contention-diag] +2382s soak 30p/253t rss 11.7G pss 10.7G swap 1.6G majflt 44235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 26.6G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 17.08 | cgroup 11.7G/max oom_kill 0 | free scratch 316.6G/45317747i tmp 29.7G/1017966i workspace 316.6G/45317747i | repeat-01 collected 26/26 workers (60602 items) tests 15719 done 1 failed | 26 in flight, oldest 90s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................................... [687%]
........................................................................ [691%]
........................................................................ [694%]
[contention-diag] +2397s soak 34p/278t rss 11.8G pss 10.8G swap 1.6G majflt 44370 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 6 descendant rss 0.1G pss 0.0G | host avail 27.0G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 22.83 | cgroup 11.8G/max oom_kill 0 | free scratch 316.6G/45316789i tmp 29.7G/1017966i workspace 316.6G/45316789i | repeat-01 collected 26/26 workers (60602 items) tests 15894 done 1 failed | 26 in flight, oldest 106s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................................................ [697%]
........................................................................ [700%]
..[contention-diag] +2413s soak 34p/262t rss 11.9G pss 10.9G swap 1.6G majflt 44612 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 6 descendant rss 0.2G pss 0.1G | host avail 23.8G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 24.5 | cgroup 11.9G/max oom_kill 0 | free scratch 316.6G/45315936i tmp 29.7G/1017966i workspace 316.6G/45315936i | repeat-01 collected 26/26 workers (60602 items) tests 16055 done 1 failed | 26 in flight, oldest 121s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................................................................... [703%]
........................................................................ [706%]
....................................................[contention-diag] +2428s soak 34p/245t rss 11.9G pss 10.9G swap 1.6G majflt 44730 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 6 descendant rss 0.1G pss 0.1G | host avail 23.3G/62.7G swapfree 55.9G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.48 cpu 23.65 | cgroup 12.0G/max oom_kill 0 | free scratch 316.4G/45314945i tmp 29.7G/1017966i workspace 316.4G/45314945i | repeat-01 collected 26/26 workers (60602 items) tests 16244 done 1 failed | 26 in flight, oldest 136s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................... [709%]
........................................................................ [713%]
........................................................................ [716%]
........................................................................ [719%]
................[contention-diag] +2443s soak 32p/261t rss 11.9G pss 10.9G swap 1.6G majflt 44889 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 4 descendant rss 0.1G pss 0.1G | host avail 22.5G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 1.1 cpu 19.56 | cgroup 11.9G/max oom_kill 0 | free scratch 316.6G/45314139i tmp 29.7G/1017966i workspace 316.6G/45314139i | repeat-01 collected 26/26 workers (60602 items) tests 16500 done 1 failed | 26 in flight, oldest 152s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................................ [722%]
........................................................................ [725%]
........................................................................ [728%]
........................................................................ [731%]
.......................[contention-diag] +2459s soak 34p/278t rss 11.9G pss 10.9G swap 1.5G majflt 45406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 6 descendant rss 0.1G pss 0.1G | host avail 24.1G/62.7G swapfree 55.7G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.75 cpu 17.65 | cgroup 11.9G/max oom_kill 0 | free scratch 316.2G/45315794i tmp 29.7G/1017966i workspace 316.2G/45315794i | repeat-01 collected 26/26 workers (60602 items) tests 16775 done 1 failed | 26 in flight, oldest 74s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
................................................. [735%]
........................................................................ [738%]
..........[contention-diag] +2474s soak 35p/282t rss 12.0G pss 11.0G swap 1.5G majflt 45670 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 7 descendant rss 0.1G pss 0.1G | host avail 29.4G/62.7G swapfree 55.7G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.33 cpu 20.36 | cgroup 11.9G/max oom_kill 0 | free scratch 316.3G/45314985i tmp 29.7G/1017966i workspace 316.3G/45314985i | repeat-01 collected 26/26 workers (60602 items) tests 16930 done 1 failed | 26 in flight, oldest 89s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.............................................................. [741%]
........................................................................ [744%]
........................................................................ [747%]
..........................[contention-diag] +2489s soak 33p/274t rss 12.1G pss 11.0G swap 1.5G majflt 46092 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 5 descendant rss 0.2G pss 0.2G | host avail 27.9G/62.7G swapfree 55.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 18.33 | cgroup 12.1G/max oom_kill 0 | free scratch 316.3G/45314557i tmp 29.7G/1017966i workspace 316.3G/45314557i | scratch used 0.5G in 87771 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 17127 done 1 failed | 26 in flight, oldest 104s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.............................................. [750%]
........................................................................ [753%]
........................................................................ [757%]
........................................................................ [760%]
.....[contention-diag] +2507s soak 32p/252t rss 11.9G pss 10.9G swap 1.5G majflt 46442 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 4 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.36 cpu 18.69 | cgroup 12.0G/max oom_kill 0 | free scratch 318.7G/45396403i tmp 29.7G/1017966i workspace 318.7G/45396403i | repeat-01 collected 26/26 workers (60602 items) tests 17424 done 1 failed | 26 in flight, oldest 122s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
................................................................... [763%]
........................................................................ [766%]
........................................................................ [769%]
.........................[contention-diag] +2522s soak 32p/225t rss 12.0G pss 10.9G swap 1.5G majflt 46522 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 4 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 56.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 17.52 | cgroup 12.1G/max oom_kill 0 | free scratch 322.3G/45397068i tmp 29.7G/1017966i workspace 322.3G/45397068i | repeat-01 collected 26/26 workers (60602 items) tests 17657 done 1 failed | 26 in flight, oldest 107s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
............................................... [772%]
........................................................................ [775%]
........................................................................ [779%]
..........................................................[contention-diag] +2537s soak 31p/248t rss 11.9G pss 10.9G swap 1.5G majflt 46777 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 56.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.69 cpu 17.19 | cgroup 12.0G/max oom_kill 0 | free scratch 322.4G/45396356i tmp 29.7G/1017966i workspace 322.4G/45396356i | repeat-01 collected 26/26 workers (60602 items) tests 17910 done 1 failed | 26 in flight, oldest 123s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.............. [782%]
........................................................................ [785%]
........................................................................ [788%]
.....................................................[contention-diag] +2553s soak 34p/259t rss 11.9G pss 10.9G swap 1.5G majflt 47333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 6 descendant rss 0.0G pss 0.0G | host avail 27.6G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.41/0.0 io 0.48 cpu 17.85 | cgroup 12.0G/max oom_kill 0 | free scratch 322.1G/45395788i tmp 29.7G/1017966i workspace 322.1G/45395788i | repeat-01 collected 26/26 workers (60602 items) tests 18105 done 1 failed | 26 in flight, oldest 50s gw21 tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
................... [791%]
........................................................................ [794%]
.......................................................[contention-diag] +2568s soak 38p/249t rss 12.1G pss 11.1G swap 1.5G majflt 47417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 10 descendant rss 0.1G pss 0.1G | host avail 25.9G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.1/0.0 io 1.64 cpu 17.88 | cgroup 12.1G/max oom_kill 0 | free scratch 322.3G/45394849i tmp 29.7G/1017964i workspace 322.3G/45394849i | repeat-01 collected 26/26 workers (60602 items) tests 18263 done 1 failed | 26 in flight, oldest 61s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
................. [797%]
........................................................................ [801%]
................[contention-diag] +2583s soak 37p/233t rss 12.1G pss 11.0G swap 1.5G majflt 47489 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 9 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.15/0.13 io 2.23 cpu 18.29 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45393752i tmp 29.7G/1017964i workspace 322.3G/45393752i | repeat-01 collected 26/26 workers (60602 items) tests 18360 done 1 failed | 26 in flight, oldest 76s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
........................................................ [804%]
........................................................................ [807%]
........................................................................ [810%]
........................................................................ [813%]
.........................[contention-diag] +2599s soak 38p/238t rss 12.1G pss 11.1G swap 1.5G majflt 47575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 10 descendant rss 0.1G pss 0.1G | host avail 25.9G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 0.71 cpu 21.63 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45393144i tmp 29.7G/1017964i workspace 322.3G/45393144i | repeat-01 collected 26/26 workers (60602 items) tests 18661 done 1 failed | 25 in flight, oldest 57s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................... [816%]
........................................................................ [819%]
........................................................................ [823%]
........................................................................ [826%]
..........................[contention-diag] +2614s soak 33p/244t rss 12.1G pss 11.1G swap 1.5G majflt 47799 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 5 descendant rss 0.1G pss 0.0G | host avail 24.2G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.95 cpu 20.9 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45392565i tmp 29.7G/1017964i workspace 322.3G/45392565i | scratch used 0.6G in 106036 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 18935 done 1 failed | 26 in flight, oldest 72s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.............................................. [829%]
........................................................................ [832%]
........................................................................ [835%]
.....[contention-diag] +2631s soak 33p/247t rss 12.1G pss 11.1G swap 1.5G majflt 47861 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 5 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 17.52 | cgroup 12.2G/max oom_kill 0 | free scratch 322.8G/45395211i tmp 29.7G/1017964i workspace 322.8G/45395211i | repeat-01 collected 26/26 workers (60602 items) tests 19146 done 1 failed | 26 in flight, oldest 90s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................................................................... [838%]
........................................................................ [841%]
........................................................................ [845%]
.............................................s......................[contention-diag] +2647s soak 36p/251t rss 12.2G pss 11.2G swap 1.5G majflt 47993 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 8 descendant rss 0.2G pss 0.1G | host avail 20.5G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 19.03 | cgroup 12.3G/max oom_kill 0 | free scratch 322.8G/45394333i tmp 29.7G/1017964i workspace 322.8G/45394333i | repeat-01 collected 26/26 workers (60602 items) tests 19428 done 1 failed | 26 in flight, oldest 105s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.... [848%]
........................................................................ [851%]
........................................................s............... [854%]
ss.............................................................[contention-diag] +2662s soak 33p/248t rss 12.2G pss 11.1G swap 1.5G majflt 48041 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 5 descendant rss 0.1G pss 0.1G | host avail 20.3G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 16.81 | cgroup 12.2G/max oom_kill 0 | free scratch 322.5G/45392908i tmp 29.7G/1017964i workspace 322.5G/45392908i | repeat-01 collected 26/26 workers (60602 items) tests 19644 done 1 failed | 26 in flight, oldest 50s gw13 tests/ace/tui/test_patch_filter_bar.py::test_patch_filter_live_typing_rolls_back_without_persistence
......... [857%]
........................................................................ [860%]
........................................................................ [863%]
........................................................................ [867%]
........................................................................ [870%]
.................................................[contention-diag] +2677s soak 32p/243t rss 12.2G pss 11.1G swap 1.5G majflt 48216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 4 descendant rss 0.1G pss 0.0G | host avail 25.1G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.36 cpu 17.64 | cgroup 12.2G/max oom_kill 0 | free scratch 322.8G/45391526i tmp 29.7G/1017962i workspace 322.8G/45391526i | repeat-01 collected 26/26 workers (60602 items) tests 19986 done 1 failed | 26 in flight, oldest 32s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
....................... [873%]
........................................................................ [876%]
.........................................[contention-diag] +2693s soak 36p/265t rss 12.2G pss 11.1G swap 1.5G majflt 48299 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 8 descendant rss 0.1G pss 0.0G | host avail 24.7G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.66 cpu 16.33 | cgroup 12.2G/max oom_kill 0 | free scratch 322.7G/45393346i tmp 29.7G/1017962i workspace 322.7G/45393346i | repeat-01 collected 26/26 workers (60602 items) tests 20125 done 1 failed | 26 in flight, oldest 48s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
............................... [879%]
........................................................................ [882%]
......................................[contention-diag] +2708s soak 34p/279t rss 12.3G pss 11.2G swap 1.5G majflt 48586 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 6 descendant rss 0.1G pss 0.1G | host avail 24.7G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 17.87 | cgroup 12.3G/max oom_kill 0 | free scratch 322.8G/45392577i tmp 29.7G/1017962i workspace 322.8G/45392577i | repeat-01 collected 26/26 workers (60602 items) tests 20265 done 1 failed | 26 in flight, oldest 63s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
.................................. [885%]
........................................................................ [889%]
........................................................................ [892%]
...............................[contention-diag] +2723s soak 42p/296t rss 12.4G pss 11.2G swap 1.5G majflt 48667 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 14 descendant rss 0.2G pss 0.1G | host avail 24.6G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 19.01 | cgroup 12.4G/max oom_kill 0 | free scratch 322.7G/45391871i tmp 29.7G/1017961i workspace 322.7G/45391871i | repeat-01 collected 26/26 workers (60602 items) tests 20476 done 1 failed | 26 in flight, oldest 67s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
......................................... [895%]
........................................................................ [898%]
.............................[contention-diag] +2739s soak 34p/267t rss 12.3G pss 11.2G swap 1.4G majflt 48764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 6 descendant rss 0.1G pss 0.1G | host avail 24.2G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.45 cpu 19.26 | cgroup 12.3G/max oom_kill 0 | free scratch 322.7G/45391629i tmp 29.7G/1017961i workspace 322.7G/45391629i | scratch used 0.6G in 118780 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 20602 done 1 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................................... [901%]
........................................................................ [904%]
[contention-diag] +2756s soak 41p/290t rss 12.4G pss 11.3G swap 1.4G majflt 48827 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 13 descendant rss 0.2G pss 0.1G | host avail 23.2G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 16.93 | cgroup 12.4G/max oom_kill 0 | free scratch 322.7G/45389783i tmp 29.7G/1017961i workspace 322.7G/45389783i | repeat-01 collected 26/26 workers (60602 items) tests 20729 done 1 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................................................................ [907%]
.......................................[contention-diag] +2771s soak 34p/292t rss 12.3G pss 11.2G swap 1.4G majflt 49046 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 6 descendant rss 0.2G pss 0.1G | host avail 21.4G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.37 cpu 17.25 | cgroup 12.3G/max oom_kill 0 | free scratch 322.7G/45389577i tmp 29.7G/1017961i workspace 322.7G/45389577i | repeat-01 collected 26/26 workers (60602 items) tests 20835 done 1 failed | 25 in flight, oldest 52s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
................................. [910%]
........................................................................ [914%]
........................................................................ [917%]
.......[contention-diag] +2787s soak 34p/234t rss 12.3G pss 11.2G swap 1.4G majflt 49287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 6 descendant rss 0.2G pss 0.2G | host avail 20.5G/62.7G swapfree 56.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.39 cpu 17.96 | cgroup 12.3G/max oom_kill 0 | free scratch 322.7G/45388864i tmp 29.7G/1017961i workspace 322.7G/45388864i | repeat-01 collected 26/26 workers (60602 items) tests 21024 done 1 failed | 26 in flight, oldest 68s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
................................................................. [920%]
........................................................................ [923%]
........................................................................ [926%]
.............................................................[contention-diag] +2802s soak 36p/202t rss 12.4G pss 11.3G swap 1.4G majflt 49373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 8 descendant rss 0.3G pss 0.2G | host avail 22.4G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 23.07 | cgroup 12.4G/max oom_kill 0 | free scratch 322.4G/45388132i tmp 29.7G/1017961i workspace 322.4G/45388133i | repeat-01 collected 26/26 workers (60602 items) tests 21283 done 1 failed | 25 in flight, oldest 46s gw15 tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
........... [929%]
........................................................................ [932%]
........................................................................ [936%]
........................................................................ [939%]
........................................................................ [942%]
..............................................[contention-diag] +2817s soak 33p/198t rss 12.3G pss 11.2G swap 1.4G majflt 49740 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 5 descendant rss 0.1G pss 0.1G | host avail 22.0G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.06 cpu 20.53 | cgroup 12.3G/max oom_kill 0 | free scratch 322.4G/45386641i tmp 29.7G/1017960i workspace 322.4G/45386641i | repeat-01 collected 26/26 workers (60602 items) tests 21626 done 1 failed | 26 in flight, oldest 43s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail
.......................... [945%]
........................................................................ [948%]
........................................................................ [951%]
........................................................................ [954%]
........................................................................ [958%]
........................................................................ [961%]
..........[contention-diag] +2833s soak 31p/197t rss 12.3G pss 11.2G swap 1.4G majflt 49852 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 3 descendant rss 0.1G pss 0.1G | host avail 22.1G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.92 cpu 18.27 | cgroup 12.3G/max oom_kill 0 | free scratch 321.2G/45384530i tmp 29.7G/1017988i workspace 321.2G/45384530i | repeat-01 collected 26/26 workers (60602 items) tests 22036 done 1 failed | 26 in flight, oldest 55s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_axe_tab
.........................s.................................... [964%]
........................................................................ [967%]
.......................................s................................ [970%]
.......................................................[contention-diag] +2848s soak 32p/206t rss 12.3G pss 11.2G swap 1.4G majflt 50141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 4 descendant rss 0.1G pss 0.1G | host avail 24.6G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.41 cpu 19.77 | cgroup 12.4G/max oom_kill 0 | free scratch 321.2G/45385329i tmp 29.7G/1017988i workspace 321.2G/45385329i | repeat-01 collected 26/26 workers (60602 items) tests 22299 done 1 failed | 25 in flight, oldest 51s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
................. [973%]
........................................................................ [976%]
........................................................................ [980%]
........................................................................ [983%]
........................................................................ [986%]
........................................................................ [989%]
........................................................................ [992%]
....................................................[contention-diag] +2863s soak 39p/208t rss 12.3G pss 11.2G swap 1.4G majflt 50324 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 11 descendant rss 0.1G pss 0.0G | host avail 23.1G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.11 cpu 15.41 | cgroup 12.3G/max oom_kill 0 | free scratch 321.0G/45382557i tmp 29.7G/1017988i workspace 321.0G/45382557i | scratch used 0.4G in 66469 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 22747 done 1 failed | 25 in flight, oldest 46s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_overview_revalidation_tick_never_paints_loading
.................... [995%]
........................................................................ [998%]
........................................................................ [1002%]
...................................................[contention-diag] +2881s soak 36p/205t rss 12.5G pss 11.3G swap 1.4G majflt 50442 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 8 descendant rss 0.3G pss 0.1G | host avail 22.4G/62.7G swapfree 56.9G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.85 cpu 17.66 | cgroup 12.5G/max oom_kill 0 | free scratch 320.8G/45381791i tmp 29.7G/1017988i workspace 320.8G/45381791i | repeat-01 collected 26/26 workers (60602 items) tests 23016 done 1 failed | 26 in flight, oldest 55s gw9 tests/ace/tui/test_projects_pane.py::test_show_new_project_key_clears_filter
..................... [1005%]
........................................................................ [1008%]
........................................................................ [1011%]
........................................................................ [1014%]
...........................[contention-diag] +2896s soak 35p/186t rss 12.4G pss 11.3G swap 1.4G majflt 50577 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 7 descendant rss 0.2G pss 0.2G | host avail 21.2G/62.7G swapfree 56.7G/64.0G oom_kill +0 | psi10 mem 2.36/0.92 io 5.34 cpu 14.17 | cgroup 12.4G/max oom_kill 0 | free scratch 320.7G/45380934i tmp 29.7G/1017988i workspace 320.7G/45380934i | repeat-01 collected 26/26 workers (60602 items) tests 23267 done 1 failed | 26 in flight, oldest 53s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
............................................. [1017%]
........................................................................ [1020%]
........................................................................ [1024%]
........................................................................ [1027%]
........................................................................ [1030%]
...................................[contention-diag] +2911s soak 33p/186t rss 12.4G pss 11.2G swap 1.5G majflt 50760 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 5 descendant rss 0.2G pss 0.1G | host avail 19.5G/62.7G swapfree 56.6G/64.0G oom_kill +0 | psi10 mem 0.98/0.33 io 2.04 cpu 16.49 | cgroup 12.2G/max oom_kill 0 | free scratch 320.6G/45379814i tmp 29.7G/1017987i workspace 320.6G/45379814i | repeat-01 collected 26/26 workers (60602 items) tests 23644 done 1 failed | 26 in flight, oldest 69s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
..................................... [1033%]
........................................................................ [1036%]
........................................................................ [1039%]
........................................................................ [1042%]
........................................................................ [1046%]
............[contention-diag] +2927s soak 35p/198t rss 12.3G pss 11.2G swap 1.5G majflt 50985 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 7 descendant rss 0.1G pss 0.1G | host avail 19.9G/62.7G swapfree 56.6G/64.0G oom_kill +0 | psi10 mem 0.24/0.08 io 3.0 cpu 19.6 | cgroup 12.2G/max oom_kill 0 | free scratch 320.5G/45378647i tmp 29.7G/1017986i workspace 320.5G/45378647i | repeat-01 collected 26/26 workers (60602 items) tests 23981 done 1 failed | 25 in flight, oldest 84s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
............................................................ [1049%]
........................................................................ [1052%]
..............................................[contention-diag] +2942s soak 40p/205t rss 12.4G pss 11.2G swap 1.5G majflt 51232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 12 descendant rss 0.2G pss 0.1G | host avail 18.8G/62.7G swapfree 56.5G/64.0G oom_kill +0 | psi10 mem 0.1/0.07 io 1.95 cpu 16.64 | cgroup 12.0G/max oom_kill 0 | free scratch 320.2G/45377484i tmp 29.7G/1017985i workspace 320.2G/45377484i | repeat-01 collected 26/26 workers (60602 items) tests 24160 done 1 failed | 26 in flight, oldest 99s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.......................... [1055%]
........................................................................ [1058%]
.....................................................................[contention-diag] +2958s soak 38p/189t rss 12.3G pss 11.2G swap 1.5G majflt 51388 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 10 descendant rss 0.1G pss 0.1G | host avail 17.9G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 1.49/0.86 io 2.28 cpu 14.4 | cgroup 12.1G/max oom_kill 0 | free scratch 320.6G/45399362i tmp 29.7G/1017981i workspace 320.6G/45399362i | repeat-01 collected 26/26 workers (60602 items) tests 24319 done 1 failed | 25 in flight, oldest 115s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
... [1061%]
........................................................................ [1064%]
..........................................................[contention-diag] +2973s soak 42p/205t rss 12.7G pss 11.4G swap 1.5G majflt 51523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 14 descendant rss 0.5G pss 0.4G | host avail 21.1G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.36/0.21 io 1.01 cpu 15.34 | cgroup 12.4G/max oom_kill 0 | free scratch 320.2G/45377086i tmp 29.7G/1017982i workspace 320.2G/45377086i | repeat-01 collected 26/26 workers (60602 items) tests 24462 done 1 failed | 26 in flight, oldest 130s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.............. [1068%]
........................................................................ [1071%]
...........................F[contention-failure] call tests/test_provider_disable.py::test_facade_try_disable_one_winner_under_process_contention: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa7af382390>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw14/test_facade_try_disable_one_wi0')
registered_providers = None, real_provider_disable_reads = None

    def test_facade_try_disable_one_winner_under_process_contention(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        registered_providers: None,
        real_provider_disable_reads: None,
    ) -> None:
        monkeypatch.setenv("SASE_HOME", str(tmp_path))
        sibling = disable_provider("codex", 1_200.0, source="sibling", now=_NOW)
        start = tmp_path / "start"
        worker = tmp_path / "worker.py"
        worker.write_text(
            "\n".join(
                [
                    "import json, sys, time",
                    "from pathlib import Path",
                    "from sase.llm_provider.provider_disable import try_disable_provider",
                    f"start = Path({str(start)!r})",
                    "for _ in range(400):",
                    "    if start.exists():",
                    "        break",
                    "    time.sleep(0.005)",
                    "else:",
                    "    raise SystemExit('start file never appeared')",
                    "index = int(sys.argv[1])",
                    "outcome = try_disable_provider(",
                    '    "claude",',
                    "    60.0 + index,",
                    '    source=f"contender-{index}",',
                    f"    now={_NOW} + index,",
                    ")",
                    'print(json.dumps({"inserted": outcome.inserted, '
                    '"source": outcome.record.source}))',
                ]
            ),
            encoding="utf-8",
        )
        env = os.environ.copy()
        env["SASE_HOME"] = str(tmp_path)
        processes = [
            subprocess.Popen(
                [sys.executable, str(worker), str(index)],
                cwd=str(Path(__file__).resolve().parents[1]),
                env=env,
                text=True,
                stdout=subprocess.PIPE,
                stderr=subprocess.PIPE,
            )
            for index in range(6)
        ]
        start.write_text("go\n", encoding="utf-8")
        outcomes = []
        for process in processes:
>           stdout, stderr = process.communicate(timeout=10)
                             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_provider_disable.py:181: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:1209: in communicate
    stdout, stderr = self._communicate(input, endtime, timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:2116: in _communicate
    self._check_timeout(endtime, orig_timeout, stdout, stderr)
_ _ _ 
............................................ [1074%]
........................................................................ [1077%]
................................................................[contention-diag] +2989s soak 37p/190t rss 12.3G pss 11.2G swap 1.5G majflt 51802 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 9 descendant rss 0.1G pss 0.1G | host avail 21.1G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.04 io 3.15 cpu 13.41 | cgroup 11.9G/max oom_kill 0 | free scratch 320.1G/45386820i tmp 29.7G/1017980i workspace 320.1G/45386820i | scratch used 0.0G in 1559 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 24728 done 2 failed | 26 in flight, oldest 146s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........ [1080%]
........................................................................ [1083%]
........................................................................ [1086%]
.......................................................[contention-diag] +3006s soak 36p/190t rss 12.3G pss 11.2G swap 1.6G majflt 52479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 8 descendant rss 0.2G pss 0.1G | host avail 22.0G/62.7G swapfree 55.5G/64.0G oom_kill +0 | psi10 mem 4.52/3.46 io 7.44 cpu 13.44 | cgroup 11.8G/max oom_kill 0 | free scratch 320.2G/45385915i tmp 29.7G/1017965i workspace 320.2G/45385915i | repeat-01 collected 26/26 workers (60602 items) tests 24964 done 2 failed | 26 in flight, oldest 164s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
................. [1090%]
........................................................................ [1093%]
.......................................................................s [1096%]
........................................................................ [1099%]
[contention-diag] +3022s soak 35p/189t rss 12.2G pss 11.0G swap 1.8G majflt 52845 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 7 descendant rss 0.2G pss 0.1G | host avail 24.4G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 1.65/0.69 io 3.14 cpu 14.03 | cgroup 11.6G/max oom_kill 0 | free scratch 320.0G/45374443i tmp 29.7G/1017965i workspace 320.0G/45374443i | repeat-01 collected 26/26 workers (60602 items) tests 25187 done 2 failed | 25 in flight, oldest 179s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........................................................................ [1102%]
........................................................................ [1105%]
........................................................................ [1108%]
....................................[contention-diag] +3037s soak 32p/189t rss 12.1G pss 10.9G swap 1.8G majflt 53634 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.6G, 4 descendant rss 0.1G pss 0.1G | host avail 22.9G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 1.96/0.17 io 2.5 cpu 16.98 | cgroup 11.6G/max oom_kill 0 | free scratch 320.0G/45373236i tmp 29.7G/1017963i workspace 320.0G/45373236i | repeat-01 collected 26/26 workers (60602 items) tests 25428 done 2 failed | 26 in flight, oldest 194s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.................................... [1112%]
........................................................................ [1115%]
........................................................................ [1118%]
........................................................................ [1121%]
...........................................................[contention-diag] +3053s soak 35p/183t rss 12.2G pss 11.0G swap 1.8G majflt 55138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.6G, 7 descendant rss 0.2G pss 0.1G | host avail 22.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 1.45/0.03 io 1.75 cpu 18.18 | cgroup 11.6G/max oom_kill 0 | free scratch 320.0G/45372332i tmp 29.7G/1017962i workspace 320.0G/45372332i | repeat-01 collected 26/26 workers (60602 items) tests 25759 done 2 failed | 26 in flight, oldest 210s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
............. [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
.................................................[contention-diag] +3068s soak 36p/184t rss 12.2G pss 11.0G swap 1.8G majflt 73799 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 8 descendant rss 0.2G pss 0.1G | host avail 23.9G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 6.13/0.0 io 2.23 cpu 21.4 | cgroup 11.7G/max oom_kill 0 | free scratch 320.0G/45371887i tmp 29.7G/1017963i workspace 320.0G/45371887i | repeat-01 collected 26/26 workers (60602 items) tests 25965 done 2 failed | 26 in flight, oldest 225s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
....................... [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
........................................................................ [1143%]
.....................[contention-diag] +3083s soak 30p/165t rss 12.1G pss 10.9G swap 1.7G majflt 74309 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 2.08/0.0 io 1.25 cpu 20.0 | cgroup 11.7G/max oom_kill 0 | free scratch 320.0G/45372192i tmp 29.7G/1017963i workspace 320.0G/45372192i | repeat-01 collected 26/26 workers (60602 items) tests 26221 done 2 failed | 25 in flight, oldest 240s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................................................... [1146%]
........................................................................ [1149%]
........................................................................ [1152%]
........................................................................ [1156%]
........................................................................ [1159%]
........................................................................ [1162%]
...................................[contention-diag] +3099s soak 30p/161t rss 12.2G pss 11.0G swap 1.7G majflt 74686 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 2 descendant rss 0.1G pss 0.1G | host avail 23.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.72/0.0 io 1.04 cpu 16.56 | cgroup 11.7G/max oom_kill 0 | free scratch 319.8G/45370082i tmp 29.7G/1017963i workspace 319.8G/45370082i | repeat-01 collected 26/26 workers (60602 items) tests 26667 done 2 failed | 24 in flight, oldest 256s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
..................................... [1165%]
........................................................................ [1168%]
........................................................................ [1171%]
........................................................................ [1174%]
..[contention-diag] +3114s soak 32p/172t rss 12.3G pss 11.1G swap 1.7G majflt 75033 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 4 descendant rss 0.2G pss 0.2G | host avail 23.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.65 cpu 13.44 | cgroup 11.8G/max oom_kill 0 | free scratch 319.3G/45368620i tmp 29.7G/1017963i workspace 319.3G/45368620i | scratch used 0.0G in 5151 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 26903 done 2 failed | 25 in flight, oldest 271s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...................................................................... [1178%]
........................................................................ [1181%]
........................................................................ [1184%]
........................................................................ [1187%]
........................................................................ [1190%]
............................[contention-diag] +3131s soak 39p/176t rss 12.3G pss 11.1G swap 1.7G majflt 75586 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 11 descendant rss 0.1G pss 0.1G | host avail 25.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.47/0.0 io 0.89 cpu 19.75 | cgroup 11.8G/max oom_kill 0 | free scratch 319.3G/45367365i tmp 29.7G/1017963i workspace 319.3G/45367365i | repeat-01 collected 26/26 workers (60602 items) tests 27304 done 2 failed | 24 in flight, oldest 225s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................ [1193%]
........................................................................ [1196%]
.........................................................[contention-diag] +3147s soak 35p/173t rss 12.4G pss 11.2G swap 1.7G majflt 77830 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 7 descendant rss 0.3G pss 0.2G | host avail 24.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.68/0.0 io 0.85 cpu 22.51 | cgroup 12.0G/max oom_kill 0 | free scratch 319.3G/45366909i tmp 29.7G/1017963i workspace 319.3G/45366909i | repeat-01 collected 26/26 workers (60602 items) tests 27481 done 2 failed | 25 in flight, oldest 241s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............... [1200%]
........................................................................ [1203%]
........................................................................ [1206%]
........................................................................ [1209%]
.....[contention-diag] +3162s soak 34p/173t rss 12.2G pss 11.0G swap 1.9G majflt 76723 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 6 descendant rss 0.2G pss 0.2G | host avail 25.1G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 2.11/0.27 io 1.88 cpu 18.77 | cgroup 12.0G/max oom_kill 0 | free scratch 319.3G/45365556i tmp 29.7G/1017963i workspace 319.3G/45365556i | repeat-01 collected 26/26 workers (60602 items) tests 27705 done 2 failed | 25 in flight, oldest 256s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................................... [1212%]
........................................................................ [1215%]
........................................................................ [1218%]
.....................[contention-diag] +3177s soak 34p/173t rss 12.2G pss 10.9G swap 1.9G majflt 77199 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 6 descendant rss 0.1G pss 0.1G | host avail 23.1G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 2.29/0.06 io 0.8 cpu 21.93 | cgroup 11.9G/max oom_kill 0 | free scratch 319.7G/45372731i tmp 29.7G/1017963i workspace 319.7G/45372731i | repeat-01 collected 26/26 workers (60602 items) tests 27946 done 2 failed | 25 in flight, oldest 271s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................... [1221%]
........................................................................ [1225%]
........................................................................ [1228%]
........................................................................ [1231%]
............................................[contention-diag] +3193s soak 33p/161t rss 12.1G pss 10.9G swap 1.8G majflt 77616 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 5 descendant rss 0.1G pss 0.1G | host avail 22.5G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.5/0.01 io 0.38 cpu 18.22 | cgroup 11.8G/max oom_kill 0 | free scratch 319.5G/45371969i tmp 29.7G/1017963i workspace 319.5G/45371969i | repeat-01 collected 26/26 workers (60602 items) tests 28244 done 2 failed | 25 in flight, oldest 188s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................ [1234%]
........................................................................ [1237%]
.............................................................[contention-diag] +3208s soak 35p/173t rss 12.2G pss 11.0G swap 1.8G majflt 78339 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 7 descendant rss 0.1G pss 0.1G | host avail 27.9G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.1/0.0 io 1.05 cpu 22.05 | cgroup 11.9G/max oom_kill 0 | free scratch 319.0G/45368142i tmp 29.7G/1017961i workspace 319.0G/45368142i | repeat-01 collected 26/26 workers (60602 items) tests 28424 done 2 failed | 25 in flight, oldest 203s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........... [1240%]
........................................................................ [1243%]
........................................................................ [1247%]
........................................................................ [1250%]
........................................................................ [1253%]
.......................................................[contention-diag] +3223s soak 35p/178t rss 12.2G pss 11.0G swap 1.8G majflt 79362 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 7 descendant rss 0.1G pss 0.1G | host avail 28.0G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 2.53 cpu 27.01 | cgroup 11.9G/max oom_kill 0 | free scratch 319.0G/45364858i tmp 29.7G/1017961i workspace 319.0G/45364858i | repeat-01 collected 26/26 workers (60602 items) tests 28775 done 2 failed | 25 in flight, oldest 218s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................. [1256%]
........................................................................ [1259%]
........................................................................ [1262%]
........................................................................ [1265%]
.......................................................F[contention-failure] call tests/llm_provider/test_codex_usage_probe.py::test_descendant_processes_are_reaped: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f84e1c7d700>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw12/test_descendant_processes_are_0')

    def test_descendant_processes_are_reaped(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pidfile = tmp_path / "child.pid"
        monkeypatch.setenv("SASE_CODEX_APP_SERVER_PIDFILE", str(pidfile))
        for deadline_seconds in hang_deadlines(1.5):
            context = _context(
                mode="descendants",
                monkeypatch=monkeypatch,
                deadline_seconds=deadline_seconds,
            )
            observation = collect_codex_usage(context)
            assert observation["outcome"] == "error"
            assert observation["reason_code"] == "timeout"
            if pidfile.exists():
                break
        child_pid = int(pidfile.read_text(encoding="utf-8"))
>       assert not _pid_alive(child_pid)
E       assert not True
E        +  where True = _pid_alive(2677914)

tests/llm_provider/test_codex_usage_probe.py:335: AssertionError
................ [1269%]
........................................................................ [1272%]
...........................[contention-diag] +3239s soak 37p/168t rss 12.2G pss 11.0G swap 1.8G majflt 79936 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 9 descendant rss 0.1G pss 0.1G | host avail 27.2G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.37 cpu 25.97 | cgroup 11.9G/max oom_kill 0 | free scratch 318.9G/45348872i tmp 29.7G/1017961i workspace 318.9G/45348872i | scratch used 0.1G in 18349 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 29137 done 3 failed | 25 in flight, oldest 234s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................. [1275%]
........................................................................ [1278%]
..................................[contention-diag] +3256s soak 34p/173t rss 12.3G pss 11.0G swap 1.8G majflt 80948 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 6 descendant rss 0.2G pss 0.1G | host avail 25.8G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.43 cpu 23.16 | cgroup 12.0G/max oom_kill 0 | free scratch 318.9G/45348004i tmp 29.7G/1017961i workspace 318.9G/45348004i | repeat-01 collected 26/26 workers (60602 items) tests 29335 done 3 failed | 25 in flight, oldest 251s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................................... [1281%]
........................................................................ [1284%]
........................................................................ [1287%]
........................................................................ [1291%]
........................................................................ [1294%]
........................................................................ [1297%]
............[contention-diag] +3271s soak 34p/165t rss 12.3G pss 11.0G swap 1.8G majflt 81574 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 6 descendant rss 0.2G pss 0.1G | host avail 26.9G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.98 cpu 31.0 | cgroup 12.0G/max oom_kill 0 | free scratch 318.9G/45347110i tmp 29.7G/1017961i workspace 318.9G/45347111i | repeat-01 collected 26/26 workers (60602 items) tests 29745 done 3 failed | 24 in flight, oldest 266s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................ [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
........................................................................ [1309%]
........................................................................ [1313%]
.....................[contention-diag] +3287s soak 34p/160t rss 12.3G pss 11.1G swap 1.8G majflt 81901 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 6 descendant rss 0.2G pss 0.1G | host avail 26.6G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.74 cpu 28.13 | cgroup 12.0G/max oom_kill 0 | free scratch 318.9G/45346207i tmp 29.7G/1017961i workspace 318.9G/45346207i | repeat-01 collected 26/26 workers (60602 items) tests 30101 done 3 failed | 25 in flight, oldest 282s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................... [1316%]
........................................................................ [1319%]
........................................................................ [1322%]
........................................................................ [1325%]
........................................................................ [1328%]
....................................................[contention-diag] +3302s soak 32p/165t rss 12.3G pss 11.1G swap 1.8G majflt 82267 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 26.8G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 29.42 | cgroup 12.1G/max oom_kill 0 | free scratch 318.9G/45344911i tmp 29.7G/1017960i workspace 318.9G/45344911i | repeat-01 collected 26/26 workers (60602 items) tests 30504 done 3 failed | 25 in flight, oldest 297s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................... [1331%]
........................................................................ [1335%]
........................................................................ [1338%]
........[contention-diag] +3317s soak 34p/176t rss 12.4G pss 11.1G swap 1.8G majflt 82925 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 6 descendant rss 0.2G pss 0.1G | host avail 26.5G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.75 cpu 28.3 | cgroup 12.2G/max oom_kill 0 | free scratch 318.9G/45343955i tmp 29.7G/1017960i workspace 318.9G/45343955i | repeat-01 collected 26/26 workers (60602 items) tests 30679 done 3 failed | 25 in flight, oldest 312s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................................ [1341%]
........................................................................ [1344%]
........................................................................ [1347%]
........................................................................ [1350%]
............................................[contention-diag] +3333s soak 34p/163t rss 12.4G pss 11.2G swap 1.8G majflt 83213 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 6 descendant rss 0.2G pss 0.2G | host avail 26.7G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.87 cpu 28.4 | cgroup 12.2G/max oom_kill 0 | free scratch 318.9G/45342143i tmp 29.7G/1017960i workspace 318.9G/45342143i | repeat-01 collected 26/26 workers (60602 items) tests 30986 done 3 failed | 25 in flight, oldest 328s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................ [1353%]
........................................................................ [1357%]
........................................................................ [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
.............................................[contention-diag] +3348s soak 38p/174t rss 12.5G pss 11.2G swap 1.8G majflt 83764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 10 descendant rss 0.3G pss 0.2G | host avail 26.9G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 1.88 cpu 27.1 | cgroup 12.3G/max oom_kill 0 | free scratch 318.9G/45341700i tmp 29.7G/1017959i workspace 318.9G/45341700i | repeat-01 collected 26/26 workers (60602 items) tests 31352 done 3 failed | 25 in flight, oldest 300s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
........................... [1369%]
........................................................................ [1372%]
........................................................................ [1375%]
........................................................................ [1379%]
........................................................................ [1382%]
........................................................................ [1385%]
...................................................[contention-diag] +3363s soak 32p/161t rss 12.4G pss 11.1G swap 1.8G majflt 84202 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 4 descendant rss 0.1G pss 0.1G | host avail 26.9G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.78 cpu 28.93 | cgroup 12.2G/max oom_kill 0 | free scratch 318.9G/45341147i tmp 29.7G/1017959i workspace 318.9G/45341147i | scratch used 0.2G in 38460 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 31743 done 3 failed | 25 in flight, oldest 315s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
..................... [1388%]
........................................................................ [1391%]
........................................................................ [1394%]
........................................................................ [1397%]
........................................................................ [1401%]
.......................................................................[contention-diag] +3381s soak 34p/171t rss 12.5G pss 11.2G swap 1.7G majflt 85458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 6 descendant rss 0.2G pss 0.2G | host avail 23.6G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.56 cpu 25.87 | cgroup 12.4G/max oom_kill 0 | free scratch 318.9G/45339778i tmp 29.7G/1017958i workspace 318.9G/45339778i | repeat-01 collected 26/26 workers (60602 items) tests 32176 done 3 failed | 25 in flight, oldest 333s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
. [1404%]
........................................................................ [1407%]
........................................................................ [1410%]
........................................................................ [1413%]
...........................................[contention-diag] +3396s soak 36p/195t rss 12.7G pss 11.4G swap 1.8G majflt 85864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 8 descendant rss 0.4G pss 0.3G | host avail 23.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 21.08 | cgroup 12.5G/max oom_kill 0 | free scratch 318.9G/45339801i tmp 29.7G/1017958i workspace 318.9G/45339801i | repeat-01 collected 26/26 workers (60602 items) tests 32443 done 3 failed | 25 in flight, oldest 348s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................. [1416%]
........................................................................ [1419%]
........................................................................ [1423%]
........................................................................ [1426%]
............................................[contention-diag] +3412s soak 39p/188t rss 12.7G pss 11.4G swap 1.8G majflt 86010 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.8G, 11 descendant rss 0.4G pss 0.3G | host avail 22.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 22.33 | cgroup 12.6G/max oom_kill 0 | free scratch 318.8G/45337391i tmp 29.7G/1017958i workspace 318.8G/45337391i | repeat-01 collected 26/26 workers (60602 items) tests 32707 done 3 failed | 25 in flight, oldest 363s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................ [1429%]
........................................................................ [1432%]
........................................................................ [1435%]
........................................................................ [1438%]
........................................................................ [1441%]
[contention-diag] +3427s soak 38p/181t rss 12.6G pss 11.3G swap 1.7G majflt 86483 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 10 descendant rss 0.2G pss 0.2G | host avail 23.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 2.4/1.63 io 3.94 cpu 19.46 | cgroup 12.5G/max oom_kill 0 | free scratch 318.9G/45333052i tmp 29.7G/1017958i workspace 318.9G/45333050i | repeat-01 collected 26/26 workers (60602 items) tests 33037 done 3 failed | 24 in flight, oldest 379s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
........................................................................ [1445%]
........................................................................ [1448%]
........................................................................ [1451%]
........................................................................ [1454%]
.............................................................[contention-diag] +3442s soak 32p/182t rss 12.3G pss 11.0G swap 1.9G majflt 86776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 23.5G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 1.53/0.49 io 4.48 cpu 17.14 | cgroup 12.1G/max oom_kill 0 | free scratch 318.8G/45317161i tmp 29.7G/1017958i workspace 318.8G/45317161i | repeat-01 collected 26/26 workers (60602 items) tests 33370 done 3 failed | 25 in flight, oldest 394s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
........... [1457%]
........................................................................ [1460%]
........................................................................ [1463%]
........................................................................ [1467%]
........................................................................ [1470%]
........................................................................ [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
..................................[contention-diag] +3458s soak 31p/173t rss 12.3G pss 11.0G swap 1.9G majflt 87052 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 3 descendant rss 0.1G pss 0.1G | host avail 20.9G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 1.18/0.12 io 2.32 cpu 15.34 | cgroup 11.9G/max oom_kill 0 | free scratch 318.7G/45312926i tmp 29.7G/1017957i workspace 318.7G/45312926i | repeat-01 collected 26/26 workers (60602 items) tests 33911 done 3 failed | 25 in flight, oldest 410s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
...................................... [1482%]
........................................................................ [1485%]
........................................................................ [1489%]
............................................[contention-diag] +3473s soak 36p/178t rss 12.4G pss 11.0G swap 2.0G majflt 87402 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 8 descendant rss 0.2G pss 0.1G | host avail 18.6G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.7/0.25 io 0.97 cpu 9.65 | cgroup 12.2G/max oom_kill 0 | free scratch 318.1G/45310664i tmp 29.7G/1017956i workspace 318.1G/45310664i | repeat-01 collected 26/26 workers (60602 items) tests 34160 done 3 failed | 25 in flight, oldest 425s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
............................ [1492%]
........................................................................ [1495%]
........................................................................ [1498%]
........................................................................ [1501%]
......................................................................[contention-diag] +3488s soak 40p/175t rss 12.5G pss 11.1G swap 2.0G majflt 87894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 12 descendant rss 0.3G pss 0.2G | host avail 25.9G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.34/0.05 io 2.03 cpu 10.17 | cgroup 12.2G/max oom_kill 0 | free scratch 318.4G/45308677i tmp 29.7G/1017955i workspace 318.4G/45308677i | scratch used 0.2G in 37447 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 34452 done 3 failed | 25 in flight, oldest 440s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
.. [1504%]
........................................................................ [1507%]
........................................................................ [1510%]
........................................................................ [1514%]
........................................................................ [1517%]
........................................................................ [1520%]
...........................................[contention-diag] +3506s soak 35p/176t rss 12.3G pss 11.0G swap 1.9G majflt 88256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 7 descendant rss 0.1G pss 0.1G | host avail 26.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.29/0.0 io 2.66 cpu 15.48 | cgroup 12.2G/max oom_kill 0 | free scratch 318.4G/45307308i tmp 29.7G/1017953i workspace 318.4G/45307308i | repeat-01 collected 26/26 workers (60602 items) tests 34889 done 3 failed | 25 in flight, oldest 451s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
............................. [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1532%]
........................................................................ [1536%]
..............................[contention-diag] +3522s soak 35p/184t rss 12.4G pss 11.1G swap 1.9G majflt 88544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.9G pss 10.7G, 7 descendant rss 0.2G pss 0.1G | host avail 24.6G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.11/0.0 io 1.09 cpu 17.92 | cgroup 12.1G/max oom_kill 0 | free scratch 317.9G/45303032i tmp 29.7G/1017953i workspace 317.9G/45303032i | repeat-01 collected 26/26 workers (60602 items) tests 35228 done 3 failed | 25 in flight, oldest 157s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 4 hazardous kill call(s)
.......................................... [1539%]
........................................................................ [1542%]
........................................................................ [1545%]
............................................[contention-diag] +3537s soak 36p/185t rss 12.4G pss 11.1G swap 2.0G majflt 88906 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.9G pss 10.6G, 8 descendant rss 0.2G pss 0.2G | host avail 22.7G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 1.21/0.29 io 1.05 cpu 16.6 | cgroup 12.1G/max oom_kill 0 | free scratch 317.9G/45301915i tmp 29.7G/1017953i workspace 317.9G/45301915i | repeat-01 collected 26/26 workers (60602 items) tests 35464 done 3 failed | 25 in flight, oldest 172s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 4 hazardous kill call(s)
............................ [1548%]
........................................................................ [1551%]
........................................................................ [1554%]
...................................[contention-diag] +3552s soak 34p/182t rss 12.4G pss 11.1G swap 2.0G majflt 89221 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.9G pss 10.6G, 6 descendant rss 0.2G pss 0.2G | host avail 20.6G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.29/0.07 io 0.85 cpu 17.13 | cgroup 12.2G/max oom_kill 0 | free scratch 317.9G/45301530i tmp 29.7G/1017952i workspace 317.9G/45301530i | repeat-01 collected 26/26 workers (60602 items) tests 35655 done 3 failed | 25 in flight, oldest 188s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 4 hazardous kill call(s)
..................................... [1558%]
........................................................................ [1561%]
........................................................................ [1564%]
........................................................................ [1567%]
..[contention-diag] +3568s soak 35p/191t rss 12.4G pss 11.0G swap 2.0G majflt 89776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.9G pss 10.6G, 7 descendant rss 0.2G pss 0.1G | host avail 24.5G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.46/0.24 io 4.01 cpu 14.2 | cgroup 12.1G/max oom_kill 0 | free scratch 317.5G/45300933i tmp 29.7G/1017950i workspace 317.5G/45300933i | repeat-01 collected 26/26 workers (60602 items) tests 35917 done 3 failed | 24 in flight, oldest 203s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
............s......................................................... [1570%]
........................................................................ [1573%]
........................................................................ [1576%]
............................................................[contention-diag] +3583s soak 38p/201t rss 12.5G pss 11.1G swap 2.1G majflt 90174 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.9G pss 10.6G, 10 descendant rss 0.3G pss 0.2G | host avail 21.4G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.09/0.04 io 1.36 cpu 10.42 | cgroup 12.3G/max oom_kill 0 | free scratch 317.1G/45299182i tmp 29.7G/1017950i workspace 317.1G/45299182i | repeat-01 collected 26/26 workers (60602 items) tests 36195 done 3 failed | 23 in flight, oldest 218s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
............ [1580%]
........................................................................ [1583%]
.............................................[contention-diag] +3598s soak 38p/195t rss 12.4G pss 11.1G swap 2.0G majflt 90387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.9G pss 10.6G, 10 descendant rss 0.2G pss 0.2G | host avail 23.3G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 4.99/3.95 io 7.64 cpu 8.51 | cgroup 12.4G/max oom_kill 0 | free scratch 316.4G/45297856i tmp 29.7G/1017950i workspace 316.4G/45297856i | repeat-01 collected 26/26 workers (60602 items) tests 36327 done 3 failed | 24 in flight, oldest 234s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
........................... [1586%]
........................................................................ [1589%]
........................................................................ [1592%]
........................................................................ [1595%]
.................................................[contention-diag] +3614s soak 38p/194t rss 12.2G pss 10.8G swap 2.3G majflt 90952 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.6G pss 10.3G, 10 descendant rss 0.3G pss 0.2G | host avail 17.5G/62.7G swapfree 49.7G/64.0G oom_kill +0 | psi10 mem 3.03/2.15 io 11.9 cpu 11.34 | cgroup 11.5G/max oom_kill 0 | free scratch 316.3G/45297453i tmp 29.7G/1017950i workspace 316.3G/45297453i | scratch used 0.0G in 7393 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 36599 done 3 failed | 24 in flight, oldest 249s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
....................... [1598%]
........................................................................ [1602%]
........................................................................ [1605%]
........................................................................ [1608%]
.............[contention-diag] +3631s soak 35p/195t rss 11.0G pss 9.6G swap 3.5G majflt 91064 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 10.6G pss 9.3G, 7 descendant rss 0.2G pss 0.2G | host avail 15.2G/62.7G swapfree 48.4G/64.0G oom_kill +0 | psi10 mem 6.78/4.87 io 17.58 cpu 10.18 | cgroup 10.1G/max oom_kill 0 | free scratch 318.0G/45340285i tmp 29.7G/1017950i workspace 318.0G/45340285i | repeat-01 collected 26/26 workers (60602 items) tests 36870 done 3 failed | 23 in flight, oldest 267s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
........................................................... [1611%]
........................................................................ [1614%]
........................................................................ [1617%]
........................................................................ [1620%]
.................[contention-diag] +3647s soak 33p/201t rss 10.5G pss 9.1G swap 4.0G majflt 93178 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.2G pss 8.8G, 5 descendant rss 0.2G pss 0.1G | host avail 16.1G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 4.52/1.92 io 11.53 cpu 11.08 | cgroup 9.6G/max oom_kill 0 | free scratch 317.6G/45339334i tmp 29.7G/1017950i workspace 317.6G/45339334i | repeat-01 collected 26/26 workers (60602 items) tests 37164 done 3 failed | 23 in flight, oldest 282s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
....................................................... [1624%]
........................................................................ [1627%]
........................................................................ [1630%]
.........................s..............................[contention-diag] +3662s soak 32p/190t rss 10.4G pss 9.0G swap 4.0G majflt 98872 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.2G pss 8.8G, 4 descendant rss 0.1G pss 0.1G | host avail 18.1G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 3.97/0.43 io 5.26 cpu 11.99 | cgroup 9.6G/max oom_kill 0 | free scratch 317.4G/45338066i tmp 29.7G/1017950i workspace 317.4G/45338066i | repeat-01 collected 26/26 workers (60602 items) tests 37407 done 3 failed | 23 in flight, oldest 297s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
................ [1633%]
........................................................................ [1636%]
........................................................................ [1639%]
........................................................................ [1642%]
........................................................................ [1646%]
........[contention-diag] +3677s soak 37p/180t rss 10.6G pss 9.1G swap 4.0G majflt 104090 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.2G pss 8.9G, 9 descendant rss 0.2G pss 0.1G | host avail 17.8G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 4.49/0.08 io 3.11 cpu 12.58 | cgroup 9.8G/max oom_kill 0 | free scratch 317.4G/45337520i tmp 29.7G/1017950i workspace 317.4G/45337520i | repeat-01 collected 26/26 workers (60602 items) tests 37712 done 3 failed | 24 in flight, oldest 313s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
................................................................ [1649%]
........................................................................ [1652%]
........................................................................ [1655%]
........................................................................ [1658%]
.........[contention-diag] +3693s soak 36p/180t rss 10.8G pss 9.3G swap 3.9G majflt 118827 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.3G pss 8.9G, 8 descendant rss 0.3G pss 0.2G | host avail 20.3G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 7.67/0.02 io 2.73 cpu 16.11 | cgroup 10.1G/max oom_kill 0 | free scratch 317.2G/45336650i tmp 29.7G/1017950i workspace 317.2G/45336650i | repeat-01 collected 26/26 workers (60602 items) tests 38020 done 3 failed | 23 in flight, oldest 290s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
............................................................... [1661%]
.........................................................[contention-diag] +3708s soak 36p/178t rss 10.7G pss 9.3G swap 3.9G majflt 119906 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.3G pss 9.0G, 8 descendant rss 0.3G pss 0.2G | host avail 18.6G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 2.59/0.0 io 1.21 cpu 11.54 | cgroup 10.1G/max oom_kill 0 | free scratch 316.7G/45335486i tmp 29.7G/1017950i workspace 316.7G/45335486i | repeat-01 collected 26/26 workers (60602 items) tests 38140 done 3 failed | 24 in flight, oldest 306s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
............... [1664%]
........................................................................ [1668%]
........................................................................ [1671%]
...[contention-diag] +3723s soak 36p/191t rss 10.8G pss 9.4G swap 3.8G majflt 127048 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.3G pss 9.0G, 8 descendant rss 0.2G pss 0.2G | host avail 27.8G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.82/0.0 io 0.6 cpu 10.62 | cgroup 10.2G/max oom_kill 0 | free scratch 316.3G/45334209i tmp 29.7G/1017949i workspace 316.3G/45334209i | repeat-01 collected 26/26 workers (60602 items) tests 38304 done 3 failed | 24 in flight, oldest 321s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
..................................................................... [1674%]
........................................................................ [1677%]
........................................................................ [1680%]
........................................................................ [1683%]
........................................................................ [1686%]
..........................[contention-diag] +3739s soak 33p/185t rss 10.8G pss 9.4G swap 3.7G majflt 142022 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.5G pss 9.1G, 5 descendant rss 0.2G pss 0.1G | host avail 27.5G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 1.77/0.67 io 1.08 cpu 12.67 | cgroup 10.2G/max oom_kill 0 | free scratch 316.3G/45332535i tmp 29.7G/1017949i workspace 316.3G/45332535i | scratch used 0.1G in 14985 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 38651 done 3 failed | 24 in flight, oldest 336s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
.............................................. [1690%]
........................................................................ [1693%]
........................................................................ [1696%]
........................................................................ [1699%]
........................................................................ [1702%]
........................................................................ [1705%]
........................[contention-diag] +3756s soak 35p/192t rss 10.9G pss 9.5G swap 3.6G majflt 155274 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.6G pss 9.2G, 7 descendant rss 0.2G pss 0.2G | host avail 24.9G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 3.8/0.11 io 0.71 cpu 18.74 | cgroup 10.4G/max oom_kill 0 | free scratch 316.2G/45331676i tmp 29.7G/1017948i workspace 316.2G/45331676i | repeat-01 collected 26/26 workers (60602 items) tests 39100 done 3 failed | 24 in flight, oldest 248s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................ [1708%]
........................................................................ [1712%]
........................................................................ [1715%]
........................................................................ [1718%]
........................................................................ [1721%]
........................................................................ [1724%]
.........[contention-diag] +3771s soak 34p/181t rss 11.0G pss 9.5G swap 3.5G majflt 157045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.6G pss 9.3G, 6 descendant rss 0.2G pss 0.1G | host avail 20.9G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 1.37/0.02 io 1.15 cpu 14.71 | cgroup 10.5G/max oom_kill 0 | free scratch 316.2G/45330246i tmp 29.7G/1017948i workspace 316.2G/45330246i | repeat-01 collected 26/26 workers (60602 items) tests 39512 done 3 failed | 23 in flight, oldest 263s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................................... [1727%]
........................................................................ [1730%]
........................................................................ [1734%]
........................................................................ [1737%]
...........................................[contention-diag] +3787s soak 36p/193t rss 11.2G pss 9.7G swap 3.4G majflt 176001 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 10.6G pss 9.3G, 8 descendant rss 0.3G pss 0.2G | host avail 20.5G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 5.01/0.0 io 1.95 cpu 14.95 | cgroup 10.7G/max oom_kill 0 | free scratch 316.2G/45328741i tmp 29.7G/1017946i workspace 316.2G/45328741i | repeat-01 collected 26/26 workers (60602 items) tests 39834 done 3 failed | 24 in flight, oldest 279s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................. [1740%]
........................................................................ [1743%]
........................................................................ [1746%]
........................................................................ [1749%]
........................................................................ [1752%]
..............................................................[contention-diag] +3802s soak 32p/202t rss 11.0G pss 9.6G swap 3.6G majflt 182712 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.1G, 4 descendant rss 0.2G pss 0.2G | host avail 19.2G/62.7G swapfree 49.7G/64.0G oom_kill +0 | psi10 mem 3.82/0.0 io 3.47 cpu 16.19 | cgroup 10.3G/max oom_kill 0 | free scratch 316.2G/45327490i tmp 29.7G/1017946i workspace 316.2G/45327490i | repeat-01 collected 26/26 workers (60602 items) tests 40217 done 3 failed | 24 in flight, oldest 294s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1756%]
........................................................................ [1759%]
........................................................................ [1762%]
........................................................................ [1765%]
.............................................[contention-diag] +3817s soak 36p/189t rss 11.1G pss 9.7G swap 3.6G majflt 193977 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.2G, 8 descendant rss 0.3G pss 0.3G | host avail 17.9G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 2.34/0.55 io 3.51 cpu 16.19 | cgroup 10.2G/max oom_kill 0 | free scratch 316.1G/45327137i tmp 29.7G/1017946i workspace 316.1G/45327137i | repeat-01 collected 26/26 workers (60602 items) tests 40499 done 3 failed | 24 in flight, oldest 309s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........................... [1768%]
........................................................................ [1771%]
........................................................................ [1774%]
........................................................................ [1778%]
........................................................................ [1781%]
........................................................................ [1784%]
..............................................[contention-diag] +3833s soak 36p/181t rss 11.1G pss 9.6G swap 3.7G majflt 197630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.4G pss 9.1G, 8 descendant rss 0.3G pss 0.3G | host avail 16.3G/62.7G swapfree 48.8G/64.0G oom_kill +0 | psi10 mem 1.23/0.13 io 6.75 cpu 12.4 | cgroup 10.2G/max oom_kill 0 | free scratch 315.9G/45324260i tmp 29.7G/1017947i workspace 315.9G/45324261i | repeat-01 collected 26/26 workers (60602 items) tests 40924 done 3 failed | 24 in flight, oldest 325s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [1787%]
........................................................................ [1790%]
........................................................................ [1793%]
........................................................................ [1796%]
........................................................................ [1800%]
..............................................................[contention-diag] +3848s soak 36p/186t rss 11.0G pss 9.5G swap 3.7G majflt 203135 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.1G, 8 descendant rss 0.2G pss 0.2G | host avail 18.2G/62.7G swapfree 48.8G/64.0G oom_kill +0 | psi10 mem 0.33/0.02 io 4.93 cpu 10.8 | cgroup 10.1G/max oom_kill 0 | free scratch 314.8G/45320484i tmp 29.7G/1017947i workspace 314.8G/45320484i | repeat-01 collected 26/26 workers (60602 items) tests 41307 done 3 failed | 23 in flight, oldest 340s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1803%]
........................................................................ [1806%]
........................................................................ [1809%]
........................................................................ [1812%]
.........................................................[contention-diag] +3864s soak 32p/176t rss 10.9G pss 9.4G swap 3.6G majflt 207586 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.1G, 4 descendant rss 0.1G pss 0.1G | host avail 20.8G/62.7G swapfree 48.6G/64.0G oom_kill +0 | psi10 mem 0.48/0.1 io 6.74 cpu 8.96 | cgroup 10.2G/max oom_kill 0 | free scratch 314.1G/45316063i tmp 29.7G/1017947i workspace 314.1G/45316063i | scratch used 0.1G in 9572 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 41549 done 3 failed | 24 in flight, oldest 355s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............... [1815%]
.....................................................s.................. [1818%]
........................................................................ [1821%]
........................................................................ [1825%]
........................................................................ [1828%]
.............................................[contention-diag] +3881s soak 34p/178t rss 11.1G pss 9.7G swap 3.5G majflt 225710 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.6G pss 9.3G, 6 descendant rss 0.2G pss 0.1G | host avail 29.0G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 1.07/0.01 io 6.8 cpu 11.37 | cgroup 10.5G/max oom_kill 0 | free scratch 313.7G/45314299i tmp 29.7G/1017941i workspace 313.7G/45314299i | repeat-01 collected 26/26 workers (60602 items) tests 41942 done 3 failed | 22 in flight, oldest 373s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........................... [1831%]
........................................................................ [1834%]
........................................................................ [1837%]
........................................................................ [1840%]
........................................................................ [1843%]
.......................................................................[contention-diag] +3896s soak 34p/172t rss 11.3G pss 9.8G swap 3.4G majflt 236539 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.7G pss 9.4G, 6 descendant rss 0.2G pss 0.2G | host avail 26.3G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 2.59/0.0 io 5.76 cpu 13.66 | cgroup 10.6G/max oom_kill 0 | free scratch 313.7G/45312817i tmp 29.7G/1017941i workspace 313.7G/45312817i | repeat-01 collected 26/26 workers (60602 items) tests 42326 done 3 failed | 24 in flight, oldest 388s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
. [1847%]
........................................................................ [1850%]
........................................................................ [1853%]
........................................................................ [1856%]
..[contention-diag] +3912s soak 35p/177t rss 11.3G pss 9.9G swap 3.4G majflt 247886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 7 descendant rss 0.2G pss 0.2G | host avail 23.4G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 2.17/0.0 io 3.87 cpu 9.33 | cgroup 10.7G/max oom_kill 0 | free scratch 313.5G/45310899i tmp 29.7G/1017939i workspace 313.5G/45310899i | repeat-01 collected 26/26 workers (60602 items) tests 42546 done 3 failed | 23 in flight, oldest 404s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
.......................................s.............................. [1859%]
........................................................................ [1862%]
........................................................................ [1865%]
...................[contention-diag] +3927s soak 35p/182t rss 11.4G pss 10.0G swap 3.3G majflt 258168 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.9G pss 9.5G, 7 descendant rss 0.2G pss 0.2G | host avail 23.4G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 1.92/0.0 io 3.92 cpu 12.31 | cgroup 10.8G/max oom_kill 0 | free scratch 313.5G/45304680i tmp 29.7G/1017939i workspace 313.5G/45304680i | repeat-01 collected 26/26 workers (60602 items) tests 42781 done 3 failed | 24 in flight, oldest 419s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
..................................................... [1869%]
...............................................................[contention-diag] +3943s soak 43p/207t rss 11.6G pss 10.0G swap 3.3G majflt 258991 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.9G pss 9.5G, 15 descendant rss 0.4G pss 0.2G | host avail 20.7G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 0.62/0.14 io 23.02 cpu 8.11 | cgroup 10.8G/max oom_kill 0 | free scratch 313.2G/45281370i tmp 29.7G/1017584i workspace 313.2G/45281369i | repeat-01 collected 26/26 workers (60602 items) tests 42901 done 3 failed | 24 in flight, oldest 434s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 9 hazardous kill call(s)
......... [1872%]
........................................................................ [1875%]
....................................................................[contention-diag] +3958s soak 39p/182t rss 10.9G pss 9.5G swap 3.8G majflt 259955 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.4G pss 9.0G, 11 descendant rss 0.2G pss 0.2G | host avail 17.3G/62.7G swapfree 48.2G/64.0G oom_kill +0 | psi10 mem 28.27/25.14 io 44.42 cpu 4.8 | cgroup 9.9G/max oom_kill 0 | free scratch 313.2G/45283361i tmp 29.7G/1017652i workspace 313.2G/45283361i | repeat-01 collected 26/26 workers (60602 items) tests 43042 done 3 failed | 24 in flight, oldest 274s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.... [1878%]
........................................................................ [1881%]
........................................................................ [1884%]
........................................................................ [1887%]
........................................................................ [1891%]
..............[contention-diag] +3973s soak 35p/200t rss 11.0G pss 9.5G swap 3.8G majflt 261603 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.4G pss 9.0G, 7 descendant rss 0.3G pss 0.2G | host avail 20.4G/62.7G swapfree 48.1G/64.0G oom_kill +0 | psi10 mem 7.28/6.43 io 19.48 cpu 10.34 | cgroup 10.0G/max oom_kill 0 | free scratch 313.2G/45280104i tmp 29.7G/1017885i workspace 313.2G/45280103i | repeat-01 collected 26/26 workers (60602 items) tests 43345 done 3 failed | 24 in flight, oldest 289s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................................... [1894%]
........................................................................ [1897%]
........................................................................ [1900%]
........................................................................ [1903%]
........................................................................ [1906%]
........................................................................ [1909%]
........................................................................ [1913%]
..............................................[contention-diag] +3989s soak 37p/191t rss 11.1G pss 9.6G swap 3.8G majflt 264351 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.1G, 9 descendant rss 0.3G pss 0.3G | host avail 19.3G/62.7G swapfree 48.1G/64.0G oom_kill +0 | psi10 mem 1.79/1.58 io 8.85 cpu 14.45 | cgroup 10.1G/max oom_kill 0 | free scratch 313.1G/45279625i tmp 29.7G/1017885i workspace 313.1G/45279625i | scratch used 0.1G in 14054 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 43817 done 3 failed | 23 in flight, oldest 304s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................... [1916%]
........................................................................ [1919%]
........................................................................ [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
........................................................................ [1931%]
.............[contention-diag] +4006s soak 34p/185t rss 11.2G pss 9.7G swap 3.8G majflt 265540 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.1G, 6 descendant rss 0.4G pss 0.3G | host avail 17.4G/62.7G swapfree 47.0G/64.0G oom_kill +0 | psi10 mem 1.9/1.6 io 10.14 cpu 13.38 | cgroup 10.2G/max oom_kill 0 | free scratch 312.8G/45278154i tmp 29.7G/1017898i workspace 312.8G/45278154i | repeat-01 collected 26/26 workers (60602 items) tests 44275 done 3 failed | 23 in flight, oldest 322s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................................... [1935%]
........................................................................ [1938%]
........................................................[contention-diag] +4021s soak 34p/192t rss 11.3G pss 9.8G swap 3.8G majflt 271447 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.5G pss 9.1G, 6 descendant rss 0.5G pss 0.4G | host avail 18.0G/62.7G swapfree 46.9G/64.0G oom_kill +0 | psi10 mem 0.53/0.36 io 8.79 cpu 10.29 | cgroup 10.5G/max oom_kill 0 | free scratch 312.1G/45277678i tmp 29.7G/1017913i workspace 312.1G/45277678i | repeat-01 collected 26/26 workers (60602 items) tests 44477 done 3 failed | 23 in flight, oldest 337s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................ [1941%]
........................................................................ [1944%]
........................................................................ [1947%]
........................................................................ [1950%]
........................................................................ [1953%]
..................[contention-diag] +4037s soak 39p/209t rss 11.4G pss 9.9G swap 3.7G majflt 277624 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.6G pss 9.2G, 11 descendant rss 0.6G pss 0.5G | host avail 25.0G/62.7G swapfree 46.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.09 io 6.61 cpu 10.82 | cgroup 10.6G/max oom_kill 0 | free scratch 312.1G/45276098i tmp 29.7G/1017913i workspace 312.1G/45276098i | repeat-01 collected 26/26 workers (60602 items) tests 44793 done 3 failed | 22 in flight, oldest 353s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................................... [1957%]
........................................................................ [1960%]
...................[contention-diag] +4052s soak 41p/205t rss 11.8G pss 10.3G swap 3.7G majflt 294445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.7G pss 9.3G, 13 descendant rss 0.8G pss 0.7G | host avail 25.7G/62.7G swapfree 46.8G/64.0G oom_kill +0 | psi10 mem 1.27/1.27 io 4.42 cpu 10.68 | cgroup 11.0G/max oom_kill 0 | free scratch 311.7G/45273273i tmp 29.7G/1017911i workspace 311.7G/45273273i | repeat-01 collected 26/26 workers (60602 items) tests 44940 done 3 failed | 23 in flight, oldest 368s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................... [1963%]
........................................................................ [1966%]
.........................................[contention-diag] +4068s soak 41p/208t rss 12.0G pss 10.4G swap 3.6G majflt 302588 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 13 descendant rss 0.9G pss 0.7G | host avail 32.5G/62.7G swapfree 46.8G/64.0G oom_kill +0 | psi10 mem 0.3/0.3 io 4.9 cpu 14.12 | cgroup 11.1G/max oom_kill 0 | free scratch 311.7G/45272337i tmp 29.7G/1017913i workspace 311.7G/45272337i | repeat-01 collected 26/26 workers (60602 items) tests 45109 done 3 failed | 23 in flight, oldest 383s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................... [1969%]
........................................................................ [1972%]
........................................................................ [1975%]
........................................................................ [1979%]
........................................................................ [1982%]
.........[contention-diag] +4083s soak 41p/199t rss 11.9G pss 10.4G swap 3.6G majflt 303446 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 13 descendant rss 0.8G pss 0.7G | host avail 30.0G/62.7G swapfree 46.8G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 5.92 cpu 13.89 | cgroup 11.2G/max oom_kill 0 | free scratch 316.7G/45276762i tmp 29.7G/1017912i workspace 316.7G/45276762i | repeat-01 collected 26/26 workers (60602 items) tests 45437 done 3 failed | 22 in flight, oldest 399s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................................... [1985%]
........................................................................ [1988%]
........................................................................ [1991%]
..................................[contention-diag] +4098s soak 40p/180t rss 11.9G pss 10.4G swap 3.5G majflt 304232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 12 descendant rss 0.8G pss 0.7G | host avail 30.8G/62.7G swapfree 46.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 6.32 cpu 19.03 | cgroup 11.2G/max oom_kill 0 | free scratch 316.7G/45275382i tmp 29.7G/1017912i workspace 316.7G/45275382i | repeat-01 collected 26/26 workers (60602 items) tests 45675 done 3 failed | 22 in flight, oldest 414s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................... [1994%]
........................................................................ [1997%]
........................................................................ [2001%]
........................................................................ [2004%]
........................................................................ [2007%]
........................................................................ [2010%]
.................................................................[contention-diag] +4114s soak 35p/163t rss 11.8G pss 10.3G swap 3.5G majflt 304706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 7 descendant rss 0.7G pss 0.6G | host avail 29.1G/62.7G swapfree 46.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.53 cpu 17.52 | cgroup 11.1G/max oom_kill 0 | free scratch 316.6G/45275019i tmp 29.7G/1017912i workspace 316.6G/45275019i | scratch used 0.1G in 21235 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 46082 done 3 failed | 21 in flight, oldest 429s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
....... [2013%]
........................................................................ [2016%]
........................................................................ [2019%]
........................................................................ [2023%]
........................................................................ [2026%]
........................................................................ [2029%]
............................................[contention-diag] +4131s soak 37p/176t rss 11.7G pss 10.2G swap 3.5G majflt 305774 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 9 descendant rss 0.6G pss 0.5G | host avail 25.1G/62.7G swapfree 46.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.87 cpu 14.53 | cgroup 11.1G/max oom_kill 0 | free scratch 316.7G/45274090i tmp 29.7G/1017912i workspace 316.7G/45274091i | repeat-01 collected 26/26 workers (60602 items) tests 46543 done 3 failed | 21 in flight, oldest 260s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................ [2032%]
........................................................................ [2035%]
........................................................................ [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
........................................................................ [2054%]
.........[contention-diag] +4146s soak 36p/168t rss 11.9G pss 10.3G swap 3.4G majflt 306623 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.9G pss 9.4G, 8 descendant rss 0.7G pss 0.6G | host avail 22.9G/62.7G swapfree 47.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.61 cpu 14.21 | cgroup 11.2G/max oom_kill 0 | free scratch 316.5G/45272884i tmp 29.7G/1017912i workspace 316.5G/45272884i | repeat-01 collected 26/26 workers (60602 items) tests 47080 done 3 failed | 19 in flight, oldest 275s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................... [2057%]
........................................................................ [2060%]
........................................................................ [2063%]
........................................................................ [2067%]
........................................................................ [2070%]
........................................................................ [2073%]
........................................................................ [2076%]
..........[contention-diag] +4162s soak 36p/176t rss 11.2G pss 9.7G swap 4.1G majflt 307791 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.3G pss 8.9G, 8 descendant rss 0.7G pss 0.6G | host avail 20.2G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 4.58/3.19 io 8.18 cpu 11.99 | cgroup 10.4G/max oom_kill 0 | free scratch 316.4G/45272190i tmp 29.7G/1017911i workspace 316.4G/45272190i | repeat-01 collected 26/26 workers (60602 items) tests 47576 done 3 failed | 17 in flight, oldest 290s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................................. [2079%]
........................................................................ [2082%]
........................................................................ [2085%]
..................................................................[contention-diag] +4177s soak 36p/185t rss 11.5G pss 10.0G swap 4.0G majflt 328881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.4G pss 9.0G, 8 descendant rss 0.8G pss 0.7G | host avail 23.8G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 2.69/0.78 io 6.04 cpu 14.17 | cgroup 10.7G/max oom_kill 0 | free scratch 316.0G/45270069i tmp 29.7G/1017908i workspace 316.0G/45270069i | repeat-01 collected 26/26 workers (60602 items) tests 47873 done 3 failed | 19 in flight, oldest 306s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...... [2089%]
........................................................................ [2092%]
........................................................................ [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
........................................[contention-diag] +4193s soak 39p/178t rss 11.6G pss 10.1G swap 3.9G majflt 347508 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.5G pss 9.1G, 11 descendant rss 0.9G pss 0.8G | host avail 21.4G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 3.92/0.15 io 3.43 cpu 12.77 | cgroup 10.9G/max oom_kill 0 | free scratch 315.8G/45274049i tmp 29.7G/1017908i workspace 315.8G/45274049i | repeat-01 collected 26/26 workers (60602 items) tests 48182 done 3 failed | 18 in flight, oldest 321s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................ [2104%]
........................................................................ [2107%]
........................................................................ [2110%]
........................................................................ [2114%]
........................................................................ [2117%]
........................................................................ [2120%]
........................................................................ [2123%]
................................[contention-diag] +4208s soak 38p/167t rss 11.8G pss 10.2G swap 3.7G majflt 370001 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.7G pss 9.2G, 10 descendant rss 0.8G pss 0.8G | host avail 20.8G/62.7G swapfree 46.2G/64.0G oom_kill +0 | psi10 mem 2.61/0.03 io 4.01 cpu 17.78 | cgroup 11.1G/max oom_kill 0 | free scratch 315.8G/45272589i tmp 29.7G/1017894i workspace 315.8G/45272589i | repeat-01 collected 26/26 workers (60602 items) tests 48704 done 3 failed | 19 in flight, oldest 337s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................................ [2126%]
................................................s....................... [2129%]
........................................................................ [2132%]
........................................................................ [2136%]
........................................................................ [2139%]
....................................................................[contention-diag] +4224s soak 40p/174t rss 12.0G pss 10.4G swap 3.7G majflt 370818 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.7G pss 9.3G, 12 descendant rss 1.0G pss 0.9G | host avail 20.1G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 1.18/0.19 io 5.0 cpu 15.06 | cgroup 11.2G/max oom_kill 0 | free scratch 315.5G/45271389i tmp 29.7G/1016721i workspace 315.5G/45271388i | repeat-01 collected 26/26 workers (60602 items) tests 49065 done 3 failed | 18 in flight, oldest 352s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.... [2142%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........................................................................ [2154%]
........................................................................ [2158%]
........................................................................ [2161%]
..........................[contention-diag] +4239s soak 42p/183t rss 12.1G pss 10.5G swap 3.7G majflt 371631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.7G pss 9.3G, 14 descendant rss 1.1G pss 1.0G | host avail 22.9G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 1.21/0.13 io 2.24 cpu 14.29 | cgroup 11.4G/max oom_kill 0 | free scratch 315.8G/45270087i tmp 29.7G/1016720i workspace 315.8G/45270087i | scratch used 0.2G in 39248 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 49522 done 3 failed | 19 in flight, oldest 367s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.............................................. [2164%]
........................................................................ [2167%]
........................................................................ [2170%]
........................................................................ [2173%]
........................................................................ [2176%]
........................................................................ [2180%]
..............................................................[contention-diag] +4256s soak 38p/177t rss 12.1G pss 10.6G swap 3.7G majflt 372126 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.7G pss 9.3G, 10 descendant rss 1.1G pss 1.0G | host avail 23.1G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.2/0.02 io 1.36 cpu 12.47 | cgroup 11.5G/max oom_kill 0 | free scratch 315.4G/45269383i tmp 29.7G/1016720i workspace 315.4G/45269383i | repeat-01 collected 26/26 workers (60602 items) tests 50023 done 3 failed | 18 in flight, oldest 385s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......... [2183%]
........................................................................ [2186%]
........................................................................ [2189%]
........................................................................ [2192%]
........................................................................ [2195%]
........................................................................ [2198%]
.......................................................................[contention-diag] +4272s soak 45p/198t rss 12.0G pss 10.4G swap 3.7G majflt 372527 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.7G pss 9.3G, 17 descendant rss 1.0G pss 0.9G | host avail 29.6G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 0.92 cpu 11.24 | cgroup 11.4G/max oom_kill 0 | free scratch 315.3G/45266438i tmp 29.7G/1016719i workspace 315.3G/45266438i | repeat-01 collected 26/26 workers (60602 items) tests 50466 done 3 failed | 18 in flight, oldest 400s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
. [2202%]
........................................................................ [2205%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
..............................................................s......... [2217%]
........................................................................ [2220%]
........................................................................ [2224%]
.............................................................[contention-diag] +4287s soak 36p/184t rss 11.9G pss 10.4G swap 3.7G majflt 373155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.7G pss 9.3G, 8 descendant rss 0.9G pss 0.8G | host avail 26.3G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.42/0.0 io 1.72 cpu 12.83 | cgroup 11.4G/max oom_kill 0 | free scratch 315.3G/45263776i tmp 29.7G/1016719i workspace 315.3G/45263776i | repeat-01 collected 26/26 workers (60602 items) tests 51028 done 3 failed | 17 in flight, oldest 416s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........... [2227%]
........................................................................ [2230%]
........................................................................ [2233%]
........................................................................ [2236%]
........................................................................ [2239%]
........................................................................ [2242%]
...................................................[contention-diag] +4302s soak 35p/183t rss 11.9G pss 10.4G swap 3.7G majflt 374512 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.8G pss 9.3G, 7 descendant rss 0.9G pss 0.8G | host avail 24.0G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.2/0.0 io 3.17 cpu 14.45 | cgroup 11.6G/max oom_kill 0 | free scratch 315.1G/45262647i tmp 29.7G/1016719i workspace 315.1G/45262647i | repeat-01 collected 26/26 workers (60602 items) tests 51440 done 3 failed | 18 in flight, oldest 431s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
..................... [2246%]
........................................................................ [2249%]
........................................................................ [2252%]
........................................................................ [2255%]
........................................................................ [2258%]
........................................................[contention-diag] +4318s soak 33p/163t rss 12.0G pss 10.5G swap 3.6G majflt 381628 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.8G pss 9.4G, 5 descendant rss 0.9G pss 0.9G | host avail 20.8G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 1.98/0.62 io 2.72 cpu 13.53 | cgroup 11.4G/max oom_kill 0 | free scratch 314.8G/45261068i tmp 29.7G/1016719i workspace 314.8G/45261068i | repeat-01 collected 26/26 workers (60602 items) tests 51760 done 3 failed | 18 in flight, oldest 446s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
........................................................................ [2274%]
........................................................................ [2277%]
........................................................................ [2280%]
........................................................................ [2283%]
........................................................................ [2286%]
........................................................................ [2290%]
........................................................................ [2293%]
........................................................................ [2296%]
..........................................[contention-diag] +4333s soak 37p/173t rss 12.1G pss 10.4G swap 3.6G majflt 389275 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.7G pss 9.2G, 9 descendant rss 1.0G pss 0.9G | host avail 18.9G/62.7G swapfree 45.8G/64.0G oom_kill +0 | psi10 mem 2.8/0.19 io 2.71 cpu 13.45 | cgroup 11.5G/max oom_kill 0 | free scratch 314.7G/45259494i tmp 29.7G/1016719i workspace 314.7G/45259494i | repeat-01 collected 26/26 workers (60602 items) tests 52672 done 3 failed | 18 in flight, oldest 462s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.............................. [2299%]
........................................................................ [2302%]
........................................................................ [2305%]
........................................................................ [2308%]
........................................................................ [2312%]
....................................[contention-diag] +4349s soak 37p/182t rss 12.0G pss 10.5G swap 3.8G majflt 403845 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.6G pss 9.2G, 9 descendant rss 1.1G pss 1.0G | host avail 21.7G/62.7G swapfree 45.4G/64.0G oom_kill +0 | psi10 mem 1.55/0.36 io 3.77 cpu 12.36 | cgroup 11.4G/max oom_kill 0 | free scratch 314.6G/45258422i tmp 29.7G/1016719i workspace 314.6G/45258422i | repeat-01 collected 26/26 workers (60602 items) tests 53019 done 3 failed | 16 in flight, oldest 477s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................... [2315%]
........................................................................ [2318%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2330%]
........................................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2340%]
........................................................................ [2343%]
..................[contention-diag] +4364s soak 34p/168t rss 11.9G pss 10.4G swap 3.8G majflt 404236 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.6G pss 9.2G, 6 descendant rss 1.0G pss 0.9G | host avail 18.6G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.38/0.08 io 3.6 cpu 14.05 | cgroup 11.3G/max oom_kill 0 | free scratch 314.5G/45258358i tmp 29.7G/1016717i workspace 314.5G/45258358i | scratch used 0.1G in 15892 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 53591 done 3 failed | 15 in flight, oldest 493s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
...................................................... [2346%]
........................................................................ [2349%]
........................................................................ [2352%]
........................................................................ [2356%]
........................................................................ [2359%]
........................................................................ [2362%]
........................................................................ [2365%]
[contention-diag] +4382s soak 35p/168t rss 11.9G pss 10.4G swap 3.8G majflt 404765 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 10.6G pss 9.2G, 7 descendant rss 1.0G pss 0.9G | host avail 19.6G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.25/0.2 io 4.53 cpu 13.58 | cgroup 11.0G/max oom_kill 0 | free scratch 314.0G/45256864i tmp 29.7G/1016719i workspace 314.0G/45256864i | repeat-01 collected 26/26 workers (60602 items) tests 54178 done 3 failed | 15 in flight, oldest 510s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................................................................ [2368%]
........................................................................ [2371%]
........................................................................ [2374%]
........................................................................ [2378%]
........................................................................ [2381%]
........................................................................ [2384%]
...........................................[contention-diag] +4397s soak 35p/168t rss 12.0G pss 10.4G swap 3.8G majflt 405252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.6G pss 9.2G, 7 descendant rss 1.0G pss 0.9G | host avail 19.3G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.1/0.03 io 4.53 cpu 13.38 | cgroup 11.0G/max oom_kill 0 | free scratch 313.8G/45255890i tmp 29.7G/1016719i workspace 313.8G/45255890i | repeat-01 collected 26/26 workers (60602 items) tests 54681 done 3 failed | 15 in flight, oldest 526s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................. [2387%]
........................................................................ [2390%]
........................................................................ [2393%]
........................................................................ [2396%]
................[contention-diag] +4412s soak 38p/174t rss 12.0G pss 10.4G swap 3.8G majflt 405652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.6G pss 9.1G, 10 descendant rss 1.1G pss 1.0G | host avail 21.6G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.2/0.0 io 4.68 cpu 11.49 | cgroup 10.9G/max oom_kill 0 | free scratch 313.0G/45254596i tmp 29.7G/1016719i workspace 313.0G/45254596i | repeat-01 collected 26/26 workers (60602 items) tests 54951 done 3 failed | 15 in flight, oldest 541s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................................................ [2400%]
........................................................................ [2403%]
........................................................................ [2406%]
........................................................................ [2409%]
........................................................................ [2412%]
........................................................................ [2415%]
.................................[contention-diag] +4428s soak 34p/154t rss 11.9G pss 10.4G swap 3.8G majflt 405979 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.6G pss 9.1G, 6 descendant rss 0.9G pss 0.9G | host avail 24.2G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 4.5 cpu 11.67 | cgroup 11.0G/max oom_kill 0 | free scratch 312.6G/45253809i tmp 29.7G/1016719i workspace 312.6G/45253809i | repeat-01 collected 26/26 workers (60602 items) tests 55396 done 3 failed | 15 in flight, oldest 556s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
....................................... [2418%]
........................................................................ [2421%]
........................................................................ [2425%]
......................................s.............[contention-diag] +4443s soak 38p/168t rss 12.0G pss 10.5G swap 3.8G majflt 406544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.6G pss 9.1G, 10 descendant rss 1.1G pss 1.0G | host avail 29.5G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.21/0.0 io 3.23 cpu 15.03 | cgroup 11.2G/max oom_kill 0 | free scratch 311.8G/45253683i tmp 29.7G/1016719i workspace 311.8G/45253683i | repeat-01 collected 26/26 workers (60602 items) tests 55635 done 3 failed | 14 in flight, oldest 572s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................... [2428%]
........................................................................ [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
.......................................................[contention-diag] +4458s soak 36p/158t rss 11.2G pss 9.7G swap 3.8G majflt 406776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.6G pss 9.1G, 8 descendant rss 0.2G pss 0.2G | host avail 29.2G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 4.39 cpu 18.47 | cgroup 10.5G/max oom_kill 0 | free scratch 311.8G/45253641i tmp 29.7G/1016718i workspace 311.8G/45253641i | repeat-01 collected 26/26 workers (60602 items) tests 55916 done 3 failed | 13 in flight, oldest 587s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................. [2440%]
........................................................................ [2443%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2453%]
........................................................................ [2456%]
........................s............................................... [2459%]
........................................................................ [2462%]
........................................................................ [2465%]
........................................................................ [2469%]
..............[contention-diag] +4474s soak 34p/160t rss 11.3G pss 9.7G swap 3.7G majflt 423403 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.7G pss 9.2G, 6 descendant rss 0.2G pss 0.2G | host avail 29.2G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.35 cpu 18.64 | cgroup 10.6G/max oom_kill 0 | free scratch 311.8G/45257207i tmp 29.7G/1016718i workspace 311.8G/45257207i | repeat-01 collected 26/26 workers (60602 items) tests 56577 done 3 failed | 11 in flight, oldest 123s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.......................................................... [2472%]
........................................................................ [2475%]
........................................................................ [2478%]
........................................................................ [2481%]
........................................................................ [2484%]
........................................................................ [2487%]
.......................................[contention-diag] +4489s soak 35p/163t rss 11.3G pss 9.8G swap 3.7G majflt 426958 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.7G pss 9.3G, 7 descendant rss 0.2G pss 0.2G | host avail 24.5G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.71 cpu 12.68 | cgroup 10.6G/max oom_kill 0 | free scratch 311.6G/45271574i tmp 29.7G/1016718i workspace 311.6G/45271574i | scratch used 0.1G in 8619 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 56997 done 3 failed | 10 in flight, oldest 117s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................................. [2491%]
........................................................................ [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2503%]
........................................................................ [2506%]
.................[contention-diag] +4507s soak 37p/177t rss 11.3G pss 9.8G swap 3.7G majflt 432505 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.8G pss 9.3G, 9 descendant rss 0.2G pss 0.1G | host avail 24.0G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.09/0.05 io 3.66 cpu 8.89 | cgroup 10.5G/max oom_kill 0 | free scratch 311.2G/45289310i tmp 29.7G/1016718i workspace 311.2G/45289310i | repeat-01 collected 26/26 workers (60602 items) tests 57449 done 3 failed | 9 in flight, oldest 66s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
....................................................... [2509%]
........................................................................ [2513%]
........................................................................ [2516%]
........................................................................ [2519%]
........................................................................ [2522%]
........................................................................ [2525%]
........................................................................ [2528%]
........................................................................ [2531%]
....................................................[contention-diag] +4522s soak 34p/168t rss 11.6G pss 10.0G swap 3.4G majflt 462993 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.0G pss 9.6G, 6 descendant rss 0.2G pss 0.1G | host avail 23.9G/62.7G swapfree 46.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 3.47 cpu 14.01 | cgroup 10.9G/max oom_kill 0 | free scratch 311.3G/45315741i tmp 29.7G/1016718i workspace 311.3G/45315741i | repeat-01 collected 26/26 workers (60602 items) tests 58062 done 3 failed | 10 in flight, oldest 81s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.................... [2535%]
........................................................................ [2538%]
........................................................................ [2541%]
........................................................................ [2544%]
........................................................................ [2547%]
.....................................................................[contention-diag] +4537s soak 37p/164t rss 11.6G pss 10.1G swap 3.4G majflt 463594 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.0G pss 9.6G, 9 descendant rss 0.2G pss 0.2G | host avail 22.3G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.17/0.16 io 4.45 cpu 15.07 | cgroup 11.1G/max oom_kill 0 | free scratch 311.3G/45337390i tmp 29.7G/1016716i workspace 311.3G/45337391i | repeat-01 collected 26/26 workers (60602 items) tests 58435 done 3 failed | 9 in flight, oldest 96s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
... [2550%]
........................................................................ [2553%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2563%]
........................................................................ [2566%]
........................................................................ [2569%]
.............................................[contention-diag] +4553s soak 38p/162t rss 11.5G pss 10.0G swap 3.5G majflt 463902 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.9G pss 9.5G, 10 descendant rss 0.2G pss 0.2G | host avail 27.2G/62.7G swapfree 46.0G/64.0G oom_kill +0 | psi10 mem 0.08/0.03 io 5.81 cpu 14.18 | cgroup 11.1G/max oom_kill 0 | free scratch 311.3G/45359864i tmp 29.7G/1016716i workspace 311.3G/45359865i | repeat-01 collected 26/26 workers (60602 items) tests 58923 done 3 failed | 9 in flight, oldest 112s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
........................... [2572%]
........................................................................ [2575%]
.............................................s.......................... [2579%]
........................................................................ [2582%]
........................................................................ [2585%]
..............................................[contention-diag] +4568s soak 36p/161t rss 11.5G pss 9.9G swap 3.5G majflt 464011 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 10.9G pss 9.5G, 8 descendant rss 0.2G pss 0.1G | host avail 25.7G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 27.43 cpu 6.15 | cgroup 11.1G/max oom_kill 0 | free scratch 311.2G/45349573i tmp 29.7G/1016716i workspace 311.2G/45349573i | repeat-01 collected 26/26 workers (60602 items) tests 59275 done 3 failed | 8 in flight, oldest 127s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.......................... [2588%]
........................................................................ [2591%]
........................................................................ [2594%]
........................................................................ [2597%]
........................................................................ [2601%]
........................................................................ [2604%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
............[contention-diag] +4583s soak 35p/168t rss 11.6G pss 10.1G swap 3.5G majflt 464248 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 10.9G pss 9.5G, 7 descendant rss 0.3G pss 0.2G | host avail 24.4G/62.7G swapfree 46.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 25.19 cpu 5.28 | cgroup 11.2G/max oom_kill 0 | free scratch 311.3G/45368019i tmp 29.7G/1016714i workspace 311.3G/45368019i | repeat-01 collected 26/26 workers (60602 items) tests 59907 done 3 failed | 9 in flight, oldest 142s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.............................................ssss........... [2616%]
........................................................................ [2619%]
........................................................................ [2623%]
......[contention-diag] +4599s soak 37p/167t rss 11.5G pss 9.9G swap 4.0G majflt 465153 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 10.5G pss 9.0G, 9 descendant rss 0.6G pss 0.5G | host avail 21.9G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 2.06/1.64 io 24.13 cpu 5.68 | cgroup 11.1G/max oom_kill 0 | free scratch 311.1G/45374278i tmp 29.7G/1016714i workspace 311.1G/45374278i | repeat-01 collected 26/26 workers (60602 items) tests 60125 done 3 failed | 6 in flight, oldest 158s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.................................................................. [2626%]
........................................................................ [2629%]
...............................................................[contention-diag] +4614s soak 34p/155t rss 10.6G pss 9.0G swap 4.6G majflt 465170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 9.9G pss 8.4G, 6 descendant rss 0.3G pss 0.2G | host avail 20.9G/62.7G swapfree 45.4G/64.0G oom_kill +0 | psi10 mem 2.33/1.7 io 11.71 cpu 6.22 | cgroup 10.4G/max oom_kill 0 | free scratch 310.8G/45386127i tmp 29.7G/1016714i workspace 310.8G/45386127i | scratch used 0.0G in 5694 entries (truncated) | repeat-01 collected 26/26 workers (60602 items) tests 60290 done 3 failed | 4 in flight, oldest 173s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
......... [2632%]
........................................................................ [2635%]
........................................................................ [2638%]
..............................................................[contention-diag] +4631s soak 33p/151t rss 10.5G pss 8.9G swap 4.5G majflt 465438 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 9.9G pss 8.4G, 5 descendant rss 0.2G pss 0.1G | host avail 24.1G/62.7G swapfree 45.6G/64.0G oom_kill +0 | psi10 mem 0.5/0.4 io 10.1 cpu 4.11 | cgroup 10.3G/max oom_kill 0 | free scratch 310.9G/45408599i tmp 29.7G/1016714i workspace 310.9G/45408599i | repeat-01 collected 26/26 workers (60602 items) tests 60542 done 3 failed | 2 in flight, oldest 6s gw9 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
.......... [2641%]
..................................................                       [100%][contention-diag] +4647s soak 32p/143t rss 10.2G pss 8.7G swap 4.6G majflt 470786 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 9.9G pss 8.4G, 4 descendant rss 0.0G pss 0.0G | host avail 22.0G/62.7G swapfree 47.7G/64.0G oom_kill +0 | psi10 mem 0.97/0.22 io 9.47 cpu 1.6 | cgroup 10.1G/max oom_kill 0 | free scratch 310.7G/45409871i tmp 29.7G/1016712i workspace 310.7G/45409871i | repeat-01 collected 26/26 workers (60602 items) tests 60591 done 3 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______ test_gated_muse_stream_reaches_mounted_session_current_turn_reply _______
[gw6] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fad21b285c0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw6/test_gated_muse_stream_reaches0')

    @pytest.mark.asyncio
    async def test_gated_muse_stream_reaches_mounted_session_current_turn_reply(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        container, _old, current = _build_mounted_session_agents(tmp_path)
        stream_dir = Path(current.artifacts_dir or "")
        monkeypatch.setenv("SASE_ARTIFACTS_DIR", str(stream_dir))
        patch_startup_loaders(monkeypatch, agents=[container])
    
        async with AcePage(
            query='"sess-stream"',
            patches=patches(),
        ) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_visual_idle(page)
            await page.press("j")
            await wait_for_visual_idle(page)
            panel = page.query_one_widget("#agent-prompt-panel", AgentPromptPanel)
            await wait_for_page(
                page,
                lambda: panel._live_reply_source is not None,
                "selected live reply source setup",
            )
            assert panel._live_reply_source is not None
            assert panel._live_reply_source.reply_identity == current.identity
>           await exercise_gated_stream(
                page,
                panel,
                monkeypatch,
                tmp_path,
                stream_dir,
                expected_identity=current.identity,
                expected_dir=stream_dir,
                # Session Reply cards also render per-turn phase dividers that
                # match the timestamp-divider pattern, so exact divider counts
                # are asserted on the single-agent shapes above. Here the
                # older/newer text singleton counts prove clean concatenation.
                expected_dividers=None,
                old_text="older completed turn text",
            )

tests/ace/tui/test_live_reply_follow_mounted_session.py:143: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

page = <sase.ace.testing.ace_page.AcePage object at 0x7fac871804d0>
panel = AgentPromptPanel(id='agent-prompt-panel', classes='-deck-source')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fad21b285c0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw6/test_gated_muse_stream_reaches0')
stream_dir = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw6/test_gated_muse_stream_reaches0/sess/current')

    async def exercise_gated_stream(
        page: AcePage,
        panel: AgentPromptPanel,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        stream_dir: Path,
        *,
        expected_identity: Any,
        expected_dir: Path,
        expected_dividers: int | None = 1,
        old_text: str | None = None,
    ) -> None:
        reply_path = stream_dir / "live_reply.md"
        timestamps_path = stream_dir / "live_reply_timestamps.jsonl"
        assert panel._live_reply_source is not None
        assert panel._live_reply_source.reply_identity == expected_identity
        assert panel._live_reply_source.reply_path.startswith(str(expected_dir))
        assert _contains_live_reply_region(
            panel._last_prompt_panel_content, expected_identity
        )
        if old_text is not None:
            assert old_text in reply_card_text(page)
    
        route_calls: list[tuple[Path, ...]] = []
        on_live_reply_artifact_change = panel.on_live_reply_artifact_change
    
        def track_live_reply_route(paths: tuple[Path, ...]) -> None:
            route_calls.append(paths)
            on_live_reply_artifact_change(paths)
    
        monkeypatch.setattr(panel, "on_live_reply_artifact_change", track_live_reply_route)
        await page.press("ctrl+j")
        await wait_for_visual_idle(page)
    
        refresh_calls: list[tuple[tuple[Any, ...], dict[str, Any]]] = []
        schedule_refresh = page.app._schedule_agents_async_refresh
    
        def track_refresh(*args: Any, **kwargs: Any) -> Any:
            refresh_calls.append((args, kwargs))
            return schedule_refresh(*args, **kwargs)
    
        monkeypatch.setattr(page.app, "_schedule_agents_async_refresh", track_refresh)
    
        # The session-log tail resolves its log through XDG_DATA_HOME in this
        # same process, so point it at a per-test fake home the fixture populates.
        xdg_home = tmp_path / "xdg-home"
        xdg_home.mkdir(exist_ok=True)
        monkeypatch.setenv("XDG_DATA_HOME", str(xdg_home))
    
        first_sent = tmp_path / "first-sent"
        release_second = tmp_path / "release-second"
        second_sent = tmp_path / "second-sent"
        release_terminal = tmp_path / "release-terminal"
        terminal_sent = tmp_path / "terminal-sent"
        process = subprocess.Popen(
            [
                sys.executable,
                "-u",
                "-c",
                gated_muse_script(),
                str(first_sent),
                str(release_second),
                str(second_sent),
                str(release_terminal),
                str(terminal_sent),
            ],
            stdin=subprocess.DEVNULL,
            stdout=subprocess.PIPE,
            stderr=subprocess.PIPE,
            text=True,
        )
        parser_task = asyncio.create_task(
            asyncio.to_thread(
                stream_and_parse_muse_json_output,
                process,
                suppress_output=True,
                session_id=MOUNTED_MUSE_SESSION_ID,
            )
        )
        try:
            await wait_for_page(page, first_sent.exists, "first commentary record")
            await wait_for_page(
                page,
                lambda: reply_path.read_text(encoding="utf-8").startswith(
                    MOUNTED_COMMENTARY_1
                ),
                "tail to append the first commentary chunk",
            )
>           assert process.poll() is None
                   ^^^^^^^^^^^^^^^^^^^^^^
E           AssertionError

tests/ace/tui/_live_reply_follow_mounted_helpers.py:302: AssertionError
_________ test_facade_try_disable_one_winner_under_process_contention __________
[gw14] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa7af382390>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw14/test_facade_try_disable_one_wi0')
registered_providers = None, real_provider_disable_reads = None

    def test_facade_try_disable_one_winner_under_process_contention(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        registered_providers: None,
        real_provider_disable_reads: None,
    ) -> None:
        monkeypatch.setenv("SASE_HOME", str(tmp_path))
        sibling = disable_provider("codex", 1_200.0, source="sibling", now=_NOW)
        start = tmp_path / "start"
        worker = tmp_path / "worker.py"
        worker.write_text(
            "\n".join(
                [
                    "import json, sys, time",
                    "from pathlib import Path",
                    "from sase.llm_provider.provider_disable import try_disable_provider",
                    f"start = Path({str(start)!r})",
                    "for _ in range(400):",
                    "    if start.exists():",
                    "        break",
                    "    time.sleep(0.005)",
                    "else:",
                    "    raise SystemExit('start file never appeared')",
                    "index = int(sys.argv[1])",
                    "outcome = try_disable_provider(",
                    '    "claude",',
                    "    60.0 + index,",
                    '    source=f"contender-{index}",',
                    f"    now={_NOW} + index,",
                    ")",
                    'print(json.dumps({"inserted": outcome.inserted, '
                    '"source": outcome.record.source}))',
                ]
            ),
            encoding="utf-8",
        )
        env = os.environ.copy()
        env["SASE_HOME"] = str(tmp_path)
        processes = [
            subprocess.Popen(
                [sys.executable, str(worker), str(index)],
                cwd=str(Path(__file__).resolve().parents[1]),
                env=env,
                text=True,
                stdout=subprocess.PIPE,
                stderr=subprocess.PIPE,
            )
            for index in range(6)
        ]
        start.write_text("go\n", encoding="utf-8")
        outcomes = []
        for process in processes:
>           stdout, stderr = process.communicate(timeout=10)
                             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_provider_disable.py:181: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:1209: in communicate
    stdout, stderr = self._communicate(input, endtime, timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:2116: in _communicate
    self._check_timeout(endtime, orig_timeout, stdout, stderr)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: None args: ['/tmp/sase-1rq-runtime-py312/bin/python', '/...>
endtime = 90007.956679124, orig_timeout = 10
stdout_seq = [b'{"inserted": false, "source": "contender-1"}\n']
stderr_seq = [], skip_check_and_raise = False

    def _check_timeout(self, endtime, orig_timeout, stdout_seq, stderr_seq,
                       skip_check_and_raise=False):
        """Convenience for checking if a timeout has expired."""
        if endtime is None:
            return
        if skip_check_and_raise or _time() > endtime:
>           raise TimeoutExpired(
                    self.args, orig_timeout,
                    output=b''.join(stdout_seq) if stdout_seq else None,
                    stderr=b''.join(stderr_seq) if stderr_seq else None)
E           subprocess.TimeoutExpired: Command '['/tmp/sase-1rq-runtime-py312/bin/python', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw14/test_facade_try_disable_one_wi0/worker.py', '0']' timed out after 10 seconds

../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:1253: TimeoutExpired
_____________________ test_descendant_processes_are_reaped _____________________
[gw12] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f84e1c7d700>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw12/test_descendant_processes_are_0')

    def test_descendant_processes_are_reaped(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pidfile = tmp_path / "child.pid"
        monkeypatch.setenv("SASE_CODEX_APP_SERVER_PIDFILE", str(pidfile))
        for deadline_seconds in hang_deadlines(1.5):
            context = _context(
                mode="descendants",
                monkeypatch=monkeypatch,
                deadline_seconds=deadline_seconds,
            )
            observation = collect_codex_usage(context)
            assert observation["outcome"] == "error"
            assert observation["reason_code"] == "timeout"
            if pidfile.exists():
                break
        child_pid = int(pidfile.read_text(encoding="utf-8"))
>       assert not _pid_alive(child_pid)
E       assert not True
E        +  where True = _pid_alive(2677914)

tests/llm_provider/test_codex_usage_probe.py:335: AssertionError
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

tests/ace/tui/command_line/test_run_policies.py::test_builtin_cd_submit_pins_and_renders_block
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/core/content_layout_wire.py:268: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    legacy=tuple(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_view_foundation.py::test_open_parks_inbox_and_blocks_detail
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:137: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return next(self.gen)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _recheck_grammar_key at 0x7fd9b59be680>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/modals/test_new_project_create_execution.py::test_create_review_renders_danger_heading_and_keep_notice
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/rich/text.py:144: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def __init__(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/keymaps/key_validation.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    return tuple(part.strip() for part in key.split(","))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    payload = binding(
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

tests/ace/tui/test_agent_runner_slots_eligibility.py::test_queued_rows_match_chip_header_summary_and_capacity_counts
  <string>:169: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1458361) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=1458660) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=1458253) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1458317) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:888: DeprecationWarning: This process (pid=1458253) is multi-threaded, use of fork() may lead to deadlocks in the child.

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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1459065) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
586.91s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
460.49s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
453.36s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
445.30s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
433.24s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
388.24s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
342.59s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
338.31s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
336.79s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
321.18s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
309.96s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
284.63s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
282.00s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
216.65s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
192.99s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
192.00s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
186.00s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
178.51s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
162.86s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
160.53s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
=========================== short test summary info ============================
FAILED tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
FAILED tests/test_provider_disable.py::test_facade_try_disable_one_winner_under_process_contention
FAILED tests/llm_provider/test_codex_usage_probe.py::test_descendant_processes_are_reaped
==== 3 failed, 60579 passed, 21 skipped, 111 warnings in 4659.30s (1:17:39) ====
[contention-diag] +4662s soak 2p/2t rss 0.4G pss 0.4G swap 0.1G majflt 52112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 30.6G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 4.24/0.71 io 6.47 cpu 5.93 | cgroup 1.7G/max oom_kill 0 | free scratch 310.6G/45409800i tmp 29.7G/1016714i workspace 310.6G/45409800i | repeat-01 collected 26/26 workers (60602 items) tests 60602 done 3 failed | 10 hazardous kill call(s)
[contention-diag] +4669s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 501 | 1 parent rss 0.0G pss 0.0G | host avail 33.1G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 1.9/0.32 io 7.06 cpu 2.66 | cgroup 1.4G/max oom_kill 0 | free scratch 310.5G/45409808i tmp 29.7G/1016714i workspace 310.5G/45409808i | repeat-01 collected 26/26 workers (60602 items) tests 60602 done 3 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4669s, 301 samples, 0 signal(s); peaks: cgroup_current 12.6G, min_free_scratch 310.5G, min_free_tmp 29.7G, min_free_workspace 310.5G, min_inodes_scratch 45253641, min_inodes_tmp 1016712, min_inodes_workspace 45253641, min_mem_available 15.2G, min_swap_free 45.4G, oom_kill_delta 0, pressure_memory_full 25.14, pswpin_delta 3020691, pswpout_delta 7130584, scratch_bytes 0.6G, soak_procs 45, soak_pss 11.4G, soak_rss 12.7G, soak_swap 4.6G, soak_threads 296

contention tally: 3 node(s) failed across 1 repeat(s) in 4669.1s; red repeats: 1
  1/1  tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply  (repeats 1)
  1/1  tests/llm_provider/test_codex_usage_probe.py::test_descendant_processes_are_reaped  (repeats 1)
  1/1  tests/test_provider_disable.py::test_facade_try_disable_one_winner_under_process_contention  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

