# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-6)

- **TIMESTAMP:** 2026-11-08 17:25:48 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-6

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after stitches snapshot-query apply repair for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 408224, sampler pid 408225 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-61054-1794172177424970085.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 40.4G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 325.0G/45342002i tmp 29.0G/1006711i workspace 325.0G/45342002i | scratch used 0.2G in 43070 entries (truncated) | progress none yet
[contention-diag] +17s soak 29p/81t rss 2.3G pss 2.0G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.2G pss 1.9G, 1 descendant rss 0.0G pss 0.0G | host avail 38.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 17.91 | cgroup 2.1G/max oom_kill 0 | free scratch 325.0G/45341901i tmp 29.0G/1006711i workspace 325.0G/45341901i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 3.7G pss 3.3G swap 0.4G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.6G pss 3.2G | host avail 38.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 22.96 | cgroup 3.4G/max oom_kill 0 | free scratch 325.0G/45341886i tmp 29.0G/1006711i workspace 325.0G/45341886i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +48s soak 28p/82t rss 4.7G pss 4.3G swap 0.5G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.6G pss 4.2G | host avail 37.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.9 | cgroup 4.4G/max oom_kill 0 | free scratch 325.0G/45341892i tmp 29.0G/1006711i workspace 325.0G/45341892i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +63s soak 29p/88t rss 5.5G pss 5.0G swap 0.5G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.4G pss 4.9G, 1 descendant rss 0.0G pss 0.0G | host avail 38.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.11 | cgroup 5.1G/max oom_kill 0 | free scratch 325.0G/45341907i tmp 29.0G/1006711i workspace 325.0G/45341907i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/90t rss 6.3G pss 5.7G swap 0.5G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.2G pss 5.6G | host avail 36.8G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.98 | cgroup 5.9G/max oom_kill 0 | free scratch 325.0G/45341911i tmp 29.0G/1006711i workspace 325.0G/45341911i | repeat-01 collected 5/26 workers (11101 items) tests 0 done 0 failed
contention shards: 26 workers collected 60622 items in total (2020-2558 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
....................[contention-diag] +93s soak 31p/95t rss 6.8G pss 6.2G swap 0.5G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.6G pss 6.1G, 3 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.72 | cgroup 6.4G/max oom_kill 0 | free scratch 325.0G/45340775i tmp 29.0G/1006711i workspace 325.0G/45340775i | repeat-01 collected 26/26 workers (60622 items) tests 195 done 0 failed | 26 in flight, oldest 2s gw15 tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
.................................................... [ 12%]
........................................................................ [ 15%]
........................................................................ [ 18%]
........................................................................ [ 21%]
........................................................................ [ 25%]
........................................................................ [ 28%]
........................................................................ [ 31%]
........................................................................ [ 34%]
........................................................................ [ 37%]
........................................................................ [ 40%]
.................[contention-diag] +108s soak 30p/136t rss 7.3G pss 6.7G swap 0.5G majflt 65 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.1G pss 6.5G, 2 descendant rss 0.1G pss 0.1G | host avail 35.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.86 | cgroup 6.8G/max oom_kill 0 | free scratch 325.0G/45339135i tmp 29.0G/1006711i workspace 325.0G/45339135i | repeat-01 collected 26/26 workers (60622 items) tests 942 done 0 failed | 26 in flight, oldest 17s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
....................................................... [ 43%]
........................................................................ [ 46%]
........................................................................ [ 50%]
........................................................................ [ 53%]
.....................................[contention-diag] +124s soak 30p/156t rss 7.6G pss 6.9G swap 0.5G majflt 72 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.7G, 2 descendant rss 0.1G pss 0.1G | host avail 35.8G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.25 | cgroup 7.1G/max oom_kill 0 | free scratch 325.0G/45338413i tmp 29.0G/1006711i workspace 325.0G/45338413i | scratch used 0.4G in 80518 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 1231 done 0 failed | 26 in flight, oldest 32s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
................................... [ 56%]
........................................................................ [ 59%]
........................................................................ [ 62%]
........................................................................ [ 65%]
....................................................................[contention-diag] +141s soak 30p/174t rss 7.9G pss 7.1G swap 0.5G majflt 72 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 6.9G, 2 descendant rss 0.1G pss 0.1G | host avail 34.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 26.94 | cgroup 7.4G/max oom_kill 0 | free scratch 325.0G/45337559i tmp 29.0G/1006711i workspace 325.0G/45337559i | repeat-01 collected 26/26 workers (60622 items) tests 1578 done 0 failed | 26 in flight, oldest 50s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.... [ 68%]
........................................................................ [ 72%]
........................................................................ [ 75%]
........................................................................ [ 78%]
...................................[contention-diag] +156s soak 29p/170t rss 8.0G pss 7.3G swap 0.5G majflt 72 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.1G, 1 descendant rss 0.0G pss 0.0G | host avail 35.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 31.53 | cgroup 7.6G/max oom_kill 0 | free scratch 325.0G/45336872i tmp 29.0G/1006711i workspace 325.0G/45336872i | repeat-01 collected 26/26 workers (60622 items) tests 1830 done 0 failed | 26 in flight, oldest 61s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
..................................... [ 81%]
........................................................................ [ 84%]
...............[contention-diag] +171s soak 33p/192t rss 8.2G pss 7.4G swap 0.5G majflt 74 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.3G, 5 descendant rss 0.1G pss 0.0G | host avail 34.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.34 | cgroup 7.7G/max oom_kill 0 | free scratch 325.0G/45336409i tmp 29.0G/1006711i workspace 325.0G/45336409i | repeat-01 collected 26/26 workers (60622 items) tests 1951 done 0 failed | 26 in flight, oldest 53s gw7 tests/ace/tui/command_line/test_completion_fixes.py::test_tab_through_every_subcommand_reaches_the_last_with_a_highlight
......................................................... [ 87%]
........................................................................ [ 90%]
..............................................................[contention-diag] +186s soak 35p/223t rss 8.4G pss 7.6G swap 0.5G majflt 74 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.4G, 7 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.26 | cgroup 7.9G/max oom_kill 0 | free scratch 324.8G/45335111i tmp 29.0G/1006711i workspace 324.8G/45335111i | repeat-01 collected 26/26 workers (60622 items) tests 2130 done 0 failed | 25 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......... [ 93%]
........................................................................ [ 97%]
........................................................................ [100%]
........................................................................ [103%]
..................................[contention-diag] +202s soak 36p/220t rss 8.7G pss 7.8G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.5G, 8 descendant rss 0.3G pss 0.2G | host avail 33.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.28 | cgroup 8.1G/max oom_kill 0 | free scratch 324.6G/45333384i tmp 29.0G/1006709i workspace 324.6G/45333384i | repeat-01 collected 26/26 workers (60622 items) tests 2401 done 0 failed | 26 in flight, oldest 83s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................... [106%]
........................................................................ [109%]
......................[contention-diag] +217s soak 35p/212t rss 8.8G pss 8.0G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.7G, 7 descendant rss 0.2G pss 0.2G | host avail 31.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.25 | cgroup 8.2G/max oom_kill 0 | free scratch 324.5G/45332997i tmp 29.0G/1006711i workspace 324.5G/45332997i | repeat-01 collected 26/26 workers (60622 items) tests 2533 done 0 failed | 26 in flight, oldest 98s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................. [112%]
........................................................................ [115%]
........................................................[contention-diag] +232s soak 34p/214t rss 8.9G pss 8.1G swap 0.5G majflt 75 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 7.8G, 6 descendant rss 0.2G pss 0.1G | host avail 29.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.85 | cgroup 8.4G/max oom_kill 0 | free scratch 324.3G/45332485i tmp 29.0G/1006711i workspace 324.3G/45332485i | repeat-01 collected 26/26 workers (60622 items) tests 2720 done 0 failed | 26 in flight, oldest 114s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................ [119%]
........................................................................ [122%]
..........[contention-diag] +248s soak 36p/222t rss 9.0G pss 8.2G swap 0.5G majflt 75 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 7.9G, 8 descendant rss 0.2G pss 0.1G | host avail 28.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 23.51 | cgroup 8.4G/max oom_kill 0 | free scratch 324.2G/45332251i tmp 29.0G/1006711i workspace 324.2G/45332251i | scratch used 0.6G in 103761 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 2793 done 0 failed | 26 in flight, oldest 129s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................................. [125%]
........................................................................ [128%]
........................................................................ [131%]
...........[contention-diag] +265s soak 37p/219t rss 9.2G pss 8.4G swap 0.6G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.0G, 9 descendant rss 0.3G pss 0.3G | host avail 27.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 25.12 | cgroup 8.7G/max oom_kill 0 | free scratch 324.0G/45331550i tmp 29.0G/1006711i workspace 324.0G/45331550i | repeat-01 collected 26/26 workers (60622 items) tests 3024 done 0 failed | 25 in flight, oldest 146s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................. [134%]
........................................................................ [137%]
..........................................[contention-diag] +280s soak 33p/223t rss 9.1G pss 8.2G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 28.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.18 | cgroup 8.5G/max oom_kill 0 | free scratch 324.0G/45331045i tmp 29.0G/1006711i workspace 324.0G/45331045i | repeat-01 collected 26/26 workers (60622 items) tests 3202 done 0 failed | 26 in flight, oldest 162s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................[contention-diag] +295s soak 33p/245t rss 9.1G pss 8.3G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 30.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.49 | cgroup 8.6G/max oom_kill 0 | free scratch 324.0G/45330907i tmp 29.0G/1006711i workspace 324.0G/45330907i | repeat-01 collected 26/26 workers (60622 items) tests 3228 done 0 failed | 26 in flight, oldest 177s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......... [140%]
................[contention-diag] +311s soak 35p/251t rss 9.3G pss 8.4G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.2G, 7 descendant rss 0.1G pss 0.1G | host avail 28.9G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.59 | cgroup 8.7G/max oom_kill 0 | free scratch 324.0G/45330738i tmp 29.0G/1006711i workspace 324.0G/45330738i | repeat-01 collected 26/26 workers (60622 items) tests 3250 done 0 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................................ [144%]
....................[contention-diag] +326s soak 37p/249t rss 9.3G pss 8.5G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.3G, 9 descendant rss 0.1G pss 0.1G | host avail 29.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 20.4 | cgroup 8.8G/max oom_kill 0 | free scratch 324.5G/45330083i tmp 29.0G/1006710i workspace 324.5G/45330083i | repeat-01 collected 26/26 workers (60622 items) tests 3324 done 0 failed | 26 in flight, oldest 207s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................... [147%]
........................................................................ [150%]
............[contention-diag] +341s soak 34p/237t rss 9.4G pss 8.5G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 30.9G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 19.53 | cgroup 8.8G/max oom_kill 0 | free scratch 324.3G/45329743i tmp 29.0G/1006710i workspace 324.3G/45329743i | repeat-01 collected 26/26 workers (60622 items) tests 3448 done 0 failed | 26 in flight, oldest 223s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................ [153%]
........................................................................ [156%]
..........................[contention-diag] +356s soak 33p/257t rss 9.4G pss 8.6G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 30.0G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 22.41 | cgroup 8.9G/max oom_kill 0 | free scratch 324.2G/45329220i tmp 29.0G/1006710i workspace 324.2G/45329220i | repeat-01 collected 26/26 workers (60622 items) tests 3624 done 0 failed | 26 in flight, oldest 238s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...........[contention-diag] +372s soak 35p/256t rss 9.6G pss 8.7G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.5G, 7 descendant rss 0.2G pss 0.1G | host avail 27.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 21.73 | cgroup 9.0G/max oom_kill 0 | free scratch 324.1G/45329075i tmp 29.0G/1006710i workspace 324.1G/45329075i | scratch used 0.6G in 117123 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 3634 done 0 failed | 26 in flight, oldest 253s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [159%]
........................................................................ [162%]
...............[contention-diag] +389s soak 40p/276t rss 9.7G pss 8.8G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.6G, 12 descendant rss 0.2G pss 0.1G | host avail 28.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.1 cpu 20.1 | cgroup 9.2G/max oom_kill 0 | free scratch 324.1G/45328655i tmp 29.0G/1006710i workspace 324.1G/45328655i | repeat-01 collected 26/26 workers (60622 items) tests 3758 done 0 failed | 26 in flight, oldest 270s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................[contention-diag] +404s soak 38p/258t rss 9.7G pss 8.8G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.6G, 10 descendant rss 0.1G pss 0.0G | host avail 28.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.02 cpu 23.18 | cgroup 9.2G/max oom_kill 0 | free scratch 324.0G/45328468i tmp 29.0G/1006710i workspace 324.0G/45328468i | repeat-01 collected 26/26 workers (60622 items) tests 3775 done 0 failed | 26 in flight, oldest 286s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [165%]
........................................................................ [169%]
.....................................[contention-diag] +419s soak 38p/269t rss 9.7G pss 8.8G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.6G, 10 descendant rss 0.1G pss 0.0G | host avail 28.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.35 | cgroup 9.2G/max oom_kill 0 | free scratch 324.0G/45328081i tmp 29.0G/1006710i workspace 324.0G/45328081i | repeat-01 collected 26/26 workers (60622 items) tests 3925 done 0 failed | 26 in flight, oldest 301s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [172%]
.........................[contention-diag] +435s soak 41p/292t rss 9.9G pss 9.0G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.7G, 13 descendant rss 0.3G pss 0.2G | host avail 31.4G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.28 | cgroup 9.3G/max oom_kill 0 | free scratch 324.0G/45327867i tmp 29.0G/1006710i workspace 324.0G/45327867i | repeat-01 collected 26/26 workers (60622 items) tests 3981 done 0 failed | 26 in flight, oldest 316s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................... [175%]
........................................................................ [178%]
.....................[contention-diag] +450s soak 37p/247t rss 9.9G pss 9.0G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.7G, 9 descendant rss 0.2G pss 0.1G | host avail 33.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.96 cpu 23.71 | cgroup 9.4G/max oom_kill 0 | free scratch 324.0G/45329837i tmp 29.0G/1006708i workspace 324.0G/45329837i | repeat-01 collected 26/26 workers (60622 items) tests 4123 done 0 failed | 26 in flight, oldest 331s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................... [181%]
........................[contention-diag] +465s soak 35p/254t rss 9.9G pss 9.0G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 33.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.47 cpu 23.74 | cgroup 9.4G/max oom_kill 0 | free scratch 324.0G/45329608i tmp 29.0G/1006708i workspace 324.0G/45329608i | repeat-01 collected 26/26 workers (60622 items) tests 4197 done 0 failed | 26 in flight, oldest 347s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................ [184%]
.................[contention-diag] +480s soak 35p/289t rss 10.0G pss 9.1G swap 0.5G majflt 76 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 31.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 22.62 | cgroup 9.5G/max oom_kill 0 | free scratch 323.9G/45329336i tmp 29.0G/1006708i workspace 323.9G/45329336i | repeat-01 collected 26/26 workers (60622 items) tests 4261 done 0 failed | 26 in flight, oldest 362s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [187%]
...........................[contention-diag] +496s soak 29p/254t rss 9.9G pss 9.1G swap 0.5G majflt 77 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 8.9G, 1 descendant rss 0.1G pss 0.1G | host avail 30.9G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.9 cpu 21.75 | cgroup 9.4G/max oom_kill 0 | free scratch 323.8G/45329056i tmp 29.0G/1006708i workspace 323.8G/45329056i | scratch used 0.7G in 131660 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 4338 done 0 failed | 26 in flight, oldest 377s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................. [191%]
.....................................................[contention-diag] +513s soak 30p/240t rss 10.1G pss 9.2G swap 0.6G majflt 77 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 8.9G, 2 descendant rss 0.2G pss 0.1G | host avail 29.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.1 cpu 22.12 | cgroup 9.6G/max oom_kill 0 | free scratch 323.7G/45328681i tmp 29.0G/1006708i workspace 323.7G/45328681i | repeat-01 collected 26/26 workers (60622 items) tests 4443 done 0 failed | 26 in flight, oldest 76s gw16 tests/ace/tui/modals/test_memory_panel_history.py::test_no_call_from_thread_in_async_workers_under_ace_tui
............[contention-diag] +528s soak 29p/250t rss 10.0G pss 9.1G swap 0.5G majflt 79 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 20.41 | cgroup 9.5G/max oom_kill 0 | free scratch 323.6G/45328431i tmp 29.0G/1006708i workspace 323.6G/45328431i | repeat-01 collected 26/26 workers (60622 items) tests 4456 done 0 failed | 26 in flight, oldest 49s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
....... [194%]
.......................................[contention-diag] +544s soak 30p/231t rss 10.1G pss 9.3G swap 0.5G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.39 cpu 26.84 | cgroup 9.6G/max oom_kill 0 | free scratch 323.6G/45328227i tmp 29.0G/1006708i workspace 323.6G/45328227i | repeat-01 collected 26/26 workers (60622 items) tests 4497 done 0 failed | 26 in flight, oldest 65s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
.......................[contention-diag] +559s soak 31p/251t rss 10.1G pss 9.3G swap 0.5G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.0G, 3 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 24.05 | cgroup 9.6G/max oom_kill 0 | free scratch 323.6G/45327968i tmp 29.0G/1006708i workspace 323.6G/45327968i | repeat-01 collected 26/26 workers (60622 items) tests 4521 done 0 failed | 26 in flight, oldest 80s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
.......... [197%]
........................................................................ [200%]
.............[contention-diag] +574s soak 30p/242t rss 10.2G pss 9.3G swap 0.6G majflt 89 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.1G, 2 descendant rss 0.2G pss 0.1G | host avail 28.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.29/0.19 io 1.21 cpu 18.29 | cgroup 9.7G/max oom_kill 0 | free scratch 323.0G/45327278i tmp 29.0G/1006708i workspace 323.0G/45327278i | repeat-01 collected 26/26 workers (60622 items) tests 4618 done 0 failed | 26 in flight, oldest 95s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
................................................[contention-diag] +590s soak 28p/237t rss 10.1G pss 9.2G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.1G | host avail 28.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.43/0.41 io 1.18 cpu 19.68 | cgroup 9.6G/max oom_kill 0 | free scratch 323.0G/45327044i tmp 29.0G/1006708i workspace 323.0G/45327044i | repeat-01 collected 26/26 workers (60622 items) tests 4666 done 0 failed | 26 in flight, oldest 77s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
........... [203%]
.............................[contention-diag] +605s soak 29p/236t rss 10.2G pss 9.3G swap 0.6G majflt 98 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.1G, 1 descendant rss 0.1G pss 0.0G | host avail 29.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.14 io 1.99 cpu 22.62 | cgroup 9.7G/max oom_kill 0 | free scratch 322.9G/45326831i tmp 29.0G/1006708i workspace 322.9G/45326831i | repeat-01 collected 26/26 workers (60622 items) tests 4706 done 0 failed | 26 in flight, oldest 49s gw18 tests/ace/tui/command_line/test_policy_io.py::test_poll_once_ticks_submitting_without_log_read
...........[contention-diag] +620s soak 30p/252t rss 10.2G pss 9.3G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.2G, 2 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 1.82 cpu 25.49 | cgroup 9.7G/max oom_kill 0 | free scratch 322.8G/45326732i tmp 29.0G/1006708i workspace 322.8G/45326732i | scratch used 0.2G in 36267 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 4716 done 0 failed | 26 in flight, oldest 61s gw19 tests/ace/tui/test_agent_grouping_picker.py::test_agents_default_oo_toggles_panel_layout_once_and_preserves_mode
................................ [206%]
.........................[contention-diag] +637s soak 28p/256t rss 10.2G pss 9.3G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.2G | host avail 28.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.17 cpu 23.94 | cgroup 9.8G/max oom_kill 0 | free scratch 322.6G/45326456i tmp 29.0G/1006708i workspace 322.6G/45326456i | repeat-01 collected 26/26 workers (60622 items) tests 4771 done 0 failed | 26 in flight, oldest 52s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_marks_render_and_footer_syncs
..............................[contention-diag] +653s soak 28p/250t rss 10.2G pss 9.4G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.2G | host avail 31.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.39 cpu 28.45 | cgroup 9.9G/max oom_kill 0 | free scratch 322.6G/45326252i tmp 29.0G/1006708i workspace 322.6G/45326252i | repeat-01 collected 26/26 workers (60622 items) tests 4806 done 0 failed | 26 in flight, oldest 65s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
................. [209%]
....................[contention-diag] +668s soak 29p/233t rss 10.3G pss 9.5G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G, 1 descendant rss 0.1G pss 0.1G | host avail 31.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.94 cpu 24.96 | cgroup 10.0G/max oom_kill 0 | free scratch 322.6G/45326065i tmp 29.0G/1006708i workspace 322.6G/45326065i | repeat-01 collected 26/26 workers (60622 items) tests 4843 done 0 failed | 26 in flight, oldest 65s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...............................[contention-diag] +683s soak 29p/236t rss 10.4G pss 9.5G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.3G, 1 descendant rss 0.1G pss 0.0G | host avail 28.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.18 cpu 23.82 | cgroup 10.0G/max oom_kill 0 | free scratch 323.1G/45325837i tmp 29.0G/1006708i workspace 323.1G/45325837i | repeat-01 collected 26/26 workers (60622 items) tests 4873 done 0 failed | 26 in flight, oldest 62s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_picker_acts_on_focused_split_panel
.........[contention-diag] +698s soak 28p/247t rss 10.3G pss 9.5G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G | host avail 27.8G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.44/0.29 io 0.77 cpu 18.01 | cgroup 10.0G/max oom_kill 0 | free scratch 322.9G/45325667i tmp 29.0G/1006708i workspace 322.9G/45325667i | repeat-01 collected 26/26 workers (60622 items) tests 4884 done 0 failed | 26 in flight, oldest 59s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
..........[contention-diag] +714s soak 28p/246t rss 10.4G pss 9.5G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G | host avail 26.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.27/0.24 io 1.08 cpu 18.12 | cgroup 10.1G/max oom_kill 0 | free scratch 322.8G/45325568i tmp 29.0G/1006708i workspace 322.8G/45325568i | repeat-01 collected 26/26 workers (60622 items) tests 4893 done 0 failed | 26 in flight, oldest 74s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
.. [212%]
...............................[contention-diag] +729s soak 30p/242t rss 10.5G pss 9.6G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.4G, 2 descendant rss 0.1G pss 0.1G | host avail 26.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.04 io 1.55 cpu 22.31 | cgroup 10.1G/max oom_kill 0 | free scratch 322.8G/45325363i tmp 29.0G/1006708i workspace 322.8G/45325363i | repeat-01 collected 26/26 workers (60622 items) tests 4925 done 0 failed | 26 in flight, oldest 55s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
......................................... [216%]
........................................................................ [219%]
.....[contention-diag] +744s soak 29p/233t rss 10.5G pss 9.6G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G, 1 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 1.94 cpu 21.0 | cgroup 10.2G/max oom_kill 0 | free scratch 322.5G/45324580i tmp 29.0G/1006708i workspace 322.5G/45324580i | scratch used 0.4G in 69287 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 5037 done 0 failed | 26 in flight, oldest 63s gw11 tests/ace/tui/test_agent_cleanup_panel_clan_sticky_e2e.py::test_cleanup_kill_folded_clan_unmounts_its_tribe_panel
................................................................... [222%]
.......................................................................[contention-diag] +762s soak 28p/230t rss 10.5G pss 9.6G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G | host avail 26.5G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.5 cpu 20.63 | cgroup 10.3G/max oom_kill 0 | free scratch 322.4G/45324094i tmp 29.0G/1006708i workspace 322.4G/45324094i | repeat-01 collected 26/26 workers (60622 items) tests 5181 done 0 failed | 26 in flight, oldest 48s gw19 tests/ace/tui/test_agent_grouping_picker.py::test_agents_grouping_result_after_tab_change_is_ignored
. [225%]
........................................................................ [228%]
........................................................................ [231%]
....................................................................[contention-diag] +777s soak 29p/254t rss 10.5G pss 9.7G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.63 cpu 19.28 | cgroup 10.2G/max oom_kill 0 | free scratch 322.4G/45323477i tmp 29.0G/1006708i workspace 322.4G/45323477i | repeat-01 collected 26/26 workers (60622 items) tests 5391 done 0 failed | 26 in flight, oldest 60s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
.... [234%]
......................................[contention-diag] +792s soak 30p/269t rss 10.6G pss 9.7G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 2 descendant rss 0.1G pss 0.1G | host avail 31.2G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 25.67 | cgroup 10.3G/max oom_kill 0 | free scratch 322.2G/45323284i tmp 29.0G/1006707i workspace 322.2G/45323284i | repeat-01 collected 26/26 workers (60622 items) tests 5436 done 0 failed | 26 in flight, oldest 75s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................................. [238%]
........................................................................ [241%]
..............................[contention-diag] +808s soak 30p/230t rss 10.7G pss 9.8G swap 0.6G majflt 88 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 29.3G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 19.56 | cgroup 10.4G/max oom_kill 0 | free scratch 322.1G/45322064i tmp 29.0G/1006707i workspace 322.1G/45322064i | repeat-01 collected 26/26 workers (60622 items) tests 5560 done 0 failed | 26 in flight, oldest 90s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.......................................... [244%]
...................[contention-diag] +823s soak 29p/236t rss 10.6G pss 9.7G swap 0.6G majflt 93 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 16.5 | cgroup 10.4G/max oom_kill 0 | free scratch 321.7G/45321012i tmp 29.0G/1006707i workspace 321.7G/45321012i | repeat-01 collected 26/26 workers (60622 items) tests 5631 done 0 failed | 26 in flight, oldest 106s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................................[contention-diag] +838s soak 31p/262t rss 10.8G pss 9.8G swap 0.6G majflt 89 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.6G, 3 descendant rss 0.1G pss 0.1G | host avail 26.5G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 19.28 | cgroup 10.4G/max oom_kill 0 | free scratch 321.7G/45320742i tmp 29.0G/1006705i workspace 321.7G/45320742i | repeat-01 collected 26/26 workers (60622 items) tests 5665 done 0 failed | 26 in flight, oldest 121s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................[contention-diag] +854s soak 32p/267t rss 10.8G pss 9.9G swap 0.6G majflt 89 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.7G, 4 descendant rss 0.1G pss 0.0G | host avail 27.0G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.01 cpu 21.66 | cgroup 10.5G/max oom_kill 0 | free scratch 321.7G/45320609i tmp 29.0G/1006707i workspace 321.7G/45320609i | repeat-01 collected 26/26 workers (60622 items) tests 5682 done 0 failed | 26 in flight, oldest 136s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.... [247%]
........................................................................ [250%]
..............................................[contention-diag] +869s soak 29p/228t rss 10.8G pss 9.9G swap 0.6G majflt 89 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 1 descendant rss 0.1G pss 0.1G | host avail 25.4G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.26 cpu 21.57 | cgroup 10.6G/max oom_kill 0 | free scratch 321.7G/45320313i tmp 29.0G/1006707i workspace 321.7G/45320313i | scratch used 0.5G in 98213 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 5772 done 0 failed | 26 in flight, oldest 55s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_toggle_clamps_container_and_restores_width
.......................... [253%]
............[contention-diag] +886s soak 28p/233t rss 10.8G pss 9.9G swap 0.6G majflt 89 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G | host avail 23.8G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 0.31/0.31 io 1.85 cpu 20.51 | cgroup 10.4G/max oom_kill 0 | free scratch 321.6G/45319990i tmp 29.0G/1006707i workspace 321.6G/45319990i | repeat-01 collected 26/26 workers (60622 items) tests 5841 done 0 failed | 26 in flight, oldest 72s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_toggle_clamps_container_and_restores_width
............................................................ [256%]
........................................................................ [259%]
.................................................................[contention-diag] +901s soak 28p/231t rss 10.8G pss 9.9G swap 0.7G majflt 89 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G | host avail 22.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 1.24/1.07 io 3.27 cpu 16.13 | cgroup 10.5G/max oom_kill 0 | free scratch 321.4G/45319490i tmp 29.0G/1006707i workspace 321.4G/45319490i | repeat-01 collected 26/26 workers (60622 items) tests 6021 done 0 failed | 26 in flight, oldest 59s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
....... [263%]
........................................................................ [266%]
........................................................................ [269%]
.....................................................................[contention-diag] +917s soak 29p/228t rss 10.8G pss 10.0G swap 0.7G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.53/0.49 io 2.43 cpu 16.83 | cgroup 10.5G/max oom_kill 0 | free scratch 319.9G/45318695i tmp 29.0G/1006707i workspace 319.9G/45318695i | repeat-01 collected 26/26 workers (60622 items) tests 6248 done 0 failed | 26 in flight, oldest 74s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
... [272%]
........................................................................ [275%]
.........................[contention-diag] +932s soak 28p/213t rss 10.8G pss 10.0G swap 0.7G majflt 93 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G | host avail 26.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.25/0.09 io 1.73 cpu 17.31 | cgroup 10.5G/max oom_kill 0 | free scratch 319.6G/45318292i tmp 29.0G/1006707i workspace 319.6G/45318292i | repeat-01 collected 26/26 workers (60622 items) tests 6358 done 0 failed | 26 in flight, oldest 46s gw1 tests/ace/tui/test_plugins_browser_pane_update.py::test_plugins_pane_editable_update_skipped_reason_toasts
............................................... [278%]
....[contention-diag] +947s soak 28p/243t rss 10.9G pss 10.0G swap 0.7G majflt 93 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.05/0.01 io 1.93 cpu 12.93 | cgroup 10.6G/max oom_kill 0 | free scratch 319.4G/45315063i tmp 29.0G/1006707i workspace 319.4G/45315063i | repeat-01 collected 26/26 workers (60622 items) tests 6411 done 0 failed | 26 in flight, oldest 55s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
.....................[contention-diag] +962s soak 28p/258t rss 10.9G pss 10.0G swap 0.7G majflt 93 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G | host avail 31.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.62 cpu 13.33 | cgroup 10.6G/max oom_kill 0 | free scratch 319.4G/45316903i tmp 29.0G/1006707i workspace 319.4G/45316903i | repeat-01 collected 26/26 workers (60622 items) tests 6433 done 0 failed | 26 in flight, oldest 70s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
............................................... [281%]
........................................................................ [284%]
.....................................[contention-diag] +978s soak 28p/218t rss 10.9G pss 10.0G swap 0.7G majflt 109 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.9G | host avail 30.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.0 cpu 12.88 | cgroup 10.6G/max oom_kill 0 | free scratch 319.1G/45290475i tmp 29.0G/1006199i workspace 319.1G/45290475i | repeat-01 collected 26/26 workers (60622 items) tests 6582 done 0 failed | 26 in flight, oldest 67s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
................................... [288%]
.........................[contention-diag] +993s soak 28p/222t rss 10.9G pss 10.1G swap 0.7G majflt 109 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G | host avail 29.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.61 cpu 10.63 | cgroup 10.7G/max oom_kill 0 | free scratch 319.2G/45289505i tmp 29.0G/1006562i workspace 319.2G/45289505i | scratch used 0.3G in 64270 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 6647 done 0 failed | 26 in flight, oldest 68s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
............................................... [291%]
...............[contention-diag] +1011s soak 29p/230t rss 11.0G pss 10.1G swap 0.7G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G, 1 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.45 cpu 23.86 | cgroup 10.7G/max oom_kill 0 | free scratch 319.2G/45287947i tmp 29.0G/1006653i workspace 319.2G/45287947i | repeat-01 collected 26/26 workers (60622 items) tests 6702 done 0 failed | 26 in flight, oldest 53s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_toggle_install_mark_noops_for_installed
......................................................... [294%]
......[contention-diag] +1026s soak 32p/242t rss 11.1G pss 10.1G swap 0.7G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.0G, 4 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.56 cpu 26.53 | cgroup 10.7G/max oom_kill 0 | free scratch 319.2G/45287621i tmp 29.0G/1006653i workspace 319.2G/45287621i | repeat-01 collected 26/26 workers (60622 items) tests 6774 done 0 failed | 26 in flight, oldest 57s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
.................................................................. [297%]
................[contention-diag] +1041s soak 29p/221t rss 11.1G pss 10.2G swap 0.7G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.37 cpu 24.77 | cgroup 10.8G/max oom_kill 0 | free scratch 319.2G/45287520i tmp 29.0G/1006666i workspace 319.2G/45287520i | repeat-01 collected 26/26 workers (60622 items) tests 6854 done 0 failed | 26 in flight, oldest 72s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........................................................ [300%]
........................................................................ [303%]
.....................................[contention-diag] +1057s soak 29p/219t rss 11.1G pss 10.2G swap 0.7G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 32.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.29 cpu 16.54 | cgroup 10.8G/max oom_kill 0 | free scratch 319.2G/45287198i tmp 29.0G/1006681i workspace 319.2G/45287198i | repeat-01 collected 26/26 workers (60622 items) tests 7018 done 0 failed | 26 in flight, oldest 46s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_limit_all_then_ctrl_k_introduces_page_size
................................... [306%]
...............................................[contention-diag] +1072s soak 31p/235t rss 11.2G pss 10.3G swap 0.7G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 3 descendant rss 0.1G pss 0.1G | host avail 32.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 16.2 | cgroup 10.9G/max oom_kill 0 | free scratch 319.2G/45286500i tmp 29.0G/1006681i workspace 319.2G/45286500i | repeat-01 collected 26/26 workers (60622 items) tests 7102 done 0 failed | 26 in flight, oldest 50s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
......................... [310%]
........[contention-diag] +1087s soak 30p/231t rss 11.2G pss 10.3G swap 0.7G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 2 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 17.2 | cgroup 10.9G/max oom_kill 0 | free scratch 319.2G/45286657i tmp 29.0G/1006681i workspace 319.2G/45286657i | repeat-01 collected 26/26 workers (60622 items) tests 7135 done 0 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................................................................ [313%]
........................................................................ [316%]
..............................................................[contention-diag] +1103s soak 29p/235t rss 11.2G pss 10.3G swap 0.7G majflt 117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 1 descendant rss 0.1G pss 0.0G | host avail 30.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 23.11 | cgroup 10.9G/max oom_kill 0 | free scratch 319.2G/45286162i tmp 29.0G/1006681i workspace 319.2G/45286162i | repeat-01 collected 26/26 workers (60622 items) tests 7333 done 0 failed | 26 in flight, oldest 63s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
.......... [319%]
........................................................................ [322%]
...............[contention-diag] +1118s soak 28p/202t rss 11.2G pss 10.2G swap 0.7G majflt 120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.8 cpu 21.07 | cgroup 10.9G/max oom_kill 0 | free scratch 319.1G/45282731i tmp 29.0G/1006681i workspace 319.1G/45282731i | scratch used 0.5G in 103184 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 7404 done 0 failed | 26 in flight, oldest 46s gw4 tests/ace/tui/test_artifacts_files_loading.py::test_error_snapshot_renders_status_without_crashing
......................................................... [325%]
........................................................................ [328%]
............................[contention-diag] +1135s soak 28p/247t rss 11.2G pss 10.3G swap 0.7G majflt 120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G | host avail 30.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.38/0.38 io 0.36 cpu 14.86 | cgroup 10.9G/max oom_kill 0 | free scratch 319.1G/45284434i tmp 29.0G/1006681i workspace 319.1G/45284434i | repeat-01 collected 26/26 workers (60622 items) tests 7577 done 0 failed | 26 in flight, oldest 52s gw12 tests/ace/tui/test_artifacts_plans_interactions.py::test_plans_pane_navigates_three_document_sections
............................................ [331%]
........................................................................ [335%]
.............[contention-diag] +1150s soak 38p/254t rss 11.3G pss 10.3G swap 0.7G majflt 120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 32.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.43 cpu 24.59 | cgroup 10.9G/max oom_kill 0 | free scratch 319.1G/45284091i tmp 29.0G/1006681i workspace 319.1G/45284091i | repeat-01 collected 26/26 workers (60622 items) tests 7717 done 0 failed | 26 in flight, oldest 64s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
...................[contention-diag] +1166s soak 38p/256t rss 11.3G pss 10.3G swap 0.7G majflt 121 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 30.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.53 cpu 25.32 | cgroup 11.0G/max oom_kill 0 | free scratch 319.1G/45283957i tmp 29.0G/1006681i workspace 319.1G/45283957i | repeat-01 collected 26/26 workers (60622 items) tests 7729 done 0 failed | 25 in flight, oldest 79s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
......[contention-diag] +1181s soak 38p/294t rss 11.3G pss 10.3G swap 0.7G majflt 121 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 30.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 23.4 | cgroup 11.0G/max oom_kill 0 | free scratch 319.1G/45283639i tmp 29.0G/1004435i workspace 319.1G/45283639i | repeat-01 collected 26/26 workers (60622 items) tests 7742 done 0 failed | 26 in flight, oldest 94s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................................[contention-diag] +1196s soak 38p/283t rss 11.3G pss 10.4G swap 0.7G majflt 122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 29.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.78 cpu 25.55 | cgroup 11.0G/max oom_kill 0 | free scratch 319.1G/45283447i tmp 29.0G/1004435i workspace 319.1G/45283447i | repeat-01 collected 26/26 workers (60622 items) tests 7773 done 0 failed | 25 in flight, oldest 109s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.. [338%]
............................................[contention-diag] +1212s soak 29p/237t rss 11.2G pss 10.3G swap 0.7G majflt 122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 29.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 24.68 | cgroup 11.0G/max oom_kill 0 | free scratch 319.1G/45283242i tmp 29.0G/1004435i workspace 319.1G/45283242i | repeat-01 collected 26/26 workers (60622 items) tests 7817 done 0 failed | 26 in flight, oldest 125s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
............................ [341%]
..............................................[contention-diag] +1227s soak 38p/253t rss 11.4G pss 10.4G swap 0.7G majflt 122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 28.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.37 cpu 24.34 | cgroup 11.1G/max oom_kill 0 | free scratch 319.1G/45282939i tmp 29.0G/1004435i workspace 319.1G/45282939i | repeat-01 collected 26/26 workers (60622 items) tests 7893 done 0 failed | 26 in flight, oldest 45s gw6 tests/ace/tui/modals/test_preview_panel_modal_search.py::test_preview_modal_forwards_percent_to_app_copy_mode
.......................... [344%]
............................................[contention-diag] +1242s soak 38p/260t rss 11.4G pss 10.4G swap 0.7G majflt 122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 26.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.4 cpu 22.14 | cgroup 11.1G/max oom_kill 0 | free scratch 319.1G/45282652i tmp 29.0G/1004433i workspace 319.1G/45282652i | scratch used 0.7G in 125159 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 7954 done 0 failed | 26 in flight, oldest 60s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
............................ [347%]
................................................................[contention-diag] +1260s soak 38p/249t rss 11.4G pss 10.4G swap 0.7G majflt 123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 25.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 2.37 cpu 23.21 | cgroup 11.1G/max oom_kill 0 | free scratch 319.1G/45282308i tmp 29.0G/1004435i workspace 319.1G/45282308i | repeat-01 collected 26/26 workers (60622 items) tests 8055 done 0 failed | 26 in flight, oldest 49s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
........ [350%]
...........................[contention-diag] +1275s soak 28p/242t rss 11.3G pss 10.4G swap 0.7G majflt 123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G | host avail 25.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.64 cpu 21.55 | cgroup 11.1G/max oom_kill 0 | free scratch 319.0G/45282127i tmp 29.0G/1004435i workspace 319.0G/45282127i | repeat-01 collected 26/26 workers (60622 items) tests 8091 done 0 failed | 26 in flight, oldest 65s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
............................................. [353%]
........................................................................ [357%]
.........[contention-diag] +1290s soak 29p/243t rss 11.3G pss 10.4G swap 0.7G majflt 123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 27.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 0.7 cpu 19.31 | cgroup 11.1G/max oom_kill 0 | free scratch 318.7G/45281756i tmp 29.0G/1004435i workspace 318.7G/45281756i | repeat-01 collected 26/26 workers (60622 items) tests 8207 done 0 failed | 26 in flight, oldest 46s gw16 tests/ace/tui/test_macro_browser_jump.py::test_apostrophe_enters_jump_mode_with_hints_skipping_headers
...........................................................[contention-diag] +1306s soak 28p/237t rss 11.3G pss 10.4G swap 0.7G majflt 123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G | host avail 30.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 1.5 cpu 20.56 | cgroup 11.1G/max oom_kill 0 | free scratch 319.1G/45281192i tmp 29.0G/1004435i workspace 319.1G/45281192i | repeat-01 collected 26/26 workers (60622 items) tests 8270 done 0 failed | 26 in flight, oldest 59s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.... [360%]
........................................................................ [363%]
........................................................................ [366%]
...............................................[contention-diag] +1321s soak 28p/251t rss 11.4G pss 10.4G swap 0.7G majflt 138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G | host avail 28.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.14 cpu 17.49 | cgroup 11.2G/max oom_kill 0 | free scratch 319.0G/45276571i tmp 29.0G/1004434i workspace 319.0G/45276571i | repeat-01 collected 26/26 workers (60622 items) tests 8470 done 0 failed | 26 in flight, oldest 74s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
......................... [369%]
........................................................................ [372%]
........................................................................ [375%]
...........................................................[contention-diag] +1336s soak 28p/258t rss 11.4G pss 10.5G swap 0.7G majflt 139 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G | host avail 29.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 14.19 | cgroup 11.2G/max oom_kill 0 | free scratch 319.5G/45278824i tmp 29.0G/1004434i workspace 319.5G/45278824i | repeat-01 collected 26/26 workers (60622 items) tests 8693 done 0 failed | 25 in flight, oldest 89s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............. [378%]
........................................................................ [382%]
...............[contention-diag] +1352s soak 29p/226t rss 11.4G pss 10.5G swap 0.7G majflt 224 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 20.91 | cgroup 11.2G/max oom_kill 0 | free scratch 319.6G/45278622i tmp 29.0G/1004435i workspace 319.6G/45278622i | repeat-01 collected 26/26 workers (60622 items) tests 8795 done 0 failed | 26 in flight, oldest 105s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
......................................................... [385%]
........................................................................ [388%]
......................................................[contention-diag] +1367s soak 28p/225t rss 11.4G pss 10.5G swap 0.7G majflt 225 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G | host avail 28.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.34 cpu 24.58 | cgroup 11.2G/max oom_kill 0 | free scratch 319.6G/45278156i tmp 29.0G/1004435i workspace 319.6G/45278156i | scratch used 0.7G in 137813 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 8953 done 0 failed | 26 in flight, oldest 120s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............[contention-diag] +1384s soak 28p/257t rss 11.5G pss 10.5G swap 0.7G majflt 225 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G | host avail 25.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.43 cpu 21.3 | cgroup 11.3G/max oom_kill 0 | free scratch 319.5G/45277971i tmp 29.0G/1004435i workspace 319.5G/45277971i | repeat-01 collected 26/26 workers (60622 items) tests 8995 done 0 failed | 26 in flight, oldest 137s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..... [391%]
........................................................................ [394%]
................................................................[contention-diag] +1399s soak 28p/260t rss 11.5G pss 10.5G swap 0.7G majflt 225 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G | host avail 26.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.99 cpu 19.6 | cgroup 11.3G/max oom_kill 0 | free scratch 319.2G/45277561i tmp 29.0G/1004435i workspace 319.2G/45277561i | repeat-01 collected 26/26 workers (60622 items) tests 9134 done 0 failed | 26 in flight, oldest 152s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........ [397%]
.......................[contention-diag] +1415s soak 29p/256t rss 11.6G pss 10.7G swap 0.7G majflt 229 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.4G, 1 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.48 cpu 22.14 | cgroup 11.4G/max oom_kill 0 | free scratch 319.1G/45277339i tmp 29.0G/1004435i workspace 319.1G/45277339i | repeat-01 collected 26/26 workers (60622 items) tests 9166 done 0 failed | 26 in flight, oldest 168s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................................. [400%]
...............[contention-diag] +1430s soak 29p/253t rss 11.6G pss 10.6G swap 0.7G majflt 229 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 31.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.75 cpu 30.76 | cgroup 11.4G/max oom_kill 0 | free scratch 319.1G/45276926i tmp 29.0G/1006682i workspace 319.1G/45276926i | repeat-01 collected 26/26 workers (60622 items) tests 9228 done 0 failed | 26 in flight, oldest 86s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..............................[contention-diag] +1445s soak 28p/233t rss 11.6G pss 10.6G swap 0.7G majflt 229 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.4G | host avail 31.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.35 cpu 27.22 | cgroup 11.5G/max oom_kill 0 | free scratch 319.1G/45276749i tmp 29.0G/1006682i workspace 319.1G/45276749i | repeat-01 collected 26/26 workers (60622 items) tests 9260 done 0 failed | 26 in flight, oldest 102s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................[contention-diag] +1461s soak 28p/247t rss 11.6G pss 10.6G swap 0.7G majflt 229 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G | host avail 29.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.46 cpu 23.85 | cgroup 11.5G/max oom_kill 0 | free scratch 319.1G/45276628i tmp 29.0G/1006682i workspace 319.1G/45276628i | repeat-01 collected 26/26 workers (60622 items) tests 9278 done 0 failed | 26 in flight, oldest 117s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.......... [404%]
...............................................................[contention-diag] +1476s soak 29p/251t rss 11.6G pss 10.7G swap 0.7G majflt 233 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.38 cpu 26.19 | cgroup 11.5G/max oom_kill 0 | free scratch 319.1G/45276335i tmp 29.0G/1006682i workspace 319.1G/45276335i | repeat-01 collected 26/26 workers (60622 items) tests 9350 done 0 failed | 26 in flight, oldest 132s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
......... [407%]
......................................................................[contention-diag] +1491s soak 28p/246t rss 11.6G pss 10.7G swap 0.7G majflt 233 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G | host avail 31.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.49 cpu 31.57 | cgroup 11.5G/max oom_kill 0 | free scratch 319.1G/45276134i tmp 29.0G/1006682i workspace 319.1G/45276134i | scratch used 0.8G in 144485 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 9396 done 0 failed | 26 in flight, oldest 148s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.. [410%]
....................................................................[contention-diag] +1508s soak 29p/247t rss 11.6G pss 10.7G swap 0.7G majflt 238 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.61 cpu 28.12 | cgroup 11.6G/max oom_kill 0 | free scratch 319.1G/45275752i tmp 29.0G/1006682i workspace 319.1G/45275752i | repeat-01 collected 26/26 workers (60622 items) tests 9498 done 0 failed | 26 in flight, oldest 165s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.... [413%]
........................................................................ [416%]
..............................................................[contention-diag] +1524s soak 30p/239t rss 11.8G pss 10.8G swap 0.7G majflt 254 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G, 2 descendant rss 0.2G pss 0.1G | host avail 29.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.3 cpu 27.76 | cgroup 11.7G/max oom_kill 0 | free scratch 319.1G/45275351i tmp 29.0G/1006682i workspace 319.1G/45275351i | repeat-01 collected 26/26 workers (60622 items) tests 9637 done 0 failed | 26 in flight, oldest 67s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......... [419%]
........................................................................ [422%]
...........................................[contention-diag] +1539s soak 28p/238t rss 11.6G pss 10.7G swap 0.6G majflt 254 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.5G | host avail 33.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.83/0.83 io 5.18 cpu 27.49 | cgroup 11.6G/max oom_kill 0 | free scratch 319.1G/45275039i tmp 29.0G/1006682i workspace 319.1G/45275039i | repeat-01 collected 26/26 workers (60622 items) tests 9762 done 0 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............[contention-diag] +1554s soak 28p/255t rss 11.7G pss 10.7G swap 0.6G majflt 256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.5G | host avail 32.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 4.96 cpu 27.28 | cgroup 11.6G/max oom_kill 0 | free scratch 319.1G/45274878i tmp 29.0G/1006681i workspace 319.1G/45274878i | repeat-01 collected 26/26 workers (60622 items) tests 9774 done 0 failed | 26 in flight, oldest 98s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................. [425%]
....................................................[contention-diag] +1570s soak 29p/240t rss 11.7G pss 10.8G swap 0.6G majflt 256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 33.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 5.05 cpu 28.07 | cgroup 11.6G/max oom_kill 0 | free scratch 319.1G/45274599i tmp 29.0G/1006681i workspace 319.1G/45274599i | repeat-01 collected 26/26 workers (60622 items) tests 9842 done 0 failed | 26 in flight, oldest 113s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................... [429%]
........................................................................ [432%]
...............................[contention-diag] +1585s soak 28p/229t rss 11.7G pss 10.8G swap 0.6G majflt 257 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 30.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.7 cpu 22.6 | cgroup 11.7G/max oom_kill 0 | free scratch 323.5G/45275400i tmp 29.0G/1006681i workspace 323.5G/45275400i | repeat-01 collected 26/26 workers (60622 items) tests 9965 done 0 failed | 26 in flight, oldest 128s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................................... [435%]
.................................................................[contention-diag] +1600s soak 28p/228t rss 11.7G pss 10.8G swap 0.6G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G | host avail 28.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.86 cpu 18.54 | cgroup 11.7G/max oom_kill 0 | free scratch 323.5G/45275011i tmp 29.0G/1006681i workspace 323.5G/45275011i | repeat-01 collected 26/26 workers (60622 items) tests 10072 done 0 failed | 26 in flight, oldest 144s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....... [438%]
...............................................................[contention-diag] +1616s soak 29p/248t rss 11.7G pss 10.8G swap 0.6G majflt 266 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.92 cpu 23.87 | cgroup 11.7G/max oom_kill 0 | free scratch 323.5G/45274786i tmp 29.0G/1006681i workspace 323.5G/45274786i | scratch used 0.8G in 151737 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 10133 done 0 failed | 26 in flight, oldest 159s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......... [441%]
..................................[contention-diag] +1633s soak 29p/253t rss 11.8G pss 10.8G swap 0.6G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 28.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.63 cpu 25.21 | cgroup 11.8G/max oom_kill 0 | free scratch 323.5G/45274530i tmp 29.0G/1006681i workspace 323.5G/45274530i | repeat-01 collected 26/26 workers (60622 items) tests 10186 done 0 failed | 26 in flight, oldest 176s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..........[contention-diag] +1648s soak 28p/268t rss 11.8G pss 10.8G swap 0.6G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G | host avail 26.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.53 cpu 24.85 | cgroup 11.8G/max oom_kill 0 | free scratch 323.5G/45274419i tmp 29.0G/1006681i workspace 323.5G/45274419i | repeat-01 collected 26/26 workers (60622 items) tests 10194 done 0 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................ [444%]
........................................................[contention-diag] +1664s soak 30p/279t rss 11.8G pss 10.9G swap 0.6G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 2 descendant rss 0.1G pss 0.1G | host avail 24.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.77 cpu 22.13 | cgroup 11.8G/max oom_kill 0 | free scratch 323.5G/45274119i tmp 29.0G/1006681i workspace 323.5G/45274119i | repeat-01 collected 26/26 workers (60622 items) tests 10277 done 0 failed | 25 in flight, oldest 207s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [447%]
........................................................................ [450%]
..................................................[contention-diag] +1679s soak 28p/235t rss 11.8G pss 10.9G swap 0.6G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G | host avail 25.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.5 cpu 20.04 | cgroup 11.8G/max oom_kill 0 | free scratch 323.2G/45273658i tmp 29.0G/1006681i workspace 323.2G/45273658i | repeat-01 collected 26/26 workers (60622 items) tests 10389 done 0 failed | 25 in flight, oldest 222s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................... [454%]
........................................................................ [457%]
...[contention-diag] +1694s soak 29p/246t rss 11.9G pss 10.9G swap 0.6G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.53 cpu 23.08 | cgroup 11.9G/max oom_kill 0 | free scratch 323.2G/45273415i tmp 29.0G/1006681i workspace 323.2G/45273415i | repeat-01 collected 26/26 workers (60622 items) tests 10514 done 0 failed | 26 in flight, oldest 238s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................................... [460%]
....................................................................[contention-diag] +1710s soak 28p/256t rss 11.8G pss 10.9G swap 0.6G majflt 289 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G | host avail 31.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.7 cpu 22.61 | cgroup 11.9G/max oom_kill 0 | free scratch 323.2G/45273039i tmp 29.0G/1006681i workspace 323.2G/45273039i | repeat-01 collected 26/26 workers (60622 items) tests 10646 done 0 failed | 26 in flight, oldest 253s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.... [463%]
.......................................................[contention-diag] +1725s soak 29p/294t rss 11.9G pss 10.9G swap 0.6G majflt 291 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.77 cpu 22.79 | cgroup 11.9G/max oom_kill 0 | free scratch 323.2G/45272723i tmp 29.0G/1006681i workspace 323.2G/45272723i | repeat-01 collected 26/26 workers (60622 items) tests 10707 done 0 failed | 26 in flight, oldest 268s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................. [466%]
........................................................................ [469%]
................................................[contention-diag] +1740s soak 28p/262t rss 11.9G pss 10.9G swap 0.6G majflt 293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.8 cpu 24.14 | cgroup 11.9G/max oom_kill 0 | free scratch 323.2G/45272421i tmp 29.0G/1006681i workspace 323.2G/45272421i | scratch used 0.8G in 157973 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 10828 done 0 failed | 26 in flight, oldest 284s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................ [472%]
..............................................................[contention-diag] +1758s soak 30p/258t rss 11.9G pss 10.9G swap 0.6G majflt 301 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 31.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.49 cpu 25.81 | cgroup 11.9G/max oom_kill 0 | free scratch 323.2G/45272586i tmp 29.0G/1006680i workspace 323.2G/45272586i | repeat-01 collected 26/26 workers (60622 items) tests 10930 done 0 failed | 26 in flight, oldest 301s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......... [476%]
......................................................[contention-diag] +1773s soak 30p/279t rss 11.9G pss 10.9G swap 0.6G majflt 311 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.51 cpu 28.49 | cgroup 12.0G/max oom_kill 0 | free scratch 323.2G/45271756i tmp 29.0G/1006681i workspace 323.2G/45271756i | repeat-01 collected 26/26 workers (60622 items) tests 10998 done 0 failed | 26 in flight, oldest 47s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.................. [479%]
.....................................................[contention-diag] +1788s soak 29p/273t rss 11.9G pss 10.9G swap 0.6G majflt 352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 25.67 | cgroup 12.0G/max oom_kill 0 | free scratch 323.2G/45271427i tmp 29.0G/1006681i workspace 323.2G/45271427i | repeat-01 collected 26/26 workers (60622 items) tests 11068 done 0 failed | 26 in flight, oldest 62s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
...........[contention-diag] +1804s soak 29p/280t rss 11.9G pss 10.9G swap 0.6G majflt 352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 25.92 | cgroup 12.0G/max oom_kill 0 | free scratch 323.2G/45271264i tmp 29.0G/1006681i workspace 323.2G/45271264i | repeat-01 collected 26/26 workers (60622 items) tests 11078 done 0 failed | 26 in flight, oldest 78s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........ [482%]
........................................[contention-diag] +1819s soak 30p/292t rss 11.9G pss 11.0G swap 0.6G majflt 356 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 28.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 29.44 | cgroup 12.0G/max oom_kill 0 | free scratch 323.2G/45271039i tmp 29.0G/1006681i workspace 323.2G/45271039i | repeat-01 collected 26/26 workers (60622 items) tests 11124 done 0 failed | 26 in flight, oldest 93s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
................................ [485%]
........................................................................ [488%]
...............................................................[contention-diag] +1834s soak 30p/275t rss 12.0G pss 11.0G swap 0.6G majflt 356 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 27.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.79 | cgroup 12.1G/max oom_kill 0 | free scratch 323.1G/45270610i tmp 29.0G/1006681i workspace 323.1G/45270610i | repeat-01 collected 26/26 workers (60622 items) tests 11287 done 0 failed | 26 in flight, oldest 54s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
......... [491%]
........................................................................ [494%]
........................................................................ [497%]
...[contention-diag] +1850s soak 29p/250t rss 12.0G pss 11.0G swap 0.6G majflt 359 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 1.17/0.39 io 0.0 cpu 23.04 | cgroup 12.1G/max oom_kill 0 | free scratch 323.0G/45269926i tmp 29.0G/1006680i workspace 323.0G/45269926i | repeat-01 collected 26/26 workers (60622 items) tests 11440 done 0 failed | 25 in flight, oldest 69s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
..................................................................... [501%]
.................................................[contention-diag] +1865s soak 30p/249t rss 12.0G pss 11.0G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 29.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.63/0.47 io 0.0 cpu 21.39 | cgroup 12.1G/max oom_kill 0 | free scratch 322.4G/45269520i tmp 29.0G/1006681i workspace 322.4G/45269520i | scratch used 0.9G in 163882 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 11564 done 0 failed | 26 in flight, oldest 48s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
..................[contention-diag] +1882s soak 32p/270t rss 12.0G pss 11.0G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.12/0.09 io 0.04 cpu 27.15 | cgroup 12.2G/max oom_kill 0 | free scratch 322.4G/45267191i tmp 29.0G/1006681i workspace 322.4G/45267191i | repeat-01 collected 26/26 workers (60622 items) tests 11586 done 0 failed | 26 in flight, oldest 51s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_escape_cancels_without_moving
..... [504%]
........................................................................ [507%]
...............................................[contention-diag] +1898s soak 30p/271t rss 12.0G pss 11.1G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 0.0 cpu 28.56 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45248787i tmp 29.0G/1006681i workspace 322.3G/45248787i | repeat-01 collected 26/26 workers (60622 items) tests 11708 done 0 failed | 26 in flight, oldest 62s gw23 tests/ace/tui/test_feature_flags_pane_journeys.py::test_flags_pane_enable_and_disable_write_state_and_request_restart
.......................[contention-diag] +1913s soak 29p/262t rss 12.0G pss 11.0G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.33 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45248338i tmp 29.0G/1006681i workspace 322.3G/45248338i | repeat-01 collected 26/26 workers (60622 items) tests 11733 done 0 failed | 26 in flight, oldest 59s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
.. [510%]
.............................[contention-diag] +1928s soak 30p/276t rss 12.1G pss 11.1G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 30.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.92 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45248227i tmp 29.0G/1006681i workspace 322.3G/45248227i | repeat-01 collected 26/26 workers (60622 items) tests 11764 done 0 failed | 26 in flight, oldest 75s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
........................................... [513%]
................................[contention-diag] +1944s soak 30p/261t rss 12.1G pss 11.1G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 30.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.64 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45247972i tmp 29.0G/1006681i workspace 322.3G/45247972i | repeat-01 collected 26/26 workers (60622 items) tests 11839 done 0 failed | 26 in flight, oldest 50s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_preserves_collapsed_sections
........................................ [516%]
..........[contention-diag] +1959s soak 30p/255t rss 12.2G pss 11.2G swap 0.6G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.44 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45247751i tmp 29.0G/1006681i workspace 322.3G/45247751i | repeat-01 collected 26/26 workers (60622 items) tests 11880 done 0 failed | 26 in flight, oldest 59s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.............................................................. [519%]
..............................[contention-diag] +1974s soak 31p/247t rss 12.1G pss 11.1G swap 0.6G majflt 362 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 3 descendant rss 0.1G pss 0.0G | host avail 29.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.62 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45247302i tmp 29.0G/1006681i workspace 322.3G/45247302i | repeat-01 collected 26/26 workers (60622 items) tests 11980 done 0 failed | 26 in flight, oldest 74s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.......................................... [523%]
........................................................................ [526%]
.....................................................[contention-diag] +1990s soak 29p/257t rss 12.1G pss 11.1G swap 0.6G majflt 362 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.95 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45247007i tmp 29.0G/1006681i workspace 322.3G/45247007i | scratch used 0.9G in 170614 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 12072 done 0 failed | 26 in flight, oldest 89s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................... [529%]
........................................................................ [532%]
.....................[contention-diag] +2007s soak 29p/252t rss 12.1G pss 11.1G swap 0.6G majflt 364 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 29.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 23.96 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45246188i tmp 29.0G/1006681i workspace 322.3G/45246188i | repeat-01 collected 26/26 workers (60622 items) tests 12257 done 0 failed | 26 in flight, oldest 107s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................................................... [535%]
........................................................................ [538%]
.......................................................[contention-diag] +2022s soak 29p/248t rss 12.1G pss 11.1G swap 0.6G majflt 366 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.43 | cgroup 12.2G/max oom_kill 0 | free scratch 322.3G/45246133i tmp 29.0G/1006681i workspace 322.3G/45246133i | repeat-01 collected 26/26 workers (60622 items) tests 12422 done 0 failed | 26 in flight, oldest 54s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
................. [541%]
........................................................................ [544%]
........................................................................ [548%]
........[contention-diag] +2038s soak 30p/259t rss 12.1G pss 11.1G swap 0.6G majflt 366 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 28.49 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45245607i tmp 29.0G/1006681i workspace 322.3G/45245607i | repeat-01 collected 26/26 workers (60622 items) tests 12600 done 0 failed | 26 in flight, oldest 47s gw8 tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_header_age_label_prefers_checked_at
................................................................ [551%]
........................................................................ [554%]
........................................................................ [557%]
........................[contention-diag] +2053s soak 31p/256t rss 12.1G pss 11.2G swap 0.6G majflt 382 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 34.69 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45244983i tmp 29.0G/1006681i workspace 322.3G/45244983i | repeat-01 collected 26/26 workers (60622 items) tests 12837 done 0 failed | 26 in flight, oldest 57s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
................................................ [560%]
.................................[contention-diag] +2068s soak 28p/260t rss 12.1G pss 11.2G swap 0.6G majflt 382 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 35.93 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45244739i tmp 29.0G/1006681i workspace 322.3G/45244739i | repeat-01 collected 26/26 workers (60622 items) tests 12918 done 0 failed | 26 in flight, oldest 72s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
....................................... [563%]
....................................................................[contention-diag] +2084s soak 32p/280t rss 12.2G pss 11.2G swap 0.6G majflt 382 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 4 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.98 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45244320i tmp 29.0G/1006681i workspace 322.3G/45244320i | repeat-01 collected 26/26 workers (60622 items) tests 13018 done 0 failed | 26 in flight, oldest 55s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
.... [566%]
........................................................................ [569%]
........................................................................ [573%]
..............................................................[contention-diag] +2099s soak 30p/256t rss 12.2G pss 11.2G swap 0.6G majflt 387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.07 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45243690i tmp 29.0G/1006681i workspace 322.3G/45243690i | repeat-01 collected 26/26 workers (60622 items) tests 13234 done 0 failed | 26 in flight, oldest 60s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.......... [576%]
........................................................................ [579%]
..................................................[contention-diag] +2114s soak 30p/250t rss 12.2G pss 11.2G swap 0.6G majflt 387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.42 | cgroup 12.3G/max oom_kill 0 | free scratch 322.3G/45243241i tmp 29.0G/1006681i workspace 322.3G/45243241i | scratch used 1.0G in 185517 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 13324 done 0 failed | 26 in flight, oldest 75s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
...................... [582%]
........................................................................ [585%]
.................................[contention-diag] +2131s soak 32p/242t rss 12.2G pss 11.2G swap 0.6G majflt 388 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 4 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 28.2 | cgroup 12.4G/max oom_kill 0 | free scratch 322.3G/45242334i tmp 29.0G/1006681i workspace 322.3G/45242335i | repeat-01 collected 26/26 workers (60622 items) tests 13490 done 0 failed | 26 in flight, oldest 44s gw23 tests/ace/tui/test_link_follow_planner.py::test_kind_mismatch_stays_pending_until_query_worker_settles
....................................... [588%]
.........[contention-diag] +2147s soak 31p/274t rss 12.3G pss 11.3G swap 0.6G majflt 441 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 3 descendant rss 0.1G pss 0.1G | host avail 31.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 29.7 | cgroup 12.4G/max oom_kill 0 | free scratch 322.3G/45242538i tmp 29.0G/1006680i workspace 322.3G/45242538i | repeat-01 collected 26/26 workers (60622 items) tests 13541 done 0 failed | 26 in flight, oldest 60s gw23 tests/ace/tui/test_link_follow_planner.py::test_kind_mismatch_stays_pending_until_query_worker_settles
............................................................... [591%]
.................................................[contention-diag] +2162s soak 35p/285t rss 12.3G pss 11.3G swap 0.6G majflt 396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 7 descendant rss 0.1G pss 0.1G | host avail 32.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.84 | cgroup 12.4G/max oom_kill 0 | free scratch 322.3G/45242122i tmp 29.0G/1006680i workspace 322.3G/45242122i | repeat-01 collected 26/26 workers (60622 items) tests 13644 done 0 failed | 26 in flight, oldest 63s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
....................... [595%]
........................................................................ [598%]
................................................................[contention-diag] +2177s soak 31p/280t rss 12.2G pss 11.2G swap 0.6G majflt 396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 1.25/1.25 io 0.0 cpu 20.52 | cgroup 12.5G/max oom_kill 0 | free scratch 322.3G/45241438i tmp 29.0G/1006680i workspace 322.3G/45241438i | repeat-01 collected 26/26 workers (60622 items) tests 13813 done 0 failed | 26 in flight, oldest 78s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
........ [601%]
......................................[contention-diag] +2193s soak 30p/267t rss 12.3G pss 11.3G swap 0.6G majflt 396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.25/0.25 io 0.0 cpu 22.27 | cgroup 12.7G/max oom_kill 0 | free scratch 322.3G/45241184i tmp 29.0G/1006680i workspace 322.3G/45241184i | repeat-01 collected 26/26 workers (60622 items) tests 13860 done 0 failed | 26 in flight, oldest 77s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.................................. [604%]
...........................................................[contention-diag] +2208s soak 31p/269t rss 12.3G pss 11.3G swap 0.6G majflt 400 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 3 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.09 cpu 25.53 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45240842i tmp 29.0G/1006680i workspace 322.3G/45240842i | repeat-01 collected 26/26 workers (60622 items) tests 13953 done 0 failed | 26 in flight, oldest 92s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............. [607%]
........................................................................ [610%]
...........[contention-diag] +2223s soak 30p/247t rss 12.3G pss 11.3G swap 0.6G majflt 400 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 2 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.02 cpu 22.18 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45240323i tmp 29.0G/1006680i workspace 322.3G/45240323i | repeat-01 collected 26/26 workers (60622 items) tests 14041 done 0 failed | 26 in flight, oldest 108s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................................................. [613%]
.....................................................................[contention-diag] +2239s soak 29p/266t rss 12.3G pss 11.3G swap 0.6G majflt 401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.84 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45239813i tmp 29.0G/1006680i workspace 322.3G/45239813i | scratch used 1.0G in 191303 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 14175 done 0 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/test_macro_browser_filter.py::test_cached_reactivation_restores_open_filter_or_list
... [616%]
........................................................................ [620%]
........[contention-diag] +2256s soak 28p/277t rss 12.3G pss 11.3G swap 0.6G majflt 401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.93 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45239503i tmp 29.0G/1006680i workspace 322.3G/45239503i | repeat-01 collected 26/26 workers (60622 items) tests 14260 done 0 failed | 26 in flight, oldest 71s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
................................................................ [623%]
......................................[contention-diag] +2271s soak 31p/256t rss 12.4G pss 11.4G swap 0.6G majflt 401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 3 descendant rss 0.0G pss 0.0G | host avail 32.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.78 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45239104i tmp 29.0G/1006680i workspace 322.3G/45239104i | repeat-01 collected 26/26 workers (60622 items) tests 14358 done 0 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
.................................. [626%]
........................................................................ [629%]
........................................................................ [632%]
..........................[contention-diag] +2287s soak 32p/252t rss 12.4G pss 11.4G swap 0.6G majflt 406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 4 descendant rss 0.0G pss 0.0G | host avail 31.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.96 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45238219i tmp 29.0G/1006680i workspace 322.3G/45238219i | repeat-01 collected 26/26 workers (60622 items) tests 14567 done 0 failed | 26 in flight, oldest 52s gw22 tests/ace/tui/test_statistics_footprint.py::test_footprint_keep_reason_is_recorded_by_a_worker
.............................................. [635%]
.........................................[contention-diag] +2302s soak 35p/280t rss 12.4G pss 11.4G swap 0.6G majflt 410 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 7 descendant rss 0.0G pss 0.0G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.91 | cgroup 12.6G/max oom_kill 0 | free scratch 322.3G/45237751i tmp 29.0G/1006680i workspace 322.3G/45237751i | repeat-01 collected 26/26 workers (60622 items) tests 14656 done 0 failed | 26 in flight, oldest 61s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_filter_types_brackets_and_tab_switches_main_tab
............................... [638%]
........................................................................ [642%]
........................................................................ [645%]
..[contention-diag] +2317s soak 31p/273t rss 12.4G pss 11.4G swap 0.6G majflt 415 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 30.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 21.84 | cgroup 12.7G/max oom_kill 0 | free scratch 322.3G/45237322i tmp 29.0G/1006680i workspace 322.3G/45237322i | repeat-01 collected 26/26 workers (60622 items) tests 14828 done 0 failed | 25 in flight, oldest 52s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
...................................................................... [648%]
................................................[contention-diag] +2333s soak 31p/257t rss 12.4G pss 11.4G swap 0.6G majflt 416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 3 descendant rss 0.0G pss 0.0G | host avail 31.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.77 cpu 24.71 | cgroup 12.7G/max oom_kill 0 | free scratch 322.3G/45236368i tmp 29.0G/1006680i workspace 322.3G/45236368i | repeat-01 collected 26/26 workers (60622 items) tests 14949 done 0 failed | 26 in flight, oldest 67s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
........................ [651%]
........................................................................ [654%]
........................................................................ [657%]
..[contention-diag] +2348s soak 32p/244t rss 12.5G pss 11.5G swap 0.6G majflt 416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 4 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 27.49 | cgroup 12.7G/max oom_kill 0 | free scratch 322.3G/45235294i tmp 29.0G/1006680i workspace 322.3G/45235294i | repeat-01 collected 26/26 workers (60622 items) tests 15115 done 0 failed | 26 in flight, oldest 69s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
...................................................................... [660%]
........................................................................ [663%]
........................................................................ [667%]
.................[contention-diag] +2363s soak 30p/258t rss 12.5G pss 11.5G swap 0.6G majflt 418 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.3G, 2 descendant rss 0.0G pss 0.0G | host avail 31.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.97 cpu 31.36 | cgroup 12.8G/max oom_kill 0 | free scratch 322.3G/45234154i tmp 29.0G/1006680i workspace 322.3G/45234154i | scratch used 1.0G in 196266 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 15318 done 0 failed | 26 in flight, oldest 53s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
....................................................... [670%]
........................................................................ [673%]
................................................[contention-diag] +2381s soak 32p/271t rss 12.5G pss 11.5G swap 0.6G majflt 418 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 4 descendant rss 0.0G pss 0.0G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 27.34 | cgroup 12.8G/max oom_kill 0 | free scratch 322.3G/45232874i tmp 29.0G/1006680i workspace 322.3G/45232874i | repeat-01 collected 26/26 workers (60622 items) tests 15522 done 0 failed | 26 in flight, oldest 70s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................ [676%]
........................................................................ [679%]
........................................................................ [682%]
........................................................................ [685%]
........................[contention-diag] +2396s soak 34p/281t rss 12.7G pss 11.7G swap 0.6G majflt 419 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 6 descendant rss 0.2G pss 0.2G | host avail 31.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 31.21 | cgroup 12.9G/max oom_kill 0 | free scratch 322.3G/45232375i tmp 29.0G/1006680i workspace 322.3G/45232375i | repeat-01 collected 26/26 workers (60622 items) tests 15767 done 0 failed | 26 in flight, oldest 86s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................ [688%]
........................................................................ [692%]
.........................[contention-diag] +2411s soak 34p/250t rss 12.8G pss 11.7G swap 0.6G majflt 422 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 6 descendant rss 0.2G pss 0.1G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 29.67 | cgroup 12.9G/max oom_kill 0 | free scratch 322.2G/45231311i tmp 29.0G/1006680i workspace 322.2G/45231311i | repeat-01 collected 26/26 workers (60622 items) tests 15928 done 0 failed | 26 in flight, oldest 101s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............................................... [695%]
........................................................................ [698%]
........................[contention-diag] +2427s soak 34p/255t rss 12.8G pss 11.8G swap 0.6G majflt 422 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 6 descendant rss 0.3G pss 0.2G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 28.51 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45230736i tmp 29.0G/1006680i workspace 322.2G/45230736i | repeat-01 collected 26/26 workers (60622 items) tests 16063 done 0 failed | 26 in flight, oldest 116s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................ [701%]
........................................................................ [704%]
........................................................................ [707%]
........................................................................ [710%]
........................................................[contention-diag] +2442s soak 31p/244t rss 12.7G pss 11.6G swap 0.6G majflt 422 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 3 descendant rss 0.1G pss 0.1G | host avail 30.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 26.12 | cgroup 12.9G/max oom_kill 0 | free scratch 322.2G/45229711i tmp 29.0G/1006680i workspace 322.2G/45229710i | repeat-01 collected 26/26 workers (60622 items) tests 16391 done 0 failed | 26 in flight, oldest 132s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................ [714%]
........................................................................ [717%]
........................................................................ [720%]
........................................................................ [723%]
........................................................................ [726%]
......................................[contention-diag] +2457s soak 30p/243t rss 12.6G pss 11.6G swap 0.6G majflt 427 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.4G, 2 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 21.98 | cgroup 12.9G/max oom_kill 0 | free scratch 322.2G/45228750i tmp 29.0G/1006680i workspace 322.2G/45228750i | repeat-01 collected 26/26 workers (60622 items) tests 16740 done 0 failed | 26 in flight, oldest 147s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................. [729%]
........................................................................ [732%]
........................................................................ [735%]
.............................................[contention-diag] +2473s soak 34p/274t rss 12.7G pss 11.6G swap 0.6G majflt 430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 6 descendant rss 0.1G pss 0.0G | host avail 30.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.2 cpu 29.29 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45227353i tmp 29.0G/1006680i workspace 322.2G/45227353i | repeat-01 collected 26/26 workers (60622 items) tests 16963 done 0 failed | 26 in flight, oldest 162s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................... [739%]
........................................................................ [742%]
..................................[contention-diag] +2488s soak 34p/297t rss 12.7G pss 11.7G swap 0.6G majflt 430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 6 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 28.0 | cgroup 13.1G/max oom_kill 0 | free scratch 322.2G/45229462i tmp 29.0G/1006680i workspace 322.2G/45229462i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 17090 done 0 failed | 26 in flight, oldest 124s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
...................................... [745%]
........................................................................ [748%]
.......................[contention-diag] +2505s soak 32p/251t rss 12.7G pss 11.6G swap 0.6G majflt 430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 4 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.12 | cgroup 13.2G/max oom_kill 0 | free scratch 322.2G/45229258i tmp 29.0G/1006680i workspace 322.2G/45229258i | repeat-01 collected 26/26 workers (60622 items) tests 17205 done 0 failed | 26 in flight, oldest 74s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cancel_saves_once_submit_path_quiet
...............................F[contention-failure] call tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds: footprint_home = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw21/test_bump_microbench_stays_wit0')

    def test_bump_microbench_stays_within_two_microseconds(
        footprint_home: Path,
    ) -> None:
        # The Full CI 3.12 leg runs tests under branch coverage. Measure in a child
        # interpreter without coverage's subprocess hooks so the 2 µs contract
        # remains about the product's event-loop path, not Python tracing.
        child_env = os.environ.copy()
        for name in tuple(child_env):
            if name.startswith(("COV_CORE_", "COVERAGE_")):
                child_env.pop(name)
        child_env["SASE_FOOTPRINT"] = "test"
        script = """
    import json
    import sys
    import time
    
    if sys.gettrace() is not None:
        raise RuntimeError("coverage tracing is active in the benchmark child")
    
    from sase.footprint import _tui
    
    feature = "tui:app.dismiss_toasts"
    for _ in range(200):
        _tui.bump(feature, "key")
    iterations = 5000
    samples = []
    for _ in range(5):
        start = time.perf_counter()
        for _ in range(iterations):
            _tui.bump(feature, "key")
        samples.append((time.perf_counter() - start) / iterations)
    print(json.dumps({"best": min(samples)}))
    """
        result = subprocess.run(
            [sys.executable, "-c", script],
            capture_output=True,
            check=False,
            env=child_env,
            text=True,
            timeout=30,
        )
        assert result.returncode == 0, result.stderr
        best = float(json.loads(result.stdout)["best"])
>       assert best <= 2e-6, f"best bump cost {best * 1e6:.3f} µs"
E       AssertionError: best bump cost 3.402 µs
E       assert 3.4024613996734842e-06 <= 2e-06

tests/footprint/test_tui.py:190: AssertionError
................. [751%]
........................................................................ [754%]
........................................................................ [757%]
..[contention-diag] +2520s soak 31p/240t rss 12.7G pss 11.7G swap 0.6G majflt 431 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 3 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.68 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45228680i tmp 29.0G/1006680i workspace 322.2G/45228680i | repeat-01 collected 26/26 workers (60622 items) tests 17417 done 1 failed | 24 in flight, oldest 50s gw16 tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_not_installed_toasts
...................................................................... [761%]
........................................................................ [764%]
..............................................[contention-diag] +2536s soak 30p/242t rss 12.7G pss 11.7G swap 0.6G majflt 431 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 2 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.18 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45228213i tmp 29.0G/1006680i workspace 322.2G/45228213i | repeat-01 collected 26/26 workers (60622 items) tests 17607 done 1 failed | 26 in flight, oldest 48s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_manual_update_drops_expired_load_freshness
.......................... [767%]
........................................................................ [770%]
........................................................................ [773%]
........................................................................ [776%]
....................................................................[contention-diag] +2551s soak 32p/240t rss 12.7G pss 11.7G swap 0.6G majflt 432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 1.03/1.03 io 0.0 cpu 32.25 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45227437i tmp 29.0G/1006680i workspace 322.2G/45227437i | repeat-01 collected 26/26 workers (60622 items) tests 17907 done 1 failed | 26 in flight, oldest 61s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.... [779%]
........................................................................ [782%]
........................................................................ [786%]
..........................................[contention-diag] +2566s soak 32p/250t rss 12.8G pss 11.7G swap 0.6G majflt 432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 4 descendant rss 0.1G pss 0.1G | host avail 30.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.2/0.2 io 0.0 cpu 36.19 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45227077i tmp 29.0G/1006680i workspace 322.2G/45227077i | repeat-01 collected 26/26 workers (60622 items) tests 18109 done 1 failed | 26 in flight, oldest 76s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.............................. [789%]
........................................................................ [792%]
...........................................................[contention-diag] +2582s soak 35p/228t rss 12.7G pss 11.7G swap 0.6G majflt 432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 7 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.0 cpu 28.22 | cgroup 13.0G/max oom_kill 0 | free scratch 322.2G/45226562i tmp 29.0G/1006680i workspace 322.2G/45226562i | repeat-01 collected 26/26 workers (60622 items) tests 18272 done 1 failed | 26 in flight, oldest 91s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............. [795%]
........................................................................ [798%]
............................................[contention-diag] +2597s soak 33p/224t rss 12.7G pss 11.7G swap 0.6G majflt 433 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 28.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.92 cpu 22.18 | cgroup 13.0G/max oom_kill 0 | free scratch 322.3G/45235746i tmp 29.0G/1006680i workspace 322.3G/45235746i | repeat-01 collected 26/26 workers (60622 items) tests 18387 done 1 failed | 26 in flight, oldest 107s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................ [801%]
........................................................................ [804%]
........................................................................ [808%]
........................................................................ [811%]
........................[contention-diag] +2612s soak 33p/233t rss 12.7G pss 11.7G swap 0.6G majflt 433 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.35 cpu 19.29 | cgroup 13.1G/max oom_kill 0 | free scratch 322.3G/45235160i tmp 29.0G/1006679i workspace 322.3G/45235160i | scratch used 1.1G in 199377 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 18643 done 1 failed | 26 in flight, oldest 45s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_agents_tab
................................................ [814%]
........................................................................ [817%]
........................................................................ [820%]
........................................................................ [823%]
.............................................................[contention-diag] +2630s soak 31p/235t rss 12.8G pss 11.7G swap 0.6G majflt 435 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 3 descendant rss 0.0G pss 0.0G | host avail 28.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.09/0.05 io 2.6 cpu 18.26 | cgroup 13.0G/max oom_kill 0 | free scratch 322.3G/45233947i tmp 29.0G/1006680i workspace 322.3G/45233947i | repeat-01 collected 26/26 workers (60622 items) tests 18989 done 1 failed | 25 in flight, oldest 54s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_offline_reload_does_not_retain_freshness
........... [826%]
........................................................................ [829%]
........................................................................ [833%]
........................................................................ [836%]
......[contention-diag] +2645s soak 32p/228t rss 12.8G pss 11.8G swap 0.6G majflt 437 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 4 descendant rss 0.1G pss 0.0G | host avail 27.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.93 cpu 20.44 | cgroup 13.0G/max oom_kill 0 | free scratch 322.3G/45232807i tmp 29.0G/1006680i workspace 322.3G/45232807i | repeat-01 collected 26/26 workers (60622 items) tests 19225 done 1 failed | 26 in flight, oldest 64s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
.................................................................. [839%]
........................................................................ [842%]
........................................................................ [845%]
...................[contention-diag] +2661s soak 32p/235t rss 12.8G pss 11.8G swap 0.6G majflt 471 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 27.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.37 cpu 24.04 | cgroup 13.1G/max oom_kill 0 | free scratch 322.3G/45232395i tmp 29.0G/1006680i workspace 322.3G/45232395i | repeat-01 collected 26/26 workers (60622 items) tests 19446 done 1 failed | 26 in flight, oldest 79s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
..................................................... [848%]
........................................................................ [851%]
........................................................................ [854%]
........s...............................[contention-diag] +2676s soak 30p/249t rss 12.8G pss 11.8G swap 0.6G majflt 472 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 2 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 24.74 | cgroup 13.2G/max oom_kill 0 | free scratch 322.3G/45231532i tmp 29.0G/1006680i workspace 322.3G/45231532i | repeat-01 collected 26/26 workers (60622 items) tests 19690 done 1 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
................................ [858%]
........................................................................ [861%]
......................................s..s.............................. [864%]
........................................................................ [867%]
.........................[contention-diag] +2691s soak 38p/258t rss 12.9G pss 11.8G swap 0.6G majflt 485 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 10 descendant rss 0.1G pss 0.0G | host avail 30.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 27.85 | cgroup 13.2G/max oom_kill 0 | free scratch 322.3G/45230659i tmp 29.0G/1006680i workspace 322.3G/45230659i | repeat-01 collected 26/26 workers (60622 items) tests 19956 done 1 failed | 25 in flight, oldest 90s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............................................... [870%]
........................................................................ [873%]
........................................................................ [876%]
..............................................................[contention-diag] +2707s soak 34p/271t rss 12.9G pss 11.8G swap 0.6G majflt 492 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 29.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.64 cpu 24.24 | cgroup 13.2G/max oom_kill 0 | free scratch 322.3G/45230370i tmp 29.0G/1006680i workspace 322.3G/45230370i | repeat-01 collected 26/26 workers (60622 items) tests 20214 done 1 failed | 26 in flight, oldest 105s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.......... [880%]
........................................................................ [883%]
........................................................................ [886%]
........................................................................ [889%]
...............[contention-diag] +2722s soak 33p/261t rss 12.9G pss 11.8G swap 0.6G majflt 495 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 5 descendant rss 0.1G pss 0.0G | host avail 30.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.95 cpu 28.41 | cgroup 13.1G/max oom_kill 0 | free scratch 322.3G/45229311i tmp 29.0G/1006680i workspace 322.3G/45229311i | repeat-01 collected 26/26 workers (60622 items) tests 20441 done 1 failed | 25 in flight, oldest 50s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_macro_focus_picker_all_clear_key_and_cancel
......................................................... [892%]
........................................................................ [895%]
........................................................................ [898%]
...............................[contention-diag] +2737s soak 33p/262t rss 12.9G pss 11.8G swap 0.6G majflt 496 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 5 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.57 cpu 27.51 | cgroup 13.2G/max oom_kill 0 | free scratch 322.3G/45229028i tmp 29.0G/1006680i workspace 322.3G/45229028i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 20675 done 1 failed | 26 in flight, oldest 56s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
......................................... [901%]
..........................................................[contention-diag] +2755s soak 34p/272t rss 13.0G pss 11.9G swap 0.6G majflt 500 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 29.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 30.77 | cgroup 13.2G/max oom_kill 0 | free scratch 322.3G/45228768i tmp 29.0G/1006680i workspace 322.3G/45228768i | repeat-01 collected 26/26 workers (60622 items) tests 20787 done 1 failed | 26 in flight, oldest 58s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.............. [905%]
........................................................................ [908%]
........................................................................ [911%]
........................................................................ [914%]
.......[contention-diag] +2770s soak 42p/269t rss 13.1G pss 11.9G swap 0.6G majflt 505 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 14 descendant rss 0.3G pss 0.2G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 31.83 | cgroup 13.3G/max oom_kill 0 | free scratch 322.3G/45227832i tmp 29.0G/1006680i workspace 322.3G/45227832i | repeat-01 collected 26/26 workers (60622 items) tests 21015 done 1 failed | 26 in flight, oldest 74s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
................................................................. [917%]
........................................................................ [920%]
........................................................................ [923%]
........................................................................ [927%]
......................................................[contention-diag] +2785s soak 36p/252t rss 13.1G pss 12.0G swap 0.6G majflt 505 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 8 descendant rss 0.3G pss 0.3G | host avail 32.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 33.6 | cgroup 13.4G/max oom_kill 0 | free scratch 322.3G/45226438i tmp 29.0G/1006680i workspace 322.3G/45226438i | repeat-01 collected 26/26 workers (60622 items) tests 21361 done 1 failed | 26 in flight, oldest 45s gw15 tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
.................. [930%]
................................................................s....... [933%]
..................s..................................................... [936%]
..........................................[contention-diag] +2801s soak 37p/269t rss 13.0G pss 11.9G swap 0.6G majflt 502 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 9 descendant rss 0.2G pss 0.2G | host avail 32.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 30.34 | cgroup 13.3G/max oom_kill 0 | free scratch 322.3G/45225858i tmp 29.0G/1006680i workspace 322.3G/45225858i | repeat-01 collected 26/26 workers (60622 items) tests 21567 done 1 failed | 26 in flight, oldest 50s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
.............................. [939%]
........................................................................ [942%]
........................................................................ [945%]
.................................................[contention-diag] +2816s soak 34p/256t rss 12.9G pss 11.9G swap 0.6G majflt 505 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 32.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 31.05 | cgroup 13.2G/max oom_kill 0 | free scratch 322.3G/45223778i tmp 29.0G/1006680i workspace 322.3G/45223778i | repeat-01 collected 26/26 workers (60622 items) tests 21787 done 1 failed | 26 in flight, oldest 48s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
....................... [948%]
........................................................................ [952%]
........................................................................ [955%]
........................[contention-diag] +2831s soak 37p/241t rss 13.1G pss 12.0G swap 0.6G majflt 509 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 9 descendant rss 0.3G pss 0.2G | host avail 31.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 29.2 | cgroup 13.3G/max oom_kill 0 | free scratch 322.3G/45224571i tmp 29.0G/1006680i workspace 322.3G/45224571i | repeat-01 collected 26/26 workers (60622 items) tests 21980 done 1 failed | 25 in flight, oldest 63s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
................................................ [958%]
........................................................................ [961%]
........................................................................ [964%]
........................................................................ [967%]
..............................................................[contention-diag] +2847s soak 49p/237t rss 13.2G pss 12.0G swap 0.6G majflt 514 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 21 descendant rss 0.3G pss 0.2G | host avail 31.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 31.66 | cgroup 13.4G/max oom_kill 0 | free scratch 322.3G/45223710i tmp 29.0G/1006680i workspace 322.3G/45223710i | repeat-01 collected 26/26 workers (60622 items) tests 22309 done 1 failed | 26 in flight, oldest 79s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.......... [970%]
........................................................................ [973%]
........................................................................ [977%]
........................................................................ [980%]
............................................[contention-diag] +2862s soak 36p/219t rss 13.1G pss 11.9G swap 0.6G majflt 521 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 8 descendant rss 0.2G pss 0.2G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 31.97 | cgroup 13.3G/max oom_kill 0 | free scratch 322.3G/45223372i tmp 29.0G/1006680i workspace 322.3G/45223372i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 22538 done 1 failed | 26 in flight, oldest 94s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............................ [983%]
........................................................................ [986%]
........................................................................ [989%]
........................................................................ [992%]
........................................................................ [995%]
........................................................................ [999%]
.........................................................[contention-diag] +2880s soak 37p/227t rss 13.1G pss 12.0G swap 0.6G majflt 523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 9 descendant rss 0.3G pss 0.2G | host avail 31.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.47/0.47 io 0.76 cpu 28.85 | cgroup 13.4G/max oom_kill 0 | free scratch 322.3G/45222209i tmp 29.0G/1006680i workspace 322.3G/45222209i | repeat-01 collected 26/26 workers (60622 items) tests 22988 done 1 failed | 26 in flight, oldest 111s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............... [1002%]
........................................................................ [1005%]
........................................................................ [1008%]
........................................................................ [1011%]
........................................................................ [1014%]
........................................................................ [1017%]
...............[contention-diag] +2895s soak 33p/186t rss 13.1G pss 12.0G swap 0.6G majflt 523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 5 descendant rss 0.2G pss 0.1G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 0.18 cpu 33.97 | cgroup 13.4G/max oom_kill 0 | free scratch 322.3G/45221249i tmp 29.0G/1006680i workspace 322.3G/45221249i | repeat-01 collected 26/26 workers (60622 items) tests 23409 done 1 failed | 26 in flight, oldest 58s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_refresh_and_hidden_tab_keep_the_active_view_rail
......................................................... [1020%]
........................................................................ [1024%]
........................................................................ [1027%]
........................................................................ [1030%]
........................................................................ [1033%]
........................................................................ [1036%]
...........[contention-diag] +2910s soak 38p/201t rss 13.0G pss 11.9G swap 0.6G majflt 523 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 10 descendant rss 0.1G pss 0.1G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.03 cpu 31.14 | cgroup 13.3G/max oom_kill 0 | free scratch 322.3G/45220199i tmp 29.0G/1006680i workspace 322.3G/45220199i | repeat-01 collected 26/26 workers (60622 items) tests 23826 done 1 failed | 26 in flight, oldest 42s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
............................................................. [1039%]
........................................................................ [1042%]
........................................................................ [1046%]
........................................................................ [1049%]
........................................................................ [1052%]
............................................[contention-diag] +2926s soak 35p/196t rss 13.1G pss 12.0G swap 0.6G majflt 528 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 7 descendant rss 0.2G pss 0.1G | host avail 32.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 26.63 | cgroup 13.4G/max oom_kill 0 | free scratch 322.2G/45219051i tmp 29.0G/1006680i workspace 322.2G/45219051i | repeat-01 collected 26/26 workers (60622 items) tests 24211 done 1 failed | 25 in flight, oldest 57s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
............................ [1055%]
........................................................................ [1058%]
........................................................................ [1061%]
........................................................................ [1064%]
........................................................................ [1067%]
........................................................................ [1071%]
................[contention-diag] +2941s soak 40p/225t rss 13.3G pss 12.2G swap 0.6G majflt 614 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 12 descendant rss 0.3G pss 0.3G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 26.98 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45217792i tmp 29.0G/1006680i workspace 322.2G/45217792i | repeat-01 collected 26/26 workers (60622 items) tests 24639 done 1 failed | 26 in flight, oldest 73s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
........................................................ [1074%]
.............................................................[contention-diag] +2956s soak 37p/198t rss 13.2G pss 12.0G swap 0.6G majflt 533 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 9 descendant rss 0.2G pss 0.2G | host avail 31.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 24.93 | cgroup 13.5G/max oom_kill 0 | free scratch 322.2G/45217020i tmp 29.0G/1006680i workspace 322.2G/45217020i | repeat-01 collected 26/26 workers (60622 items) tests 24757 done 1 failed | 26 in flight, oldest 88s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........... [1077%]
........................................................................ [1080%]
........................................................................ [1083%]
........................................................................ [1086%]
...........[contention-diag] +2972s soak 34p/182t rss 13.1G pss 12.0G swap 0.6G majflt 537 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 31.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 34.14 | cgroup 13.4G/max oom_kill 0 | free scratch 322.2G/45216443i tmp 29.0G/1006680i workspace 322.2G/45216443i | repeat-01 collected 26/26 workers (60622 items) tests 24991 done 1 failed | 26 in flight, oldest 103s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................................. [1089%]
........................................................................ [1092%]
........................................................................ [1096%]
.......................s................................................ [1099%]
........................................................................ [1102%]
...........[contention-diag] +2987s soak 35p/186t rss 13.1G pss 12.0G swap 0.6G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 31.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 36.58 | cgroup 13.4G/max oom_kill 0 | free scratch 322.2G/45215708i tmp 29.0G/1006680i workspace 322.2G/45215708i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 25296 done 1 failed | 25 in flight, oldest 119s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................................. [1105%]
........................................................................ [1108%]
........................................................................ [1111%]
........................................[contention-diag] +3004s soak 31p/186t rss 13.0G pss 11.9G swap 0.6G majflt 538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 3 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 34.15 | cgroup 13.4G/max oom_kill 0 | free scratch 322.2G/45215025i tmp 29.0G/1006680i workspace 322.2G/45215025i | repeat-01 collected 26/26 workers (60622 items) tests 25598 done 1 failed | 26 in flight, oldest 136s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................ [1114%]
........................................................................ [1118%]
........................................................................ [1121%]
...............................................................[contention-diag] +3020s soak 31p/173t rss 13.0G pss 12.0G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 3 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.82 | cgroup 13.5G/max oom_kill 0 | free scratch 322.2G/45214961i tmp 29.0G/1006680i workspace 322.2G/45214961i | repeat-01 collected 26/26 workers (60622 items) tests 25835 done 1 failed | 25 in flight, oldest 151s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
......... [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
............................................................[contention-diag] +3035s soak 33p/180t rss 13.1G pss 12.0G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 5 descendant rss 0.1G pss 0.1G | host avail 30.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 27.67 | cgroup 13.5G/max oom_kill 0 | free scratch 322.2G/45214341i tmp 29.0G/1006680i workspace 322.2G/45214341i | repeat-01 collected 26/26 workers (60622 items) tests 26045 done 1 failed | 25 in flight, oldest 167s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............ [1133%]
........................................................................ [1136%]
........................................................................ [1139%]
.........................................[contention-diag] +3050s soak 35p/173t rss 13.1G pss 12.0G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 30.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 25.9 | cgroup 13.5G/max oom_kill 0 | free scratch 322.2G/45213644i tmp 29.0G/1006680i workspace 322.2G/45213644i | repeat-01 collected 26/26 workers (60622 items) tests 26249 done 1 failed | 25 in flight, oldest 182s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................... [1143%]
........................................................................ [1146%]
..........[contention-diag] +3066s soak 38p/184t rss 13.2G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 10 descendant rss 0.2G pss 0.1G | host avail 30.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.4 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45213367i tmp 29.0G/1006680i workspace 322.2G/45213367i | repeat-01 collected 26/26 workers (60622 items) tests 26357 done 1 failed | 25 in flight, oldest 197s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.............................................................. [1149%]
........................................................................ [1152%]
........................................................................ [1155%]
........................................................................ [1158%]
........................................................................ [1161%]
....................................[contention-diag] +3081s soak 37p/168t rss 13.2G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 9 descendant rss 0.2G pss 0.1G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.35 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45212210i tmp 29.0G/1006677i workspace 322.2G/45212210i | repeat-01 collected 26/26 workers (60622 items) tests 26730 done 1 failed | 25 in flight, oldest 213s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................... [1165%]
........................................................................ [1168%]
........................................................................ [1171%]
..........................................................[contention-diag] +3096s soak 36p/164t rss 13.3G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 8 descendant rss 0.2G pss 0.2G | host avail 30.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.77 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45211775i tmp 29.0G/1006677i workspace 322.2G/45211775i | repeat-01 collected 26/26 workers (60622 items) tests 26978 done 1 failed | 25 in flight, oldest 228s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.............. [1174%]
........................................................................ [1177%]
........................................................................ [1180%]
........................................................................ [1183%]
........................................................................ [1186%]
......................[contention-diag] +3112s soak 35p/172t rss 13.3G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 7 descendant rss 0.2G pss 0.2G | host avail 30.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.41 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45211018i tmp 29.0G/1006677i workspace 322.2G/45211018i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 27295 done 1 failed | 25 in flight, oldest 243s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................................. [1190%]
........................................................................ [1193%]
...........................[contention-diag] +3129s soak 34p/173t rss 13.2G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 39.12 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45210134i tmp 29.0G/1006677i workspace 322.2G/45210134i | repeat-01 collected 26/26 workers (60622 items) tests 27443 done 1 failed | 25 in flight, oldest 139s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................. [1196%]
........................................................................ [1199%]
........................................................................ [1202%]
........................[contention-diag] +3144s soak 35p/170t rss 13.1G pss 12.0G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 7 descendant rss 0.1G pss 0.0G | host avail 30.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 33.39 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45209340i tmp 29.0G/1005265i workspace 322.2G/45209340i | repeat-01 collected 26/26 workers (60622 items) tests 27670 done 1 failed | 24 in flight, oldest 154s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................ [1205%]
........................................................................ [1208%]
........................................................................ [1212%]
........................................................................ [1215%]
........................................................................ [1218%]
........................................................................ [1221%]
........................................................................ [1224%]
..............................................[contention-diag] +3160s soak 34p/188t rss 13.2G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 30.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 32.88 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45208222i tmp 29.0G/1005262i workspace 322.2G/45208222i | repeat-01 collected 26/26 workers (60622 items) tests 28189 done 1 failed | 24 in flight, oldest 169s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.......................... [1227%]
........................................................................ [1230%]
........................................................................ [1233%]
........................................................................ [1237%]
........................................................................ [1240%]
........................................................................ [1243%]
...........................[contention-diag] +3175s soak 33p/174t rss 13.3G pss 12.1G swap 0.6G majflt 544 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 5 descendant rss 0.2G pss 0.1G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 30.53 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45206941i tmp 29.0G/1005262i workspace 322.2G/45206941i | repeat-01 collected 26/26 workers (60622 items) tests 28608 done 1 failed | 25 in flight, oldest 185s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................. [1246%]
........................................................................ [1249%]
........................................................................ [1252%]
..........................[contention-diag] +3190s soak 34p/163t rss 13.2G pss 12.1G swap 0.6G majflt 547 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 6 descendant rss 0.1G pss 0.1G | host avail 28.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.41/0.41 io 0.25 cpu 27.05 | cgroup 13.6G/max oom_kill 0 | free scratch 322.2G/45206165i tmp 29.0G/1005262i workspace 322.2G/45206166i | repeat-01 collected 26/26 workers (60622 items) tests 28809 done 1 failed | 24 in flight, oldest 200s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................................. [1255%]
........................................................................ [1258%]
........................................................................ [1262%]
........................................................................ [1265%]
................................................................[contention-diag] +3206s soak 37p/170t rss 13.3G pss 12.1G swap 0.6G majflt 546 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 9 descendant rss 0.2G pss 0.1G | host avail 30.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.09 cpu 28.4 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45205302i tmp 29.0G/1005262i workspace 322.2G/45205302i | repeat-01 collected 26/26 workers (60622 items) tests 29113 done 1 failed | 25 in flight, oldest 215s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........ [1268%]
........................................................................ [1271%]
........................................................................ [1274%]
........................................................................ [1277%]
........................................................................ [1280%]
[contention-diag] +3221s soak 40p/178t rss 13.3G pss 12.1G swap 0.6G majflt 549 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.7G, 12 descendant rss 0.2G pss 0.1G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.48 cpu 30.62 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45203557i tmp 29.0G/1005262i workspace 322.2G/45203557i | repeat-01 collected 26/26 workers (60622 items) tests 29439 done 1 failed | 24 in flight, oldest 231s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................................ [1284%]
........................................................................ [1287%]
........................................................................ [1290%]
........................................................................ [1293%]
...........[contention-diag] +3236s soak 35p/171t rss 13.3G pss 12.1G swap 0.6G majflt 549 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 7 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 28.69 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45202981i tmp 29.0G/1005262i workspace 322.2G/45202981i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 29707 done 1 failed | 25 in flight, oldest 246s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................. [1296%]
........................................................................ [1299%]
..[contention-diag] +3254s soak 38p/172t rss 13.4G pss 12.2G swap 0.6G majflt 549 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 10 descendant rss 0.2G pss 0.2G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.2 cpu 35.85 | cgroup 13.8G/max oom_kill 0 | free scratch 322.2G/45202906i tmp 29.0G/1005262i workspace 322.2G/45202906i | repeat-01 collected 26/26 workers (60622 items) tests 29869 done 1 failed | 25 in flight, oldest 263s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................................................................... [1302%]
........................................................................ [1305%]
........................................................................ [1309%]
................................................................[contention-diag] +3269s soak 33p/166t rss 13.2G pss 12.1G swap 0.6G majflt 549 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 5 descendant rss 0.1G pss 0.0G | host avail 30.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 35.43 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45202172i tmp 29.0G/1005262i workspace 322.2G/45202172i | repeat-01 collected 26/26 workers (60622 items) tests 30151 done 1 failed | 25 in flight, oldest 279s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........ [1312%]
........................................................................ [1315%]
........................................................................ [1318%]
........................................................................ [1321%]
........................................................................ [1324%]
........................................................................ [1327%]
.......................[contention-diag] +3284s soak 33p/176t rss 13.3G pss 12.2G swap 0.6G majflt 551 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 30.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 33.03 | cgroup 13.8G/max oom_kill 0 | free scratch 322.2G/45200769i tmp 29.0G/1005262i workspace 322.2G/45200769i | repeat-01 collected 26/26 workers (60622 items) tests 30539 done 1 failed | 25 in flight, oldest 294s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................. [1331%]
........................................................................ [1334%]
........................................................................ [1337%]
........................................................................ [1340%]
...............................................[contention-diag] +3300s soak 34p/156t rss 13.3G pss 12.2G swap 0.6G majflt 553 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 6 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.89 cpu 31.57 | cgroup 13.8G/max oom_kill 0 | free scratch 322.2G/45199753i tmp 29.0G/1005262i workspace 322.2G/45199753i | repeat-01 collected 26/26 workers (60622 items) tests 30859 done 1 failed | 25 in flight, oldest 309s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
......................... [1343%]
........................................................................ [1346%]
........................................................................ [1349%]
........................................................................ [1352%]
...................................................[contention-diag] +3315s soak 32p/163t rss 13.3G pss 12.1G swap 0.6G majflt 553 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 29.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.69 cpu 28.35 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45198986i tmp 29.0G/1005262i workspace 322.2G/45198986i | repeat-01 collected 26/26 workers (60622 items) tests 31151 done 1 failed | 25 in flight, oldest 325s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
..................... [1356%]
........................................................................ [1359%]
........................................................................ [1362%]
........................................................................ [1365%]
........................................................................ [1368%]
................................................................[contention-diag] +3330s soak 32p/177t rss 13.3G pss 12.2G swap 0.6G majflt 562 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 28.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.42 cpu 27.7 | cgroup 13.7G/max oom_kill 0 | free scratch 322.2G/45197840i tmp 29.0G/1005262i workspace 322.2G/45197840i | repeat-01 collected 26/26 workers (60622 items) tests 31504 done 1 failed | 24 in flight, oldest 266s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........ [1371%]
........................................................................ [1374%]
........................................................................ [1377%]
........................................................................ [1381%]
........................................................................ [1384%]
........................................................................ [1387%]
........................................................................ [1390%]
..................................................................[contention-diag] +3346s soak 31p/152t rss 13.3G pss 12.2G swap 0.6G majflt 564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 3 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.52 cpu 24.77 | cgroup 13.8G/max oom_kill 0 | free scratch 322.2G/45197182i tmp 29.0G/1005262i workspace 322.2G/45197181i | repeat-01 collected 26/26 workers (60622 items) tests 31973 done 1 failed | 24 in flight, oldest 281s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
...... [1393%]
........................................................................ [1396%]
........................................................................ [1399%]
........................................................................ [1403%]
........................................................................ [1406%]
........................................................................ [1409%]
........................................................................ [1412%]
.............[contention-diag] +3361s soak 31p/165t rss 13.2G pss 12.1G swap 0.6G majflt 566 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 3 descendant rss 0.0G pss 0.0G | host avail 27.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 26.13 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45196186i tmp 29.0G/1005262i workspace 322.1G/45196186i | scratch used 1.0G in 195461 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 32435 done 1 failed | 24 in flight, oldest 296s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................................................... [1415%]
........................................................................ [1418%]
........................................................................ [1421%]
........................................................................ [1424%]
........................................................................ [1428%]
........................[contention-diag] +3378s soak 34p/169t rss 13.4G pss 12.2G swap 0.6G majflt 569 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 6 descendant rss 0.2G pss 0.1G | host avail 27.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 25.34 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45195250i tmp 29.0G/1005262i workspace 322.1G/45195250i | repeat-01 collected 26/26 workers (60622 items) tests 32831 done 1 failed | 24 in flight, oldest 314s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................................................ [1431%]
........................................................................ [1434%]
........................................................................ [1437%]
...............................................................[contention-diag] +3394s soak 33p/175t rss 13.4G pss 12.3G swap 0.6G majflt 571 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 26.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 30.88 | cgroup 13.9G/max oom_kill 0 | free scratch 322.1G/45194431i tmp 29.0G/1005262i workspace 322.1G/45194431i | repeat-01 collected 26/26 workers (60622 items) tests 33091 done 1 failed | 24 in flight, oldest 329s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
......... [1440%]
........................................................................ [1443%]
........................................................................ [1446%]
........................................................................ [1450%]
........................................................................ [1453%]
.................[contention-diag] +3409s soak 37p/177t rss 13.5G pss 12.2G swap 0.6G majflt 655 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 9 descendant rss 0.2G pss 0.1G | host avail 31.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.85 cpu 30.09 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45193175i tmp 29.0G/1005262i workspace 322.1G/45193175i | repeat-01 collected 26/26 workers (60622 items) tests 33419 done 1 failed | 24 in flight, oldest 344s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
....................................................... [1456%]
........................................................................ [1459%]
..................................................................[contention-diag] +3424s soak 36p/181t rss 13.5G pss 12.3G swap 0.6G majflt 655 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.8G, 8 descendant rss 0.3G pss 0.2G | host avail 30.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.36 cpu 27.38 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45192126i tmp 29.0G/1005262i workspace 322.1G/45192126i | repeat-01 collected 26/26 workers (60622 items) tests 33609 done 1 failed | 24 in flight, oldest 360s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
...... [1462%]
........................................................................ [1465%]
........................................................................ [1468%]
........................................................................ [1471%]
........................................................................ [1475%]
........................................................................ [1478%]
...................................................................[contention-diag] +3440s soak 36p/167t rss 13.5G pss 12.3G swap 0.6G majflt 655 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 8 descendant rss 0.3G pss 0.2G | host avail 28.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 25.28 | cgroup 14.1G/max oom_kill 0 | free scratch 322.1G/45191176i tmp 29.0G/1005262i workspace 322.1G/45191176i | repeat-01 collected 26/26 workers (60622 items) tests 34042 done 1 failed | 24 in flight, oldest 375s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
..... [1481%]
........................................................................ [1484%]
........................................................[contention-diag] +3455s soak 35p/163t rss 13.6G pss 12.4G swap 0.6G majflt 656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.8G, 7 descendant rss 0.3G pss 0.2G | host avail 28.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.42 cpu 23.62 | cgroup 14.1G/max oom_kill 0 | free scratch 322.1G/45190677i tmp 29.0G/1005262i workspace 322.1G/45190677i | repeat-01 collected 26/26 workers (60622 items) tests 34176 done 1 failed | 24 in flight, oldest 391s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................ [1487%]
........................................................................ [1490%]
........................................................................ [1493%]
.............................................[contention-diag] +3470s soak 38p/174t rss 13.7G pss 12.5G swap 0.6G majflt 656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 10 descendant rss 0.4G pss 0.3G | host avail 27.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 26.05 | cgroup 14.2G/max oom_kill 0 | free scratch 322.1G/45190279i tmp 29.0G/1005262i workspace 322.1G/45190279i | repeat-01 collected 26/26 workers (60622 items) tests 34389 done 1 failed | 24 in flight, oldest 406s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................... [1496%]
........................................................................ [1500%]
.....................................................................s.. [1503%]
........................................................................ [1506%]
........................................................................ [1509%]
.......................[contention-diag] +3486s soak 36p/167t rss 13.5G pss 12.4G swap 0.6G majflt 656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 8 descendant rss 0.2G pss 0.2G | host avail 26.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 29.48 | cgroup 14.2G/max oom_kill 0 | free scratch 322.1G/45189627i tmp 29.0G/1005262i workspace 322.1G/45189627i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 34689 done 1 failed | 24 in flight, oldest 421s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................................................. [1512%]
........................................................................ [1515%]
........................................................................ [1518%]
........................................................................ [1522%]
........................................................................ [1525%]
.........[contention-diag] +3503s soak 32p/172t rss 13.5G pss 12.3G swap 0.6G majflt 656 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.07 cpu 28.95 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45189002i tmp 29.0G/1005262i workspace 322.1G/45189002i | repeat-01 collected 26/26 workers (60622 items) tests 35051 done 1 failed | 24 in flight, oldest 439s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
............................................................... [1528%]
........................................................................ [1531%]
........................................................................ [1534%]
........................................................................ [1537%]
........................................................................ [1540%]
........................................................................ [1543%]
...............................[contention-diag] +3518s soak 32p/182t rss 13.5G pss 12.3G swap 0.6G majflt 664 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 26.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.01 cpu 25.58 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45187432i tmp 29.0G/1005262i workspace 322.1G/45187432i | repeat-01 collected 26/26 workers (60622 items) tests 35514 done 1 failed | 24 in flight, oldest 325s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
......................................... [1547%]
........................................................................ [1550%]
........................................................................ [1553%]
........................................................................ [1556%]
........................................................................ [1559%]
...........[contention-diag] +3534s soak 31p/169t rss 13.4G pss 12.2G swap 0.6G majflt 665 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 3 descendant rss 0.0G pss 0.0G | host avail 23.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 20.59 | cgroup 13.9G/max oom_kill 0 | free scratch 321.8G/45186591i tmp 29.0G/1005262i workspace 321.8G/45186591i | repeat-01 collected 26/26 workers (60622 items) tests 35854 done 1 failed | 24 in flight, oldest 341s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................................................. [1562%]
........................................................................ [1565%]
........................................................................ [1569%]
........................................................................ [1572%]
.....................................[contention-diag] +3549s soak 31p/179t rss 13.4G pss 12.2G swap 0.6G majflt 666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 3 descendant rss 0.0G pss 0.0G | host avail 29.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 24.85 | cgroup 13.9G/max oom_kill 0 | free scratch 322.1G/45185602i tmp 29.0G/1005262i workspace 322.1G/45185602i | repeat-01 collected 26/26 workers (60622 items) tests 36180 done 1 failed | 24 in flight, oldest 356s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................................... [1575%]
........................................................................ [1578%]
........................................................................ [1581%]
........................................................................ [1584%]
........................................................................ [1587%]
........................................................................ [1590%]
..............[contention-diag] +3564s soak 34p/177t rss 13.5G pss 12.3G swap 0.6G majflt 666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 6 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.34 cpu 31.1 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45183961i tmp 29.0G/1005262i workspace 322.1G/45183961i | repeat-01 collected 26/26 workers (60622 items) tests 36585 done 1 failed | 24 in flight, oldest 371s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.......................................................... [1594%]
........................................................................ [1597%]
........................................................................ [1600%]
........................................................................ [1603%]
.....................................................................[contention-diag] +3580s soak 32p/181t rss 13.5G pss 12.4G swap 0.6G majflt 666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 28.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 25.7 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45182572i tmp 29.0G/1005262i workspace 322.1G/45182572i | repeat-01 collected 26/26 workers (60622 items) tests 36930 done 1 failed | 24 in flight, oldest 387s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
... [1606%]
........................................................................ [1609%]
........................................................................ [1612%]
........................................................................ [1616%]
.....................................[contention-diag] +3595s soak 33p/180t rss 13.5G pss 12.3G swap 0.6G majflt 680 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 30.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 30.92 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45181701i tmp 29.0G/1005262i workspace 322.1G/45181701i | repeat-01 collected 26/26 workers (60622 items) tests 37172 done 1 failed | 24 in flight, oldest 402s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................................... [1619%]
........................................................................ [1622%]
........................................................................ [1625%]
........................................................................ [1628%]
........................................................................ [1631%]
........................................................................ [1634%]
........................................................................ [1637%]
..................................................[contention-diag] +3610s soak 31p/165t rss 13.5G pss 12.3G swap 0.6G majflt 685 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 3 descendant rss 0.1G pss 0.1G | host avail 30.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.06 cpu 33.64 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45180669i tmp 29.0G/1005262i workspace 322.1G/45180669i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 37617 done 1 failed | 23 in flight, oldest 417s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...................... [1641%]
..........F[contention-failure] call tests/test_output.py::test_provider_timer_stops_background_thread: def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
                timer_threads = [
                    thread
                    for thread in threading.enumerate()
                    if thread.name == "sase-provider-timer"
                    and thread.ident not in existing_thread_ids
                ]
>               assert len(timer_threads) == 1
E               assert 0 == 1
E                +  where 0 = len([])

tests/test_output.py:67: AssertionError
............................................................. [1644%]
........................................................................ [1647%]
........................................................................ [1650%]
........................................................................ [1653%]
............[contention-diag] +3628s soak 35p/194t rss 13.6G pss 12.4G swap 0.6G majflt 685 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 7 descendant rss 0.2G pss 0.1G | host avail 29.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 28.91 | cgroup 14.1G/max oom_kill 0 | free scratch 322.1G/45179136i tmp 29.0G/1005262i workspace 322.1G/45179136i | repeat-01 collected 26/26 workers (60622 items) tests 38014 done 2 failed | 24 in flight, oldest 435s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................................................ [1656%]
............s.....................................s..................... [1659%]
........................................................................ [1662%]
............................................................[contention-diag] +3643s soak 37p/200t rss 13.6G pss 12.4G swap 0.6G majflt 685 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.9G, 9 descendant rss 0.2G pss 0.1G | host avail 29.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 27.37 | cgroup 14.1G/max oom_kill 0 | free scratch 322.1G/45178374i tmp 29.0G/1005262i workspace 322.1G/45178374i | repeat-01 collected 26/26 workers (60622 items) tests 38288 done 2 failed | 23 in flight, oldest 333s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 8 hazardous kill call(s)
............ [1666%]
.......................................s................................ [1669%]
........................................................................ [1672%]
........................................................................ [1675%]
.....[contention-diag] +3658s soak 38p/206t rss 13.7G pss 12.5G swap 0.6G majflt 685 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 10 descendant rss 0.3G pss 0.2G | host avail 28.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.2 cpu 26.72 | cgroup 14.2G/max oom_kill 0 | free scratch 322.0G/45178162i tmp 29.0G/1005262i workspace 322.0G/45178162i | repeat-01 collected 26/26 workers (60622 items) tests 38515 done 2 failed | 24 in flight, oldest 281s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................................... [1678%]
........................................................................ [1681%]
........................................................................ [1684%]
........................................................[contention-diag] +3674s soak 39p/207t rss 13.8G pss 12.5G swap 0.6G majflt 694 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 11 descendant rss 0.4G pss 0.3G | host avail 30.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 30.56 | cgroup 14.3G/max oom_kill 0 | free scratch 322.1G/45177273i tmp 29.0G/1005262i workspace 322.1G/45177273i | repeat-01 collected 26/26 workers (60622 items) tests 38787 done 2 failed | 24 in flight, oldest 296s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................ [1688%]
........................................................................ [1691%]
........................................................................ [1694%]
............................................[contention-diag] +3689s soak 37p/192t rss 13.8G pss 12.6G swap 0.6G majflt 695 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.4G pss 0.3G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 33.25 | cgroup 14.3G/max oom_kill 0 | free scratch 322.0G/45176822i tmp 29.0G/1003853i workspace 322.0G/45176822i | repeat-01 collected 26/26 workers (60622 items) tests 38985 done 2 failed | 24 in flight, oldest 311s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1697%]
........................................................................ [1700%]
........................................................................ [1703%]
................................................................[contention-diag] +3704s soak 35p/186t rss 13.9G pss 12.7G swap 0.6G majflt 754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 7 descendant rss 0.4G pss 0.4G | host avail 29.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 26.38 | cgroup 14.4G/max oom_kill 0 | free scratch 322.0G/45176273i tmp 29.0G/1003853i workspace 322.0G/45176273i | repeat-01 collected 26/26 workers (60622 items) tests 39219 done 2 failed | 24 in flight, oldest 327s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
........ [1706%]
........................................................................ [1709%]
........................................................................ [1713%]
....................................[contention-diag] +3720s soak 37p/197t rss 13.8G pss 12.6G swap 0.6G majflt 754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 9 descendant rss 0.3G pss 0.3G | host avail 28.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 3.72/3.18 io 0.0 cpu 17.99 | cgroup 14.7G/max oom_kill 0 | free scratch 322.0G/45175382i tmp 28.9G/1002437i workspace 322.0G/45175382i | repeat-01 collected 26/26 workers (60622 items) tests 39420 done 2 failed | 24 in flight, oldest 342s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................................... [1716%]
........................................................................ [1719%]
........................................................................ [1722%]
........................................................................ [1725%]
........................................................................ [1728%]
........................................................................ [1731%]
............................................[contention-diag] +3735s soak 37p/189t rss 13.8G pss 12.6G swap 0.6G majflt 755 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.4G pss 0.3G | host avail 30.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.75/0.64 io 0.28 cpu 29.75 | cgroup 15.0G/max oom_kill 0 | free scratch 321.7G/45174284i tmp 28.9G/1002436i workspace 321.7G/45174284i | scratch used 1.0G in 191751 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 39756 done 2 failed | 23 in flight, oldest 357s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1735%]
........................................................................ [1738%]
........................................................................ [1741%]
...........................................................[contention-diag] +3753s soak 36p/179t rss 13.8G pss 12.6G swap 0.6G majflt 755 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 8 descendant rss 0.4G pss 0.3G | host avail 29.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.15/0.12 io 0.32 cpu 22.21 | cgroup 15.1G/max oom_kill 0 | free scratch 321.4G/45172731i tmp 28.8G/1001406i workspace 321.4G/45172731i | repeat-01 collected 26/26 workers (60622 items) tests 40087 done 2 failed | 24 in flight, oldest 375s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............. [1744%]
........................................................................ [1747%]
........................................................................ [1750%]
........................................................................ [1753%]
..........[contention-diag] +3768s soak 40p/191t rss 13.7G pss 12.5G swap 0.6G majflt 756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 12 descendant rss 0.3G pss 0.2G | host avail 29.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.74 cpu 25.28 | cgroup 14.5G/max oom_kill 0 | free scratch 322.0G/45171862i tmp 28.7G/1001354i workspace 322.0G/45171862i | repeat-01 collected 26/26 workers (60622 items) tests 40329 done 2 failed | 23 in flight, oldest 390s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............................................................. [1756%]
...................................................s.................... [1760%]
........................................................................ [1763%]
.....................................[contention-diag] +3783s soak 37p/184t rss 13.9G pss 12.7G swap 0.6G majflt 756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.9G, 9 descendant rss 0.5G pss 0.4G | host avail 28.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.13 cpu 27.94 | cgroup 14.7G/max oom_kill 0 | free scratch 322.0G/45171290i tmp 28.7G/1001289i workspace 322.0G/45171290i | repeat-01 collected 26/26 workers (60622 items) tests 40556 done 2 failed | 24 in flight, oldest 406s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................... [1766%]
........................................................................ [1769%]
........................................................................ [1772%]
........................................................................ [1775%]
........................................................................ [1778%]
..............................................................[contention-diag] +3799s soak 35p/181t rss 13.9G pss 12.6G swap 0.6G majflt 756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 7 descendant rss 0.4G pss 0.3G | host avail 28.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.1 cpu 28.29 | cgroup 14.6G/max oom_kill 0 | free scratch 322.0G/45170857i tmp 28.7G/1001280i workspace 322.0G/45170857i | repeat-01 collected 26/26 workers (60622 items) tests 40947 done 2 failed | 24 in flight, oldest 421s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1781%]
........................................................................ [1785%]
........................................................................ [1788%]
...............................................[contention-diag] +3814s soak 36p/188t rss 13.9G pss 12.7G swap 0.6G majflt 756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 8 descendant rss 0.4G pss 0.4G | host avail 28.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.11 cpu 22.08 | cgroup 14.6G/max oom_kill 0 | free scratch 322.0G/45170204i tmp 28.7G/1001276i workspace 322.0G/45170204i | repeat-01 collected 26/26 workers (60622 items) tests 41139 done 2 failed | 23 in flight, oldest 170s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
......................... [1791%]
........................................................................ [1794%]
........................................................................ [1797%]
........................................................................ [1800%]
........................................................................ [1803%]
................................................................[contention-diag] +3829s soak 35p/186t rss 14.0G pss 12.7G swap 0.6G majflt 756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 7 descendant rss 0.5G pss 0.4G | host avail 29.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.38/0.38 io 0.7 cpu 21.01 | cgroup 14.7G/max oom_kill 0 | free scratch 322.0G/45169177i tmp 28.7G/1001276i workspace 322.0G/45169177i | repeat-01 collected 26/26 workers (60622 items) tests 41522 done 2 failed | 23 in flight, oldest 185s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
........ [1807%]
........................................................................ [1810%]
........................................................................ [1813%]
........................................................................ [1816%]
........................................................................ [1819%]
........................................................................ [1822%]
........................................................................ [1825%]
........................................................................ [1828%]
...........................[contention-diag] +3845s soak 42p/197t rss 14.0G pss 12.7G swap 0.6G majflt 757 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 14 descendant rss 0.5G pss 0.4G | host avail 29.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.82 cpu 23.9 | cgroup 14.7G/max oom_kill 0 | free scratch 322.0G/45167234i tmp 29.0G/1005143i workspace 322.0G/45167234i | repeat-01 collected 26/26 workers (60622 items) tests 42053 done 2 failed | 23 in flight, oldest 201s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
............................................. [1832%]
........................................................................ [1835%]
........................................................................ [1838%]
........................................................................ [1841%]
........................................................................ [1844%]
........................................................................ [1847%]
.....[contention-diag] +3860s soak 38p/190t rss 14.0G pss 12.7G swap 0.6G majflt 757 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 10 descendant rss 0.5G pss 0.4G | host avail 29.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.06 cpu 31.9 | cgroup 14.8G/max oom_kill 0 | free scratch 322.0G/45165040i tmp 29.0G/1005143i workspace 322.0G/45165040i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 42396 done 2 failed | 24 in flight, oldest 216s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................................................... [1850%]
........................................................................ [1854%]
........................................................................ [1857%]
.......[contention-diag] +3878s soak 37p/192t rss 14.0G pss 12.8G swap 0.6G majflt 757 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 9 descendant rss 0.5G pss 0.4G | host avail 28.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.95 cpu 28.53 | cgroup 14.8G/max oom_kill 0 | free scratch 322.0G/45164251i tmp 29.0G/1005143i workspace 322.0G/45164251i | repeat-01 collected 26/26 workers (60622 items) tests 42703 done 2 failed | 24 in flight, oldest 233s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................................................. [1860%]
........................................................................ [1863%]
......................................................................[contention-diag] +3893s soak 39p/188t rss 14.1G pss 12.8G swap 0.6G majflt 761 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 11 descendant rss 0.5G pss 0.5G | host avail 29.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.05 cpu 30.43 | cgroup 14.9G/max oom_kill 0 | free scratch 322.0G/45163114i tmp 29.0G/1005143i workspace 322.0G/45163114i | repeat-01 collected 26/26 workers (60622 items) tests 42906 done 2 failed | 24 in flight, oldest 249s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.. [1866%]
........................................................................ [1869%]
........................................................................ [1872%]
........................................................[contention-diag] +3908s soak 37p/199t rss 14.1G pss 12.8G swap 0.6G majflt 762 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 9 descendant rss 0.5G pss 0.5G | host avail 30.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.89 cpu 32.63 | cgroup 14.9G/max oom_kill 0 | free scratch 322.0G/45160465i tmp 29.0G/1005143i workspace 322.0G/45160465i | repeat-01 collected 26/26 workers (60622 items) tests 43107 done 2 failed | 24 in flight, oldest 264s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................ [1875%]
........................................................................ [1879%]
........................................................................ [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
........................................................................ [1891%]
.........................................................[contention-diag] +3924s soak 38p/189t rss 14.3G pss 13.0G swap 0.6G majflt 762 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 10 descendant rss 0.7G pss 0.6G | host avail 27.9G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 31.39 | cgroup 15.1G/max oom_kill 0 | free scratch 322.0G/45161137i tmp 29.0G/1005143i workspace 322.0G/45161137i | repeat-01 collected 26/26 workers (60622 items) tests 43531 done 2 failed | 24 in flight, oldest 280s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
............... [1894%]
........................................................................ [1897%]
........................................................................ [1901%]
........................................................................ [1904%]
........................................................................ [1907%]
......................................[contention-diag] +3939s soak 44p/195t rss 14.5G pss 13.2G swap 0.6G majflt 763 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 16 descendant rss 0.9G pss 0.8G | host avail 26.4G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 23.43 | cgroup 15.3G/max oom_kill 0 | free scratch 322.0G/45161387i tmp 29.0G/1005142i workspace 322.0G/45161387i | repeat-01 collected 26/26 workers (60622 items) tests 43871 done 2 failed | 23 in flight, oldest 295s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.................................. [1910%]
........................................................................ [1913%]
........................................................................ [1916%]
........................................................................ [1919%]
........................................................................ [1922%]
....................................[contention-diag] +3954s soak 43p/193t rss 14.3G pss 13.0G swap 0.6G majflt 763 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.0G, 15 descendant rss 0.7G pss 0.6G | host avail 26.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 20.1 | cgroup 15.1G/max oom_kill 0 | free scratch 322.0G/45160962i tmp 29.0G/1005142i workspace 322.0G/45160962i | repeat-01 collected 26/26 workers (60622 items) tests 44236 done 2 failed | 22 in flight, oldest 310s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.................................... [1926%]
........................................................................ [1929%]
........................................................................ [1932%]
........................................................................ [1935%]
........................................................................ [1938%]
........................................................................ [1941%]
........................................................................ [1944%]
..[contention-diag] +3970s soak 35p/192t rss 14.3G pss 13.0G swap 0.6G majflt 763 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.6G pss 0.6G | host avail 27.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 4.16/3.62 io 0.01 cpu 16.51 | cgroup 15.1G/max oom_kill 0 | free scratch 322.0G/45159865i tmp 28.9G/1003709i workspace 322.0G/45159865i | repeat-01 collected 26/26 workers (60622 items) tests 44694 done 2 failed | 21 in flight, oldest 271s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................................................... [1947%]
........................................................................ [1951%]
........................................................................ [1954%]
........................................................................ [1957%]
.......................................................[contention-diag] +3985s soak 36p/194t rss 14.4G pss 13.1G swap 0.6G majflt 763 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 0.7G pss 0.7G | host avail 25.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 1.02/0.89 io 0.15 cpu 20.81 | cgroup 15.2G/max oom_kill 0 | free scratch 322.0G/45159023i tmp 28.9G/1003697i workspace 322.0G/45159023i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 44983 done 2 failed | 22 in flight, oldest 286s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................. [1960%]
........s............................................................... [1963%]
........................................................................ [1966%]
........................................................................ [1969%]
..................................................................[contention-diag] +4002s soak 36p/185t rss 14.4G pss 13.2G swap 0.6G majflt 763 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 0.8G pss 0.7G | host avail 23.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.16/0.14 io 0.21 cpu 18.43 | cgroup 15.3G/max oom_kill 0 | free scratch 321.9G/45157579i tmp 28.8G/1002668i workspace 321.9G/45157579i | repeat-01 collected 26/26 workers (60622 items) tests 45333 done 2 failed | 21 in flight, oldest 303s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...... [1973%]
........................................................................ [1976%]
........................................................................ [1979%]
........................................................................ [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
......................................[contention-diag] +4018s soak 36p/189t rss 14.5G pss 13.2G swap 0.6G majflt 764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 0.8G pss 0.8G | host avail 24.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 0.52 cpu 21.55 | cgroup 15.4G/max oom_kill 0 | free scratch 321.9G/45156285i tmp 28.7G/1002637i workspace 321.9G/45156285i | repeat-01 collected 26/26 workers (60622 items) tests 45736 done 2 failed | 21 in flight, oldest 319s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................. [1991%]
........................................................................ [1994%]
........................................................................ [1998%]
........................................................................ [2001%]
........................................................................ [2004%]
...................[contention-diag] +4033s soak 37p/181t rss 14.3G pss 13.1G swap 0.6G majflt 764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 9 descendant rss 0.7G pss 0.6G | host avail 25.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.27 cpu 20.78 | cgroup 15.2G/max oom_kill 0 | free scratch 321.6G/45155215i tmp 28.7G/1002612i workspace 321.6G/45155215i | repeat-01 collected 26/26 workers (60622 items) tests 46089 done 2 failed | 22 in flight, oldest 334s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................... [2007%]
........................................................................ [2010%]
........................................................................ [2013%]
........................................................................ [2016%]
........................................................................ [2020%]
........................................................................ [2023%]
........................................................................ [2026%]
........................................................................ [2029%]
......[contention-diag] +4048s soak 38p/200t rss 14.6G pss 13.3G swap 0.6G majflt 764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 0.9G pss 0.8G | host avail 29.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.87 cpu 19.73 | cgroup 15.4G/max oom_kill 0 | free scratch 321.9G/45154484i tmp 28.7G/1002603i workspace 321.9G/45154484i | repeat-01 collected 26/26 workers (60622 items) tests 46651 done 2 failed | 22 in flight, oldest 349s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................................................. [2032%]
........................................................................ [2035%]
........................................................................ [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
.......................................................[contention-diag] +4064s soak 39p/219t rss 14.7G pss 13.3G swap 0.6G majflt 765 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 11 descendant rss 1.0G pss 0.8G | host avail 29.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.32 cpu 20.89 | cgroup 15.5G/max oom_kill 0 | free scratch 322.4G/45152952i tmp 28.7G/1002604i workspace 322.4G/45152952i | repeat-01 collected 26/26 workers (60622 items) tests 47208 done 2 failed | 22 in flight, oldest 365s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................. [2054%]
........................................................................ [2057%]
........................................................................ [2060%]
........................................................................ [2063%]
............[contention-diag] +4079s soak 37p/172t rss 14.7G pss 13.4G swap 0.6G majflt 765 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 9 descendant rss 1.0G pss 0.9G | host avail 28.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.58 cpu 20.78 | cgroup 15.6G/max oom_kill 0 | free scratch 322.3G/45149747i tmp 28.7G/1002584i workspace 322.3G/45149747i | repeat-01 collected 26/26 workers (60622 items) tests 47460 done 2 failed | 21 in flight, oldest 380s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................................ [2066%]
........................................................................ [2070%]
........................................................................ [2073%]
........................................................................ [2076%]
........................................................................ [2079%]
........................................................................ [2082%]
........................................................................ [2085%]
........................................................................ [2088%]
................................[contention-diag] +4095s soak 36p/174t rss 14.7G pss 13.5G swap 0.6G majflt 765 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 1.0G pss 1.0G | host avail 27.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.36 cpu 21.15 | cgroup 15.7G/max oom_kill 0 | free scratch 322.4G/45151429i tmp 28.7G/1002541i workspace 322.4G/45151429i | repeat-01 collected 26/26 workers (60622 items) tests 48052 done 2 failed | 21 in flight, oldest 396s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................ [2092%]
........................................................................ [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
........................................................................ [2104%]
......................................[contention-diag] +4110s soak 40p/176t rss 14.8G pss 13.5G swap 0.6G majflt 768 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 12 descendant rss 1.1G pss 1.0G | host avail 25.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.91 cpu 21.32 | cgroup 15.8G/max oom_kill 0 | free scratch 322.3G/45151302i tmp 28.7G/1002541i workspace 322.3G/45151302i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 48355 done 2 failed | 20 in flight, oldest 411s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................. [2107%]
........................................................................ [2110%]
........................................................................ [2113%]
........................................................................ [2117%]
........................................................................ [2120%]
.............[contention-diag] +4127s soak 36p/173t rss 14.8G pss 13.5G swap 0.6G majflt 767 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 1.1G pss 1.0G | host avail 25.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.0 cpu 21.87 | cgroup 15.9G/max oom_kill 0 | free scratch 322.3G/45150158i tmp 28.7G/1002541i workspace 322.3G/45150158i | repeat-01 collected 26/26 workers (60622 items) tests 48734 done 2 failed | 20 in flight, oldest 400s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................... [2123%]
........................................................................ [2126%]
........................................................................ [2129%]
........................................................................ [2132%]
........................................................................ [2135%]
........................................................................ [2139%]
...........................[contention-diag] +4143s soak 38p/186t rss 14.9G pss 13.7G swap 0.6G majflt 780 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 1.2G pss 1.1G | host avail 29.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 1.89 cpu 19.13 | cgroup 15.9G/max oom_kill 0 | free scratch 321.9G/45148471i tmp 28.7G/1002541i workspace 321.9G/45148471i | repeat-01 collected 26/26 workers (60622 items) tests 49196 done 2 failed | 20 in flight, oldest 415s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................. [2142%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........[contention-diag] +4158s soak 38p/201t rss 14.8G pss 13.5G swap 0.6G majflt 780 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 1.1G pss 1.0G | host avail 29.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 1.93 cpu 19.88 | cgroup 15.8G/max oom_kill 0 | free scratch 321.1G/45148145i tmp 28.7G/1002541i workspace 321.1G/45148145i | repeat-01 collected 26/26 workers (60622 items) tests 49461 done 2 failed | 19 in flight, oldest 430s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................ [2154%]
........................................................................ [2157%]
........................................................................ [2160%]
........................................................................ [2164%]
........................................................................ [2167%]
........................................................................ [2170%]
..................................................................[contention-diag] +4174s soak 38p/204t rss 14.8G pss 13.5G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.2G, 10 descendant rss 1.0G pss 0.9G | host avail 28.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.98 cpu 21.15 | cgroup 15.8G/max oom_kill 0 | free scratch 321.1G/45147026i tmp 28.7G/1002541i workspace 321.1G/45147026i | repeat-01 collected 26/26 workers (60622 items) tests 49955 done 2 failed | 19 in flight, oldest 446s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...... [2173%]
........................................................................ [2176%]
........................................................................ [2179%]
........................................................................ [2182%]
........................................................................ [2185%]
.................................................[contention-diag] +4189s soak 44p/201t rss 15.0G pss 13.7G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 16 descendant rss 1.3G pss 1.2G | host avail 29.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.34 cpu 24.23 | cgroup 16.0G/max oom_kill 0 | free scratch 321.1G/45146578i tmp 28.7G/1002541i workspace 321.1G/45146578i | repeat-01 collected 26/26 workers (60622 items) tests 50303 done 2 failed | 18 in flight, oldest 461s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................... [2189%]
........................................................................ [2192%]
........................................................................ [2195%]
........................................................................ [2198%]
........................................................................ [2201%]
.....................................s.................................. [2204%]
........................................................................ [2207%]
..........................[contention-diag] +4204s soak 41p/186t rss 14.8G pss 13.5G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 13 descendant rss 1.1G pss 1.0G | host avail 28.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.16 cpu 22.84 | cgroup 15.8G/max oom_kill 0 | free scratch 321.1G/45145237i tmp 28.7G/1002541i workspace 321.1G/45145237i | repeat-01 collected 26/26 workers (60622 items) tests 50779 done 2 failed | 17 in flight, oldest 477s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................. [2211%]
........................................................................ [2214%]
........................................................................ [2217%]
........................................................................ [2220%]
........................................................................ [2223%]
........................................................................ [2226%]
........................................................................ [2229%]
[contention-diag] +4220s soak 43p/185t rss 15.0G pss 13.7G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 15 descendant rss 1.3G pss 1.1G | host avail 29.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.75 cpu 23.12 | cgroup 16.0G/max oom_kill 0 | free scratch 321.1G/45143898i tmp 28.7G/1002541i workspace 321.1G/45143898i | repeat-01 collected 26/26 workers (60622 items) tests 51257 done 2 failed | 18 in flight, oldest 492s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................................ [2232%]
........................................................................ [2236%]
........................................................................ [2239%]
........................................................................ [2242%]
........................[contention-diag] +4235s soak 36p/164t rss 14.9G pss 13.6G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 1.2G pss 1.1G | host avail 28.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.93 cpu 27.2 | cgroup 16.0G/max oom_kill 0 | free scratch 321.1G/45142428i tmp 28.7G/1002541i workspace 321.1G/45142428i | scratch used 1.0G in 189860 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 51551 done 2 failed | 18 in flight, oldest 507s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................ [2245%]
........................................................................ [2248%]
........................................................................ [2251%]
........................................................................ [2254%]
........................................................................ [2258%]
.............................[contention-diag] +4253s soak 34p/172t rss 14.7G pss 13.5G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.2G, 6 descendant rss 1.0G pss 0.9G | host avail 27.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.01 cpu 22.77 | cgroup 16.0G/max oom_kill 0 | free scratch 321.1G/45141392i tmp 28.7G/1002541i workspace 321.1G/45141392i | repeat-01 collected 26/26 workers (60622 items) tests 51935 done 2 failed | 18 in flight, oldest 525s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................... [2261%]
........................................................................ [2264%]
........................................................................ [2267%]
........................................................................ [2270%]
........................................................................ [2273%]
........................................................................ [2276%]
........................................................................ [2279%]
.......................................[contention-diag] +4268s soak 36p/173t rss 14.8G pss 13.5G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 8 descendant rss 1.0G pss 0.9G | host avail 29.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.08 cpu 28.58 | cgroup 16.1G/max oom_kill 0 | free scratch 321.1G/45140041i tmp 28.7G/1002541i workspace 321.1G/45140041i | repeat-01 collected 26/26 workers (60622 items) tests 52450 done 2 failed | 17 in flight, oldest 540s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................. [2283%]
........................................................................ [2286%]
........................................................................ [2289%]
........................................................................ [2292%]
........................................................................ [2295%]
........................................................................ [2298%]
...........................................[contention-diag] +4283s soak 37p/177t rss 14.8G pss 13.5G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 9 descendant rss 1.0G pss 1.0G | host avail 26.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.94 cpu 24.96 | cgroup 16.1G/max oom_kill 0 | free scratch 321.1G/45138861i tmp 28.7G/1002541i workspace 321.1G/45138861i | repeat-01 collected 26/26 workers (60622 items) tests 52887 done 2 failed | 17 in flight, oldest 556s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................. [2301%]
........................................................................ [2305%]
........................................................................ [2308%]
........................................................................ [2311%]
.....................................................s.................. [2314%]
........................................................................ [2317%]
........................................................................ [2320%]
........................................................................ [2323%]
................[contention-diag] +4299s soak 35p/165t rss 14.8G pss 13.5G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 7 descendant rss 1.0G pss 1.0G | host avail 25.7G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 2.89 cpu 20.55 | cgroup 16.1G/max oom_kill 0 | free scratch 320.8G/45137310i tmp 28.7G/1002541i workspace 320.8G/45137310i | repeat-01 collected 26/26 workers (60622 items) tests 53424 done 2 failed | 18 in flight, oldest 571s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................................................ [2326%]
........................................................................ [2330%]
........................................................................ [2333%]
........................................................................ [2336%]
........................................................................ [2339%]
........................................................................ [2342%]
........................................................................ [2345%]
........................................................................ [2348%]
........................................................................ [2351%]
........................................................................ [2355%]
........................................................................ [2358%]
........................................................................ [2361%]
........................................................................ [2364%]
.......[contention-diag] +4314s soak 39p/182t rss 14.9G pss 13.6G swap 0.6G majflt 769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 11 descendant rss 1.1G pss 1.0G | host avail 24.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.45/0.45 io 2.48 cpu 16.47 | cgroup 16.2G/max oom_kill 0 | free scratch 320.8G/45135051i tmp 28.7G/1002541i workspace 320.8G/45135051i | repeat-01 collected 26/26 workers (60622 items) tests 54344 done 2 failed | 18 in flight, oldest 586s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................................................. [2367%]
........................................................................ [2370%]
........................................................................ [2373%]
........................................................................ [2377%]
........................................................................ [2380%]
........................................................................ [2383%]
........................................................................ [2386%]
........................................................................ [2389%]
............................................................[contention-diag] +4330s soak 39p/173t rss 15.0G pss 13.6G swap 0.7G majflt 770 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 11 descendant rss 1.2G pss 1.1G | host avail 24.1G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.23/0.23 io 2.24 cpu 18.98 | cgroup 16.0G/max oom_kill 0 | free scratch 320.7G/45133157i tmp 28.7G/1002541i workspace 320.7G/45133157i | repeat-01 collected 26/26 workers (60622 items) tests 54956 done 2 failed | 17 in flight, oldest 602s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............ [2392%]
........................................................................ [2395%]
........................................................................ [2398%]
........................................................................ [2402%]
........................................................................ [2405%]
........................................................................ [2408%]
........................................................................ [2411%]
.....................................................[contention-diag] +4345s soak 38p/181t rss 14.2G pss 12.9G swap 0.7G majflt 771 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 10 descendant rss 0.4G pss 0.3G | host avail 23.0G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 1.5 cpu 19.69 | cgroup 15.4G/max oom_kill 0 | free scratch 320.6G/45134405i tmp 28.7G/1002541i workspace 320.6G/45134405i | repeat-01 collected 26/26 workers (60622 items) tests 55477 done 2 failed | 15 in flight, oldest 81s gw25 tests/test_timezone_display_guard.py::test_no_system_clock_display_sites | 10 hazardous kill call(s)
................... [2414%]
........................................................................ [2417%]
........................................................................ [2420%]
...............................................................[contention-diag] +4360s soak 42p/175t rss 14.4G pss 13.1G swap 0.7G majflt 771 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 14 descendant rss 0.6G pss 0.5G | host avail 24.2G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.68 cpu 23.27 | cgroup 15.6G/max oom_kill 0 | free scratch 320.6G/45133580i tmp 28.7G/1002539i workspace 320.6G/45133580i | scratch used 1.1G in 200000 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 55678 done 2 failed | 15 in flight, oldest 96s gw25 tests/test_timezone_display_guard.py::test_no_system_clock_display_sites | 10 hazardous kill call(s)
......... [2424%]
........................................................................ [2427%]
........................................................................ [2430%]
........................................................................ [2433%]
........................................................................ [2436%]
........................................................................ [2439%]
.................[contention-diag] +4378s soak 43p/193t rss 14.5G pss 13.2G swap 0.7G majflt 773 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 15 descendant rss 0.7G pss 0.6G | host avail 24.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.24 cpu 22.09 | cgroup 15.6G/max oom_kill 0 | free scratch 320.5G/45132545i tmp 28.7G/1002534i workspace 320.5G/45132545i | repeat-01 collected 26/26 workers (60622 items) tests 56100 done 2 failed | 15 in flight, oldest 113s gw25 tests/test_timezone_display_guard.py::test_no_system_clock_display_sites | 10 hazardous kill call(s)
....................................................... [2442%]
....................................................................s... [2445%]
........................................................................ [2449%]
........................................................................ [2452%]
.........[contention-diag] +4393s soak 38p/169t rss 14.1G pss 12.8G swap 0.6G majflt 773 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 0.3G pss 0.2G | host avail 27.2G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.54 cpu 19.03 | cgroup 15.3G/max oom_kill 0 | free scratch 320.5G/45131552i tmp 28.7G/1002534i workspace 320.5G/45131552i | repeat-01 collected 26/26 workers (60622 items) tests 56383 done 2 failed | 15 in flight, oldest 125s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............................................................... [2455%]
........................................................................ [2458%]
........................................................................ [2461%]
........................................................................ [2464%]
........................................................................ [2467%]
.....................................[contention-diag] +4408s soak 38p/168t rss 14.1G pss 12.8G swap 0.6G majflt 773 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 10 descendant rss 0.3G pss 0.3G | host avail 28.9G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.37 cpu 21.27 | cgroup 15.3G/max oom_kill 0 | free scratch 321.0G/45131076i tmp 28.7G/1002533i workspace 321.0G/45131076i | repeat-01 collected 26/26 workers (60622 items) tests 56752 done 2 failed | 13 in flight, oldest 140s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
................................... [2470%]
........................................................................ [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
........................................................................ [2483%]
........................................................................ [2486%]
........................................................................ [2489%]
...................................................................[contention-diag] +4424s soak 35p/160t rss 14.2G pss 12.9G swap 0.7G majflt 773 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.3G pss 12.1G, 7 descendant rss 0.4G pss 0.3G | host avail 28.5G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.63 cpu 16.99 | cgroup 15.5G/max oom_kill 0 | free scratch 321.0G/45177322i tmp 28.7G/1002533i workspace 321.0G/45177322i | repeat-01 collected 26/26 workers (60622 items) tests 57295 done 2 failed | 14 in flight, oldest 42s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
..... [2492%]
........................................................................ [2496%]
........................................................................ [2499%]
........................................................................ [2502%]
........................................................................ [2505%]
........................................................................ [2508%]
......................................[contention-diag] +4439s soak 36p/167t rss 14.0G pss 12.7G swap 0.6G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 8 descendant rss 0.2G pss 0.1G | host avail 25.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.79 cpu 12.2 | cgroup 15.3G/max oom_kill 0 | free scratch 321.2G/45229786i tmp 28.7G/1002533i workspace 321.2G/45229786i | repeat-01 collected 26/26 workers (60622 items) tests 57692 done 2 failed | 13 in flight, oldest 57s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.................................. [2511%]
........................................................................ [2514%]
........................................................................ [2517%]
.s...................................................................... [2521%]
........................................................................ [2524%]
........................................................................ [2527%]
........................................................................ [2530%]
........................................................................ [2533%]
............................[contention-diag] +4455s soak 39p/177t rss 14.1G pss 12.8G swap 0.6G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.1G, 11 descendant rss 0.3G pss 0.2G | host avail 25.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.91 cpu 14.37 | cgroup 15.4G/max oom_kill 0 | free scratch 321.4G/45282124i tmp 28.7G/1002533i workspace 321.4G/45282124i | repeat-01 collected 26/26 workers (60622 items) tests 58249 done 2 failed | 11 in flight, oldest 72s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................................ [2536%]
........................................................................ [2539%]
........................................................................ [2543%]
........................................................................ [2546%]
........................................................................ [2549%]
........................................................................ [2552%]
........................................................................ [2555%]
........................................................................ [2558%]
....................[contention-diag] +4470s soak 34p/157t rss 14.0G pss 12.7G swap 0.7G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.1G, 6 descendant rss 0.2G pss 0.1G | host avail 24.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.17 cpu 15.46 | cgroup 15.2G/max oom_kill 0 | free scratch 321.4G/45293323i tmp 28.7G/1002533i workspace 321.4G/45293323i | repeat-01 collected 26/26 workers (60622 items) tests 58836 done 2 failed | 10 in flight, oldest 88s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.................................................... [2561%]
........................................................................ [2564%]
........................................................................ [2568%]
........................................................................ [2571%]
........................................................................ [2574%]
.............................[contention-diag] +4486s soak 35p/156t rss 13.9G pss 12.7G swap 0.6G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 0.1G pss 0.1G | host avail 25.8G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.97 cpu 15.59 | cgroup 15.2G/max oom_kill 0 | free scratch 321.3G/45294267i tmp 28.7G/1002533i workspace 321.3G/45294267i | scratch used 0.5G in 87892 entries (truncated) | repeat-01 collected 26/26 workers (60622 items) tests 59187 done 2 failed | 8 in flight, oldest 103s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
........................................... [2577%]
........................................................................ [2580%]
........................................................................ [2583%]
........................................................................ [2586%]
.......................................................................[contention-diag] +4503s soak 36p/159t rss 13.9G pss 12.6G swap 0.6G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 8 descendant rss 0.1G pss 0.0G | host avail 24.4G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.96 cpu 17.22 | cgroup 15.2G/max oom_kill 0 | free scratch 321.3G/45294649i tmp 28.7G/1002533i workspace 321.3G/45294649i | repeat-01 collected 26/26 workers (60622 items) tests 59516 done 2 failed | 6 in flight, oldest 35s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
. [2589%]
........................................................................ [2593%]
........................................................................ [2596%]
........................................................................ [2599%]
.......................................[contention-diag] +4518s soak 35p/156t rss 13.8G pss 12.6G swap 0.6G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 7 descendant rss 0.0G pss 0.0G | host avail 26.0G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.08 cpu 18.89 | cgroup 15.1G/max oom_kill 0 | free scratch 321.3G/45293988i tmp 28.7G/1002533i workspace 321.3G/45293988i | repeat-01 collected 26/26 workers (60622 items) tests 59784 done 2 failed | 6 in flight, oldest 50s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
................................. [2602%]
........................................................................ [2605%]
........................................................................ [2608%]
........................................................................ [2611%]
........................................................................ [2615%]
........................................................................ [2618%]
........................................ssss.......[contention-diag] +4534s soak 34p/154t rss 13.8G pss 12.6G swap 0.6G majflt 775 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 6 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.5 cpu 20.97 | cgroup 15.3G/max oom_kill 0 | free scratch 321.3G/45294170i tmp 28.7G/1002533i workspace 321.3G/45294170i | repeat-01 collected 26/26 workers (60622 items) tests 60217 done 2 failed | 4 in flight, oldest 4s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
..................... [2621%]
........................................................................ [2624%]
........................................................................ [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
......................................................................   [100%][contention-diag] +4549s soak 32p/143t rss 13.8G pss 12.6G swap 0.6G majflt 778 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.4G pss 12.2G, 4 descendant rss 0.0G pss 0.0G | host avail 27.6G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.96 cpu 14.22 | cgroup 15.1G/max oom_kill 0 | free scratch 321.8G/45296262i tmp 28.7G/1002533i workspace 321.8G/45296262i | repeat-01 collected 26/26 workers (60622 items) tests 60613 done 2 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
______________ test_bump_microbench_stays_within_two_microseconds ______________
[gw21] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

footprint_home = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw21/test_bump_microbench_stays_wit0')

    def test_bump_microbench_stays_within_two_microseconds(
        footprint_home: Path,
    ) -> None:
        # The Full CI 3.12 leg runs tests under branch coverage. Measure in a child
        # interpreter without coverage's subprocess hooks so the 2 µs contract
        # remains about the product's event-loop path, not Python tracing.
        child_env = os.environ.copy()
        for name in tuple(child_env):
            if name.startswith(("COV_CORE_", "COVERAGE_")):
                child_env.pop(name)
        child_env["SASE_FOOTPRINT"] = "test"
        script = """
    import json
    import sys
    import time
    
    if sys.gettrace() is not None:
        raise RuntimeError("coverage tracing is active in the benchmark child")
    
    from sase.footprint import _tui
    
    feature = "tui:app.dismiss_toasts"
    for _ in range(200):
        _tui.bump(feature, "key")
    iterations = 5000
    samples = []
    for _ in range(5):
        start = time.perf_counter()
        for _ in range(iterations):
            _tui.bump(feature, "key")
        samples.append((time.perf_counter() - start) / iterations)
    print(json.dumps({"best": min(samples)}))
    """
        result = subprocess.run(
            [sys.executable, "-c", script],
            capture_output=True,
            check=False,
            env=child_env,
            text=True,
            timeout=30,
        )
        assert result.returncode == 0, result.stderr
        best = float(json.loads(result.stdout)["best"])
>       assert best <= 2e-6, f"best bump cost {best * 1e6:.3f} µs"
E       AssertionError: best bump cost 3.402 µs
E       assert 3.4024613996734842e-06 <= 2e-06

tests/footprint/test_tui.py:190: AssertionError
_________________ test_provider_timer_stops_background_thread __________________
[gw5] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

    def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
                timer_threads = [
                    thread
                    for thread in threading.enumerate()
                    if thread.name == "sase-provider-timer"
                    and thread.ident not in existing_thread_ids
                ]
>               assert len(timer_threads) == 1
E               assert 0 == 1
E                +  where 0 = len([])

tests/test_output.py:67: AssertionError
----------------------------- Captured stdout call -----------------------------
✅ Short operation completed in 00:00
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

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_early_open_paints_loading_and_queues_until_gate
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/inspect.py:3076: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    params = OrderedDict((param.name, param) for param in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_proc_submit_captures_confirm_flags
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _recheck_grammar_key at 0x7f98e2e7a460>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/modals/test_project_management_modal_edit.py::test_project_management_modal_alias_editor_updates_selected_project
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_submit_happy_path_settles_on_exit_completion
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    path = os.fspath(arg)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_collapsed_panel_selection.py::test_collapsed_nonfocused_panel_does_not_hide_expanded_selection
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    payload = binding(
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=408505) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=408293) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=409012) is multi-threaded, use of fork() may lead to deadlocks in the child.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=408346) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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
  <frozen os>:888: DeprecationWarning: This process (pid=408293) is multi-threaded, use of fork() may lead to deadlocks in the child.

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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=409168) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
602.72s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
448.66s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
448.06s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
436.25s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
417.58s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
394.30s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
337.68s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
334.04s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
331.91s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
320.15s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
306.23s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
258.70s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
211.65s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
190.61s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
184.46s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
174.94s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
165.15s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
163.09s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
156.66s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
152.30s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
=========================== short test summary info ============================
FAILED tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds
FAILED tests/test_output.py::test_provider_timer_stops_background_thread - as...
==== 2 failed, 60600 passed, 21 skipped, 111 warnings in 4558.31s (1:15:58) ====
[contention-diag] +4564s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G | host avail 40.3G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.51 cpu 8.67 | cgroup 2.6G/max oom_kill 0 | free scratch 321.7G/45296249i tmp 28.7G/1002533i workspace 321.7G/45296249i | repeat-01 collected 26/26 workers (60622 items) tests 60622 done 2 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4564s, 294 samples, 0 signal(s); peaks: cgroup_current 16.2G, min_free_scratch 318.7G, min_free_tmp 28.7G, min_free_workspace 318.7G, min_inodes_scratch 45131076, min_inodes_tmp 1001276, min_inodes_workspace 45131076, min_mem_available 22.4G, min_swap_free 54.2G, oom_kill_delta 0, pressure_memory_full 3.62, pswpin_delta 42587, pswpout_delta 286573, scratch_bytes 1.1G, soak_procs 49, soak_pss 13.7G, soak_rss 15.0G, soak_swap 0.7G, soak_threads 297

contention tally: 2 node(s) failed across 1 repeat(s) in 4564.4s; red repeats: 1
  1/1  tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds  (repeats 1)
  1/1  tests/test_output.py::test_provider_timer_stops_background_thread  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

