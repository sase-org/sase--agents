# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon)

- **TIMESTAMP:** 2026-11-08 03:58:49 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat for phase sase-1rq.2.1.4.1.5.2 zero-failure proof'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5670 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 3055035, sampler pid 3055261 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-1087786-1794123962400068455.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 44.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.03 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 329.7G/45471785i tmp 29.7G/1019839i workspace 329.7G/45471785i | scratch used 0.1G in 27051 entries (truncated) | progress none yet
[contention-diag] +17s soak 28p/80t rss 2.4G pss 2.0G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.2G pss 1.9G | host avail 42.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 24.67 | cgroup 2.1G/max oom_kill 0 | free scratch 329.7G/45471684i tmp 29.7G/1019839i workspace 329.7G/45471684i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 3.8G pss 3.3G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.7G pss 3.3G | host avail 40.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 30.15 | cgroup 3.5G/max oom_kill 0 | free scratch 329.7G/45471629i tmp 29.7G/1019839i workspace 329.7G/45471629i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +47s soak 28p/84t rss 4.9G pss 4.4G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.8G pss 4.3G | host avail 39.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 27.21 | cgroup 4.5G/max oom_kill 0 | free scratch 329.7G/45471631i tmp 29.7G/1019839i workspace 329.7G/45471631i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +62s soak 29p/89t rss 5.7G pss 5.2G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.6G pss 5.1G, 1 descendant rss 0.0G pss 0.0G | host avail 39.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.66 | cgroup 5.4G/max oom_kill 0 | free scratch 329.7G/45471606i tmp 29.7G/1019839i workspace 329.7G/45471606i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/89t rss 6.5G pss 5.9G swap 0.0G majflt 12 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.3G pss 5.8G | host avail 38.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.7 | cgroup 6.3G/max oom_kill 0 | free scratch 329.7G/45471589i tmp 29.7G/1019839i workspace 329.7G/45471588i | repeat-01 collected 9/26 workers (21088 items) tests 0 done 0 failed
contention shards: 26 workers collected 60601 items in total (2079-2555 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
........................................................................ [ 12%]
........................................................................ [ 15%]
........................................................................ [ 18%]
........................................................................ [ 21%]
........................................................................ [ 25%]
.[contention-diag] +93s soak 28p/105t rss 7.0G pss 6.3G swap 0.3G majflt 47 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.8G pss 6.2G | host avail 39.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.3 cpu 32.28 | cgroup 6.7G/max oom_kill 0 | free scratch 329.7G/45469428i tmp 29.7G/1019839i workspace 329.7G/45469428i | repeat-01 collected 26/26 workers (60601 items) tests 526 done 0 failed | 26 in flight, oldest 6s gw15 tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
....................................................................... [ 28%]
........................................................................ [ 31%]
........................................................................ [ 34%]
........................................................................ [ 37%]
........................................................................ [ 40%]
........................................................................ [ 43%]
..................................................................[contention-diag] +108s soak 29p/146t rss 7.6G pss 6.8G swap 0.3G majflt 126 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.7G, 1 descendant rss 0.0G pss 0.0G | host avail 38.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.17/0.01 io 0.07 cpu 38.14 | cgroup 7.3G/max oom_kill 0 | free scratch 329.7G/45468596i tmp 29.7G/1019839i workspace 329.7G/45468596i | repeat-01 collected 26/26 workers (60601 items) tests 1071 done 0 failed | 25 in flight, oldest 18s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
...... [ 47%]
........................................................................ [ 50%]
........................................................................ [ 53%]
........................................................................ [ 56%]
....................[contention-diag] +124s soak 30p/164t rss 7.8G pss 7.0G swap 0.3G majflt 138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 6.8G, 2 descendant rss 0.1G pss 0.1G | host avail 38.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 0.01 cpu 40.23 | cgroup 7.5G/max oom_kill 0 | free scratch 329.7G/45468096i tmp 29.7G/1019839i workspace 329.7G/45468096i | scratch used 0.3G in 52244 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 1270 done 0 failed | 26 in flight, oldest 33s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.................................................... [ 59%]
........................................................................ [ 62%]
........................................................................ [ 65%]
...............[contention-diag] +141s soak 32p/181t rss 8.1G pss 7.3G swap 0.3G majflt 153 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.0G, 4 descendant rss 0.2G pss 0.2G | host avail 37.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.54/0.54 io 0.16 cpu 32.37 | cgroup 7.8G/max oom_kill 0 | free scratch 329.7G/45467431i tmp 29.7G/1019839i workspace 329.7G/45467431i | repeat-01 collected 26/26 workers (60601 items) tests 1513 done 0 failed | 26 in flight, oldest 50s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
......................................................... [ 69%]
........................................................................ [ 72%]
........................................................................ [ 75%]
...............................................[contention-diag] +156s soak 33p/172t rss 8.2G pss 7.4G swap 0.3G majflt 181 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.2G, 5 descendant rss 0.1G pss 0.0G | host avail 38.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.13 cpu 35.84 | cgroup 7.9G/max oom_kill 0 | free scratch 329.7G/45466765i tmp 29.7G/1019839i workspace 329.7G/45466765i | repeat-01 collected 26/26 workers (60601 items) tests 1754 done 0 failed | 26 in flight, oldest 64s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
......................... [ 78%]
........................................................................ [ 81%]
..............................[contention-diag] +171s soak 35p/201t rss 8.4G pss 7.5G swap 0.3G majflt 181 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.3G, 7 descendant rss 0.1G pss 0.1G | host avail 37.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.02 cpu 35.36 | cgroup 8.1G/max oom_kill 0 | free scratch 329.7G/45466384i tmp 29.7G/1019839i workspace 329.7G/45466384i | repeat-01 collected 26/26 workers (60601 items) tests 1898 done 0 failed | 26 in flight, oldest 60s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................................... [ 84%]
........................................................................ [ 87%]
........................................................................ [ 91%]
........................................................................ [ 94%]
.......................................................[contention-diag] +186s soak 38p/218t rss 8.7G pss 7.8G swap 0.3G majflt 182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.5G, 10 descendant rss 0.3G pss 0.2G | host avail 39.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.69 | cgroup 8.3G/max oom_kill 0 | free scratch 329.7G/45465630i tmp 29.7G/1019839i workspace 329.7G/45465630i | repeat-01 collected 26/26 workers (60601 items) tests 2203 done 0 failed | 26 in flight, oldest 75s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................. [ 97%]
........................................................................ [100%]
........................................................................ [103%]
...................................[contention-diag] +202s soak 38p/202t rss 9.1G pss 8.1G swap 0.3G majflt 210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 7.7G, 10 descendant rss 0.4G pss 0.3G | host avail 38.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.15 | cgroup 8.7G/max oom_kill 0 | free scratch 329.7G/45465049i tmp 29.7G/1019839i workspace 329.7G/45465049i | repeat-01 collected 26/26 workers (60601 items) tests 2393 done 0 failed | 26 in flight, oldest 90s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................... [106%]
........................................................................ [109%]
.........................[contention-diag] +217s soak 31p/227t rss 8.9G pss 8.1G swap 0.3G majflt 210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 7.8G, 3 descendant rss 0.2G pss 0.1G | host avail 40.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.18 | cgroup 8.7G/max oom_kill 0 | free scratch 329.7G/45464664i tmp 29.7G/1019839i workspace 329.7G/45464664i | repeat-01 collected 26/26 workers (60601 items) tests 2529 done 0 failed | 26 in flight, oldest 106s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................... [113%]
........................................................................ [116%]
........................................................................ [119%]
...........[contention-diag] +232s soak 35p/231t rss 9.0G pss 8.1G swap 0.3G majflt 213 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 7.8G, 7 descendant rss 0.1G pss 0.1G | host avail 39.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.03 | cgroup 8.7G/max oom_kill 0 | free scratch 329.7G/45464105i tmp 29.7G/1019839i workspace 329.7G/45464105i | repeat-01 collected 26/26 workers (60601 items) tests 2734 done 0 failed | 25 in flight, oldest 121s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................. [122%]
........................................................................ [125%]
........................................[contention-diag] +247s soak 42p/235t rss 9.4G pss 8.4G swap 0.3G majflt 222 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 7.9G, 14 descendant rss 0.5G pss 0.3G | host avail 39.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.04 | cgroup 9.0G/max oom_kill 0 | free scratch 329.7G/45463538i tmp 29.7G/1019839i workspace 329.7G/45463538i | scratch used 0.4G in 77098 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 2914 done 0 failed | 26 in flight, oldest 136s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................ [128%]
......................................................................[contention-diag] +265s soak 33p/220t rss 9.1G pss 8.2G swap 0.3G majflt 229 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.1G, 5 descendant rss 0.0G pss 0.0G | host avail 38.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 33.73 | cgroup 8.9G/max oom_kill 0 | free scratch 329.7G/45463253i tmp 29.7G/1019839i workspace 329.7G/45463253i | repeat-01 collected 26/26 workers (60601 items) tests 3019 done 0 failed | 26 in flight, oldest 153s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.. [131%]
.......................[contention-diag] +280s soak 33p/234t rss 9.2G pss 8.3G swap 0.3G majflt 232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 39.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 0.02 cpu 33.2 | cgroup 9.0G/max oom_kill 0 | free scratch 329.7G/45463089i tmp 29.7G/1019839i workspace 329.7G/45463089i | repeat-01 collected 26/26 workers (60601 items) tests 3039 done 0 failed | 25 in flight, oldest 169s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................. [135%]
........................................................................ [138%]
................................................................[contention-diag] +295s soak 34p/233t rss 9.3G pss 8.4G swap 0.3G majflt 232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.2G, 6 descendant rss 0.1G pss 0.0G | host avail 38.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.0 cpu 34.07 | cgroup 9.1G/max oom_kill 0 | free scratch 329.7G/45462569i tmp 29.7G/1019839i workspace 329.7G/45462569i | repeat-01 collected 26/26 workers (60601 items) tests 3230 done 0 failed | 26 in flight, oldest 184s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........ [141%]
........................................................................ [144%]
.................................[contention-diag] +310s soak 35p/249t rss 9.5G pss 8.5G swap 0.3G majflt 232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.3G, 7 descendant rss 0.2G pss 0.1G | host avail 37.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 37.44 | cgroup 9.2G/max oom_kill 0 | free scratch 329.7G/45462163i tmp 29.7G/1019839i workspace 329.7G/45462163i | repeat-01 collected 26/26 workers (60601 items) tests 3336 done 0 failed | 26 in flight, oldest 199s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................... [147%]
........................................................................ [150%]
........................................................................ [153%]
........................................................................ [157%]
...................[contention-diag] +326s soak 33p/254t rss 9.4G pss 8.5G swap 0.3G majflt 232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.3G, 5 descendant rss 0.1G pss 0.0G | host avail 36.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.83 | cgroup 9.2G/max oom_kill 0 | free scratch 329.7G/45461453i tmp 29.7G/1019839i workspace 329.7G/45461453i | repeat-01 collected 26/26 workers (60601 items) tests 3616 done 0 failed | 26 in flight, oldest 214s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................... [160%]
..........................[contention-diag] +341s soak 33p/246t rss 9.5G pss 8.6G swap 0.3G majflt 232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 37.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.0 cpu 30.94 | cgroup 9.3G/max oom_kill 0 | free scratch 329.7G/45461193i tmp 29.7G/1019839i workspace 329.7G/45461193i | repeat-01 collected 26/26 workers (60601 items) tests 3698 done 0 failed | 26 in flight, oldest 230s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................. [163%]
........................................[contention-diag] +356s soak 35p/247t rss 9.7G pss 8.7G swap 0.3G majflt 235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.5G, 7 descendant rss 0.1G pss 0.1G | host avail 37.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.82 | cgroup 9.4G/max oom_kill 0 | free scratch 329.7G/45460852i tmp 29.7G/1019839i workspace 329.7G/45460852i | repeat-01 collected 26/26 workers (60601 items) tests 3769 done 0 failed | 26 in flight, oldest 245s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................ [166%]
..............................................[contention-diag] +371s soak 31p/252t rss 9.7G pss 8.8G swap 0.3G majflt 235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.5G, 3 descendant rss 0.1G pss 0.1G | host avail 37.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.05 | cgroup 9.5G/max oom_kill 0 | free scratch 329.7G/45460632i tmp 29.7G/1019839i workspace 329.7G/45460632i | scratch used 0.5G in 95578 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 3816 done 0 failed | 26 in flight, oldest 260s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................... [169%]
........................................................................ [172%]
..[contention-diag] +389s soak 39p/250t rss 9.8G pss 8.8G swap 0.3G majflt 235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.6G, 11 descendant rss 0.1G pss 0.1G | host avail 36.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 33.51 | cgroup 9.6G/max oom_kill 0 | free scratch 329.7G/45460209i tmp 29.7G/1019839i workspace 329.7G/45460209i | repeat-01 collected 26/26 workers (60601 items) tests 3957 done 0 failed | 26 in flight, oldest 277s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................................... [175%]
...................................[contention-diag] +404s soak 42p/271t rss 9.9G pss 8.9G swap 0.3G majflt 235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.6G, 14 descendant rss 0.2G pss 0.1G | host avail 37.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 37.3 | cgroup 9.7G/max oom_kill 0 | free scratch 329.7G/45459900i tmp 29.7G/1019839i workspace 329.7G/45459900i | repeat-01 collected 26/26 workers (60601 items) tests 4060 done 0 failed | 26 in flight, oldest 293s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................... [179%]
.................................[contention-diag] +419s soak 43p/265t rss 10.2G pss 9.2G swap 0.3G majflt 236 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.7G, 15 descendant rss 0.5G pss 0.3G | host avail 36.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.77 | cgroup 9.9G/max oom_kill 0 | free scratch 329.7G/45459641i tmp 29.7G/1019839i workspace 329.7G/45459641i | repeat-01 collected 26/26 workers (60601 items) tests 4133 done 0 failed | 26 in flight, oldest 308s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................... [182%]
........................................................................ [185%]
.....................................................[contention-diag] +434s soak 37p/259t rss 10.0G pss 9.0G swap 0.3G majflt 251 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.7G, 9 descendant rss 0.2G pss 0.2G | host avail 36.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.77 | cgroup 9.8G/max oom_kill 0 | free scratch 329.6G/45459137i tmp 29.7G/1019839i workspace 329.6G/45459137i | repeat-01 collected 26/26 workers (60601 items) tests 4293 done 0 failed | 25 in flight, oldest 323s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [188%]
.......[contention-diag] +450s soak 34p/274t rss 9.9G pss 9.0G swap 0.3G majflt 251 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 8.8G, 6 descendant rss 0.1G pss 0.0G | host avail 34.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.0 cpu 29.65 | cgroup 9.8G/max oom_kill 0 | free scratch 329.6G/45458965i tmp 29.7G/1019839i workspace 329.6G/45458965i | repeat-01 collected 26/26 workers (60601 items) tests 4327 done 0 failed | 26 in flight, oldest 338s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..............................................................[contention-diag] +465s soak 35p/270t rss 10.0G pss 9.0G swap 0.3G majflt 252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 8.9G, 7 descendant rss 0.1G pss 0.0G | host avail 37.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.0 cpu 34.76 | cgroup 9.8G/max oom_kill 0 | free scratch 329.6G/45458688i tmp 29.7G/1019839i workspace 329.6G/45458688i | repeat-01 collected 26/26 workers (60601 items) tests 4389 done 0 failed | 26 in flight, oldest 354s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
... [191%]
........................................................................ [194%]
........................................................................ [197%]
....[contention-diag] +480s soak 31p/252t rss 10.2G pss 9.2G swap 0.3G majflt 252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 8.9G, 3 descendant rss 0.2G pss 0.1G | host avail 36.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 39.8 | cgroup 9.9G/max oom_kill 0 | free scratch 329.6G/45458293i tmp 29.7G/1019839i workspace 329.6G/45458293i | repeat-01 collected 26/26 workers (60601 items) tests 4536 done 0 failed | 26 in flight, oldest 369s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..........................[contention-diag] +495s soak 28p/233t rss 10.1G pss 9.1G swap 0.3G majflt 252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.0G | host avail 36.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.44 | cgroup 9.9G/max oom_kill 0 | free scratch 329.6G/45458063i tmp 29.7G/1019839i workspace 329.6G/45458063i | scratch used 0.6G in 109812 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 4561 done 0 failed | 26 in flight, oldest 96s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
.....................[contention-diag] +513s soak 29p/219t rss 10.1G pss 9.2G swap 0.3G majflt 256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 36.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 34.58 | cgroup 10.0G/max oom_kill 0 | free scratch 329.6G/45457864i tmp 29.7G/1019839i workspace 329.6G/45457864i | repeat-01 collected 26/26 workers (60601 items) tests 4586 done 0 failed | 26 in flight, oldest 43s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
..................... [201%]
......................[contention-diag] +528s soak 30p/239t rss 10.3G pss 9.3G swap 0.3G majflt 256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.1G, 2 descendant rss 0.1G pss 0.1G | host avail 36.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 38.89 | cgroup 10.1G/max oom_kill 0 | free scratch 329.6G/45457617i tmp 29.7G/1019839i workspace 329.6G/45457617i | repeat-01 collected 26/26 workers (60601 items) tests 4625 done 0 failed | 26 in flight, oldest 58s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
.................................................. [204%]
.................................................[contention-diag] +543s soak 30p/238t rss 10.4G pss 9.4G swap 0.3G majflt 262 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.1G, 2 descendant rss 0.2G pss 0.1G | host avail 34.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.5 | cgroup 10.2G/max oom_kill 0 | free scratch 329.6G/45457232i tmp 29.7G/1019839i workspace 329.6G/45457232i | repeat-01 collected 26/26 workers (60601 items) tests 4721 done 0 failed | 26 in flight, oldest 60s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_from_fresh_main_lands_on_record_then_main
....................... [207%]
........................................[contention-diag] +558s soak 29p/245t rss 10.2G pss 9.3G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.2G, 1 descendant rss 0.0G pss 0.0G | host avail 34.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.0 cpu 31.96 | cgroup 10.2G/max oom_kill 0 | free scratch 329.6G/45456970i tmp 29.7G/1019839i workspace 329.6G/45456970i | repeat-01 collected 26/26 workers (60601 items) tests 4791 done 0 failed | 26 in flight, oldest 72s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
........[contention-diag] +574s soak 29p/251t rss 10.3G pss 9.4G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.2G, 1 descendant rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.0 cpu 30.03 | cgroup 10.2G/max oom_kill 0 | free scratch 329.6G/45456824i tmp 29.7G/1019839i workspace 329.6G/45456824i | repeat-01 collected 26/26 workers (60601 items) tests 4800 done 0 failed | 26 in flight, oldest 78s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
.............[contention-diag] +589s soak 31p/248t rss 10.4G pss 9.5G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.2G, 3 descendant rss 0.1G pss 0.1G | host avail 35.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.0 cpu 32.07 | cgroup 10.3G/max oom_kill 0 | free scratch 329.6G/45456673i tmp 29.7G/1019837i workspace 329.6G/45456673i | repeat-01 collected 26/26 workers (60601 items) tests 4811 done 0 failed | 26 in flight, oldest 93s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
........... [210%]
..................[contention-diag] +604s soak 29p/250t rss 10.3G pss 9.4G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.2G, 1 descendant rss 0.0G pss 0.0G | host avail 36.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.0 cpu 37.48 | cgroup 10.2G/max oom_kill 0 | free scratch 329.6G/45456478i tmp 29.7G/1019839i workspace 329.6G/45456478i | repeat-01 collected 26/26 workers (60601 items) tests 4842 done 0 failed | 26 in flight, oldest 55s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
...................................................... [213%]
.............[contention-diag] +620s soak 30p/262t rss 10.4G pss 9.4G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G, 2 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 35.34 | cgroup 10.3G/max oom_kill 0 | free scratch 329.6G/45456231i tmp 29.7G/1019839i workspace 329.6G/45456231i | scratch used 0.7G in 125209 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 4905 done 0 failed | 26 in flight, oldest 64s gw9 tests/ace/tui/test_agent_collapsed_panel_kill.py::test_confirming_last_panel_member_preserves_neighbors_and_valid_focus
........................................................... [216%]
.....................[contention-diag] +637s soak 29p/231t rss 10.5G pss 9.5G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G, 1 descendant rss 0.1G pss 0.0G | host avail 35.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 34.28 | cgroup 10.4G/max oom_kill 0 | free scratch 329.6G/45455907i tmp 29.7G/1019839i workspace 329.6G/45455907i | repeat-01 collected 26/26 workers (60601 items) tests 4988 done 0 failed | 25 in flight, oldest 56s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
..........[contention-diag] +652s soak 29p/250t rss 10.5G pss 9.6G swap 0.3G majflt 263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 35.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 36.07 | cgroup 10.5G/max oom_kill 0 | free scratch 329.6G/45455724i tmp 29.7G/1019839i workspace 329.6G/45455724i | repeat-01 collected 26/26 workers (60601 items) tests 4998 done 0 failed | 26 in flight, oldest 56s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_picker_acts_on_focused_split_panel
........................[contention-diag] +667s soak 28p/252t rss 10.5G pss 9.5G swap 0.3G majflt 264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G | host avail 35.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 29.58 | cgroup 10.6G/max oom_kill 0 | free scratch 329.6G/45455512i tmp 29.7G/1019839i workspace 329.6G/45455512i | repeat-01 collected 26/26 workers (60601 items) tests 5023 done 0 failed | 26 in flight, oldest 53s gw0 tests/ace/tui/test_copy_as_palette_entrypoints.py::test_percent_opens_palette_for_each_live_artifacts_subtab[beads]
................. [219%]
.............................[contention-diag] +683s soak 29p/229t rss 10.6G pss 9.6G swap 0.3G majflt 264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G, 1 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.3 | cgroup 10.6G/max oom_kill 0 | free scratch 329.6G/45455267i tmp 29.7G/1019839i workspace 329.6G/45455267i | repeat-01 collected 26/26 workers (60601 items) tests 5066 done 0 failed | 26 in flight, oldest 55s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_panel_action_override_takes_effect_in_mounted_pilot
........................................... [223%]
....................................[contention-diag] +698s soak 29p/237t rss 10.6G pss 9.7G swap 0.3G majflt 264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 1 descendant rss 0.1G pss 0.1G | host avail 33.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.0 cpu 30.11 | cgroup 10.7G/max oom_kill 0 | free scratch 329.6G/45454948i tmp 29.7G/1019839i workspace 329.6G/45454948i | repeat-01 collected 26/26 workers (60601 items) tests 5138 done 0 failed | 26 in flight, oldest 54s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
.................................... [226%]
.....[contention-diag] +713s soak 29p/228t rss 10.6G pss 9.7G swap 0.3G majflt 264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 1 descendant rss 0.1G pss 0.0G | host avail 35.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.0 cpu 34.92 | cgroup 10.6G/max oom_kill 0 | free scratch 329.6G/45454735i tmp 29.7G/1019839i workspace 329.6G/45454735i | repeat-01 collected 26/26 workers (60601 items) tests 5179 done 0 failed | 26 in flight, oldest 53s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_real_R_press_reruns_declined_and_notices_otherwise
................................................................... [229%]
........................................................................ [232%]
........................................................................ [235%]
..........................[contention-diag] +728s soak 29p/230t rss 10.6G pss 9.7G swap 0.3G majflt 264 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 35.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 42.96 | cgroup 10.6G/max oom_kill 0 | free scratch 329.6G/45454068i tmp 29.7G/1019839i workspace 329.6G/45454068i | repeat-01 collected 26/26 workers (60601 items) tests 5420 done 0 failed | 26 in flight, oldest 49s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
.............................................. [238%]
.....F[contention-failure] call tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6360a3f3b0>

    async def test_on_mount_refines_title_to_resolved_version(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A resolved dev version replaces the instant ``__version__`` title."""
        dev_version = f"{sase.__version__}+9.gdeadbee.dirty"
        monkeypatch.setattr(
            "sase.ace.tui.util.app_version.resolved_app_version",
            lambda: dev_version,
        )
    
        app = AceApp(query="!!!", auto_start_axe=False)
        async with app.run_test() as pilot:
>           await _wait_for_mount_state_loads(app, pilot)

tests/ace/tui/test_app_title.py:156: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

app = AceApp(title='sase tui (v0.18.1+9.gdeadbee.dirty)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
pilot = <Pilot app=AceApp(title='sase tui (v0.18.1+9.gdeadbee.dirty)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})>

    async def _wait_for_mount_state_loads(app: AceApp, pilot: Pilot[None]) -> None:
        """Poll until the title write's barrier fires, or fail with a clear message."""
        deadline = asyncio.get_running_loop().time() + 15.0
        while not app._mount_state_loads_done:
            if asyncio.get_running_loop().time() >= deadline:
>               raise AssertionError("mount state loads did not finish within 15 seconds")
E               AssertionError: mount state loads did not finish within 15 seconds

tests/ace/tui/test_app_title.py:140: AssertionError
........................................................[contention-diag] +744s soak 28p/235t rss 10.6G pss 9.7G swap 0.3G majflt 265 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.5G | host avail 34.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.19 | cgroup 10.6G/max oom_kill 0 | free scratch 329.6G/45453703i tmp 29.7G/1019839i workspace 329.6G/45453703i | scratch used 0.7G in 138444 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 5520 done 1 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
.......... [241%]
.......................................................................[contention-diag] +761s soak 31p/248t rss 10.7G pss 9.8G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.6G, 3 descendant rss 0.1G pss 0.1G | host avail 34.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.01 | cgroup 10.8G/max oom_kill 0 | free scratch 329.6G/45453352i tmp 29.7G/1019839i workspace 329.6G/45453351i | repeat-01 collected 26/26 workers (60601 items) tests 5613 done 1 failed | 26 in flight, oldest 53s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
. [245%]
.......................[contention-diag] +776s soak 31p/248t rss 10.9G pss 9.9G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.6G, 3 descendant rss 0.1G pss 0.1G | host avail 34.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.33 | cgroup 10.8G/max oom_kill 0 | free scratch 329.6G/45453116i tmp 29.7G/1019839i workspace 329.6G/45453116i | repeat-01 collected 26/26 workers (60601 items) tests 5637 done 1 failed | 26 in flight, oldest 68s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................................................. [248%]
......................................[contention-diag] +792s soak 29p/246t rss 10.8G pss 9.9G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 34.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.77 | cgroup 10.8G/max oom_kill 0 | free scratch 329.6G/45452802i tmp 29.7G/1019839i workspace 329.6G/45452802i | repeat-01 collected 26/26 workers (60601 items) tests 5719 done 1 failed | 26 in flight, oldest 83s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................................. [251%]
................................[contention-diag] +807s soak 28p/252t rss 10.8G pss 9.8G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G | host avail 33.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.13 | cgroup 10.9G/max oom_kill 0 | free scratch 329.6G/45452507i tmp 29.7G/1019839i workspace 329.6G/45452507i | repeat-01 collected 26/26 workers (60601 items) tests 5791 done 1 failed | 26 in flight, oldest 99s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................ [254%]
..................................................[contention-diag] +822s soak 29p/260t rss 10.8G pss 9.9G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 35.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.44 | cgroup 10.8G/max oom_kill 0 | free scratch 329.6G/45452182i tmp 29.7G/1019839i workspace 329.6G/45452182i | repeat-01 collected 26/26 workers (60601 items) tests 5881 done 1 failed | 26 in flight, oldest 114s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................[contention-diag] +838s soak 31p/263t rss 11.0G pss 10.0G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.7G, 3 descendant rss 0.1G pss 0.1G | host avail 37.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.55 | cgroup 10.9G/max oom_kill 0 | free scratch 329.6G/45452023i tmp 29.7G/1019839i workspace 329.6G/45452023i | repeat-01 collected 26/26 workers (60601 items) tests 5896 done 1 failed | 26 in flight, oldest 129s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..... [257%]
........................................................................ [260%]
........................................................................ [263%]
............[contention-diag] +853s soak 29p/247t rss 11.0G pss 9.9G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 1 descendant rss 0.1G pss 0.0G | host avail 37.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.61 | cgroup 10.9G/max oom_kill 0 | free scratch 329.6G/45451519i tmp 29.7G/1019839i workspace 329.6G/45451519i | repeat-01 collected 26/26 workers (60601 items) tests 6053 done 1 failed | 26 in flight, oldest 66s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
............................................................ [267%]
........................................................................ [270%]
.................................[contention-diag] +868s soak 29p/208t rss 11.0G pss 10.0G swap 0.3G majflt 267 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.8G, 1 descendant rss 0.1G pss 0.0G | host avail 36.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.03 | cgroup 10.9G/max oom_kill 0 | free scratch 329.6G/45451056i tmp 29.7G/1019839i workspace 329.6G/45451056i | scratch used 0.8G in 149247 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 6193 done 1 failed | 26 in flight, oldest 65s gw19 tests/ace/tui/test_agents_pane_mount.py::test_agents_pane_mounts_activates_and_loads
....................................... [273%]
........................................................................ [276%]
........................................................................ [279%]
.......................................................[contention-diag] +885s soak 28p/221t rss 11.0G pss 10.0G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G | host avail 37.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 36.62 | cgroup 11.0G/max oom_kill 0 | free scratch 329.6G/45450379i tmp 29.7G/1019839i workspace 329.6G/45450379i | repeat-01 collected 26/26 workers (60601 items) tests 6456 done 1 failed | 25 in flight, oldest 52s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................. [282%]
........................................................................ [285%]
................................................[contention-diag] +901s soak 31p/248t rss 11.2G pss 10.1G swap 0.3G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.9G, 3 descendant rss 0.1G pss 0.1G | host avail 37.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.0 cpu 38.54 | cgroup 11.1G/max oom_kill 0 | free scratch 329.6G/45449938i tmp 29.7G/1019837i workspace 329.6G/45449938i | repeat-01 collected 26/26 workers (60601 items) tests 6596 done 1 failed | 26 in flight, oldest 67s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
........................ [289%]
........................................................................ [292%]
..........................................[contention-diag] +916s soak 30p/235t rss 11.1G pss 10.1G swap 0.3G majflt 276 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.9G, 2 descendant rss 0.0G pss 0.0G | host avail 36.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.0 cpu 34.68 | cgroup 11.1G/max oom_kill 0 | free scratch 329.6G/45449536i tmp 29.7G/1019839i workspace 329.6G/45449536i | repeat-01 collected 26/26 workers (60601 items) tests 6726 done 1 failed | 25 in flight, oldest 49s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
.............................. [295%]
.........................[contention-diag] +931s soak 28p/233t rss 11.1G pss 10.1G swap 0.3G majflt 276 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.9G | host avail 35.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 31.42 | cgroup 11.1G/max oom_kill 0 | free scratch 329.6G/45449239i tmp 29.7G/1019839i workspace 329.6G/45449239i | repeat-01 collected 26/26 workers (60601 items) tests 6793 done 1 failed | 26 in flight, oldest 47s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
............................................... [298%]
..................[contention-diag] +946s soak 29p/222t rss 11.1G pss 10.2G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.3 | cgroup 11.1G/max oom_kill 0 | free scratch 329.6G/45448985i tmp 29.7G/1019839i workspace 329.6G/45448985i | repeat-01 collected 26/26 workers (60601 items) tests 6857 done 1 failed | 26 in flight, oldest 42s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
...................................................... [301%]
.............[contention-diag] +962s soak 30p/234t rss 11.2G pss 10.2G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 2 descendant rss 0.1G pss 0.0G | host avail 36.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.01 | cgroup 11.2G/max oom_kill 0 | free scratch 329.6G/45448706i tmp 29.7G/1019839i workspace 329.6G/45448706i | repeat-01 collected 26/26 workers (60601 items) tests 6923 done 1 failed | 26 in flight, oldest 57s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........................................................... [304%]
........................................................................ [307%]
...............................................[contention-diag] +977s soak 29p/227t rss 11.2G pss 10.2G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 36.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 39.35 | cgroup 11.2G/max oom_kill 0 | free scratch 329.6G/45448236i tmp 29.7G/1019839i workspace 329.6G/45448236i | repeat-01 collected 26/26 workers (60601 items) tests 7098 done 1 failed | 25 in flight, oldest 46s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_f_opens_files_below_and_keeps_focus
......................... [310%]
......................................................[contention-diag] +992s soak 30p/233t rss 11.3G pss 10.3G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 35.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.26 | cgroup 11.3G/max oom_kill 0 | free scratch 329.6G/45447915i tmp 29.7G/1019839i workspace 329.6G/45447915i | scratch used 0.9G in 159307 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 7177 done 1 failed | 26 in flight, oldest 46s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
.................. [314%]
.............................................................[contention-diag] +1010s soak 31p/229t rss 11.2G pss 10.2G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 3 descendant rss 0.0G pss 0.0G | host avail 36.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 34.64 | cgroup 11.3G/max oom_kill 0 | free scratch 329.6G/45447623i tmp 29.7G/1019839i workspace 329.6G/45447623i | repeat-01 collected 26/26 workers (60601 items) tests 7255 done 1 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
........... [317%]
........................................................................ [320%]
........................................................................ [323%]
...............................................................[contention-diag] +1025s soak 29p/238t rss 11.3G pss 10.3G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 36.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 41.13 | cgroup 11.3G/max oom_kill 0 | free scratch 329.6G/45447049i tmp 29.7G/1019839i workspace 329.6G/45447049i | repeat-01 collected 26/26 workers (60601 items) tests 7473 done 1 failed | 26 in flight, oldest 50s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
......... [326%]
........................................................................ [329%]
........................................................................ [332%]
...................[contention-diag] +1040s soak 39p/250t rss 11.4G pss 10.3G swap 0.3G majflt 279 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.1G, 11 descendant rss 0.2G pss 0.1G | host avail 36.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.86 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45446504i tmp 29.7G/1019839i workspace 329.6G/45446504i | repeat-01 collected 26/26 workers (60601 items) tests 7649 done 1 failed | 26 in flight, oldest 66s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
..................................................... [336%]
..[contention-diag] +1056s soak 38p/257t rss 11.4G pss 10.3G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 34.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.99 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45446278i tmp 29.7G/1019839i workspace 329.6G/45446278i | repeat-01 collected 26/26 workers (60601 items) tests 7706 done 1 failed | 26 in flight, oldest 52s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_archived_plan_reveals_through_path_context_after_scan
.....[contention-diag] +1071s soak 38p/265t rss 11.4G pss 10.3G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 34.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.53 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45446164i tmp 29.7G/1019839i workspace 329.6G/45446164i | repeat-01 collected 26/26 workers (60601 items) tests 7711 done 1 failed | 26 in flight, oldest 52s gw20 tests/ace/tui/test_link_follow_seam.py::test_closed_phase_follow_selects_without_hanging
.........................................[contention-diag] +1086s soak 38p/259t rss 11.4G pss 10.3G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 36.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.97 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45445897i tmp 29.7G/1019839i workspace 329.6G/45445897i | repeat-01 collected 26/26 workers (60601 items) tests 7752 done 1 failed | 26 in flight, oldest 49s gw7 tests/ace/tui/test_agents_tab_x_clan_race_e2e.py::test_clan_x_stays_removed_through_racing_load_fleet_refresh_and_reload
...........[contention-diag] +1101s soak 38p/264t rss 11.4G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 35.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.52 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45445749i tmp 29.7G/1019839i workspace 329.6G/45445749i | repeat-01 collected 26/26 workers (60601 items) tests 7763 done 1 failed | 26 in flight, oldest 62s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
........[contention-diag] +1117s soak 38p/283t rss 11.4G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 35.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.54 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45445604i tmp 29.7G/1019839i workspace 329.6G/45445604i | scratch used 0.9G in 165895 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 7769 done 1 failed | 26 in flight, oldest 77s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
..... [339%]
..............................................................[contention-diag] +1134s soak 38p/255t rss 11.5G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 35.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.85 | cgroup 11.5G/max oom_kill 0 | free scratch 329.6G/45445362i tmp 29.7G/1019839i workspace 329.6G/45445362i | repeat-01 collected 26/26 workers (60601 items) tests 7833 done 1 failed | 26 in flight, oldest 78s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......... [342%]
..............[contention-diag] +1149s soak 30p/263t rss 11.4G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 2 descendant rss 0.0G pss 0.0G | host avail 34.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.77 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45445156i tmp 29.7G/1019839i workspace 329.6G/45445156i | repeat-01 collected 26/26 workers (60601 items) tests 7860 done 1 failed | 26 in flight, oldest 93s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......................................................... [345%]
........................................................................ [348%]
........................................................................ [351%]
..[contention-diag] +1164s soak 28p/276t rss 11.4G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.2G | host avail 35.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.71 | cgroup 11.4G/max oom_kill 0 | free scratch 329.6G/45444625i tmp 29.7G/1019839i workspace 329.6G/45444625i | repeat-01 collected 26/26 workers (60601 items) tests 8047 done 1 failed | 26 in flight, oldest 108s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.................................................[contention-diag] +1180s soak 28p/232t rss 11.4G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.2G | host avail 33.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.85 | cgroup 11.5G/max oom_kill 0 | free scratch 329.6G/45444392i tmp 29.7G/1019839i workspace 329.6G/45444392i | repeat-01 collected 26/26 workers (60601 items) tests 8115 done 1 failed | 26 in flight, oldest 70s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
...............[contention-diag] +1195s soak 29p/230t rss 11.4G pss 10.4G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 33.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.0 cpu 27.6 | cgroup 11.5G/max oom_kill 0 | free scratch 329.6G/45444245i tmp 29.7G/1019839i workspace 329.6G/45444245i | repeat-01 collected 26/26 workers (60601 items) tests 8128 done 1 failed | 26 in flight, oldest 44s gw9 tests/ace/tui/test_config_center_alternate_tab.py::test_single_section_visited_leaves_opener_inert
...... [354%]
........................................................................ [358%]
.[contention-diag] +1210s soak 29p/238t rss 11.5G pss 10.5G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 34.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.0 cpu 36.36 | cgroup 11.5G/max oom_kill 0 | free scratch 329.6G/45443966i tmp 29.7G/1019839i workspace 329.6G/45443966i | repeat-01 collected 26/26 workers (60601 items) tests 8193 done 1 failed | 25 in flight, oldest 53s gw7 tests/ace/tui/test_config_hub_pane.py::test_opening_config_constructs_only_the_active_child
....................................................................... [361%]
........................................................................ [364%]
...............[contention-diag] +1226s soak 29p/226t rss 11.5G pss 10.5G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 35.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.0 cpu 37.7 | cgroup 11.5G/max oom_kill 0 | free scratch 329.6G/45443523i tmp 29.7G/1019839i workspace 329.6G/45443523i | repeat-01 collected 26/26 workers (60601 items) tests 8360 done 1 failed | 26 in flight, oldest 45s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
......................................................... [367%]
........................................................................ [370%]
................................[contention-diag] +1241s soak 29p/255t rss 11.5G pss 10.5G swap 0.3G majflt 280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 34.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.0 cpu 36.97 | cgroup 11.6G/max oom_kill 0 | free scratch 329.6G/45443190i tmp 29.7G/1019839i workspace 329.6G/45443190i | scratch used 0.9G in 174768 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 8488 done 1 failed | 26 in flight, oldest 60s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
........................................ [373%]
........................................................................ [376%]
........................................................................ [380%]
....................................[contention-diag] +1258s soak 28p/259t rss 11.5G pss 10.5G swap 0.3G majflt 318 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G | host avail 34.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 36.89 | cgroup 11.6G/max oom_kill 0 | free scratch 329.6G/45442527i tmp 29.7G/1019837i workspace 329.6G/45442527i | repeat-01 collected 26/26 workers (60601 items) tests 8734 done 1 failed | 26 in flight, oldest 71s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................... [383%]
........................................................................ [386%]
.............................[contention-diag] +1273s soak 28p/248t rss 11.5G pss 10.5G swap 0.3G majflt 374 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G | host avail 34.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.85 | cgroup 11.6G/max oom_kill 0 | free scratch 329.5G/45442152i tmp 29.7G/1019839i workspace 329.5G/45442152i | repeat-01 collected 26/26 workers (60601 items) tests 8883 done 1 failed | 26 in flight, oldest 86s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................................... [389%]
........................................................................ [392%]
..........[contention-diag] +1289s soak 28p/249t rss 11.6G pss 10.5G swap 0.3G majflt 374 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G | host avail 34.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.03 | cgroup 11.6G/max oom_kill 0 | free scratch 329.6G/45441788i tmp 29.7G/1019839i workspace 329.6G/45441788i | repeat-01 collected 26/26 workers (60601 items) tests 9005 done 1 failed | 26 in flight, oldest 101s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............................................................. [395%]
..............................................................[contention-diag] +1304s soak 28p/261t rss 11.6G pss 10.6G swap 0.3G majflt 374 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G | host avail 33.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.02 | cgroup 11.7G/max oom_kill 0 | free scratch 329.5G/45441415i tmp 29.7G/1019839i workspace 329.5G/45441415i | repeat-01 collected 26/26 workers (60601 items) tests 9133 done 1 failed | 26 in flight, oldest 117s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.......... [398%]
........................................................................ [402%]
.......................................................................[contention-diag] +1319s soak 29p/235t rss 11.8G pss 10.8G swap 0.3G majflt 374 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.4G, 1 descendant rss 0.1G pss 0.1G | host avail 33.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.64 | cgroup 11.8G/max oom_kill 0 | free scratch 329.5G/45440974i tmp 29.7G/1019839i workspace 329.5G/45440974i | repeat-01 collected 26/26 workers (60601 items) tests 9284 done 1 failed | 26 in flight, oldest 132s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
. [405%]
...........................[contention-diag] +1335s soak 29p/246t rss 11.7G pss 10.6G swap 0.3G majflt 374 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 34.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.58 | cgroup 11.7G/max oom_kill 0 | free scratch 329.5G/45440861i tmp 29.7G/1019839i workspace 329.5G/45440861i | repeat-01 collected 26/26 workers (60601 items) tests 9309 done 1 failed | 25 in flight, oldest 147s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................. [408%]
........[contention-diag] +1350s soak 29p/246t rss 11.7G pss 10.7G swap 0.3G majflt 375 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 34.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 37.45 | cgroup 11.7G/max oom_kill 0 | free scratch 329.5G/45440625i tmp 29.7G/1019839i workspace 329.5G/45440625i | repeat-01 collected 26/26 workers (60601 items) tests 9364 done 1 failed | 26 in flight, oldest 163s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..............................[contention-diag] +1365s soak 28p/255t rss 11.7G pss 10.6G swap 0.3G majflt 376 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G | host avail 33.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 35.43 | cgroup 11.8G/max oom_kill 0 | free scratch 329.5G/45440427i tmp 29.7G/1019839i workspace 329.5G/45440427i | scratch used 1.0G in 182800 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 9392 done 1 failed | 26 in flight, oldest 88s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................................. [411%]
..............[contention-diag] +1382s soak 29p/253t rss 11.7G pss 10.7G swap 0.3G majflt 378 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 35.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.07 | cgroup 11.8G/max oom_kill 0 | free scratch 329.5G/45440129i tmp 29.7G/1019839i workspace 329.5G/45440129i | repeat-01 collected 26/26 workers (60601 items) tests 9446 done 1 failed | 26 in flight, oldest 105s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.......................................................[contention-diag] +1398s soak 28p/254t rss 11.7G pss 10.7G swap 0.3G majflt 378 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G | host avail 34.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 41.39 | cgroup 11.8G/max oom_kill 0 | free scratch 329.5G/45439987i tmp 29.7G/1019839i workspace 329.5G/45439987i | repeat-01 collected 26/26 workers (60601 items) tests 9497 done 1 failed | 26 in flight, oldest 120s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
... [414%]
...........................................................[contention-diag] +1413s soak 29p/248t rss 11.8G pss 10.7G swap 0.3G majflt 379 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 32.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.95 | cgroup 11.8G/max oom_kill 0 | free scratch 329.5G/45439693i tmp 29.7G/1019839i workspace 329.5G/45439693i | repeat-01 collected 26/26 workers (60601 items) tests 9559 done 1 failed | 26 in flight, oldest 136s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............. [417%]
..........................[contention-diag] +1428s soak 28p/249t rss 11.7G pss 10.7G swap 0.3G majflt 379 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.5G | host avail 32.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.36 | cgroup 11.8G/max oom_kill 0 | free scratch 329.5G/45439248i tmp 29.7G/1019839i workspace 329.5G/45439248i | repeat-01 collected 26/26 workers (60601 items) tests 9602 done 1 failed | 26 in flight, oldest 151s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
......................................[contention-diag] +1444s soak 30p/242t rss 11.8G pss 10.8G swap 0.3G majflt 379 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.5G, 2 descendant rss 0.1G pss 0.1G | host avail 33.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.53 | cgroup 11.9G/max oom_kill 0 | free scratch 329.5G/45439315i tmp 29.7G/1019839i workspace 329.5G/45439315i | repeat-01 collected 26/26 workers (60601 items) tests 9638 done 1 failed | 26 in flight, oldest 86s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........ [420%]
......[contention-diag] +1459s soak 29p/260t rss 11.9G pss 10.9G swap 0.3G majflt 379 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 37.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.64 | cgroup 12.0G/max oom_kill 0 | free scratch 329.5G/45439134i tmp 29.7G/1019839i workspace 329.5G/45439134i | repeat-01 collected 26/26 workers (60601 items) tests 9650 done 1 failed | 26 in flight, oldest 101s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................................. [424%]
..[contention-diag] +1474s soak 28p/261t rss 11.8G pss 10.8G swap 0.3G majflt 379 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G | host avail 37.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.94 | cgroup 11.9G/max oom_kill 0 | free scratch 329.5G/45438878i tmp 29.7G/1019839i workspace 329.5G/45438878i | repeat-01 collected 26/26 workers (60601 items) tests 9706 done 1 failed | 26 in flight, oldest 116s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................................... [427%]
........................................................................ [430%]
........................................................................ [433%]
......................[contention-diag] +1490s soak 28p/250t rss 11.8G pss 10.8G swap 0.3G majflt 379 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G | host avail 36.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.18 | cgroup 12.0G/max oom_kill 0 | free scratch 329.5G/45438357i tmp 29.7G/1019839i workspace 329.5G/45438357i | scratch used 1.0G in 189714 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 9934 done 1 failed | 26 in flight, oldest 132s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................. [436%]
........................................................................ [439%]
..............[contention-diag] +1507s soak 30p/261t rss 11.9G pss 10.8G swap 0.3G majflt 382 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 36.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 36.99 | cgroup 12.0G/max oom_kill 0 | free scratch 329.5G/45437892i tmp 29.7G/1019839i workspace 329.5G/45437892i | repeat-01 collected 26/26 workers (60601 items) tests 10083 done 1 failed | 26 in flight, oldest 149s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................................................... [442%]
.....[contention-diag] +1522s soak 29p/264t rss 11.9G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 36.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 43.33 | cgroup 12.0G/max oom_kill 0 | free scratch 329.5G/45437625i tmp 29.7G/1019839i workspace 329.5G/45437625i | repeat-01 collected 26/26 workers (60601 items) tests 10156 done 1 failed | 26 in flight, oldest 164s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................................... [446%]
[contention-diag] +1538s soak 29p/262t rss 11.9G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 36.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.0 cpu 33.77 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45437363i tmp 29.7G/1019839i workspace 329.5G/45437363i | repeat-01 collected 26/26 workers (60601 items) tests 10220 done 1 failed | 26 in flight, oldest 180s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.........................[contention-diag] +1553s soak 30p/292t rss 12.0G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.0 cpu 29.77 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45437225i tmp 29.7G/1019839i workspace 329.5G/45437225i | repeat-01 collected 26/26 workers (60601 items) tests 10247 done 1 failed | 26 in flight, oldest 195s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................... [449%]
........................................................................ [452%]
....[contention-diag] +1568s soak 29p/257t rss 11.9G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 33.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.88 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45436707i tmp 29.7G/1019839i workspace 329.5G/45436707i | repeat-01 collected 26/26 workers (60601 items) tests 10362 done 1 failed | 26 in flight, oldest 210s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................................... [455%]
...[contention-diag] +1583s soak 28p/252t rss 11.9G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G | host avail 35.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.47 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45436609i tmp 29.7G/1019839i workspace 329.5G/45436609i | repeat-01 collected 26/26 workers (60601 items) tests 10440 done 1 failed | 26 in flight, oldest 226s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..............................................................[contention-diag] +1599s soak 30p/281t rss 12.0G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 36.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.51 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45436361i tmp 29.7G/1019839i workspace 329.5G/45436361i | repeat-01 collected 26/26 workers (60601 items) tests 10495 done 1 failed | 26 in flight, oldest 241s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....... [458%]
......................................................[contention-diag] +1614s soak 29p/279t rss 12.0G pss 10.9G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.29 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45436125i tmp 29.7G/1019839i workspace 329.5G/45436125i | scratch used 1.0G in 194037 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 10563 done 1 failed | 26 in flight, oldest 256s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [461%]
...................................[contention-diag] +1631s soak 28p/272t rss 12.0G pss 11.0G swap 0.3G majflt 385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G | host avail 35.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 38.48 | cgroup 12.2G/max oom_kill 0 | free scratch 329.5G/45435907i tmp 29.7G/1019839i workspace 329.5G/45435907i | repeat-01 collected 26/26 workers (60601 items) tests 10618 done 1 failed | 26 in flight, oldest 273s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................[contention-diag] +1646s soak 28p/272t rss 12.0G pss 10.9G swap 0.3G majflt 388 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G | host avail 35.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 41.0 | cgroup 12.1G/max oom_kill 0 | free scratch 329.5G/45435722i tmp 29.7G/1019839i workspace 329.5G/45435722i | repeat-01 collected 26/26 workers (60601 items) tests 10644 done 1 failed | 26 in flight, oldest 75s gw3 tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
.. [464%]
........................................................................ [468%]
........................................................................ [471%]
..........................[contention-diag] +1662s soak 32p/263t rss 12.0G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 35.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 36.41 | cgroup 12.2G/max oom_kill 0 | free scratch 329.5G/45435102i tmp 29.7G/1019839i workspace 329.5G/45435102i | repeat-01 collected 26/26 workers (60601 items) tests 10810 done 1 failed | 26 in flight, oldest 45s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hint_moves_cursor_and_repaints_detail
........................................[contention-diag] +1677s soak 30p/265t rss 12.0G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 33.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 27.8 | cgroup 12.2G/max oom_kill 0 | free scratch 329.5G/45434751i tmp 29.7G/1019839i workspace 329.5G/45434751i | repeat-01 collected 26/26 workers (60601 items) tests 10860 done 1 failed | 26 in flight, oldest 44s gw12 tests/ace/tui/test_plugins_browser_pane_marks.py::test_cli_mark_consumed_by_update_when_cli_rows_hidden
...... [474%]
........................................................................ [477%]
........................................................................ [480%]
........................................................................ [483%]
.......................[contention-diag] +1692s soak 29p/268t rss 12.1G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 34.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 33.72 | cgroup 12.2G/max oom_kill 0 | free scratch 329.5G/45434361i tmp 29.7G/1019839i workspace 329.5G/45434361i | repeat-01 collected 26/26 workers (60601 items) tests 11106 done 1 failed | 25 in flight, oldest 54s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_invalid_draft_surfaces_in_status_and_blocks_preview
........................F[contention-failure] call tests/ace/tui/test_macro_browser_load_keymap.py::test_enter_returns_while_macro_file_read_is_blocked: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb0bf306120>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw16/test_enter_returns_while_macro0')

    async def test_enter_returns_while_macro_file_read_is_blocked(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        source = tmp_path / "slow.md"
        source.write_text("Slow definition body.", encoding="utf-8")
        prompts = {
            "slow": _md_macro(
                "slow",
                "Slow definition body.",
                source_path=str(source),
            )
        }
        started = Event()
        release = Event()
        original_read_text = Path.read_text
    
        def slow_read_text(path: Path, *args: object, **kwargs: object) -> str:
            if path == source:
                started.set()
                release.wait()
            return original_read_text(path, *args, **kwargs)  # type: ignore[arg-type]
    
        monkeypatch.setattr(Path, "read_text", slow_read_text)
    
        async with AcePage() as page:
            _, pane = await _open_macros_tab(page, monkeypatch, prompts)
            try:
                assert pane.action_edit_macro() is None
                assert await asyncio.wait_for(
                    asyncio.to_thread(started.wait, 10.0), timeout=11.0
                )
                heartbeat = asyncio.Event()
                asyncio.get_running_loop().call_soon(heartbeat.set)
                await asyncio.wait_for(heartbeat.wait(), timeout=2.0)
            finally:
                release.set()
>               await page.wait_for(
                    lambda _s: (
                        bool(page.app.query("#prompt-input-bar"))
                        and bool(page.app.query("PromptTextArea"))
                    ),
                    timeout=10.0,
                )

tests/ace/tui/test_macro_browser_load_keymap.py:199: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:563: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb0e90b1ee0>

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
    
        deadline = cloc
...[contention-diag] +1708s soak 31p/298t rss 12.0G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 35.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.55 | cgroup 12.2G/max oom_kill 0 | free scratch 329.5G/45434063i tmp 29.7G/1019839i workspace 329.5G/45434063i | repeat-01 collected 26/26 workers (60601 items) tests 11137 done 2 failed | 26 in flight, oldest 50s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
..................... [486%]
........................................................................ [490%]
[contention-diag] +1723s soak 30p/256t rss 12.1G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 35.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 41.38 | cgroup 12.2G/max oom_kill 0 | free scratch 329.5G/45433734i tmp 29.7G/1019839i workspace 329.5G/45433734i | repeat-01 collected 26/26 workers (60601 items) tests 11180 done 2 failed | 26 in flight, oldest 66s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........................................................................ [493%]
.................................................................[contention-diag] +1738s soak 31p/266t rss 12.1G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 3 descendant rss 0.1G pss 0.0G | host avail 34.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.58 | cgroup 12.3G/max oom_kill 0 | free scratch 329.5G/45433341i tmp 29.7G/1019839i workspace 329.5G/45433341i | scratch used 1.0G in 197924 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 11352 done 2 failed | 26 in flight, oldest 81s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
....... [496%]
......................................................[contention-diag] +1756s soak 30p/283t rss 12.1G pss 11.1G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 33.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.02 | cgroup 12.3G/max oom_kill 0 | free scratch 329.5G/45433055i tmp 29.7G/1019839i workspace 329.5G/45433055i | repeat-01 collected 26/26 workers (60601 items) tests 11427 done 2 failed | 26 in flight, oldest 98s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.................. [499%]
..............................................[contention-diag] +1771s soak 30p/271t rss 12.1G pss 11.1G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.69 | cgroup 12.3G/max oom_kill 0 | free scratch 329.5G/45432857i tmp 29.7G/1019839i workspace 329.5G/45432857i | repeat-01 collected 26/26 workers (60601 items) tests 11491 done 2 failed | 26 in flight, oldest 51s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
.......................... [502%]
........................................................................ [505%]
........................................................................ [508%]
..................[contention-diag] +1786s soak 28p/258t rss 12.1G pss 11.0G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G | host avail 33.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.89 | cgroup 12.3G/max oom_kill 0 | free scratch 329.5G/45432147i tmp 29.7G/1019839i workspace 329.5G/45432147i | repeat-01 collected 26/26 workers (60601 items) tests 11682 done 2 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
.................................................[contention-diag] +1802s soak 29p/268t rss 12.1G pss 11.1G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 32.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.07 | cgroup 12.4G/max oom_kill 0 | free scratch 329.5G/45431940i tmp 29.7G/1019839i workspace 329.5G/45431940i | repeat-01 collected 26/26 workers (60601 items) tests 11729 done 2 failed | 26 in flight, oldest 48s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_enter_loads_raw_definition_and_binds_source
..... [512%]
........................................................................ [515%]
....................[contention-diag] +1817s soak 29p/245t rss 12.2G pss 11.1G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 33.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.42 | cgroup 12.4G/max oom_kill 0 | free scratch 329.5G/45431607i tmp 29.7G/1019839i workspace 329.5G/45431607i | repeat-01 collected 26/26 workers (60601 items) tests 11821 done 2 failed | 26 in flight, oldest 47s gw8 tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_lazy_plugin_latest_survives_reopen
.................................................[contention-diag] +1832s soak 29p/248t rss 12.2G pss 11.1G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 34.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.51 | cgroup 12.4G/max oom_kill 0 | free scratch 329.5G/45431371i tmp 29.7G/1019839i workspace 329.5G/45431371i | repeat-01 collected 26/26 workers (60601 items) tests 11875 done 2 failed | 26 in flight, oldest 39s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
... [518%]
...............................[contention-diag] +1848s soak 31p/268t rss 12.2G pss 11.2G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 3 descendant rss 0.1G pss 0.1G | host avail 34.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.93 | cgroup 12.4G/max oom_kill 0 | free scratch 329.5G/45431248i tmp 29.7G/1019839i workspace 329.5G/45431248i | repeat-01 collected 26/26 workers (60601 items) tests 11907 done 2 failed | 26 in flight, oldest 54s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
......................................... [521%]
........................................................................ [524%]
..............[contention-diag] +1863s soak 32p/266t rss 12.3G pss 11.2G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 4 descendant rss 0.1G pss 0.1G | host avail 34.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 37.93 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45430842i tmp 29.7G/1019837i workspace 329.5G/45430842i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 12031 done 2 failed | 26 in flight, oldest 69s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.......................................................... [527%]
...........................[contention-diag] +1880s soak 30p/258t rss 12.3G pss 11.2G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 2 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.13 cpu 33.08 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45430349i tmp 29.7G/1019837i workspace 329.5G/45430348i | repeat-01 collected 26/26 workers (60601 items) tests 12121 done 2 failed | 26 in flight, oldest 87s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
............................................. [530%]
........................................................................ [534%]
......[contention-diag] +1895s soak 32p/259t rss 12.3G pss 11.2G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 4 descendant rss 0.1G pss 0.0G | host avail 34.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.17 cpu 30.73 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45429920i tmp 29.7G/1019837i workspace 329.5G/45429920i | repeat-01 collected 26/26 workers (60601 items) tests 12235 done 2 failed | 26 in flight, oldest 41s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_is_inert_for_yaml_backed_rows
.................................................................. [537%]
........................................................................ [540%]
.....................................................[contention-diag] +1910s soak 31p/240t rss 12.2G pss 11.2G swap 0.3G majflt 390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 3 descendant rss 0.0G pss 0.0G | host avail 33.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.38 cpu 27.0 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45429452i tmp 29.7G/1019837i workspace 329.5G/45429452i | repeat-01 collected 26/26 workers (60601 items) tests 12431 done 2 failed | 26 in flight, oldest 51s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
................... [543%]
........................................................................ [546%]
............................................................[contention-diag] +1926s soak 30p/255t rss 12.3G pss 11.2G swap 0.3G majflt 430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 2 descendant rss 0.1G pss 0.0G | host avail 32.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.09 cpu 28.02 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45429070i tmp 29.7G/1019836i workspace 329.5G/45429070i | repeat-01 collected 26/26 workers (60601 items) tests 12582 done 2 failed | 26 in flight, oldest 46s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
............ [549%]
........................................................................ [552%]
........................................................................ [556%]
........................................................................ [559%]
.............[contention-diag] +1941s soak 31p/257t rss 12.3G pss 11.2G swap 0.3G majflt 393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 32.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.87 cpu 26.78 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45428389i tmp 29.7G/1019836i workspace 329.5G/45428389i | repeat-01 collected 26/26 workers (60601 items) tests 12828 done 2 failed | 26 in flight, oldest 46s gw12 tests/ace/tui/test_plugins_browser_pane_marks.py::test_cli_install_mark_stays_inside_agent_cli_section
........................................................... [562%]
[contention-diag] +1956s soak 29p/261t rss 12.3G pss 11.2G swap 0.3G majflt 393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 33.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 29.48 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45428342i tmp 29.7G/1019836i workspace 329.5G/45428342i | repeat-01 collected 26/26 workers (60601 items) tests 12885 done 2 failed | 26 in flight, oldest 48s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree
........................................................................ [565%]
........................................................................ [568%]
................................................................[contention-diag] +1972s soak 28p/249t rss 12.3G pss 11.2G swap 0.3G majflt 393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G | host avail 33.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 28.05 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45427764i tmp 29.7G/1019836i workspace 329.5G/45427764i | repeat-01 collected 26/26 workers (60601 items) tests 13092 done 2 failed | 26 in flight, oldest 47s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
........ [571%]
........................................................................ [574%]
........................................................................ [578%]
....................[contention-diag] +1987s soak 31p/244t rss 12.3G pss 11.2G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.09 cpu 31.21 | cgroup 12.5G/max oom_kill 0 | free scratch 329.5G/45427422i tmp 29.7G/1019836i workspace 329.5G/45427421i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 13216 done 2 failed | 26 in flight, oldest 63s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.................................................... [581%]
........................................................................ [584%]
........................................................................ [587%]
.[contention-diag] +2004s soak 31p/234t rss 12.4G pss 11.3G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 3 descendant rss 0.0G pss 0.0G | host avail 34.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.55 cpu 34.33 | cgroup 12.6G/max oom_kill 0 | free scratch 329.5G/45426818i tmp 29.7G/1019836i workspace 329.5G/45426818i | repeat-01 collected 26/26 workers (60601 items) tests 13456 done 2 failed | 26 in flight, oldest 71s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
...................................................................[contention-diag] +2019s soak 34p/264t rss 12.5G pss 11.4G swap 0.3G majflt 547 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 6 descendant rss 0.1G pss 0.1G | host avail 34.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.47 cpu 31.06 | cgroup 12.6G/max oom_kill 0 | free scratch 329.5G/45426329i tmp 29.7G/1019836i workspace 329.5G/45426329i | repeat-01 collected 26/26 workers (60601 items) tests 13523 done 2 failed | 26 in flight, oldest 60s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_updates_title_match_count
.... [590%]
......................................[contention-diag] +2035s soak 39p/278t rss 12.5G pss 11.4G swap 0.3G majflt 2649 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 11 descendant rss 0.1G pss 0.1G | host avail 32.5G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.51/0.51 io 3.06 cpu 25.81 | cgroup 12.7G/max oom_kill 0 | free scratch 329.5G/45426006i tmp 29.7G/1019836i workspace 329.5G/45426006i | repeat-01 collected 26/26 workers (60601 items) tests 13571 done 2 failed | 26 in flight, oldest 50s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.................................. [593%]
........................................................................ [596%]
.[contention-diag] +2050s soak 33p/290t rss 12.6G pss 11.4G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 5 descendant rss 0.2G pss 0.2G | host avail 33.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 2.07 cpu 28.26 | cgroup 12.8G/max oom_kill 0 | free scratch 329.5G/45425624i tmp 29.7G/1019836i workspace 329.5G/45425624i | repeat-01 collected 26/26 workers (60601 items) tests 13676 done 2 failed | 26 in flight, oldest 66s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
....................................................................... [600%]
.............................[contention-diag] +2065s soak 33p/274t rss 12.5G pss 11.4G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 32.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.57 cpu 24.83 | cgroup 12.8G/max oom_kill 0 | free scratch 329.5G/45425252i tmp 29.7G/1019836i workspace 329.5G/45425252i | repeat-01 collected 26/26 workers (60601 items) tests 13777 done 2 failed | 26 in flight, oldest 81s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
........................................... [603%]
........................................[contention-diag] +2081s soak 30p/254t rss 12.5G pss 11.4G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.1G, 2 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.01 cpu 27.08 | cgroup 12.9G/max oom_kill 0 | free scratch 329.5G/45424899i tmp 29.7G/1019836i workspace 329.5G/45424899i | repeat-01 collected 26/26 workers (60601 items) tests 13862 done 2 failed | 26 in flight, oldest 96s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
................................ [606%]
........................................................................ [609%]
............................[contention-diag] +2096s soak 30p/235t rss 12.4G pss 11.3G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.1G, 2 descendant rss 0.0G pss 0.0G | host avail 36.0G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 28.21 | cgroup 12.8G/max oom_kill 0 | free scratch 329.5G/45424450i tmp 29.7G/1019836i workspace 329.5G/45424450i | repeat-01 collected 26/26 workers (60601 items) tests 13992 done 2 failed | 26 in flight, oldest 54s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[p-sase-SASE]
............................................ [612%]
...........................................[contention-diag] +2111s soak 28p/235t rss 12.4G pss 11.3G swap 0.3G majflt 394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.1G | host avail 36.7G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.45 cpu 29.72 | cgroup 12.9G/max oom_kill 0 | free scratch 329.5G/45424135i tmp 29.7G/1019836i workspace 329.5G/45424135i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 14060 done 2 failed | 26 in flight, oldest 32s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle
............................. [615%]
........................................................................ [618%]
...............................................[contention-diag] +2129s soak 30p/275t rss 12.5G pss 11.4G swap 0.3G majflt 395 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 2 descendant rss 0.0G pss 0.0G | host avail 36.2G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.69 cpu 34.03 | cgroup 12.9G/max oom_kill 0 | free scratch 329.5G/45423291i tmp 29.7G/1019836i workspace 329.5G/45423291i | repeat-01 collected 26/26 workers (60601 items) tests 14229 done 2 failed | 26 in flight, oldest 49s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle
......................... [621%]
........................................................................ [625%]
........................................................................ [628%]
....................................................................[contention-diag] +2144s soak 35p/256t rss 12.5G pss 11.4G swap 0.3G majflt 406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 7 descendant rss 0.0G pss 0.0G | host avail 35.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.06 cpu 31.43 | cgroup 12.9G/max oom_kill 0 | free scratch 329.5G/45422239i tmp 29.7G/1019836i workspace 329.5G/45422239i | repeat-01 collected 26/26 workers (60601 items) tests 14456 done 2 failed | 25 in flight, oldest 52s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
.... [631%]
........................................................................ [634%]
........................................................................ [637%]
...............................................[contention-diag] +2159s soak 33p/254t rss 12.6G pss 11.5G swap 0.3G majflt 409 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.2G, 5 descendant rss 0.1G pss 0.0G | host avail 35.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.78 cpu 25.69 | cgroup 13.0G/max oom_kill 0 | free scratch 329.4G/45421962i tmp 29.7G/1019836i workspace 329.4G/45421962i | repeat-01 collected 26/26 workers (60601 items) tests 14658 done 2 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
......................... [640%]
........................................................................ [643%]
............................................[contention-diag] +2174s soak 30p/245t rss 12.5G pss 11.4G swap 0.3G majflt 411 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.2G, 2 descendant rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 1.05 cpu 26.07 | cgroup 13.0G/max oom_kill 0 | free scratch 329.4G/45421674i tmp 29.7G/1019836i workspace 329.4G/45421674i | repeat-01 collected 26/26 workers (60601 items) tests 14802 done 2 failed | 26 in flight, oldest 50s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_deck_close_each_and_erase_through_keys
............................ [647%]
........................................................................ [650%]
....[contention-diag] +2190s soak 29p/247t rss 12.5G pss 11.4G swap 0.3G majflt 412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.2G, 1 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.46 cpu 26.31 | cgroup 12.9G/max oom_kill 0 | free scratch 329.4G/45420696i tmp 29.7G/1019836i workspace 329.4G/45420696i | repeat-01 collected 26/26 workers (60601 items) tests 14908 done 2 failed | 26 in flight, oldest 39s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
.................................................................... [653%]
........................................................................ [656%]
........................................................................ [659%]
....[contention-diag] +2205s soak 31p/259t rss 12.6G pss 11.5G swap 0.3G majflt 412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.2G, 3 descendant rss 0.1G pss 0.1G | host avail 33.6G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.62 cpu 26.2 | cgroup 13.0G/max oom_kill 0 | free scratch 329.4G/45419521i tmp 29.7G/1019836i workspace 329.4G/45419521i | repeat-01 collected 26/26 workers (60601 items) tests 15110 done 2 failed | 26 in flight, oldest 51s gw23 tests/ace/tui/test_notification_jump_to_agent_reveal.py::test_real_app_notification_jump_expands_collapsed_clan
.................................................................... [662%]
........................................................................ [665%]
........................................................................ [669%]
........................................................................ [672%]
.................................................[contention-diag] +2220s soak 30p/244t rss 12.6G pss 11.5G swap 0.3G majflt 412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 2 descendant rss 0.1G pss 0.1G | host avail 33.9G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.56 cpu 27.64 | cgroup 13.0G/max oom_kill 0 | free scratch 329.4G/45418257i tmp 29.7G/1019835i workspace 329.4G/45418257i | repeat-01 collected 26/26 workers (60601 items) tests 15440 done 2 failed | 26 in flight, oldest 56s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
....................... [675%]
........................................................................ [678%]
......................................[contention-diag] +2236s soak 31p/247t rss 12.7G pss 11.6G swap 0.3G majflt 421 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.3G, 3 descendant rss 0.1G pss 0.0G | host avail 34.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.46 cpu 28.43 | cgroup 13.1G/max oom_kill 0 | free scratch 329.4G/45417523i tmp 29.7G/1019836i workspace 329.4G/45417523i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 15577 done 2 failed | 26 in flight, oldest 71s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
.................................. [681%]
........................................................................ [684%]
..................................[contention-diag] +2253s soak 31p/238t rss 12.7G pss 11.6G swap 0.3G majflt 421 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.3G, 3 descendant rss 0.1G pss 0.0G | host avail 35.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.31/0.22 io 2.33 cpu 30.72 | cgroup 13.1G/max oom_kill 0 | free scratch 329.4G/45416647i tmp 29.7G/1019836i workspace 329.4G/45416647i | repeat-01 collected 26/26 workers (60601 items) tests 15723 done 2 failed | 26 in flight, oldest 84s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................................... [687%]
........................................................................ [691%]
........................................................................ [694%]
........................................................................ [697%]
...[contention-diag] +2268s soak 36p/268t rss 12.7G pss 11.6G swap 0.3G majflt 421 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.3G, 8 descendant rss 0.1G pss 0.0G | host avail 35.1G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.07/0.05 io 3.52 cpu 32.17 | cgroup 13.1G/max oom_kill 0 | free scratch 329.4G/45415639i tmp 29.7G/1019836i workspace 329.4G/45415639i | repeat-01 collected 26/26 workers (60601 items) tests 15970 done 2 failed | 26 in flight, oldest 100s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
..................................................................... [700%]
........................................................................ [703%]
........................................................................ [706%]
........................................................................ [709%]
...[contention-diag] +2284s soak 34p/277t rss 12.7G pss 11.6G swap 0.3G majflt 423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.3G, 6 descendant rss 0.1G pss 0.1G | host avail 33.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 2.35 cpu 29.68 | cgroup 13.1G/max oom_kill 0 | free scratch 329.4G/45414744i tmp 29.7G/1019836i workspace 329.4G/45414744i | repeat-01 collected 26/26 workers (60601 items) tests 16267 done 2 failed | 26 in flight, oldest 115s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
..................................................................... [713%]
........................................................................ [716%]
................[contention-diag] +2299s soak 40p/262t rss 13.0G pss 11.8G swap 0.3G majflt 425 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.3G, 12 descendant rss 0.3G pss 0.2G | host avail 33.8G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 1.56 cpu 25.33 | cgroup 13.3G/max oom_kill 0 | free scratch 329.4G/45413762i tmp 29.7G/1019836i workspace 329.4G/45413762i | repeat-01 collected 26/26 workers (60601 items) tests 16418 done 2 failed | 26 in flight, oldest 130s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................................ [719%]
........................................................................ [722%]
.....................................................................[contention-diag] +2314s soak 32p/254t rss 12.8G pss 11.7G swap 0.3G majflt 435 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 4 descendant rss 0.1G pss 0.1G | host avail 34.4G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 2.33 cpu 27.54 | cgroup 13.2G/max oom_kill 0 | free scratch 329.4G/45413327i tmp 29.7G/1019836i workspace 329.4G/45413327i | repeat-01 collected 26/26 workers (60601 items) tests 16626 done 2 failed | 26 in flight, oldest 146s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
... [725%]
........................................................................ [728%]
........................................................................ [731%]
..............................[contention-diag] +2330s soak 31p/270t rss 12.8G pss 11.6G swap 0.3G majflt 427 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 3 descendant rss 0.1G pss 0.0G | host avail 33.3G/62.7G swapfree 57.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.64 cpu 27.91 | cgroup 13.2G/max oom_kill 0 | free scratch 329.4G/45414982i tmp 29.7G/1019836i workspace 329.4G/45414982i | repeat-01 collected 26/26 workers (60601 items) tests 16797 done 2 failed | 26 in flight, oldest 97s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.......................................... [735%]
........................................................................ [738%]
........................................................................ [741%]
........................................................................ [744%]
....................................[contention-diag] +2345s soak 35p/279t rss 12.8G pss 11.7G swap 0.4G majflt 442 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 7 descendant rss 0.1G pss 0.1G | host avail 34.9G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 3.52 cpu 25.12 | cgroup 13.2G/max oom_kill 0 | free scratch 329.4G/45413815i tmp 29.7G/1019836i workspace 329.4G/45413815i | repeat-01 collected 26/26 workers (60601 items) tests 17092 done 2 failed | 26 in flight, oldest 112s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.................................... [747%]
........................................................................ [750%]
........................................................................ [753%]
........................................................................ [757%]
..........................................[contention-diag] +2360s soak 36p/269t rss 12.8G pss 11.7G swap 0.4G majflt 458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 8 descendant rss 0.1G pss 0.1G | host avail 34.2G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 3.37 cpu 29.07 | cgroup 13.4G/max oom_kill 0 | free scratch 329.4G/45413114i tmp 29.7G/1019836i workspace 329.4G/45413114i | scratch used 1.0G in 187127 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 17315 done 2 failed | 26 in flight, oldest 73s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.............................. [760%]
........................................................................ [763%]
........................................................................ [766%]
........................................................................ [769%]
................................[contention-diag] +2378s soak 33p/241t rss 12.8G pss 11.7G swap 0.4G majflt 459 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 5 descendant rss 0.1G pss 0.1G | host avail 33.4G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.02 cpu 25.76 | cgroup 13.4G/max oom_kill 0 | free scratch 329.4G/45412141i tmp 29.7G/1019836i workspace 329.4G/45412141i | repeat-01 collected 26/26 workers (60601 items) tests 17666 done 2 failed | 26 in flight, oldest 91s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........................................ [772%]
........................................................................ [775%]
........................................................................ [779%]
.......................[contention-diag] +2393s soak 32p/239t rss 12.8G pss 11.6G swap 0.4G majflt 453 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 34.7G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.7 cpu 30.83 | cgroup 13.4G/max oom_kill 0 | free scratch 329.4G/45411637i tmp 29.7G/1019836i workspace 329.4G/45411637i | repeat-01 collected 26/26 workers (60601 items) tests 17867 done 2 failed | 26 in flight, oldest 106s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
................................................. [782%]
........................................................................ [785%]
[contention-diag] +2408s soak 32p/250t rss 12.8G pss 11.7G swap 0.4G majflt 453 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 29.41 | cgroup 13.3G/max oom_kill 0 | free scratch 329.4G/45411310i tmp 29.7G/1019836i workspace 329.4G/45411310i | repeat-01 collected 26/26 workers (60601 items) tests 17994 done 2 failed | 26 in flight, oldest 122s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........................................................................ [788%]
........................................................................ [791%]
........................................................................ [794%]
.........[contention-diag] +2424s soak 36p/244t rss 12.9G pss 11.7G swap 0.4G majflt 458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 8 descendant rss 0.1G pss 0.0G | host avail 33.5G/62.7G swapfree 57.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 28.38 | cgroup 13.3G/max oom_kill 0 | free scratch 329.4G/45410691i tmp 29.7G/1019836i workspace 329.4G/45410691i | repeat-01 collected 26/26 workers (60601 items) tests 18221 done 2 failed | 26 in flight, oldest 76s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................................... [797%]
.............................................[contention-diag] +2439s soak 41p/254t rss 13.0G pss 11.8G swap 0.4G majflt 458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 13 descendant rss 0.1G pss 0.1G | host avail 33.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.54/0.36 io 0.93 cpu 26.02 | cgroup 13.4G/max oom_kill 0 | free scratch 329.4G/45410284i tmp 29.7G/1019836i workspace 329.4G/45410284i | repeat-01 collected 26/26 workers (60601 items) tests 18331 done 2 failed | 26 in flight, oldest 92s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
........................... [801%]
........................................................................ [804%]
........................................................................ [807%]
.............[contention-diag] +2454s soak 32p/246t rss 12.9G pss 11.8G swap 0.4G majflt 458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 4 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.1/0.07 io 1.42 cpu 29.29 | cgroup 13.5G/max oom_kill 0 | free scratch 329.4G/45409871i tmp 29.7G/1019836i workspace 329.4G/45409871i | repeat-01 collected 26/26 workers (60601 items) tests 18505 done 2 failed | 25 in flight, oldest 61s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
........................................................... [810%]
........................................................................ [813%]
........................................................................ [816%]
...............................................[contention-diag] +2470s soak 35p/237t rss 13.0G pss 11.8G swap 0.4G majflt 458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 7 descendant rss 0.1G pss 0.1G | host avail 32.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 0.88 cpu 25.95 | cgroup 13.5G/max oom_kill 0 | free scratch 329.4G/45409206i tmp 29.7G/1019836i workspace 329.4G/45409206i | repeat-01 collected 26/26 workers (60601 items) tests 18752 done 2 failed | 26 in flight, oldest 45s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_offline_reload_does_not_retain_freshness
......................... [819%]
........................................................................ [823%]
........................................................................ [826%]
........................................................................ [829%]
.....................................................................[contention-diag] +2485s soak 33p/240t rss 12.9G pss 11.8G swap 0.4G majflt 459 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 5 descendant rss 0.1G pss 0.0G | host avail 34.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 27.39 | cgroup 13.5G/max oom_kill 0 | free scratch 329.4G/45408448i tmp 29.7G/1019836i workspace 329.4G/45408448i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 19029 done 2 failed | 26 in flight, oldest 36s gw9 tests/ace/tui/test_projects_pane.py::test_configured_cycle_subtab_keys_bubble_and_forward
... [832%]
.....s.................................................................. [835%]
........................................................................ [838%]
........................................................................ [841%]
.....................ss........................................[contention-diag] +2502s soak 35p/277t rss 13.0G pss 11.8G swap 0.4G majflt 459 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 7 descendant rss 0.1G pss 0.1G | host avail 33.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 28.58 | cgroup 13.5G/max oom_kill 0 | free scratch 329.4G/45407624i tmp 29.7G/1019836i workspace 329.4G/45407624i | repeat-01 collected 26/26 workers (60601 items) tests 19354 done 2 failed | 26 in flight, oldest 51s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
......... [845%]
........................................................................ [848%]
........................................................................ [851%]
........................................................................ [854%]
.................[contention-diag] +2518s soak 36p/239t rss 13.0G pss 11.9G swap 0.4G majflt 460 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.5G, 8 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 29.92 | cgroup 13.6G/max oom_kill 0 | free scratch 329.4G/45406485i tmp 29.7G/1019836i workspace 329.4G/45406485i | repeat-01 collected 26/26 workers (60601 items) tests 19592 done 2 failed | 26 in flight, oldest 67s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
....................................................... [857%]
........................................................................ [860%]
........................................................................ [863%]
...[contention-diag] +2533s soak 37p/260t rss 13.1G pss 11.9G swap 0.4G majflt 466 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.5G, 9 descendant rss 0.2G pss 0.1G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 30.82 | cgroup 13.7G/max oom_kill 0 | free scratch 329.4G/45406060i tmp 29.7G/1019834i workspace 329.4G/45406060i | repeat-01 collected 26/26 workers (60601 items) tests 19792 done 2 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
..................................................................... [867%]
..........................................................s............. [870%]
........................................................................ [873%]
........................................................................ [876%]
..............................................[contention-diag] +2548s soak 31p/246t rss 13.0G pss 11.8G swap 0.4G majflt 469 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 3 descendant rss 0.1G pss 0.0G | host avail 33.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 2.86 cpu 28.31 | cgroup 13.5G/max oom_kill 0 | free scratch 329.4G/45404849i tmp 29.7G/1019836i workspace 329.4G/45404849i | repeat-01 collected 26/26 workers (60601 items) tests 20134 done 2 failed | 26 in flight, oldest 97s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.......................... [879%]
........................................................................ [882%]
.......................................................[contention-diag] +2564s soak 31p/248t rss 13.0G pss 11.8G swap 0.4G majflt 484 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 3 descendant rss 0.0G pss 0.0G | host avail 32.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.59 cpu 27.18 | cgroup 13.6G/max oom_kill 0 | free scratch 329.4G/45404572i tmp 29.7G/1019836i workspace 329.4G/45404572i | repeat-01 collected 26/26 workers (60601 items) tests 20285 done 2 failed | 26 in flight, oldest 113s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
................. [885%]
........................................................................ [889%]
........................................................................ [892%]
........................................................................ [895%]
[contention-diag] +2579s soak 35p/279t rss 13.1G pss 11.9G swap 0.4G majflt 490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.01 cpu 29.67 | cgroup 13.7G/max oom_kill 0 | free scratch 329.4G/45404036i tmp 29.7G/1019836i workspace 329.4G/45404036i | repeat-01 collected 26/26 workers (60601 items) tests 20514 done 2 failed | 26 in flight, oldest 59s gw1 tests/test_command_palette_e2e.py::test_semicolon_opens_command_palette_from_agents_and_axe_tabs
........................................................................ [898%]
.........................................[contention-diag] +2594s soak 36p/287t rss 13.1G pss 11.9G swap 0.4G majflt 490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 8 descendant rss 0.2G pss 0.1G | host avail 32.4G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.6 cpu 30.56 | cgroup 13.6G/max oom_kill 0 | free scratch 329.4G/45403679i tmp 29.7G/1019836i workspace 329.4G/45403679i | repeat-01 collected 26/26 workers (60601 items) tests 20630 done 2 failed | 26 in flight, oldest 54s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
............................... [901%]
........................................................................ [904%]
........................................................................ [907%]
......................[contention-diag] +2610s soak 38p/272t rss 13.1G pss 11.9G swap 0.4G majflt 490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 10 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 1.64 cpu 25.92 | cgroup 13.7G/max oom_kill 0 | free scratch 329.4G/45402803i tmp 29.7G/1019836i workspace 329.4G/45402803i | scratch used 1.0G in 198953 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 20783 done 2 failed | 25 in flight, oldest 70s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.................................................. [910%]
........................................................................ [914%]
..........[contention-diag] +2627s soak 38p/253t rss 13.1G pss 11.9G swap 0.4G majflt 490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 10 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 5.02 cpu 28.06 | cgroup 13.7G/max oom_kill 0 | free scratch 329.4G/45401865i tmp 29.7G/1019837i workspace 329.4G/45401865i | repeat-01 collected 26/26 workers (60601 items) tests 20958 done 2 failed | 25 in flight, oldest 38s gw0 tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_space_action_is_gated_only_while_prompt_is_mounted
.............................................................. [917%]
........................................................................ [920%]
........................................................................ [923%]
...................................[contention-diag] +2642s soak 35p/238t rss 13.1G pss 11.9G swap 0.4G majflt 497 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 34.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 4.48 cpu 27.45 | cgroup 13.7G/max oom_kill 0 | free scratch 329.3G/45401504i tmp 29.7G/1019836i workspace 329.3G/45401504i | repeat-01 collected 26/26 workers (60601 items) tests 21203 done 2 failed | 26 in flight, oldest 41s gw19 tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_then_digit_selects_view
..................................... [926%]
........................................................................ [929%]
........................................................................ [932%]
........................................................................ [936%]
...........................................................[contention-diag] +2658s soak 39p/231t rss 13.2G pss 12.0G swap 0.4G majflt 498 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 11 descendant rss 0.2G pss 0.2G | host avail 34.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 3.86 cpu 31.3 | cgroup 13.8G/max oom_kill 0 | free scratch 329.3G/45400376i tmp 29.7G/1019837i workspace 329.3G/45400376i | repeat-01 collected 26/26 workers (60601 items) tests 21507 done 2 failed | 26 in flight, oldest 44s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
............. [939%]
........................................................................ [942%]
........................................................................ [945%]
........................................................................ [948%]
............................................................[contention-diag] +2673s soak 36p/215t rss 13.2G pss 12.0G swap 0.4G majflt 498 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 8 descendant rss 0.3G pss 0.2G | host avail 33.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.61 cpu 30.59 | cgroup 13.8G/max oom_kill 0 | free scratch 329.3G/45398857i tmp 29.7G/1019837i workspace 329.3G/45398857i | repeat-01 collected 26/26 workers (60601 items) tests 21803 done 2 failed | 26 in flight, oldest 59s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
............ [951%]
.......................s................................................ [954%]
........................................................................ [958%]
.............[contention-diag] +2688s soak 31p/209t rss 13.1G pss 11.9G swap 0.4G majflt 499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 3 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.04 cpu 28.71 | cgroup 13.7G/max oom_kill 0 | free scratch 329.3G/45397770i tmp 29.7G/1019837i workspace 329.3G/45397770i | repeat-01 collected 26/26 workers (60601 items) tests 21972 done 2 failed | 26 in flight, oldest 57s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_axe_tab
........................................................... [961%]
........................................................................ [964%]
........................................................................ [967%]
........................................................................ [970%]
........................................................................ [973%]
......................s................................................. [976%]
........................................................................ [980%]
........................................................................ [983%]
..............................................................[contention-diag] +2704s soak 37p/196t rss 13.1G pss 11.9G swap 0.4G majflt 499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 9 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 4.19 cpu 27.44 | cgroup 13.7G/max oom_kill 0 | free scratch 329.3G/45398008i tmp 29.7G/1019837i workspace 329.3G/45398008i | repeat-01 collected 26/26 workers (60601 items) tests 22551 done 2 failed | 24 in flight, oldest 53s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail
.......... [986%]
........................................................................ [989%]
........................................................................ [992%]
........................................................................ [995%]
........................................................................ [998%]
..[contention-diag] +2719s soak 35p/193t rss 13.3G pss 12.0G swap 0.4G majflt 499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 32.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.11/0.07 io 5.53 cpu 32.74 | cgroup 13.8G/max oom_kill 0 | free scratch 329.3G/45397102i tmp 29.7G/1019837i workspace 329.3G/45397102i | repeat-01 collected 26/26 workers (60601 items) tests 22875 done 2 failed | 26 in flight, oldest 34s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
...................................................................... [1002%]
........................................................................ [1005%]
........................................................................ [1008%]
........................................................................ [1011%]
.............................................................[contention-diag] +2734s soak 35p/190t rss 13.1G pss 11.9G swap 0.4G majflt 501 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 7 descendant rss 0.1G pss 0.1G | host avail 35.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 3.97 cpu 29.45 | cgroup 13.8G/max oom_kill 0 | free scratch 329.3G/45396353i tmp 29.7G/1019837i workspace 329.3G/45396353i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 23148 done 2 failed | 26 in flight, oldest 50s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........... [1014%]
........................................................................ [1017%]
........................................................................ [1020%]
........................................................................ [1024%]
.............................................................[contention-diag] +2751s soak 38p/203t rss 13.2G pss 12.0G swap 0.4G majflt 513 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 10 descendant rss 0.2G pss 0.1G | host avail 36.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.43 cpu 30.28 | cgroup 13.9G/max oom_kill 0 | free scratch 329.3G/45395410i tmp 29.7G/1019837i workspace 329.3G/45395410i | repeat-01 collected 26/26 workers (60601 items) tests 23514 done 2 failed | 25 in flight, oldest 67s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........... [1027%]
........................................................................ [1030%]
........................................................................ [1033%]
........................................................................ [1036%]
........................................................................ [1039%]
........................................................................ [1042%]
................[contention-diag] +2767s soak 35p/212t rss 13.3G pss 12.0G swap 0.4G majflt 517 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 36.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.68 cpu 28.89 | cgroup 13.8G/max oom_kill 0 | free scratch 329.3G/45394044i tmp 29.7G/1019837i workspace 329.3G/45394044i | repeat-01 collected 26/26 workers (60601 items) tests 23912 done 2 failed | 26 in flight, oldest 82s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........................................................ [1046%]
........................................................................ [1049%]
........................................................................ [1052%]
........................................................................ [1055%]
....................................................[contention-diag] +2782s soak 33p/215t rss 13.3G pss 12.0G swap 0.4G majflt 513 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 5 descendant rss 0.2G pss 0.1G | host avail 35.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.32 cpu 31.35 | cgroup 13.9G/max oom_kill 0 | free scratch 329.3G/45393230i tmp 29.7G/1019837i workspace 329.3G/45393230i | repeat-01 collected 26/26 workers (60601 items) tests 24235 done 2 failed | 26 in flight, oldest 97s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.................... [1058%]
........................................................................ [1061%]
.....................................................................[contention-diag] +2797s soak 34p/193t rss 13.3G pss 12.0G swap 0.4G majflt 513 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 6 descendant rss 0.2G pss 0.1G | host avail 35.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.34 cpu 26.86 | cgroup 14.1G/max oom_kill 0 | free scratch 329.3G/45392467i tmp 29.7G/1019837i workspace 329.3G/45392467i | repeat-01 collected 26/26 workers (60601 items) tests 24404 done 2 failed | 26 in flight, oldest 113s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
... [1064%]
........................................................................ [1068%]
........................................................................ [1071%]
........................................................................ [1074%]
........................................................................ [1077%]
...........[contention-diag] +2813s soak 36p/194t rss 13.3G pss 12.1G swap 0.4G majflt 520 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 8 descendant rss 0.3G pss 0.2G | host avail 35.4G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.2 cpu 30.43 | cgroup 14.0G/max oom_kill 0 | free scratch 329.3G/45391797i tmp 29.7G/1019837i workspace 329.3G/45391797i | repeat-01 collected 26/26 workers (60601 items) tests 24706 done 2 failed | 26 in flight, oldest 128s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
............................................................. [1080%]
........................................................................ [1083%]
..............................[contention-diag] +2828s soak 31p/189t rss 13.2G pss 11.9G swap 0.4G majflt 520 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 3 descendant rss 0.1G pss 0.0G | host avail 34.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.88 cpu 29.0 | cgroup 13.9G/max oom_kill 0 | free scratch 329.3G/45391157i tmp 29.7G/1019837i workspace 329.3G/45391157i | repeat-01 collected 26/26 workers (60601 items) tests 24853 done 2 failed | 26 in flight, oldest 143s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.......................................... [1086%]
........................................................................ [1090%]
........................................................................ [1093%]
........................................................................ [1096%]
..............[contention-diag] +2843s soak 38p/176t rss 13.3G pss 12.1G swap 0.4G majflt 523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.8G pss 11.7G, 10 descendant rss 0.2G pss 0.1G | host avail 35.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.8 cpu 31.38 | cgroup 14.0G/max oom_kill 0 | free scratch 329.3G/45390508i tmp 29.7G/1019837i workspace 329.3G/45390508i | repeat-01 collected 26/26 workers (60601 items) tests 25129 done 2 failed | 26 in flight, oldest 159s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.......................................................... [1099%]
..................s..................................................... [1102%]
........................................................................ [1105%]
........................................................................ [1108%]
................................[contention-diag] +2859s soak 31p/177t rss 13.3G pss 12.1G swap 0.4G majflt 523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 3 descendant rss 0.1G pss 0.1G | host avail 34.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 4.75 cpu 29.23 | cgroup 14.0G/max oom_kill 0 | free scratch 329.3G/45389591i tmp 29.7G/1019837i workspace 329.3G/45389591i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 25432 done 2 failed | 26 in flight, oldest 174s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........................................ [1112%]
........................................................................ [1115%]
.........................................................[contention-diag] +2876s soak 33p/184t rss 13.3G pss 12.1G swap 0.4G majflt 527 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.2G pss 0.1G | host avail 34.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 3.94 cpu 28.21 | cgroup 14.0G/max oom_kill 0 | free scratch 329.3G/45388664i tmp 29.7G/1019837i workspace 329.3G/45388664i | repeat-01 collected 26/26 workers (60601 items) tests 25615 done 2 failed | 25 in flight, oldest 191s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
............... [1118%]
........................................................................ [1121%]
........................................................................ [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
....................................................................[contention-diag] +2891s soak 38p/185t rss 13.3G pss 12.1G swap 0.4G majflt 527 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 10 descendant rss 0.2G pss 0.1G | host avail 34.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.98 cpu 30.07 | cgroup 14.1G/max oom_kill 0 | free scratch 329.3G/45387408i tmp 29.7G/1019837i workspace 329.3G/45387408i | repeat-01 collected 26/26 workers (60601 items) tests 25974 done 2 failed | 26 in flight, oldest 207s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.... [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
........................................................................ [1143%]
........................................................................ [1146%]
................................................................[contention-diag] +2906s soak 32p/165t rss 13.2G pss 12.0G swap 0.4G majflt 537 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 4 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.27 cpu 29.47 | cgroup 14.0G/max oom_kill 0 | free scratch 329.3G/45386723i tmp 29.7G/1019837i workspace 329.3G/45386723i | repeat-01 collected 26/26 workers (60601 items) tests 26318 done 2 failed | 26 in flight, oldest 136s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........ [1149%]
........................................................................ [1152%]
........................................................................ [1156%]
........................................................................ [1159%]
........................................................................ [1162%]
........................................................................ [1165%]
........................................................................ [1168%]
.............................................................[contention-diag] +2922s soak 33p/163t rss 13.4G pss 12.1G swap 0.4G majflt 537 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.2G pss 0.1G | host avail 33.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.24 cpu 27.49 | cgroup 14.2G/max oom_kill 0 | free scratch 329.3G/45386691i tmp 29.7G/1019837i workspace 329.3G/45386691i | repeat-01 collected 26/26 workers (60601 items) tests 26824 done 2 failed | 25 in flight, oldest 151s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........... [1171%]
........................................................................ [1174%]
..............................................................[contention-diag] +2937s soak 37p/171t rss 13.4G pss 12.2G swap 0.4G majflt 537 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 9 descendant rss 0.2G pss 0.2G | host avail 33.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.81 cpu 32.31 | cgroup 14.2G/max oom_kill 0 | free scratch 329.3G/45386111i tmp 29.7G/1019837i workspace 329.3G/45386111i | repeat-01 collected 26/26 workers (60601 items) tests 26986 done 2 failed | 25 in flight, oldest 166s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.......... [1178%]
........................................................................ [1181%]
........................................................................ [1184%]
........................................................................ [1187%]
........................................................................ [1190%]
....................................[contention-diag] +2952s soak 35p/173t rss 13.4G pss 12.1G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 7 descendant rss 0.2G pss 0.1G | host avail 33.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.82 cpu 34.93 | cgroup 14.2G/max oom_kill 0 | free scratch 329.3G/45385243i tmp 29.7G/1019838i workspace 329.3G/45385243i | repeat-01 collected 26/26 workers (60601 items) tests 27317 done 2 failed | 24 in flight, oldest 182s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................... [1193%]
........................................................................ [1196%]
........................................................................ [1200%]
........................................................................ [1203%]
........................................................................ [1206%]
......................................[contention-diag] +2968s soak 39p/177t rss 13.6G pss 12.3G swap 0.4G majflt 2351 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 11 descendant rss 0.4G pss 0.3G | host avail 32.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.44 cpu 34.65 | cgroup 14.3G/max oom_kill 0 | free scratch 329.3G/45384241i tmp 29.7G/1019838i workspace 329.3G/45384241i | repeat-01 collected 26/26 workers (60601 items) tests 27685 done 2 failed | 25 in flight, oldest 197s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................. [1209%]
........................................................................ [1212%]
........................................................................ [1215%]
........................................................................ [1218%]
.............[contention-diag] +2983s soak 32p/183t rss 13.4G pss 12.1G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 4 descendant rss 0.2G pss 0.1G | host avail 32.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 0.39 cpu 29.44 | cgroup 14.4G/max oom_kill 0 | free scratch 329.3G/45383569i tmp 29.7G/1019838i workspace 329.3G/45383569i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 27900 done 2 failed | 25 in flight, oldest 212s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................................... [1221%]
........................................................................ [1225%]
........................................................................ [1228%]
.......................[contention-diag] +3000s soak 34p/172t rss 13.4G pss 12.1G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.38/0.19 io 0.65 cpu 31.02 | cgroup 14.3G/max oom_kill 0 | free scratch 329.2G/45382861i tmp 29.7G/1019838i workspace 329.2G/45382861i | repeat-01 collected 26/26 workers (60601 items) tests 28172 done 2 failed | 25 in flight, oldest 230s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................. [1231%]
........................................................................ [1234%]
........................................................................ [1237%]
........................................................................ [1240%]
....................[contention-diag] +3016s soak 33p/173t rss 13.4G pss 12.1G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.1G pss 0.1G | host avail 34.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.09/0.04 io 0.16 cpu 37.04 | cgroup 14.3G/max oom_kill 0 | free scratch 329.2G/45381520i tmp 29.7G/1019838i workspace 329.2G/45381520i | repeat-01 collected 26/26 workers (60601 items) tests 28449 done 2 failed | 25 in flight, oldest 182s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................................................... [1243%]
........................................................................ [1247%]
........................................................................ [1250%]
.................................................................[contention-diag] +3031s soak 33p/168t rss 13.3G pss 12.1G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 5 descendant rss 0.1G pss 0.0G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.31 cpu 34.18 | cgroup 14.2G/max oom_kill 0 | free scratch 329.2G/45380521i tmp 29.7G/1019838i workspace 329.2G/45380521i | repeat-01 collected 26/26 workers (60601 items) tests 28718 done 2 failed | 24 in flight, oldest 198s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....... [1253%]
........................................................................ [1256%]
........................................................................ [1259%]
................................................[contention-diag] +3046s soak 41p/180t rss 13.4G pss 12.1G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 13 descendant rss 0.1G pss 0.1G | host avail 34.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 31.34 | cgroup 14.2G/max oom_kill 0 | free scratch 329.2G/45380409i tmp 29.7G/1019838i workspace 329.2G/45380409i | repeat-01 collected 26/26 workers (60601 items) tests 28919 done 2 failed | 25 in flight, oldest 213s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................ [1262%]
........................................................................ [1265%]
........................................................................ [1269%]
........................................................[contention-diag] +3062s soak 36p/179t rss 13.4G pss 12.2G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 8 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.56 cpu 38.58 | cgroup 14.3G/max oom_kill 0 | free scratch 329.2G/45379664i tmp 29.7G/1019838i workspace 329.2G/45379664i | repeat-01 collected 26/26 workers (60601 items) tests 29144 done 2 failed | 25 in flight, oldest 228s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................ [1272%]
........................................................................ [1275%]
........................................................................ [1278%]
........................................................................ [1281%]
[contention-diag] +3077s soak 37p/166t rss 13.5G pss 12.2G swap 0.4G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 9 descendant rss 0.2G pss 0.1G | host avail 34.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 40.25 | cgroup 14.3G/max oom_kill 0 | free scratch 329.2G/45379161i tmp 29.7G/1019838i workspace 329.2G/45379161i | repeat-01 collected 26/26 workers (60601 items) tests 29368 done 2 failed | 25 in flight, oldest 244s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................................ [1284%]
........................................................................ [1287%]
........................................................................ [1291%]
........................................................................ [1294%]
........................................................................ [1297%]
........................................................................ [1300%]
.............................................................[contention-diag] +3092s soak 33p/171t rss 13.4G pss 12.2G swap 0.4G majflt 555 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 5 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 37.3 | cgroup 14.3G/max oom_kill 0 | free scratch 329.2G/45378157i tmp 29.7G/1019838i workspace 329.2G/45378157i | repeat-01 collected 26/26 workers (60601 items) tests 29856 done 2 failed | 24 in flight, oldest 259s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........... [1303%]
........................................................................ [1306%]
........................................................................ [1309%]
........................................................................ [1313%]
........................................................................ [1316%]
........................................................................ [1319%]
...........................................................[contention-diag] +3108s soak 34p/178t rss 13.6G pss 12.3G swap 0.4G majflt 555 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 6 descendant rss 0.2G pss 0.2G | host avail 34.4G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.17 cpu 35.42 | cgroup 14.4G/max oom_kill 0 | free scratch 329.2G/45377005i tmp 29.7G/1019838i workspace 329.2G/45377005i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 30238 done 2 failed | 24 in flight, oldest 274s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............. [1322%]
........................................................................ [1325%]
........................................................................ [1328%]
........................................................................ [1331%]
........................................................................ [1335%]
.....[contention-diag] +3125s soak 35p/169t rss 13.5G pss 12.2G swap 0.4G majflt 555 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 7 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.32 cpu 34.26 | cgroup 14.3G/max oom_kill 0 | free scratch 329.2G/45375477i tmp 29.7G/1019838i workspace 329.2G/45375477i | repeat-01 collected 26/26 workers (60601 items) tests 30592 done 2 failed | 25 in flight, oldest 292s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................................... [1338%]
........................................................................ [1341%]
........................................................................ [1344%]
........................................................................ [1347%]
.......................................................................[contention-diag] +3140s soak 37p/172t rss 13.5G pss 12.2G swap 0.4G majflt 557 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 9 descendant rss 0.1G pss 0.1G | host avail 33.4G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.62 cpu 33.24 | cgroup 14.4G/max oom_kill 0 | free scratch 329.2G/45374247i tmp 29.7G/1019838i workspace 329.2G/45374247i | repeat-01 collected 26/26 workers (60601 items) tests 30955 done 2 failed | 25 in flight, oldest 307s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
. [1350%]
........................................................................ [1353%]
........................................................................ [1357%]
........................................................................ [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
........................................................................ [1369%]
......................[contention-diag] +3156s soak 39p/186t rss 13.6G pss 12.3G swap 0.4G majflt 558 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 11 descendant rss 0.2G pss 0.1G | host avail 32.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.65 cpu 33.78 | cgroup 14.4G/max oom_kill 0 | free scratch 329.2G/45372269i tmp 29.7G/1019838i workspace 329.2G/45372269i | repeat-01 collected 26/26 workers (60601 items) tests 31405 done 2 failed | 24 in flight, oldest 306s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.................................................. [1372%]
........................................................................ [1375%]
........................................................................ [1379%]
........................................................................ [1382%]
........................................................................ [1385%]
...........[contention-diag] +3171s soak 35p/161t rss 13.5G pss 12.2G swap 0.4G majflt 558 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 7 descendant rss 0.1G pss 0.1G | host avail 32.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.54 cpu 27.54 | cgroup 14.4G/max oom_kill 0 | free scratch 329.2G/45371710i tmp 29.7G/1019838i workspace 329.2G/45371710i | repeat-01 collected 26/26 workers (60601 items) tests 31757 done 2 failed | 25 in flight, oldest 321s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................................................. [1388%]
........................................................................ [1391%]
........................................................................ [1394%]
........................................................................ [1397%]
........................................................................ [1401%]
..[contention-diag] +3186s soak 31p/164t rss 13.5G pss 12.2G swap 0.4G majflt 558 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.8G, 3 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.53 cpu 35.48 | cgroup 14.5G/max oom_kill 0 | free scratch 329.3G/45383112i tmp 29.7G/1019838i workspace 329.3G/45383112i | repeat-01 collected 26/26 workers (60601 items) tests 32097 done 2 failed | 16 in flight, oldest 10s gw23 tests/test_ace_tui_app.py::test_navigation_next_key
...................................................................... [1404%]
........................................................................ [1407%]
........................................................................ [1410%]
....................................................[contention-diag] +3202s soak 42p/178t rss 13.7G pss 12.4G swap 0.4G majflt 560 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 14 descendant rss 0.3G pss 0.2G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.3 cpu 39.44 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45392681i tmp 29.7G/1019838i workspace 329.3G/45392681i | repeat-01 collected 26/26 workers (60601 items) tests 32377 done 2 failed | 20 in flight, oldest 26s gw23 tests/test_ace_tui_app.py::test_navigation_next_key
.................... [1413%]
........................................................................ [1416%]
........................................................................ [1419%]
........................................................................ [1423%]
.................................................[contention-diag] +3217s soak 37p/209t rss 13.9G pss 12.5G swap 0.4G majflt 566 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.4G pss 0.3G | host avail 32.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.17 cpu 36.61 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45392046i tmp 29.7G/1019838i workspace 329.3G/45392046i | repeat-01 collected 26/26 workers (60601 items) tests 32659 done 2 failed | 20 in flight, oldest 31s gw24 tests/autonomy_contract/test_spelling_contract.py::test_spelling_row[short_a]
....................... [1426%]
........................................................................ [1429%]
........................................................................ [1432%]
........................................................................ [1435%]
......................................................................[contention-diag] +3232s soak 36p/190t rss 13.8G pss 12.4G swap 0.4G majflt 566 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 8 descendant rss 0.3G pss 0.3G | host avail 31.4G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.76 cpu 31.18 | cgroup 14.8G/max oom_kill 0 | free scratch 329.3G/45391138i tmp 29.7G/1019838i workspace 329.3G/45391138i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 32913 done 2 failed | 21 in flight, oldest 47s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
.. [1438%]
........................................................................ [1441%]
........................................................................ [1445%]
........................................................................ [1448%]
........................................................................ [1451%]
........................................................................ [1454%]
........................................................................ [1457%]
........................................................................ [1460%]
........................................................................ [1463%]
........................................................................ [1467%]
........................................................................ [1470%]
.............[contention-diag] +3249s soak 33p/174t rss 13.6G pss 12.3G swap 0.4G majflt 567 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 32.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.69 cpu 35.05 | cgroup 14.6G/max oom_kill 0 | free scratch 329.3G/45389100i tmp 29.7G/1019838i workspace 329.3G/45389100i | repeat-01 collected 26/26 workers (60601 items) tests 33662 done 2 failed | 23 in flight, oldest 64s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
........................................................... [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1482%]
........................................................................ [1485%]
........................................................................ [1489%]
..[contention-diag] +3265s soak 39p/183t rss 13.6G pss 12.3G swap 0.4G majflt 720 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 11 descendant rss 0.1G pss 0.0G | host avail 31.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 34.46 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45387494i tmp 29.7G/1019838i workspace 329.3G/45387494i | repeat-01 collected 26/26 workers (60601 items) tests 34127 done 2 failed | 23 in flight, oldest 79s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
...................................................................... [1492%]
........................................................................ [1495%]
................[contention-diag] +3280s soak 35p/190t rss 13.7G pss 12.3G swap 0.4G majflt 728 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 7 descendant rss 0.2G pss 0.1G | host avail 32.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 32.46 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45386935i tmp 29.7G/1019838i workspace 329.3G/45386935i | repeat-01 collected 26/26 workers (60601 items) tests 34287 done 2 failed | 23 in flight, oldest 94s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
........................................................ [1498%]
........................................................................ [1501%]
........................................................................ [1504%]
........................................................................ [1507%]
...................................[contention-diag] +3295s soak 39p/188t rss 13.7G pss 12.4G swap 0.4G majflt 733 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 11 descendant rss 0.2G pss 0.1G | host avail 31.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 26.88 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45386421i tmp 29.7G/1019838i workspace 329.3G/45386421i | repeat-01 collected 26/26 workers (60601 items) tests 34560 done 2 failed | 24 in flight, oldest 110s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
..................................... [1510%]
........................................................................ [1514%]
........................................................................ [1517%]
........................................................................ [1520%]
.................[contention-diag] +3311s soak 31p/164t rss 13.6G pss 12.3G swap 0.4G majflt 733 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 3 descendant rss 0.1G pss 0.1G | host avail 33.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 34.89 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45385131i tmp 29.7G/1019838i workspace 329.3G/45385131i | repeat-01 collected 26/26 workers (60601 items) tests 34861 done 2 failed | 24 in flight, oldest 125s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
....................................................... [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1532%]
..............................[contention-diag] +3326s soak 34p/185t rss 13.7G pss 12.4G swap 0.4G majflt 738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 6 descendant rss 0.2G pss 0.2G | host avail 33.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.68 cpu 41.15 | cgroup 14.8G/max oom_kill 0 | free scratch 329.3G/45384386i tmp 29.7G/1019838i workspace 329.3G/45384386i | repeat-01 collected 26/26 workers (60601 items) tests 35160 done 2 failed | 24 in flight, oldest 140s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
.......................................... [1536%]
........................................................................ [1539%]
........................................................................ [1542%]
........................................................................ [1545%]
...................................................[contention-diag] +3342s soak 35p/188t rss 13.8G pss 12.5G swap 0.4G majflt 738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 7 descendant rss 0.3G pss 0.2G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.51 cpu 41.5 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45383792i tmp 29.7G/1019838i workspace 329.3G/45383792i | repeat-01 collected 26/26 workers (60601 items) tests 35471 done 2 failed | 24 in flight, oldest 156s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
..................... [1548%]
........................................................................ [1551%]
........................................................................ [1554%]
........................................................................ [1558%]
........................................................................ [1561%]
.............................................................[contention-diag] +3357s soak 38p/198t rss 13.7G pss 12.4G swap 0.4G majflt 738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 10 descendant rss 0.2G pss 0.1G | host avail 32.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 34.97 | cgroup 14.7G/max oom_kill 0 | free scratch 329.3G/45382350i tmp 29.7G/1019838i workspace 329.3G/45382350i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 35790 done 2 failed | 25 in flight, oldest 171s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 3 hazardous kill call(s)
........... [1564%]
........................................................................ [1567%]
........................................................................ [1570%]
.......................................................[contention-diag] +3374s soak 35p/188t rss 13.7G pss 12.4G swap 0.4G majflt 810 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 7 descendant rss 0.1G pss 0.1G | host avail 35.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.41 cpu 37.51 | cgroup 15.3G/max oom_kill 0 | free scratch 329.3G/45380849i tmp 29.7G/1019838i workspace 329.3G/45380847i | repeat-01 collected 26/26 workers (60601 items) tests 36054 done 2 failed | 25 in flight, oldest 188s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 6 hazardous kill call(s)
................. [1573%]
........................................................................ [1576%]
........................................................................ [1580%]
........................................................................ [1583%]
.....................................................................[contention-diag] +3390s soak 36p/187t rss 13.8G pss 12.4G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 11.9G, 8 descendant rss 0.2G pss 0.2G | host avail 35.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.37 cpu 34.58 | cgroup 15.3G/max oom_kill 0 | free scratch 329.0G/45381651i tmp 29.7G/1019838i workspace 329.0G/45381651i | repeat-01 collected 26/26 workers (60601 items) tests 36328 done 2 failed | 23 in flight, oldest 204s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 6 hazardous kill call(s)
... [1586%]
........................................................................ [1589%]
...........................s............................................ [1592%]
........................................................................ [1595%]
........................................................................ [1598%]
..........[contention-diag] +3405s soak 40p/197t rss 13.8G pss 12.5G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 12 descendant rss 0.3G pss 0.2G | host avail 35.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.62 cpu 30.56 | cgroup 15.4G/max oom_kill 0 | free scratch 328.7G/45380370i tmp 29.7G/1019838i workspace 328.7G/45380370i | repeat-01 collected 26/26 workers (60601 items) tests 36649 done 2 failed | 24 in flight, oldest 219s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 6 hazardous kill call(s)
.............................................................. [1602%]
........................................................................ [1605%]
........................................................................ [1608%]
........................................................................ [1611%]
.................................................[contention-diag] +3420s soak 38p/200t rss 13.9G pss 12.6G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 10 descendant rss 0.3G pss 0.3G | host avail 34.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.8 cpu 28.8 | cgroup 14.9G/max oom_kill 0 | free scratch 329.3G/45379647i tmp 29.7G/1019838i workspace 329.3G/45379647i | repeat-01 collected 26/26 workers (60601 items) tests 36972 done 2 failed | 24 in flight, oldest 235s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 6 hazardous kill call(s)
....................... [1614%]
........................................................................ [1617%]
........................................................................ [1620%]
.............................[contention-diag] +3436s soak 36p/202t rss 13.8G pss 12.5G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 8 descendant rss 0.2G pss 0.2G | host avail 33.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.63 cpu 31.35 | cgroup 14.8G/max oom_kill 0 | free scratch 329.3G/45378925i tmp 29.7G/1019838i workspace 329.3G/45378925i | repeat-01 collected 26/26 workers (60601 items) tests 37174 done 2 failed | 24 in flight, oldest 250s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 6 hazardous kill call(s)
........................................... [1624%]
........................................................................ [1627%]
........................................................................ [1630%]
..................................................................[contention-diag] +3451s soak 34p/175t rss 13.7G pss 12.4G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 6 descendant rss 0.1G pss 0.1G | host avail 35.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 41.76 | cgroup 14.8G/max oom_kill 0 | free scratch 329.3G/45378290i tmp 29.7G/1019838i workspace 329.3G/45378290i | repeat-01 collected 26/26 workers (60601 items) tests 37418 done 2 failed | 24 in flight, oldest 265s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 6 hazardous kill call(s)
...... [1633%]
........................................................................ [1636%]
........................................................................ [1639%]
........................................................................ [1642%]
...................................................s.................... [1646%]
........................................................................ [1649%]
................[contention-diag] +3466s soak 34p/186t rss 13.7G pss 12.4G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 6 descendant rss 0.1G pss 0.1G | host avail 35.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 41.09 | cgroup 14.8G/max oom_kill 0 | free scratch 329.3G/45377602i tmp 29.7G/1019838i workspace 329.3G/45377602i | repeat-01 collected 26/26 workers (60601 items) tests 37796 done 2 failed | 24 in flight, oldest 280s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
........................................................ [1652%]
........................................................................ [1655%]
........................................................................ [1658%]
........................................................................ [1661%]
........................................................................ [1664%]
........................................................................ [1668%]
............................[contention-diag] +3482s soak 35p/190t rss 13.9G pss 12.5G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 7 descendant rss 0.2G pss 0.2G | host avail 34.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.9 cpu 35.72 | cgroup 14.9G/max oom_kill 0 | free scratch 329.2G/45375958i tmp 29.7G/1019838i workspace 329.2G/45375958i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 38234 done 2 failed | 24 in flight, oldest 296s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
............................................ [1671%]
........................................................................ [1674%]
........................................................................ [1677%]
........................................................................ [1680%]
...................................................[contention-diag] +3499s soak 34p/193t rss 13.8G pss 12.4G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 6 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 36.22 | cgroup 14.8G/max oom_kill 0 | free scratch 329.2G/45375312i tmp 29.7G/1019838i workspace 329.2G/45375312i | repeat-01 collected 26/26 workers (60601 items) tests 38544 done 2 failed | 24 in flight, oldest 313s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
..................... [1683%]
........................................................................ [1686%]
........................................................................ [1690%]
........................................................................ [1693%]
........................................................................ [1696%]
............[contention-diag] +3514s soak 37p/196t rss 13.9G pss 12.5G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 9 descendant rss 0.2G pss 0.2G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 34.54 | cgroup 14.9G/max oom_kill 0 | free scratch 329.2G/45374142i tmp 29.7G/1019838i workspace 329.2G/45374142i | repeat-01 collected 26/26 workers (60601 items) tests 38881 done 2 failed | 24 in flight, oldest 307s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 7 hazardous kill call(s)
............................................................ [1699%]
........................................................................ [1702%]
........................................................................ [1705%]
........................................................................ [1708%]
...................................................................[contention-diag] +3529s soak 34p/181t rss 13.8G pss 12.5G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 6 descendant rss 0.2G pss 0.2G | host avail 33.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 33.65 | cgroup 14.9G/max oom_kill 0 | free scratch 329.2G/45372826i tmp 29.7G/1019838i workspace 329.2G/45372826i | repeat-01 collected 26/26 workers (60601 items) tests 39216 done 2 failed | 24 in flight, oldest 252s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
..... [1712%]
........................................................................ [1715%]
........................................................................ [1718%]
........................................................................ [1721%]
........................................................................ [1724%]
........................................................................ [1727%]
..[contention-diag] +3545s soak 36p/183t rss 13.9G pss 12.5G swap 0.4G majflt 745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 8 descendant rss 0.3G pss 0.2G | host avail 34.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.25 cpu 29.16 | cgroup 15.0G/max oom_kill 0 | free scratch 329.2G/45371714i tmp 29.7G/1019838i workspace 329.2G/45371714i | repeat-01 collected 26/26 workers (60601 items) tests 39595 done 2 failed | 24 in flight, oldest 267s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
...................................................................... [1730%]
........................................................................ [1734%]
........................................................................ [1737%]
.......................[contention-diag] +3560s soak 38p/177t rss 14.0G pss 12.6G swap 0.4G majflt 787 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 10 descendant rss 0.3G pss 0.3G | host avail 34.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.86 cpu 30.14 | cgroup 15.0G/max oom_kill 0 | free scratch 329.2G/45370982i tmp 29.7G/1019838i workspace 329.2G/45370982i | repeat-01 collected 26/26 workers (60601 items) tests 39823 done 2 failed | 23 in flight, oldest 283s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
................................................. [1740%]
........................................................................ [1743%]
........................................................................ [1746%]
........................................................................ [1749%]
........................................................................ [1752%]
........................................................................ [1756%]
[contention-diag] +3576s soak 43p/196t rss 14.0G pss 12.6G swap 0.4G majflt 789 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 15 descendant rss 0.4G pss 0.3G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.95 cpu 34.54 | cgroup 15.1G/max oom_kill 0 | free scratch 329.2G/45369729i tmp 29.7G/1019838i workspace 329.2G/45369729i | repeat-01 collected 26/26 workers (60601 items) tests 40225 done 2 failed | 24 in flight, oldest 298s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
........................................................................ [1759%]
........................................................................ [1762%]
........................................................................ [1765%]
........................................................................ [1768%]
........................................................................ [1771%]
........................................[contention-diag] +3591s soak 37p/198t rss 14.0G pss 12.6G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 9 descendant rss 0.3G pss 0.3G | host avail 31.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.53 cpu 24.92 | cgroup 15.2G/max oom_kill 0 | free scratch 329.2G/45368599i tmp 29.7G/1019838i workspace 329.2G/45368599i | repeat-01 collected 26/26 workers (60601 items) tests 40635 done 2 failed | 24 in flight, oldest 313s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
................................ [1774%]
........................................................................ [1778%]
........................................................................ [1781%]
........................................................................ [1784%]
...........................................s............................ [1787%]
........................................................................ [1790%]
............................................[contention-diag] +3606s soak 36p/186t rss 14.0G pss 12.6G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 8 descendant rss 0.3G pss 0.2G | host avail 32.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 3.76 cpu 21.37 | cgroup 15.2G/max oom_kill 0 | free scratch 329.2G/45367495i tmp 29.7G/1019838i workspace 329.2G/45367495i | scratch used 1.0G in 184948 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 41047 done 2 failed | 24 in flight, oldest 329s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
............................ [1793%]
........................................................................ [1796%]
........................................................................ [1800%]
........................................................................ [1803%]
.............[contention-diag] +3624s soak 45p/206t rss 14.0G pss 12.6G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 12.0G, 17 descendant rss 0.3G pss 0.2G | host avail 32.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 2.86 cpu 21.38 | cgroup 15.1G/max oom_kill 0 | free scratch 329.2G/45366252i tmp 29.7G/1019838i workspace 329.2G/45366252i | repeat-01 collected 26/26 workers (60601 items) tests 41337 done 2 failed | 24 in flight, oldest 346s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
........................................................... [1806%]
........................................................................ [1809%]
........................................................................ [1812%]
......................................................................[contention-diag] +3639s soak 36p/207t rss 14.0G pss 12.6G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 8 descendant rss 0.2G pss 0.2G | host avail 31.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.62/0.62 io 1.59 cpu 22.3 | cgroup 15.1G/max oom_kill 0 | free scratch 329.2G/45366059i tmp 29.7G/1019838i workspace 329.2G/45366059i | repeat-01 collected 26/26 workers (60601 items) tests 41592 done 2 failed | 24 in flight, oldest 361s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
.. [1815%]
..s..................................................................... [1818%]
........................................................................ [1821%]
........................................................................ [1825%]
........................................................................ [1828%]
........................................................................ [1831%]
........................................................................ [1834%]
..............[contention-diag] +3654s soak 35p/188t rss 14.0G pss 12.6G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 0.3G pss 0.2G | host avail 31.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 1.69 cpu 24.8 | cgroup 15.1G/max oom_kill 0 | free scratch 329.2G/45364338i tmp 29.7G/1019838i workspace 329.2G/45364338i | repeat-01 collected 26/26 workers (60601 items) tests 42036 done 2 failed | 24 in flight, oldest 377s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................................................... [1837%]
........................................................................ [1840%]
........................................................................ [1843%]
........................................................................ [1847%]
........................................................................ [1850%]
..................................................................[contention-diag] +3670s soak 35p/199t rss 14.0G pss 12.4G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 11.8G, 7 descendant rss 0.2G pss 0.2G | host avail 30.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.41 cpu 24.75 | cgroup 15.1G/max oom_kill 0 | free scratch 329.2G/45362496i tmp 29.7G/1019838i workspace 329.2G/45362496i | repeat-01 collected 26/26 workers (60601 items) tests 42464 done 2 failed | 24 in flight, oldest 392s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
...... [1853%]
........................................................................ [1856%]
........................................................................ [1859%]
........................................................................ [1862%]
.......................................................[contention-diag] +3685s soak 39p/207t rss 14.0G pss 12.7G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 11 descendant rss 0.3G pss 0.2G | host avail 32.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.77 cpu 30.57 | cgroup 15.3G/max oom_kill 0 | free scratch 329.2G/45362406i tmp 29.7G/1019838i workspace 329.2G/45362406i | repeat-01 collected 26/26 workers (60601 items) tests 42744 done 2 failed | 24 in flight, oldest 408s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................. [1865%]
........................................................................ [1869%]
........................................................................ [1872%]
........................................................................ [1875%]
........................................................................ [1878%]
.......................[contention-diag] +3700s soak 34p/192t rss 14.1G pss 12.8G swap 0.4G majflt 847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 6 descendant rss 0.4G pss 0.3G | host avail 33.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 33.92 | cgroup 15.4G/max oom_kill 0 | free scratch 329.2G/45361308i tmp 29.7G/1019838i workspace 329.2G/45361308i | repeat-01 collected 26/26 workers (60601 items) tests 43065 done 2 failed | 23 in flight, oldest 423s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................. [1881%]
........................................................................ [1884%]
........................................................................ [1887%]
........................................................................ [1891%]
........................................................................ [1894%]
........................................................................ [1897%]
........................................................................ [1900%]
..........[contention-diag] +3716s soak 35p/185t rss 14.0G pss 12.7G swap 0.4G majflt 848 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 0.3G pss 0.2G | host avail 33.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 37.1 | cgroup 15.3G/max oom_kill 0 | free scratch 329.1G/45359588i tmp 29.7G/1019838i workspace 329.1G/45359588i | repeat-01 collected 26/26 workers (60601 items) tests 43567 done 2 failed | 24 in flight, oldest 438s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............................................................. [1903%]
........................................................................ [1906%]
........................................................................ [1909%]
........................................................................ [1913%]
........................................................................ [1916%]
...........................................[contention-diag] +3731s soak 42p/188t rss 14.2G pss 12.8G swap 0.4G majflt 848 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 14 descendant rss 0.4G pss 0.3G | host avail 33.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.4 cpu 36.47 | cgroup 15.4G/max oom_kill 0 | free scratch 329.1G/45358934i tmp 29.7G/1019838i workspace 329.1G/45358934i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 43862 done 2 failed | 23 in flight, oldest 281s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
............................. [1919%]
........................................................................ [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
................[contention-diag] +3748s soak 42p/195t rss 14.5G pss 13.1G swap 0.4G majflt 856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 14 descendant rss 0.7G pss 0.6G | host avail 32.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.79 cpu 36.2 | cgroup 15.7G/max oom_kill 0 | free scratch 329.1G/45358102i tmp 29.7G/1019838i workspace 329.1G/45358102i | repeat-01 collected 26/26 workers (60601 items) tests 44213 done 2 failed | 23 in flight, oldest 298s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
........................................................ [1931%]
........................................................................ [1935%]
........................................................................ [1938%]
...........................................................[contention-diag] +3764s soak 39p/201t rss 14.3G pss 12.9G swap 0.4G majflt 856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 11 descendant rss 0.5G pss 0.4G | host avail 31.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.45 cpu 30.58 | cgroup 15.6G/max oom_kill 0 | free scratch 329.1G/45356844i tmp 29.7G/1019838i workspace 329.1G/45356844i | repeat-01 collected 26/26 workers (60601 items) tests 44482 done 2 failed | 23 in flight, oldest 313s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
............. [1941%]
........................................................................ [1944%]
........................................................................ [1947%]
........................................................................ [1950%]
..............................................................[contention-diag] +3779s soak 39p/198t rss 14.3G pss 12.9G swap 0.4G majflt 856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 11 descendant rss 0.5G pss 0.4G | host avail 32.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.64 cpu 35.47 | cgroup 15.6G/max oom_kill 0 | free scratch 329.1G/45355993i tmp 29.7G/1019836i workspace 329.1G/45355992i | repeat-01 collected 26/26 workers (60601 items) tests 44764 done 2 failed | 22 in flight, oldest 329s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1953%]
........................................................................ [1957%]
........................................................................ [1960%]
........................................................................ [1963%]
........................................................................ [1966%]
............................................[contention-diag] +3795s soak 40p/197t rss 14.4G pss 13.0G swap 0.4G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 12 descendant rss 0.6G pss 0.5G | host avail 31.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.85 cpu 31.57 | cgroup 15.6G/max oom_kill 0 | free scratch 329.1G/45354977i tmp 29.7G/1019838i workspace 329.1G/45354977i | repeat-01 collected 26/26 workers (60601 items) tests 45100 done 2 failed | 23 in flight, oldest 344s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1969%]
........................................................................ [1972%]
........................................................................ [1975%]
...........................[contention-diag] +3810s soak 37p/189t rss 14.5G pss 13.1G swap 0.4G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 9 descendant rss 0.7G pss 0.6G | host avail 32.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.39 cpu 30.9 | cgroup 15.7G/max oom_kill 0 | free scratch 329.1G/45353834i tmp 29.7G/1019838i workspace 329.1G/45353835i | repeat-01 collected 26/26 workers (60601 items) tests 45315 done 2 failed | 22 in flight, oldest 359s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
............................................. [1979%]
........................................................................ [1982%]
...............................................[contention-diag] +3825s soak 37p/176t rss 14.8G pss 13.3G swap 0.5G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.5G pss 12.1G, 9 descendant rss 0.9G pss 0.8G | host avail 31.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.77 cpu 31.75 | cgroup 16.0G/max oom_kill 0 | free scratch 329.1G/45352993i tmp 29.7G/1019838i workspace 329.1G/45352993i | repeat-01 collected 26/26 workers (60601 items) tests 45462 done 2 failed | 22 in flight, oldest 375s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
......................... [1985%]
........................................................................ [1988%]
........................................................................ [1991%]
........................................................................ [1994%]
.......................................[contention-diag] +3841s soak 38p/184t rss 14.7G pss 13.2G swap 0.5G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.5G pss 12.1G, 10 descendant rss 0.8G pss 0.7G | host avail 31.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.42 cpu 32.95 | cgroup 15.8G/max oom_kill 0 | free scratch 329.1G/45354793i tmp 29.7G/1019838i workspace 329.1G/45354793i | repeat-01 collected 26/26 workers (60601 items) tests 45740 done 2 failed | 20 in flight, oldest 390s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
................................. [1997%]
........................................................................ [2001%]
........................................................................ [2004%]
........................................................................ [2007%]
........................................................................ [2010%]
........................................................................ [2013%]
........................................................................ [2016%]
........................................................................ [2019%]
..............................................[contention-diag] +3856s soak 37p/189t rss 14.8G pss 13.3G swap 0.5G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 9 descendant rss 0.9G pss 0.8G | host avail 32.4G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.24 cpu 37.54 | cgroup 15.9G/max oom_kill 0 | free scratch 329.1G/45353798i tmp 29.7G/1019838i workspace 329.1G/45353798i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 46299 done 2 failed | 21 in flight, oldest 406s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [2023%]
........................................................................ [2026%]
........................................................................ [2029%]
........................................................................ [2032%]
........................................................................ [2035%]
...........[contention-diag] +3873s soak 40p/181t rss 14.7G pss 13.2G swap 0.4G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.1G, 12 descendant rss 0.8G pss 0.7G | host avail 32.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.52 cpu 41.03 | cgroup 15.8G/max oom_kill 0 | free scratch 329.1G/45353381i tmp 29.7G/1019838i workspace 329.1G/45353381i | repeat-01 collected 26/26 workers (60601 items) tests 46661 done 2 failed | 20 in flight, oldest 236s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 8 hazardous kill call(s)
............................................................. [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
........................................................................ [2054%]
........................................................................ [2057%]
................................................[contention-diag] +3889s soak 39p/185t rss 14.7G pss 13.2G swap 0.5G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 11 descendant rss 0.8G pss 0.7G | host avail 31.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 31.47 | cgroup 15.9G/max oom_kill 0 | free scratch 329.1G/45351742i tmp 29.7G/1019838i workspace 329.1G/45351742i | repeat-01 collected 26/26 workers (60601 items) tests 47201 done 2 failed | 20 in flight, oldest 251s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 8 hazardous kill call(s)
........................ [2060%]
........................................................................ [2063%]
........................................................................ [2067%]
........................................................................ [2070%]
........................................................................ [2073%]
..................................................................[contention-diag] +3904s soak 44p/187t rss 15.0G pss 13.5G swap 0.5G majflt 857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 16 descendant rss 1.1G pss 1.0G | host avail 31.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.96 cpu 28.29 | cgroup 16.1G/max oom_kill 0 | free scratch 329.1G/45350890i tmp 29.7G/1019838i workspace 329.1G/45350890i | repeat-01 collected 26/26 workers (60601 items) tests 47581 done 2 failed | 19 in flight, oldest 267s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 8 hazardous kill call(s)
...... [2076%]
........................................................................ [2079%]
........................................................................ [2082%]
........................................................................ [2085%]
........................................................................ [2089%]
.....................[contention-diag] +3920s soak 38p/179t rss 14.7G pss 13.3G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 10 descendant rss 0.8G pss 0.8G | host avail 30.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.78 cpu 34.69 | cgroup 15.9G/max oom_kill 0 | free scratch 329.1G/45350277i tmp 29.7G/1019838i workspace 329.1G/45350277i | repeat-01 collected 26/26 workers (60601 items) tests 47897 done 2 failed | 19 in flight, oldest 282s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 8 hazardous kill call(s)
................................................... [2092%]
........................................................................ [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
........................................................................ [2104%]
........................................................................ [2107%]
........................................................................ [2110%]
........................................................................ [2114%]
........................................................................ [2117%]
.........................[contention-diag] +3935s soak 37p/184t rss 14.7G pss 13.3G swap 0.4G majflt 859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 9 descendant rss 0.8G pss 0.8G | host avail 30.2G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.25 cpu 30.29 | cgroup 15.9G/max oom_kill 0 | free scratch 329.1G/45348855i tmp 29.7G/1019838i workspace 329.1G/45348855i | repeat-01 collected 26/26 workers (60601 items) tests 48551 done 2 failed | 19 in flight, oldest 297s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................... [2120%]
..............F[contention-failure] call tests/test_core_rust.py::test_require_rust_extension_raises_when_missing: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb0bf5c4650>

    def test_require_rust_extension_raises_when_missing(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A missing wheel surfaces as :class:`ImportError`, not ``None``.
    
        The strict loader raises with a message that names the package and
        the supported install commands, so callers cannot accidentally
        silently fall back to Python.
        """
        evict_rust_extension(monkeypatch)
    
        def _missing(name: str) -> object:
            raise ImportError(f"No module named {name!r}")
    
        monkeypatch.setattr(importlib, "import_module", _missing)
        with pytest.raises(ImportError) as excinfo:
            require_rust_extension()
        message = str(excinfo.value)
        assert RUST_EXTENSION_MODULE_NAME in message
>       assert "just install-venv" in message
E       AssertionError: assert 'just install-venv' in 'sase_core_rs is not importable in this environment but is a hard runtime dependency of sase; reinstall sase in this environment (for example `uv tool install --force sase`).'

tests/test_core_rust.py:53: AssertionError
......................................................... [2123%]
........................................................................ [2126%]
........................................................................ [2129%]
........................................................................ [2132%]
.................................................[contention-diag] +3950s soak 37p/179t rss 14.9G pss 13.4G swap 0.4G majflt 859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 9 descendant rss 1.0G pss 0.8G | host avail 31.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 31.83 | cgroup 16.0G/max oom_kill 0 | free scratch 329.1G/45348215i tmp 29.7G/1019838i workspace 329.1G/45348215i | repeat-01 collected 26/26 workers (60601 items) tests 48937 done 3 failed | 18 in flight, oldest 313s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................... [2136%]
........................................................................ [2139%]
........................................................................ [2142%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........................................................................ [2154%]
...................[contention-diag] +3966s soak 37p/176t rss 14.9G pss 13.5G swap 0.4G majflt 859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 9 descendant rss 1.0G pss 0.9G | host avail 30.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.68 cpu 32.08 | cgroup 16.1G/max oom_kill 0 | free scratch 329.1G/45347025i tmp 29.7G/1019838i workspace 329.1G/45347025i | repeat-01 collected 26/26 workers (60601 items) tests 49405 done 3 failed | 18 in flight, oldest 328s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
..................................................... [2158%]
..................s..................................................... [2161%]
........................................................................ [2164%]
........................................................................ [2167%]
........................................................................ [2170%]
........................................................................ [2173%]
........................................................................ [2176%]
.[contention-diag] +3981s soak 36p/180t rss 14.9G pss 13.5G swap 0.4G majflt 859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 8 descendant rss 1.0G pss 0.9G | host avail 31.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 35.92 | cgroup 16.2G/max oom_kill 0 | free scratch 329.1G/45345765i tmp 29.7G/1019838i workspace 329.1G/45345765i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 49824 done 3 failed | 18 in flight, oldest 343s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................................................................... [2180%]
........................................................................ [2183%]
........................................................................ [2186%]
........................................................................ [2189%]
........................................................................ [2192%]
........................................................................ [2195%]
........................................................................ [2198%]
........................................................................ [2202%]
.................................................[contention-diag] +3998s soak 44p/200t rss 15.1G pss 13.7G swap 0.5G majflt 894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 16 descendant rss 1.2G pss 1.1G | host avail 30.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 40.41 | cgroup 16.3G/max oom_kill 0 | free scratch 329.1G/45343441i tmp 29.7G/1019838i workspace 329.1G/45343441i | repeat-01 collected 26/26 workers (60601 items) tests 50503 done 3 failed | 18 in flight, oldest 361s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................... [2205%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2217%]
........................................................................ [2220%]
........................................................................ [2224%]
..............................................s......................... [2227%]
........................................................................ [2230%]
.................[contention-diag] +4014s soak 40p/192t rss 15.0G pss 13.6G swap 0.4G majflt 897 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 12 descendant rss 1.1G pss 1.0G | host avail 34.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 35.15 | cgroup 16.3G/max oom_kill 0 | free scratch 329.0G/45341824i tmp 29.7G/1019838i workspace 329.0G/45341824i | repeat-01 collected 26/26 workers (60601 items) tests 51124 done 3 failed | 17 in flight, oldest 376s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................................................... [2233%]
........................................................................ [2236%]
........................................................................ [2239%]
........................................................................ [2242%]
........................................................................ [2246%]
........................................................................ [2249%]
........................................................................ [2252%]
........................................................................ [2255%]
..............................[contention-diag] +4029s soak 45p/190t rss 15.1G pss 13.6G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 17 descendant rss 1.2G pss 1.0G | host avail 33.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 32.25 | cgroup 16.3G/max oom_kill 0 | free scratch 329.1G/45340486i tmp 29.7G/1019838i workspace 329.1G/45340486i | repeat-01 collected 26/26 workers (60601 items) tests 51705 done 3 failed | 17 in flight, oldest 392s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......................................... [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
........................................................................ [2274%]
........................................................................ [2277%]
........................................................................ [2280%]
........................................................................ [2283%]
.............................................................[contention-diag] +4044s soak 37p/183t rss 14.9G pss 13.5G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 9 descendant rss 1.0G pss 0.9G | host avail 34.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.62 cpu 38.45 | cgroup 16.3G/max oom_kill 0 | free scratch 329.0G/45338606i tmp 29.7G/1019838i workspace 329.0G/45338606i | repeat-01 collected 26/26 workers (60601 items) tests 52368 done 3 failed | 17 in flight, oldest 407s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........... [2286%]
........................................................................ [2290%]
........................................................................ [2293%]
........................................................................ [2296%]
........................................................................ [2299%]
........................................................................ [2302%]
........................................................................ [2305%]
........................................................................ [2308%]
........................................................................ [2312%]
....................................................[contention-diag] +4060s soak 38p/170t rss 14.9G pss 13.5G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 10 descendant rss 1.0G pss 0.9G | host avail 32.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.9 cpu 33.33 | cgroup 16.5G/max oom_kill 0 | free scratch 329.0G/45336665i tmp 29.7G/1019838i workspace 329.0G/45336665i | repeat-01 collected 26/26 workers (60601 items) tests 53044 done 3 failed | 18 in flight, oldest 422s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.................... [2315%]
........................................................................ [2318%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2330%]
........................................................................ [2334%]
..........[contention-diag] +4075s soak 39p/179t rss 15.0G pss 13.5G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 11 descendant rss 1.1G pss 1.0G | host avail 32.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 33.36 | cgroup 16.5G/max oom_kill 0 | free scratch 329.0G/45335570i tmp 29.7G/1019838i workspace 329.0G/45335570i | repeat-01 collected 26/26 workers (60601 items) tests 53501 done 3 failed | 18 in flight, oldest 438s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................................. [2337%]
........................................................................ [2340%]
........................................................................ [2343%]
........................................................................ [2346%]
........................................................................ [2349%]
........................................................................ [2352%]
........................................................................ [2356%]
..................[contention-diag] +4091s soak 46p/177t rss 15.0G pss 13.6G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 18 descendant rss 1.1G pss 1.0G | host avail 33.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 33.22 | cgroup 16.5G/max oom_kill 0 | free scratch 329.0G/45334084i tmp 29.7G/1019838i workspace 329.0G/45334084i | repeat-01 collected 26/26 workers (60601 items) tests 54016 done 3 failed | 17 in flight, oldest 453s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................................... [2359%]
........................................................................ [2362%]
........................................................................ [2365%]
........................................................................ [2368%]
.......................................[contention-diag] +4106s soak 43p/188t rss 15.0G pss 13.6G swap 0.4G majflt 861 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 15 descendant rss 1.1G pss 1.0G | host avail 32.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 35.5 | cgroup 16.5G/max oom_kill 0 | free scratch 329.0G/45334728i tmp 29.7G/1019838i workspace 329.0G/45334728i | scratch used 1.0G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60601 items) tests 54285 done 3 failed | 16 in flight, oldest 468s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................. [2371%]
........................................................................ [2374%]
........................................................................ [2378%]
........................................................................ [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
.............................................[contention-diag] +4123s soak 41p/174t rss 15.1G pss 13.6G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 13 descendant rss 1.2G pss 1.1G | host avail 33.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 39.27 | cgroup 16.6G/max oom_kill 0 | free scratch 329.0G/45334326i tmp 29.7G/1019838i workspace 329.0G/45334326i | repeat-01 collected 26/26 workers (60601 items) tests 54757 done 3 failed | 15 in flight, oldest 486s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................... [2390%]
........................................................................ [2393%]
........................................................................ [2396%]
........................................................................ [2400%]
........................................................................ [2403%]
........................................................................ [2406%]
........................................................................ [2409%]
.........................s.....[contention-diag] +4139s soak 42p/176t rss 15.1G pss 13.7G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 14 descendant rss 1.2G pss 1.1G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.62 cpu 38.24 | cgroup 16.7G/max oom_kill 0 | free scratch 329.0G/45333593i tmp 29.7G/1019838i workspace 329.0G/45333593i | repeat-01 collected 26/26 workers (60601 items) tests 55252 done 3 failed | 14 in flight, oldest 501s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
......................................... [2412%]
........................................................................ [2415%]
........................................................................ [2418%]
........................................................................ [2421%]
.......[contention-diag] +4154s soak 35p/158t rss 14.1G pss 12.7G swap 0.4G majflt 860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 7 descendant rss 0.1G pss 0.1G | host avail 33.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 33.79 | cgroup 15.7G/max oom_kill 0 | free scratch 329.0G/45334283i tmp 29.7G/1019837i workspace 329.0G/45334283i | repeat-01 collected 26/26 workers (60601 items) tests 55515 done 3 failed | 10 in flight, oldest 108s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 9 hazardous kill call(s)
................................................................. [2425%]
........................................................................ [2428%]
........................................................................ [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
........................................................................ [2440%]
........................................................................ [2443%]
..........[contention-diag] +4169s soak 36p/166t rss 14.2G pss 12.8G swap 0.4G majflt 863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 8 descendant rss 0.3G pss 0.2G | host avail 33.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 33.83 | cgroup 15.9G/max oom_kill 0 | free scratch 329.2G/45362243i tmp 29.7G/1019838i workspace 329.2G/45362243i | repeat-01 collected 26/26 workers (60601 items) tests 56025 done 3 failed | 11 in flight, oldest 123s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 9 hazardous kill call(s)
.............................................................. [2447%]
........................................................................ [2450%]
........................................................................ [2453%]
........................................................................ [2456%]
........................................................................ [2459%]
........................................................................ [2462%]
...............................[contention-diag] +4185s soak 34p/164t rss 14.1G pss 12.7G swap 0.4G majflt 863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.1G, 6 descendant rss 0.2G pss 0.2G | host avail 32.9G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 30.8 | cgroup 15.8G/max oom_kill 0 | free scratch 329.5G/45438124i tmp 29.7G/1019838i workspace 329.5G/45438124i | repeat-01 collected 26/26 workers (60601 items) tests 56465 done 3 failed | 11 in flight, oldest 78s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 9 hazardous kill call(s)
......................................... [2465%]
........................................................................ [2469%]
........................................................................ [2472%]
........................................................................ [2475%]
...........[contention-diag] +4200s soak 35p/160t rss 14.2G pss 12.8G swap 0.4G majflt 863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 7 descendant rss 0.3G pss 0.2G | host avail 32.7G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.9 cpu 31.3 | cgroup 15.9G/max oom_kill 0 | free scratch 329.8G/45495230i tmp 29.7G/1019838i workspace 329.8G/45495230i | repeat-01 collected 26/26 workers (60601 items) tests 56697 done 3 failed | 10 in flight, oldest 94s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 9 hazardous kill call(s)
............................................................. [2478%]
........................................................................ [2481%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2491%]
........................................................................ [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2503%]
....[contention-diag] +4215s soak 34p/170t rss 14.2G pss 12.8G swap 0.4G majflt 863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 6 descendant rss 0.2G pss 0.2G | host avail 33.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 28.9 | cgroup 15.9G/max oom_kill 0 | free scratch 330.0G/45521180i tmp 29.7G/1019838i workspace 330.0G/45521180i | repeat-01 collected 26/26 workers (60601 items) tests 57344 done 3 failed | 9 in flight, oldest 78s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 9 hazardous kill call(s)
.................................................................... [2506%]
........................................................................ [2509%]
........................................................................ [2513%]
.....................s.................................................. [2516%]
........................................................................ [2519%]
........................................................................ [2522%]
........................................................................ [2525%]
........................................................................ [2528%]
........................................................................ [2531%]
..........[contention-diag] +4231s soak 38p/163t rss 14.3G pss 12.8G swap 0.4G majflt 863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 10 descendant rss 0.3G pss 0.2G | host avail 33.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.45/0.45 io 1.31 cpu 31.4 | cgroup 16.0G/max oom_kill 0 | free scratch 329.9G/45519508i tmp 29.7G/1019838i workspace 329.9G/45519508i | scratch used 0.9G in 165787 entries | repeat-01 collected 26/26 workers (60601 items) tests 57955 done 3 failed | 10 in flight, oldest 14s gw23 tests/tool/test_nested_stage_recording.py::test_fixtures_that_run_run_silent_leave_the_enclosing_run_alone | 9 hazardous kill call(s)
.............................................................. [2535%]
........................................................................ [2538%]
........................................................................ [2541%]
........................................................................ [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
....................[contention-diag] +4248s soak 35p/157t rss 14.1G pss 12.7G swap 0.4G majflt 863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 7 descendant rss 0.1G pss 0.1G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.96 cpu 36.5 | cgroup 15.9G/max oom_kill 0 | free scratch 329.9G/45518821i tmp 29.7G/1019838i workspace 329.9G/45518824i | repeat-01 collected 26/26 workers (60601 items) tests 58481 done 3 failed | 9 in flight, oldest 6s gw9 tests/test_provider_usage_indicator_widget.py::test_unchanged_apply_content_does_not_reissue_static_update | 9 hazardous kill call(s)
.................................................... [2553%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2563%]
........................................................................ [2566%]
........................................................................ [2569%]
........................................................................ [2572%]
........................................................................ [2575%]
........................................................................ [2579%]
................[contention-diag] +4263s soak 32p/162t rss 14.0G pss 12.6G swap 0.4G majflt 864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 4 descendant rss 0.0G pss 0.0G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.26 cpu 36.14 | cgroup 15.8G/max oom_kill 0 | free scratch 329.9G/45517268i tmp 29.7G/1019838i workspace 329.9G/45517268i | repeat-01 collected 26/26 workers (60601 items) tests 59117 done 3 failed | 8 in flight, oldest 8s gw9 tests/test_provider_usage_indicator_widget.py::test_initial_cache_renders_after_header_budget | 9 hazardous kill call(s)
........................................................ [2582%]
........................................................................ [2585%]
........................................................................ [2588%]
........................................................................ [2591%]
...........................................................s............ [2594%]
........................................................................ [2597%]
........................................................................ [2601%]
.................................[contention-diag] +4279s soak 36p/167t rss 14.1G pss 12.6G swap 0.4G majflt 864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 8 descendant rss 0.1G pss 0.0G | host avail 34.0G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.46 cpu 35.07 | cgroup 15.9G/max oom_kill 0 | free scratch 329.9G/45515721i tmp 29.7G/1019838i workspace 329.9G/45515721i | repeat-01 collected 26/26 workers (60601 items) tests 59622 done 3 failed | 8 in flight, oldest 16s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 9 hazardous kill call(s)
....................................... [2604%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
........................................................................ [2616%]
........................................................................ [2619%]
........................................................................ [2623%]
........[contention-diag] +4294s soak 35p/158t rss 14.2G pss 12.8G swap 0.4G majflt 864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 7 descendant rss 0.2G pss 0.1G | host avail 32.8G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 32.75 | cgroup 16.1G/max oom_kill 0 | free scratch 329.9G/45516338i tmp 29.7G/1019838i workspace 329.9G/45516337i | repeat-01 collected 26/26 workers (60601 items) tests 60115 done 3 failed | 6 in flight, oldest 31s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 9 hazardous kill call(s)
................................................................ [2626%]
........................................................................ [2629%]
........................................................................ [2632%]
...................................[contention-diag] +4309s soak 35p/157t rss 14.5G pss 13.1G swap 0.5G majflt 864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 7 descendant rss 0.5G pss 0.4G | host avail 32.6G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.69 cpu 36.16 | cgroup 16.3G/max oom_kill 0 | free scratch 329.9G/45517059i tmp 29.7G/1019838i workspace 329.9G/45517059i | repeat-01 collected 26/26 workers (60601 items) tests 60369 done 3 failed | 4 in flight, oldest 47s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 9 hazardous kill call(s)
..................................... [2635%]
.....................................ssss............................... [2638%]
........................................................................ [2641%]
.....[contention-diag] +4325s soak 32p/149t rss 14.0G pss 12.6G swap 0.4G majflt 867 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 4 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 23.59 | cgroup 15.8G/max oom_kill 0 | free scratch 329.9G/45518904i tmp 29.7G/1019838i workspace 329.9G/45518904i | repeat-01 collected 26/26 workers (60601 items) tests 60541 done 3 failed | 1 in flight, oldest 0s gw9 tests/tool/test_demand_runs.py::test_foreground_run_records_context_usage_and_grant | 9 hazardous kill call(s)
...........................[contention-diag] +4340s soak 34p/153t rss 14.1G pss 12.7G swap 0.4G majflt 867 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.5G pss 12.2G, 6 descendant rss 0.1G pss 0.1G | host avail 33.1G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 4.91 | cgroup 15.9G/max oom_kill 0 | free scratch 329.9G/45518829i tmp 29.7G/1019838i workspace 329.9G/45518829i | repeat-01 collected 26/26 workers (60601 items) tests 60576 done 3 failed | 1 in flight, oldest 5s gw9 tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors | 9 hazardous kill call(s)
.................                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_______________ test_on_mount_refines_title_to_resolved_version ________________
[gw9] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6360a3f3b0>

    async def test_on_mount_refines_title_to_resolved_version(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A resolved dev version replaces the instant ``__version__`` title."""
        dev_version = f"{sase.__version__}+9.gdeadbee.dirty"
        monkeypatch.setattr(
            "sase.ace.tui.util.app_version.resolved_app_version",
            lambda: dev_version,
        )
    
        app = AceApp(query="!!!", auto_start_axe=False)
        async with app.run_test() as pilot:
>           await _wait_for_mount_state_loads(app, pilot)

tests/ace/tui/test_app_title.py:156: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

app = AceApp(title='sase tui (v0.18.1+9.gdeadbee.dirty)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
pilot = <Pilot app=AceApp(title='sase tui (v0.18.1+9.gdeadbee.dirty)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})>

    async def _wait_for_mount_state_loads(app: AceApp, pilot: Pilot[None]) -> None:
        """Poll until the title write's barrier fires, or fail with a clear message."""
        deadline = asyncio.get_running_loop().time() + 15.0
        while not app._mount_state_loads_done:
            if asyncio.get_running_loop().time() >= deadline:
>               raise AssertionError("mount state loads did not finish within 15 seconds")
E               AssertionError: mount state loads did not finish within 15 seconds

tests/ace/tui/test_app_title.py:140: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:295 TUI message pump stall detected: 5.244s pid=3055955
_____________ test_enter_returns_while_macro_file_read_is_blocked ______________
[gw16] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb0bf306120>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw16/test_enter_returns_while_macro0')

    async def test_enter_returns_while_macro_file_read_is_blocked(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        source = tmp_path / "slow.md"
        source.write_text("Slow definition body.", encoding="utf-8")
        prompts = {
            "slow": _md_macro(
                "slow",
                "Slow definition body.",
                source_path=str(source),
            )
        }
        started = Event()
        release = Event()
        original_read_text = Path.read_text
    
        def slow_read_text(path: Path, *args: object, **kwargs: object) -> str:
            if path == source:
                started.set()
                release.wait()
            return original_read_text(path, *args, **kwargs)  # type: ignore[arg-type]
    
        monkeypatch.setattr(Path, "read_text", slow_read_text)
    
        async with AcePage() as page:
            _, pane = await _open_macros_tab(page, monkeypatch, prompts)
            try:
                assert pane.action_edit_macro() is None
                assert await asyncio.wait_for(
                    asyncio.to_thread(started.wait, 10.0), timeout=11.0
                )
                heartbeat = asyncio.Event()
                asyncio.get_running_loop().call_soon(heartbeat.set)
                await asyncio.wait_for(heartbeat.wait(), timeout=2.0)
            finally:
                release.set()
>               await page.wait_for(
                    lambda _s: (
                        bool(page.app.query("#prompt-input-bar"))
                        and bool(page.app.query("PromptTextArea"))
                    ),
                    timeout=10.0,
                )

tests/ace/tui/test_macro_browser_load_keymap.py:199: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:563: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fb0e90b1ee0>

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
E               AssertionError: wait_for() timed out after 10.0s — predicate never returned True

src/sase/ace/testing/wait.py:64: AssertionError

During handling of the above exception, another exception occurred:

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb0bf306120>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-1/popen-gw16/test_enter_returns_while_macro0')

    async def test_enter_returns_while_macro_file_read_is_blocked(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        source = tmp_path / "slow.md"
        source.write_text("Slow definition body.", encoding="utf-8")
        prompts = {
            "slow": _md_macro(
                "slow",
                "Slow definition body.",
                source_path=str(source),
            )
        }
        started = Event()
        release = Event()
        original_read_text = Path.read_text
    
        def slow_read_text(path: Path, *args: object, **kwargs: object) -> str:
            if path == source:
                started.set()
                release.wait()
            return original_read_text(path, *args, **kwargs)  # type: ignore[arg-type]
    
        monkeypatch.setattr(Path, "read_text", slow_read_text)
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_macro_browser_load_keymap.py:187: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:358: in __aexit__
    await stack.__aexit__(exc_type, exc_val, exc_tb)
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:754: in __aexit__
    raise exc_details[1]
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:737: in __aexit__
    cb_suppress = await cb(*exc_details)
                  ^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/contextlib.py:231: in __aexit__
    await self.gen.athrow(value)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/app.py:2145: in run_test
    raise self._exception
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py:595: in _pre_process
    await self._dispatch_message(events.Mount())
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py:101: in on_mount
    self.activate()
src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py:127: in activate
    text_area = self.active_text_area()
                ^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_input_bar_stack_rendering.py:428: in active_text_area
    return self.query_one(f"#{self._pane_id(item)}", PromptTextArea)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PromptInputBar(id='prompt-input-bar', classes='macro-target')
selector = '#prompt-input-g0-p0'
expect_type = <class 'sase.ace.tui.widgets.prompt_text_area.PromptTextArea'>

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
E           textual.css.query.NoMatches: No nodes match '#prompt-input-g0-p0' on PromptInputBar(id='prompt-input-bar', classes='macro-target')

/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/dom.py:1503: NoMatches
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_lifecycle.py:101 in on_mount                   │
│                                                                              │
│    98 │   │   │   │   discard()                                              │
│    99 │   │   except Exception:  # noqa: BLE001 - spare discard is best-effo │
│   100 │   │   │   pass                                                       │
│ ❱ 101 │   │   self.activate()                                                │
│   102 │                                                                      │
│   103 │   def activate(self) -> None:                                        │
│   104 │   │   """Publish, focus, and warm this bar; idempotent after the fir │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │ discard = <bound method PromptBarSpareMixin._discard_prompt_bar_spare of │ │
│ │           AceApp(title='sase tui (v0.18.1)', classes={'-dark-mode'},     │ │
│ │           pseudo_classes={'dark', 'focus'})>                             │ │
│ │    self = PromptInputBar(id='prompt-input-bar', classes='macro-target')  │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_lifecycle.py:127 in activate                   │
│                                                                              │
│   124 │   │   │   self.app._active_prompt_bar = self  # type: ignore[attr-de │
│   125 │   │   except Exception:  # noqa: BLE001 - explicit state is best-eff │
│   126 │   │   │   pass                                                       │
│ ❱ 127 │   │   text_area = self.active_text_area()                            │
│   128 │   │   self.watch(self.app, "theme", self._app_theme_changed, init=Fa │
│   129 │   │   self._sync_todo_counts_from_mounted_panes()                    │
│   130 │   │   text_area.focus()                                              │
│                                                                              │
│ ╭─────────────────────────────── locals ───────────────────────────────╮     │
│ │ self = PromptInputBar(id='prompt-input-bar', classes='macro-target') │     │
│ ╰──────────────────────────────────────────────────────────────────────╯     │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_stack_rendering.py:428 in active_text_area     │
│                                                                              │
│   425 │   def active_text_area(self) -> PromptTextArea:                      │
│   426 │   │   """Return the ``PromptTextArea`` for the currently active pane │
│   427 │   │   item = self._stack.selected_item                               │
│ ❱ 428 │   │   return self.query_one(f"#{self._pane_id(item)}", PromptTextAre │
│   429 │                                                                      │
│   430 │   def active_text(self) -> str:                                      │
│   431 │   │   """Return the active pane's text verbatim."""                  │
│                                                                              │
│ ╭─────────────────────────────── locals ───────────────────────────────╮     │
│ │ item = PromptStackItem(                                              │     │
│ │        │   text='Slow definition body.',                             │     │
│ │        │   item_id='p0',                                             │     │
│ │        │   cursor=(0, 0),                                            │     │
│ │        │   mode='insert',                                            │     │
│ │        │   last_height=None,                                         │     │
│ │        │   snippet_target=None,                                      │     │
│ │        │   mini_macro_target=None                                    │     │
│ │        )                                                             │     │
│ │ self = PromptInputBar(id='prompt-input-bar', classes='macro-target') │     │
│ ╰──────────────────────────────────────────────────────────────────────╯     │
╰──────────────────────────────────────────────────────────────────────────────╯
NoMatches: No nodes match '#prompt-input-g0-p0' on 
PromptInputBar(id='prompt-input-bar', classes='macro-target')
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:396 Unhandled exception in sase's TUI
Traceback (most recent call last):
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py", line 595, in _pre_process
    await self._dispatch_message(events.Mount())
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py", line 101, in on_mount
    self.activate()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py", line 127, in activate
    text_area = self.active_text_area()
                ^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/widgets/_prompt_input_bar_stack_rendering.py", line 428, in active_text_area
    return self.query_one(f"#{self._pane_id(item)}", PromptTextArea)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/dom.py", line 1503, in query_one
    raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
textual.css.query.NoMatches: No nodes match '#prompt-input-g0-p0' on PromptInputBar(id='prompt-input-bar', classes='macro-target')
_______________ test_require_rust_extension_raises_when_missing ________________
[gw16] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb0bf5c4650>

    def test_require_rust_extension_raises_when_missing(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A missing wheel surfaces as :class:`ImportError`, not ``None``.
    
        The strict loader raises with a message that names the package and
        the supported install commands, so callers cannot accidentally
        silently fall back to Python.
        """
        evict_rust_extension(monkeypatch)
    
        def _missing(name: str) -> object:
            raise ImportError(f"No module named {name!r}")
    
        monkeypatch.setattr(importlib, "import_module", _missing)
        with pytest.raises(ImportError) as excinfo:
            require_rust_extension()
        message = str(excinfo.value)
        assert RUST_EXTENSION_MODULE_NAME in message
>       assert "just install-venv" in message
E       AssertionError: assert 'just install-venv' in 'sase_core_rs is not importable in this environment but is a hard runtime dependency of sase; reinstall sase in this environment (for example `uv tool install --force sase`).'

tests/test_core_rust.py:53: AssertionError
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

tests/ace/tui/command_line/test_run_policies.py::test_proc_submit_captures_confirm_flags
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/keymaps/key_validation.py:94: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    return tuple(part.strip() for part in key.split(","))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/dom.py:1735: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    return self._classes.issuperset(class_names)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/core/content_layout_wire.py:270: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    for item in cast(list[Any], raw.get("legacy", []))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/_agent_archive_column_helpers.py:88: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    roots.append(("member", row))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_tabs_launch_view.py::test_view_inherited_tab_name_from_named_tab
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/typing.py:2187: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    def cast(typ, val):
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

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=3056943) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=3055686) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3056356) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

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

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=3055875) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  <frozen os>:888: DeprecationWarning: This process (pid=3055686) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=3056985) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
516.38s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
441.42s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
441.13s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
436.55s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
416.54s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
376.41s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
317.76s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
315.01s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
311.37s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
309.42s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
288.45s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
242.17s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
211.57s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
187.14s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
186.67s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
173.42s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
163.84s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
159.81s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
154.36s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
140.03s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
=========================== short test summary info ============================
FAILED tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version
FAILED tests/ace/tui/test_macro_browser_load_keymap.py::test_enter_returns_while_macro_file_read_is_blocked
FAILED tests/test_core_rust.py::test_require_rust_extension_raises_when_missing
==== 3 failed, 60578 passed, 21 skipped, 111 warnings in 4355.02s (1:12:35) ====
[contention-diag] +4355s soak 11p/25t rss 0.5G pss 0.5G swap 0.0G majflt 296 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 9 worker rss 0.0G pss 0.0G | host avail 44.5G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 23.64 | cgroup 4.0G/max oom_kill 0 | free scratch 329.9G/45519532i tmp 29.7G/1019838i workspace 329.9G/45519532i | scratch used 0.9G in 165764 entries | repeat-01 collected 26/26 workers (60601 items) tests 60590 done 3 failed | 9 hazardous kill call(s)
[contention-diag] +4361s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G | host avail 45.3G/62.7G swapfree 57.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 15.85 | cgroup 3.3G/max oom_kill 0 | free scratch 329.9G/45519554i tmp 29.7G/1019838i workspace 329.9G/45519554i | repeat-01 collected 26/26 workers (60601 items) tests 60601 done 3 failed | 9 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4361s, 282 samples, 0 signal(s); peaks: cgroup_current 16.7G, min_free_scratch 328.7G, min_free_tmp 29.7G, min_free_workspace 328.7G, min_inodes_scratch 45333593, min_inodes_tmp 1019834, min_inodes_workspace 45333593, min_mem_available 30.2G, min_swap_free 57.6G, oom_kill_delta 0, pressure_memory_full 0.62, pswpin_delta 32372, pswpout_delta 111905, scratch_bytes 1.1G, soak_procs 46, soak_pss 13.7G, soak_rss 15.1G, soak_swap 0.5G, soak_threads 298

contention tally: 2 node(s) failed across 1 repeat(s) in 4360.7s; red repeats: 1
  1/1  tests/t.py::test_before_cancel  (repeats 1)
  1/1  tests/test_core_rust.py::test_require_rust_extension_raises_when_missing  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

