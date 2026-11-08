# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-5)

- **TIMESTAMP:** 2026-11-08 15:39:52 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-5

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after post-update toast hang-guard repair for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 2818977, sampler pid 2819359 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-2406802-1794165735301864055.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 82 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.28 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 320.2G/45213145i tmp 29.4G/1010764i workspace 320.2G/45213145i | scratch used 0.1G in 9398 entries (truncated) | progress none yet
[contention-diag] +17s soak 28p/80t rss 2.2G pss 1.9G swap 0.0G majflt 98 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.1G pss 1.8G | host avail 28.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.03 cpu 11.51 | cgroup 2.0G/max oom_kill 0 | free scratch 320.2G/45211238i tmp 29.4G/1010764i workspace 320.2G/45211238i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 3.5G pss 3.1G swap 0.7G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.4G pss 3.0G | host avail 27.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.78 cpu 12.73 | cgroup 3.1G/max oom_kill 0 | free scratch 320.2G/45209733i tmp 29.4G/1010764i workspace 320.2G/45209733i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +48s soak 28p/80t rss 4.6G pss 4.2G swap 0.9G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.5G pss 4.1G | host avail 29.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.6 cpu 15.5 | cgroup 4.2G/max oom_kill 0 | free scratch 320.2G/45208089i tmp 29.4G/1010763i workspace 320.2G/45208089i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +63s soak 28p/86t rss 5.4G pss 4.9G swap 0.9G majflt 368 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.3G pss 4.8G | host avail 28.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.35 cpu 19.3 | cgroup 5.1G/max oom_kill 0 | free scratch 320.2G/45206534i tmp 29.4G/1010764i workspace 320.2G/45206534i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/89t rss 6.1G pss 5.7G swap 0.9G majflt 437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.0G pss 5.6G | host avail 26.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.81 cpu 17.87 | cgroup 5.9G/max oom_kill 0 | free scratch 320.2G/45206986i tmp 29.4G/1010764i workspace 320.2G/45206986i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
contention shards: 26 workers collected 60617 items in total (2020-2558 per worker)
26 workers [2465 items]

.................................................[contention-diag] +93s soak 28p/81t rss 6.6G pss 6.1G swap 0.9G majflt 450 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.5G pss 6.0G | host avail 25.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.28 cpu 14.48 | cgroup 6.4G/max oom_kill 0 | free scratch 320.2G/45206304i tmp 29.4G/1010764i workspace 320.2G/45206304i | repeat-01 collected 26/26 workers (60617 items) tests 0 done 0 failed | 24 in flight, oldest 0s gw15 tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
....................... [  3%]
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
..............[contention-diag] +108s soak 29p/127t rss 7.2G pss 6.6G swap 0.9G majflt 848 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.0G pss 6.4G, 1 descendant rss 0.0G pss 0.0G | host avail 24.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.5 cpu 14.73 | cgroup 6.9G/max oom_kill 0 | free scratch 320.2G/45211207i tmp 29.4G/1010764i workspace 320.2G/45211206i | repeat-01 collected 26/26 workers (60617 items) tests 866 done 0 failed | 26 in flight, oldest 15s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.......................................................... [ 43%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
........................................................................ [ 56%]
.................[contention-diag] +124s soak 29p/144t rss 7.5G pss 6.9G swap 0.9G majflt 868 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.3G pss 6.7G, 1 descendant rss 0.0G pss 0.0G | host avail 25.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.3 cpu 14.84 | cgroup 7.2G/max oom_kill 0 | free scratch 320.7G/45315304i tmp 29.4G/1010764i workspace 320.7G/45315306i | scratch used 0.2G in 33759 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 1216 done 0 failed | 26 in flight, oldest 30s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
....................................................... [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 69%]
.............[contention-diag] +141s soak 30p/165t rss 7.7G pss 7.1G swap 0.9G majflt 901 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.5G pss 6.9G, 2 descendant rss 0.1G pss 0.1G | host avail 26.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.21/0.14 io 2.33 cpu 17.03 | cgroup 7.5G/max oom_kill 0 | free scratch 321.0G/45364448i tmp 29.4G/1010764i workspace 321.0G/45364448i | repeat-01 collected 26/26 workers (60617 items) tests 1505 done 0 failed | 26 in flight, oldest 47s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
........................................................... [ 73%]
........................................................................ [ 76%]
........................................................................ [ 79%]
......................................................[contention-diag] +156s soak 31p/174t rss 8.0G pss 7.3G swap 0.9G majflt 982 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.7G pss 7.0G, 3 descendant rss 0.1G pss 0.1G | host avail 26.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.05/0.03 io 3.14 cpu 16.97 | cgroup 7.7G/max oom_kill 0 | free scratch 321.0G/45362938i tmp 29.4G/1010764i workspace 321.0G/45362936i | repeat-01 collected 26/26 workers (60617 items) tests 1760 done 0 failed | 26 in flight, oldest 60s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
.................. [ 83%]
........................................................................ [ 86%]
...................................................................[contention-diag] +171s soak 34p/196t rss 8.1G pss 7.4G swap 0.9G majflt 986 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.9G pss 7.2G, 6 descendant rss 0.1G pss 0.1G | host avail 25.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.71 cpu 18.16 | cgroup 7.8G/max oom_kill 0 | free scratch 321.0G/45360902i tmp 29.4G/1010764i workspace 321.0G/45360902i | repeat-01 collected 26/26 workers (60617 items) tests 1938 done 0 failed | 26 in flight, oldest 75s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
..... [ 89%]
........................................................................ [ 93%]
.....................................................[contention-diag] +187s soak 35p/209t rss 8.3G pss 7.5G swap 0.9G majflt 985 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.4G, 7 descendant rss 0.1G pss 0.1G | host avail 25.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.2/0.19 io 1.99 cpu 16.4 | cgroup 8.0G/max oom_kill 0 | free scratch 321.0G/45360081i tmp 29.4G/1010764i workspace 321.0G/45360081i | repeat-01 collected 26/26 workers (60617 items) tests 2065 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [ 96%]
........................................................................ [ 99%]
........................................................................ [103%]
........................................................................ [106%]
..............................................................[contention-diag] +202s soak 35p/240t rss 8.4G pss 7.7G swap 0.9G majflt 1000 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.4G, 7 descendant rss 0.1G pss 0.1G | host avail 25.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.49 cpu 17.48 | cgroup 8.1G/max oom_kill 0 | free scratch 321.0G/45357929i tmp 29.4G/1010764i workspace 321.0G/45357929i | repeat-01 collected 26/26 workers (60617 items) tests 2357 done 0 failed | 25 in flight, oldest 83s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......... [109%]
........................................................................ [113%]
...................................................[contention-diag] +217s soak 36p/215t rss 8.7G pss 8.0G swap 0.9G majflt 1004 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.6G, 8 descendant rss 0.3G pss 0.2G | host avail 23.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.07 io 1.61 cpu 14.18 | cgroup 8.4G/max oom_kill 0 | free scratch 321.0G/45356554i tmp 29.4G/1010764i workspace 321.0G/45356554i | repeat-01 collected 26/26 workers (60617 items) tests 2494 done 0 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................... [116%]
........................................................................ [119%]
......................................................................[contention-diag] +232s soak 38p/216t rss 8.9G pss 8.2G swap 0.9G majflt 1029 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.8G, 10 descendant rss 0.3G pss 0.2G | host avail 23.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 2.44 cpu 13.0 | cgroup 8.7G/max oom_kill 0 | free scratch 320.9G/45353117i tmp 29.4G/1010764i workspace 320.9G/45353117i | repeat-01 collected 26/26 workers (60617 items) tests 2660 done 0 failed | 26 in flight, oldest 114s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.. [123%]
........................................................................ [126%]
.............................................[contention-diag] +248s soak 35p/232t rss 8.8G pss 8.0G swap 0.8G majflt 1060 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.8G, 7 descendant rss 0.1G pss 0.1G | host avail 24.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.64 cpu 13.06 | cgroup 8.6G/max oom_kill 0 | free scratch 324.8G/45374967i tmp 29.4G/1010759i workspace 324.8G/45374967i | scratch used 0.3G in 55846 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 2770 done 0 failed | 26 in flight, oldest 129s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................... [129%]
........................................................................ [133%]
...................................[contention-diag] +265s soak 36p/222t rss 9.0G pss 8.2G swap 0.9G majflt 1073 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 7.9G, 8 descendant rss 0.3G pss 0.2G | host avail 21.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 9.78 | cgroup 8.8G/max oom_kill 0 | free scratch 324.6G/45368780i tmp 29.4G/1010764i workspace 324.6G/45368780i | repeat-01 collected 26/26 workers (60617 items) tests 2899 done 0 failed | 26 in flight, oldest 147s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................... [136%]
........................................................................ [139%]
.....................................[contention-diag] +280s soak 36p/220t rss 9.2G pss 8.4G swap 0.9G majflt 1106 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.0G, 8 descendant rss 0.3G pss 0.3G | host avail 21.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.1 cpu 9.59 | cgroup 9.0G/max oom_kill 0 | free scratch 324.4G/45365242i tmp 29.4G/1010764i workspace 324.4G/45365242i | repeat-01 collected 26/26 workers (60617 items) tests 3048 done 0 failed | 25 in flight, oldest 162s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [143%]
........................................................................ [146%]
...........................................[contention-diag] +296s soak 33p/237t rss 9.0G pss 8.2G swap 0.8G majflt 1118 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 20.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 11.15 | cgroup 8.8G/max oom_kill 0 | free scratch 324.1G/45362030i tmp 29.4G/1010764i workspace 324.1G/45362030i | repeat-01 collected 26/26 workers (60617 items) tests 3205 done 0 failed | 26 in flight, oldest 177s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................[contention-diag] +311s soak 33p/245t rss 9.0G pss 8.3G swap 0.8G majflt 1118 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 20.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.22/0.22 io 2.35 cpu 12.13 | cgroup 8.8G/max oom_kill 0 | free scratch 324.0G/45360588i tmp 29.4G/1010764i workspace 324.0G/45360588i | repeat-01 collected 26/26 workers (60617 items) tests 3237 done 0 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
. [149%]
............[contention-diag] +326s soak 35p/270t rss 9.2G pss 8.4G swap 0.8G majflt 1130 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.2G, 7 descendant rss 0.1G pss 0.0G | host avail 20.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.23/0.23 io 2.59 cpu 12.58 | cgroup 8.8G/max oom_kill 0 | free scratch 323.7G/45357087i tmp 29.4G/1010764i workspace 323.7G/45357087i | repeat-01 collected 26/26 workers (60617 items) tests 3252 done 0 failed | 26 in flight, oldest 208s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................ [152%]
...............[contention-diag] +342s soak 37p/244t rss 9.4G pss 8.6G swap 0.9G majflt 1172 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.3G, 9 descendant rss 0.3G pss 0.2G | host avail 19.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 2.75 cpu 11.96 | cgroup 9.0G/max oom_kill 0 | free scratch 323.6G/45354623i tmp 29.4G/1010764i workspace 323.6G/45354623i | repeat-01 collected 26/26 workers (60617 items) tests 3321 done 0 failed | 25 in flight, oldest 223s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................................................... [156%]
........................................................................ [159%]
.....................................[contention-diag] +357s soak 33p/232t rss 9.2G pss 8.5G swap 0.8G majflt 1122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.3G, 5 descendant rss 0.1G pss 0.0G | host avail 24.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.42 cpu 13.76 | cgroup 8.9G/max oom_kill 0 | free scratch 323.3G/45350858i tmp 29.4G/1010764i workspace 323.3G/45350858i | repeat-01 collected 26/26 workers (60617 items) tests 3480 done 0 failed | 25 in flight, oldest 239s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [162%]
........................................................................ [166%]
...........................[contention-diag] +372s soak 33p/251t rss 9.3G pss 8.5G swap 0.8G majflt 1128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 23.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.25 cpu 13.15 | cgroup 8.9G/max oom_kill 0 | free scratch 323.3G/45349375i tmp 29.4G/1010764i workspace 323.3G/45349375i | scratch used 0.4G in 63755 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 3583 done 0 failed | 26 in flight, oldest 254s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..........[contention-diag] +390s soak 35p/254t rss 9.5G pss 8.7G swap 0.8G majflt 1128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.5G, 7 descendant rss 0.1G pss 0.1G | host avail 22.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.2 cpu 13.17 | cgroup 9.1G/max oom_kill 0 | free scratch 323.3G/45346595i tmp 29.4G/1010764i workspace 323.3G/45346593i | repeat-01 collected 26/26 workers (60617 items) tests 3635 done 0 failed | 26 in flight, oldest 271s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [169%]
........................................................................ [172%]
..............[contention-diag] +405s soak 40p/268t rss 9.6G pss 8.8G swap 0.8G majflt 1128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.5G, 12 descendant rss 0.2G pss 0.1G | host avail 24.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.94 cpu 14.81 | cgroup 9.2G/max oom_kill 0 | free scratch 323.3G/45345402i tmp 29.4G/1010764i workspace 323.3G/45345402i | repeat-01 collected 26/26 workers (60617 items) tests 3757 done 0 failed | 26 in flight, oldest 286s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............[contention-diag] +420s soak 39p/267t rss 9.7G pss 8.8G swap 0.9G majflt 1128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.6G, 11 descendant rss 0.2G pss 0.1G | host avail 21.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.37 cpu 9.28 | cgroup 9.3G/max oom_kill 0 | free scratch 322.8G/45342674i tmp 29.4G/1010764i workspace 322.8G/45342674i | repeat-01 collected 26/26 workers (60617 items) tests 3770 done 0 failed | 26 in flight, oldest 302s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................. [176%]
........................................................................ [179%]
................[contention-diag] +435s soak 38p/261t rss 9.6G pss 8.8G swap 0.8G majflt 1128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.6G, 10 descendant rss 0.1G pss 0.0G | host avail 22.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.98 cpu 12.22 | cgroup 9.2G/max oom_kill 0 | free scratch 322.7G/45341135i tmp 29.4G/1010764i workspace 322.7G/45341135i | repeat-01 collected 26/26 workers (60617 items) tests 3900 done 0 failed | 26 in flight, oldest 317s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................[contention-diag] +451s soak 43p/296t rss 9.8G pss 8.9G swap 0.8G majflt 1128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.6G, 15 descendant rss 0.3G pss 0.1G | host avail 22.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.63 cpu 13.44 | cgroup 9.3G/max oom_kill 0 | free scratch 322.5G/45339700i tmp 29.4G/1010764i workspace 322.5G/45339700i | repeat-01 collected 26/26 workers (60617 items) tests 3952 done 0 failed | 26 in flight, oldest 332s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.... [182%]
........................................................................ [186%]
....................................[contention-diag] +466s soak 42p/259t rss 9.9G pss 9.0G swap 0.9G majflt 1129 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.7G, 14 descendant rss 0.3G pss 0.2G | host avail 21.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.53 cpu 13.0 | cgroup 9.5G/max oom_kill 0 | free scratch 322.7G/45337710i tmp 29.4G/1010764i workspace 322.7G/45337710i | repeat-01 collected 26/26 workers (60617 items) tests 4051 done 0 failed | 26 in flight, oldest 348s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................... [189%]
.............................................................[contention-diag] +481s soak 36p/248t rss 9.8G pss 9.0G swap 0.9G majflt 1204 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.7G, 8 descendant rss 0.2G pss 0.1G | host avail 20.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.2/0.2 io 0.36 cpu 12.78 | cgroup 9.5G/max oom_kill 0 | free scratch 322.7G/45336254i tmp 29.4G/1010764i workspace 322.7G/45336254i | repeat-01 collected 26/26 workers (60617 items) tests 4158 done 0 failed | 26 in flight, oldest 363s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [192%]
..................................................................[contention-diag] +497s soak 35p/279t rss 9.9G pss 9.1G swap 0.9G majflt 1182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 19.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.23/0.23 io 0.76 cpu 12.48 | cgroup 9.5G/max oom_kill 0 | free scratch 322.6G/45333933i tmp 29.4G/1010762i workspace 322.6G/45333933i | scratch used 0.4G in 79683 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 4238 done 0 failed | 26 in flight, oldest 378s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...... [196%]
.........................F[contention-failure] call tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap]: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8d7f5a8e30>
result = VcsLogResult(repos=(LogRepo(name='alpha-platform-repository', path='/tmp/alpha', kind='primary', aliases=(), plan_work...tched_at=1.0)), aggregate_truncated=False, provider_truncation_possible=False, resolved_filters=None, filter_spec=None)
expected_count = 41, capped = False

    @pytest.mark.parametrize(
        ("result", "expected_count", "capped"),
        (
            (_result_with_commit_count(2), 2, False),
            (
                _result_with_commit_count(2, provider_truncation_possible=True),
                2,
                True,
            ),
            (_result_with_commit_count(2, aggregate_truncated=True), 2, True),
            (_result_with_commit_count(41), 41, False),
        ),
        ids=("exact", "provider-cap", "aggregate-cap", "above-old-default-cap"),
    )
    async def test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap(
        monkeypatch: pytest.MonkeyPatch,
        result: VcsLogResult,
        expected_count: int,
        capped: bool,
    ) -> None:
        monkeypatch.setattr(
            "sase.config.load_merged_config",
            lambda: {
                "ace": {
                    "artifacts": {
                        "stitches": {"default_query": "sidecar:false since:24h limit:all"}
                    }
                }
            },
        )
        monkeypatch.setattr(commits_module, "run_vcs_log", lambda **_kwargs: result)
        monkeypatch.setattr(commits_module, "load_commit_diff_text", lambda _spec: "")
    
        async with AcePage(initial_tab="patches") as page:
            await page.press(page.artifacts_digit("stitches"))
            pane = page.query_one_widget("#artifacts-stitches-pane", CommitsPane)
            bar = pane.query_one(CommitFilterBar)
            status = bar.query_one("#commit-filter-status", Static)
            editor = bar.query_one("#commit-filter-input", SingleLineVimTextArea)
            await page.wait_for(
                lambda _state: (
                    pane.result is not None
                    and len(pane.result.commits) == expected_count
                    and ("capped" in status.content.plain) is capped
                )
            )
    
            coverage = "capped" if capped else "exact"
            marker = "+" if capped else ""
>           assert status.content.plain == coverage
E           AssertionError: assert 'preview' == 'exact'
E             
E             - exact
E             + preview

