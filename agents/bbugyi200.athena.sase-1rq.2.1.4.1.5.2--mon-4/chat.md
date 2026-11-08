# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-4)

- **TIMESTAMP:** 2026-11-08 14:01:45 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-4

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after settle-pause, AcePage.press, and zsh PTY hang-guard repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 519765, sampler pid 519907 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-3836883-1794159766324459270.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 36.7G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.8 cpu 0.14 | cgroup 0.1G/max oom_kill 0 | free scratch 301.6G/45109190i tmp 29.4G/1011451i workspace 301.6G/45109190i | scratch used 0.1G in 16742 entries (truncated) | progress none yet
[contention-diag] +17s soak 28p/80t rss 2.2G pss 1.9G swap 0.0G majflt 138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.1G pss 1.8G | host avail 33.7G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 15.04 | cgroup 2.1G/max oom_kill 0 | free scratch 301.6G/45109112i tmp 29.4G/1011466i workspace 301.6G/45109112i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 3.4G pss 3.1G swap 1.0G majflt 489 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.3G pss 3.0G | host avail 35.9G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.52 cpu 15.42 | cgroup 3.3G/max oom_kill 0 | free scratch 301.6G/45109287i tmp 29.4G/1011479i workspace 301.6G/45109287i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +48s soak 28p/80t rss 4.5G pss 4.1G swap 1.3G majflt 495 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.4G pss 4.1G | host avail 33.9G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.1 cpu 17.33 | cgroup 4.4G/max oom_kill 0 | free scratch 301.6G/45109260i tmp 29.4G/1011479i workspace 301.6G/45109260i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +63s soak 28p/86t rss 5.3G pss 4.9G swap 1.2G majflt 825 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.2G pss 4.8G | host avail 33.1G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 23.18 | cgroup 5.3G/max oom_kill 0 | free scratch 301.6G/45108921i tmp 29.4G/1011477i workspace 301.6G/45108921i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/89t rss 6.0G pss 5.6G swap 1.3G majflt 959 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.9G pss 5.5G | host avail 32.5G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 24.13 | cgroup 6.1G/max oom_kill 0 | free scratch 301.6G/45108907i tmp 29.4G/1011477i workspace 301.6G/45108907i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +93s soak 28p/90t rss 6.5G pss 6.1G swap 1.3G majflt 960 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.4G pss 6.0G | host avail 31.5G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 1.3/1.3 io 0.15 cpu 22.77 | cgroup 6.7G/max oom_kill 0 | free scratch 301.6G/45108893i tmp 29.4G/1011477i workspace 301.6G/45108893i | repeat-01 collected 25/26 workers (58452 items) tests 0 done 0 failed
contention shards: 26 workers collected 60617 items in total (2020-2558 per worker)
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
........................................................................ [ 36%]
........................................................................ [ 39%]
..................[contention-diag] +108s soak 29p/114t rss 7.0G pss 6.5G swap 1.1G majflt 1999 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.8G pss 6.4G, 1 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 0.21 cpu 21.98 | cgroup 7.1G/max oom_kill 0 | free scratch 301.6G/45106907i tmp 29.4G/1011477i workspace 301.6G/45106907i | repeat-01 collected 26/26 workers (60617 items) tests 881 done 0 failed | 26 in flight, oldest 15s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
...................................................... [ 43%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
........................................................................ [ 56%]
...[contention-diag] +124s soak 29p/144t rss 7.4G pss 6.9G swap 1.1G majflt 2090 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.7G, 1 descendant rss 0.0G pss 0.0G | host avail 30.0G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.04 cpu 22.25 | cgroup 7.5G/max oom_kill 0 | free scratch 301.6G/45106100i tmp 29.4G/1011477i workspace 301.6G/45106100i | scratch used 0.2G in 39150 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 1205 done 0 failed | 26 in flight, oldest 30s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
..................................................................... [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 69%]
............[contention-diag] +141s soak 30p/165t rss 7.6G pss 7.1G swap 1.1G majflt 2198 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.9G, 2 descendant rss 0.1G pss 0.1G | host avail 31.1G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.24 cpu 23.67 | cgroup 7.8G/max oom_kill 0 | free scratch 301.6G/45104991i tmp 29.4G/1011477i workspace 301.6G/45104990i | repeat-01 collected 26/26 workers (60617 items) tests 1513 done 0 failed | 26 in flight, oldest 47s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
............................................................ [ 73%]
........................................................................ [ 76%]
........................................................................ [ 79%]
..............................................................[contention-diag] +156s soak 30p/170t rss 7.8G pss 7.3G swap 1.1G majflt 2289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.5G pss 7.0G, 2 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 23.73 | cgroup 8.0G/max oom_kill 0 | free scratch 301.6G/45104277i tmp 29.4G/1011477i workspace 301.6G/45104277i | repeat-01 collected 26/26 workers (60617 items) tests 1763 done 0 failed | 25 in flight, oldest 59s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
.......... [ 83%]
........................................................................ [ 86%]
....................................................................[contention-diag] +171s soak 33p/196t rss 8.0G pss 7.4G swap 1.1G majflt 2304 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.2G, 5 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 23.53 | cgroup 8.1G/max oom_kill 0 | free scratch 301.5G/45103804i tmp 29.4G/1011477i workspace 301.5G/45103804i | repeat-01 collected 26/26 workers (60617 items) tests 1940 done 0 failed | 26 in flight, oldest 74s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
.... [ 89%]
........................................................................ [ 93%]
..............................................................[contention-diag] +186s soak 38p/227t rss 8.2G pss 7.6G swap 1.1G majflt 2304 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.9G pss 7.4G, 10 descendant rss 0.2G pss 0.1G | host avail 31.5G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 21.57 | cgroup 8.3G/max oom_kill 0 | free scratch 301.5G/45103362i tmp 29.4G/1011476i workspace 301.5G/45103362i | repeat-01 collected 26/26 workers (60617 items) tests 2076 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......... [ 96%]
........................................................................ [ 99%]
........................................................................ [103%]
........................................................................ [106%]
........................................................................ [109%]
.......[contention-diag] +202s soak 36p/222t rss 8.4G pss 7.7G swap 1.1G majflt 2321 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.5G, 8 descendant rss 0.2G pss 0.1G | host avail 30.6G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.0 cpu 20.28 | cgroup 8.5G/max oom_kill 0 | free scratch 301.5G/45102644i tmp 29.4G/1011476i workspace 301.5G/45102644i | repeat-01 collected 26/26 workers (60617 items) tests 2380 done 0 failed | 26 in flight, oldest 84s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................. [113%]
...................[contention-diag] +217s soak 37p/210t rss 8.6G pss 8.0G swap 1.1G majflt 2357 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.2G pss 7.6G, 9 descendant rss 0.3G pss 0.2G | host avail 29.8G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.05 cpu 12.59 | cgroup 8.7G/max oom_kill 0 | free scratch 300.9G/45100424i tmp 29.4G/1011476i workspace 300.9G/45100424i | repeat-01 collected 26/26 workers (60617 items) tests 2461 done 0 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................... [116%]
........................................................................ [119%]
....................[contention-diag] +232s soak 36p/212t rss 8.8G pss 8.2G swap 1.1G majflt 2399 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.9G, 8 descendant rss 0.2G pss 0.2G | host avail 28.7G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.42/0.32 io 0.06 cpu 14.07 | cgroup 9.0G/max oom_kill 0 | free scratch 300.8G/45099848i tmp 29.4G/1011476i workspace 300.8G/45099848i | repeat-01 collected 26/26 workers (60617 items) tests 2609 done 0 failed | 26 in flight, oldest 114s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................... [123%]
........................................................................ [126%]
.......................................[contention-diag] +248s soak 35p/222t rss 8.7G pss 8.1G swap 1.0G majflt 2400 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 7 descendant rss 0.1G pss 0.1G | host avail 27.6G/62.7G swapfree 52.7G/64.0G oom_kill +0 | psi10 mem 0.08/0.06 io 1.11 cpu 15.43 | cgroup 8.9G/max oom_kill 0 | free scratch 306.7G/45134475i tmp 29.4G/1011474i workspace 306.7G/45134475i | scratch used 0.3G in 56372 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 2757 done 0 failed | 26 in flight, oldest 129s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................. [129%]
........................................................................ [133%]
........................................................................ [136%]
.....[contention-diag] +265s soak 36p/226t rss 8.9G pss 8.2G swap 1.0G majflt 2461 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 8 descendant rss 0.3G pss 0.2G | host avail 29.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.41 cpu 20.85 | cgroup 9.1G/max oom_kill 0 | free scratch 306.7G/45133947i tmp 29.4G/1011476i workspace 306.7G/45133947i | repeat-01 collected 26/26 workers (60617 items) tests 2947 done 0 failed | 25 in flight, oldest 147s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................... [139%]
........................................................................ [143%]
...................[contention-diag] +280s soak 31p/223t rss 8.9G pss 8.3G swap 1.0G majflt 2518 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 8.0G, 3 descendant rss 0.2G pss 0.2G | host avail 28.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.54/0.54 io 0.08 cpu 17.77 | cgroup 9.2G/max oom_kill 0 | free scratch 306.7G/45135493i tmp 29.4G/1011474i workspace 306.7G/45135493i | repeat-01 collected 26/26 workers (60617 items) tests 3111 done 0 failed | 25 in flight, oldest 162s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................... [146%]
..............................................[contention-diag] +295s soak 33p/239t rss 8.9G pss 8.2G swap 1.0G majflt 2520 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 32.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 0.01 cpu 21.4 | cgroup 9.1G/max oom_kill 0 | free scratch 306.8G/45135189i tmp 29.4G/1011476i workspace 306.8G/45135189i | repeat-01 collected 26/26 workers (60617 items) tests 3210 done 0 failed | 26 in flight, oldest 177s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................... [149%]
....[contention-diag] +311s soak 34p/250t rss 8.9G pss 8.3G swap 1.0G majflt 2520 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 6 descendant rss 0.1G pss 0.0G | host avail 31.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.0 cpu 23.76 | cgroup 9.2G/max oom_kill 0 | free scratch 306.8G/45135019i tmp 29.4G/1011476i workspace 306.8G/45135019i | repeat-01 collected 26/26 workers (60617 items) tests 3243 done 0 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..............................[contention-diag] +326s soak 35p/263t rss 9.1G pss 8.4G swap 1.0G majflt 2521 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 7 descendant rss 0.1G pss 0.1G | host avail 29.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 24.69 | cgroup 9.3G/max oom_kill 0 | free scratch 306.7G/45134865i tmp 29.4G/1011476i workspace 306.7G/45134865i | repeat-01 collected 26/26 workers (60617 items) tests 3272 done 0 failed | 26 in flight, oldest 208s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................... [152%]
........................................................................ [156%]
...............[contention-diag] +341s soak 34p/229t rss 9.2G pss 8.5G swap 1.0G majflt 2523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 30.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.22 | cgroup 9.4G/max oom_kill 0 | free scratch 306.7G/45134453i tmp 29.4G/1011476i workspace 306.7G/45134453i | repeat-01 collected 26/26 workers (60617 items) tests 3391 done 0 failed | 26 in flight, oldest 223s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................................................... [159%]
........................................................................ [162%]
..............[contention-diag] +356s soak 35p/252t rss 9.2G pss 8.6G swap 1.0G majflt 2530 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 7 descendant rss 0.1G pss 0.1G | host avail 29.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.93 | cgroup 9.5G/max oom_kill 0 | free scratch 306.7G/45134035i tmp 29.4G/1011476i workspace 306.7G/45134035i | repeat-01 collected 26/26 workers (60617 items) tests 3534 done 0 failed | 26 in flight, oldest 238s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................................................... [166%]
................................[contention-diag] +372s soak 35p/254t rss 9.3G pss 8.6G swap 1.0G majflt 2531 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 7 descendant rss 0.1G pss 0.0G | host avail 28.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.41 | cgroup 9.5G/max oom_kill 0 | free scratch 306.7G/45133713i tmp 29.4G/1011476i workspace 306.7G/45133713i | scratch used 0.4G in 73684 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 3631 done 0 failed | 26 in flight, oldest 254s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................ [169%]
...................................................................[contention-diag] +389s soak 36p/262t rss 9.5G pss 8.8G swap 1.0G majflt 2532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 8 descendant rss 0.2G pss 0.2G | host avail 26.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 23.18 | cgroup 9.8G/max oom_kill 0 | free scratch 306.7G/45133365i tmp 29.4G/1011476i workspace 306.7G/45133365i | repeat-01 collected 26/26 workers (60617 items) tests 3734 done 0 failed | 26 in flight, oldest 271s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [172%]
........................[contention-diag] +404s soak 39p/262t rss 9.5G pss 8.8G swap 1.0G majflt 2532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 11 descendant rss 0.2G pss 0.1G | host avail 25.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 23.92 | cgroup 9.8G/max oom_kill 0 | free scratch 306.7G/45133135i tmp 29.4G/1011476i workspace 306.7G/45133135i | repeat-01 collected 26/26 workers (60617 items) tests 3766 done 0 failed | 26 in flight, oldest 286s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................ [176%]
...............................................................[contention-diag] +420s soak 38p/246t rss 9.5G pss 8.8G swap 1.0G majflt 2532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 10 descendant rss 0.1G pss 0.0G | host avail 24.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.01 | cgroup 9.8G/max oom_kill 0 | free scratch 306.7G/45132541i tmp 29.4G/1011476i workspace 306.7G/45132541i | repeat-01 collected 26/26 workers (60617 items) tests 3871 done 0 failed | 26 in flight, oldest 302s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......... [179%]
................................................[contention-diag] +435s soak 39p/286t rss 9.6G pss 8.8G swap 1.0G majflt 2532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 11 descendant rss 0.1G pss 0.1G | host avail 24.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.97 | cgroup 9.8G/max oom_kill 0 | free scratch 306.7G/45132261i tmp 29.4G/1011476i workspace 306.7G/45132261i | repeat-01 collected 26/26 workers (60617 items) tests 3935 done 0 failed | 26 in flight, oldest 317s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................ [182%]
...................................................................[contention-diag] +450s soak 40p/284t rss 9.7G pss 9.0G swap 1.0G majflt 2532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 12 descendant rss 0.2G pss 0.1G | host avail 22.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.36 | cgroup 10.0G/max oom_kill 0 | free scratch 306.4G/45131919i tmp 29.4G/1011476i workspace 306.4G/45131919i | repeat-01 collected 26/26 workers (60617 items) tests 4017 done 0 failed | 26 in flight, oldest 332s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [186%]
........................................................................ [189%]
...............................................[contention-diag] +466s soak 37p/240t rss 9.7G pss 9.0G swap 1.0G majflt 2536 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 9 descendant rss 0.2G pss 0.2G | host avail 25.1G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.04 | cgroup 10.0G/max oom_kill 0 | free scratch 306.4G/45131414i tmp 29.4G/1011476i workspace 306.4G/45131414i | repeat-01 collected 26/26 workers (60617 items) tests 4127 done 0 failed | 26 in flight, oldest 347s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................... [192%]
................................................................[contention-diag] +481s soak 36p/247t rss 9.8G pss 9.1G swap 1.0G majflt 2571 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 8 descendant rss 0.2G pss 0.1G | host avail 28.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.46/0.46 io 0.0 cpu 21.88 | cgroup 10.1G/max oom_kill 0 | free scratch 306.4G/45131123i tmp 29.4G/1011476i workspace 306.4G/45131123i | repeat-01 collected 26/26 workers (60617 items) tests 4237 done 0 failed | 26 in flight, oldest 363s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........ [196%]
........................[contention-diag] +496s soak 35p/281t rss 9.8G pss 9.1G swap 1.0G majflt 2606 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 28.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.0 cpu 27.31 | cgroup 10.1G/max oom_kill 0 | free scratch 306.4G/45130870i tmp 29.4G/1011476i workspace 306.4G/45130870i | scratch used 0.5G in 90009 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 4268 done 0 failed | 26 in flight, oldest 378s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................ [199%]
........................................................................ [202%]
...................[contention-diag] +514s soak 31p/253t rss 9.8G pss 9.1G swap 1.0G majflt 2608 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 3 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.25 cpu 27.23 | cgroup 10.2G/max oom_kill 0 | free scratch 305.9G/45127007i tmp 29.4G/1011476i workspace 305.9G/45127007i | repeat-01 collected 26/26 workers (60617 items) tests 4405 done 0 failed | 26 in flight, oldest 395s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................[contention-diag] +529s soak 29p/242t rss 9.8G pss 9.1G swap 1.0G majflt 2608 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 1 descendant rss 0.1G pss 0.1G | host avail 28.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 26.82 | cgroup 10.2G/max oom_kill 0 | free scratch 305.9G/45126833i tmp 29.4G/1011476i workspace 305.9G/45126833i | repeat-01 collected 26/26 workers (60617 items) tests 4436 done 0 failed | 26 in flight, oldest 411s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................ [206%]
[contention-diag] +544s soak 29p/251t rss 9.7G pss 9.1G swap 1.0G majflt 2609 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 28.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 23.7 | cgroup 10.2G/max oom_kill 0 | free scratch 305.9G/45126646i tmp 29.4G/1011476i workspace 305.9G/45126646i | repeat-01 collected 26/26 workers (60617 items) tests 4463 done 0 failed | 26 in flight, oldest 49s gw17 tests/ace/tui/command_line/test_transcript_scroll.py::test_block_nav_scrolls_selection_into_view
..................................................[contention-diag] +559s soak 30p/233t rss 9.9G pss 9.2G swap 1.0G majflt 2630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 29.1G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 28.35 | cgroup 10.3G/max oom_kill 0 | free scratch 305.9G/45126378i tmp 29.4G/1011476i workspace 305.9G/45126378i | repeat-01 collected 26/26 workers (60617 items) tests 4509 done 0 failed | 26 in flight, oldest 64s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...................... [209%]
................................................................[contention-diag] +575s soak 31p/238t rss 9.9G pss 9.3G swap 1.0G majflt 2630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 3 descendant rss 0.1G pss 0.1G | host avail 29.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.42 | cgroup 10.4G/max oom_kill 0 | free scratch 305.9G/45126083i tmp 29.4G/1011476i workspace 305.9G/45126083i | repeat-01 collected 26/26 workers (60617 items) tests 4589 done 0 failed | 25 in flight, oldest 80s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
........ [212%]
.....................................................[contention-diag] +590s soak 28p/243t rss 9.8G pss 9.2G swap 1.0G majflt 2630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 28.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.83 | cgroup 10.3G/max oom_kill 0 | free scratch 305.9G/45125758i tmp 29.4G/1011476i workspace 305.9G/45125758i | repeat-01 collected 26/26 workers (60617 items) tests 4657 done 0 failed | 26 in flight, oldest 95s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
................... [216%]
..[contention-diag] +605s soak 28p/235t rss 9.9G pss 9.2G swap 1.0G majflt 2630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 26.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.64 | cgroup 10.3G/max oom_kill 0 | free scratch 305.9G/45125602i tmp 29.4G/1011476i workspace 305.9G/45125602i | repeat-01 collected 26/26 workers (60617 items) tests 4682 done 0 failed | 26 in flight, oldest 77s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_escape_restores_the_prior_committed_query
..............................[contention-diag] +620s soak 29p/240t rss 10.0G pss 9.3G swap 1.0G majflt 2631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 1 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.69 | cgroup 10.4G/max oom_kill 0 | free scratch 305.9G/45125444i tmp 29.4G/1011476i workspace 305.9G/45125444i | scratch used 0.6G in 102713 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 4711 done 0 failed | 26 in flight, oldest 46s gw18 tests/ace/tui/command_line/test_policy_io.py::test_poll_once_ticks_submitting_without_log_read
.................................[contention-diag] +638s soak 29p/247t rss 10.0G pss 9.3G swap 1.0G majflt 2631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 34.75 | cgroup 10.5G/max oom_kill 0 | free scratch 305.9G/45125225i tmp 29.4G/1011476i workspace 305.9G/45125225i | repeat-01 collected 26/26 workers (60617 items) tests 4743 done 0 failed | 26 in flight, oldest 60s gw19 tests/ace/tui/test_agent_grouping_picker.py::test_agents_default_oo_toggles_panel_layout_once_and_preserves_mode
....... [219%]
.................................................................[contention-diag] +653s soak 28p/244t rss 10.0G pss 9.4G swap 1.0G majflt 2631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 29.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 33.47 | cgroup 10.5G/max oom_kill 0 | free scratch 305.9G/45124942i tmp 29.4G/1011476i workspace 305.9G/45124942i | repeat-01 collected 26/26 workers (60617 items) tests 4813 done 0 failed | 26 in flight, oldest 53s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
....... [222%]
......................[contention-diag] +668s soak 28p/254t rss 10.0G pss 9.4G swap 1.0G majflt 2631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G | host avail 28.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 0.0 cpu 30.47 | cgroup 10.5G/max oom_kill 0 | free scratch 305.9G/45124743i tmp 29.4G/1011476i workspace 305.9G/45124743i | repeat-01 collected 26/26 workers (60617 items) tests 4845 done 0 failed | 26 in flight, oldest 68s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
...................[contention-diag] +684s soak 30p/255t rss 10.2G pss 9.5G swap 1.0G majflt 2631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 2 descendant rss 0.1G pss 0.1G | host avail 28.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.0 cpu 28.16 | cgroup 10.6G/max oom_kill 0 | free scratch 305.9G/45124574i tmp 29.4G/1011476i workspace 305.9G/45124574i | repeat-01 collected 26/26 workers (60617 items) tests 4862 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...........................[contention-diag] +699s soak 29p/243t rss 10.2G pss 9.5G swap 1.0G majflt 2636 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.1G pss 0.1G | host avail 28.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.01 | cgroup 10.7G/max oom_kill 0 | free scratch 305.9G/45124371i tmp 29.4G/1011476i workspace 305.9G/45124371i | repeat-01 collected 26/26 workers (60617 items) tests 4889 done 0 failed | 26 in flight, oldest 68s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_picker_acts_on_focused_split_panel
.... [226%]
......[contention-diag] +714s soak 28p/259t rss 10.1G pss 9.5G swap 1.0G majflt 2636 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G | host avail 28.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.73 | cgroup 10.7G/max oom_kill 0 | free scratch 305.9G/45124225i tmp 29.4G/1011476i workspace 305.9G/45124225i | repeat-01 collected 26/26 workers (60617 items) tests 4902 done 0 failed | 26 in flight, oldest 70s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
.................[contention-diag] +729s soak 28p/235t rss 10.1G pss 9.5G swap 1.0G majflt 2637 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 27.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.75 | cgroup 10.7G/max oom_kill 0 | free scratch 305.9G/45124000i tmp 29.4G/1011476i workspace 305.9G/45124000i | repeat-01 collected 26/26 workers (60617 items) tests 4919 done 0 failed | 26 in flight, oldest 52s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
................................................. [229%]
..........................................[contention-diag] +745s soak 31p/249t rss 10.3G pss 9.6G swap 1.0G majflt 2638 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 3 descendant rss 0.1G pss 0.1G | host avail 29.0G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.54 | cgroup 10.8G/max oom_kill 0 | free scratch 305.9G/45123803i tmp 29.4G/1011476i workspace 305.9G/45123803i | scratch used 0.7G in 116516 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 4969 done 0 failed | 26 in flight, oldest 58s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
.............................. [232%]
.........................................................[contention-diag] +762s soak 29p/224t rss 10.3G pss 9.6G swap 1.0G majflt 2638 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.1G pss 0.0G | host avail 27.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 29.85 | cgroup 10.9G/max oom_kill 0 | free scratch 305.9G/45123402i tmp 29.4G/1011476i workspace 305.9G/45123402i | repeat-01 collected 26/26 workers (60617 items) tests 5089 done 0 failed | 26 in flight, oldest 58s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_real_R_press_reruns_declined_and_notices_otherwise
............... [236%]
........................................................................ [239%]
........................................................................ [242%]
................................................................[contention-diag] +777s soak 28p/212t rss 10.3G pss 9.6G swap 1.0G majflt 2638 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 25.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 27.55 | cgroup 10.9G/max oom_kill 0 | free scratch 305.9G/45122783i tmp 29.4G/1011476i workspace 305.9G/45122783i | repeat-01 collected 26/26 workers (60617 items) tests 5307 done 0 failed | 26 in flight, oldest 43s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........ [246%]
........................................................................ [249%]
................................[contention-diag] +792s soak 28p/267t rss 10.3G pss 9.7G swap 1.0G majflt 2638 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 29.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.32 | cgroup 10.9G/max oom_kill 0 | free scratch 305.9G/45122370i tmp 29.4G/1011476i workspace 305.9G/45122370i | repeat-01 collected 26/26 workers (60617 items) tests 5431 done 0 failed | 25 in flight, oldest 59s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................ [252%]
...............................................[contention-diag] +808s soak 31p/270t rss 10.4G pss 9.8G swap 1.0G majflt 2645 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G, 3 descendant rss 0.1G pss 0.1G | host avail 27.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.41 | cgroup 11.0G/max oom_kill 0 | free scratch 305.9G/45122035i tmp 29.4G/1011476i workspace 305.9G/45122035i | repeat-01 collected 26/26 workers (60617 items) tests 5514 done 0 failed | 26 in flight, oldest 74s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
......................... [256%]
........................................................................ [259%]
..........[contention-diag] +823s soak 31p/246t rss 10.4G pss 9.7G swap 1.0G majflt 2656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 3 descendant rss 0.1G pss 0.0G | host avail 27.1G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.57 | cgroup 11.1G/max oom_kill 0 | free scratch 305.9G/45121665i tmp 29.4G/1011476i workspace 305.9G/45121665i | repeat-01 collected 26/26 workers (60617 items) tests 5614 done 0 failed | 26 in flight, oldest 89s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...............[contention-diag] +838s soak 30p/262t rss 10.5G pss 9.8G swap 1.0G majflt 2656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.46 | cgroup 11.1G/max oom_kill 0 | free scratch 305.9G/45121486i tmp 29.4G/1011476i workspace 305.9G/45121486i | repeat-01 collected 26/26 workers (60617 items) tests 5639 done 0 failed | 26 in flight, oldest 105s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...............................[contention-diag] +854s soak 29p/257t rss 10.4G pss 9.8G swap 1.0G majflt 2656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 29.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.25 | cgroup 11.1G/max oom_kill 0 | free scratch 305.9G/45121298i tmp 29.4G/1011476i workspace 305.9G/45121298i | repeat-01 collected 26/26 workers (60617 items) tests 5672 done 0 failed | 26 in flight, oldest 120s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................ [262%]
...............................................................[contention-diag] +869s soak 30p/251t rss 10.5G pss 9.9G swap 1.0G majflt 2656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 0.0 cpu 29.08 | cgroup 11.2G/max oom_kill 0 | free scratch 305.9G/45121005i tmp 29.4G/1011476i workspace 305.9G/45121005i | scratch used 0.7G in 129996 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 5742 done 0 failed | 26 in flight, oldest 135s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
......... [266%]
....................................[contention-diag] +886s soak 29p/232t rss 10.6G pss 9.9G swap 1.0G majflt 2656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 1 descendant rss 0.1G pss 0.1G | host avail 28.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.04 cpu 26.1 | cgroup 11.2G/max oom_kill 0 | free scratch 305.9G/45120739i tmp 29.4G/1011476i workspace 305.9G/45120739i | repeat-01 collected 26/26 workers (60617 items) tests 5787 done 0 failed | 26 in flight, oldest 68s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_toggle_clamps_container_and_restores_width
.................................... [269%]
........................................................................ [272%]
.............[contention-diag] +902s soak 29p/249t rss 10.6G pss 9.9G swap 1.0G majflt 2659 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 1 descendant rss 0.1G pss 0.0G | host avail 26.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 27.32 | cgroup 11.2G/max oom_kill 0 | free scratch 305.9G/45120338i tmp 29.4G/1011476i workspace 305.9G/45120338i | repeat-01 collected 26/26 workers (60617 items) tests 5910 done 0 failed | 26 in flight, oldest 65s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
........................................................... [276%]
........................................................................ [279%]
........................................................................ [282%]
................[contention-diag] +917s soak 30p/229t rss 10.6G pss 9.9G swap 1.0G majflt 2658 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 2 descendant rss 0.0G pss 0.0G | host avail 24.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.73 | cgroup 11.2G/max oom_kill 0 | free scratch 305.9G/45119498i tmp 29.4G/1011476i workspace 305.9G/45119498i | repeat-01 collected 26/26 workers (60617 items) tests 6120 done 0 failed | 26 in flight, oldest 80s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
........................................................ [286%]
........................................................................ [289%]
..........................................................[contention-diag] +932s soak 29p/215t rss 10.7G pss 10.0G swap 1.0G majflt 2662 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G, 1 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.81 | cgroup 11.3G/max oom_kill 0 | free scratch 305.9G/45118969i tmp 29.4G/1011476i workspace 305.9G/45118969i | repeat-01 collected 26/26 workers (60617 items) tests 6317 done 0 failed | 26 in flight, oldest 58s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_menu_moves_with_fixed_arrows_when_history_rebound
.............. [292%]
........................................................................ [295%]
....[contention-diag] +947s soak 28p/218t rss 10.6G pss 10.0G swap 1.0G majflt 2662 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G | host avail 22.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.92 | cgroup 11.3G/max oom_kill 0 | free scratch 305.8G/45118625i tmp 29.4G/1011476i workspace 305.8G/45118625i | repeat-01 collected 26/26 workers (60617 items) tests 6411 done 0 failed | 25 in flight, oldest 51s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
.................................................................... [299%]
..................................................[contention-diag] +963s soak 29p/241t rss 10.7G pss 10.0G swap 1.0G majflt 2699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 26.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.9 | cgroup 11.3G/max oom_kill 0 | free scratch 305.4G/45118231i tmp 29.4G/1011476i workspace 305.4G/45118231i | repeat-01 collected 26/26 workers (60617 items) tests 6520 done 0 failed | 26 in flight, oldest 66s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
...................... [302%]
...........................................................[contention-diag] +978s soak 30p/240t rss 10.7G pss 10.0G swap 1.0G majflt 2699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 2 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.93 | cgroup 11.3G/max oom_kill 0 | free scratch 305.9G/45117959i tmp 29.4G/1011476i workspace 305.9G/45117959i | repeat-01 collected 26/26 workers (60617 items) tests 6608 done 0 failed | 26 in flight, oldest 62s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
............. [305%]
................................................[contention-diag] +993s soak 29p/213t rss 10.8G pss 10.1G swap 1.0G majflt 2702 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G, 1 descendant rss 0.1G pss 0.0G | host avail 27.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.96 | cgroup 11.4G/max oom_kill 0 | free scratch 305.8G/45116692i tmp 29.4G/1011476i workspace 305.8G/45116692i | scratch used 0.7G in 133294 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 6668 done 0 failed | 26 in flight, oldest 41s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_sidecar_stitch_context_carries_sidecar_true
........................ [309%]
...........................................................[contention-diag] +1011s soak 29p/220t rss 10.8G pss 10.1G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.1G pss 0.0G | host avail 26.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 16.54 | cgroup 11.4G/max oom_kill 0 | free scratch 305.2G/45115411i tmp 29.4G/1011476i workspace 305.2G/45115411i | repeat-01 collected 26/26 workers (60617 items) tests 6754 done 0 failed | 26 in flight, oldest 44s gw4 tests/ace/tui/test_artifacts_files_loading.py::test_hydrate_ref_resolves_exact_file_by_logical_id
............. [312%]
........................................[contention-diag] +1026s soak 28p/248t rss 10.8G pss 10.1G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G | host avail 25.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 21.64 | cgroup 11.4G/max oom_kill 0 | free scratch 305.2G/45115219i tmp 29.4G/1011476i workspace 305.2G/45115219i | repeat-01 collected 26/26 workers (60617 items) tests 6806 done 0 failed | 26 in flight, oldest 53s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
................................ [315%]
........................................................................ [319%]
..........................................................[contention-diag] +1041s soak 29p/227t rss 10.8G pss 10.1G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 23.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 21.02 | cgroup 11.5G/max oom_kill 0 | free scratch 305.2G/45114695i tmp 29.4G/1011475i workspace 305.2G/45114695i | repeat-01 collected 26/26 workers (60617 items) tests 6969 done 0 failed | 26 in flight, oldest 69s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
.............. [322%]
........................................................................ [325%]
..........[contention-diag] +1057s soak 30p/220t rss 10.9G pss 10.2G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 21.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.13 | cgroup 11.5G/max oom_kill 0 | free scratch 305.2G/45114325i tmp 29.4G/1011476i workspace 305.2G/45114325i | repeat-01 collected 26/26 workers (60617 items) tests 7057 done 0 failed | 26 in flight, oldest 41s gw4 tests/ace/tui/test_artifacts_files_loading.py::test_hydrate_ref_reports_absent_for_unknown_logical_id
...................................[contention-diag] +1072s soak 30p/231t rss 11.0G pss 10.2G swap 1.0G majflt 2708 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 19.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.39/0.21 io 3.08 cpu 15.79 | cgroup 11.5G/max oom_kill 0 | free scratch 307.3G/45116057i tmp 29.4G/1011476i workspace 307.3G/45116057i | repeat-01 collected 26/26 workers (60617 items) tests 7101 done 0 failed | 26 in flight, oldest 51s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
........................... [329%]
........................................................................ [332%]
.......[contention-diag] +1087s soak 29p/243t rss 10.9G pss 10.2G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 15.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.34/0.22 io 2.24 cpu 14.79 | cgroup 11.5G/max oom_kill 0 | free scratch 307.3G/45115725i tmp 29.4G/1011476i workspace 307.3G/45115725i | repeat-01 collected 26/26 workers (60617 items) tests 7207 done 0 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................................................................. [335%]
...........................[contention-diag] +1103s soak 29p/235t rss 10.9G pss 10.2G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 16.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.05 io 1.19 cpu 13.02 | cgroup 11.3G/max oom_kill 0 | free scratch 306.9G/45115430i tmp 29.4G/1011476i workspace 306.9G/45115430i | repeat-01 collected 26/26 workers (60617 items) tests 7288 done 0 failed | 26 in flight, oldest 60s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
............................................. [339%]
........................................................................ [342%]
...................................................................[contention-diag] +1118s soak 28p/231t rss 10.9G pss 10.2G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G | host avail 19.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.41 cpu 16.09 | cgroup 11.2G/max oom_kill 0 | free scratch 307.0G/45114950i tmp 29.4G/1011476i workspace 307.0G/45114950i | scratch used 0.3G in 42298 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 7455 done 0 failed | 26 in flight, oldest 75s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
..... [345%]
........................................................................ [349%]
..............................[contention-diag] +1135s soak 28p/241t rss 10.9G pss 10.2G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G | host avail 26.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 22.43 | cgroup 11.3G/max oom_kill 0 | free scratch 307.0G/45114599i tmp 29.4G/1011476i workspace 307.0G/45114599i | repeat-01 collected 26/26 workers (60617 items) tests 7587 done 0 failed | 26 in flight, oldest 47s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......................................... [352%]
........................................................................ [355%]
......[contention-diag] +1151s soak 38p/292t rss 11.0G pss 10.3G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 27.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 26.09 | cgroup 11.4G/max oom_kill 0 | free scratch 307.0G/45114229i tmp 29.4G/1011476i workspace 307.0G/45114229i | repeat-01 collected 26/26 workers (60617 items) tests 7710 done 0 failed | 26 in flight, oldest 62s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
............................[contention-diag] +1166s soak 38p/270t rss 11.1G pss 10.3G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 26.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 24.46 | cgroup 11.4G/max oom_kill 0 | free scratch 307.0G/45113923i tmp 29.4G/1011476i workspace 307.0G/45113923i | repeat-01 collected 26/26 workers (60617 items) tests 7731 done 0 failed | 26 in flight, oldest 77s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.....[contention-diag] +1181s soak 38p/289t rss 11.1G pss 10.3G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 26.9G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.22/0.22 io 0.22 cpu 22.99 | cgroup 11.3G/max oom_kill 0 | free scratch 307.0G/45113822i tmp 29.4G/1011476i workspace 307.0G/45113822i | repeat-01 collected 26/26 workers (60617 items) tests 7743 done 0 failed | 26 in flight, oldest 93s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................................. [359%]
.[contention-diag] +1196s soak 39p/277t rss 11.1G pss 10.3G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 11 descendant rss 0.1G pss 0.0G | host avail 27.0G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.04 cpu 24.19 | cgroup 11.3G/max oom_kill 0 | free scratch 307.0G/45113648i tmp 29.4G/1011476i workspace 307.0G/45113648i | repeat-01 collected 26/26 workers (60617 items) tests 7776 done 0 failed | 26 in flight, oldest 108s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
....................................[contention-diag] +1212s soak 39p/278t rss 11.2G pss 10.5G swap 1.0G majflt 2726 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 11 descendant rss 0.2G pss 0.1G | host avail 26.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.38 | cgroup 11.4G/max oom_kill 0 | free scratch 307.0G/45113482i tmp 29.4G/1011476i workspace 307.0G/45113482i | repeat-01 collected 26/26 workers (60617 items) tests 7807 done 0 failed | 26 in flight, oldest 123s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................................... [362%]
........................................................[contention-diag] +1227s soak 38p/257t rss 11.1G pss 10.3G swap 1.0G majflt 2706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 25.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.96 | cgroup 11.3G/max oom_kill 0 | free scratch 307.0G/45113122i tmp 29.4G/1011476i workspace 307.0G/45113122i | repeat-01 collected 26/26 workers (60617 items) tests 7899 done 0 failed | 26 in flight, oldest 66s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
................ [365%]
...................................................................[contention-diag] +1242s soak 38p/252t rss 11.1G pss 10.4G swap 1.0G majflt 2711 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 26.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.47 | cgroup 11.3G/max oom_kill 0 | free scratch 307.0G/45112806i tmp 29.4G/1011476i workspace 307.0G/45112806i | scratch used 0.4G in 76245 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 7982 done 0 failed | 26 in flight, oldest 69s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
..... [369%]
........................................................................ [372%]
[contention-diag] +1260s soak 38p/243t rss 11.1G pss 10.4G swap 1.0G majflt 2713 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 25.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 27.55 | cgroup 11.4G/max oom_kill 0 | free scratch 306.9G/45112528i tmp 29.4G/1011476i workspace 306.9G/45112528i | repeat-01 collected 26/26 workers (60617 items) tests 8064 done 0 failed | 26 in flight, oldest 52s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
...............[contention-diag] +1275s soak 28p/229t rss 11.1G pss 10.4G swap 1.0G majflt 2713 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 23.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 27.49 | cgroup 11.4G/max oom_kill 0 | free scratch 306.9G/45112408i tmp 29.4G/1011474i workspace 306.9G/45112408i | repeat-01 collected 26/26 workers (60617 items) tests 8073 done 0 failed | 26 in flight, oldest 67s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
......................................................... [375%]
..........................................................[contention-diag] +1290s soak 28p/233t rss 11.1G pss 10.4G swap 1.0G majflt 2716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 23.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.33 | cgroup 11.4G/max oom_kill 0 | free scratch 306.6G/45112014i tmp 29.4G/1011476i workspace 306.6G/45112014i | repeat-01 collected 26/26 workers (60617 items) tests 8189 done 0 failed | 26 in flight, oldest 57s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_after_tools_returns_to_main_then_tools
.............. [379%]
................[contention-diag] +1306s soak 28p/238t rss 11.1G pss 10.4G swap 1.0G majflt 2716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 23.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.8 | cgroup 11.4G/max oom_kill 0 | free scratch 305.5G/45111849i tmp 29.4G/1011476i workspace 305.5G/45111849i | repeat-01 collected 26/26 workers (60617 items) tests 8224 done 0 failed | 26 in flight, oldest 58s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
........................................................ [382%]
........................................................................ [385%]
..............................[contention-diag] +1321s soak 28p/245t rss 11.1G pss 10.4G swap 1.0G majflt 2716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 23.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.72 | cgroup 11.4G/max oom_kill 0 | free scratch 305.5G/45111388i tmp 29.4G/1011476i workspace 305.5G/45111388i | repeat-01 collected 26/26 workers (60617 items) tests 8379 done 0 failed | 26 in flight, oldest 73s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
.......................................... [389%]
........................................................................ [392%]
........................................................................ [395%]
..........................................[contention-diag] +1336s soak 28p/236t rss 11.1G pss 10.4G swap 0.9G majflt 2912 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.3G | host avail 23.1G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 20.8 | cgroup 11.5G/max oom_kill 0 | free scratch 305.3G/45110738i tmp 29.4G/1011476i workspace 305.3G/45110738i | repeat-01 collected 26/26 workers (60617 items) tests 8593 done 0 failed | 26 in flight, oldest 82s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............................. [399%]
........................................................................ [402%]
.......................................................[contention-diag] +1352s soak 28p/233t rss 11.1G pss 10.4G swap 0.9G majflt 2923 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 24.0G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 22.17 | cgroup 11.4G/max oom_kill 0 | free scratch 305.3G/45110334i tmp 29.4G/1011476i workspace 305.3G/45110334i | repeat-01 collected 26/26 workers (60617 items) tests 8751 done 0 failed | 26 in flight, oldest 98s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................. [405%]
........................................................................ [409%]
........................................................................ [412%]
....................................[contention-diag] +1367s soak 28p/233t rss 11.2G pss 10.5G swap 0.9G majflt 2923 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 22.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 0.13 cpu 23.2 | cgroup 11.5G/max oom_kill 0 | free scratch 305.3G/45107575i tmp 29.4G/1011476i workspace 305.3G/45107575i | scratch used 0.8G in 147185 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 8961 done 0 failed | 26 in flight, oldest 113s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................... [415%]
................................[contention-diag] +1384s soak 29p/247t rss 11.2G pss 10.5G swap 0.9G majflt 2927 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 20.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 18.5 | cgroup 11.6G/max oom_kill 0 | free scratch 305.0G/45095947i tmp 29.4G/1011476i workspace 305.0G/45095947i | repeat-01 collected 26/26 workers (60617 items) tests 9030 done 0 failed | 26 in flight, oldest 130s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................................ [419%]
........................................................................ [422%]
...................................[contention-diag] +1400s soak 28p/268t rss 11.2G pss 10.5G swap 0.9G majflt 2927 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 27.5G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.63 | cgroup 11.7G/max oom_kill 0 | free scratch 305.2G/45088625i tmp 29.4G/1011476i workspace 305.2G/45088625i | repeat-01 collected 26/26 workers (60617 items) tests 9179 done 0 failed | 26 in flight, oldest 146s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.......................[contention-diag] +1415s soak 28p/267t rss 11.3G pss 10.5G swap 0.9G majflt 2934 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 27.8G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.68 | cgroup 11.7G/max oom_kill 0 | free scratch 305.2G/45088500i tmp 29.4G/1011476i workspace 305.2G/45088500i | repeat-01 collected 26/26 workers (60617 items) tests 9201 done 0 failed | 26 in flight, oldest 161s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............. [425%]
..................[contention-diag] +1430s soak 29p/250t rss 11.3G pss 10.6G swap 0.9G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 26.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.12 | cgroup 11.7G/max oom_kill 0 | free scratch 305.3G/45088882i tmp 29.4G/1011476i workspace 305.3G/45088882i | repeat-01 collected 26/26 workers (60617 items) tests 9232 done 0 failed | 26 in flight, oldest 83s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.....................[contention-diag] +1446s soak 29p/254t rss 11.3G pss 10.6G swap 0.9G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 25.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.47 | cgroup 11.8G/max oom_kill 0 | free scratch 305.2G/45088151i tmp 29.4G/1011476i workspace 305.2G/45088151i | repeat-01 collected 26/26 workers (60617 items) tests 9252 done 0 failed | 26 in flight, oldest 98s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................. [429%]
.............[contention-diag] +1461s soak 28p/235t rss 11.3G pss 10.6G swap 0.9G majflt 2942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G | host avail 26.3G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.84 | cgroup 11.8G/max oom_kill 0 | free scratch 305.2G/45085756i tmp 29.4G/1011476i workspace 305.2G/45085756i | repeat-01 collected 26/26 workers (60617 items) tests 9292 done 0 failed | 26 in flight, oldest 113s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
........................................................... [432%]
.........[contention-diag] +1476s soak 29p/248t rss 11.3G pss 10.6G swap 0.9G majflt 2949 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 26.6G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.0 | cgroup 11.8G/max oom_kill 0 | free scratch 305.1G/45068508i tmp 29.4G/1011476i workspace 305.1G/45068508i | repeat-01 collected 26/26 workers (60617 items) tests 9359 done 0 failed | 26 in flight, oldest 128s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................................................... [435%]
.....................................[contention-diag] +1491s soak 31p/244t rss 11.4G pss 10.6G swap 0.9G majflt 2951 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 3 descendant rss 0.0G pss 0.0G | host avail 26.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.54/0.36 io 0.44 cpu 24.63 | cgroup 11.7G/max oom_kill 0 | free scratch 305.1G/45066918i tmp 29.4G/1011476i workspace 305.1G/45066918i | scratch used 0.8G in 151507 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 9445 done 0 failed | 26 in flight, oldest 144s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................................[contention-diag] +1509s soak 29p/246t rss 11.4G pss 10.6G swap 0.9G majflt 2971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 26.7G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.19/0.05 io 0.11 cpu 17.13 | cgroup 11.7G/max oom_kill 0 | free scratch 305.0G/45065547i tmp 29.4G/1011476i workspace 305.0G/45065547i | repeat-01 collected 26/26 workers (60617 items) tests 9501 done 0 failed | 26 in flight, oldest 161s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.. [438%]
.......................[contention-diag] +1524s soak 28p/246t rss 11.4G pss 10.7G swap 0.9G majflt 2971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 25.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 0.02 cpu 17.52 | cgroup 11.7G/max oom_kill 0 | free scratch 304.9G/45064983i tmp 29.4G/1011476i workspace 304.9G/45064983i | repeat-01 collected 26/26 workers (60617 items) tests 9526 done 0 failed | 26 in flight, oldest 177s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................................. [442%]
......................................................[contention-diag] +1540s soak 28p/236t rss 11.4G pss 10.7G swap 0.9G majflt 2971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 23.1G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.31 | cgroup 11.7G/max oom_kill 0 | free scratch 304.7G/45064671i tmp 29.4G/1011476i workspace 304.7G/45064671i | repeat-01 collected 26/26 workers (60617 items) tests 9628 done 0 failed | 26 in flight, oldest 79s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [445%]
........................................................................ [448%]
...........................................................[contention-diag] +1555s soak 30p/247t rss 11.4G pss 10.7G swap 0.9G majflt 2971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 20.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.08 cpu 17.75 | cgroup 11.8G/max oom_kill 0 | free scratch 304.6G/45064124i tmp 29.4G/1011476i workspace 304.6G/45064124i | repeat-01 collected 26/26 workers (60617 items) tests 9779 done 0 failed | 26 in flight, oldest 94s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............. [452%]
................................................[contention-diag] +1570s soak 30p/261t rss 11.4G pss 10.7G swap 0.9G majflt 2989 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 17.2G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.54 cpu 16.51 | cgroup 11.8G/max oom_kill 0 | free scratch 304.5G/45064007i tmp 29.4G/1011476i workspace 304.5G/45064007i | repeat-01 collected 26/26 workers (60617 items) tests 9840 done 0 failed | 26 in flight, oldest 110s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................ [455%]
........................................................................ [458%]
.................[contention-diag] +1585s soak 28p/218t rss 11.4G pss 10.7G swap 0.9G majflt 2989 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 15.4G/62.7G swapfree 53.1G/64.0G oom_kill +0 | psi10 mem 0.17/0.17 io 1.53 cpu 16.89 | cgroup 11.8G/max oom_kill 0 | free scratch 304.2G/45063676i tmp 29.4G/1011476i workspace 304.2G/45063676i | repeat-01 collected 26/26 workers (60617 items) tests 9949 done 0 failed | 26 in flight, oldest 125s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................................................... [462%]
........................................[contention-diag] +1601s soak 32p/235t rss 11.5G pss 10.8G swap 0.9G majflt 2997 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 4 descendant rss 0.1G pss 0.1G | host avail 16.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.5 cpu 14.91 | cgroup 11.8G/max oom_kill 0 | free scratch 303.8G/45062871i tmp 29.4G/1011476i workspace 303.8G/45062871i | repeat-01 collected 26/26 workers (60617 items) tests 10047 done 0 failed | 26 in flight, oldest 140s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................ [465%]
......................................................[contention-diag] +1616s soak 29p/247t rss 11.5G pss 10.8G swap 0.9G majflt 3007 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 21.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 16.29 | cgroup 11.8G/max oom_kill 0 | free scratch 304.1G/45062498i tmp 29.4G/1011476i workspace 304.1G/45062498i | scratch used 0.9G in 159119 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 10125 done 0 failed | 26 in flight, oldest 156s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................[contention-diag] +1634s soak 29p/268t rss 11.6G pss 10.9G swap 0.9G majflt 3037 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 25.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.14 cpu 15.72 | cgroup 12.0G/max oom_kill 0 | free scratch 304.3G/45093022i tmp 29.4G/1011474i workspace 304.3G/45093022i | repeat-01 collected 26/26 workers (60617 items) tests 10149 done 0 failed | 26 in flight, oldest 174s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
. [468%]
.................................[contention-diag] +1649s soak 28p/270t rss 11.5G pss 10.8G swap 0.9G majflt 3037 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 24.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.77 cpu 10.49 | cgroup 11.9G/max oom_kill 0 | free scratch 304.2G/45092819i tmp 29.4G/1011476i workspace 304.2G/45092819i | repeat-01 collected 26/26 workers (60617 items) tests 10183 done 0 failed | 26 in flight, oldest 189s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................................... [472%]
........................................[contention-diag] +1665s soak 28p/267t rss 11.5G pss 10.8G swap 0.9G majflt 3039 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 22.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.69 cpu 11.71 | cgroup 11.9G/max oom_kill 0 | free scratch 304.2G/45075034i tmp 29.4G/1011371i workspace 304.2G/45075034i | repeat-01 collected 26/26 workers (60617 items) tests 10264 done 0 failed | 26 in flight, oldest 205s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................ [475%]
.............................[contention-diag] +1680s soak 29p/255t rss 11.6G pss 10.8G swap 0.9G majflt 3039 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 21.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.25 cpu 12.75 | cgroup 12.0G/max oom_kill 0 | free scratch 304.0G/45066176i tmp 29.3G/1011113i workspace 304.0G/45066176i | repeat-01 collected 26/26 workers (60617 items) tests 10321 done 0 failed | 26 in flight, oldest 220s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................................... [478%]
.......................................[contention-diag] +1696s soak 28p/256t rss 11.5G pss 10.8G swap 0.9G majflt 3039 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 24.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 16.49 | cgroup 12.0G/max oom_kill 0 | free scratch 304.0G/45064140i tmp 29.4G/1011422i workspace 304.0G/45064140i | repeat-01 collected 26/26 workers (60617 items) tests 10395 done 0 failed | 26 in flight, oldest 235s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................. [482%]
........................................................................ [485%]
.........................................[contention-diag] +1711s soak 29p/238t rss 11.6G pss 10.9G swap 1.0G majflt 3039 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.1G pss 0.1G | host avail 23.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.97 cpu 18.68 | cgroup 12.0G/max oom_kill 0 | free scratch 304.0G/45063246i tmp 29.4G/1011422i workspace 304.0G/45063246i | repeat-01 collected 26/26 workers (60617 items) tests 10552 done 0 failed | 26 in flight, oldest 251s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................... [488%]
.............................................[contention-diag] +1726s soak 29p/265t rss 11.6G pss 10.8G swap 0.9G majflt 3039 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 19.29 | cgroup 12.0G/max oom_kill 0 | free scratch 303.8G/45062937i tmp 29.4G/1011421i workspace 303.8G/45062937i | repeat-01 collected 26/26 workers (60617 items) tests 10628 done 0 failed | 26 in flight, oldest 266s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................... [492%]
.........................[contention-diag] +1742s soak 28p/272t rss 11.6G pss 10.8G swap 0.9G majflt 3040 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 20.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.81 cpu 14.76 | cgroup 12.0G/max oom_kill 0 | free scratch 304.0G/45062223i tmp 29.4G/1011449i workspace 304.0G/45062223i | scratch used 0.9G in 162709 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 10664 done 0 failed | 25 in flight, oldest 282s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................... [495%]
.......................................[contention-diag] +1759s soak 29p/265t rss 11.6G pss 10.9G swap 0.9G majflt 3045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 18.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.25 cpu 12.84 | cgroup 12.1G/max oom_kill 0 | free scratch 304.0G/45062499i tmp 29.4G/1011449i workspace 304.0G/45062499i | repeat-01 collected 26/26 workers (60617 items) tests 10766 done 0 failed | 26 in flight, oldest 299s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................. [498%]
.................................................[contention-diag] +1774s soak 28p/254t rss 11.6G pss 10.9G swap 0.9G majflt 3048 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 18.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.05 cpu 14.19 | cgroup 12.1G/max oom_kill 0 | free scratch 304.0G/45061347i tmp 29.4G/1011449i workspace 304.0G/45061347i | repeat-01 collected 26/26 workers (60617 items) tests 10847 done 0 failed | 26 in flight, oldest 314s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................... [502%]
....................................................[contention-diag] +1790s soak 30p/273t rss 11.6G pss 10.9G swap 0.9G majflt 3054 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 19.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 15.95 | cgroup 12.1G/max oom_kill 0 | free scratch 304.0G/45061931i tmp 29.4G/1011449i workspace 304.0G/45061931i | repeat-01 collected 26/26 workers (60617 items) tests 10910 done 0 failed | 26 in flight, oldest 330s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................... [505%]
.............................................................[contention-diag] +1805s soak 30p/274t rss 11.6G pss 10.8G swap 0.9G majflt 3100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 20.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 16.85 | cgroup 12.1G/max oom_kill 0 | free scratch 304.0G/45061295i tmp 29.4G/1011449i workspace 304.0G/45061295i | repeat-01 collected 26/26 workers (60617 items) tests 11003 done 0 failed | 26 in flight, oldest 51s gw9 tests/ace/tui/test_config_center_tabs.py::test_landing_compact_class_tracks_viewport_size
........... [508%]
.............................................................[contention-diag] +1821s soak 30p/284t rss 11.6G pss 10.8G swap 1.0G majflt 3139 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 16.1G/62.7G swapfree 52.9G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.23 cpu 11.1 | cgroup 12.0G/max oom_kill 0 | free scratch 303.8G/45060066i tmp 29.4G/1011449i workspace 303.8G/45060066i | repeat-01 collected 26/26 workers (60617 items) tests 11075 done 0 failed | 26 in flight, oldest 66s gw9 tests/ace/tui/test_config_center_tabs.py::test_landing_compact_class_tracks_viewport_size
........... [512%]
.............................................[contention-diag] +1836s soak 29p/286t rss 11.6G pss 10.8G swap 1.0G majflt 3243 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 16.8G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.05 cpu 12.26 | cgroup 12.1G/max oom_kill 0 | free scratch 303.8G/45059530i tmp 29.4G/1011449i workspace 303.8G/45059530i | repeat-01 collected 26/26 workers (60617 items) tests 11132 done 0 failed | 26 in flight, oldest 66s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........................... [515%]
[contention-diag] +1852s soak 32p/292t rss 11.5G pss 10.7G swap 1.2G majflt 3560 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.5G, 4 descendant rss 0.1G pss 0.1G | host avail 14.1G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 3.94/3.19 io 4.95 cpu 9.68 | cgroup 11.5G/max oom_kill 0 | free scratch 303.6G/45057891i tmp 29.4G/1011449i workspace 303.6G/45057891i | repeat-01 collected 26/26 workers (60617 items) tests 11158 done 0 failed | 26 in flight, oldest 81s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........................................................................ [518%]
...............................................................[contention-diag] +1867s soak 31p/268t rss 11.5G pss 10.6G swap 1.2G majflt 4488 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.5G, 3 descendant rss 0.1G pss 0.0G | host avail 18.1G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.95/0.64 io 1.31 cpu 14.22 | cgroup 11.5G/max oom_kill 0 | free scratch 303.6G/45057985i tmp 29.4G/1011449i workspace 303.6G/45057985i | scratch used 0.2G in 37191 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 11267 done 0 failed | 26 in flight, oldest 97s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
......... [522%]
......................[contention-diag] +1884s soak 30p/261t rss 11.5G pss 10.6G swap 1.3G majflt 4490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 2 descendant rss 0.0G pss 0.0G | host avail 16.2G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.86/0.49 io 9.79 cpu 14.3 | cgroup 11.5G/max oom_kill 0 | free scratch 303.2G/45029263i tmp 29.3G/1011119i workspace 303.2G/45029263i | repeat-01 collected 26/26 workers (60617 items) tests 11324 done 0 failed | 26 in flight, oldest 114s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.................................................. [525%]
.................................[contention-diag] +1900s soak 31p/272t rss 11.4G pss 10.4G swap 1.5G majflt 6891 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 3 descendant rss 0.1G pss 0.0G | host avail 16.4G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 4.29/3.36 io 18.34 cpu 9.29 | cgroup 10.8G/max oom_kill 0 | free scratch 303.3G/45029487i tmp 29.4G/1011350i workspace 303.3G/45029487i | repeat-01 collected 26/26 workers (60617 items) tests 11405 done 0 failed | 25 in flight, oldest 83s gw3 tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast
....................................... [528%]
.............................................................[contention-diag] +1915s soak 28p/266t rss 11.4G pss 10.3G swap 1.5G majflt 7677 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.2G | host avail 17.5G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.86/0.67 io 4.06 cpu 14.92 | cgroup 10.8G/max oom_kill 0 | free scratch 303.2G/45028967i tmp 29.4G/1011395i workspace 303.2G/45028967i | repeat-01 collected 26/26 workers (60617 items) tests 11507 done 0 failed | 26 in flight, oldest 98s gw3 tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast
.........F[contention-failure] call tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc41d6be000>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw3/test_post_update_toast_appears0')

    async def test_post_update_toast_appears_once_and_suppresses_available_toast(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        # This test's own subject is toast suppression between the post-update and
        # update-available toasts; pre-seed the unrelated one-shot keymap-unification,
        # agent-decks, and agent-pane-retirement notices as already shown so they
        # don't ride along on this receipt and add unrelated notifications.
        mark_keymap_unification_notice_shown()
        mark_agent_decks_notice_shown()
        mark_artifacts_agent_pane_notice_shown()
        receipt_file = tmp_path / "pending_update_toast.json"
        monkeypatch.setattr(update_receipt, "_PENDING_UPDATE_TOAST_FILE", receipt_file)
        assert write_pending_update_toast(_receipt()) is True
        monkeypatch.setattr(
            update_toast,
            "_load_update_toast_config",
            lambda: update_toast._UpdateToastConfig(
                startup_toast=True,
                post_update_toast=True,
            ),
        )
        monkeypatch.setattr(
            update_toast,
            "get_cached_update_status",
            lambda **_kwargs: _status(),
        )
    
        async with AcePage(query='"toast"') as page:
>           await page.wait_for(lambda _s: bool(list(page.app._notifications)))

tests/ace/tui/test_post_update_toast.py:525: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fc405d99f80>

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
E               AssertionError: wait_for() timed out a
. [532%]
........................................................................ [535%]
...................................................................[contention-diag] +1930s soak 29p/251t rss 11.5G pss 10.4G swap 1.5G majflt 9163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 1 descendant rss 0.1G pss 0.0G | host avail 23.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.51/0.16 io 1.0 cpu 18.0 | cgroup 10.8G/max oom_kill 0 | free scratch 303.2G/45028423i tmp 29.4G/1011395i workspace 303.2G/45028423i | repeat-01 collected 26/26 workers (60617 items) tests 11657 done 1 failed | 26 in flight, oldest 51s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_summary_counts
..... [538%]
.......................[contention-diag] +1946s soak 29p/276t rss 11.4G pss 10.4G swap 1.5G majflt 9334 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 25.0G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.4/0.23 io 0.79 cpu 18.86 | cgroup 10.8G/max oom_kill 0 | free scratch 303.3G/45027537i tmp 29.4G/1011408i workspace 303.3G/45027537i | repeat-01 collected 26/26 workers (60617 items) tests 11686 done 1 failed | 26 in flight, oldest 56s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
........................................[contention-diag] +1961s soak 29p/274t rss 11.4G pss 10.4G swap 1.5G majflt 9577 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 21.6G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.04 io 1.25 cpu 13.72 | cgroup 10.8G/max oom_kill 0 | free scratch 303.2G/45027512i tmp 29.4G/1011423i workspace 303.2G/45027512i | repeat-01 collected 26/26 workers (60617 items) tests 11721 done 1 failed | 26 in flight, oldest 61s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
......... [542%]
...............................................................[contention-diag] +1976s soak 30p/252t rss 11.5G pss 10.4G swap 1.5G majflt 9889 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 2 descendant rss 0.0G pss 0.0G | host avail 21.2G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.68 cpu 12.17 | cgroup 10.8G/max oom_kill 0 | free scratch 303.1G/45027224i tmp 29.4G/1011423i workspace 303.1G/45027224i | repeat-01 collected 26/26 workers (60617 items) tests 11796 done 1 failed | 26 in flight, oldest 77s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
......... [545%]
.........................[contention-diag] +1992s soak 29p/259t rss 11.5G pss 10.4G swap 1.5G majflt 10155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 20.8G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.16/0.0 io 0.13 cpu 19.01 | cgroup 10.8G/max oom_kill 0 | free scratch 303.0G/45027172i tmp 29.4G/1011423i workspace 303.0G/45027172i | scratch used 0.2G in 29005 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 11825 done 1 failed | 26 in flight, oldest 50s gw23 tests/ace/tui/test_feature_flags_pane_journeys.py::test_toggle_commits_saved_state_before_restart_runs
............................................... [548%]
........................................................................ [552%]
............................[contention-diag] +2009s soak 31p/248t rss 11.5G pss 10.4G swap 1.5G majflt 10452 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 3 descendant rss 0.0G pss 0.0G | host avail 20.2G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.17 cpu 20.75 | cgroup 10.9G/max oom_kill 0 | free scratch 302.9G/45027214i tmp 29.4G/1011423i workspace 302.9G/45027214i | repeat-01 collected 26/26 workers (60617 items) tests 11969 done 1 failed | 24 in flight, oldest 63s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
............................................ [555%]
...[contention-diag] +2024s soak 30p/240t rss 11.6G pss 10.5G swap 1.5G majflt 10711 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 2 descendant rss 0.1G pss 0.1G | host avail 21.3G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 19.63 | cgroup 11.0G/max oom_kill 0 | free scratch 302.8G/45026164i tmp 29.4G/1011423i workspace 302.8G/45026164i | repeat-01 collected 26/26 workers (60617 items) tests 12024 done 1 failed | 26 in flight, oldest 78s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
..................................................................... [558%]
........................................................................ [562%]
................................[contention-diag] +2040s soak 30p/250t rss 11.5G pss 10.5G swap 1.5G majflt 11196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 2 descendant rss 0.1G pss 0.0G | host avail 19.6G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.08 cpu 20.21 | cgroup 11.0G/max oom_kill 0 | free scratch 302.8G/45023455i tmp 29.4G/1011423i workspace 302.8G/45023455i | repeat-01 collected 26/26 workers (60617 items) tests 12196 done 1 failed | 26 in flight, oldest 94s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
........................................ [565%]
...................................[contention-diag] +2055s soak 30p/245t rss 11.6G pss 10.5G swap 1.5G majflt 11482 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 2 descendant rss 0.1G pss 0.0G | host avail 21.3G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.02 cpu 24.35 | cgroup 11.0G/max oom_kill 0 | free scratch 302.7G/45006551i tmp 29.4G/1011421i workspace 302.7G/45006551i | repeat-01 collected 26/26 workers (60617 items) tests 12270 done 1 failed | 26 in flight, oldest 46s gw9 tests/ace/tui/test_projects_pane.py::test_projects_session_round_trips_current_project_display
..................................... [568%]
........................................................................ [572%]
.............................................................[contention-diag] +2070s soak 31p/256t rss 11.5G pss 10.5G swap 1.4G majflt 11630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 3 descendant rss 0.0G pss 0.0G | host avail 25.4G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.11 cpu 20.77 | cgroup 11.0G/max oom_kill 0 | free scratch 302.7G/45004466i tmp 29.4G/1011421i workspace 302.7G/45004466i | repeat-01 collected 26/26 workers (60617 items) tests 12434 done 1 failed | 26 in flight, oldest 57s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
........... [575%]
........................................................................ [578%]
........................................................................ [581%]
..........................[contention-diag] +2086s soak 30p/236t rss 11.6G pss 10.5G swap 1.4G majflt 11820 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 2 descendant rss 0.1G pss 0.0G | host avail 25.3G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 1.96 cpu 19.98 | cgroup 11.0G/max oom_kill 0 | free scratch 302.7G/45004039i tmp 29.4G/1011421i workspace 302.7G/45004039i | repeat-01 collected 26/26 workers (60617 items) tests 12623 done 1 failed | 26 in flight, oldest 53s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree
.............................................. [585%]
........................................................................ [588%]
........................[contention-diag] +2101s soak 32p/251t rss 11.6G pss 10.5G swap 1.4G majflt 11941 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 4 descendant rss 0.0G pss 0.0G | host avail 23.0G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.74 cpu 19.46 | cgroup 11.0G/max oom_kill 0 | free scratch 303.2G/45003592i tmp 29.4G/1011421i workspace 303.2G/45003592i | repeat-01 collected 26/26 workers (60617 items) tests 12757 done 1 failed | 26 in flight, oldest 57s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
................................................ [591%]
........................................................................ [595%]
.......[contention-diag] +2116s soak 34p/277t rss 11.6G pss 10.5G swap 1.4G majflt 12373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 6 descendant rss 0.0G pss 0.0G | host avail 18.2G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.92 cpu 12.51 | cgroup 11.0G/max oom_kill 0 | free scratch 302.9G/45001998i tmp 29.4G/1011421i workspace 302.9G/45001998i | scratch used 0.3G in 55173 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 12875 done 1 failed | 26 in flight, oldest 73s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
................................................................. [598%]
..........................[contention-diag] +2134s soak 32p/253t rss 11.6G pss 10.5G swap 1.4G majflt 12718 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 4 descendant rss 0.0G pss 0.0G | host avail 19.5G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 1.15/1.15 io 1.79 cpu 12.68 | cgroup 11.1G/max oom_kill 0 | free scratch 302.8G/44994405i tmp 29.4G/1011421i workspace 302.8G/44994405i | repeat-01 collected 26/26 workers (60617 items) tests 12978 done 1 failed | 26 in flight, oldest 60s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
.....................................[contention-diag] +2149s soak 32p/259t rss 11.6G pss 10.6G swap 1.4G majflt 12743 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 4 descendant rss 0.0G pss 0.0G | host avail 15.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.23/0.23 io 12.54 cpu 10.91 | cgroup 11.1G/max oom_kill 0 | free scratch 302.5G/44974864i tmp 29.3G/1011137i workspace 302.5G/44974864i | repeat-01 collected 26/26 workers (60617 items) tests 13018 done 1 failed | 26 in flight, oldest 74s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
......... [601%]
........................................................................ [605%]
........................................................................ [608%]
[contention-diag] +2165s soak 35p/262t rss 11.6G pss 10.5G swap 1.4G majflt 13228 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 7 descendant rss 0.0G pss 0.0G | host avail 21.9G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 2.3/1.97 io 10.94 cpu 11.19 | cgroup 11.1G/max oom_kill 0 | free scratch 302.5G/44973172i tmp 29.4G/1011367i workspace 302.5G/44973172i | repeat-01 collected 26/26 workers (60617 items) tests 13172 done 1 failed | 26 in flight, oldest 56s gw2 tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_loads_receipt_on_plan_worker
........................................................................ [611%]
...................................[contention-diag] +2180s soak 29p/249t rss 11.6G pss 10.6G swap 1.4G majflt 14206 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.46/0.39 io 3.25 cpu 18.8 | cgroup 11.1G/max oom_kill 0 | free scratch 302.4G/44972830i tmp 29.4G/1011360i workspace 302.4G/44972830i | repeat-01 collected 26/26 workers (60617 items) tests 13282 done 1 failed | 26 in flight, oldest 61s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_cancel_cleans_up_fetched_script
..................................... [615%]
........................................[contention-diag] +2195s soak 29p/255t rss 11.7G pss 10.6G swap 1.4G majflt 14523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 22.0G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.09/0.07 io 2.05 cpu 18.7 | cgroup 11.1G/max oom_kill 0 | free scratch 302.4G/44972072i tmp 29.4G/1010775i workspace 302.4G/44972072i | repeat-01 collected 26/26 workers (60617 items) tests 13359 done 1 failed | 26 in flight, oldest 59s gw23 tests/ace/tui/test_link_follow_planner.py::test_kind_mismatch_stays_pending_until_query_worker_settles
................................ [618%]
........................................................................ [621%]
.........................................................[contention-diag] +2211s soak 33p/283t rss 11.7G pss 10.6G swap 1.4G majflt 14630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.4G, 5 descendant rss 0.1G pss 0.0G | host avail 22.6G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 1.24 cpu 18.94 | cgroup 11.2G/max oom_kill 0 | free scratch 302.4G/44972207i tmp 29.4G/1010803i workspace 302.4G/44972207i | repeat-01 collected 26/26 workers (60617 items) tests 13508 done 1 failed | 26 in flight, oldest 60s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
............... [625%]
........................................................................ [628%]
........................................................................ [631%]
................................[contention-diag] +2226s soak 29p/279t rss 11.8G pss 10.7G swap 1.4G majflt 14938 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.1G pss 0.1G | host avail 27.2G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.18 cpu 15.83 | cgroup 11.2G/max oom_kill 0 | free scratch 302.4G/44971812i tmp 29.4G/1010803i workspace 302.4G/44971812i | repeat-01 collected 26/26 workers (60617 items) tests 13710 done 1 failed | 25 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
........................................ [635%]
..............................................................[contention-diag] +2241s soak 30p/266t rss 11.7G pss 10.6G swap 1.4G majflt 15035 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 27.7G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.38 cpu 14.95 | cgroup 11.3G/max oom_kill 0 | free scratch 302.4G/44971490i tmp 29.4G/1010803i workspace 302.4G/44971490i | scratch used 0.4G in 69757 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 13804 done 1 failed | 26 in flight, oldest 75s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.......... [638%]
.....................................[contention-diag] +2259s soak 29p/276t rss 11.8G pss 10.6G swap 1.4G majflt 15320 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.1G pss 0.0G | host avail 25.4G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.31 cpu 20.22 | cgroup 11.4G/max oom_kill 0 | free scratch 302.4G/44971132i tmp 29.4G/1010803i workspace 302.4G/44971132i | repeat-01 collected 26/26 workers (60617 items) tests 13857 done 1 failed | 26 in flight, oldest 93s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
................................... [641%]
.....[contention-diag] +2274s soak 29p/263t rss 11.8G pss 10.7G swap 1.4G majflt 15369 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.1G pss 0.0G | host avail 26.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.73 cpu 18.05 | cgroup 11.6G/max oom_kill 0 | free scratch 302.4G/44971545i tmp 29.4G/1010803i workspace 302.4G/44971545i | repeat-01 collected 26/26 workers (60617 items) tests 13893 done 1 failed | 25 in flight, oldest 108s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
................................................................... [645%]
........................................................................ [648%]
.....................[contention-diag] +2289s soak 31p/264t rss 11.9G pss 10.8G swap 1.4G majflt 15428 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 3 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.56 cpu 19.13 | cgroup 11.6G/max oom_kill 0 | free scratch 302.9G/44970222i tmp 29.4G/1010803i workspace 302.9G/44970222i | repeat-01 collected 26/26 workers (60617 items) tests 14057 done 1 failed | 26 in flight, oldest 54s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[P-core-Core]
................................................... [651%]
........................................................................ [655%]
....[contention-diag] +2305s soak 32p/276t rss 12.0G pss 10.8G swap 1.4G majflt 15485 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.5G, 4 descendant rss 0.3G pss 0.2G | host avail 24.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.87 cpu 17.08 | cgroup 11.5G/max oom_kill 0 | free scratch 302.8G/44967463i tmp 29.4G/1010803i workspace 302.8G/44967463i | repeat-01 collected 26/26 workers (60617 items) tests 14184 done 1 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
.................................................................... [658%]
........................................................................ [661%]
....................[contention-diag] +2320s soak 30p/267t rss 11.8G pss 10.7G swap 1.4G majflt 15652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 24.4G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.91 cpu 18.91 | cgroup 11.5G/max oom_kill 0 | free scratch 302.5G/44949041i tmp 29.4G/1010803i workspace 302.5G/44949041i | repeat-01 collected 26/26 workers (60617 items) tests 14348 done 1 failed | 25 in flight, oldest 63s gw22 tests/ace/tui/test_statistics_footprint.py::test_footprint_copy_sends_selected_feature_id
.................................................... [665%]
.......................[contention-diag] +2335s soak 29p/252t rss 11.8G pss 10.7G swap 1.4G majflt 15943 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 22.1G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.56/0.49 io 1.7 cpu 17.25 | cgroup 11.5G/max oom_kill 0 | free scratch 302.5G/44968686i tmp 29.4G/1010803i workspace 302.5G/44968686i | repeat-01 collected 26/26 workers (60617 items) tests 14422 done 1 failed | 26 in flight, oldest 56s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
................................................. [668%]
...........................................[contention-diag] +2351s soak 28p/271t rss 11.8G pss 10.7G swap 1.4G majflt 16116 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.6G | host avail 21.9G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.11/0.09 io 1.61 cpu 17.84 | cgroup 11.5G/max oom_kill 0 | free scratch 302.4G/44968469i tmp 29.4G/1010803i workspace 302.4G/44968469i | repeat-01 collected 26/26 workers (60617 items) tests 14513 done 1 failed | 26 in flight, oldest 72s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
............................. [671%]
........................................................................ [675%]
...............[contention-diag] +2366s soak 30p/295t rss 11.9G pss 10.8G swap 1.4G majflt 16426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 23.6G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 3.47 cpu 22.12 | cgroup 11.5G/max oom_kill 0 | free scratch 302.4G/44968121i tmp 29.4G/1010803i workspace 302.4G/44968121i | scratch used 0.5G in 85037 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 14617 done 1 failed | 26 in flight, oldest 50s gw23 tests/ace/tui/test_link_follow_planner.py::test_missing_bead_hydrates_then_reveals
......................................................... [678%]
........................................................................ [681%]
........................................................................ [685%]
..............................................................[contention-diag] +2383s soak 31p/239t rss 11.9G pss 10.8G swap 1.4G majflt 16860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 3 descendant rss 0.0G pss 0.0G | host avail 22.2G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.58 cpu 21.47 | cgroup 11.6G/max oom_kill 0 | free scratch 302.4G/44967332i tmp 29.4G/1010803i workspace 302.4G/44967332i | repeat-01 collected 26/26 workers (60617 items) tests 14883 done 1 failed | 25 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
.......... [688%]
........................................................................ [691%]
.............................................[contention-diag] +2399s soak 32p/257t rss 12.0G pss 10.8G swap 1.3G majflt 16981 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 4 descendant rss 0.1G pss 0.0G | host avail 23.0G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.87 cpu 19.13 | cgroup 11.7G/max oom_kill 0 | free scratch 302.4G/44966831i tmp 29.4G/1010802i workspace 302.4G/44966831i | repeat-01 collected 26/26 workers (60617 items) tests 15019 done 1 failed | 26 in flight, oldest 51s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_deck_close_each_and_erase_through_keys
........................... [695%]
........................................................................ [698%]
........................................................................ [701%]
............[contention-diag] +2414s soak 37p/273t rss 12.0G pss 10.9G swap 1.3G majflt 17144 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.7G, 9 descendant rss 0.1G pss 0.0G | host avail 26.9G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.77 cpu 20.14 | cgroup 11.7G/max oom_kill 0 | free scratch 302.4G/44965797i tmp 29.4G/1010802i workspace 302.4G/44965797i | repeat-01 collected 26/26 workers (60617 items) tests 15201 done 1 failed | 26 in flight, oldest 53s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
............................................................ [705%]
........................................................................ [708%]
........................................................................ [711%]
........................................................................ [715%]
...........[contention-diag] +2429s soak 33p/272t rss 12.0G pss 10.9G swap 1.3G majflt 17315 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 5 descendant rss 0.1G pss 0.1G | host avail 25.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.59 cpu 19.21 | cgroup 11.7G/max oom_kill 0 | free scratch 302.4G/44965187i tmp 29.4G/1010802i workspace 302.4G/44965187i | repeat-01 collected 26/26 workers (60617 items) tests 15488 done 1 failed | 25 in flight, oldest 68s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
............................................................. [718%]
........................................................................ [721%]
........................................................[contention-diag] +2445s soak 31p/260t rss 12.0G pss 10.9G swap 1.3G majflt 17492 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 17.72 | cgroup 11.7G/max oom_kill 0 | free scratch 302.4G/44964481i tmp 29.4G/1010802i workspace 302.4G/44964481i | repeat-01 collected 26/26 workers (60617 items) tests 15673 done 1 failed | 26 in flight, oldest 52s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_each_activation_mints_new_session
................ [724%]
.....................................................[contention-diag] +2460s soak 32p/269t rss 12.2G pss 11.1G swap 1.3G majflt 18277 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 4 descendant rss 0.2G pss 0.2G | host avail 24.4G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.44 cpu 18.52 | cgroup 11.8G/max oom_kill 0 | free scratch 302.3G/44963634i tmp 29.4G/1010802i workspace 302.3G/44963634i | repeat-01 collected 26/26 workers (60617 items) tests 15747 done 1 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_each_activation_mints_new_session
................... [728%]
................................................................[contention-diag] +2475s soak 34p/281t rss 12.1G pss 10.9G swap 1.3G majflt 18367 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 6 descendant rss 0.0G pss 0.0G | host avail 24.3G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.16 cpu 15.73 | cgroup 11.8G/max oom_kill 0 | free scratch 304.7G/45114050i tmp 29.4G/1010800i workspace 304.7G/45114050i | repeat-01 collected 26/26 workers (60617 items) tests 15824 done 1 failed | 26 in flight, oldest 72s gw14 tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
........ [731%]
........................................................................ [734%]
........................................................................ [738%]
........................................................................ [741%]
.[contention-diag] +2491s soak 32p/257t rss 12.2G pss 11.0G swap 1.3G majflt 18552 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 4 descendant rss 0.2G pss 0.1G | host avail 24.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.34 cpu 16.89 | cgroup 11.8G/max oom_kill 0 | free scratch 307.6G/45114310i tmp 29.4G/1010802i workspace 307.6G/45114310i | scratch used 0.5G in 98635 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 16015 done 1 failed | 25 in flight, oldest 87s gw14 tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
....................................................................... [744%]
........................................................................ [748%]
........................................................................ [751%]
........................................................................ [754%]
..............................[contention-diag] +2508s soak 31p/239t rss 12.1G pss 11.0G swap 1.3G majflt 18964 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 3 descendant rss 0.1G pss 0.1G | host avail 23.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.92 cpu 14.87 | cgroup 11.8G/max oom_kill 0 | free scratch 308.0G/45116357i tmp 29.4G/1010802i workspace 308.0G/45116357i | repeat-01 collected 26/26 workers (60617 items) tests 16350 done 1 failed | 25 in flight, oldest 79s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.......................................... [758%]
........................................................................ [761%]
........................................................................ [764%]
...........................................................[contention-diag] +2524s soak 34p/249t rss 12.2G pss 11.0G swap 1.3G majflt 19312 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 6 descendant rss 0.1G pss 0.1G | host avail 21.3G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.35/0.35 io 2.91 cpu 13.27 | cgroup 11.8G/max oom_kill 0 | free scratch 308.0G/45115390i tmp 29.4G/1010802i workspace 308.0G/45115390i | repeat-01 collected 26/26 workers (60617 items) tests 16602 done 1 failed | 26 in flight, oldest 94s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
............. [768%]
........................................................................ [771%]
........................................................................ [774%]
........................................................................ [778%]
...............................[contention-diag] +2539s soak 34p/250t rss 12.2G pss 11.0G swap 1.3G majflt 19344 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 6 descendant rss 0.1G pss 0.1G | host avail 21.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 1.06/0.66 io 3.79 cpu 13.99 | cgroup 11.8G/max oom_kill 0 | free scratch 308.0G/45114313i tmp 29.4G/1010802i workspace 308.0G/45114313i | repeat-01 collected 26/26 workers (60617 items) tests 16863 done 1 failed | 26 in flight, oldest 109s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
......................................... [781%]
........................................................................ [784%]
........................................................................ [788%]
................................[contention-diag] +2554s soak 33p/266t rss 12.2G pss 11.0G swap 1.3G majflt 19979 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 5 descendant rss 0.1G pss 0.1G | host avail 23.7G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 2.62/1.65 io 4.53 cpu 12.59 | cgroup 11.8G/max oom_kill 0 | free scratch 307.7G/45113450i tmp 29.4G/1010802i workspace 307.7G/45113450i | repeat-01 collected 26/26 workers (60617 items) tests 17088 done 1 failed | 26 in flight, oldest 125s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........................................ [791%]
........................................................................ [794%]
........................................................................ [798%]
.........[contention-diag] +2570s soak 32p/267t rss 12.1G pss 11.0G swap 1.3G majflt 20258 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 26.7G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.64/0.4 io 2.18 cpu 13.96 | cgroup 11.8G/max oom_kill 0 | free scratch 308.0G/45112505i tmp 29.4G/1010802i workspace 308.0G/45112505i | repeat-01 collected 26/26 workers (60617 items) tests 17288 done 1 failed | 26 in flight, oldest 139s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............................................................... [801%]
........................................................................ [804%]
..........[contention-diag] +2585s soak 33p/281t rss 12.2G pss 11.1G swap 1.3G majflt 20718 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 5 descendant rss 0.1G pss 0.1G | host avail 27.3G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.12/0.08 io 1.78 cpu 16.21 | cgroup 11.9G/max oom_kill 0 | free scratch 308.0G/45111893i tmp 29.4G/1010802i workspace 308.0G/45111893i | repeat-01 collected 26/26 workers (60617 items) tests 17431 done 1 failed | 26 in flight, oldest 154s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.............................................................. [808%]
......[contention-diag] +2601s soak 32p/265t rss 12.1G pss 11.0G swap 1.3G majflt 20926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 26.0G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 1.62 cpu 14.68 | cgroup 12.0G/max oom_kill 0 | free scratch 308.0G/45111565i tmp 29.4G/1010802i workspace 308.0G/45111565i | repeat-01 collected 26/26 workers (60617 items) tests 17497 done 1 failed | 26 in flight, oldest 170s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................................. [811%]
........................................................................ [814%]
........................................................................ [818%]
....................................................................[contention-diag] +2616s soak 34p/269t rss 12.2G pss 11.0G swap 1.3G majflt 21126 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 6 descendant rss 0.0G pss 0.0G | host avail 27.2G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.12 cpu 16.62 | cgroup 11.9G/max oom_kill 0 | free scratch 308.0G/45110883i tmp 29.4G/1010802i workspace 308.0G/45110883i | scratch used 0.3G in 48092 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 17727 done 1 failed | 25 in flight, oldest 185s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.... [821%]
........................................................................ [824%]
........................................................................ [828%]
...[contention-diag] +2634s soak 32p/236t rss 12.2G pss 11.1G swap 1.3G majflt 21348 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 4 descendant rss 0.0G pss 0.0G | host avail 26.1G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.06 cpu 16.83 | cgroup 12.0G/max oom_kill 0 | free scratch 308.0G/45112674i tmp 29.4G/1010802i workspace 308.0G/45112674i | repeat-01 collected 26/26 workers (60617 items) tests 17924 done 1 failed | 26 in flight, oldest 78s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
..................................................................... [831%]
.......................................................[contention-diag] +2649s soak 33p/236t rss 12.2G pss 11.0G swap 1.3G majflt 21396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 5 descendant rss 0.0G pss 0.0G | host avail 25.1G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.75 cpu 17.36 | cgroup 11.9G/max oom_kill 0 | free scratch 308.0G/45112345i tmp 29.4G/1010802i workspace 308.0G/45112345i | repeat-01 collected 26/26 workers (60617 items) tests 18050 done 1 failed | 26 in flight, oldest 78s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................. [834%]
........................................................................ [838%]
.....................................................................[contention-diag] +2664s soak 31p/239t rss 12.2G pss 11.1G swap 1.3G majflt 21446 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 3 descendant rss 0.0G pss 0.0G | host avail 24.4G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.44 cpu 17.23 | cgroup 12.0G/max oom_kill 0 | free scratch 308.0G/45111846i tmp 29.4G/1010802i workspace 308.0G/45111846i | repeat-01 collected 26/26 workers (60617 items) tests 18201 done 1 failed | 26 in flight, oldest 94s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
... [841%]
........................................................................ [844%]
........................................................................ [848%]
.............................[contention-diag] +2680s soak 32p/269t rss 12.3G pss 11.1G swap 1.3G majflt 21529 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 4 descendant rss 0.1G pss 0.0G | host avail 24.2G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.01 cpu 14.71 | cgroup 12.0G/max oom_kill 0 | free scratch 308.0G/45111068i tmp 29.4G/1010802i workspace 308.0G/45111068i | repeat-01 collected 26/26 workers (60617 items) tests 18383 done 1 failed | 26 in flight, oldest 109s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
........................................... [851%]
........................................................................ [854%]
..................................[contention-diag] +2695s soak 36p/246t rss 12.3G pss 11.1G swap 1.3G majflt 21650 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 8 descendant rss 0.0G pss 0.0G | host avail 25.7G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 1.23/0.75 io 3.22 cpu 13.9 | cgroup 12.0G/max oom_kill 0 | free scratch 311.5G/45137990i tmp 29.4G/1010800i workspace 311.5G/45137990i | repeat-01 collected 26/26 workers (60617 items) tests 18536 done 1 failed | 26 in flight, oldest 53s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
...................................... [858%]
........................................................................ [861%]
........................................................................ [864%]
........................................................................ [867%]
........................................................................ [871%]
...................................................[contention-diag] +2710s soak 31p/239t rss 12.3G pss 11.2G swap 1.3G majflt 21813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 3 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.3/0.18 io 2.15 cpu 15.02 | cgroup 12.0G/max oom_kill 0 | free scratch 311.3G/45125869i tmp 29.4G/1010802i workspace 311.3G/45125869i | repeat-01 collected 26/26 workers (60617 items) tests 18880 done 1 failed | 25 in flight, oldest 69s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
..................... [874%]
.......................................................s................ [877%]
........................................................................ [881%]
....................................................................[contention-diag] +2726s soak 35p/228t rss 12.3G pss 11.1G swap 1.3G majflt 21892 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 7 descendant rss 0.0G pss 0.0G | host avail 22.2G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.06/0.03 io 1.87 cpu 13.1 | cgroup 12.1G/max oom_kill 0 | free scratch 311.2G/45124751i tmp 29.4G/1010802i workspace 311.2G/45124751i | repeat-01 collected 26/26 workers (60617 items) tests 19134 done 1 failed | 26 in flight, oldest 43s gw8 tests/ace/tui/test_usage_header.py::test_fallback_clicks_open_usage
.... [884%]
............s.s......................................................... [887%]
........................................................................ [891%]
........................................................................ [894%]
..............................[contention-diag] +2741s soak 32p/246t rss 12.3G pss 11.0G swap 1.3G majflt 22459 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 4 descendant rss 0.0G pss 0.0G | host avail 24.7G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 2.66 cpu 17.22 | cgroup 12.1G/max oom_kill 0 | free scratch 311.2G/45124081i tmp 29.4G/1010802i workspace 311.2G/45124081i | scratch used 0.6G in 111513 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 19357 done 1 failed | 26 in flight, oldest 48s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.......................................... [897%]
........................................................................ [901%]
........................................................................ [904%]
........................................................................ [907%]
......................................[contention-diag] +2758s soak 30p/236t rss 12.3G pss 11.2G swap 1.2G majflt 22710 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 21.9G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.45 cpu 14.54 | cgroup 12.2G/max oom_kill 0 | free scratch 311.3G/45123771i tmp 29.4G/1010802i workspace 311.3G/45123771i | repeat-01 collected 26/26 workers (60617 items) tests 19693 done 1 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................................. [911%]
........................................................................ [914%]
........................................................................ [917%]
................................[contention-diag] +2774s soak 31p/260t rss 12.4G pss 11.2G swap 1.2G majflt 23222 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 21.6G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 0.59 cpu 13.01 | cgroup 12.2G/max oom_kill 0 | free scratch 311.3G/45123985i tmp 29.4G/1010802i workspace 311.3G/45123985i | repeat-01 collected 26/26 workers (60617 items) tests 19901 done 1 failed | 26 in flight, oldest 81s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................................ [921%]
........................................................................ [924%]
........................................................................ [927%]
.........[contention-diag] +2789s soak 35p/256t rss 12.4G pss 11.2G swap 1.2G majflt 23691 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 7 descendant rss 0.0G pss 0.0G | host avail 18.9G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 0.82/0.67 io 1.81 cpu 11.71 | cgroup 12.3G/max oom_kill 0 | free scratch 311.3G/45123049i tmp 29.4G/1010801i workspace 311.3G/45123049i | repeat-01 collected 26/26 workers (60617 items) tests 20095 done 1 failed | 25 in flight, oldest 97s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............................................................... [931%]
........................................................................ [934%]
........................................................................ [937%]
....................................[contention-diag] +2805s soak 33p/267t rss 12.3G pss 11.1G swap 1.5G majflt 24404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 5 descendant rss 0.1G pss 0.1G | host avail 17.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.29/0.22 io 1.77 cpu 12.63 | cgroup 12.1G/max oom_kill 0 | free scratch 311.3G/45122378i tmp 29.4G/1010801i workspace 311.3G/45122378i | repeat-01 collected 26/26 workers (60617 items) tests 20332 done 1 failed | 25 in flight, oldest 112s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................................... [941%]
.......................................................[contention-diag] +2821s soak 35p/273t rss 12.4G pss 11.1G swap 1.5G majflt 24506 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 7 descendant rss 0.2G pss 0.2G | host avail 21.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.12/0.04 io 3.05 cpu 12.68 | cgroup 12.2G/max oom_kill 0 | free scratch 311.8G/45147542i tmp 29.4G/1010801i workspace 311.8G/45147542i | repeat-01 collected 26/26 workers (60617 items) tests 20427 done 1 failed | 26 in flight, oldest 128s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
................. [944%]
........................................................................ [947%]
.......[contention-diag] +2836s soak 36p/266t rss 12.4G pss 11.2G swap 1.5G majflt 24694 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 8 descendant rss 0.3G pss 0.2G | host avail 18.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 1.18 cpu 11.54 | cgroup 12.2G/max oom_kill 0 | free scratch 311.8G/45147275i tmp 29.4G/1010801i workspace 311.8G/45147275i | repeat-01 collected 26/26 workers (60617 items) tests 20521 done 1 failed | 26 in flight, oldest 73s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
................................................................. [951%]
........................................................................ [954%]
........................................................................ [957%]
[contention-diag] +2852s soak 34p/265t rss 12.4G pss 11.2G swap 1.5G majflt 24833 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 6 descendant rss 0.2G pss 0.2G | host avail 18.0G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.76 cpu 11.35 | cgroup 12.2G/max oom_kill 0 | free scratch 311.8G/45146652i tmp 29.4G/1010801i workspace 311.8G/45146652i | repeat-01 collected 26/26 workers (60617 items) tests 20733 done 1 failed | 26 in flight, oldest 55s gw15 tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
........................................................................ [961%]
........................................................................ [964%]
........................................................................ [967%]
...................[contention-diag] +2867s soak 36p/266t rss 12.4G pss 11.2G swap 1.5G majflt 25155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 8 descendant rss 0.3G pss 0.2G | host avail 18.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.5 cpu 10.95 | cgroup 12.2G/max oom_kill 0 | free scratch 311.8G/45145828i tmp 29.4G/1010799i workspace 311.8G/45145828i | scratch used 0.6G in 116448 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 20961 done 1 failed | 26 in flight, oldest 70s gw15 tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
..................................................... [971%]
........................................................................ [974%]
........................................................................ [977%]
........................................................................ [981%]
....................................[contention-diag] +2884s soak 35p/266t rss 12.3G pss 11.0G swap 1.5G majflt 25319 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 7 descendant rss 0.1G pss 0.1G | host avail 16.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.15/0.0 io 0.81 cpu 11.19 | cgroup 12.0G/max oom_kill 0 | free scratch 311.8G/45144781i tmp 29.4G/1010801i workspace 311.8G/45144781i | repeat-01 collected 26/26 workers (60617 items) tests 21259 done 1 failed | 26 in flight, oldest 78s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.................................... [984%]
........................................................................ [987%]
........................................................................ [991%]
..........................................................[contention-diag] +2900s soak 41p/280t rss 12.5G pss 11.2G swap 1.5G majflt 25434 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 13 descendant rss 0.3G pss 0.2G | host avail 16.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 1.06 cpu 13.54 | cgroup 12.1G/max oom_kill 0 | free scratch 311.7G/45144086i tmp 29.4G/1010766i workspace 311.7G/45144086i | repeat-01 collected 26/26 workers (60617 items) tests 21511 done 1 failed | 26 in flight, oldest 72s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
.............. [994%]
........................................................................ [997%]
........................................................................ [1001%]
.s....................................................[contention-diag] +2915s soak 34p/258t rss 12.3G pss 11.0G swap 1.5G majflt 25646 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 6 descendant rss 0.2G pss 0.1G | host avail 18.0G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.79 cpu 14.71 | cgroup 12.0G/max oom_kill 0 | free scratch 311.7G/45141468i tmp 29.4G/1010766i workspace 311.7G/45141468i | repeat-01 collected 26/26 workers (60617 items) tests 21721 done 1 failed | 26 in flight, oldest 52s gw9 tests/ace/tui/test_projects_pane.py::test_projects_help_opens_from_list_and_inventory
.................. [1004%]
...................................................................[contention-diag] +2930s soak 36p/230t rss 12.4G pss 11.1G swap 1.6G majflt 25894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 8 descendant rss 0.2G pss 0.2G | host avail 18.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.46 cpu 12.91 | cgroup 12.1G/max oom_kill 0 | free scratch 311.7G/45140261i tmp 29.4G/1010766i workspace 311.7G/45140261i | repeat-01 collected 26/26 workers (60617 items) tests 21810 done 1 failed | 26 in flight, oldest 66s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
..... [1007%]
.......................................................s................ [1010%]
........................................................................ [1014%]
......................................................................[contention-diag] +2946s soak 38p/236t rss 12.4G pss 11.1G swap 1.5G majflt 26152 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 10 descendant rss 0.2G pss 0.1G | host avail 17.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.24/0.0 io 0.88 cpu 13.73 | cgroup 12.1G/max oom_kill 0 | free scratch 311.7G/45141554i tmp 29.4G/1010766i workspace 311.7G/45141554i | repeat-01 collected 26/26 workers (60617 items) tests 22029 done 1 failed | 26 in flight, oldest 81s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.. [1017%]
........................................................................ [1020%]
........................................................................ [1024%]
........................................................................ [1027%]
........................[contention-diag] +2961s soak 35p/219t rss 12.4G pss 11.1G swap 1.5G majflt 26326 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.2G pss 0.2G | host avail 18.9G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 2.46 cpu 16.33 | cgroup 12.1G/max oom_kill 0 | free scratch 311.7G/45141159i tmp 29.4G/1010765i workspace 311.7G/45141159i | repeat-01 collected 26/26 workers (60617 items) tests 22228 done 1 failed | 26 in flight, oldest 97s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
................................................ [1030%]
........................................................................ [1034%]
........................................................................ [1037%]
........................................................................ [1040%]
...........................[contention-diag] +2976s soak 35p/236t rss 12.5G pss 11.2G swap 1.5G majflt 26527 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.3G pss 0.2G | host avail 21.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.78 cpu 15.57 | cgroup 12.2G/max oom_kill 0 | free scratch 311.7G/45140188i tmp 29.4G/1010766i workspace 311.7G/45140187i | repeat-01 collected 26/26 workers (60617 items) tests 22548 done 1 failed | 26 in flight, oldest 112s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............................................. [1044%]
........................................................................ [1047%]
........................................................................ [1050%]
........................................................................ [1054%]
........................................................................ [1057%]
...................................................[contention-diag] +2992s soak 40p/195t rss 12.5G pss 11.2G swap 1.5G majflt 26708 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 12 descendant rss 0.4G pss 0.2G | host avail 20.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.06 cpu 18.87 | cgroup 12.2G/max oom_kill 0 | free scratch 311.7G/45139211i tmp 29.4G/1010766i workspace 311.7G/45139211i | scratch used 0.7G in 124598 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 22864 done 1 failed | 26 in flight, oldest 127s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
..................... [1060%]
........................................................................ [1064%]
........................................................................ [1067%]
........................................................................ [1070%]
........................................................................ [1074%]
....................[contention-diag] +3009s soak 36p/199t rss 12.5G pss 11.1G swap 1.5G majflt 27391 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 8 descendant rss 0.2G pss 0.2G | host avail 21.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 22.49 | cgroup 12.2G/max oom_kill 0 | free scratch 311.7G/45138509i tmp 29.4G/1010766i workspace 311.7G/45138509i | repeat-01 collected 26/26 workers (60617 items) tests 23267 done 1 failed | 26 in flight, oldest 63s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.................................................... [1077%]
........................................................................ [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
.........................................................[contention-diag] +3025s soak 35p/204t rss 12.4G pss 11.1G swap 1.5G majflt 27959 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.1G pss 0.1G | host avail 20.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.6 cpu 21.86 | cgroup 12.2G/max oom_kill 0 | free scratch 311.6G/45137595i tmp 29.4G/1010766i workspace 311.6G/45137595i | repeat-01 collected 26/26 workers (60617 items) tests 23593 done 1 failed | 25 in flight, oldest 79s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
............... [1090%]
........................................................................ [1094%]
........................................................................ [1097%]
........................................................................ [1100%]
........................................................................ [1104%]
........................................................................ [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
........................................................................ [1117%]
......................................................[contention-diag] +3040s soak 41p/202t rss 12.5G pss 11.2G swap 1.5G majflt 28146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 13 descendant rss 0.2G pss 0.2G | host avail 22.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 1.89 cpu 26.33 | cgroup 12.4G/max oom_kill 0 | free scratch 311.6G/45136051i tmp 29.4G/1010766i workspace 311.6G/45136051i | repeat-01 collected 26/26 workers (60617 items) tests 24238 done 1 failed | 26 in flight, oldest 94s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.................. [1120%]
........................................................................ [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
........[contention-diag] +3055s soak 36p/198t rss 12.6G pss 11.3G swap 1.5G majflt 29211 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 8 descendant rss 0.3G pss 0.3G | host avail 21.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.93 cpu 24.7 | cgroup 12.5G/max oom_kill 0 | free scratch 311.5G/45133913i tmp 29.4G/1010766i workspace 311.5G/45133913i | repeat-01 collected 26/26 workers (60617 items) tests 24487 done 1 failed | 26 in flight, oldest 109s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
................................................................ [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
......................................................................[contention-diag] +3071s soak 37p/193t rss 12.5G pss 11.2G swap 1.4G majflt 28652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 9 descendant rss 0.2G pss 0.1G | host avail 22.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.93 cpu 23.24 | cgroup 12.6G/max oom_kill 0 | free scratch 311.5G/45133160i tmp 29.4G/1010767i workspace 311.5G/45133160i | repeat-01 collected 26/26 workers (60617 items) tests 24766 done 1 failed | 26 in flight, oldest 125s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.. [1144%]
........................................................................ [1147%]
........................................................................ [1150%]
........................................................................ [1153%]
...................................................................[contention-diag] +3086s soak 35p/187t rss 12.4G pss 11.1G swap 1.4G majflt 28794 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 7 descendant rss 0.1G pss 0.0G | host avail 21.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.96 cpu 23.23 | cgroup 12.5G/max oom_kill 0 | free scratch 311.5G/45132356i tmp 29.4G/1010767i workspace 311.5G/45132356i | repeat-01 collected 26/26 workers (60617 items) tests 25033 done 1 failed | 26 in flight, oldest 140s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..... [1157%]
........................................................................ [1160%]
........................................................................ [1163%]
........................................................................ [1167%]
..............s........................................[contention-diag] +3101s soak 34p/188t rss 12.4G pss 11.2G swap 1.5G majflt 28875 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 6 descendant rss 0.1G pss 0.1G | host avail 21.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.69 cpu 21.57 | cgroup 12.6G/max oom_kill 0 | free scratch 311.5G/45131409i tmp 29.4G/1010767i workspace 311.5G/45131409i | repeat-01 collected 26/26 workers (60617 items) tests 25323 done 1 failed | 26 in flight, oldest 155s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................. [1170%]
........................................................................ [1173%]
........................................................................ [1177%]
........................................................................ [1180%]
........................................................................ [1183%]
..............[contention-diag] +3117s soak 33p/172t rss 12.4G pss 11.1G swap 1.4G majflt 29033 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 5 descendant rss 0.0G pss 0.0G | host avail 21.9G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.64 cpu 16.83 | cgroup 12.6G/max oom_kill 0 | free scratch 311.0G/45127242i tmp 29.4G/1010762i workspace 311.0G/45127242i | scratch used 0.8G in 138679 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 25595 done 1 failed | 26 in flight, oldest 171s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.......................................................... [1187%]
........................................................................ [1190%]
..........................[contention-diag] +3134s soak 34p/180t rss 12.4G pss 11.2G swap 1.4G majflt 29145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 6 descendant rss 0.1G pss 0.0G | host avail 23.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.32 cpu 20.29 | cgroup 12.6G/max oom_kill 0 | free scratch 311.0G/45126507i tmp 29.4G/1010767i workspace 311.0G/45126507i | repeat-01 collected 26/26 workers (60617 items) tests 25793 done 1 failed | 26 in flight, oldest 188s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.............................................. [1193%]
........................................................................ [1197%]
......................................................[contention-diag] +3150s soak 38p/189t rss 12.5G pss 11.2G swap 1.4G majflt 29384 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 10.9G, 10 descendant rss 0.1G pss 0.0G | host avail 22.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.12 cpu 22.8 | cgroup 12.7G/max oom_kill 0 | free scratch 311.0G/45126721i tmp 29.4G/1010767i workspace 311.0G/45126721i | repeat-01 collected 26/26 workers (60617 items) tests 25973 done 1 failed | 25 in flight, oldest 203s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................. [1200%]
........................................................................ [1203%]
........................................................................ [1207%]
........................................................................ [1210%]
........[contention-diag] +3165s soak 34p/172t rss 12.4G pss 11.2G swap 1.4G majflt 29593 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 10.9G, 6 descendant rss 0.0G pss 0.0G | host avail 22.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.53 cpu 21.48 | cgroup 12.7G/max oom_kill 0 | free scratch 311.0G/45125480i tmp 29.4G/1010767i workspace 311.0G/45125480i | repeat-01 collected 26/26 workers (60617 items) tests 26215 done 1 failed | 25 in flight, oldest 219s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................................ [1213%]
........................................................................ [1217%]
........................................................................ [1220%]
........................................................................ [1223%]
........................................................................ [1227%]
.................................[contention-diag] +3180s soak 33p/177t rss 12.5G pss 11.2G swap 1.4G majflt 29836 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 5 descendant rss 0.1G pss 0.0G | host avail 23.2G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.01 cpu 19.83 | cgroup 12.7G/max oom_kill 0 | free scratch 311.0G/45124608i tmp 29.4G/1010767i workspace 311.0G/45124608i | repeat-01 collected 26/26 workers (60617 items) tests 26597 done 1 failed | 25 in flight, oldest 234s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................... [1230%]
........................................................................ [1233%]
..................[contention-diag] +3196s soak 35p/186t rss 12.6G pss 11.3G swap 1.5G majflt 30102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 7 descendant rss 0.2G pss 0.2G | host avail 23.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.65 cpu 23.89 | cgroup 12.8G/max oom_kill 0 | free scratch 311.0G/45124517i tmp 29.4G/1010767i workspace 311.0G/45124517i | repeat-01 collected 26/26 workers (60617 items) tests 26726 done 1 failed | 25 in flight, oldest 249s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
...................................................... [1237%]
........................................................................ [1240%]
........................................................................ [1243%]
.................................[contention-diag] +3211s soak 31p/160t rss 12.6G pss 11.3G swap 1.4G majflt 30452 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 3 descendant rss 0.1G pss 0.1G | host avail 22.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.35 cpu 18.61 | cgroup 12.8G/max oom_kill 0 | free scratch 311.0G/45123446i tmp 29.4G/1010767i workspace 311.0G/45123446i | repeat-01 collected 26/26 workers (60617 items) tests 26952 done 1 failed | 25 in flight, oldest 265s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................... [1247%]
........................................................................ [1250%]
........................................................................ [1253%]
........................................................................ [1257%]
........................................................................ [1260%]
................[contention-diag] +3226s soak 33p/165t rss 12.7G pss 11.4G swap 1.4G majflt 30616 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 5 descendant rss 0.2G pss 0.2G | host avail 22.0G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.3/0.3 io 2.97 cpu 16.59 | cgroup 12.9G/max oom_kill 0 | free scratch 311.0G/45122243i tmp 29.4G/1010801i workspace 311.0G/45122243i | repeat-01 collected 26/26 workers (60617 items) tests 27296 done 1 failed | 25 in flight, oldest 218s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........................................................ [1263%]
........................................................................ [1267%]
........................................................................ [1270%]
..................................................[contention-diag] +3242s soak 39p/177t rss 12.8G pss 11.4G swap 1.4G majflt 30965 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 11 descendant rss 0.3G pss 0.2G | host avail 22.2G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 3.01 cpu 15.95 | cgroup 12.9G/max oom_kill 0 | free scratch 310.9G/45121516i tmp 29.4G/1010801i workspace 310.9G/45121516i | scratch used 0.8G in 148529 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 27518 done 1 failed | 24 in flight, oldest 234s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...................... [1273%]
........................................................................ [1277%]
........................................................................ [1280%]
........................................................................ [1283%]
..........[contention-diag] +3259s soak 34p/164t rss 12.8G pss 11.4G swap 1.4G majflt 31422 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 6 descendant rss 0.3G pss 0.1G | host avail 23.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 3.82 cpu 18.88 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45120939i tmp 29.4G/1010801i workspace 311.0G/45120939i | repeat-01 collected 26/26 workers (60617 items) tests 27789 done 1 failed | 24 in flight, oldest 251s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.............................................................. [1287%]
........................................................................ [1290%]
........................................................................ [1293%]
........................................................................ [1296%]
.....................................................[contention-diag] +3274s soak 40p/184t rss 12.8G pss 11.4G swap 1.4G majflt 31486 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.0G, 12 descendant rss 0.2G pss 0.1G | host avail 24.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.5 cpu 23.6 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45119985i tmp 29.4G/1010801i workspace 311.0G/45119985i | repeat-01 collected 26/26 workers (60617 items) tests 28131 done 1 failed | 25 in flight, oldest 101s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................... [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
.....................................................................[contention-diag] +3290s soak 40p/185t rss 12.8G pss 11.5G swap 1.4G majflt 32110 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.0G, 12 descendant rss 0.3G pss 0.2G | host avail 23.3G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.3 cpu 21.16 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45119220i tmp 29.4G/1010800i workspace 311.0G/45119220i | repeat-01 collected 26/26 workers (60617 items) tests 28359 done 1 failed | 25 in flight, oldest 116s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
... [1310%]
........................................................................ [1313%]
........................................................................ [1316%]
........................................................................ [1320%]
...............................[contention-diag] +3305s soak 34p/179t rss 12.7G pss 11.4G swap 1.4G majflt 32564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 6 descendant rss 0.1G pss 0.1G | host avail 24.0G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 3.73 cpu 19.79 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45118381i tmp 29.4G/1010211i workspace 311.0G/45118381i | repeat-01 collected 26/26 workers (60617 items) tests 28612 done 1 failed | 25 in flight, oldest 131s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
......................................... [1323%]
........................................................................ [1326%]
........................................................................ [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
........................................................................ [1340%]
.........[contention-diag] +3320s soak 38p/172t rss 12.7G pss 11.4G swap 1.4G majflt 32842 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 10 descendant rss 0.2G pss 0.1G | host avail 23.2G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 4.04 cpu 22.27 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45116333i tmp 29.4G/1010207i workspace 311.0G/45116333i | repeat-01 collected 26/26 workers (60617 items) tests 29014 done 1 failed | 25 in flight, oldest 147s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................... [1343%]
........................................................................ [1346%]
........................................................................ [1350%]
.............................................[contention-diag] +3336s soak 38p/176t rss 12.8G pss 11.5G swap 1.4G majflt 32998 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 10 descendant rss 0.2G pss 0.2G | host avail 23.3G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.14 cpu 25.18 | cgroup 13.1G/max oom_kill 0 | free scratch 311.0G/45115973i tmp 29.4G/1010207i workspace 311.0G/45115973i | repeat-01 collected 26/26 workers (60617 items) tests 29275 done 1 failed | 25 in flight, oldest 162s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................... [1353%]
........................................................................ [1356%]
........................................................................ [1360%]
......................................................................[contention-diag] +3351s soak 35p/170t rss 12.7G pss 11.4G swap 1.4G majflt 33143 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 7 descendant rss 0.1G pss 0.1G | host avail 24.2G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.51 cpu 21.95 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45115314i tmp 29.4G/1010207i workspace 311.0G/45115314i | repeat-01 collected 26/26 workers (60617 items) tests 29497 done 1 failed | 25 in flight, oldest 178s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.. [1363%]
........................................................................ [1366%]
........................................................................ [1370%]
........................................................................ [1373%]
.................[contention-diag] +3366s soak 36p/169t rss 12.7G pss 11.4G swap 1.4G majflt 33256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 8 descendant rss 0.1G pss 0.1G | host avail 23.3G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.48 cpu 21.1 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45115006i tmp 29.4G/1010207i workspace 311.0G/45115006i | scratch used 0.8G in 160306 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 29711 done 1 failed | 25 in flight, oldest 193s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....................................................... [1376%]
........................................................................ [1380%]
........................................................................ [1383%]
........................................................................ [1386%]
.............................................................[contention-diag] +3384s soak 35p/173t rss 12.7G pss 11.4G swap 1.3G majflt 33344 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 7 descendant rss 0.1G pss 0.1G | host avail 22.2G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.57 cpu 17.05 | cgroup 13.1G/max oom_kill 0 | free scratch 311.0G/45113511i tmp 29.4G/1010207i workspace 311.0G/45113511i | repeat-01 collected 26/26 workers (60617 items) tests 30080 done 1 failed | 25 in flight, oldest 210s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........... [1390%]
........................................................................ [1393%]
........................................................................ [1396%]
........................................................................ [1400%]
........................................................................ [1403%]
........................................................................ [1406%]
.............................................[contention-diag] +3399s soak 35p/163t rss 12.8G pss 11.5G swap 1.3G majflt 33444 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 7 descendant rss 0.2G pss 0.1G | host avail 22.8G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.63 cpu 20.96 | cgroup 13.1G/max oom_kill 0 | free scratch 311.0G/45113032i tmp 29.4G/1010801i workspace 311.0G/45113032i | repeat-01 collected 26/26 workers (60617 items) tests 30483 done 1 failed | 25 in flight, oldest 226s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................... [1410%]
........................................................................ [1413%]
........................................................................ [1416%]
........................................................................ [1420%]
........................................................................ [1423%]
..............................[contention-diag] +3414s soak 33p/164t rss 12.7G pss 11.4G swap 1.4G majflt 33569 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.3G pss 11.1G, 5 descendant rss 0.2G pss 0.1G | host avail 22.5G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 1.26/1.26 io 3.34 cpu 19.77 | cgroup 13.3G/max oom_kill 0 | free scratch 310.9G/45111954i tmp 29.4G/1010799i workspace 310.9G/45111954i | repeat-01 collected 26/26 workers (60617 items) tests 30824 done 1 failed | 25 in flight, oldest 241s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.......................................... [1426%]
........................................................................ [1430%]
........................................................................ [1433%]
........................................................................ [1436%]
........................................................................ [1440%]
.....[contention-diag] +3430s soak 31p/163t rss 12.6G pss 11.3G swap 1.3G majflt 33976 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.1G, 3 descendant rss 0.0G pss 0.0G | host avail 22.0G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.3/0.25 io 5.91 cpu 20.55 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45110402i tmp 29.4G/1010800i workspace 311.0G/45110402i | repeat-01 collected 26/26 workers (60617 items) tests 31180 done 1 failed | 25 in flight, oldest 256s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................................... [1443%]
........................................................................ [1446%]
........................................................................ [1449%]
........................................................................ [1453%]
................................................................[contention-diag] +3445s soak 31p/172t rss 12.7G pss 11.4G swap 1.3G majflt 34183 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.1G, 3 descendant rss 0.1G pss 0.0G | host avail 23.0G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.07/0.06 io 4.43 cpu 17.67 | cgroup 13.0G/max oom_kill 0 | free scratch 311.0G/45109298i tmp 29.4G/1010800i workspace 311.0G/45109298i | repeat-01 collected 26/26 workers (60617 items) tests 31524 done 1 failed | 25 in flight, oldest 272s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........ [1456%]
........................................................................ [1459%]
........................................................................ [1463%]
........................................................................ [1466%]
..........................................................[contention-diag] +3461s soak 33p/182t rss 12.8G pss 11.5G swap 1.3G majflt 34309 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 23.9G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 3.43 cpu 16.19 | cgroup 13.1G/max oom_kill 0 | free scratch 311.0G/45108530i tmp 29.4G/1010800i workspace 311.0G/45108530i | repeat-01 collected 26/26 workers (60617 items) tests 31806 done 1 failed | 23 in flight, oldest 287s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............. [1469%]
........................................................................ [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1483%]
........................................................................ [1486%]
...................................................................[contention-diag] +3476s soak 38p/165t rss 12.9G pss 11.5G swap 1.3G majflt 34615 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.1G, 10 descendant rss 0.2G pss 0.1G | host avail 26.5G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.4 cpu 18.99 | cgroup 13.2G/max oom_kill 0 | free scratch 311.0G/45108366i tmp 29.4G/1010800i workspace 311.0G/45108366i | repeat-01 collected 26/26 workers (60617 items) tests 32237 done 1 failed | 24 in flight, oldest 303s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
..... [1489%]
........................................................................ [1493%]
........................................................................ [1496%]
........................................................................ [1499%]
........................................................................ [1503%]
.........................................[contention-diag] +3492s soak 33p/171t rss 12.8G pss 11.5G swap 1.3G majflt 34675 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.2G, 5 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.34 cpu 15.6 | cgroup 13.1G/max oom_kill 0 | free scratch 311.0G/45107558i tmp 29.4G/1010800i workspace 311.0G/45107558i | scratch used 0.9G in 170022 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 32523 done 1 failed | 24 in flight, oldest 318s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................... [1506%]
........................................................................ [1509%]
........................................................................ [1513%]
........................................................................ [1516%]
............................................[contention-diag] +3509s soak 33p/157t rss 12.8G pss 11.5G swap 1.3G majflt 34737 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.2G, 5 descendant rss 0.1G pss 0.1G | host avail 23.6G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.67 cpu 18.51 | cgroup 13.2G/max oom_kill 0 | free scratch 311.0G/45106857i tmp 29.4G/1010800i workspace 311.0G/45106857i | repeat-01 collected 26/26 workers (60617 items) tests 32865 done 1 failed | 23 in flight, oldest 335s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................ [1519%]
........................................................................ [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
.............................[contention-diag] +3524s soak 36p/174t rss 13.0G pss 11.6G swap 1.4G majflt 34800 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.2G, 8 descendant rss 0.3G pss 0.2G | host avail 23.7G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.18 cpu 18.27 | cgroup 13.3G/max oom_kill 0 | free scratch 311.0G/45105201i tmp 29.4G/1010801i workspace 311.0G/45105201i | repeat-01 collected 26/26 workers (60617 items) tests 33149 done 1 failed | 24 in flight, oldest 346s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................................... [1533%]
........................................................................ [1536%]
........................................................................ [1539%]
...........................................[contention-diag] +3540s soak 32p/157t rss 12.8G pss 11.5G swap 1.3G majflt 34862 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.4G pss 11.2G, 4 descendant rss 0.1G pss 0.1G | host avail 22.4G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 1.17 cpu 16.41 | cgroup 13.4G/max oom_kill 0 | free scratch 310.9G/45104099i tmp 29.4G/1010801i workspace 310.9G/45104099i | repeat-01 collected 26/26 workers (60617 items) tests 33369 done 1 failed | 24 in flight, oldest 361s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................. [1543%]
........................................................................ [1546%]
........................................................................ [1549%]
........................................................................ [1553%]
........................................................................ [1556%]
........................................................[contention-diag] +3555s soak 33p/157t rss 12.9G pss 11.6G swap 1.3G majflt 35075 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.2G, 5 descendant rss 0.2G pss 0.2G | host avail 23.7G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.5/0.5 io 0.52 cpu 17.88 | cgroup 13.3G/max oom_kill 0 | free scratch 310.9G/45102999i tmp 29.4G/1010801i workspace 310.9G/45103000i | repeat-01 collected 26/26 workers (60617 items) tests 33739 done 1 failed | 24 in flight, oldest 377s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................ [1559%]
........................................................................ [1563%]
........................................................................ [1566%]
........................................................................ [1569%]
........................................................................ [1573%]
............................................................[contention-diag] +3570s soak 34p/167t rss 13.1G pss 11.7G swap 1.3G majflt 35175 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.2G, 6 descendant rss 0.3G pss 0.3G | host avail 24.4G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 0.82 cpu 19.46 | cgroup 13.5G/max oom_kill 0 | free scratch 310.9G/45102059i tmp 29.4G/1010801i workspace 310.9G/45102059i | repeat-01 collected 26/26 workers (60617 items) tests 34103 done 1 failed | 24 in flight, oldest 392s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............ [1576%]
........................................................................ [1579%]
........................................................................ [1583%]
........................................................................ [1586%]
..[contention-diag] +3586s soak 34p/161t rss 13.1G pss 11.7G swap 1.4G majflt 35264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 6 descendant rss 0.3G pss 0.2G | host avail 24.1G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.01 cpu 19.79 | cgroup 13.5G/max oom_kill 0 | free scratch 310.9G/45101498i tmp 29.4G/1010801i workspace 310.9G/45101498i | repeat-01 collected 26/26 workers (60617 items) tests 34344 done 1 failed | 24 in flight, oldest 408s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
...................................................................... [1589%]
........................................................................ [1592%]
.......................................................s................ [1596%]
......................[contention-diag] +3601s soak 38p/170t rss 13.1G pss 11.7G swap 1.4G majflt 35354 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 10 descendant rss 0.3G pss 0.2G | host avail 22.9G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 20.55 | cgroup 13.4G/max oom_kill 0 | free scratch 310.9G/45100407i tmp 29.4G/1010801i workspace 310.9G/45100407i | repeat-01 collected 26/26 workers (60617 items) tests 34582 done 1 failed | 24 in flight, oldest 423s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
.................................................. [1599%]
........................................................................ [1602%]
........................................................................ [1606%]
........................................................................ [1609%]
........................................................................ [1612%]
.............[contention-diag] +3616s soak 35p/173t rss 13.0G pss 11.6G swap 1.4G majflt 35436 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 7 descendant rss 0.2G pss 0.1G | host avail 22.9G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 16.16 | cgroup 13.3G/max oom_kill 0 | free scratch 310.6G/45098844i tmp 29.4G/1010801i workspace 310.6G/45098844i | scratch used 0.9G in 179927 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 34870 done 1 failed | 24 in flight, oldest 438s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
........................................................... [1616%]
........................................................................ [1619%]
........................................................................ [1622%]
........................................................................ [1626%]
.............................................[contention-diag] +3634s soak 31p/170t rss 12.9G pss 11.6G swap 1.3G majflt 35539 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 3 descendant rss 0.1G pss 0.1G | host avail 23.7G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.65/0.48 io 0.75 cpu 18.3 | cgroup 13.3G/max oom_kill 0 | free scratch 310.5G/45097646i tmp 29.4G/1010801i workspace 310.5G/45097646i | repeat-01 collected 26/26 workers (60617 items) tests 35250 done 1 failed | 24 in flight, oldest 456s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
........................... [1629%]
........................................................................ [1632%]
........................................................................ [1636%]
........................................................................ [1639%]
.........[contention-diag] +3649s soak 30p/164t rss 12.9G pss 11.5G swap 1.3G majflt 35572 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 2 descendant rss 0.1G pss 0.0G | host avail 22.7G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.13/0.09 io 0.43 cpu 19.77 | cgroup 13.4G/max oom_kill 0 | free scratch 310.5G/45096847i tmp 29.4G/1010801i workspace 310.5G/45096847i | repeat-01 collected 26/26 workers (60617 items) tests 35493 done 1 failed | 24 in flight, oldest 305s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
............................................................... [1642%]
........................................................................ [1646%]
........................................................................ [1649%]
........................................................................ [1652%]
...........................................................[contention-diag] +3665s soak 33p/177t rss 12.9G pss 11.5G swap 1.3G majflt 35729 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 5 descendant rss 0.0G pss 0.0G | host avail 19.1G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.53/0.53 io 0.3 cpu 19.8 | cgroup 13.3G/max oom_kill 0 | free scratch 310.4G/45095699i tmp 29.4G/1010801i workspace 310.4G/45095699i | repeat-01 collected 26/26 workers (60617 items) tests 35837 done 1 failed | 24 in flight, oldest 321s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
............. [1656%]
........................................................................ [1659%]
........................................................................ [1662%]
........................................................................ [1666%]
........................................................................ [1669%]
........................................................................ [1672%]
...[contention-diag] +3680s soak 31p/176t rss 12.9G pss 11.5G swap 1.4G majflt 35837 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 25.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 1.25/1.2 io 1.36 cpu 21.14 | cgroup 13.3G/max oom_kill 0 | free scratch 310.4G/45094658i tmp 29.4G/1010801i workspace 310.4G/45094658i | repeat-01 collected 26/26 workers (60617 items) tests 36188 done 1 failed | 24 in flight, oldest 336s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
..................................................................... [1676%]
........................................................................ [1679%]
........................................................................ [1682%]
........................................................................ [1686%]
......................................................................[contention-diag] +3695s soak 32p/180t rss 13.0G pss 11.6G swap 1.4G majflt 35914 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 4 descendant rss 0.2G pss 0.1G | host avail 25.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.25/0.24 io 1.37 cpu 28.19 | cgroup 13.4G/max oom_kill 0 | free scratch 310.4G/45093489i tmp 29.4G/1010801i workspace 310.4G/45093489i | repeat-01 collected 26/26 workers (60617 items) tests 36550 done 1 failed | 24 in flight, oldest 351s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.. [1689%]
........................................................................ [1692%]
........................................................................ [1696%]
........................................................................ [1699%]
...............................................[contention-diag] +3711s soak 32p/187t rss 12.9G pss 11.5G swap 1.4G majflt 36186 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 4 descendant rss 0.1G pss 0.1G | host avail 24.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.15/0.04 io 0.91 cpu 24.62 | cgroup 13.4G/max oom_kill 0 | free scratch 310.4G/45092770i tmp 29.4G/1010801i workspace 310.4G/45092770i | repeat-01 collected 26/26 workers (60617 items) tests 36835 done 1 failed | 24 in flight, oldest 367s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
......................... [1702%]
........................................................................ [1706%]
........................................................................ [1709%]
........................................................................ [1712%]
............................................[contention-diag] +3726s soak 32p/180t rss 13.0G pss 11.6G swap 1.3G majflt 36251 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 4 descendant rss 0.1G pss 0.1G | host avail 24.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 0.75 cpu 22.99 | cgroup 13.4G/max oom_kill 0 | free scratch 310.4G/45091857i tmp 29.4G/1010801i workspace 310.4G/45091857i | repeat-01 collected 26/26 workers (60617 items) tests 37105 done 1 failed | 24 in flight, oldest 382s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1716%]
........................................................................ [1719%]
........................................................................ [1722%]
........................................................................ [1726%]
........................................................................ [1729%]
........................................................................ [1732%]
........................................................................ [1735%]
............[contention-diag] +3742s soak 34p/184t rss 13.0G pss 11.6G swap 1.3G majflt 36439 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 6 descendant rss 0.1G pss 0.1G | host avail 24.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 25.23 | cgroup 13.4G/max oom_kill 0 | free scratch 310.6G/45089904i tmp 29.4G/1010799i workspace 310.6G/45089904i | scratch used 0.9G in 165031 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 37537 done 1 failed | 24 in flight, oldest 397s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...........................................................s [1739%]
........................................................................ [1742%]
........................................................................ [1745%]
........................................................................ [1749%]
.......[contention-diag] +3759s soak 35p/187t rss 13.0G pss 11.6G swap 1.3G majflt 36539 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.5G pss 11.2G, 7 descendant rss 0.1G pss 0.1G | host avail 22.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 22.83 | cgroup 13.4G/max oom_kill 0 | free scratch 310.5G/45089307i tmp 29.4G/1010798i workspace 310.5G/45089307i | repeat-01 collected 26/26 workers (60617 items) tests 37869 done 1 failed | 24 in flight, oldest 415s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................................................................. [1752%]
........................................................................ [1755%]
........................................................................ [1759%]
.............................................................[contention-diag] +3774s soak 37p/196t rss 13.2G pss 11.7G swap 1.4G majflt 36592 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 9 descendant rss 0.3G pss 0.2G | host avail 21.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.7 cpu 21.82 | cgroup 13.5G/max oom_kill 0 | free scratch 310.4G/45088086i tmp 29.4G/1010798i workspace 310.4G/45088086i | repeat-01 collected 26/26 workers (60617 items) tests 38149 done 1 failed | 24 in flight, oldest 430s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
........... [1762%]
........................................................................ [1765%]
........................................................................ [1769%]
.......................[contention-diag] +3790s soak 39p/197t rss 13.1G pss 11.6G swap 1.4G majflt 36919 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 11 descendant rss 0.2G pss 0.1G | host avail 24.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.42/0.0 io 0.24 cpu 22.39 | cgroup 13.4G/max oom_kill 0 | free scratch 310.3G/45087395i tmp 29.4G/1010794i workspace 310.3G/45087395i | repeat-01 collected 26/26 workers (60617 items) tests 38327 done 1 failed | 24 in flight, oldest 446s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...s............................................. [1772%]
........................................................................ [1775%]
.........s....................................[contention-diag] +3805s soak 38p/191t rss 13.2G pss 11.8G swap 1.3G majflt 37115 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 10 descendant rss 0.3G pss 0.3G | host avail 23.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.35 cpu 21.39 | cgroup 13.6G/max oom_kill 0 | free scratch 310.5G/45087174i tmp 29.4G/1010795i workspace 310.5G/45087174i | repeat-01 collected 26/26 workers (60617 items) tests 38491 done 1 failed | 24 in flight, oldest 461s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [1779%]
........................................................................ [1782%]
........................................................................ [1785%]
........................................................................ [1789%]
........................................................................ [1792%]
........................................[contention-diag] +3820s soak 34p/181t rss 13.2G pss 11.7G swap 1.3G majflt 37145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.3G, 6 descendant rss 0.3G pss 0.2G | host avail 23.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.08 cpu 23.29 | cgroup 13.6G/max oom_kill 0 | free scratch 310.4G/45086420i tmp 29.4G/1010795i workspace 310.4G/45086420i | repeat-01 collected 26/26 workers (60617 items) tests 38819 done 1 failed | 24 in flight, oldest 335s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................ [1795%]
........................................................................ [1799%]
........................................................................ [1802%]
........................................................................ [1805%]
..............[contention-diag] +3836s soak 36p/199t rss 13.2G pss 11.8G swap 1.4G majflt 37214 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.3G, 8 descendant rss 0.3G pss 0.2G | host avail 22.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 20.92 | cgroup 13.6G/max oom_kill 0 | free scratch 310.4G/45085529i tmp 29.4G/1010795i workspace 310.4G/45085529i | repeat-01 collected 26/26 workers (60617 items) tests 39105 done 1 failed | 24 in flight, oldest 351s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................................................... [1809%]
........................................................................ [1812%]
........................................................................ [1815%]
........................................................................ [1819%]
...[contention-diag] +3851s soak 40p/193t rss 13.3G pss 11.9G swap 1.4G majflt 37393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.3G, 12 descendant rss 0.4G pss 0.3G | host avail 20.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.79 cpu 21.42 | cgroup 13.8G/max oom_kill 0 | free scratch 310.3G/45084288i tmp 29.4G/1010795i workspace 310.3G/45084288i | repeat-01 collected 26/26 workers (60617 items) tests 39383 done 1 failed | 24 in flight, oldest 366s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..................................................................... [1822%]
........................................................................ [1825%]
........................................................................ [1829%]
......[contention-diag] +3866s soak 31p/173t rss 13.1G pss 11.7G swap 1.4G majflt 37643 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 3 descendant rss 0.2G pss 0.2G | host avail 23.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.74/0.74 io 2.72 cpu 19.12 | cgroup 13.6G/max oom_kill 0 | free scratch 310.2G/45083680i tmp 29.4G/1010795i workspace 310.2G/45083680i | scratch used 1.0G in 194949 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 39561 done 1 failed | 22 in flight, oldest 382s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................................................................. [1832%]
........................................................................ [1835%]
..............................................[contention-diag] +3884s soak 36p/184t rss 13.3G pss 11.8G swap 1.4G majflt 37924 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 8 descendant rss 0.4G pss 0.3G | host avail 24.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.2/0.12 io 1.53 cpu 21.92 | cgroup 13.8G/max oom_kill 0 | free scratch 310.2G/45083688i tmp 29.4G/1010795i workspace 310.2G/45083688i | repeat-01 collected 26/26 workers (60617 items) tests 39780 done 1 failed | 24 in flight, oldest 399s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [1839%]
........................................................................ [1842%]
........................................................................ [1845%]
..............................................[contention-diag] +3899s soak 35p/187t rss 13.3G pss 11.8G swap 1.3G majflt 37976 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 7 descendant rss 0.4G pss 0.3G | host avail 23.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 1.0 cpu 20.24 | cgroup 14.3G/max oom_kill 0 | free scratch 309.9G/45082529i tmp 29.4G/1010795i workspace 309.9G/45082529i | repeat-01 collected 26/26 workers (60617 items) tests 39990 done 1 failed | 24 in flight, oldest 414s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [1849%]
........................................................................ [1852%]
............................................................[contention-diag] +3915s soak 36p/197t rss 13.3G pss 11.8G swap 1.4G majflt 38136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 8 descendant rss 0.4G pss 0.3G | host avail 21.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.76 cpu 20.01 | cgroup 14.5G/max oom_kill 0 | free scratch 309.7G/45081976i tmp 29.4G/1010795i workspace 309.7G/45081976i | repeat-01 collected 26/26 workers (60617 items) tests 40163 done 1 failed | 24 in flight, oldest 430s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............ [1855%]
........................................................................ [1859%]
........................................................................ [1862%]
........................................................................ [1865%]
........................................................................ [1869%]
........................................................................ [1872%]
..............................[contention-diag] +3930s soak 40p/201t rss 13.3G pss 11.8G swap 1.4G majflt 38193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.2G, 12 descendant rss 0.3G pss 0.3G | host avail 20.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.85 cpu 21.44 | cgroup 13.9G/max oom_kill 0 | free scratch 310.1G/45080702i tmp 29.4G/1010795i workspace 310.1G/45080702i | repeat-01 collected 26/26 workers (60617 items) tests 40531 done 1 failed | 24 in flight, oldest 445s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................................... [1875%]
..................s..................................................... [1878%]
........................................................................ [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
........................................................................ [1892%]
............................[contention-diag] +3945s soak 42p/198t rss 13.4G pss 11.9G swap 1.4G majflt 38547 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.3G, 14 descendant rss 0.5G pss 0.4G | host avail 18.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.49 cpu 21.07 | cgroup 14.0G/max oom_kill 0 | free scratch 310.1G/45079856i tmp 29.4G/1010795i workspace 310.1G/45079856i | repeat-01 collected 26/26 workers (60617 items) tests 40967 done 1 failed | 23 in flight, oldest 460s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................ [1895%]
........................................................................ [1898%]
........................................................................ [1902%]
........................................................................ [1905%]
........................................................................ [1908%]
.....................................[contention-diag] +3961s soak 42p/192t rss 13.3G pss 11.9G swap 1.4G majflt 38635 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 14 descendant rss 0.3G pss 0.3G | host avail 19.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 1.64 cpu 19.83 | cgroup 13.9G/max oom_kill 0 | free scratch 309.7G/45078267i tmp 29.4G/1010795i workspace 309.7G/45078267i | repeat-01 collected 26/26 workers (60617 items) tests 41346 done 1 failed | 24 in flight, oldest 213s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................................... [1912%]
........................................................................ [1915%]
........................................................................ [1918%]
........................................................................ [1922%]
..........................[contention-diag] +3976s soak 33p/181t rss 13.3G pss 11.9G swap 1.4G majflt 38937 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 5 descendant rss 0.3G pss 0.3G | host avail 22.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.92 cpu 22.36 | cgroup 14.0G/max oom_kill 0 | free scratch 309.8G/45076690i tmp 29.4G/1010795i workspace 309.8G/45076690i | repeat-01 collected 26/26 workers (60617 items) tests 41624 done 1 failed | 24 in flight, oldest 229s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
.............................................. [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
..................................................[contention-diag] +3992s soak 34p/188t rss 13.3G pss 11.9G swap 1.4G majflt 39252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 6 descendant rss 0.3G pss 0.3G | host avail 21.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.9 cpu 21.72 | cgroup 14.1G/max oom_kill 0 | free scratch 309.8G/45075655i tmp 29.4G/1010795i workspace 309.8G/45075654i | scratch used 0.7G in 139014 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 41828 done 1 failed | 24 in flight, oldest 244s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
...................... [1935%]
........................................................................ [1938%]
........................................................................ [1942%]
........................................................................ [1945%]
........................................................................ [1948%]
.................................[contention-diag] +4009s soak 44p/191t rss 13.4G pss 12.0G swap 1.4G majflt 39437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 16 descendant rss 0.4G pss 0.4G | host avail 20.9G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.88 cpu 18.65 | cgroup 14.1G/max oom_kill 0 | free scratch 309.4G/45063927i tmp 29.4G/1010795i workspace 309.4G/45063927i | repeat-01 collected 26/26 workers (60617 items) tests 42207 done 1 failed | 22 in flight, oldest 262s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
....................................... [1952%]
........................................................................ [1955%]
........................................................................ [1958%]
........................................................................ [1962%]
...............................................[contention-diag] +4024s soak 38p/198t rss 13.5G pss 12.0G swap 1.4G majflt 39486 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 10 descendant rss 0.5G pss 0.4G | host avail 21.4G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.18 cpu 13.79 | cgroup 14.1G/max oom_kill 0 | free scratch 309.1G/45061999i tmp 29.4G/1010795i workspace 309.1G/45061999i | repeat-01 collected 26/26 workers (60617 items) tests 42523 done 1 failed | 24 in flight, oldest 277s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
......................... [1965%]
........................................................................ [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
........................................................................ [1978%]
....................................................[contention-diag] +4040s soak 34p/189t rss 13.4G pss 12.0G swap 1.4G majflt 39584 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 6 descendant rss 0.4G pss 0.4G | host avail 20.4G/62.7G swapfree 52.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.74 cpu 14.81 | cgroup 14.1G/max oom_kill 0 | free scratch 309.1G/45060652i tmp 29.4G/1010795i workspace 309.1G/45060652i | repeat-01 collected 26/26 workers (60617 items) tests 42884 done 1 failed | 24 in flight, oldest 292s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.................... [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
........................................................................ [1992%]
........................................................................ [1995%]
.............................[contention-diag] +4055s soak 36p/192t rss 13.6G pss 12.1G swap 1.4G majflt 39634 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 8 descendant rss 0.5G pss 0.4G | host avail 20.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 2.12 cpu 18.76 | cgroup 14.2G/max oom_kill 0 | free scratch 309.1G/45059538i tmp 29.4G/1010793i workspace 309.1G/45059538i | repeat-01 collected 26/26 workers (60617 items) tests 43228 done 1 failed | 24 in flight, oldest 308s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........................................... [1998%]
........................................................................ [2002%]
........................................................................ [2005%]
........................................................................ [2008%]
........................................................................ [2012%]
............................[contention-diag] +4071s soak 41p/195t rss 13.8G pss 12.3G swap 1.4G majflt 39729 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 13 descendant rss 0.8G pss 0.7G | host avail 18.8G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.1 cpu 21.19 | cgroup 14.5G/max oom_kill 0 | free scratch 309.1G/45059679i tmp 29.4G/1010795i workspace 309.1G/45059679i | repeat-01 collected 26/26 workers (60617 items) tests 43551 done 1 failed | 22 in flight, oldest 255s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................ [2015%]
........................................................................ [2018%]
........................................................................ [2021%]
........................................................................ [2025%]
........................................................................ [2028%]
........................................................................ [2031%]
........................................................................ [2035%]
........................................................[contention-diag] +4086s soak 40p/195t rss 13.7G pss 12.2G swap 1.4G majflt 39821 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 12 descendant rss 0.7G pss 0.6G | host avail 19.0G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.28/0.19 io 1.44 cpu 20.39 | cgroup 14.3G/max oom_kill 0 | free scratch 309.1G/45058536i tmp 29.4G/1010795i workspace 309.1G/45058536i | repeat-01 collected 26/26 workers (60617 items) tests 44118 done 1 failed | 22 in flight, oldest 270s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................ [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
..................................................................[contention-diag] +4101s soak 37p/191t rss 13.8G pss 12.3G swap 1.4G majflt 39863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 9 descendant rss 0.7G pss 0.6G | host avail 19.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.03 io 0.47 cpu 17.94 | cgroup 14.4G/max oom_kill 0 | free scratch 309.0G/45057315i tmp 29.4G/1010795i workspace 309.0G/45057315i | repeat-01 collected 26/26 workers (60617 items) tests 44482 done 1 failed | 23 in flight, oldest 286s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...... [2055%]
........................................................................ [2058%]
........................................................................ [2061%]
........................................................................ [2065%]
..................................................[contention-diag] +4117s soak 39p/188t rss 13.9G pss 12.4G swap 1.4G majflt 39914 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.3G, 11 descendant rss 0.8G pss 0.7G | host avail 19.1G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.76 cpu 19.78 | cgroup 14.5G/max oom_kill 0 | free scratch 309.0G/45057191i tmp 29.4G/1010795i workspace 309.0G/45057191i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 44736 done 1 failed | 22 in flight, oldest 301s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................... [2068%]
........................................................................ [2071%]
........................................................................ [2075%]
...................................................................[contention-diag] +4134s soak 35p/190t rss 13.8G pss 12.3G swap 1.4G majflt 39972 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 7 descendant rss 0.7G pss 0.6G | host avail 17.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.96 cpu 15.29 | cgroup 14.4G/max oom_kill 0 | free scratch 308.7G/45056300i tmp 29.4G/1010795i workspace 308.7G/45056300i | repeat-01 collected 26/26 workers (60617 items) tests 44986 done 1 failed | 21 in flight, oldest 318s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..... [2078%]
........................................................................ [2081%]
........................................................................ [2085%]
........................................................................ [2088%]
........................................................................ [2091%]
........................................................................ [2095%]
.................[contention-diag] +4150s soak 38p/180t rss 13.8G pss 12.3G swap 1.4G majflt 40121 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 10 descendant rss 0.7G pss 0.6G | host avail 22.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.35 cpu 20.57 | cgroup 14.5G/max oom_kill 0 | free scratch 308.7G/45055224i tmp 29.4G/1010795i workspace 308.7G/45055224i | repeat-01 collected 26/26 workers (60617 items) tests 45365 done 1 failed | 22 in flight, oldest 334s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
....................................................... [2098%]
........................................................................ [2101%]
........................................................................ [2105%]
........................................................................ [2108%]
........................................................................ [2111%]
........................................................................ [2115%]
........................................................................ [2118%]
..........[contention-diag] +4165s soak 36p/191t rss 13.9G pss 12.4G swap 1.4G majflt 40216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 8 descendant rss 0.8G pss 0.7G | host avail 23.9G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.7 cpu 27.37 | cgroup 14.6G/max oom_kill 0 | free scratch 308.7G/45053535i tmp 29.4G/1010795i workspace 308.7G/45053535i | repeat-01 collected 26/26 workers (60617 items) tests 45869 done 1 failed | 22 in flight, oldest 349s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.............................................................. [2121%]
........................................................................ [2125%]
............................s........................................... [2128%]
........................................................................ [2131%]
.....................................................[contention-diag] +4180s soak 36p/200t rss 14.0G pss 12.5G swap 1.4G majflt 40321 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 8 descendant rss 0.9G pss 0.8G | host avail 23.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.75 cpu 23.13 | cgroup 14.7G/max oom_kill 0 | free scratch 308.7G/45053128i tmp 29.4G/1010795i workspace 308.7G/45053127i | repeat-01 collected 26/26 workers (60617 items) tests 46188 done 1 failed | 20 in flight, oldest 365s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................... [2135%]
........................................................................ [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........................................................................ [2155%]
........................................................................ [2158%]
...............................................[contention-diag] +4196s soak 37p/190t rss 14.1G pss 12.6G swap 1.4G majflt 40426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 9 descendant rss 1.0G pss 0.9G | host avail 22.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.08 cpu 21.98 | cgroup 14.9G/max oom_kill 0 | free scratch 308.7G/45051976i tmp 29.4G/1010795i workspace 308.7G/45051976i | repeat-01 collected 26/26 workers (60617 items) tests 46745 done 1 failed | 22 in flight, oldest 380s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......................... [2161%]
........................................................................ [2164%]
........................................................................ [2168%]
........................................................................ [2171%]
........................................................................ [2174%]
..................................................................[contention-diag] +4211s soak 37p/201t rss 14.1G pss 12.5G swap 1.4G majflt 40575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 9 descendant rss 0.9G pss 0.8G | host avail 22.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.44 cpu 24.26 | cgroup 14.7G/max oom_kill 0 | free scratch 308.8G/45052233i tmp 29.4G/1010795i workspace 308.8G/45052233i | repeat-01 collected 26/26 workers (60617 items) tests 47148 done 1 failed | 21 in flight, oldest 395s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...... [2178%]
........................................................................ [2181%]
........................................................................ [2184%]
........................................................................ [2188%]
....[contention-diag] +4226s soak 38p/184t rss 14.1G pss 12.5G swap 1.4G majflt 40605 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 10 descendant rss 0.9G pss 0.8G | host avail 22.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.45 cpu 26.06 | cgroup 14.8G/max oom_kill 0 | free scratch 308.7G/45043828i tmp 29.4G/1010795i workspace 308.7G/45043828i | repeat-01 collected 26/26 workers (60617 items) tests 47371 done 1 failed | 21 in flight, oldest 411s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................................................... [2191%]
........................................................................ [2194%]
........................................................................ [2198%]
........................................................................ [2201%]
........................................................................ [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
.............[contention-diag] +4242s soak 40p/180t rss 14.0G pss 12.5G swap 1.3G majflt 40664 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 12 descendant rss 0.8G pss 0.8G | host avail 20.7G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.29 cpu 20.34 | cgroup 14.8G/max oom_kill 0 | free scratch 308.7G/45049682i tmp 29.4G/1010795i workspace 308.7G/45049682i | scratch used 0.8G in 163432 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 47789 done 1 failed | 21 in flight, oldest 356s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................... [2214%]
........................................................................ [2218%]
........................................................................ [2221%]
........................................................................ [2224%]
........................................................................ [2228%]
........................................................................ [2231%]
........................................................................ [2234%]
..........................[contention-diag] +4259s soak 36p/173t rss 14.2G pss 12.7G swap 1.3G majflt 40731 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 8 descendant rss 1.0G pss 0.9G | host avail 18.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 2.01 cpu 16.45 | cgroup 15.0G/max oom_kill 0 | free scratch 308.7G/45048588i tmp 29.4G/1010794i workspace 308.7G/45048588i | repeat-01 collected 26/26 workers (60617 items) tests 48391 done 1 failed | 20 in flight, oldest 373s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................. [2238%]
........................................................................ [2241%]
........................................................................ [2244%]
........................................................................ [2248%]
........................................................................ [2251%]
.......................................................................[contention-diag] +4275s soak 35p/175t rss 14.3G pss 12.8G swap 1.4G majflt 40828 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 7 descendant rss 1.0G pss 1.0G | host avail 17.6G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 16.29 | cgroup 15.1G/max oom_kill 0 | free scratch 308.7G/45047532i tmp 29.4G/1010794i workspace 308.7G/45047532i | repeat-01 collected 26/26 workers (60617 items) tests 48788 done 1 failed | 20 in flight, oldest 389s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
. [2254%]
........................................................................ [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
........................................................................ [2274%]
........................................................................ [2278%]
.......................[contention-diag] +4290s soak 39p/191t rss 14.4G pss 12.8G swap 1.4G majflt 40949 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.5G, 11 descendant rss 1.2G pss 1.1G | host avail 16.3G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.18/0.0 io 0.11 cpu 16.79 | cgroup 15.2G/max oom_kill 0 | free scratch 308.7G/45045645i tmp 29.4G/1010794i workspace 308.7G/45045645i | repeat-01 collected 26/26 workers (60617 items) tests 49323 done 1 failed | 20 in flight, oldest 404s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................. [2281%]
........................................................................ [2284%]
........................................................................ [2288%]
........................................................................ [2291%]
..............................................................[contention-diag] +4305s soak 56p/203t rss 14.6G pss 13.0G swap 1.4G majflt 41090 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 28 descendant rss 1.4G pss 1.2G | host avail 15.3G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 0.02 cpu 14.5 | cgroup 15.3G/max oom_kill 0 | free scratch 308.5G/45045397i tmp 29.4G/1010794i workspace 308.5G/45045397i | repeat-01 collected 26/26 workers (60617 items) tests 49669 done 1 failed | 19 in flight, oldest 419s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......... [2294%]
........................................................................ [2298%]
........................................................................ [2301%]
........................................................................ [2304%]
........................................................................ [2307%]
........................................................................ [2311%]
.............................[contention-diag] +4321s soak 44p/195t rss 14.5G pss 12.9G swap 1.4G majflt 41134 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 16 descendant rss 1.2G pss 1.1G | host avail 20.6G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.47 cpu 12.08 | cgroup 15.2G/max oom_kill 0 | free scratch 308.7G/45044432i tmp 29.4G/1010794i workspace 308.7G/45044432i | repeat-01 collected 26/26 workers (60617 items) tests 50066 done 1 failed | 19 in flight, oldest 435s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................... [2314%]
........................................................................ [2317%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2331%]
............[contention-diag] +4336s soak 40p/174t rss 14.4G pss 12.9G swap 1.4G majflt 41168 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 12 descendant rss 1.2G pss 1.1G | host avail 20.2G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.31 cpu 14.03 | cgroup 15.2G/max oom_kill 0 | free scratch 308.5G/45042303i tmp 29.4G/1010794i workspace 308.5G/45042303i | repeat-01 collected 26/26 workers (60617 items) tests 50483 done 1 failed | 18 in flight, oldest 450s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2341%]
........................................................................ [2344%]
........................................................................ [2347%]
........................................................................ [2351%]
........................................................................ [2354%]
.......................[contention-diag] +4352s soak 35p/173t rss 14.3G pss 12.7G swap 1.4G majflt 41423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 7 descendant rss 1.0G pss 1.0G | host avail 20.5G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 11.84 | cgroup 15.1G/max oom_kill 0 | free scratch 308.3G/45040943i tmp 29.4G/1010794i workspace 308.3G/45040943i | repeat-01 collected 26/26 workers (60617 items) tests 50997 done 1 failed | 18 in flight, oldest 466s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................. [2357%]
........................................................................ [2361%]
........................................................................ [2364%]
........................................................................ [2367%]
........................................................................ [2371%]
.................s...................................................... [2374%]
.............................................[contention-diag] +4367s soak 37p/173t rss 14.3G pss 12.7G swap 1.4G majflt 41461 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.8G pss 11.4G, 9 descendant rss 1.1G pss 1.0G | host avail 19.1G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 13.22 | cgroup 15.1G/max oom_kill 0 | free scratch 308.2G/45039125i tmp 29.4G/1010794i workspace 308.2G/45039125i | scratch used 0.9G in 169273 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 51383 done 1 failed | 18 in flight, oldest 481s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................... [2377%]
........................................................................ [2381%]
........................................................................ [2384%]
..........................................[contention-diag] +4385s soak 37p/184t rss 14.4G pss 12.8G swap 1.4G majflt 41564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 9 descendant rss 1.1G pss 1.1G | host avail 19.2G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 12.03 | cgroup 15.4G/max oom_kill 0 | free scratch 308.1G/45038178i tmp 29.4G/1010789i workspace 308.1G/45038178i | repeat-01 collected 26/26 workers (60617 items) tests 51662 done 1 failed | 18 in flight, oldest 499s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................. [2387%]
........................................................................ [2391%]
........................................................................ [2394%]
........................................................................ [2397%]
...........................................[contention-diag] +4400s soak 38p/174t rss 14.4G pss 12.9G swap 1.4G majflt 41586 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 10 descendant rss 1.2G pss 1.1G | host avail 17.2G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.21 cpu 12.55 | cgroup 15.4G/max oom_kill 0 | free scratch 308.1G/45036976i tmp 29.4G/1010794i workspace 308.1G/45036976i | repeat-01 collected 26/26 workers (60617 items) tests 51947 done 1 failed | 18 in flight, oldest 514s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................. [2401%]
........................................................................ [2404%]
........................................................................ [2407%]
........................................................................ [2411%]
..................................[contention-diag] +4416s soak 37p/170t rss 14.5G pss 12.7G swap 1.4G majflt 41695 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 9 descendant rss 1.2G pss 1.0G | host avail 20.0G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.05 cpu 12.4 | cgroup 15.3G/max oom_kill 0 | free scratch 307.9G/45036217i tmp 29.4G/1010794i workspace 307.9G/45036217i | repeat-01 collected 26/26 workers (60617 items) tests 52220 done 1 failed | 17 in flight, oldest 530s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................... [2414%]
........................................................................ [2417%]
........................................................................ [2421%]
........................................................................ [2424%]
........................................................................ [2427%]
........................................................................ [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
[contention-diag] +4431s soak 35p/176t rss 14.3G pss 12.7G swap 1.4G majflt 41752 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 7 descendant rss 1.0G pss 1.0G | host avail 19.5G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.24 cpu 13.89 | cgroup 15.4G/max oom_kill 0 | free scratch 307.9G/45034496i tmp 29.4G/1010794i workspace 307.9G/45034495i | repeat-01 collected 26/26 workers (60617 items) tests 52753 done 1 failed | 18 in flight, oldest 545s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................................ [2441%]
........................................................................ [2444%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2454%]
........................................................................ [2457%]
........................................................................ [2460%]
.................................[contention-diag] +4447s soak 37p/173t rss 14.3G pss 12.7G swap 1.4G majflt 41810 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 9 descendant rss 1.0G pss 1.0G | host avail 17.8G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.31 cpu 12.6 | cgroup 15.3G/max oom_kill 0 | free scratch 307.9G/45033265i tmp 29.4G/1010794i workspace 307.9G/45033265i | repeat-01 collected 26/26 workers (60617 items) tests 53298 done 1 failed | 16 in flight, oldest 561s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
....................................... [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
........................................................................ [2474%]
........................................................................ [2477%]
.............................................................[contention-diag] +4462s soak 37p/193t rss 14.4G pss 12.8G swap 1.4G majflt 41854 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.9G pss 11.4G, 9 descendant rss 1.1G pss 1.0G | host avail 17.3G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.67 cpu 12.28 | cgroup 15.4G/max oom_kill 0 | free scratch 307.9G/45033048i tmp 29.4G/1010794i workspace 307.9G/45033048i | repeat-01 collected 26/26 workers (60617 items) tests 53684 done 1 failed | 15 in flight, oldest 576s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........... [2480%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
........................................................................ [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
........................................................................ [2507%]
....................................................................[contention-diag] +4478s soak 42p/179t rss 14.4G pss 12.8G swap 1.4G majflt 41899 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.5G, 14 descendant rss 1.1G pss 1.0G | host avail 18.9G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.11 cpu 13.22 | cgroup 15.4G/max oom_kill 0 | free scratch 307.9G/45032158i tmp 29.4G/1010794i workspace 307.9G/45032158i | repeat-01 collected 26/26 workers (60617 items) tests 54324 done 1 failed | 15 in flight, oldest 592s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.... [2510%]
........................................................................ [2514%]
........................s............................................... [2517%]
........................................................................ [2520%]
........................................................................ [2524%]
........................................................................ [2527%]
........................................................................ [2530%]
........................................................................ [2534%]
........................................................................ [2537%]
........................................................................ [2540%]
.....................................................[contention-diag] +4493s soak 35p/166t rss 14.3G pss 12.8G swap 1.4G majflt 41960 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.5G, 7 descendant rss 1.0G pss 1.0G | host avail 15.7G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 12.47 | cgroup 15.5G/max oom_kill 0 | free scratch 307.7G/45030540i tmp 29.4G/1010794i workspace 307.7G/45030540i | scratch used 0.9G in 165178 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 54928 done 1 failed | 15 in flight, oldest 607s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................... [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
........................................................................ [2554%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2564%]
........................................................................ [2567%]
........................................................................ [2570%]
....................[contention-diag] +4510s soak 35p/171t rss 13.5G pss 12.0G swap 1.4G majflt 42021 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 7 descendant rss 0.2G pss 0.2G | host avail 20.8G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 13.66 | cgroup 14.7G/max oom_kill 0 | free scratch 307.9G/45029581i tmp 29.4G/1010794i workspace 307.9G/45029581i | repeat-01 collected 26/26 workers (60617 items) tests 55674 done 1 failed | 15 in flight, oldest 93s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.................................................... [2574%]
........................................................................ [2577%]
........................................................................ [2580%]
.....................................................[contention-diag] +4526s soak 41p/171t rss 13.8G pss 12.2G swap 1.5G majflt 42057 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 13 descendant rss 0.5G pss 0.4G | host avail 23.5G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 15.25 | cgroup 14.9G/max oom_kill 0 | free scratch 307.9G/45028577i tmp 29.4G/1010794i workspace 307.9G/45028577i | repeat-01 collected 26/26 workers (60617 items) tests 55923 done 1 failed | 15 in flight, oldest 108s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
................... [2584%]
........................................................................ [2587%]
........................................................................ [2590%]
........................................................................ [2593%]
........................................................................ [2597%]
.[contention-diag] +4541s soak 41p/182t rss 13.9G pss 12.3G swap 1.5G majflt 42086 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 13 descendant rss 0.6G pss 0.5G | host avail 23.2G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.63 cpu 16.48 | cgroup 15.0G/max oom_kill 0 | free scratch 307.9G/45027768i tmp 29.4G/1010794i workspace 307.9G/45027768i | repeat-01 collected 26/26 workers (60617 items) tests 56220 done 1 failed | 15 in flight, oldest 124s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
....................................................................... [2600%]
........................................................................ [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
.........s............[contention-diag] +4556s soak 44p/179t rss 14.2G pss 12.5G swap 1.5G majflt 42216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 16 descendant rss 0.9G pss 0.7G | host avail 21.8G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.36 cpu 16.63 | cgroup 15.2G/max oom_kill 0 | free scratch 307.9G/45026348i tmp 29.4G/1010794i workspace 307.9G/45026348i | repeat-01 collected 26/26 workers (60617 items) tests 56612 done 1 failed | 15 in flight, oldest 139s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.................................................. [2617%]
........................................................................ [2620%]
........................................................................ [2623%]
........................................................................ [2627%]
........................................................................ [2630%]
....................[contention-diag] +4572s soak 34p/160t rss 13.5G pss 12.0G swap 1.4G majflt 42412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 6 descendant rss 0.3G pss 0.2G | host avail 21.5G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 0.56 cpu 15.73 | cgroup 14.5G/max oom_kill 0 | free scratch 307.9G/45026338i tmp 29.4G/1010794i workspace 307.9G/45026338i | repeat-01 collected 26/26 workers (60617 items) tests 56959 done 1 failed | 14 in flight, oldest 75s gw9 tests/test_visual_capture_e2e.py::test_pytester_xdist_project_merges_worker_local_records | 10 hazardous kill call(s)
.................................................... [2633%]
........................................................................ [2637%]
........................................................................ [2640%]
........................................................................ [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
........................................................................ [2657%]
........................................................................ [2660%]
........................................................................ [2663%]
......[contention-diag] +4587s soak 36p/164t rss 13.6G pss 12.0G swap 1.4G majflt 42476 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 8 descendant rss 0.3G pss 0.2G | host avail 21.0G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.16 cpu 15.82 | cgroup 14.5G/max oom_kill 0 | free scratch 307.9G/45031535i tmp 29.4G/1010794i workspace 307.9G/45031535i | repeat-01 collected 26/26 workers (60617 items) tests 57663 done 1 failed | 13 in flight, oldest 75s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.................................................................. [2667%]
........................................................................ [2670%]
........................................................................ [2673%]
............................................................s........... [2677%]
........................................................................ [2680%]
........................................................................ [2683%]
........................................................................ [2687%]
..[contention-diag] +4603s soak 34p/165t rss 13.6G pss 12.1G swap 1.4G majflt 42560 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 6 descendant rss 0.3G pss 0.3G | host avail 20.2G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.51/0.01 io 0.81 cpu 15.18 | cgroup 14.7G/max oom_kill 0 | free scratch 308.0G/45053172i tmp 29.4G/1010794i workspace 308.0G/45053172i | repeat-01 collected 26/26 workers (60617 items) tests 58177 done 1 failed | 14 in flight, oldest 91s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
...................................................................... [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
........................................................................ [2700%]
........................................................................ [2703%]
........................................................................ [2707%]
........................................................................ [2710%]
...........................[contention-diag] +4618s soak 37p/164t rss 13.5G pss 11.9G swap 1.4G majflt 42819 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 9 descendant rss 0.2G pss 0.1G | host avail 18.7G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 1.42 cpu 13.79 | cgroup 14.5G/max oom_kill 0 | free scratch 308.2G/45088528i tmp 29.4G/1010794i workspace 308.2G/45088528i | scratch used 0.1G in 20178 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 58655 done 1 failed | 11 in flight, oldest 106s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................................. [2713%]
........................................................................ [2717%]
........................................................................ [2720%]
........................................................................ [2723%]
........................................................................ [2727%]
.......................................[contention-diag] +4636s soak 38p/162t rss 13.6G pss 12.0G swap 1.4G majflt 42981 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 10 descendant rss 0.3G pss 0.2G | host avail 17.7G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 2.47 cpu 13.55 | cgroup 14.7G/max oom_kill 0 | free scratch 308.4G/45120660i tmp 29.4G/1010794i workspace 308.4G/45120660i | repeat-01 collected 26/26 workers (60617 items) tests 59078 done 1 failed | 9 in flight, oldest 124s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................................. [2730%]
........................................................................ [2733%]
........................................................................ [2736%]
........................................................................ [2740%]
........................................................................ [2743%]
.........................................[contention-diag] +4651s soak 34p/160t rss 13.5G pss 11.8G swap 1.4G majflt 43098 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.2G, 6 descendant rss 0.2G pss 0.2G | host avail 18.3G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.93 cpu 16.47 | cgroup 14.8G/max oom_kill 0 | free scratch 308.5G/45154073i tmp 29.4G/1010792i workspace 308.5G/45154073i | repeat-01 collected 26/26 workers (60617 items) tests 59433 done 1 failed | 6 in flight, oldest 95s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
............................... [2746%]
........................................................................ [2750%]
........................................................................ [2753%]
..................................................[contention-diag] +4666s soak 35p/161t rss 13.5G pss 12.0G swap 1.4G majflt 43290 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.5G, 7 descendant rss 0.2G pss 0.1G | host avail 17.5G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 16.28 | cgroup 14.9G/max oom_kill 0 | free scratch 308.7G/45189912i tmp 29.4G/1010790i workspace 308.7G/45189912i | repeat-01 collected 26/26 workers (60617 items) tests 59653 done 1 failed | 7 in flight, oldest 110s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
...................... [2756%]
........................................................................ [2760%]
........................................................................ [2763%]
................[contention-diag] +4682s soak 34p/157t rss 13.5G pss 12.0G swap 1.4G majflt 43315 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 6 descendant rss 0.2G pss 0.1G | host avail 16.6G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.93 cpu 15.28 | cgroup 14.5G/max oom_kill 0 | free scratch 308.5G/45189264i tmp 29.4G/1010788i workspace 308.5G/45189264i | repeat-01 collected 26/26 workers (60617 items) tests 59845 done 1 failed | 7 in flight, oldest 51s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
........................................................ [2766%]
........................................................................ [2770%]
....................................................................ssss [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
........................................................................ [2786%]
.....................[contention-diag] +4697s soak 32p/150t rss 13.3G pss 11.8G swap 1.4G majflt 43405 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 18.7G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 13.74 | cgroup 14.6G/max oom_kill 0 | free scratch 308.2G/45189910i tmp 29.4G/1010789i workspace 308.2G/45189910i | repeat-01 collected 26/26 workers (60617 items) tests 60345 done 1 failed | 4 in flight, oldest 5s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
................................................... [2790%]
........................................................................ [2793%]
........................................................................ [2796%]
.................................................................        [100%][contention-diag] +4712s soak 32p/142t rss 13.3G pss 11.8G swap 1.4G majflt 43659 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.9G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 22.6G/62.7G swapfree 52.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 11.16 | cgroup 14.5G/max oom_kill 0 | free scratch 308.7G/45192506i tmp 29.4G/1010789i workspace 308.7G/45192506i | repeat-01 collected 26/26 workers (60617 items) tests 60595 done 1 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______ test_post_update_toast_appears_once_and_suppresses_available_toast ______
[gw3] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc41d6be000>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw3/test_post_update_toast_appears0')

    async def test_post_update_toast_appears_once_and_suppresses_available_toast(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        # This test's own subject is toast suppression between the post-update and
        # update-available toasts; pre-seed the unrelated one-shot keymap-unification,
        # agent-decks, and agent-pane-retirement notices as already shown so they
        # don't ride along on this receipt and add unrelated notifications.
        mark_keymap_unification_notice_shown()
        mark_agent_decks_notice_shown()
        mark_artifacts_agent_pane_notice_shown()
        receipt_file = tmp_path / "pending_update_toast.json"
        monkeypatch.setattr(update_receipt, "_PENDING_UPDATE_TOAST_FILE", receipt_file)
        assert write_pending_update_toast(_receipt()) is True
        monkeypatch.setattr(
            update_toast,
            "_load_update_toast_config",
            lambda: update_toast._UpdateToastConfig(
                startup_toast=True,
                post_update_toast=True,
            ),
        )
        monkeypatch.setattr(
            update_toast,
            "get_cached_update_status",
            lambda **_kwargs: _status(),
        )
    
        async with AcePage(query='"toast"') as page:
>           await page.wait_for(lambda _s: bool(list(page.app._notifications)))

tests/ace/tui/test_post_update_toast.py:525: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fc405d99f80>

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
E               AssertionError: wait_for() timed out after 60.0s — predicate never returned True

src/sase/ace/testing/wait.py:64: AssertionError
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

tests/ace/tui/test_artifacts_beads_navigation.py::test_selection_marks_jumps_and_reload_preserve_stable_target
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/strip.py:111: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    self._offsets_cache: FIFOCache[tuple[int, int], Strip] = FIFOCache(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_pane_review.py::test_memory_badge_label_prefixes_count
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:472: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    __dict__['method_calls'] = _CallList()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_submit_happy_path_settles_on_exit_completion
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_project_management_modal_edit.py::test_project_management_modal_alias_editor_updates_selected_project
  <string>:4: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object CommandLineScreen._load_tail_worker at 0x7fa8410b2880>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/test_agent_collapsed_panel_selection.py::test_collapsed_nonfocused_panel_does_not_hide_expanded_selection
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_restore_proof.py::test_proof_pulse_bumps_as_soon_as_revive_lands
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    path = os.fspath(arg)
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=521343) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=523250) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=520051) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

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

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=520385) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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
  <frozen os>:888: DeprecationWarning: This process (pid=520051) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=523551) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
618.49s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
467.66s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
462.52s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
460.46s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
416.09s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
412.30s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
342.00s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
341.08s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
337.69s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
332.02s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
320.93s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
274.59s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
256.94s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
209.20s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
195.19s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
192.36s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
179.58s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
174.82s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
162.52s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
154.21s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
=========================== short test summary info ============================
FAILED tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast
==== 1 failed, 60596 passed, 21 skipped, 111 warnings in 4721.92s (1:18:41) ====
[contention-diag] +4728s soak 2p/2t rss 0.4G pss 0.4G swap 0.1G majflt 1969 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 35.5G/62.7G swapfree 52.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 9.71 | cgroup 3.1G/max oom_kill 0 | free scratch 308.7G/45192529i tmp 29.4G/1010789i workspace 308.7G/45192529i | repeat-01 collected 26/26 workers (60617 items) tests 60617 done 1 failed | 10 hazardous kill call(s)
[contention-diag] +4730s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 469 | 1 parent rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 52.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 7.95 | cgroup 2.7G/max oom_kill 0 | free scratch 308.7G/45192527i tmp 29.4G/1010789i workspace 308.7G/45192527i | scratch used 0.3G in 63472 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 60617 done 1 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4732s, 305 samples, 0 signal(s); peaks: cgroup_current 15.5G, min_free_scratch 300.8G, min_free_tmp 29.3G, min_free_workspace 300.8G, min_inodes_scratch 44949041, min_inodes_tmp 1010207, min_inodes_workspace 44949041, min_mem_available 14.1G, min_swap_free 50.3G, oom_kill_delta 0, pressure_memory_full 3.36, pswpin_delta 714961, pswpout_delta 1210572, scratch_bytes 1.1G, soak_procs 56, soak_pss 13.0G, soak_rss 14.6G, soak_swap 1.6G, soak_threads 295

contention tally: 1 node(s) failed across 1 repeat(s) in 4731.6s; red repeats: 1
  1/1  tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