tests/ace/tui/test_commits_pane_collection.py:172: AssertionError
...............[contention-diag] +514s soak 36p/280t rss 9.8G pss 9.0G swap 0.8G majflt 1210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.8G, 8 descendant rss 0.1G pss 0.0G | host avail 20.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.78 cpu 11.79 | cgroup 9.5G/max oom_kill 0 | free scratch 322.2G/45332730i tmp 29.4G/1010764i workspace 322.2G/45332730i | repeat-01 collected 26/26 workers (60617 items) tests 4288 done 1 failed | 26 in flight, oldest 396s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................... [199%]
........................................................................ [202%]
......[contention-diag] +529s soak 30p/246t rss 9.8G pss 9.1G swap 0.8G majflt 1208 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.9G, 2 descendant rss 0.0G pss 0.0G | host avail 25.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.22 cpu 14.23 | cgroup 9.6G/max oom_kill 0 | free scratch 321.2G/45332095i tmp 29.4G/1010764i workspace 321.2G/45332095i | repeat-01 collected 26/26 workers (60617 items) tests 4390 done 1 failed | 26 in flight, oldest 411s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................[contention-diag] +545s soak 29p/249t rss 9.9G pss 9.1G swap 0.9G majflt 1211 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 8.9G, 1 descendant rss 0.1G pss 0.1G | host avail 25.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.62 cpu 16.87 | cgroup 9.7G/max oom_kill 0 | free scratch 321.2G/45331200i tmp 29.4G/1010764i workspace 321.2G/45331200i | repeat-01 collected 26/26 workers (60617 items) tests 4437 done 1 failed | 26 in flight, oldest 426s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................[contention-diag] +560s soak 28p/246t rss 9.9G pss 9.1G swap 0.8G majflt 1236 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G | host avail 24.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.08 cpu 15.58 | cgroup 9.7G/max oom_kill 0 | free scratch 321.2G/45330148i tmp 29.4G/1010764i workspace 321.2G/45330148i | repeat-01 collected 26/26 workers (60617 items) tests 4460 done 1 failed | 26 in flight, oldest 49s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
... [206%]
........................................[contention-diag] +575s soak 30p/246t rss 10.0G pss 9.2G swap 0.8G majflt 1236 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 23.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.99 cpu 15.17 | cgroup 9.8G/max oom_kill 0 | free scratch 321.2G/45329550i tmp 29.4G/1010764i workspace 321.2G/45329550i | repeat-01 collected 26/26 workers (60617 items) tests 4501 done 1 failed | 26 in flight, oldest 64s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
................................ [209%]
[contention-diag] +590s soak 30p/234t rss 10.0G pss 9.2G swap 0.8G majflt 1237 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 24.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.85 cpu 15.05 | cgroup 9.8G/max oom_kill 0 | free scratch 321.2G/45328863i tmp 29.4G/1010764i workspace 321.2G/45328863i | repeat-01 collected 26/26 workers (60617 items) tests 4526 done 1 failed | 26 in flight, oldest 79s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
........................................................................ [212%]
....[contention-diag] +606s soak 28p/229t rss 10.0G pss 9.2G swap 0.8G majflt 1237 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G | host avail 24.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.8 cpu 17.77 | cgroup 9.8G/max oom_kill 0 | free scratch 321.2G/45328169i tmp 29.4G/1010764i workspace 321.2G/45328169i | repeat-01 collected 26/26 workers (60617 items) tests 4610 done 1 failed | 26 in flight, oldest 95s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
.................................................................... [216%]
.................[contention-diag] +621s soak 28p/246t rss 10.0G pss 9.2G swap 0.8G majflt 1239 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G | host avail 23.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 18.64 | cgroup 9.8G/max oom_kill 0 | free scratch 321.2G/45327536i tmp 29.4G/1010764i workspace 321.2G/45327536i | scratch used 0.5G in 94745 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 4661 done 1 failed | 26 in flight, oldest 79s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_escape_restores_the_prior_committed_query
...............[contention-diag] +638s soak 30p/230t rss 10.1G pss 9.3G swap 0.8G majflt 1249 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.1G, 2 descendant rss 0.1G pss 0.1G | host avail 22.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.34 cpu 15.64 | cgroup 10.0G/max oom_kill 0 | free scratch 321.2G/45326814i tmp 29.4G/1010764i workspace 321.2G/45326814i | repeat-01 collected 26/26 workers (60617 items) tests 4711 done 1 failed | 26 in flight, oldest 52s gw18 tests/ace/tui/command_line/test_policy_io.py::test_poll_once_ticks_submitting_without_log_read
....................[contention-diag] +654s soak 29p/238t rss 10.1G pss 9.4G swap 0.8G majflt 1239 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G, 1 descendant rss 0.1G pss 0.0G | host avail 24.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 2.49 cpu 15.79 | cgroup 10.0G/max oom_kill 0 | free scratch 321.2G/45326331i tmp 29.4G/1010764i workspace 321.2G/45326331i | repeat-01 collected 26/26 workers (60617 items) tests 4731 done 1 failed | 26 in flight, oldest 53s gw19 tests/ace/tui/test_agent_grouping_picker.py::test_agents_default_oo_toggles_panel_layout_once_and_preserves_mode
.................... [219%]
.............................[contention-diag] +669s soak 28p/257t rss 10.1G pss 9.3G swap 0.8G majflt 1239 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G | host avail 26.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.13 cpu 15.21 | cgroup 10.0G/max oom_kill 0 | free scratch 321.2G/45325453i tmp 29.4G/1010764i workspace 321.2G/45325453i | repeat-01 collected 26/26 workers (60617 items) tests 4779 done 1 failed | 26 in flight, oldest 53s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_marks_render_and_footer_syncs
.............................[contention-diag] +684s soak 28p/262t rss 10.1G pss 9.4G swap 0.8G majflt 1239 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.2G | host avail 26.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.44 cpu 17.44 | cgroup 10.0G/max oom_kill 0 | free scratch 321.2G/45325090i tmp 29.4G/1010764i workspace 321.2G/45325090i | repeat-01 collected 26/26 workers (60617 items) tests 4807 done 1 failed | 26 in flight, oldest 62s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
.............. [222%]
...................................[contention-diag] +699s soak 29p/237t rss 10.2G pss 9.5G swap 0.8G majflt 1239 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 26.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.88 cpu 16.24 | cgroup 10.1G/max oom_kill 0 | free scratch 321.2G/45324267i tmp 29.4G/1010764i workspace 321.2G/45324267i | repeat-01 collected 26/26 workers (60617 items) tests 4857 done 1 failed | 26 in flight, oldest 62s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
........[contention-diag] +715s soak 29p/241t rss 10.2G pss 9.5G swap 0.8G majflt 1243 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 26.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.64 cpu 17.58 | cgroup 10.1G/max oom_kill 0 | free scratch 321.2G/45323377i tmp 29.4G/1010765i workspace 321.2G/45323375i | repeat-01 collected 26/26 workers (60617 items) tests 4866 done 1 failed | 26 in flight, oldest 77s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
............................. [226%]
.[contention-diag] +730s soak 28p/243t rss 10.2G pss 9.5G swap 0.8G majflt 1243 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G | host avail 25.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.15 cpu 17.98 | cgroup 10.2G/max oom_kill 0 | free scratch 321.2G/45322599i tmp 29.4G/1010765i workspace 321.2G/45322599i | repeat-01 collected 26/26 workers (60617 items) tests 4897 done 1 failed | 26 in flight, oldest 59s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
.........[contention-diag] +745s soak 28p/258t rss 10.3G pss 9.5G swap 0.8G majflt 1244 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G | host avail 26.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.39 cpu 17.42 | cgroup 10.3G/max oom_kill 0 | free scratch 321.2G/45321834i tmp 29.4G/1010765i workspace 321.2G/45321834i | scratch used 0.6G in 108005 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 4906 done 1 failed | 26 in flight, oldest 74s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
.............................................................. [229%]
..................[contention-diag] +763s soak 30p/238t rss 10.4G pss 9.6G swap 0.8G majflt 1246 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 2 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.4 cpu 17.05 | cgroup 10.3G/max oom_kill 0 | free scratch 321.2G/45320720i tmp 29.4G/1010765i workspace 321.2G/45320720i | repeat-01 collected 26/26 workers (60617 items) tests 4984 done 1 failed | 26 in flight, oldest 53s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
...................................................... [232%]
......[contention-diag] +778s soak 29p/250t rss 10.4G pss 9.6G swap 0.8G majflt 1247 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 17.32 | cgroup 10.4G/max oom_kill 0 | free scratch 321.1G/45319280i tmp 29.4G/1010765i workspace 321.1G/45319280i | repeat-01 collected 26/26 workers (60617 items) tests 5044 done 1 failed | 26 in flight, oldest 57s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
................................................[contention-diag] +793s soak 28p/225t rss 10.3G pss 9.6G swap 0.8G majflt 1247 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.4G | host avail 25.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.02 cpu 17.35 | cgroup 10.3G/max oom_kill 0 | free scratch 321.1G/45317185i tmp 29.4G/1010765i workspace 321.1G/45317185i | repeat-01 collected 26/26 workers (60617 items) tests 5089 done 1 failed | 25 in flight, oldest 49s gw22 tests/ace/tui/test_artifacts_beads_filtering.py::test_changing_project_scope_keeps_idle_bead_bar_in_sync
.................. [236%]
........................................................................ [239%]
........................................................................ [242%]
........................................................................ [246%]
........................................................................ [249%]
..................[contention-diag] +808s soak 29p/238t rss 10.4G pss 9.6G swap 0.8G majflt 1247 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.37 cpu 16.97 | cgroup 10.3G/max oom_kill 0 | free scratch 321.1G/45315254i tmp 29.4G/1010765i workspace 321.1G/45315254i | repeat-01 collected 26/26 workers (60617 items) tests 5407 done 1 failed | 26 in flight, oldest 54s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...............................[contention-diag] +824s soak 29p/248t rss 10.5G pss 9.7G swap 0.8G majflt 1253 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 3.08 cpu 17.11 | cgroup 10.4G/max oom_kill 0 | free scratch 321.1G/45313765i tmp 29.4G/1010765i workspace 321.1G/45313765i | repeat-01 collected 26/26 workers (60617 items) tests 5445 done 1 failed | 26 in flight, oldest 70s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....................... [252%]
........................................................................ [256%]
..[contention-diag] +839s soak 33p/264t rss 10.6G pss 9.8G swap 0.8G majflt 1257 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 5 descendant rss 0.2G pss 0.1G | host avail 25.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 3.67 cpu 18.2 | cgroup 10.6G/max oom_kill 0 | free scratch 321.1G/45312996i tmp 29.4G/1010765i workspace 321.1G/45312996i | repeat-01 collected 26/26 workers (60617 items) tests 5542 done 1 failed | 26 in flight, oldest 85s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...................................................................... [259%]
................[contention-diag] +854s soak 28p/234t rss 10.5G pss 9.7G swap 0.8G majflt 1268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G | host avail 24.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.69 cpu 16.8 | cgroup 10.5G/max oom_kill 0 | free scratch 321.1G/45311467i tmp 29.4G/1010765i workspace 321.1G/45311467i | repeat-01 collected 26/26 workers (60617 items) tests 5625 done 1 failed | 26 in flight, oldest 100s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..................[contention-diag] +870s soak 28p/258t rss 10.5G pss 9.7G swap 0.8G majflt 1268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G | host avail 24.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.6 cpu 16.11 | cgroup 10.5G/max oom_kill 0 | free scratch 321.1G/45310297i tmp 29.4G/1010763i workspace 321.1G/45310297i | scratch used 0.7G in 122689 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 5647 done 1 failed | 26 in flight, oldest 116s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..........................[contention-diag] +887s soak 29p/275t rss 10.6G pss 9.8G swap 0.8G majflt 1268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 2.7 cpu 14.59 | cgroup 10.7G/max oom_kill 0 | free scratch 321.1G/45309264i tmp 29.4G/1010765i workspace 321.1G/45309263i | repeat-01 collected 26/26 workers (60617 items) tests 5675 done 1 failed | 26 in flight, oldest 133s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............ [262%]
.......................................................................[contention-diag] +902s soak 30p/252t rss 10.6G pss 9.9G swap 0.8G majflt 1268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 2 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.88 cpu 14.55 | cgroup 10.7G/max oom_kill 0 | free scratch 321.1G/45308641i tmp 29.4G/1010765i workspace 321.1G/45308641i | repeat-01 collected 26/26 workers (60617 items) tests 5744 done 1 failed | 26 in flight, oldest 148s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
. [266%]
........................................[contention-diag] +918s soak 30p/240t rss 10.8G pss 9.9G swap 0.8G majflt 1268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.7G, 2 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.56 cpu 17.16 | cgroup 10.7G/max oom_kill 0 | free scratch 321.1G/45307758i tmp 29.4G/1010765i workspace 321.1G/45307758i | repeat-01 collected 26/26 workers (60617 items) tests 5796 done 1 failed | 26 in flight, oldest 65s gw9 tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
................................ [269%]
........................................................................ [272%]
.[contention-diag] +933s soak 30p/240t rss 10.8G pss 10.0G swap 0.8G majflt 1269 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.7G, 2 descendant rss 0.1G pss 0.1G | host avail 24.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.48 cpu 16.57 | cgroup 10.7G/max oom_kill 0 | free scratch 321.1G/45306996i tmp 29.4G/1010765i workspace 321.1G/45306996i | repeat-01 collected 26/26 workers (60617 items) tests 5900 done 1 failed | 26 in flight, oldest 80s gw9 tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
....................................................................... [276%]
........................................................................ [279%]
.......................................................................[contention-diag] +948s soak 30p/233t rss 10.8G pss 10.0G swap 0.8G majflt 1269 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 2 descendant rss 0.1G pss 0.1G | host avail 25.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 2.62 cpu 16.78 | cgroup 10.7G/max oom_kill 0 | free scratch 321.1G/45305982i tmp 29.4G/1010765i workspace 321.1G/45305982i | repeat-01 collected 26/26 workers (60617 items) tests 6111 done 1 failed | 26 in flight, oldest 70s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
. [282%]
........................................................................ [286%]
........................................................................ [289%]
.......[contention-diag] +964s soak 28p/216t rss 10.7G pss 9.9G swap 0.8G majflt 1284 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 24.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.22 cpu 16.62 | cgroup 10.7G/max oom_kill 0 | free scratch 321.1G/45305239i tmp 29.4G/1010765i workspace 321.1G/45305239i | repeat-01 collected 26/26 workers (60617 items) tests 6257 done 1 failed | 26 in flight, oldest 50s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................................................................. [292%]
..................................................................[contention-diag] +979s soak 28p/225t rss 10.8G pss 10.0G swap 0.8G majflt 1286 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G | host avail 24.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.28 cpu 15.88 | cgroup 10.8G/max oom_kill 0 | free scratch 321.1G/45304243i tmp 29.4G/1010765i workspace 321.1G/45304243i | repeat-01 collected 26/26 workers (60617 items) tests 6399 done 1 failed | 26 in flight, oldest 65s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
...... [295%]
..................................[contention-diag] +994s soak 28p/246t rss 10.8G pss 10.0G swap 0.8G majflt 1287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G | host avail 24.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.06 cpu 16.33 | cgroup 10.8G/max oom_kill 0 | free scratch 321.1G/45303717i tmp 29.4G/1010765i workspace 321.1G/45303717i | scratch used 0.7G in 131971 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 6428 done 1 failed | 26 in flight, oldest 81s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
...................................... [299%]
........................................................................ [302%]
................................[contention-diag] +1011s soak 28p/244t rss 10.8G pss 10.0G swap 0.8G majflt 1350 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G | host avail 24.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.59/0.44 io 2.18 cpu 16.05 | cgroup 10.8G/max oom_kill 0 | free scratch 321.1G/45302515i tmp 29.4G/1010765i workspace 321.1G/45302515i | repeat-01 collected 26/26 workers (60617 items) tests 6579 done 1 failed | 26 in flight, oldest 72s gw0 tests/ace/tui/test_plan_decision_ace_render_rail.py::test_compact_verdict_stays_inside_rail_with_stylesheet
........................................ [305%]
.......................[contention-diag] +1027s soak 29p/220t rss 10.9G pss 10.1G swap 0.8G majflt 1357 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 23.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.11/0.08 io 2.13 cpu 15.83 | cgroup 10.9G/max oom_kill 0 | free scratch 321.1G/45301791i tmp 29.4G/1010765i workspace 321.1G/45301791i | repeat-01 collected 26/26 workers (60617 items) tests 6646 done 1 failed | 26 in flight, oldest 50s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
................................................. [309%]
[contention-diag] +1042s soak 30p/237t rss 10.9G pss 10.1G swap 0.8G majflt 1357 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G, 2 descendant rss 0.1G pss 0.1G | host avail 23.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 2.15 cpu 16.58 | cgroup 10.9G/max oom_kill 0 | free scratch 321.1G/45301356i tmp 29.4G/1010765i workspace 321.1G/45301356i | repeat-01 collected 26/26 workers (60617 items) tests 6694 done 1 failed | 26 in flight, oldest 46s gw24 tests/ace/tui/test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest
........................................................................ [312%]
........[contention-diag] +1057s soak 30p/227t rss 11.0G pss 10.2G swap 0.9G majflt 1357 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 24.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.01 cpu 14.71 | cgroup 11.0G/max oom_kill 0 | free scratch 321.1G/45300615i tmp 29.4G/1010765i workspace 321.1G/45300615i | repeat-01 collected 26/26 workers (60617 items) tests 6773 done 1 failed | 26 in flight, oldest 57s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
................................................................ [315%]
.......................................................................[contention-diag] +1073s soak 31p/235t rss 11.0G pss 10.2G swap 0.9G majflt 1358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 3 descendant rss 0.1G pss 0.1G | host avail 24.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.78 cpu 16.21 | cgroup 11.0G/max oom_kill 0 | free scratch 321.1G/45299981i tmp 29.4G/1010765i workspace 321.1G/45299981i | repeat-01 collected 26/26 workers (60617 items) tests 6909 done 1 failed | 26 in flight, oldest 58s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_picked_all_projects_is_not_reseeded_after_inventory_reload
. [319%]
........................................................................ [322%]
........................................................................ [325%]
........................[contention-diag] +1088s soak 29p/225t rss 11.0G pss 10.2G swap 0.8G majflt 1358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.6 cpu 17.28 | cgroup 11.0G/max oom_kill 0 | free scratch 321.1G/45299068i tmp 29.4G/1010765i workspace 321.1G/45299068i | repeat-01 collected 26/26 workers (60617 items) tests 7080 done 1 failed | 26 in flight, oldest 49s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_clicking_idle_file_bar_opens_the_filter_session
................[contention-diag] +1103s soak 30p/225t rss 11.1G pss 10.2G swap 0.8G majflt 1359 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 2 descendant rss 0.1G pss 0.0G | host avail 23.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.72 cpu 17.1 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45298584i tmp 29.4G/1010765i workspace 321.1G/45298584i | repeat-01 collected 26/26 workers (60617 items) tests 7094 done 1 failed | 26 in flight, oldest 47s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................................ [329%]
.......................................[contention-diag] +1119s soak 29p/243t rss 11.0G pss 10.2G swap 0.8G majflt 1359 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 23.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.36 cpu 17.77 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45298134i tmp 29.4G/1010765i workspace 321.1G/45298134i | scratch used 0.8G in 138013 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 7139 done 1 failed | 25 in flight, oldest 63s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................................. [332%]
........................................................................ [335%]
....................................................[contention-diag] +1136s soak 29p/235t rss 11.1G pss 10.3G swap 0.9G majflt 1359 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 22.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.91 cpu 16.8 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45297201i tmp 29.4G/1010765i workspace 321.1G/45297201i | repeat-01 collected 26/26 workers (60617 items) tests 7322 done 1 failed | 26 in flight, oldest 63s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
.................... [339%]
..................................................................[contention-diag] +1151s soak 28p/212t rss 11.0G pss 10.2G swap 0.8G majflt 1359 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G | host avail 22.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.71 cpu 16.02 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45296617i tmp 29.4G/1010765i workspace 321.1G/45296617i | repeat-01 collected 26/26 workers (60617 items) tests 7409 done 1 failed | 26 in flight, oldest 49s gw5 tests/ace/tui/test_artifacts_plans_filtering.py::test_changing_project_scope_keeps_idle_plan_bar_in_sync
...... [342%]
........................................................................ [345%]
........................................................................ [349%]
.[contention-diag] +1167s soak 28p/234t rss 11.0G pss 10.2G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G | host avail 23.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.26 cpu 16.9 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45295841i tmp 29.4G/1010766i workspace 321.1G/45295841i | repeat-01 collected 26/26 workers (60617 items) tests 7553 done 1 failed | 26 in flight, oldest 42s gw21 tests/ace/tui/test_help_modal_filter.py::test_typing_live_filters_columns_and_status
....................................................................... [352%]
........................................................................ [355%]
.........[contention-diag] +1182s soak 29p/243t rss 11.1G pss 10.3G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 22.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 17.55 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45312165i tmp 29.4G/1010766i workspace 321.1G/45312165i | repeat-01 collected 26/26 workers (60617 items) tests 7712 done 1 failed | 26 in flight, oldest 57s gw12 tests/ace/tui/test_artifacts_plans_interactions.py::test_plans_pane_navigates_three_document_sections
.......[contention-diag] +1197s soak 38p/270t rss 11.2G pss 10.3G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 30.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.96 cpu 18.8 | cgroup 11.2G/max oom_kill 0 | free scratch 321.1G/45311995i tmp 29.4G/1010767i workspace 321.1G/45311995i | repeat-01 collected 26/26 workers (60617 items) tests 7720 done 1 failed | 26 in flight, oldest 55s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_for_other_panels_deck_changes_nothing
....................[contention-diag] +1212s soak 38p/275t rss 11.2G pss 10.3G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 29.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 23.95 | cgroup 11.2G/max oom_kill 0 | free scratch 321.1G/45311849i tmp 29.4G/1010767i workspace 321.1G/45311849i | repeat-01 collected 26/26 workers (60617 items) tests 7739 done 1 failed | 26 in flight, oldest 71s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_for_other_panels_deck_changes_nothing
......[contention-diag] +1228s soak 39p/288t rss 11.2G pss 10.3G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 11 descendant rss 0.1G pss 0.0G | host avail 29.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 24.7 | cgroup 11.2G/max oom_kill 0 | free scratch 321.1G/45311748i tmp 29.4G/1010767i workspace 321.1G/45311748i | repeat-01 collected 26/26 workers (60617 items) tests 7746 done 1 failed | 26 in flight, oldest 85s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.............................. [359%]
...........[contention-diag] +1243s soak 38p/261t rss 11.2G pss 10.3G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 29.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.36 | cgroup 11.2G/max oom_kill 0 | free scratch 321.1G/45311494i tmp 29.4G/1010767i workspace 321.1G/45311494i | scratch used 0.8G in 147532 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 7781 done 1 failed | 26 in flight, oldest 100s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
............................................................. [362%]
.[contention-diag] +1260s soak 38p/257t rss 11.2G pss 10.4G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 29.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 30.01 | cgroup 11.3G/max oom_kill 0 | free scratch 321.1G/45311247i tmp 29.4G/1010767i workspace 321.1G/45311247i | repeat-01 collected 26/26 workers (60617 items) tests 7848 done 1 failed | 26 in flight, oldest 118s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
....................................................................... [365%]
....[contention-diag] +1276s soak 38p/261t rss 11.3G pss 10.4G swap 0.8G majflt 1361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 27.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 24.11 | cgroup 11.3G/max oom_kill 0 | free scratch 321.1G/45310837i tmp 29.4G/1010767i workspace 321.1G/45310837i | repeat-01 collected 26/26 workers (60617 items) tests 7922 done 1 failed | 26 in flight, oldest 78s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
.................................................................... [369%]
...........................................................[contention-diag] +1291s soak 38p/250t rss 11.3G pss 10.4G swap 0.8G majflt 1372 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 26.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.82 | cgroup 11.3G/max oom_kill 0 | free scratch 321.1G/45310426i tmp 29.4G/1010767i workspace 321.1G/45310426i | repeat-01 collected 26/26 workers (60617 items) tests 8044 done 1 failed | 26 in flight, oldest 71s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
............. [372%]
..[contention-diag] +1306s soak 38p/250t rss 11.3G pss 10.4G swap 0.8G majflt 1372 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 30.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.79 | cgroup 11.3G/max oom_kill 0 | free scratch 320.9G/45310274i tmp 29.4G/1010767i workspace 320.9G/45310274i | repeat-01 collected 26/26 workers (60617 items) tests 8064 done 1 failed | 26 in flight, oldest 76s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
.........................................................[contention-diag] +1322s soak 28p/240t rss 11.2G pss 10.4G swap 0.8G majflt 1373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 29.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.99 | cgroup 11.3G/max oom_kill 0 | free scratch 321.1G/45310077i tmp 29.4G/1010767i workspace 321.1G/45310077i | repeat-01 collected 26/26 workers (60617 items) tests 8122 done 1 failed | 26 in flight, oldest 54s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_after_tools_returns_to_main_then_tools
............. [375%]
........................................................................ [379%]
........................................................[contention-diag] +1337s soak 29p/232t rss 11.3G pss 10.4G swap 0.8G majflt 1373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.3G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.38 | cgroup 11.3G/max oom_kill 0 | free scratch 321.1G/45309567i tmp 29.4G/1010767i workspace 321.1G/45309567i | repeat-01 collected 26/26 workers (60617 items) tests 8264 done 1 failed | 26 in flight, oldest 49s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_q_is_insert_text_then_closes_cell_from_normal_mode
................ [382%]
.....................................................................[contention-diag] +1352s soak 28p/241t rss 11.3G pss 10.4G swap 0.8G majflt 1373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G | host avail 29.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.22 | cgroup 11.3G/max oom_kill 0 | free scratch 321.1G/45309418i tmp 29.4G/1010767i workspace 321.1G/45309418i | repeat-01 collected 26/26 workers (60617 items) tests 8347 done 1 failed | 26 in flight, oldest 57s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
... [385%]
........................................................................ [389%]
........................................................................ [392%]
........................................................................ [395%]
.......................................................[contention-diag] +1368s soak 30p/260t rss 11.3G pss 10.5G swap 0.8G majflt 1378 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 2 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.98 | cgroup 11.4G/max oom_kill 0 | free scratch 321.1G/45308761i tmp 29.4G/1010767i workspace 321.1G/45308761i | scratch used 0.9G in 158966 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 8607 done 1 failed | 26 in flight, oldest 73s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
................. [399%]
........................................................................ [402%]
........................................................................ [405%]
.........[contention-diag] +1385s soak 28p/225t rss 11.3G pss 10.5G swap 0.8G majflt 1548 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G | host avail 29.7G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.24/0.24 io 0.22 cpu 27.22 | cgroup 11.4G/max oom_kill 0 | free scratch 321.1G/45308253i tmp 29.4G/1010767i workspace 321.1G/45308253i | repeat-01 collected 26/26 workers (60617 items) tests 8782 done 1 failed | 26 in flight, oldest 86s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................................... [409%]
......................................................[contention-diag] +1400s soak 29p/241t rss 11.4G pss 10.6G swap 0.8G majflt 1548 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 1 descendant rss 0.1G pss 0.1G | host avail 27.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 0.12 cpu 24.22 | cgroup 11.5G/max oom_kill 0 | free scratch 320.9G/45307657i tmp 29.4G/1010767i workspace 320.9G/45307657i | repeat-01 collected 26/26 workers (60617 items) tests 8906 done 1 failed | 26 in flight, oldest 101s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................. [412%]
...............................................[contention-diag] +1416s soak 28p/249t rss 11.3G pss 10.5G swap 0.8G majflt 1548 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G | host avail 26.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.25 cpu 22.05 | cgroup 11.5G/max oom_kill 0 | free scratch 320.8G/45307417i tmp 29.4G/1010767i workspace 320.8G/45307417i | repeat-01 collected 26/26 workers (60617 items) tests 8966 done 1 failed | 26 in flight, oldest 116s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
......................... [415%]
........................................................................ [419%]
...............[contention-diag] +1431s soak 29p/268t rss 11.4G pss 10.6G swap 0.8G majflt 1553 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 27.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 21.17 | cgroup 11.5G/max oom_kill 0 | free scratch 320.7G/45307087i tmp 29.4G/1010767i workspace 320.7G/45307087i | repeat-01 collected 26/26 workers (60617 items) tests 9086 done 1 failed | 26 in flight, oldest 131s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
......................................................... [422%]
............................................[contention-diag] +1446s soak 28p/261t rss 11.4G pss 10.6G swap 0.8G majflt 1554 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.4G | host avail 26.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.38/0.38 io 0.01 cpu 22.09 | cgroup 11.5G/max oom_kill 0 | free scratch 320.7G/45306760i tmp 29.4G/1010767i workspace 320.7G/45306760i | repeat-01 collected 26/26 workers (60617 items) tests 9187 done 1 failed | 26 in flight, oldest 147s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................[contention-diag] +1461s soak 28p/257t rss 11.4G pss 10.6G swap 0.8G majflt 1554 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.4G | host avail 26.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.0 cpu 27.92 | cgroup 11.6G/max oom_kill 0 | free scratch 320.7G/45306610i tmp 29.4G/1010767i workspace 320.7G/45306610i | repeat-01 collected 26/26 workers (60617 items) tests 9212 done 1 failed | 26 in flight, oldest 162s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.... [425%]
........................[contention-diag] +1477s soak 28p/265t rss 11.5G pss 10.6G swap 0.8G majflt 1565 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.4G | host avail 24.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 27.06 | cgroup 11.6G/max oom_kill 0 | free scratch 320.7G/45306441i tmp 29.4G/1010767i workspace 320.7G/45306441i | repeat-01 collected 26/26 workers (60617 items) tests 9240 done 1 failed | 26 in flight, oldest 177s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..............................[contention-diag] +1492s soak 28p/259t rss 11.5G pss 10.6G swap 0.8G majflt 1565 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 23.0G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.05 | cgroup 11.6G/max oom_kill 0 | free scratch 320.6G/45306286i tmp 29.4G/1010767i workspace 320.6G/45306286i | scratch used 0.9G in 167081 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 9266 done 1 failed | 26 in flight, oldest 112s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................. [429%]
................[contention-diag] +1509s soak 28p/258t rss 11.5G pss 10.7G swap 0.8G majflt 1565 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 23.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.44 | cgroup 11.7G/max oom_kill 0 | free scratch 320.3G/45306091i tmp 29.4G/1010767i workspace 320.3G/45306091i | repeat-01 collected 26/26 workers (60617 items) tests 9303 done 1 failed | 26 in flight, oldest 130s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
........................................................ [432%]
.......................[contention-diag] +1525s soak 28p/255t rss 11.5G pss 10.7G swap 0.8G majflt 1571 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 24.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 11.56 | cgroup 11.7G/max oom_kill 0 | free scratch 320.3G/45304512i tmp 29.4G/1010767i workspace 320.3G/45304512i | repeat-01 collected 26/26 workers (60617 items) tests 9381 done 1 failed | 26 in flight, oldest 145s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................................. [435%]
.....................[contention-diag] +1540s soak 29p/250t rss 11.5G pss 10.7G swap 0.8G majflt 1573 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 14.17 | cgroup 11.7G/max oom_kill 0 | free scratch 320.4G/45304471i tmp 29.4G/1010767i workspace 320.4G/45304471i | repeat-01 collected 26/26 workers (60617 items) tests 9451 done 1 failed | 26 in flight, oldest 160s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
...............................[contention-diag] +1555s soak 28p/241t rss 11.5G pss 10.7G swap 0.8G majflt 1579 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 24.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.27 cpu 12.93 | cgroup 11.7G/max oom_kill 0 | free scratch 320.0G/45276813i tmp 29.3G/1010283i workspace 320.0G/45276813i | repeat-01 collected 26/26 workers (60617 items) tests 9483 done 1 failed | 26 in flight, oldest 176s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................... [438%]
...................[contention-diag] +1571s soak 28p/242t rss 11.5G pss 10.7G swap 0.8G majflt 1599 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 30.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 7.7 cpu 11.37 | cgroup 11.7G/max oom_kill 0 | free scratch 320.1G/45276235i tmp 29.4G/1010713i workspace 320.1G/45276235i | repeat-01 collected 26/26 workers (60617 items) tests 9512 done 1 failed | 26 in flight, oldest 79s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................................[contention-diag] +1586s soak 31p/246t rss 11.6G pss 10.7G swap 0.8G majflt 1708 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G, 3 descendant rss 0.1G pss 0.0G | host avail 29.8G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 1.55 cpu 25.3 | cgroup 11.7G/max oom_kill 0 | free scratch 320.1G/45275743i tmp 29.4G/1010713i workspace 320.1G/45275743i | repeat-01 collected 26/26 workers (60617 items) tests 9559 done 1 failed | 26 in flight, oldest 95s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................. [442%]
........................................................................ [445%]
......................[contention-diag] +1601s soak 30p/255t rss 11.6G pss 10.7G swap 0.8G majflt 1602 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 25.78 | cgroup 11.7G/max oom_kill 0 | free scratch 320.1G/45275489i tmp 29.4G/1010713i workspace 320.1G/45275489i | repeat-01 collected 26/26 workers (60617 items) tests 9669 done 1 failed | 26 in flight, oldest 110s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................. [448%]
........................................................................ [452%]
...................................[contention-diag] +1617s soak 28p/240t rss 11.5G pss 10.7G swap 0.8G majflt 1604 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 31.1G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 32.12 | cgroup 11.7G/max oom_kill 0 | free scratch 320.1G/45275243i tmp 29.4G/1010728i workspace 320.1G/45275243i | scratch used 0.6G in 104119 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 9796 done 1 failed | 26 in flight, oldest 125s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................... [455%]
........................................................................ [458%]
............[contention-diag] +1634s soak 29p/215t rss 11.6G pss 10.7G swap 0.8G majflt 1614 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.41 cpu 20.18 | cgroup 11.8G/max oom_kill 0 | free scratch 320.1G/45274975i tmp 29.4G/1010741i workspace 320.1G/45274975i | repeat-01 collected 26/26 workers (60617 items) tests 9940 done 1 failed | 26 in flight, oldest 143s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................................ [462%]
...............................[contention-diag] +1649s soak 28p/241t rss 11.6G pss 10.7G swap 0.8G majflt 1618 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G | host avail 30.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.08 cpu 28.08 | cgroup 11.8G/max oom_kill 0 | free scratch 320.1G/45274737i tmp 29.4G/1010741i workspace 320.1G/45274737i | repeat-01 collected 26/26 workers (60617 items) tests 10036 done 1 failed | 26 in flight, oldest 158s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.....................................[contention-diag] +1665s soak 31p/244t rss 11.7G pss 10.8G swap 0.8G majflt 1622 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 3 descendant rss 0.1G pss 0.0G | host avail 29.2G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 25.04 | cgroup 11.8G/max oom_kill 0 | free scratch 320.1G/45274552i tmp 29.4G/1010741i workspace 320.1G/45274552i | repeat-01 collected 26/26 workers (60617 items) tests 10076 done 1 failed | 26 in flight, oldest 173s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.... [465%]
.......................................................................[contention-diag] +1680s soak 29p/258t rss 11.7G pss 10.9G swap 0.8G majflt 1653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.58 | cgroup 11.9G/max oom_kill 0 | free scratch 320.1G/45273843i tmp 29.4G/1010741i workspace 320.1G/45273843i | repeat-01 collected 26/26 workers (60617 items) tests 10146 done 1 failed | 26 in flight, oldest 189s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
. [468%]
...................[contention-diag] +1695s soak 28p/279t rss 11.6G pss 10.8G swap 0.8G majflt 1653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G | host avail 34.5G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 32.0 | cgroup 11.9G/max oom_kill 0 | free scratch 320.0G/45273439i tmp 29.4G/1010740i workspace 320.0G/45273439i | repeat-01 collected 26/26 workers (60617 items) tests 10170 done 1 failed | 26 in flight, oldest 204s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................... [472%]
...........[contention-diag] +1711s soak 31p/263t rss 11.8G pss 10.9G swap 0.8G majflt 1656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 3 descendant rss 0.1G pss 0.1G | host avail 30.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 20.59 | cgroup 11.9G/max oom_kill 0 | free scratch 319.8G/45273115i tmp 29.4G/1010741i workspace 319.8G/45273115i | repeat-01 collected 26/26 workers (60617 items) tests 10233 done 1 failed | 26 in flight, oldest 220s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................................. [475%]
....................[contention-diag] +1726s soak 28p/259t rss 11.7G pss 10.8G swap 0.8G majflt 1653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 31.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.0 cpu 15.07 | cgroup 11.9G/max oom_kill 0 | free scratch 320.0G/45272965i tmp 29.4G/1010741i workspace 320.0G/45272965i | repeat-01 collected 26/26 workers (60617 items) tests 10313 done 1 failed | 26 in flight, oldest 235s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................... [478%]
......................................................[contention-diag] +1742s soak 28p/257t rss 11.7G pss 10.9G swap 0.8G majflt 1653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G | host avail 30.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.9 cpu 16.95 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45272501i tmp 29.4G/1010741i workspace 320.0G/45272501i | scratch used 1.0G in 173753 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 10406 done 1 failed | 26 in flight, oldest 250s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [482%]
........................................................................ [485%]
..........[contention-diag] +1759s soak 29p/256t rss 11.7G pss 10.9G swap 0.8G majflt 1653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 20.98 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45272287i tmp 29.4G/1010741i workspace 320.0G/45272287i | repeat-01 collected 26/26 workers (60617 items) tests 10515 done 1 failed | 26 in flight, oldest 268s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................................. [488%]
............................[contention-diag] +1774s soak 28p/264t rss 11.7G pss 10.9G swap 0.8G majflt 1653 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G | host avail 28.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 19.0 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45272016i tmp 29.4G/1010741i workspace 320.0G/45272016i | repeat-01 collected 26/26 workers (60617 items) tests 10609 done 1 failed | 26 in flight, oldest 283s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................ [492%]
......................................................................[contention-diag] +1790s soak 28p/273t rss 11.7G pss 10.9G swap 0.8G majflt 1660 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G | host avail 31.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.98 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45271648i tmp 29.4G/1010741i workspace 320.0G/45271648i | repeat-01 collected 26/26 workers (60617 items) tests 10722 done 1 failed | 26 in flight, oldest 298s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.. [495%]
........................................................................ [498%]
...........................[contention-diag] +1805s soak 28p/249t rss 11.8G pss 10.9G swap 0.8G majflt 1666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G | host avail 31.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.68 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45271242i tmp 29.4G/1010741i workspace 320.0G/45271242i | repeat-01 collected 26/26 workers (60617 items) tests 10824 done 1 failed | 26 in flight, oldest 314s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................. [502%]
..............................[contention-diag] +1820s soak 30p/252t rss 11.8G pss 10.9G swap 0.8G majflt 1672 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 25.99 | cgroup 12.1G/max oom_kill 0 | free scratch 320.0G/45270925i tmp 29.4G/1010741i workspace 320.0G/45270925i | repeat-01 collected 26/26 workers (60617 items) tests 10901 done 1 failed | 26 in flight, oldest 329s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................................... [505%]
...................................................[contention-diag] +1836s soak 30p/280t rss 11.8G pss 10.9G swap 0.8G majflt 1693 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.02 cpu 21.93 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45270525i tmp 29.4G/1010739i workspace 320.0G/45270525i | repeat-01 collected 26/26 workers (60617 items) tests 10992 done 1 failed | 26 in flight, oldest 56s gw9 tests/ace/tui/test_config_center_tabs.py::test_landing_compact_class_tracks_viewport_size
..................... [508%]
..................................................[contention-diag] +1851s soak 30p/289t rss 11.8G pss 10.9G swap 0.8G majflt 1718 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 32.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.19/0.07 io 0.12 cpu 25.24 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45270216i tmp 29.4G/1010741i workspace 320.0G/45270216i | repeat-01 collected 26/26 workers (60617 items) tests 11060 done 1 failed | 26 in flight, oldest 52s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
...................... [512%]
..............................................[contention-diag] +1866s soak 31p/269t rss 11.8G pss 10.9G swap 0.8G majflt 1718 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.65/0.01 io 0.14 cpu 31.17 | cgroup 12.0G/max oom_kill 0 | free scratch 320.0G/45269923i tmp 29.4G/1010741i workspace 320.0G/45269923i | scratch used 0.4G in 73715 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 11129 done 1 failed | 26 in flight, oldest 67s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.......................... [515%]
............................................[contention-diag] +1883s soak 30p/286t rss 11.8G pss 11.0G swap 0.8G majflt 1720 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 32.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.0 io 0.17 cpu 31.44 | cgroup 12.1G/max oom_kill 0 | free scratch 320.0G/45269649i tmp 29.4G/1010741i workspace 320.0G/45269649i | repeat-01 collected 26/26 workers (60617 items) tests 11203 done 1 failed | 26 in flight, oldest 84s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
............................ [518%]
..................[contention-diag] +1899s soak 30p/294t rss 11.8G pss 11.0G swap 0.8G majflt 1720 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.03 cpu 28.28 | cgroup 12.1G/max oom_kill 0 | free scratch 320.0G/45269450i tmp 29.4G/1010741i workspace 320.0G/45269450i | repeat-01 collected 26/26 workers (60617 items) tests 11249 done 1 failed | 26 in flight, oldest 100s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
...................................................... [522%]
........................................................................ [525%]
...................................................................[contention-diag] +1914s soak 29p/262t rss 11.9G pss 11.0G swap 0.8G majflt 1720 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 1 descendant rss 0.1G pss 0.0G | host avail 27.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 22.72 | cgroup 12.1G/max oom_kill 0 | free scratch 319.4G/45268510i tmp 29.4G/1010741i workspace 319.4G/45268510i | repeat-01 collected 26/26 workers (60617 items) tests 11437 done 1 failed | 26 in flight, oldest 70s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
..... [528%]
........................................................................ [532%]
.....................................................................[contention-diag] +1930s soak 29p/246t rss 11.9G pss 11.0G swap 0.8G majflt 1723 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 32.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.63 cpu 32.95 | cgroup 12.1G/max oom_kill 0 | free scratch 319.1G/45268081i tmp 29.4G/1010741i workspace 319.1G/45268081i | repeat-01 collected 26/26 workers (60617 items) tests 11588 done 1 failed | 26 in flight, oldest 85s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
... [535%]
...................[contention-diag] +1945s soak 29p/256t rss 11.9G pss 11.1G swap 0.8G majflt 1723 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 31.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 34.85 | cgroup 12.2G/max oom_kill 0 | free scratch 319.1G/45267987i tmp 29.4G/1010741i workspace 319.1G/45267987i | repeat-01 collected 26/26 workers (60617 items) tests 11608 done 1 failed | 26 in flight, oldest 50s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
..................................................... [538%]
....................................[contention-diag] +1960s soak 30p/254t rss 11.9G pss 11.1G swap 0.8G majflt 1724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.1G pss 0.0G | host avail 31.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 29.98 | cgroup 12.2G/max oom_kill 0 | free scratch 319.1G/45267619i tmp 29.4G/1010741i workspace 319.1G/45267619i | repeat-01 collected 26/26 workers (60617 items) tests 11687 done 1 failed | 26 in flight, oldest 48s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
.................................... [542%]
................................[contention-diag] +1976s soak 31p/267t rss 12.0G pss 11.1G swap 0.8G majflt 1724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 26.96 | cgroup 12.2G/max oom_kill 0 | free scratch 319.1G/45267352i tmp 29.4G/1010741i workspace 319.1G/45267352i | repeat-01 collected 26/26 workers (60617 items) tests 11766 done 1 failed | 26 in flight, oldest 63s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
.................................[contention-diag] +1991s soak 30p/272t rss 11.9G pss 11.1G swap 0.8G majflt 1724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.76 | cgroup 12.2G/max oom_kill 0 | free scratch 319.1G/45267274i tmp 29.4G/1010741i workspace 319.1G/45267274i | scratch used 0.8G in 151890 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 11798 done 1 failed | 26 in flight, oldest 78s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
....... [545%]
.................................................................[contention-diag] +2008s soak 30p/259t rss 12.0G pss 11.1G swap 0.8G majflt 1724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 2 descendant rss 0.1G pss 0.1G | host avail 31.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 33.87 | cgroup 12.3G/max oom_kill 0 | free scratch 319.1G/45267013i tmp 29.4G/1010741i workspace 319.1G/45267013i | repeat-01 collected 26/26 workers (60617 items) tests 11861 done 1 failed | 26 in flight, oldest 47s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree
....... [548%]
........................................................................ [552%]
........................................................[contention-diag] +2023s soak 31p/255t rss 12.0G pss 11.2G swap 0.8G majflt 1724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 3 descendant rss 0.1G pss 0.1G | host avail 32.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 30.84 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45266412i tmp 29.4G/1010738i workspace 319.0G/45266412i | repeat-01 collected 26/26 workers (60617 items) tests 12006 done 1 failed | 26 in flight, oldest 63s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree
................ [555%]
.................................................................[contention-diag] +2039s soak 33p/248t rss 12.0G pss 11.1G swap 0.8G majflt 1734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 5 descendant rss 0.1G pss 0.0G | host avail 31.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.0 cpu 30.24 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45266020i tmp 29.4G/1010741i workspace 319.0G/45266020i | repeat-01 collected 26/26 workers (60617 items) tests 12078 done 1 failed | 25 in flight, oldest 73s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
....... [558%]
........................................................................ [562%]
........................................................................ [565%]
...............[contention-diag] +2054s soak 29p/250t rss 12.0G pss 11.1G swap 0.8G majflt 1736 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.0 cpu 32.2 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45265846i tmp 29.4G/1010741i workspace 319.0G/45265846i | repeat-01 collected 26/26 workers (60617 items) tests 12251 done 1 failed | 26 in flight, oldest 89s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
......................................................... [568%]
.........................[contention-diag] +2069s soak 30p/250t rss 12.0G pss 11.1G swap 0.8G majflt 1746 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 31.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.22 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45265467i tmp 29.4G/1010741i workspace 319.0G/45265467i | repeat-01 collected 26/26 workers (60617 items) tests 12336 done 1 failed | 26 in flight, oldest 53s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
............................................... [572%]
........................................................................ [575%]
................................................[contention-diag] +2085s soak 30p/250t rss 12.0G pss 11.2G swap 0.7G majflt 1752 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 30.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.56 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45265149i tmp 29.4G/1010741i workspace 319.0G/45265149i | repeat-01 collected 26/26 workers (60617 items) tests 12481 done 1 failed | 26 in flight, oldest 44s gw12 tests/ace/tui/test_plugins_browser_pane_marks.py::test_i_marks_updatable_cli_rows
........................ [578%]
........................................................................ [581%]
........................................................................ [585%]
.................................[contention-diag] +2100s soak 33p/260t rss 12.0G pss 11.1G swap 0.7G majflt 1753 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 5 descendant rss 0.0G pss 0.0G | host avail 29.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.17 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45264481i tmp 29.4G/1010741i workspace 319.0G/45264481i | repeat-01 collected 26/26 workers (60617 items) tests 12704 done 1 failed | 26 in flight, oldest 46s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_digit_owns_hidden_member_jump_state[None]
....................................... [588%]
........................................................................ [591%]
..........................................................[contention-diag] +2115s soak 30p/254t rss 12.0G pss 11.2G swap 0.7G majflt 1753 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 27.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.77 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45264026i tmp 29.4G/1010741i workspace 319.0G/45264026i | scratch used 1.0G in 185943 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 12866 done 1 failed | 26 in flight, oldest 49s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
.............. [595%]
........................................................................ [598%]
....................................................[contention-diag] +2133s soak 34p/261t rss 12.1G pss 11.2G swap 0.7G majflt 1756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.0G, 6 descendant rss 0.0G pss 0.0G | host avail 27.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.04 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45263633i tmp 29.4G/1010741i workspace 319.0G/45263633i | repeat-01 collected 26/26 workers (60617 items) tests 13001 done 1 failed | 25 in flight, oldest 49s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.................... [601%]
......................................................................[contention-diag] +2148s soak 34p/273t rss 12.1G pss 11.2G swap 0.7G majflt 1756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 6 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.66 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45263347i tmp 29.4G/1010741i workspace 319.0G/45263347i | repeat-01 collected 26/26 workers (60617 items) tests 13101 done 1 failed | 26 in flight, oldest 64s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.. [605%]
........................................................................ [608%]
........................................................................ [611%]
........................................................................ [615%]
.............................[contention-diag] +2163s soak 32p/242t rss 12.1G pss 11.3G swap 0.7G majflt 1767 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 4 descendant rss 0.1G pss 0.0G | host avail 26.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.0 cpu 28.84 | cgroup 12.4G/max oom_kill 0 | free scratch 319.0G/45262336i tmp 29.4G/1010741i workspace 319.0G/45262336i | repeat-01 collected 26/26 workers (60617 items) tests 13346 done 1 failed | 26 in flight, oldest 59s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
........................................... [618%]
...................[contention-diag] +2179s soak 35p/251t rss 12.1G pss 11.2G swap 0.7G majflt 1778 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 7 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.14/0.02 io 0.0 cpu 21.91 | cgroup 12.4G/max oom_kill 0 | free scratch 318.8G/45261883i tmp 29.4G/1010741i workspace 318.8G/45261883i | repeat-01 collected 26/26 workers (60617 items) tests 13408 done 1 failed | 26 in flight, oldest 74s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
..................................................... [621%]
...........................................[contention-diag] +2194s soak 35p/254t rss 12.1G pss 11.2G swap 0.7G majflt 1783 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 7 descendant rss 0.0G pss 0.0G | host avail 30.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.92/0.0 io 0.0 cpu 21.32 | cgroup 12.4G/max oom_kill 0 | free scratch 319.0G/45261750i tmp 29.4G/1010741i workspace 319.0G/45261750i | repeat-01 collected 26/26 workers (60617 items) tests 13505 done 1 failed | 26 in flight, oldest 50s gw22 tests/ace/tui/test_statistics_footprint.py::test_footprint_rows_drill_into_and_back_out_of_an_area
............................. [625%]
........................................................................ [628%]
......................................[contention-diag] +2209s soak 31p/266t rss 12.3G pss 11.4G swap 0.7G majflt 1846 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 3 descendant rss 0.1G pss 0.1G | host avail 31.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.18/0.0 io 0.0 cpu 31.59 | cgroup 12.5G/max oom_kill 0 | free scratch 319.0G/45261533i tmp 29.4G/1010741i workspace 319.0G/45261533i | repeat-01 collected 26/26 workers (60617 items) tests 13635 done 1 failed | 26 in flight, oldest 64s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.................................. [631%]
........................................................................ [635%]
.................................[contention-diag] +2225s soak 34p/296t rss 12.3G pss 11.4G swap 0.7G majflt 1803 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 6 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.81/0.41 io 0.41 cpu 31.39 | cgroup 12.5G/max oom_kill 0 | free scratch 319.0G/45260904i tmp 29.4G/1010741i workspace 319.0G/45260904i | repeat-01 collected 26/26 workers (60617 items) tests 13783 done 1 failed | 26 in flight, oldest 79s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
....................................... [638%]
................[contention-diag] +2240s soak 29p/302t rss 12.2G pss 11.3G swap 0.7G majflt 1794 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G, 1 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.2/0.1 io 0.28 cpu 31.98 | cgroup 12.6G/max oom_kill 0 | free scratch 319.0G/45260609i tmp 29.4G/1010741i workspace 319.0G/45260609i | scratch used 1.0G in 190668 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 13831 done 1 failed | 26 in flight, oldest 95s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.............................................[contention-diag] +2257s soak 29p/258t rss 12.2G pss 11.3G swap 0.7G majflt 1798 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 0.04 cpu 28.38 | cgroup 12.7G/max oom_kill 0 | free scratch 319.0G/45260177i tmp 29.4G/1010741i workspace 319.0G/45260177i | repeat-01 collected 26/26 workers (60617 items) tests 13881 done 1 failed | 26 in flight, oldest 112s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
........... [641%]
........................................................................ [645%]
..................................................................[contention-diag] +2273s soak 28p/254t rss 12.2G pss 11.3G swap 0.7G majflt 1798 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G | host avail 30.4G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.11 | cgroup 12.7G/max oom_kill 0 | free scratch 319.0G/45259817i tmp 29.4G/1010741i workspace 319.0G/45259817i | repeat-01 collected 26/26 workers (60617 items) tests 14031 done 1 failed | 26 in flight, oldest 88s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
...... [648%]
.......................................................................[contention-diag] +2288s soak 29p/262t rss 12.2G pss 11.3G swap 0.7G majflt 1808 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.86 | cgroup 12.6G/max oom_kill 0 | free scratch 319.0G/45259387i tmp 29.4G/1010736i workspace 319.0G/45259387i | repeat-01 collected 26/26 workers (60617 items) tests 14109 done 1 failed | 26 in flight, oldest 62s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_task_uses_admin_center_trigger_and_progress
. [651%]
........................................................................ [655%]
...........................[contention-diag] +2303s soak 29p/276t rss 12.2G pss 11.3G swap 0.7G majflt 1813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.13 | cgroup 12.7G/max oom_kill 0 | free scratch 319.0G/45259035i tmp 29.4G/1010692i workspace 319.0G/45259035i | repeat-01 collected 26/26 workers (60617 items) tests 14207 done 1 failed | 26 in flight, oldest 49s gw22 tests/ace/tui/test_statistics_footprint.py::test_footprint_copy_sends_selected_feature_id
............................................. [658%]
....................................................[contention-diag] +2319s soak 33p/296t rss 12.4G pss 11.4G swap 0.7G majflt 1813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 28.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.92 | cgroup 12.8G/max oom_kill 0 | free scratch 319.0G/45258624i tmp 29.4G/1010736i workspace 319.0G/45258624i | repeat-01 collected 26/26 workers (60617 items) tests 14303 done 1 failed | 26 in flight, oldest 50s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
.................... [661%]
........................................................................ [665%]
........................................................................ [668%]
...........[contention-diag] +2334s soak 31p/263t rss 12.3G pss 11.4G swap 0.7G majflt 1843 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.26 | cgroup 12.7G/max oom_kill 0 | free scratch 319.0G/45257691i tmp 29.4G/1010736i workspace 319.0G/45257691i | repeat-01 collected 26/26 workers (60617 items) tests 14478 done 1 failed | 26 in flight, oldest 66s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
............................................................. [671%]
.................[contention-diag] +2349s soak 35p/252t rss 12.3G pss 11.4G swap 0.7G majflt 1886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 7 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 22.05 | cgroup 12.7G/max oom_kill 0 | free scratch 319.0G/45257250i tmp 29.4G/1010736i workspace 319.0G/45257250i | repeat-01 collected 26/26 workers (60617 items) tests 14556 done 1 failed | 26 in flight, oldest 73s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
....................................................... [675%]
........................................................................ [678%]
........................................................................ [681%]
..............................[contention-diag] +2365s soak 32p/232t rss 12.3G pss 11.4G swap 0.7G majflt 1892 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 4 descendant rss 0.0G pss 0.0G | host avail 31.1G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 20.38 | cgroup 12.7G/max oom_kill 0 | free scratch 324.3G/45290109i tmp 29.4G/1010734i workspace 324.3G/45290109i | scratch used 1.0G in 194529 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 14751 done 1 failed | 26 in flight, oldest 40s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
.......................................... [685%]
........................................................................ [688%]
......................................................[contention-diag] +2382s soak 32p/271t rss 12.4G pss 11.5G swap 0.7G majflt 1901 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 4 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 17.26 | cgroup 12.8G/max oom_kill 0 | free scratch 324.3G/45289064i tmp 29.4G/1010736i workspace 324.3G/45289064i | repeat-01 collected 26/26 workers (60617 items) tests 14947 done 1 failed | 25 in flight, oldest 42s gw6 tests/ace/tui/test_macro_browser_filter.py::test_empty_catalog_filter_and_list_escape_are_safe
.................. [691%]
........................................................................ [695%]
..............................................[contention-diag] +2397s soak 31p/266t rss 12.4G pss 11.5G swap 0.7G majflt 1908 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 3 descendant rss 0.1G pss 0.0G | host avail 31.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 17.52 | cgroup 12.8G/max oom_kill 0 | free scratch 324.3G/45287864i tmp 29.4G/1010736i workspace 324.3G/45287864i | repeat-01 collected 26/26 workers (60617 items) tests 15091 done 1 failed | 26 in flight, oldest 58s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_brackets_cycle_config_subtabs_from_macro_list_and_filter
.......................... [698%]
.............................[contention-diag] +2413s soak 34p/275t rss 12.5G pss 11.6G swap 0.7G majflt 1909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 6 descendant rss 0.1G pss 0.1G | host avail 28.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 18.29 | cgroup 12.8G/max oom_kill 0 | free scratch 324.3G/45287156i tmp 29.4G/1010736i workspace 324.3G/45287156i | repeat-01 collected 26/26 workers (60617 items) tests 15146 done 1 failed | 26 in flight, oldest 68s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
........................................... [701%]
........................................................................ [705%]
........................................................................ [708%]
........................................................................ [711%]
........................................................................ [715%]
.....[contention-diag] +2428s soak 31p/251t rss 12.4G pss 11.5G swap 0.7G majflt 1909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 3 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 24.31 | cgroup 12.8G/max oom_kill 0 | free scratch 324.3G/45285894i tmp 29.4G/1010736i workspace 324.3G/45285894i | repeat-01 collected 26/26 workers (60617 items) tests 15474 done 1 failed | 26 in flight, oldest 70s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
................................................................... [718%]
........................................................................ [721%]
.....................................[contention-diag] +2444s soak 30p/257t rss 12.4G pss 11.5G swap 0.7G majflt 1926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 2 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 20.0 | cgroup 12.9G/max oom_kill 0 | free scratch 324.3G/45285064i tmp 29.4G/1010736i workspace 324.3G/45285064i | repeat-01 collected 26/26 workers (60617 items) tests 15659 done 1 failed | 26 in flight, oldest 71s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................... [724%]
........................................................................ [728%]
...................[contention-diag] +2459s soak 36p/285t rss 12.5G pss 11.6G swap 0.7G majflt 1926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 8 descendant rss 0.1G pss 0.1G | host avail 29.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 23.99 | cgroup 13.0G/max oom_kill 0 | free scratch 324.3G/45284491i tmp 29.4G/1010736i workspace 324.3G/45284491i | repeat-01 collected 26/26 workers (60617 items) tests 15776 done 1 failed | 26 in flight, oldest 86s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
..................................................... [731%]
....................[contention-diag] +2474s soak 31p/276t rss 12.6G pss 11.7G swap 0.7G majflt 1926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 3 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 27.54 | cgroup 13.1G/max oom_kill 0 | free scratch 324.3G/45283640i tmp 29.4G/1010736i workspace 324.3G/45283640i | repeat-01 collected 26/26 workers (60617 items) tests 15853 done 1 failed | 26 in flight, oldest 101s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................... [734%]
........................................................................ [738%]
........................................................................ [741%]
..[contention-diag] +2490s soak 33p/260t rss 12.6G pss 11.7G swap 0.7G majflt 1934 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 5 descendant rss 0.2G pss 0.2G | host avail 29.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 27.09 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45286700i tmp 29.4G/1010736i workspace 324.7G/45286700i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 16015 done 1 failed | 26 in flight, oldest 117s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................................................................... [744%]
........................................................................ [748%]
........................................................................ [751%]
........................................................................ [754%]
.......[contention-diag] +2507s soak 33p/236t rss 12.6G pss 11.6G swap 0.7G majflt 1942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 5 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 25.73 | cgroup 13.0G/max oom_kill 0 | free scratch 324.7G/45285060i tmp 29.4G/1010736i workspace 324.7G/45285060i | repeat-01 collected 26/26 workers (60617 items) tests 16346 done 1 failed | 26 in flight, oldest 134s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................................. [758%]
........................................................................ [761%]
..............................................................[contention-diag] +2522s soak 33p/244t rss 12.6G pss 11.7G swap 0.7G majflt 1942 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 5 descendant rss 0.1G pss 0.1G | host avail 29.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.39 | cgroup 13.0G/max oom_kill 0 | free scratch 324.7G/45284560i tmp 29.4G/1010736i workspace 324.7G/45284560i | repeat-01 collected 26/26 workers (60617 items) tests 16548 done 1 failed | 26 in flight, oldest 149s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.......... [764%]
........................................................................ [768%]
........................................................................ [771%]
........................................................................ [774%]
......[contention-diag] +2538s soak 36p/293t rss 12.6G pss 11.7G swap 0.7G majflt 1943 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 8 descendant rss 0.1G pss 0.0G | host avail 29.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.66/0.66 io 0.32 cpu 21.33 | cgroup 13.0G/max oom_kill 0 | free scratch 324.7G/45284016i tmp 29.4G/1010735i workspace 324.7G/45284016i | repeat-01 collected 26/26 workers (60617 items) tests 16778 done 1 failed | 26 in flight, oldest 165s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................................. [778%]
........................................................................ [781%]
........................................................................ [784%]
......[contention-diag] +2553s soak 31p/295t rss 12.6G pss 11.7G swap 0.7G majflt 1958 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 3 descendant rss 0.1G pss 0.0G | host avail 28.5G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.29 cpu 23.66 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45285760i tmp 29.4G/1010735i workspace 324.7G/45285760i | repeat-01 collected 26/26 workers (60617 items) tests 16986 done 1 failed | 25 in flight, oldest 92s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.................................................................. [788%]
........................................................................ [791%]
......................................................[contention-diag] +2568s soak 34p/304t rss 12.8G pss 11.8G swap 0.7G majflt 1962 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 6 descendant rss 0.2G pss 0.1G | host avail 29.3G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.05 cpu 23.85 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45285194i tmp 29.4G/1010735i workspace 324.7G/45285194i | repeat-01 collected 26/26 workers (60617 items) tests 17181 done 1 failed | 25 in flight, oldest 108s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.................. [794%]
........................................................................ [798%]
..................................[contention-diag] +2584s soak 33p/264t rss 12.7G pss 11.8G swap 0.7G majflt 1963 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 28.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 26.06 | cgroup 13.4G/max oom_kill 0 | free scratch 324.7G/45284737i tmp 29.4G/1010734i workspace 324.7G/45284737i | repeat-01 collected 26/26 workers (60617 items) tests 17305 done 1 failed | 26 in flight, oldest 123s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
...................................... [801%]
........................................................................ [804%]
........................................................................ [808%]
........................................................................ [811%]
.............................................................[contention-diag] +2599s soak 32p/257t rss 12.6G pss 11.7G swap 0.7G majflt 1963 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.81 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45283724i tmp 29.4G/1010734i workspace 324.7G/45283724i | repeat-01 collected 26/26 workers (60617 items) tests 17625 done 1 failed | 26 in flight, oldest 138s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........... [814%]
........................................................................ [818%]
........................................................................ [821%]
........................................................................ [824%]
....................[contention-diag] +2614s soak 29p/237t rss 12.6G pss 11.7G swap 0.7G majflt 1971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 1 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 20.48 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45283454i tmp 29.4G/1010734i workspace 324.7G/45283454i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 17828 done 1 failed | 26 in flight, oldest 63s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.................................................... [828%]
........................................................................ [831%]
........................................................................ [834%]
...........................[contention-diag] +2632s soak 33p/252t rss 12.6G pss 11.7G swap 0.7G majflt 1973 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 19.06 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45282736i tmp 29.4G/1010734i workspace 324.7G/45282736i | repeat-01 collected 26/26 workers (60617 items) tests 18099 done 1 failed | 26 in flight, oldest 80s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................. [838%]
........................................................................ [841%]
.............................................................[contention-diag] +2647s soak 32p/247t rss 12.7G pss 11.8G swap 0.7G majflt 1973 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 4 descendant rss 0.1G pss 0.1G | host avail 29.0G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.48 cpu 27.6 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45282192i tmp 29.4G/1010734i workspace 324.7G/45282192i | repeat-01 collected 26/26 workers (60617 items) tests 18266 done 1 failed | 26 in flight, oldest 95s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
........... [844%]
........................................................................ [848%]
...................................[contention-diag] +2662s soak 32p/222t rss 12.6G pss 11.7G swap 0.7G majflt 1975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 27.86 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45281777i tmp 29.4G/1010734i workspace 324.7G/45281777i | repeat-01 collected 26/26 workers (60617 items) tests 18376 done 1 failed | 26 in flight, oldest 111s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
..................................... [851%]
........................................................................ [854%]
........[contention-diag] +2678s soak 33p/237t rss 12.7G pss 11.7G swap 0.7G majflt 1975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 28.71 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45281496i tmp 29.4G/1010734i workspace 324.7G/45281496i | repeat-01 collected 26/26 workers (60617 items) tests 18494 done 1 failed | 25 in flight, oldest 44s gw8 tests/ace/tui/test_usage_header.py::test_pilot_clicks_open_usage_without_expanding_header
................................................................ [858%]
........................................................................ [861%]
........................................................................ [864%]
........................................................................ [867%]
........................................................................ [871%]
..................[contention-diag] +2693s soak 30p/237t rss 12.7G pss 11.7G swap 0.7G majflt 1975 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 2 descendant rss 0.0G pss 0.0G | host avail 29.6G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.78 cpu 34.78 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45280393i tmp 29.4G/1010734i workspace 324.7G/45280393i | repeat-01 collected 26/26 workers (60617 items) tests 18871 done 1 failed | 26 in flight, oldest 51s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_agents_tab
...................................................... [874%]
........................................................................ [877%]
........................................................................ [881%]
...............................................[contention-diag] +2708s soak 36p/236t rss 12.7G pss 11.8G swap 0.7G majflt 1983 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 8 descendant rss 0.0G pss 0.0G | host avail 29.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 29.4 | cgroup 13.3G/max oom_kill 0 | free scratch 324.7G/45279107i tmp 29.4G/1010734i workspace 324.7G/45279107i | repeat-01 collected 26/26 workers (60617 items) tests 19125 done 1 failed | 26 in flight, oldest 47s gw9 tests/ace/tui/test_projects_pane.py::test_configured_cycle_subtab_keys_bubble_and_forward
......................... [884%]
........................................................................ [887%]
......................................................[contention-diag] +2724s soak 36p/248t rss 12.8G pss 11.9G swap 0.7G majflt 1997 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 8 descendant rss 0.1G pss 0.1G | host avail 28.6G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.52 cpu 26.65 | cgroup 13.3G/max oom_kill 0 | free scratch 324.6G/45278859i tmp 29.4G/1010734i workspace 324.6G/45278859i | repeat-01 collected 26/26 workers (60617 items) tests 19269 done 1 failed | 26 in flight, oldest 59s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........s......... [891%]
........................................................................ [894%]
........................................................................ [897%]
...............ss....................................................... [901%]
...[contention-diag] +2739s soak 31p/247t rss 12.8G pss 11.8G swap 0.7G majflt 2015 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 3 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 25.39 | cgroup 13.3G/max oom_kill 0 | free scratch 324.6G/45278484i tmp 29.4G/1010733i workspace 324.6G/45278484i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 19483 done 1 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
..................................................................... [904%]
........................................................................ [907%]
........................................................................ [911%]
........................................................................ [914%]
......................................................[contention-diag] +2756s soak 32p/258t rss 12.8G pss 11.8G swap 0.7G majflt 2033 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 4 descendant rss 0.0G pss 0.0G | host avail 29.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.66 cpu 25.66 | cgroup 13.3G/max oom_kill 0 | free scratch 324.6G/45277409i tmp 29.4G/1010733i workspace 324.6G/45277409i | repeat-01 collected 26/26 workers (60617 items) tests 19824 done 1 failed | 25 in flight, oldest 91s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................. [917%]
........................................................................ [921%]
........................................................................ [924%]
........................................................................ [927%]
................................................[contention-diag] +2772s soak 32p/252t rss 12.8G pss 11.8G swap 0.7G majflt 2035 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 4 descendant rss 0.1G pss 0.0G | host avail 31.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.14 cpu 33.76 | cgroup 13.3G/max oom_kill 0 | free scratch 324.6G/45276487i tmp 29.4G/1010733i workspace 324.6G/45276487i | repeat-01 collected 26/26 workers (60617 items) tests 20129 done 1 failed | 25 in flight, oldest 107s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................ [931%]
........................................................................ [934%]
........................................................................ [937%]
..................................................................[contention-diag] +2787s soak 38p/275t rss 12.9G pss 11.9G swap 0.7G majflt 2038 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 10 descendant rss 0.2G pss 0.1G | host avail 30.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 26.75 | cgroup 13.4G/max oom_kill 0 | free scratch 324.6G/45275683i tmp 29.4G/1010733i workspace 324.6G/45275683i | repeat-01 collected 26/26 workers (60617 items) tests 20363 done 1 failed | 26 in flight, oldest 47s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_refresh_preserves_selection_and_hidden_tick_is_inert
...... [941%]
........................................................................ [944%]
.................[contention-diag] +2802s soak 35p/278t rss 12.9G pss 11.9G swap 0.7G majflt 2045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 7 descendant rss 0.1G pss 0.1G | host avail 28.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 27.77 | cgroup 13.4G/max oom_kill 0 | free scratch 324.6G/45275302i tmp 29.4G/1010733i workspace 324.6G/45275302i | repeat-01 collected 26/26 workers (60617 items) tests 20462 done 1 failed | 26 in flight, oldest 59s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_macro_focus_picker_all_clear_key_and_cancel
....................................................... [947%]
........................................................................ [951%]
........................................................................ [954%]
............[contention-diag] +2818s soak 37p/273t rss 13.1G pss 12.1G swap 0.7G majflt 2047 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 9 descendant rss 0.3G pss 0.2G | host avail 30.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 33.6 | cgroup 13.5G/max oom_kill 0 | free scratch 324.6G/45274780i tmp 29.4G/1010733i workspace 324.6G/45274780i | repeat-01 collected 26/26 workers (60617 items) tests 20662 done 1 failed | 26 in flight, oldest 61s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
............................................................ [957%]
........................................................................ [961%]
........................................................................ [964%]
....................................................[contention-diag] +2833s soak 34p/266t rss 13.1G pss 12.1G swap 0.7G majflt 2052 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 6 descendant rss 0.3G pss 0.2G | host avail 31.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 43.04 | cgroup 13.6G/max oom_kill 0 | free scratch 324.6G/45274246i tmp 29.4G/1010733i workspace 324.6G/45274246i | repeat-01 collected 26/26 workers (60617 items) tests 20927 done 1 failed | 26 in flight, oldest 72s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.................... [967%]
........................................................................ [971%]
........................................................................ [974%]
........................................................................ [977%]
................................................[contention-diag] +2848s soak 41p/290t rss 13.0G pss 12.0G swap 0.6G majflt 2045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 13 descendant rss 0.2G pss 0.1G | host avail 30.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 0.57 cpu 30.7 | cgroup 13.4G/max oom_kill 0 | free scratch 324.6G/45273276i tmp 29.4G/1010733i workspace 324.6G/45273277i | repeat-01 collected 26/26 workers (60617 items) tests 21211 done 1 failed | 26 in flight, oldest 55s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
........................ [981%]
........................................................................ [984%]
........................................................................ [987%]
........................................................................ [991%]
........................................................................ [994%]
..........................................[contention-diag] +2864s soak 35p/265t rss 13.0G pss 12.0G swap 0.7G majflt 2048 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 30.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.11 cpu 28.51 | cgroup 13.5G/max oom_kill 0 | free scratch 324.6G/45272228i tmp 29.4G/1010733i workspace 324.6G/45272228i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 21525 done 1 failed | 26 in flight, oldest 48s gw9 tests/ace/tui/test_projects_pane.py::test_projects_help_opens_from_list_and_inventory
.............................. [997%]
...............................s........................................ [1001%]
......................................s................................. [1004%]
...................................................................[contention-diag] +2881s soak 37p/230t rss 13.1G pss 12.0G swap 0.7G majflt 2051 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 9 descendant rss 0.3G pss 0.1G | host avail 30.5G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.07 cpu 29.57 | cgroup 13.5G/max oom_kill 0 | free scratch 324.6G/45270087i tmp 29.4G/1010733i workspace 324.6G/45270087i | repeat-01 collected 26/26 workers (60617 items) tests 21790 done 1 failed | 26 in flight, oldest 46s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
..... [1007%]
........................................................................ [1010%]
.....................................................[contention-diag] +2896s soak 45p/257t rss 13.0G pss 12.0G swap 0.7G majflt 2055 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 17 descendant rss 0.2G pss 0.1G | host avail 31.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 37.62 | cgroup 13.5G/max oom_kill 0 | free scratch 324.6G/45269390i tmp 29.4G/1010733i workspace 324.6G/45269390i | repeat-01 collected 26/26 workers (60617 items) tests 21937 done 1 failed | 26 in flight, oldest 61s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
................... [1014%]
........................................................................ [1017%]
........................................................................ [1020%]
........................................................................ [1024%]
..........................................................[contention-diag] +2912s soak 34p/217t rss 13.0G pss 11.9G swap 0.7G majflt 2055 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 6 descendant rss 0.2G pss 0.1G | host avail 29.5G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 33.72 | cgroup 13.4G/max oom_kill 0 | free scratch 324.6G/45270269i tmp 29.4G/1010733i workspace 324.6G/45270269i | repeat-01 collected 26/26 workers (60617 items) tests 22200 done 1 failed | 26 in flight, oldest 69s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.............. [1027%]
........................................................................ [1030%]
........................................................................ [1034%]
........................................................................ [1037%]
.............................................................[contention-diag] +2927s soak 39p/229t rss 13.1G pss 12.1G swap 0.7G majflt 2063 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 11 descendant rss 0.3G pss 0.2G | host avail 28.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 27.7 | cgroup 13.6G/max oom_kill 0 | free scratch 324.6G/45269597i tmp 29.4G/1010733i workspace 324.6G/45269597i | repeat-01 collected 26/26 workers (60617 items) tests 22521 done 1 failed | 26 in flight, oldest 85s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
........... [1040%]
........................................................................ [1044%]
........................................................................ [1047%]
........................................................................ [1050%]
........................................................................ [1054%]
......[contention-diag] +2942s soak 36p/231t rss 13.1G pss 12.1G swap 0.7G majflt 2067 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 8 descendant rss 0.3G pss 0.2G | host avail 31.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 30.49 | cgroup 13.6G/max oom_kill 0 | free scratch 324.6G/45268602i tmp 29.4G/1010733i workspace 324.6G/45268602i | repeat-01 collected 26/26 workers (60617 items) tests 22811 done 1 failed | 25 in flight, oldest 100s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.................................................................. [1057%]
........................................................................ [1060%]
........................................................................ [1064%]
........................................................................ [1067%]
........................................................................ [1070%]
.........................................[contention-diag] +2958s soak 36p/193t rss 13.1G pss 12.1G swap 0.7G majflt 2071 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 8 descendant rss 0.3G pss 0.2G | host avail 31.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 35.38 | cgroup 13.6G/max oom_kill 0 | free scratch 324.6G/45267457i tmp 29.4G/1010733i workspace 324.6G/45267457i | repeat-01 collected 26/26 workers (60617 items) tests 23197 done 1 failed | 26 in flight, oldest 115s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............................... [1074%]
........................................................................ [1077%]
........................................................................ [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
............................................[contention-diag] +2973s soak 38p/194t rss 13.1G pss 12.1G swap 0.6G majflt 2072 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 10 descendant rss 0.3G pss 0.2G | host avail 30.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 34.38 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45266707i tmp 29.4G/1010733i workspace 324.6G/45266707i | repeat-01 collected 26/26 workers (60617 items) tests 23567 done 1 failed | 25 in flight, oldest 65s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
............................ [1090%]
........................................................................ [1094%]
........................................................................ [1097%]
........................................................................ [1100%]
........................................................................ [1104%]
..[contention-diag] +2988s soak 39p/184t rss 13.1G pss 12.1G swap 0.6G majflt 2082 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 11 descendant rss 0.2G pss 0.2G | host avail 28.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 25.83 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45265809i tmp 29.4G/1010733i workspace 324.6G/45265809i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 23866 done 1 failed | 26 in flight, oldest 80s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
...................................................................... [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
........................................................................ [1117%]
........................................................................ [1120%]
........................................................................ [1124%]
...........................[contention-diag] +3006s soak 41p/198t rss 13.3G pss 12.1G swap 0.7G majflt 2084 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 13 descendant rss 0.4G pss 0.2G | host avail 32.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 30.41 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45264580i tmp 29.4G/1010733i workspace 324.6G/45264580i | repeat-01 collected 26/26 workers (60617 items) tests 24341 done 1 failed | 26 in flight, oldest 94s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
............................................. [1127%]
........................................................................ [1130%]
........................................................................ [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
.[contention-diag] +3021s soak 36p/190t rss 13.2G pss 12.2G swap 0.7G majflt 2260 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 8 descendant rss 0.3G pss 0.2G | host avail 32.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 35.13 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45263541i tmp 29.4G/1010733i workspace 324.6G/45263541i | repeat-01 collected 26/26 workers (60617 items) tests 24695 done 1 failed | 26 in flight, oldest 109s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
....................................................................... [1144%]
........................................................................ [1147%]
................................[contention-diag] +3036s soak 36p/192t rss 13.1G pss 12.0G swap 0.6G majflt 2089 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 8 descendant rss 0.1G pss 0.0G | host avail 31.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 32.23 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45262876i tmp 29.4G/1010733i workspace 324.6G/45262876i | repeat-01 collected 26/26 workers (60617 items) tests 24847 done 1 failed | 26 in flight, oldest 124s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................ [1150%]
........................................................................ [1153%]
........................................................................ [1157%]
........................................................................ [1160%]
...................[contention-diag] +3052s soak 32p/177t rss 13.0G pss 12.0G swap 0.6G majflt 2093 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 4 descendant rss 0.1G pss 0.0G | host avail 31.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 25.38 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45261912i tmp 29.4G/1010733i workspace 324.6G/45261912i | repeat-01 collected 26/26 workers (60617 items) tests 25130 done 1 failed | 25 in flight, oldest 140s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..................................................... [1163%]
........................................................................ [1167%]
............................s........................................... [1170%]
........................................................................ [1173%]
........................................................................ [1177%]
.....................[contention-diag] +3067s soak 32p/178t rss 13.0G pss 12.0G swap 0.6G majflt 2095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 4 descendant rss 0.0G pss 0.0G | host avail 32.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 32.85 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45261160i tmp 29.4G/1010733i workspace 324.6G/45261160i | repeat-01 collected 26/26 workers (60617 items) tests 25506 done 1 failed | 25 in flight, oldest 155s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................... [1180%]
........................................................................ [1183%]
........................................[contention-diag] +3082s soak 40p/186t rss 13.0G pss 12.0G swap 0.6G majflt 2095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 12 descendant rss 0.1G pss 0.0G | host avail 32.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 37.83 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45260797i tmp 29.4G/1010733i workspace 324.6G/45260797i | repeat-01 collected 26/26 workers (60617 items) tests 25671 done 1 failed | 26 in flight, oldest 170s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................ [1187%]
........................................................................ [1190%]
........................................................................ [1193%]
.........................[contention-diag] +3098s soak 31p/176t rss 13.0G pss 12.0G swap 0.6G majflt 2105 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 3 descendant rss 0.1G pss 0.0G | host avail 31.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 33.89 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45260140i tmp 29.4G/1010731i workspace 324.6G/45260140i | repeat-01 collected 26/26 workers (60617 items) tests 25857 done 1 failed | 25 in flight, oldest 186s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................... [1197%]
........................................................................ [1200%]
........................................................................ [1203%]
...........................................................[contention-diag] +3113s soak 35p/174t rss 13.1G pss 12.0G swap 0.6G majflt 2112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 31.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 26.67 | cgroup 13.8G/max oom_kill 0 | free scratch 324.6G/45260324i tmp 29.4G/1010733i workspace 324.6G/45260324i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 26103 done 1 failed | 25 in flight, oldest 201s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............. [1207%]
........................................................................ [1210%]
.....[contention-diag] +3130s soak 37p/174t rss 13.1G pss 12.1G swap 0.6G majflt 2112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 9 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 32.6 | cgroup 13.7G/max oom_kill 0 | free scratch 324.6G/45260170i tmp 29.4G/1010733i workspace 324.6G/45260170i | repeat-01 collected 26/26 workers (60617 items) tests 26210 done 1 failed | 25 in flight, oldest 218s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................................... [1213%]
........................................................................ [1217%]
........................................................................ [1220%]
........................................................................ [1223%]
................................................................[contention-diag] +3146s soak 37p/170t rss 13.1G pss 12.1G swap 0.6G majflt 2112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 9 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 42.84 | cgroup 13.8G/max oom_kill 0 | free scratch 324.6G/45259224i tmp 29.4G/1010733i workspace 324.6G/45259224i | repeat-01 collected 26/26 workers (60617 items) tests 26543 done 1 failed | 23 in flight, oldest 234s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........ [1227%]
........................................................................ [1230%]
........................................................................ [1233%]
........................................................................ [1237%]
........................................................................ [1240%]
.............................[contention-diag] +3161s soak 37p/165t rss 13.2G pss 12.1G swap 0.6G majflt 2112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 9 descendant rss 0.2G pss 0.1G | host avail 31.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 37.28 | cgroup 13.8G/max oom_kill 0 | free scratch 324.6G/45258192i tmp 29.4G/1010733i workspace 324.6G/45258191i | repeat-01 collected 26/26 workers (60617 items) tests 26882 done 1 failed | 25 in flight, oldest 249s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................... [1243%]
........................................................................ [1247%]
........................................................................ [1250%]
........................................................................ [1253%]
..................................................[contention-diag] +3176s soak 34p/169t rss 13.2G pss 12.2G swap 0.7G majflt 2112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.7G, 6 descendant rss 0.2G pss 0.2G | host avail 30.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.08 cpu 28.81 | cgroup 13.9G/max oom_kill 0 | free scratch 324.5G/45257181i tmp 29.4G/1010733i workspace 324.5G/45257181i | repeat-01 collected 26/26 workers (60617 items) tests 27188 done 1 failed | 25 in flight, oldest 117s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................... [1257%]
........................................................................ [1260%]
........................................................................ [1263%]
[contention-diag] +3192s soak 37p/175t rss 13.3G pss 12.2G swap 0.6G majflt 2112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.2G pss 0.2G | host avail 29.9G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.01 cpu 27.53 | cgroup 13.9G/max oom_kill 0 | free scratch 324.5G/45256616i tmp 29.4G/1010733i workspace 324.5G/45256616i | repeat-01 collected 26/26 workers (60617 items) tests 27343 done 1 failed | 25 in flight, oldest 132s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................................ [1267%]
........................................................................ [1270%]
........................................................................ [1273%]
........................................................................ [1277%]
........................................................................ [1280%]
..................................................[contention-diag] +3207s soak 38p/176t rss 13.3G pss 12.2G swap 0.6G majflt 2114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 10 descendant rss 0.3G pss 0.2G | host avail 30.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 32.79 | cgroup 13.9G/max oom_kill 0 | free scratch 324.5G/45255441i tmp 29.4G/1010733i workspace 324.5G/45255441i | repeat-01 collected 26/26 workers (60617 items) tests 27761 done 1 failed | 25 in flight, oldest 148s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................... [1283%]
........................................................................ [1287%]
........................................................................ [1290%]
........................................................................ [1293%]
........................................................................ [1296%]
........................................................................ [1300%]
.............[contention-diag] +3222s soak 32p/172t rss 13.2G pss 12.1G swap 0.6G majflt 2114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 4 descendant rss 0.1G pss 0.0G | host avail 30.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 29.87 | cgroup 13.9G/max oom_kill 0 | free scratch 324.5G/45254411i tmp 29.4G/1010731i workspace 324.5G/45254411i | repeat-01 collected 26/26 workers (60617 items) tests 28159 done 1 failed | 25 in flight, oldest 163s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................... [1303%]
........................................................................ [1306%]
........................................................................ [1310%]
...............................................................[contention-diag] +3238s soak 34p/185t rss 13.3G pss 12.1G swap 0.6G majflt 2117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 6 descendant rss 0.2G pss 0.1G | host avail 31.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 23.41 | cgroup 14.0G/max oom_kill 0 | free scratch 324.5G/45253777i tmp 29.4G/1010733i workspace 324.5G/45253777i | scratch used 0.6G in 107326 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 28366 done 1 failed | 24 in flight, oldest 178s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
......... [1313%]
........................................................................ [1316%]
........................................................................ [1320%]
.......................................................[contention-diag] +3255s soak 36p/176t rss 13.3G pss 12.2G swap 0.6G majflt 2117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 8 descendant rss 0.2G pss 0.1G | host avail 30.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 29.39 | cgroup 14.0G/max oom_kill 0 | free scratch 324.5G/45252358i tmp 29.4G/1010733i workspace 324.5G/45252358i | repeat-01 collected 26/26 workers (60617 items) tests 28620 done 1 failed | 25 in flight, oldest 196s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................. [1323%]
........................................................................ [1326%]
........................................................................ [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
..........................................[contention-diag] +3271s soak 33p/169t rss 13.1G pss 12.1G swap 0.6G majflt 2119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 5 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 35.17 | cgroup 13.8G/max oom_kill 0 | free scratch 324.5G/45251877i tmp 29.4G/1010733i workspace 324.5G/45251877i | repeat-01 collected 26/26 workers (60617 items) tests 28977 done 1 failed | 25 in flight, oldest 211s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................. [1340%]
........................................................................ [1343%]
........................................................................ [1346%]
........................................................................ [1350%]
........................................................................ [1353%]
.............[contention-diag] +3286s soak 35p/170t rss 13.2G pss 12.1G swap 0.6G majflt 2127 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 7 descendant rss 0.1G pss 0.1G | host avail 31.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.88 cpu 32.78 | cgroup 13.9G/max oom_kill 0 | free scratch 324.5G/45250872i tmp 29.4G/1010729i workspace 324.5G/45250872i | repeat-01 collected 26/26 workers (60617 items) tests 29286 done 1 failed | 25 in flight, oldest 226s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................... [1356%]
........................................................................ [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
............................[contention-diag] +3301s soak 35p/174t rss 13.3G pss 12.2G swap 0.6G majflt 2129 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 7 descendant rss 0.2G pss 0.1G | host avail 28.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.35 cpu 23.26 | cgroup 14.0G/max oom_kill 0 | free scratch 324.5G/45249873i tmp 29.4G/1010731i workspace 324.5G/45249873i | repeat-01 collected 26/26 workers (60617 items) tests 29613 done 1 failed | 23 in flight, oldest 242s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................ [1370%]
........................................................................ [1373%]
........................................................................ [1376%]
........................................................................ [1380%]
...............................[contention-diag] +3317s soak 34p/165t rss 13.3G pss 12.2G swap 0.6G majflt 2129 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 6 descendant rss 0.2G pss 0.1G | host avail 29.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.04 cpu 21.22 | cgroup 14.1G/max oom_kill 0 | free scratch 324.5G/45248722i tmp 29.4G/1010731i workspace 324.5G/45248722i | repeat-01 collected 26/26 workers (60617 items) tests 29904 done 1 failed | 25 in flight, oldest 257s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
......................................... [1383%]
........................................................................ [1386%]
........................................................................ [1390%]
........................................................................ [1393%]
..........[contention-diag] +3332s soak 35p/165t rss 13.3G pss 12.2G swap 0.6G majflt 2130 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 7 descendant rss 0.2G pss 0.1G | host avail 29.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.15 cpu 21.57 | cgroup 14.0G/max oom_kill 0 | free scratch 324.5G/45248202i tmp 29.4G/1010731i workspace 324.5G/45248202i | repeat-01 collected 26/26 workers (60617 items) tests 30152 done 1 failed | 25 in flight, oldest 273s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................................................. [1396%]
........................................................................ [1400%]
........................................................................ [1403%]
........................................................................ [1406%]
....................................................[contention-diag] +3348s soak 32p/159t rss 13.3G pss 12.2G swap 0.6G majflt 2130 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 28.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.97 cpu 18.96 | cgroup 14.0G/max oom_kill 0 | free scratch 324.5G/45247184i tmp 29.4G/1010731i workspace 324.5G/45247184i | repeat-01 collected 26/26 workers (60617 items) tests 30501 done 1 failed | 25 in flight, oldest 288s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................... [1410%]
........................................................................ [1413%]
........................................................................ [1416%]
........................................................................ [1420%]
...........................................[contention-diag] +3363s soak 32p/171t rss 13.2G pss 12.2G swap 0.6G majflt 2133 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 27.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.65 cpu 18.25 | cgroup 14.0G/max oom_kill 0 | free scratch 324.5G/45246195i tmp 29.4G/1010731i workspace 324.5G/45246195i | scratch used 1.0G in 184662 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 30761 done 1 failed | 25 in flight, oldest 303s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................. [1423%]
........................................................................ [1426%]
........................................................................ [1430%]
.....................................[contention-diag] +3380s soak 32p/171t rss 13.3G pss 12.0G swap 0.6G majflt 2134 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.6G, 4 descendant rss 0.1G pss 0.1G | host avail 28.9G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.95 cpu 24.82 | cgroup 14.0G/max oom_kill 0 | free scratch 324.9G/45267774i tmp 29.4G/1010731i workspace 324.9G/45267774i | repeat-01 collected 26/26 workers (60617 items) tests 30993 done 1 failed | 25 in flight, oldest 321s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................... [1433%]
........................................................................ [1436%]
........................................................................ [1440%]
........................................................................ [1443%]
........................................................................ [1446%]
........................................................................ [1449%]
....[contention-diag] +3396s soak 32p/183t rss 13.3G pss 12.2G swap 0.6G majflt 2143 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 29.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 1.08/1.08 io 2.61 cpu 23.09 | cgroup 14.0G/max oom_kill 0 | free scratch 324.7G/45254885i tmp 29.4G/1010731i workspace 324.7G/45254886i | repeat-01 collected 26/26 workers (60617 items) tests 31391 done 1 failed | 25 in flight, oldest 336s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................................................................... [1453%]
........................................................................ [1456%]
........................................................................ [1459%]
........................................................................ [1463%]
........................................................................ [1466%]
........................................................................ [1469%]
....................................[contention-diag] +3411s soak 32p/155t rss 13.3G pss 12.2G swap 0.6G majflt 2145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 27.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 2.59 cpu 19.96 | cgroup 14.0G/max oom_kill 0 | free scratch 324.7G/45253917i tmp 29.4G/1010731i workspace 324.7G/45253917i | repeat-01 collected 26/26 workers (60617 items) tests 31852 done 1 failed | 25 in flight, oldest 275s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.................................... [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1483%]
........................................................................ [1486%]
....................................[contention-diag] +3426s soak 34p/166t rss 13.3G pss 12.2G swap 0.6G majflt 2145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 6 descendant rss 0.1G pss 0.1G | host avail 27.5G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 1.12/1.12 io 3.37 cpu 19.74 | cgroup 14.0G/max oom_kill 0 | free scratch 324.7G/45252714i tmp 29.4G/1010731i workspace 324.7G/45252714i | repeat-01 collected 26/26 workers (60617 items) tests 32217 done 1 failed | 25 in flight, oldest 290s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.................................... [1489%]
........................................................................ [1493%]
........................................................................ [1496%]
........................................................................ [1499%]
.........[contention-diag] +3442s soak 33p/177t rss 13.4G pss 12.3G swap 0.6G majflt 2146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 5 descendant rss 0.2G pss 0.2G | host avail 29.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.22/0.22 io 4.05 cpu 27.57 | cgroup 14.1G/max oom_kill 0 | free scratch 324.7G/45253047i tmp 29.4G/1010731i workspace 324.7G/45253047i | repeat-01 collected 26/26 workers (60617 items) tests 32471 done 1 failed | 24 in flight, oldest 305s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................................................... [1503%]
........................................................................ [1506%]
........................................................................ [1509%]
........................................................................ [1513%]
........................................................................ [1516%]
........................................................................ [1519%]
..............................[contention-diag] +3457s soak 31p/172t rss 13.3G pss 12.2G swap 0.6G majflt 2146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 3 descendant rss 0.1G pss 0.0G | host avail 29.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 3.24 cpu 26.51 | cgroup 14.0G/max oom_kill 0 | free scratch 324.7G/45251571i tmp 29.4G/1010731i workspace 324.7G/45251571i | repeat-01 collected 26/26 workers (60617 items) tests 32907 done 1 failed | 23 in flight, oldest 321s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.......................................... [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1533%]
........................................................................ [1536%]
........................................................................ [1539%]
......................................[contention-diag] +3472s soak 39p/176t rss 13.4G pss 12.3G swap 0.6G majflt 2201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 11 descendant rss 0.2G pss 0.1G | host avail 28.5G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.27/0.27 io 3.2 cpu 24.8 | cgroup 14.2G/max oom_kill 0 | free scratch 324.7G/45249987i tmp 29.4G/1010731i workspace 324.7G/45249987i | repeat-01 collected 26/26 workers (60617 items) tests 33353 done 1 failed | 24 in flight, oldest 336s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.................................. [1543%]
........................................................................ [1546%]
........................................................................ [1549%]
...............................................................[contention-diag] +3488s soak 35p/159t rss 13.4G pss 12.3G swap 0.6G majflt 2202 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 7 descendant rss 0.2G pss 0.2G | host avail 27.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 2.11 cpu 18.11 | cgroup 14.5G/max oom_kill 0 | free scratch 324.4G/45247868i tmp 29.4G/1010731i workspace 324.4G/45247868i | scratch used 0.3G in 54973 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 33573 done 1 failed | 24 in flight, oldest 352s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
......... [1553%]
........................................................................ [1556%]
........................................................................ [1559%]
.................[contention-diag] +3505s soak 34p/160t rss 13.4G pss 12.3G swap 0.6G majflt 2203 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 6 descendant rss 0.2G pss 0.1G | host avail 28.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.06 cpu 18.84 | cgroup 14.3G/max oom_kill 0 | free scratch 324.0G/45246635i tmp 29.4G/1010731i workspace 324.0G/45246635i | repeat-01 collected 26/26 workers (60617 items) tests 33782 done 1 failed | 24 in flight, oldest 369s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
....................................................... [1563%]
........................................................................ [1566%]
........................................................................ [1569%]
........................................................................ [1573%]
........................................................................ [1576%]
...........................[contention-diag] +3520s soak 38p/171t rss 13.5G pss 12.3G swap 0.6G majflt 2204 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 10 descendant rss 0.2G pss 0.2G | host avail 27.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 2.96 cpu 19.7 | cgroup 14.3G/max oom_kill 0 | free scratch 323.9G/45245602i tmp 29.4G/1010731i workspace 323.9G/45245602i | repeat-01 collected 26/26 workers (60617 items) tests 34146 done 1 failed | 24 in flight, oldest 384s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................................. [1579%]
........................................................................ [1583%]
............................................................s........... [1586%]
......................[contention-diag] +3536s soak 36p/173t rss 13.6G pss 12.5G swap 0.7G majflt 2204 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 8 descendant rss 0.3G pss 0.3G | host avail 24.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.56 cpu 19.57 | cgroup 14.5G/max oom_kill 0 | free scratch 323.9G/45245044i tmp 29.4G/1010731i workspace 323.9G/45245044i | repeat-01 collected 26/26 workers (60617 items) tests 34362 done 1 failed | 23 in flight, oldest 400s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.................................................. [1589%]
........................................................................ [1592%]
.........................[contention-diag] +3551s soak 32p/165t rss 13.5G pss 12.4G swap 0.7G majflt 2204 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 4 descendant rss 0.3G pss 0.2G | host avail 22.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.11/0.04 io 2.14 cpu 19.01 | cgroup 14.4G/max oom_kill 0 | free scratch 323.9G/45244925i tmp 29.4G/1010731i workspace 323.9G/45244925i | repeat-01 collected 26/26 workers (60617 items) tests 34511 done 1 failed | 24 in flight, oldest 415s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................................... [1596%]
........................................................................ [1599%]
........................................................................ [1602%]
.................................................[contention-diag] +3567s soak 37p/170t rss 13.3G pss 12.2G swap 0.6G majflt 2205 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.1G pss 0.0G | host avail 25.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.06 io 4.51 cpu 22.94 | cgroup 14.2G/max oom_kill 0 | free scratch 323.9G/45243983i tmp 29.4G/1010731i workspace 323.9G/45243983i | repeat-01 collected 26/26 workers (60617 items) tests 34736 done 1 failed | 24 in flight, oldest 431s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
....................... [1606%]
........................................................................ [1609%]
........................................................................ [1612%]
........................................................................ [1616%]
........................................................................ [1619%]
........................................................................ [1622%]
.............................................[contention-diag] +3582s soak 35p/168t rss 13.5G pss 12.4G swap 0.6G majflt 2216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.2G pss 0.2G | host avail 24.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.05 cpu 19.24 | cgroup 14.3G/max oom_kill 0 | free scratch 323.6G/45243092i tmp 29.4G/1010731i workspace 323.6G/45243092i | repeat-01 collected 26/26 workers (60617 items) tests 35160 done 1 failed | 23 in flight, oldest 446s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
........................... [1626%]
........................................................................ [1629%]
........................................................................ [1632%]
........................................................................ [1636%]
........................................................................ [1639%]
........................................................................ [1642%]
...............[contention-diag] +3597s soak 31p/172t rss 13.4G pss 12.3G swap 0.6G majflt 2216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.1G pss 0.1G | host avail 27.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.37 cpu 20.53 | cgroup 14.2G/max oom_kill 0 | free scratch 322.4G/45241823i tmp 29.4G/1010731i workspace 322.4G/45241823i | repeat-01 collected 26/26 workers (60617 items) tests 35565 done 1 failed | 24 in flight, oldest 306s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
......................................................... [1646%]
........................................................................ [1649%]
........................................................................ [1652%]
...................[contention-diag] +3613s soak 33p/185t rss 13.4G pss 12.3G swap 0.6G majflt 2217 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 26.1G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.86/0.86 io 1.56 cpu 20.56 | cgroup 14.2G/max oom_kill 0 | free scratch 322.9G/45241114i tmp 29.4G/1010731i workspace 322.9G/45241114i | scratch used 0.5G in 88897 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 35771 done 1 failed | 24 in flight, oldest 321s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
..................................................... [1656%]
........................................................................ [1659%]
........................................................................ [1662%]
........................................................................ [1666%]
........................................................................ [1669%]
......................................[contention-diag] +3630s soak 32p/185t rss 13.5G pss 12.4G swap 0.6G majflt 2217 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 29.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 2.7 cpu 26.6 | cgroup 14.3G/max oom_kill 0 | free scratch 322.9G/45239873i tmp 29.4G/1010731i workspace 322.9G/45239873i | repeat-01 collected 26/26 workers (60617 items) tests 36167 done 1 failed | 24 in flight, oldest 339s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.................................. [1672%]
........................................................................ [1676%]
........................................................................ [1679%]
........................................................................ [1682%]
........................................................................ [1686%]
........................................................................ [1689%]
......[contention-diag] +3646s soak 32p/185t rss 13.4G pss 12.3G swap 0.6G majflt 2217 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 3.63 cpu 25.78 | cgroup 14.2G/max oom_kill 0 | free scratch 322.9G/45238766i tmp 29.4G/1010730i workspace 322.9G/45238766i | repeat-01 collected 26/26 workers (60617 items) tests 36563 done 1 failed | 24 in flight, oldest 354s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.................................................................. [1692%]
........................................................................ [1696%]
........................................................................ [1699%]
............................................[contention-diag] +3661s soak 32p/180t rss 13.4G pss 12.3G swap 0.6G majflt 2217 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 25.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.7 cpu 20.47 | cgroup 14.3G/max oom_kill 0 | free scratch 322.8G/45237407i tmp 29.4G/1010731i workspace 322.8G/45237407i | repeat-01 collected 26/26 workers (60617 items) tests 36828 done 1 failed | 23 in flight, oldest 369s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1702%]
........................................................................ [1706%]
........................................................................ [1709%]
........................................................................ [1712%]
........................................................................ [1716%]
.........[contention-diag] +3676s soak 33p/177t rss 13.4G pss 12.3G swap 0.6G majflt 2217 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 24.5G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.96 cpu 19.58 | cgroup 14.2G/max oom_kill 0 | free scratch 322.8G/45236249i tmp 29.4G/1010731i workspace 322.8G/45236249i | repeat-01 collected 26/26 workers (60617 items) tests 37154 done 1 failed | 23 in flight, oldest 385s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................................................... [1719%]
........................................................................ [1722%]
........................................................................ [1726%]
........................................................................ [1729%]
........................................................................ [1732%]
.................[contention-diag] +3692s soak 36p/173t rss 13.4G pss 12.3G swap 0.7G majflt 2219 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 8 descendant rss 0.1G pss 0.1G | host avail 25.5G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.5 cpu 16.76 | cgroup 14.2G/max oom_kill 0 | free scratch 322.5G/45235474i tmp 29.4G/1010731i workspace 322.5G/45235474i | repeat-01 collected 26/26 workers (60617 items) tests 37529 done 1 failed | 23 in flight, oldest 400s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
....................................................... [1735%]
........................................................................ [1739%]
........................................................................ [1742%]
........................................................................ [1745%]
..........................................................[contention-diag] +3707s soak 34p/187t rss 13.4G pss 12.3G swap 0.6G majflt 2247 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 6 descendant rss 0.1G pss 0.1G | host avail 29.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.99 cpu 19.54 | cgroup 14.3G/max oom_kill 0 | free scratch 322.4G/45234225i tmp 29.4G/1010731i workspace 322.4G/45234225i | repeat-01 collected 26/26 workers (60617 items) tests 37856 done 1 failed | 24 in flight, oldest 416s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.............. [1749%]
........................................................................ [1752%]
........................................................................ [1755%]
........................................................................ [1759%]
........................................................................ [1762%]
...............[contention-diag] +3722s soak 37p/192t rss 13.5G pss 12.4G swap 0.6G majflt 2252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 9 descendant rss 0.2G pss 0.1G | host avail 29.1G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.07 cpu 20.66 | cgroup 14.4G/max oom_kill 0 | free scratch 322.4G/45233709i tmp 29.4G/1010731i workspace 322.4G/45233709i | repeat-01 collected 26/26 workers (60617 items) tests 38161 done 1 failed | 24 in flight, oldest 431s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...........s....................s........................ [1765%]
........................................................................ [1769%]
.....................................s.................................. [1772%]
........................................................................ [1775%]
...........................[contention-diag] +3738s soak 36p/203t rss 13.6G pss 12.4G swap 0.7G majflt 2315 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 8 descendant rss 0.2G pss 0.2G | host avail 27.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.57 cpu 18.7 | cgroup 14.5G/max oom_kill 0 | free scratch 322.4G/45232420i tmp 29.4G/1010731i workspace 322.4G/45232420i | scratch used 0.8G in 160579 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 38454 done 1 failed | 24 in flight, oldest 299s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................. [1779%]
........................................................................ [1782%]
....[contention-diag] +3755s soak 40p/202t rss 13.8G pss 12.6G swap 0.7G majflt 2385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 12 descendant rss 0.5G pss 0.4G | host avail 25.6G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.14 cpu 20.48 | cgroup 14.7G/max oom_kill 0 | free scratch 322.3G/45232260i tmp 29.4G/1010731i workspace 322.3G/45232260i | repeat-01 collected 26/26 workers (60617 items) tests 38590 done 1 failed | 24 in flight, oldest 317s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................................................................... [1785%]
........................................................................ [1789%]
........................................................................ [1792%]
........................................................................ [1795%]
........................................................................ [1799%]
............[contention-diag] +3770s soak 33p/192t rss 13.7G pss 12.5G swap 0.7G majflt 2385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 5 descendant rss 0.4G pss 0.3G | host avail 26.1G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 20.52 | cgroup 14.7G/max oom_kill 0 | free scratch 322.3G/45231313i tmp 29.4G/1010731i workspace 322.3G/45231313i | repeat-01 collected 26/26 workers (60617 items) tests 38962 done 1 failed | 24 in flight, oldest 332s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................................ [1802%]
........................................................................ [1805%]
................................[contention-diag] +3786s soak 40p/191t rss 13.7G pss 12.5G swap 0.7G majflt 2403 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 12 descendant rss 0.4G pss 0.3G | host avail 24.0G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.2/0.12 io 1.78 cpu 18.02 | cgroup 14.7G/max oom_kill 0 | free scratch 322.3G/45230892i tmp 29.4G/1010731i workspace 322.3G/45230892i | repeat-01 collected 26/26 workers (60617 items) tests 39118 done 1 failed | 24 in flight, oldest 347s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........................................ [1809%]
........................................................................ [1812%]
........................................................................ [1815%]
........................................................................ [1819%]
........................................................................ [1822%]
........................................................................ [1825%]
..[contention-diag] +3801s soak 37p/203t rss 13.8G pss 12.5G swap 0.7G majflt 2430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 9 descendant rss 0.4G pss 0.3G | host avail 24.3G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.02 io 3.09 cpu 21.63 | cgroup 14.7G/max oom_kill 0 | free scratch 322.3G/45229907i tmp 29.4G/1010728i workspace 322.3G/45229907i | repeat-01 collected 26/26 workers (60617 items) tests 39506 done 1 failed | 24 in flight, oldest 363s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
...................................................................... [1829%]
........................................................................ [1832%]
...............................................................[contention-diag] +3817s soak 32p/178t rss 13.6G pss 12.4G swap 0.7G majflt 2437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 4 descendant rss 0.2G pss 0.2G | host avail 24.9G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.12 cpu 23.07 | cgroup 14.7G/max oom_kill 0 | free scratch 322.3G/45229244i tmp 29.4G/1010728i workspace 322.3G/45229244i | repeat-01 collected 26/26 workers (60617 items) tests 39730 done 1 failed | 24 in flight, oldest 378s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
......... [1835%]
........................................................................ [1839%]
........................................................................ [1842%]
........................................................................ [1845%]
........................................................................ [1849%]
...............................................[contention-diag] +3832s soak 36p/184t rss 13.6G pss 12.4G swap 0.7G majflt 2452 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 8 descendant rss 0.2G pss 0.2G | host avail 23.0G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.52 cpu 18.24 | cgroup 15.2G/max oom_kill 0 | free scratch 322.0G/45228186i tmp 29.4G/1010728i workspace 322.0G/45228186i | repeat-01 collected 26/26 workers (60617 items) tests 40066 done 1 failed | 23 in flight, oldest 394s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
......................... [1852%]
........................................................................ [1855%]
........................................................................ [1859%]
.................................................................[contention-diag] +3848s soak 40p/203t rss 13.7G pss 12.5G swap 0.7G majflt 2466 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 12 descendant rss 0.4G pss 0.3G | host avail 22.9G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.32/0.26 io 3.87 cpu 15.37 | cgroup 15.3G/max oom_kill 0 | free scratch 321.4G/45227316i tmp 29.4G/1010728i workspace 321.4G/45227316i | repeat-01 collected 26/26 workers (60617 items) tests 40303 done 1 failed | 24 in flight, oldest 409s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....... [1862%]
........................................................................ [1865%]
........................................................................ [1869%]
..........................................s............................. [1872%]
........................................................................ [1875%]
........................................................................ [1878%]
....[contention-diag] +3863s soak 39p/193t rss 13.8G pss 12.5G swap 0.7G majflt 2502 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 11 descendant rss 0.4G pss 0.3G | host avail 28.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.05 io 4.0 cpu 17.35 | cgroup 14.9G/max oom_kill 0 | free scratch 322.0G/45226105i tmp 29.4G/1010728i workspace 322.0G/45226105i | scratch used 0.9G in 179056 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 40654 done 1 failed | 24 in flight, oldest 424s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................................................................... [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
...[contention-diag] +3880s soak 52p/206t rss 13.9G pss 12.6G swap 0.7G majflt 2514 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 24 descendant rss 0.5G pss 0.4G | host avail 28.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.87 cpu 20.02 | cgroup 14.9G/max oom_kill 0 | free scratch 321.8G/45214787i tmp 29.4G/1010728i workspace 321.8G/45214787i | repeat-01 collected 26/26 workers (60617 items) tests 40884 done 1 failed | 24 in flight, oldest 442s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..................................................................... [1892%]
........................................................................ [1895%]
........................................................................ [1898%]
........................................................................ [1902%]
........................................................................ [1905%]
.[contention-diag] +3896s soak 37p/184t rss 13.8G pss 12.5G swap 0.7G majflt 2532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 9 descendant rss 0.4G pss 0.3G | host avail 27.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.07 cpu 15.83 | cgroup 14.8G/max oom_kill 0 | free scratch 321.7G/45214055i tmp 29.4G/1010728i workspace 321.7G/45214055i | repeat-01 collected 26/26 workers (60617 items) tests 41224 done 1 failed | 24 in flight, oldest 223s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
....................................................................... [1908%]
........................................................................ [1912%]
........................................................................ [1915%]
........................................................................ [1918%]
...................................................[contention-diag] +3911s soak 34p/182t rss 13.8G pss 12.6G swap 0.7G majflt 2543 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 6 descendant rss 0.4G pss 0.3G | host avail 27.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.2 cpu 14.31 | cgroup 14.9G/max oom_kill 0 | free scratch 321.7G/45212153i tmp 29.4G/1010728i workspace 321.7G/45212153i | repeat-01 collected 26/26 workers (60617 items) tests 41576 done 1 failed | 24 in flight, oldest 239s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
..................... [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
........................................................................ [1935%]
........................................................................ [1938%]
...............................[contention-diag] +3926s soak 37p/174t rss 13.8G pss 12.6G swap 0.7G majflt 2585 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.4G pss 0.4G | host avail 27.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.28 cpu 15.82 | cgroup 15.0G/max oom_kill 0 | free scratch 321.7G/45210680i tmp 29.4G/1010728i workspace 321.7G/45210680i | repeat-01 collected 26/26 workers (60617 items) tests 42000 done 1 failed | 23 in flight, oldest 254s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
......................................... [1942%]
........................................................................ [1945%]
........................................................................ [1948%]
........................................................................ [1952%]
................................[contention-diag] +3942s soak 36p/187t rss 13.9G pss 12.7G swap 0.8G majflt 2591 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 8 descendant rss 0.5G pss 0.4G | host avail 26.5G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.4 cpu 18.15 | cgroup 15.1G/max oom_kill 0 | free scratch 321.7G/45209840i tmp 29.4G/1010728i workspace 321.7G/45209841i | repeat-01 collected 26/26 workers (60617 items) tests 42278 done 1 failed | 23 in flight, oldest 270s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........................................ [1955%]
........................................................................ [1958%]
........................................................................ [1962%]
........................................................................ [1965%]
..................................................................[contention-diag] +3957s soak 35p/197t rss 13.8G pss 12.6G swap 0.8G majflt 2604 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 7 descendant rss 0.4G pss 0.3G | host avail 27.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.8 cpu 21.29 | cgroup 15.0G/max oom_kill 0 | free scratch 321.7G/45208469i tmp 29.4G/1010728i workspace 321.7G/45208469i | repeat-01 collected 26/26 workers (60617 items) tests 42602 done 1 failed | 24 in flight, oldest 285s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
...... [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
........................................................................ [1978%]
........................................................................ [1982%]
.............................[contention-diag] +3973s soak 37p/192t rss 13.9G pss 12.7G swap 0.7G majflt 2614 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.5G pss 0.4G | host avail 27.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.39 cpu 21.59 | cgroup 15.1G/max oom_kill 0 | free scratch 321.7G/45207086i tmp 29.4G/1010728i workspace 321.7G/45207086i | repeat-01 collected 26/26 workers (60617 items) tests 42922 done 1 failed | 24 in flight, oldest 300s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........................................... [1985%]
........................................................................ [1988%]
........................................................................ [1992%]
........................................................................ [1995%]
....................................................[contention-diag] +3988s soak 35p/186t rss 14.0G pss 12.8G swap 0.8G majflt 2617 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 7 descendant rss 0.6G pss 0.5G | host avail 27.3G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.4 cpu 19.46 | cgroup 15.2G/max oom_kill 0 | free scratch 321.7G/45204354i tmp 29.4G/1010728i workspace 321.7G/45204354i | scratch used 0.9G in 173135 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 43181 done 1 failed | 24 in flight, oldest 188s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................... [1998%]
........................................................................ [2002%]
........................................................................ [2005%]
........................................................................ [2008%]
.........................[contention-diag] +4005s soak 38p/202t rss 14.1G pss 12.8G swap 0.8G majflt 2624 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 10 descendant rss 0.6G pss 0.5G | host avail 27.0G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 1.43 cpu 15.53 | cgroup 15.3G/max oom_kill 0 | free scratch 321.6G/45204545i tmp 29.4G/1010728i workspace 321.6G/45204545i | repeat-01 collected 26/26 workers (60617 items) tests 43513 done 1 failed | 24 in flight, oldest 205s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................... [2012%]
........................................................................ [2015%]
........................................................................ [2018%]
........................................................................ [2021%]
.....................................[contention-diag] +4021s soak 44p/203t rss 14.2G pss 12.9G swap 0.7G majflt 2630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 16 descendant rss 0.7G pss 0.6G | host avail 26.2G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 3.43 cpu 14.01 | cgroup 15.4G/max oom_kill 0 | free scratch 321.5G/45202806i tmp 29.4G/1010728i workspace 321.5G/45202806i | repeat-01 collected 26/26 workers (60617 items) tests 43811 done 1 failed | 24 in flight, oldest 221s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................... [2025%]
........................................................................ [2028%]
........................................................................ [2031%]
........................................................................ [2035%]
...................[contention-diag] +4036s soak 41p/210t rss 14.3G pss 13.0G swap 0.8G majflt 2633 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 13 descendant rss 0.8G pss 0.7G | host avail 24.4G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.13/0.08 io 2.96 cpu 16.21 | cgroup 15.5G/max oom_kill 0 | free scratch 321.3G/45203665i tmp 29.4G/1010728i workspace 321.3G/45203665i | repeat-01 collected 26/26 workers (60617 items) tests 44074 done 1 failed | 22 in flight, oldest 236s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................... [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
..............[contention-diag] +4052s soak 40p/195t rss 14.3G pss 13.0G swap 0.8G majflt 2637 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 12 descendant rss 0.8G pss 0.7G | host avail 23.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.27/0.26 io 1.77 cpu 19.04 | cgroup 15.5G/max oom_kill 0 | free scratch 321.2G/45203454i tmp 29.4G/1010728i workspace 321.2G/45203454i | repeat-01 collected 26/26 workers (60617 items) tests 44288 done 1 failed | 22 in flight, oldest 251s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................................... [2048%]
........................................................................ [2051%]
........................................................................ [2055%]
..................[contention-diag] +4067s soak 40p/195t rss 14.3G pss 13.0G swap 0.8G majflt 2642 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 12 descendant rss 0.8G pss 0.7G | host avail 22.5G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 1.94 cpu 16.87 | cgroup 15.4G/max oom_kill 0 | free scratch 321.1G/45202798i tmp 29.4G/1010728i workspace 321.1G/45202798i | repeat-01 collected 26/26 workers (60617 items) tests 44510 done 1 failed | 22 in flight, oldest 267s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................................... [2058%]
........................................................................ [2061%]
........................................................................ [2065%]
........................................................................ [2068%]
........................................................................ [2071%]
........................................................................ [2075%]
........................................................................ [2078%]
.....................................[contention-diag] +4082s soak 36p/197t rss 14.3G pss 13.0G swap 0.8G majflt 2682 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 8 descendant rss 0.7G pss 0.7G | host avail 20.5G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 4.72 cpu 17.12 | cgroup 15.5G/max oom_kill 0 | free scratch 321.0G/45201186i tmp 29.4G/1010728i workspace 321.0G/45201186i | repeat-01 collected 26/26 workers (60617 items) tests 45021 done 1 failed | 20 in flight, oldest 282s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................... [2081%]
........................................................................ [2085%]
........................................................................ [2088%]
........................................................................ [2091%]
........................................................................ [2095%]
........................................................................ [2098%]
[contention-diag] +4098s soak 35p/200t rss 14.1G pss 12.9G swap 0.8G majflt 2684 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 7 descendant rss 0.6G pss 0.6G | host avail 23.6G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 6.17 cpu 19.71 | cgroup 15.4G/max oom_kill 0 | free scratch 320.9G/45199436i tmp 29.4G/1010728i workspace 320.9G/45199436i | repeat-01 collected 26/26 workers (60617 items) tests 45405 done 1 failed | 20 in flight, oldest 298s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................................................ [2101%]
................................s....................................... [2105%]
........................................................................ [2108%]
........................................................................ [2111%]
........................................................................ [2115%]
........................................................................ [2118%]
........................................................................ [2121%]
...................[contention-diag] +4113s soak 37p/178t rss 14.3G pss 13.0G swap 0.8G majflt 2702 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 0.7G pss 0.7G | host avail 22.2G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.51 cpu 18.57 | cgroup 15.5G/max oom_kill 0 | free scratch 320.9G/45198553i tmp 29.4G/1010728i workspace 320.9G/45198553i | scratch used 0.8G in 152299 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 45914 done 1 failed | 22 in flight, oldest 313s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................... [2125%]
........................................................................ [2128%]
........................................................................ [2131%]
........................................................................ [2135%]
........................................................................ [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
..........[contention-diag] +4131s soak 39p/178t rss 14.5G pss 13.2G swap 0.8G majflt 2716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 11 descendant rss 0.9G pss 0.8G | host avail 22.6G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.3 cpu 18.94 | cgroup 15.7G/max oom_kill 0 | free scratch 320.9G/45196663i tmp 29.4G/1010726i workspace 320.9G/45196663i | repeat-01 collected 26/26 workers (60617 items) tests 46509 done 1 failed | 21 in flight, oldest 330s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.............................................................. [2151%]
........................................................................ [2155%]
........................................................................ [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
.......................................................................[contention-diag] +4146s soak 37p/186t rss 14.5G pss 13.2G swap 0.8G majflt 2726 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 0.9G pss 0.9G | host avail 25.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.21 cpu 21.68 | cgroup 15.7G/max oom_kill 0 | free scratch 320.9G/45195039i tmp 29.4G/1010728i workspace 320.9G/45195039i | repeat-01 collected 26/26 workers (60617 items) tests 46931 done 1 failed | 22 in flight, oldest 346s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
. [2168%]
........................................................................ [2171%]
........................................................................ [2174%]
........................................................................ [2178%]
........................................................................ [2181%]
........................................................................ [2184%]
........................................................................ [2188%]
........................................................................ [2191%]
........................................................................ [2194%]
.........[contention-diag] +4162s soak 34p/171t rss 14.5G pss 13.2G swap 0.8G majflt 2732 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 6 descendant rss 0.9G pss 0.8G | host avail 24.3G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.68 cpu 18.22 | cgroup 15.8G/max oom_kill 0 | free scratch 321.3G/45190141i tmp 29.4G/1010728i workspace 321.3G/45190141i | repeat-01 collected 26/26 workers (60617 items) tests 47493 done 1 failed | 20 in flight, oldest 361s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................................... [2198%]
........................................................................ [2201%]
........................................................................ [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2218%]
.....[contention-diag] +4177s soak 37p/172t rss 14.4G pss 13.0G swap 0.8G majflt 2744 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 11.8G, 9 descendant rss 0.9G pss 0.8G | host avail 22.8G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.31 cpu 17.24 | cgroup 15.7G/max oom_kill 0 | free scratch 321.1G/45193758i tmp 29.4G/1010728i workspace 321.1G/45193758i | repeat-01 collected 26/26 workers (60617 items) tests 48022 done 1 failed | 20 in flight, oldest 377s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................................................... [2221%]
........................................................................ [2224%]
........................................................................ [2228%]
................................[contention-diag] +4193s soak 38p/176t rss 14.6G pss 13.1G swap 0.8G majflt 2940 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 11.8G, 10 descendant rss 1.0G pss 0.9G | host avail 22.4G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.8/0.24 io 2.64 cpu 17.13 | cgroup 15.9G/max oom_kill 0 | free scratch 321.0G/45193015i tmp 29.4G/1010728i workspace 321.0G/45193015i | repeat-01 collected 26/26 workers (60617 items) tests 48264 done 1 failed | 20 in flight, oldest 392s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................ [2231%]
........................................................................ [2234%]
........................................................................ [2238%]
........................................................................ [2241%]
...................................................................[contention-diag] +4208s soak 39p/180t rss 14.7G pss 13.4G swap 0.9G majflt 3142 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 11 descendant rss 1.2G pss 1.1G | host avail 20.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 1.2/0.2 io 2.75 cpu 18.05 | cgroup 15.7G/max oom_kill 0 | free scratch 320.9G/45191973i tmp 29.4G/1010728i workspace 320.9G/45191973i | repeat-01 collected 26/26 workers (60617 items) tests 48585 done 1 failed | 20 in flight, oldest 408s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..... [2244%]
........................................................................ [2248%]
........................................................................ [2251%]
........................................................................ [2254%]
........................................................................ [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
............................................................[contention-diag] +4224s soak 41p/206t rss 14.8G pss 13.4G swap 0.9G majflt 3295 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 13 descendant rss 1.2G pss 1.1G | host avail 19.4G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.6/0.3 io 2.43 cpu 18.92 | cgroup 15.7G/max oom_kill 0 | free scratch 320.9G/45190378i tmp 29.4G/1010728i workspace 320.9G/45190378i | repeat-01 collected 26/26 workers (60617 items) tests 49076 done 1 failed | 19 in flight, oldest 394s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............ [2268%]
........................................................................ [2271%]
........................................................................ [2274%]
........................................................................ [2278%]
........................................................................ [2281%]
........................................................................ [2284%]
........................................................................ [2288%]
[contention-diag] +4239s soak 41p/200t rss 14.8G pss 13.5G swap 0.9G majflt 3373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 13 descendant rss 1.3G pss 1.2G | host avail 22.1G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.12/0.06 io 2.79 cpu 20.0 | cgroup 15.8G/max oom_kill 0 | free scratch 320.8G/45188679i tmp 29.4G/1010725i workspace 320.8G/45188679i | scratch used 0.9G in 164056 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 49422 done 1 failed | 18 in flight, oldest 409s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................................ [2291%]
........................................................................ [2294%]
........................................................................ [2298%]
........................................................................ [2301%]
........................................................................ [2304%]
................................[contention-diag] +4256s soak 46p/200t rss 14.9G pss 13.5G swap 0.8G majflt 3378 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 18 descendant rss 1.3G pss 1.2G | host avail 23.9G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 1.15 cpu 17.59 | cgroup 15.9G/max oom_kill 0 | free scratch 320.8G/45189867i tmp 29.4G/1010725i workspace 320.8G/45189867i | repeat-01 collected 26/26 workers (60617 items) tests 49911 done 1 failed | 18 in flight, oldest 427s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................ [2307%]
........................................................................ [2311%]
........................................................................ [2314%]
........................................................................ [2317%]
........................................................................ [2321%]
........................................................................ [2324%]
..[contention-diag] +4272s soak 37p/190t rss 14.6G pss 13.3G swap 0.9G majflt 3478 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 1.0G pss 0.9G | host avail 29.0G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.4 cpu 21.24 | cgroup 15.7G/max oom_kill 0 | free scratch 320.8G/45188425i tmp 29.4G/1010725i workspace 320.8G/45188425i | repeat-01 collected 26/26 workers (60617 items) tests 50318 done 1 failed | 19 in flight, oldest 442s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................................................... [2327%]
........................................................................ [2331%]
............................s........................................... [2334%]
........................................................................ [2337%]
........................................................................ [2341%]
...............................................[contention-diag] +4287s soak 36p/183t rss 14.6G pss 13.3G swap 0.9G majflt 3662 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 8 descendant rss 1.0G pss 1.0G | host avail 26.4G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.3 cpu 24.29 | cgroup 15.7G/max oom_kill 0 | free scratch 321.3G/45187973i tmp 29.4G/1010726i workspace 321.3G/45187973i | repeat-01 collected 26/26 workers (60617 items) tests 50734 done 1 failed | 18 in flight, oldest 458s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
......................... [2344%]
........................................................................ [2347%]
........................................................................ [2351%]
........................................................................ [2354%]
................................[contention-diag] +4302s soak 41p/190t rss 14.7G pss 13.4G swap 0.9G majflt 3776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 11.9G, 13 descendant rss 1.2G pss 1.1G | host avail 24.1G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.22 cpu 19.82 | cgroup 15.8G/max oom_kill 0 | free scratch 321.1G/45186982i tmp 29.4G/1010726i workspace 321.1G/45186982i | repeat-01 collected 26/26 workers (60617 items) tests 51001 done 1 failed | 18 in flight, oldest 473s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................ [2357%]
........................................................................ [2361%]
........................................................................ [2364%]
........................................................................ [2367%]
................................................................[contention-diag] +4318s soak 41p/181t rss 14.7G pss 13.4G swap 0.9G majflt 3789 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 13 descendant rss 1.2G pss 1.1G | host avail 22.3G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.77 cpu 16.56 | cgroup 15.8G/max oom_kill 0 | free scratch 321.0G/45186150i tmp 29.4G/1010726i workspace 321.0G/45186150i | repeat-01 collected 26/26 workers (60617 items) tests 51321 done 1 failed | 18 in flight, oldest 488s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........ [2371%]
........................................................................ [2374%]
........................................................................ [2377%]
........................................................................ [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
..............................................................[contention-diag] +4333s soak 34p/172t rss 14.5G pss 13.2G swap 0.8G majflt 3811 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 11.9G, 6 descendant rss 1.0G pss 0.9G | host avail 22.4G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.54 cpu 17.37 | cgroup 15.8G/max oom_kill 0 | free scratch 320.9G/45184672i tmp 29.4G/1010726i workspace 320.9G/45184672i | repeat-01 collected 26/26 workers (60617 items) tests 51745 done 1 failed | 18 in flight, oldest 504s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......... [2391%]
........................................................................ [2394%]
........................................................................ [2397%]
........................................................................ [2401%]
........................................................................ [2404%]
..................................................................[contention-diag] +4349s soak 36p/175t rss 14.7G pss 13.4G swap 0.8G majflt 3859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 8 descendant rss 1.1G pss 1.0G | host avail 23.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 3.12 cpu 16.35 | cgroup 16.0G/max oom_kill 0 | free scratch 320.8G/45183609i tmp 29.4G/1010726i workspace 320.8G/45183609i | repeat-01 collected 26/26 workers (60617 items) tests 52116 done 1 failed | 18 in flight, oldest 519s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...... [2407%]
........................................................................ [2411%]
........................................................................ [2414%]
........................................................................ [2417%]
........................................................................ [2421%]
........................................................................ [2424%]
........................................................................ [2427%]
........................................................................ [2431%]
..................................................................[contention-diag] +4364s soak 37p/166t rss 14.6G pss 13.3G swap 0.8G majflt 3876 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 1.0G pss 0.9G | host avail 23.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 3.42 cpu 19.58 | cgroup 15.9G/max oom_kill 0 | free scratch 320.8G/45182082i tmp 29.4G/1010726i workspace 320.8G/45182082i | scratch used 0.7G in 129589 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 52563 done 1 failed | 17 in flight, oldest 535s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
...... [2434%]
........................................................................ [2437%]
........................................................................ [2441%]
........................................................................ [2444%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2454%]
........................................................................ [2457%]
........................................................................ [2460%]
..............[contention-diag] +4382s soak 37p/164t rss 14.6G pss 13.3G swap 0.8G majflt 3929 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 1.0G pss 0.9G | host avail 24.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.68 cpu 19.47 | cgroup 15.9G/max oom_kill 0 | free scratch 320.8G/45181168i tmp 29.4G/1010726i workspace 320.8G/45181168i | repeat-01 collected 26/26 workers (60617 items) tests 53271 done 1 failed | 17 in flight, oldest 552s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......................................................... [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
........................................................................ [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
..............................................................s......... [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
........................................................................ [2494%]
..........................[contention-diag] +4397s soak 35p/160t rss 14.6G pss 13.3G swap 0.8G majflt 4002 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 7 descendant rss 1.0G pss 0.9G | host avail 27.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.58 cpu 21.63 | cgroup 16.0G/max oom_kill 0 | free scratch 320.7G/45179338i tmp 29.4G/1010726i workspace 320.7G/45179338i | repeat-01 collected 26/26 workers (60617 items) tests 53987 done 1 failed | 17 in flight, oldest 567s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.............................................. [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
........................................................................ [2507%]
........................................................................ [2510%]
........................................................................ [2514%]
........................................................................ [2517%]
........................................................................ [2520%]
......................[contention-diag] +4412s soak 35p/164t rss 14.6G pss 13.1G swap 0.8G majflt 4027 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 11.8G, 7 descendant rss 1.0G pss 1.0G | host avail 25.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.85 cpu 23.63 | cgroup 16.0G/max oom_kill 0 | free scratch 321.2G/45177477i tmp 29.4G/1010726i workspace 321.2G/45177477i | repeat-01 collected 26/26 workers (60617 items) tests 54556 done 1 failed | 17 in flight, oldest 583s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................................. [2524%]
........................................................................ [2527%]
........................................................................ [2530%]
........................................................................ [2534%]
........................................................................ [2537%]
........................................................................ [2540%]
.................................................[contention-diag] +4428s soak 39p/165t rss 14.8G pss 13.5G swap 0.9G majflt 4068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 11 descendant rss 1.2G pss 1.1G | host avail 24.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.4 cpu 19.16 | cgroup 16.1G/max oom_kill 0 | free scratch 321.0G/45177183i tmp 29.4G/1010726i workspace 321.0G/45177183i | repeat-01 collected 26/26 workers (60617 items) tests 55047 done 1 failed | 16 in flight, oldest 598s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
....................... [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
........................................................................ [2554%]
........................................................................ [2557%]
........................................................................ [2560%]
..............[contention-diag] +4443s soak 39p/163t rss 14.0G pss 12.7G swap 0.8G majflt 4099 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 11 descendant rss 0.3G pss 0.3G | host avail 24.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.34 cpu 20.96 | cgroup 15.4G/max oom_kill 0 | free scratch 320.9G/45176755i tmp 29.4G/1010726i workspace 320.9G/45176755i | repeat-01 collected 26/26 workers (60617 items) tests 55452 done 1 failed | 15 in flight, oldest 73s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.......................................................... [2564%]
........................................................................ [2567%]
........................................................................ [2570%]
........................................................................ [2574%]
............s........................................................... [2577%]
............................................................[contention-diag] +4459s soak 45p/200t rss 14.5G pss 13.1G swap 0.8G majflt 4119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 17 descendant rss 0.8G pss 0.7G | host avail 23.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.36 cpu 23.06 | cgroup 15.7G/max oom_kill 0 | free scratch 320.8G/45175757i tmp 29.4G/1010726i workspace 320.8G/45175757i | repeat-01 collected 26/26 workers (60617 items) tests 55859 done 1 failed | 15 in flight, oldest 88s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............ [2580%]
........................................................................ [2584%]
........................................................................ [2587%]
..................................................[contention-diag] +4474s soak 38p/175t rss 14.3G pss 12.9G swap 0.9G majflt 4149 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 10 descendant rss 0.7G pss 0.6G | host avail 25.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.38 cpu 20.96 | cgroup 15.7G/max oom_kill 0 | free scratch 320.8G/45175125i tmp 29.4G/1010726i workspace 320.8G/45175125i | repeat-01 collected 26/26 workers (60617 items) tests 56064 done 1 failed | 15 in flight, oldest 104s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
...................... [2590%]
........................................................................ [2593%]
........................................................................ [2597%]
........................................................................ [2600%]
........................................................................ [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
...........................................................[contention-diag] +4490s soak 36p/166t rss 14.0G pss 12.7G swap 0.9G majflt 4247 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 8 descendant rss 0.4G pss 0.3G | host avail 24.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.06 cpu 21.3 | cgroup 15.4G/max oom_kill 0 | free scratch 320.9G/45205533i tmp 29.4G/1010726i workspace 320.9G/45205534i | scratch used 0.8G in 149343 entries (truncated) | repeat-01 collected 26/26 workers (60617 items) tests 56587 done 1 failed | 15 in flight, oldest 119s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............. [2617%]
........................................................................ [2620%]
........................................................................ [2623%]
........................................................................ [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
........................................................................ [2637%]
.[contention-diag] +4507s soak 37p/165t rss 13.9G pss 12.6G swap 0.9G majflt 4265 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 0.3G pss 0.2G | host avail 24.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.37/0.37 io 5.22 cpu 19.78 | cgroup 15.3G/max oom_kill 0 | free scratch 321.1G/45245719i tmp 29.4G/1010726i workspace 321.1G/45245719i | repeat-01 collected 26/26 workers (60617 items) tests 57095 done 1 failed | 14 in flight, oldest 137s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
....................................................................... [2640%]
........................................................................ [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
........................................................................ [2657%]
............................[contention-diag] +4522s soak 42p/174t rss 14.1G pss 12.7G swap 0.9G majflt 4286 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 14 descendant rss 0.4G pss 0.3G | host avail 27.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 6.31 cpu 21.85 | cgroup 15.5G/max oom_kill 0 | free scratch 321.3G/45273965i tmp 29.4G/1010726i workspace 321.3G/45273965i | repeat-01 collected 26/26 workers (60617 items) tests 57549 done 1 failed | 13 in flight, oldest 100s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................................ [2660%]
........................................................................ [2663%]
........................................................................ [2667%]
........................................................................ [2670%]
........................................................................ [2673%]
............s........................................................... [2677%]
........................................................................ [2680%]
........................................................................ [2683%]
........................................................................ [2687%]
..........[contention-diag] +4538s soak 35p/161t rss 13.8G pss 12.5G swap 0.8G majflt 4370 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 7 descendant rss 0.2G pss 0.2G | host avail 25.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 4.94 cpu 20.0 | cgroup 15.3G/max oom_kill 0 | free scratch 322.0G/45307412i tmp 29.4G/1010726i workspace 322.0G/45307412i | repeat-01 collected 26/26 workers (60617 items) tests 58174 done 1 failed | 10 in flight, oldest 115s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.............................................................. [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
........................................................................ [2700%]
........................................................................ [2703%]
........................................................................ [2707%]
....................................[contention-diag] +4553s soak 35p/161t rss 13.8G pss 12.5G swap 0.9G majflt 4413 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 7 descendant rss 0.2G pss 0.2G | host avail 24.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.58 cpu 18.59 | cgroup 15.4G/max oom_kill 0 | free scratch 321.9G/45333456i tmp 29.4G/1010726i workspace 321.9G/45333456i | repeat-01 collected 26/26 workers (60617 items) tests 58631 done 1 failed | 10 in flight, oldest 102s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.................................... [2710%]
........................................................................ [2713%]
........................................................................ [2717%]
........................................................................ [2720%]
........................................................................ [2723%]
........................................................................ [2727%]
........................................................................ [2730%]
.........................................................[contention-diag] +4568s soak 33p/156t rss 13.8G pss 12.5G swap 0.8G majflt 4417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 5 descendant rss 0.1G pss 0.1G | host avail 24.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.43 cpu 19.65 | cgroup 15.3G/max oom_kill 0 | free scratch 321.8G/45336562i tmp 29.4G/1010726i workspace 321.8G/45336562i | repeat-01 collected 26/26 workers (60617 items) tests 59163 done 1 failed | 9 in flight, oldest 19s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
............... [2733%]
........................................................................ [2736%]
........................................................................ [2740%]
........................................................................ [2743%]
..........................................[contention-diag] +4584s soak 35p/156t rss 13.8G pss 12.5G swap 0.8G majflt 4428 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 7 descendant rss 0.1G pss 0.1G | host avail 23.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.22 cpu 20.5 | cgroup 15.4G/max oom_kill 0 | free scratch 321.7G/45336691i tmp 29.4G/1010726i workspace 321.7G/45336691i | repeat-01 collected 26/26 workers (60617 items) tests 59424 done 1 failed | 8 in flight, oldest 35s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.............................. [2746%]
........................................................................ [2750%]
........................................................................ [2753%]
........................................................................ [2756%]
...................................................[contention-diag] +4599s soak 35p/157t rss 13.7G pss 12.4G swap 0.8G majflt 4443 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 7 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.12 cpu 20.74 | cgroup 15.3G/max oom_kill 0 | free scratch 321.6G/45337276i tmp 29.4G/1010726i workspace 321.6G/45337276i | repeat-01 collected 26/26 workers (60617 items) tests 59734 done 1 failed | 6 in flight, oldest 50s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
..................... [2760%]
........................................................................ [2763%]
........................................................................ [2766%]
........................................................................ [2770%]
........................................................................ [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
.................................................[contention-diag] +4615s soak 36p/156t rss 13.7G pss 12.4G swap 0.8G majflt 4502 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 8 descendant rss 0.0G pss 0.0G | host avail 24.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.05 cpu 21.55 | cgroup 15.3G/max oom_kill 0 | free scratch 321.6G/45336935i tmp 29.4G/1010726i workspace 321.6G/45336935i | scratch used 0.9G in 168007 entries | repeat-01 collected 26/26 workers (60617 items) tests 60278 done 1 failed | 4 in flight, oldest 2s gw4 tests/tool/test_keep_going.py::test_continuation_never_returns_zero_after_a_failed_stage[True-outcomes2] | 10 hazardous kill call(s)
....................... [2786%]
........................................................................ [2790%]
........................................................................ [2793%]
..........ssss.......................................................... [2796%]
.................................[contention-diag] +4632s soak 32p/149t rss 13.7G pss 12.4G swap 0.8G majflt 4555 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.0G, 4 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.3 cpu 13.95 | cgroup 15.3G/max oom_kill 0 | free scratch 321.6G/45338614i tmp 29.4G/1010726i workspace 321.6G/45338614i | repeat-01 collected 26/26 workers (60617 items) tests 60584 done 1 failed | 1 in flight, oldest 0s gw20 tests/tool/test_settlement_hook.py::test_stopped_proc_before_start_settles_via_hook | 10 hazardous kill call(s)
................................        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_ test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap] _
[gw15] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8d7f5a8e30>
result = VcsLogResult(repos=(LogRepo(name='alpha-platform-repository', path='/tmp/alpha', kind='primary', aliases=(), plan_work...tched_at=1.0)), aggregate_truncated=False, provider_truncation_possible=False, resolved_filters=None, filter_spec=None)
expected_count = 41, capped = False

    @pytest.mark.parametrize(
        ("result", "expected_count", "capped"),
        (
            (_result_with_commit_count(2), 2, False),
            (
                _result_with_commit_count(2, provider_truncation_possible=True),
                2,
                True,
            ),
            (_result_with_commit_count(2, aggregate_truncated=True), 2, True),
            (_result_with_commit_count(41), 41, False),
        ),
        ids=("exact", "provider-cap", "aggregate-cap", "above-old-default-cap"),
    )
    async def test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap(
        monkeypatch: pytest.MonkeyPatch,
        result: VcsLogResult,
        expected_count: int,
        capped: bool,
    ) -> None:
        monkeypatch.setattr(
            "sase.config.load_merged_config",
            lambda: {
                "ace": {
                    "artifacts": {
                        "stitches": {"default_query": "sidecar:false since:24h limit:all"}
                    }
                }
            },
        )
        monkeypatch.setattr(commits_module, "run_vcs_log", lambda **_kwargs: result)
        monkeypatch.setattr(commits_module, "load_commit_diff_text", lambda _spec: "")
    
        async with AcePage(initial_tab="patches") as page:
            await page.press(page.artifacts_digit("stitches"))
            pane = page.query_one_widget("#artifacts-stitches-pane", CommitsPane)
            bar = pane.query_one(CommitFilterBar)
            status = bar.query_one("#commit-filter-status", Static)
            editor = bar.query_one("#commit-filter-input", SingleLineVimTextArea)
            await page.wait_for(
                lambda _state: (
                    pane.result is not None
                    and len(pane.result.commits) == expected_count
                    and ("capped" in status.content.plain) is capped
                )
            )
    
            coverage = "capped" if capped else "exact"
            marker = "+" if capped else ""
>           assert status.content.plain == coverage
E           AssertionError: assert 'preview' == 'exact'
E             
E             - exact
E             + preview

tests/ace/tui/test_commits_pane_collection.py:172: AssertionError
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/dom.py:1735: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    return self._classes.issuperset(class_names)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_panel_adapter.py::test_adapter_dismisses_on_escape
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/inspect.py:3076: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    params = OrderedDict((param.name, param) for param in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/css/model.py:189: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for selector, next_selector in zip(self.selectors, self.selectors[1:]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _record_history_async.<locals>._record at 0x7f1a706d6f80>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _record_history_async.<locals>._record at 0x7f1f383e17e0>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/walk.py:77: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    if (node := next(stack[-1], None)) is None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_selected_run_in_a_folded_banner_moves_to_the_banner
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/models/agent_archive_list.py:144: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    if all(isinstance(part, str) and part for part in (user, machine, run_id)):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_restore_proof.py::test_proof_plain_restore_leaves_parked_inbox_untouched
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/typing.py:1630: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    return ((p, type(p)) for p in parameters)
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2820462) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=2820837) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=2819942) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
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

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=2820222) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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
  <frozen os>:888: DeprecationWarning: This process (pid=2819942) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=2820930) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
602.07s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
451.88s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
445.51s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
442.07s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
427.42s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
410.72s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
339.57s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
337.92s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
322.25s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
315.59s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
311.46s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
253.98s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
221.48s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
193.07s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
184.37s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
181.50s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
178.84s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
165.77s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
157.42s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
156.22s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
=========================== short test summary info ============================
FAILED tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap]
==== 1 failed, 60596 passed, 21 skipped, 111 warnings in 4643.99s (1:17:23) ====
[contention-diag] +4647s soak 2p/2t rss 0.4G pss 0.4G swap 0.0G majflt 233 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 42.0G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.36 cpu 18.07 | cgroup 3.3G/max oom_kill 0 | free scratch 321.6G/45339400i tmp 29.4G/1010726i workspace 321.6G/45339400i | repeat-01 collected 26/26 workers (60617 items) tests 60617 done 1 failed | 10 hazardous kill call(s)
[contention-diag] +4650s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 429 | 1 parent rss 0.0G pss 0.0G | host avail 42.3G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.07 cpu 12.11 | cgroup 2.9G/max oom_kill 0 | free scratch 321.6G/45339398i tmp 29.4G/1010726i workspace 321.6G/45339398i | repeat-01 collected 26/26 workers (60617 items) tests 60617 done 1 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4650s, 300 samples, 0 signal(s); peaks: cgroup_current 16.1G, min_free_scratch 318.8G, min_free_tmp 29.3G, min_free_workspace 318.8G, min_inodes_scratch 45175125, min_inodes_tmp 1010283, min_inodes_workspace 45175125, min_mem_available 19.1G, min_swap_free 53.0G, oom_kill_delta 0, pressure_memory_full 1.12, pswpin_delta 224579, pswpout_delta 159274, scratch_bytes 1.1G, soak_procs 52, soak_pss 13.5G, soak_rss 14.9G, soak_swap 0.9G, soak_threads 304

contention tally: 1 node(s) failed across 1 repeat(s) in 4650.1s; red repeats: 1
  1/1  tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap]  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

