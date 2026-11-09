# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-8)

- **TIMESTAMP:** 2026-11-08 22:26:56 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-8

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after cycle echo-skip, caller-thread Live timer, and identity-aware group-kill repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase tool run a065cbc3a8ddf64506addb6e0b455a52
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 2170940, sampler pid 2170974 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-497468-1794190235362798013.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 41.2G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 316.8G/45470172i tmp 28.3G/998089i workspace 316.8G/45470172i | scratch used 0.0G in 13 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.1G pss 1.8G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.0G pss 1.7G | host avail 39.6G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 15.88 | cgroup 1.9G/max oom_kill 0 | free scratch 316.9G/45470068i tmp 28.3G/998089i workspace 316.9G/45470068i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 3.4G pss 3.0G swap 0.8G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.3G pss 2.9G | host avail 38.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 23.74 | cgroup 3.1G/max oom_kill 0 | free scratch 316.9G/45470065i tmp 28.3G/998089i workspace 316.9G/45470065i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +45s soak 28p/81t rss 4.6G pss 4.2G swap 1.1G majflt 0 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.5G pss 4.1G | host avail 39.6G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.55 | cgroup 4.3G/max oom_kill 0 | free scratch 316.9G/45470088i tmp 28.3G/998089i workspace 316.9G/45470088i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +61s soak 28p/87t rss 5.4G pss 5.0G swap 1.0G majflt 77 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.3G pss 4.9G | host avail 38.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.85 | cgroup 5.1G/max oom_kill 0 | free scratch 316.9G/45470100i tmp 28.3G/998089i workspace 316.9G/45470100i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 28p/90t rss 6.2G pss 5.7G swap 1.1G majflt 157 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.0G pss 5.6G | host avail 38.2G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.46 | cgroup 6.0G/max oom_kill 0 | free scratch 316.9G/45470100i tmp 28.3G/998089i workspace 316.9G/45470100i | repeat-01 collected 1/26 workers (2428 items) tests 0 done 0 failed
contention shards: 26 workers collected 60626 items in total (2020-2558 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
..........................................[contention-diag] +91s soak 30p/89t rss 6.7G pss 6.2G swap 1.1G majflt 281 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.5G pss 6.0G, 2 descendant rss 0.0G pss 0.0G | host avail 36.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.63 | cgroup 6.5G/max oom_kill 0 | free scratch 316.9G/45469092i tmp 28.3G/998089i workspace 316.9G/45469092i | repeat-01 collected 26/26 workers (60626 items) tests 101 done 0 failed | 22 in flight, oldest 2s gw20 tests/ace/test_revert_agent_import_order.py::test_module_imports_first_in_a_fresh_interpreter[sase.ace.revert_agent_resolution]
.............................. [  9%]
........................................................................ [ 13%]
........................................................................ [ 16%]
........................................................................ [ 19%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
........................................................................ [ 33%]
........................................................................ [ 36%]
........................................................................ [ 39%]
........................................................................ [ 43%]
.........[contention-diag] +106s soak 30p/125t rss 7.1G pss 6.6G swap 1.0G majflt 673 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.9G pss 6.4G, 2 descendant rss 0.1G pss 0.0G | host avail 35.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 26.82 | cgroup 6.9G/max oom_kill 0 | free scratch 316.9G/45467451i tmp 28.3G/998089i workspace 316.9G/45467451i | repeat-01 collected 26/26 workers (60626 items) tests 920 done 0 failed | 25 in flight, oldest 16s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
............................................................... [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
........................................................................ [ 56%]
..............................[contention-diag] +121s soak 30p/158t rss 7.5G pss 6.9G swap 1.0G majflt 754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.7G, 2 descendant rss 0.1G pss 0.1G | host avail 36.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 37.71 | cgroup 7.2G/max oom_kill 0 | free scratch 316.9G/45466705i tmp 28.3G/998089i workspace 316.9G/45466705i | scratch used 0.0G in 3425 entries | repeat-01 collected 26/26 workers (60626 items) tests 1238 done 0 failed | 26 in flight, oldest 31s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.......................................... [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 69%]
.........................................................[contention-diag] +137s soak 30p/166t rss 7.7G pss 7.1G swap 1.0G majflt 813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.9G, 2 descendant rss 0.1G pss 0.1G | host avail 36.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 38.84 | cgroup 7.4G/max oom_kill 0 | free scratch 316.8G/45465897i tmp 28.3G/998089i workspace 316.8G/45465897i | repeat-01 collected 26/26 workers (60626 items) tests 1558 done 0 failed | 26 in flight, oldest 47s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
............... [ 73%]
........................................................................ [ 76%]
........................................................................ [ 79%]
........................................................................ [ 83%]
.........................[contention-diag] +152s soak 30p/172t rss 7.8G pss 7.2G swap 1.0G majflt 882 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 7.1G, 2 descendant rss 0.0G pss 0.0G | host avail 35.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.2 cpu 31.5 | cgroup 7.6G/max oom_kill 0 | free scratch 316.8G/45465208i tmp 28.3G/998089i workspace 316.8G/45465208i | repeat-01 collected 26/26 workers (60626 items) tests 1815 done 0 failed | 26 in flight, oldest 58s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
............................................... [ 86%]
......................................................................[contention-diag] +167s soak 33p/190t rss 8.0G pss 7.4G swap 1.0G majflt 887 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.3G, 5 descendant rss 0.1G pss 0.0G | host avail 35.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 24.79 | cgroup 7.8G/max oom_kill 0 | free scratch 316.8G/45464760i tmp 28.3G/998089i workspace 316.8G/45464760i | repeat-01 collected 26/26 workers (60626 items) tests 1941 done 0 failed | 26 in flight, oldest 74s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
.. [ 89%]
........................................................................ [ 93%]
........................................................................ [ 96%]
..................[contention-diag] +182s soak 34p/219t rss 8.2G pss 7.6G swap 1.0G majflt 887 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.4G, 6 descendant rss 0.1G pss 0.1G | host avail 35.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 34.04 | cgroup 8.0G/max oom_kill 0 | free scratch 316.8G/45464188i tmp 28.3G/998089i workspace 316.8G/45464188i | repeat-01 collected 26/26 workers (60626 items) tests 2099 done 0 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................... [ 99%]
........................................................................ [103%]
........................................................................ [106%]
........................................................................ [109%]
................................................[contention-diag] +198s soak 38p/212t rss 8.5G pss 7.9G swap 1.0G majflt 901 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.5G, 10 descendant rss 0.3G pss 0.2G | host avail 34.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 33.49 | cgroup 8.2G/max oom_kill 0 | free scratch 316.8G/45463559i tmp 28.3G/998089i workspace 316.8G/45463559i | repeat-01 collected 26/26 workers (60626 items) tests 2413 done 0 failed | 26 in flight, oldest 84s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................ [113%]
........................................................................ [116%]
...................................................[contention-diag] +213s soak 32p/199t rss 8.6G pss 8.0G swap 1.0G majflt 918 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.2G pss 7.6G, 4 descendant rss 0.2G pss 0.2G | host avail 35.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 28.52 | cgroup 8.3G/max oom_kill 0 | free scratch 316.8G/45463154i tmp 28.3G/998089i workspace 316.8G/45463154i | repeat-01 collected 26/26 workers (60626 items) tests 2570 done 0 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................... [119%]
........................................................................ [123%]
........................................................................ [126%]
..[contention-diag] +228s soak 35p/211t rss 8.8G pss 8.1G swap 1.0G majflt 953 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 7 descendant rss 0.2G pss 0.2G | host avail 34.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.22 | cgroup 8.4G/max oom_kill 0 | free scratch 316.8G/45462677i tmp 28.3G/998089i workspace 316.8G/45462677i | repeat-01 collected 26/26 workers (60626 items) tests 2729 done 0 failed | 26 in flight, oldest 114s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................................... [129%]
......[contention-diag] +243s soak 35p/225t rss 8.8G pss 8.1G swap 0.9G majflt 970 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 7 descendant rss 0.2G pss 0.1G | host avail 33.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.22 | cgroup 8.5G/max oom_kill 0 | free scratch 316.8G/45462408i tmp 28.3G/998089i workspace 316.8G/45462408i | scratch used 0.1G in 7726 entries | repeat-01 collected 26/26 workers (60626 items) tests 2808 done 0 failed | 26 in flight, oldest 129s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................................. [133%]
........................................................................ [136%]
........................................................................ [139%]
.....................................[contention-diag] +259s soak 38p/226t rss 9.1G pss 8.4G swap 1.0G majflt 1001 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 10 descendant rss 0.4G pss 0.3G | host avail 34.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 31.83 | cgroup 8.7G/max oom_kill 0 | free scratch 316.8G/45461710i tmp 28.3G/998089i workspace 316.8G/45461710i | repeat-01 collected 26/26 workers (60626 items) tests 3052 done 0 failed | 26 in flight, oldest 145s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [143%]
........................................................................ [146%]
............................................[contention-diag] +274s soak 33p/225t rss 8.9G pss 8.2G swap 0.9G majflt 1025 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.0G, 5 descendant rss 0.1G pss 0.0G | host avail 35.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 28.73 | cgroup 8.6G/max oom_kill 0 | free scratch 316.8G/45461266i tmp 28.3G/998089i workspace 316.8G/45461266i | repeat-01 collected 26/26 workers (60626 items) tests 3212 done 0 failed | 26 in flight, oldest 160s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................[contention-diag] +289s soak 33p/242t rss 8.9G pss 8.3G swap 0.9G majflt 1025 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 36.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.51 cpu 28.29 | cgroup 8.7G/max oom_kill 0 | free scratch 316.8G/45460760i tmp 28.3G/998087i workspace 316.8G/45460760i | repeat-01 collected 26/26 workers (60626 items) tests 3231 done 0 failed | 26 in flight, oldest 175s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......... [149%]
...........[contention-diag] +304s soak 33p/259t rss 9.0G pss 8.4G swap 0.9G majflt 1025 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 5 descendant rss 0.1G pss 0.0G | host avail 36.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 27.96 | cgroup 8.7G/max oom_kill 0 | free scratch 316.8G/45460621i tmp 28.3G/998089i workspace 316.8G/45460621i | repeat-01 collected 26/26 workers (60626 items) tests 3251 done 0 failed | 26 in flight, oldest 190s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................. [152%]
.......................[contention-diag] +320s soak 37p/256t rss 9.3G pss 8.6G swap 1.0G majflt 1026 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 9 descendant rss 0.3G pss 0.2G | host avail 35.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 33.26 | cgroup 9.0G/max oom_kill 0 | free scratch 316.8G/45460268i tmp 28.3G/998089i workspace 316.8G/45460268i | repeat-01 collected 26/26 workers (60626 items) tests 3327 done 0 failed | 26 in flight, oldest 206s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................. [156%]
........................................................................ [159%]
.....................................[contention-diag] +335s soak 34p/231t rss 9.2G pss 8.5G swap 0.9G majflt 1029 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 34.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.36 | cgroup 8.9G/max oom_kill 0 | free scratch 316.8G/45459816i tmp 28.3G/998089i workspace 316.8G/45459816i | repeat-01 collected 26/26 workers (60626 items) tests 3485 done 0 failed | 26 in flight, oldest 221s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................... [162%]
........................................................................ [166%]
............................[contention-diag] +350s soak 33p/247t rss 9.2G pss 8.6G swap 0.9G majflt 1032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 34.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.05 | cgroup 8.9G/max oom_kill 0 | free scratch 316.8G/45459376i tmp 28.3G/998089i workspace 316.8G/45459376i | repeat-01 collected 26/26 workers (60626 items) tests 3612 done 0 failed | 26 in flight, oldest 236s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............[contention-diag] +365s soak 35p/251t rss 9.4G pss 8.7G swap 0.9G majflt 1032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 7 descendant rss 0.1G pss 0.1G | host avail 33.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.36 | cgroup 9.1G/max oom_kill 0 | free scratch 316.8G/45459209i tmp 28.3G/998089i workspace 316.8G/45459209i | scratch used 0.1G in 10509 entries | repeat-01 collected 26/26 workers (60626 items) tests 3638 done 0 failed | 26 in flight, oldest 251s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................... [169%]
........................................................................ [172%]
..................[contention-diag] +381s soak 40p/263t rss 9.6G pss 8.8G swap 1.0G majflt 1032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 12 descendant rss 0.3G pss 0.2G | host avail 33.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 22.63 | cgroup 9.2G/max oom_kill 0 | free scratch 316.8G/45458831i tmp 28.3G/998089i workspace 316.8G/45458831i | repeat-01 collected 26/26 workers (60626 items) tests 3759 done 0 failed | 26 in flight, oldest 267s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...........................................[contention-diag] +396s soak 41p/276t rss 9.6G pss 8.8G swap 1.0G majflt 1032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 13 descendant rss 0.2G pss 0.1G | host avail 34.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.01 cpu 23.25 | cgroup 9.2G/max oom_kill 0 | free scratch 316.8G/45458610i tmp 28.3G/998087i workspace 316.8G/45458610i | repeat-01 collected 26/26 workers (60626 items) tests 3804 done 0 failed | 26 in flight, oldest 282s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [176%]
........................................................................ [179%]
....................................................[contention-diag] +411s soak 38p/264t rss 9.5G pss 8.8G swap 0.9G majflt 1032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.6G, 10 descendant rss 0.1G pss 0.0G | host avail 34.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.63 cpu 28.18 | cgroup 9.2G/max oom_kill 0 | free scratch 316.8G/45458214i tmp 28.3G/998087i workspace 316.8G/45458214i | repeat-01 collected 26/26 workers (60626 items) tests 3939 done 0 failed | 26 in flight, oldest 297s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................... [182%]
.................................................................[contention-diag] +426s soak 43p/295t rss 9.7G pss 9.0G swap 0.9G majflt 1032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 15 descendant rss 0.3G pss 0.2G | host avail 35.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.93 cpu 26.14 | cgroup 9.3G/max oom_kill 0 | free scratch 316.8G/45457968i tmp 28.3G/998087i workspace 316.8G/45457968i | repeat-01 collected 26/26 workers (60626 items) tests 4022 done 0 failed | 26 in flight, oldest 313s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....... [186%]
........................................................................ [189%]
...[contention-diag] +442s soak 41p/246t rss 9.7G pss 9.0G swap 0.9G majflt 1040 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.7G, 13 descendant rss 0.2G pss 0.1G | host avail 34.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.31 cpu 25.31 | cgroup 9.4G/max oom_kill 0 | free scratch 316.8G/45457662i tmp 28.3G/998087i workspace 316.8G/45457662i | repeat-01 collected 26/26 workers (60626 items) tests 4103 done 0 failed | 26 in flight, oldest 328s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................................... [192%]
.......................................................[contention-diag] +457s soak 36p/259t rss 9.7G pss 9.0G swap 0.9G majflt 1081 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 8 descendant rss 0.2G pss 0.1G | host avail 35.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.08 cpu 26.89 | cgroup 9.4G/max oom_kill 0 | free scratch 316.8G/45457291i tmp 28.3G/998087i workspace 316.8G/45457291i | repeat-01 collected 26/26 workers (60626 items) tests 4230 done 0 failed | 26 in flight, oldest 343s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................. [196%]
...............[contention-diag] +472s soak 35p/288t rss 9.8G pss 9.1G swap 0.9G majflt 1094 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.8G, 7 descendant rss 0.2G pss 0.1G | host avail 34.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 22.86 | cgroup 9.5G/max oom_kill 0 | free scratch 316.8G/45457139i tmp 28.3G/998087i workspace 316.8G/45457139i | repeat-01 collected 26/26 workers (60626 items) tests 4262 done 0 failed | 26 in flight, oldest 358s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.....F[contention-failure] call tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab6c1b1640>

    async def test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
        async with AcePage(initial_tab="agents", size=(160, 40)) as page:
            await wait_for_startup(page)
            app = page.app
            _wire_corpus(app, ModelCorpus(_history()))
            note_inbox_applied_for_archive(app, load_state=complete_load())
            open_agents_archive_view(app)
            await _wait_for_rows(page)
    
            await page.press("J")
            pulse = app.query_one("#archive-pulse", ArchivePulse)
            assert pulse.has_class("-selected")
            assert app._agents_archive_view.archive.focused_section == ARCHIVE_SECTION_PULSE
            await page.pause()
            await page.press("enter")
>           await page.wait_for(
                lambda _s: app._agents_archive_view.active_view == AGENTS_VIEW_INBOX,
                timeout_message=lambda: (
                    "wait_for() timed out waiting for Inbox after pulse Enter —"
                    f" active_view={app._agents_archive_view.active_view!r}"
                    f" focused_section={app._agents_archive_view.archive.focused_section!r}"
                    f" pulse_selected={pulse.has_class('-selected')}"
                ),
            )

tests/ace/tui/test_agent_archive_column_app.py:218: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fab6c67ec00>

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
E               AssertionError: wait_for() timed out waiting for Inbox after pulse Enter — active_view='archive' focused_section='pulse' pulse_selected=True

src/sase/ace/testing/wait.py:64: As
................................................... [199%]
....................................................[contention-diag] +488s soak 30p/247t rss 9.8G pss 9.1G swap 0.9G majflt 1095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.1G pss 0.1G | host avail 33.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 24.33 | cgroup 9.5G/max oom_kill 0 | free scratch 316.8G/45456762i tmp 28.3G/998087i workspace 316.8G/45456762i | scratch used 0.1G in 12947 entries | repeat-01 collected 26/26 workers (60626 items) tests 4367 done 1 failed | 26 in flight, oldest 374s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................... [202%]
.................................[contention-diag] +503s soak 29p/252t rss 9.8G pss 9.1G swap 0.9G majflt 1095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 1 descendant rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.86 cpu 23.43 | cgroup 9.5G/max oom_kill 0 | free scratch 316.8G/45456489i tmp 28.3G/998087i workspace 316.8G/45456489i | repeat-01 collected 26/26 workers (60626 items) tests 4421 done 1 failed | 26 in flight, oldest 389s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...............................[contention-diag] +518s soak 28p/241t rss 9.8G pss 9.1G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G | host avail 34.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 25.34 | cgroup 9.5G/max oom_kill 0 | free scratch 316.8G/45456321i tmp 28.3G/998087i workspace 316.8G/45456321i | repeat-01 collected 26/26 workers (60626 items) tests 4455 done 1 failed | 26 in flight, oldest 51s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
........ [206%]
.....................................[contention-diag] +534s soak 29p/235t rss 9.8G pss 9.2G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.45 cpu 28.83 | cgroup 9.6G/max oom_kill 0 | free scratch 316.8G/45456082i tmp 28.3G/998087i workspace 316.8G/45456082i | repeat-01 collected 26/26 workers (60626 items) tests 4500 done 1 failed | 26 in flight, oldest 66s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...........................[contention-diag] +549s soak 30p/229t rss 10.0G pss 9.3G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 34.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.52 cpu 29.6 | cgroup 9.7G/max oom_kill 0 | free scratch 316.8G/45455888i tmp 28.3G/998087i workspace 316.8G/45455888i | repeat-01 collected 26/26 workers (60626 items) tests 4524 done 1 failed | 26 in flight, oldest 81s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
........ [209%]
........................................................................ [212%]
.[contention-diag] +564s soak 29p/240t rss 9.9G pss 9.3G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 1 descendant rss 0.1G pss 0.1G | host avail 33.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 16.19 | cgroup 9.7G/max oom_kill 0 | free scratch 316.1G/45453698i tmp 28.3G/998087i workspace 316.1G/45453698i | repeat-01 collected 26/26 workers (60626 items) tests 4608 done 1 failed | 26 in flight, oldest 66s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_from_fresh_main_lands_on_record_then_main
................................................[contention-diag] +579s soak 28p/235t rss 9.9G pss 9.3G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 33.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.47 cpu 22.98 | cgroup 9.7G/max oom_kill 0 | free scratch 316.0G/45453329i tmp 28.3G/998087i workspace 316.0G/45453329i | repeat-01 collected 26/26 workers (60626 items) tests 4656 done 1 failed | 26 in flight, oldest 74s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_escape_restores_the_prior_committed_query
....................... [216%]
....[contention-diag] +595s soak 29p/249t rss 10.0G pss 9.3G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.1G, 1 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.16 cpu 25.16 | cgroup 9.7G/max oom_kill 0 | free scratch 316.0G/45453174i tmp 28.3G/998087i workspace 316.0G/45453174i | repeat-01 collected 26/26 workers (60626 items) tests 4682 done 1 failed | 26 in flight, oldest 81s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
......F[contention-failure] call tests/ace/tui/test_artifacts_beads_filtering.py::test_hide_closed_default_is_visible_and_clearable: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw22/test_hide_closed_default_is_vi0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1642467560>

    async def test_hide_closed_default_is_visible_and_clearable(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        value = snapshot(tmp_path, project=None)
        monkeypatch.setattr(
            beads_pane,
            "load_beads_snapshot",
            lambda _project, **_kwargs: value,
        )
    
        async with AcePage(initial_tab="patches") as page:
            await page.press(page.artifacts_digit("beads"))
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is value)
            assert pane.filters.excluded_statuses == ("closed",)
            bar = pane.query_one(BeadFilterBar)
            assert bar.display
            display = bar.query_one("#bead-filter-display", Static)
            await page.wait_for(lambda _state: "-status:closed" in display.render().plain)
    
            assert pane.select_entry_target(
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "epic", "alpha-1"))
            )
            pane.set_selected_epic_expanded(True)
            assert (
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "phase", "alpha-1.1"))
                not in pane.entry_targets()
            )
    
            await page.press("/")
>           assert bar._editing  # type: ignore[attr-defined]
            ^^^^^^^^^^^^^^^^^^^
E           AssertionError: assert False
E            +  where False = BeadFilterBar(id='bead-filter-bar', classes='persistent')._editing

tests/ace/tui/test_artifacts_beads_filtering.py:497: AssertionError
.......................[contention-diag] +610s soak 29p/235t rss 10.1G pss 9.4G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 30.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.44 cpu 22.46 | cgroup 9.8G/max oom_kill 0 | free scratch 316.0G/45453014i tmp 28.3G/998087i workspace 316.0G/45453014i | scratch used 0.1G in 14706 entries | repeat-01 collected 26/26 workers (60626 items) tests 4709 done 2 failed | 25 in flight, oldest 57s gw18 tests/ace/tui/command_line/test_policy_io.py::test_poll_once_ticks_submitting_without_log_read
...................................... [219%]
.....[contention-diag] +625s soak 29p/250t rss 10.1G pss 9.4G swap 0.9G majflt 1117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.89 cpu 21.03 | cgroup 9.9G/max oom_kill 0 | free scratch 316.0G/45452769i tmp 28.3G/998085i workspace 316.0G/45452769i | repeat-01 collected 26/26 workers (60626 items) tests 4754 done 2 failed | 26 in flight, oldest 55s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_K_warns_when_finished_and_confirms_when_running
..................................[contention-diag] +641s soak 28p/253t rss 10.1G pss 9.4G swap 0.9G majflt 1121 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G | host avail 29.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.86 cpu 20.25 | cgroup 9.9G/max oom_kill 0 | free scratch 316.0G/45452553i tmp 28.3G/998087i workspace 316.0G/45452553i | repeat-01 collected 26/26 workers (60626 items) tests 4789 done 2 failed | 25 in flight, oldest 64s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
................................. [222%]
..................[contention-diag] +656s soak 29p/232t rss 10.2G pss 9.5G swap 0.9G majflt 1133 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 20.01 | cgroup 10.0G/max oom_kill 0 | free scratch 315.7G/45452308i tmp 28.3G/998087i workspace 315.7G/45452308i | repeat-01 collected 26/26 workers (60626 items) tests 4841 done 2 failed | 26 in flight, oldest 60s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
..........................[contention-diag] +671s soak 28p/223t rss 10.1G pss 9.5G swap 0.9G majflt 1136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G | host avail 32.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.23 cpu 24.48 | cgroup 10.0G/max oom_kill 0 | free scratch 314.5G/45452110i tmp 28.3G/998087i workspace 314.5G/45452110i | repeat-01 collected 26/26 workers (60626 items) tests 4868 done 2 failed | 26 in flight, oldest 75s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...............[contention-diag] +687s soak 29p/250t rss 10.3G pss 9.6G swap 0.9G majflt 1136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.3G, 1 descendant rss 0.1G pss 0.1G | host avail 31.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 23.44 | cgroup 10.2G/max oom_kill 0 | free scratch 314.5G/45451942i tmp 28.3G/998087i workspace 314.5G/45451942i | repeat-01 collected 26/26 workers (60626 items) tests 4882 done 2 failed | 26 in flight, oldest 60s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
............. [226%]
[contention-diag] +702s soak 28p/230t rss 10.2G pss 9.5G swap 0.9G majflt 1137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 33.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.9 cpu 23.82 | cgroup 10.2G/max oom_kill 0 | free scratch 314.3G/45451756i tmp 28.3G/998087i workspace 314.3G/45451756i | repeat-01 collected 26/26 workers (60626 items) tests 4895 done 2 failed | 26 in flight, oldest 56s gw9 tests/ace/tui/test_agent_collapsed_panel_kill.py::test_confirming_last_panel_member_preserves_neighbors_and_valid_focus
..................................................[contention-diag] +717s soak 30p/225t rss 10.3G pss 9.6G swap 0.9G majflt 1137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 2 descendant rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 27.22 | cgroup 10.1G/max oom_kill 0 | free scratch 314.3G/45451573i tmp 28.3G/998087i workspace 314.3G/45451573i | repeat-01 collected 26/26 workers (60626 items) tests 4944 done 2 failed | 26 in flight, oldest 52s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_configured_toggle_key_appears_in_rail_and_rebinding_changes_it
...................... [229%]
.......[contention-diag] +732s soak 30p/246t rss 10.4G pss 9.7G swap 0.9G majflt 1137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 2 descendant rss 0.1G pss 0.1G | host avail 32.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.87 cpu 25.49 | cgroup 10.2G/max oom_kill 0 | free scratch 314.3G/45451374i tmp 28.3G/998087i workspace 314.3G/45451374i | scratch used 0.1G in 16283 entries | repeat-01 collected 26/26 workers (60626 items) tests 4974 done 2 failed | 26 in flight, oldest 56s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_panel_action_override_takes_effect_in_mounted_pilot
................................................................. [232%]
.....................................[contention-diag] +749s soak 28p/224t rss 10.3G pss 9.6G swap 0.9G majflt 1137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 31.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 23.48 | cgroup 10.2G/max oom_kill 0 | free scratch 314.3G/45450993i tmp 28.3G/998087i workspace 314.3G/45450993i | repeat-01 collected 26/26 workers (60626 items) tests 5066 done 2 failed | 25 in flight, oldest 49s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_labels_and_description
................................... [236%]
........................................................................ [239%]
........................................................................ [242%]
................................................[contention-diag] +764s soak 28p/239t rss 10.3G pss 9.7G swap 0.9G majflt 1137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G | host avail 30.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.51 cpu 22.83 | cgroup 10.3G/max oom_kill 0 | free scratch 314.3G/45450385i tmp 28.3G/998087i workspace 314.3G/45450385i | repeat-01 collected 26/26 workers (60626 items) tests 5296 done 2 failed | 26 in flight, oldest 60s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
........................ [246%]
........................................................................ [249%]
........................................................................ [252%]
.............[contention-diag] +780s soak 29p/234t rss 10.4G pss 9.7G swap 0.9G majflt 1139 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 1 descendant rss 0.0G pss 0.0G | host avail 32.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.6 cpu 25.95 | cgroup 10.4G/max oom_kill 0 | free scratch 314.3G/45449767i tmp 28.3G/998087i workspace 314.3G/45449767i | repeat-01 collected 26/26 workers (60626 items) tests 5482 done 2 failed | 26 in flight, oldest 64s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................................... [256%]
..............................................................[contention-diag] +795s soak 30p/246t rss 10.5G pss 9.8G swap 0.9G majflt 1147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 33.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 0.85 cpu 23.99 | cgroup 10.6G/max oom_kill 0 | free scratch 314.3G/45449412i tmp 28.3G/998087i workspace 314.3G/45449412i | repeat-01 collected 26/26 workers (60626 items) tests 5604 done 2 failed | 26 in flight, oldest 80s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.......... [259%]
.....[contention-diag] +810s soak 29p/242t rss 10.4G pss 9.7G swap 0.9G majflt 1147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 32.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.84 cpu 24.08 | cgroup 10.4G/max oom_kill 0 | free scratch 314.3G/45449213i tmp 28.3G/998087i workspace 314.3G/45449213i | repeat-01 collected 26/26 workers (60626 items) tests 5618 done 2 failed | 26 in flight, oldest 95s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................[contention-diag] +826s soak 28p/277t rss 10.5G pss 9.8G swap 0.9G majflt 1147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G | host avail 33.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 25.64 | cgroup 10.4G/max oom_kill 0 | free scratch 314.3G/45449057i tmp 28.3G/998087i workspace 314.3G/45449057i | repeat-01 collected 26/26 workers (60626 items) tests 5645 done 2 failed | 26 in flight, oldest 110s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................................[contention-diag] +841s soak 30p/264t rss 10.5G pss 9.8G swap 0.9G majflt 1148 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 2 descendant rss 0.0G pss 0.0G | host avail 33.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.45 cpu 27.28 | cgroup 10.5G/max oom_kill 0 | free scratch 314.3G/45448816i tmp 28.3G/998087i workspace 314.3G/45448816i | repeat-01 collected 26/26 workers (60626 items) tests 5673 done 2 failed | 26 in flight, oldest 126s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........... [262%]
........................................................................ [266%]
.............[contention-diag] +856s soak 30p/237t rss 10.6G pss 9.9G swap 0.9G majflt 1149 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 2 descendant rss 0.1G pss 0.1G | host avail 33.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.75 cpu 23.52 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45448481i tmp 28.3G/998087i workspace 314.3G/45448481i | scratch used 0.1G in 19164 entries | repeat-01 collected 26/26 workers (60626 items) tests 5767 done 2 failed | 25 in flight, oldest 141s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................................................... [269%]
............[contention-diag] +872s soak 28p/227t rss 10.6G pss 9.9G swap 0.9G majflt 1148 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G | host avail 32.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.35/0.2 io 2.7 cpu 24.17 | cgroup 10.5G/max oom_kill 0 | free scratch 314.3G/45448147i tmp 28.3G/998087i workspace 314.3G/45448147i | repeat-01 collected 26/26 workers (60626 items) tests 5841 done 2 failed | 26 in flight, oldest 45s gw3 tests/ace/tui/test_agent_cleanup_panel_clan_members_e2e.py::test_cleanup_panel_kill_and_dismiss_includes_clan_members
............................................................ [272%]
...................................................................[contention-diag] +887s soak 28p/242t rss 10.6G pss 9.9G swap 0.9G majflt 1148 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G | host avail 31.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.03 io 1.48 cpu 22.0 | cgroup 10.5G/max oom_kill 0 | free scratch 314.3G/45447872i tmp 28.3G/998087i workspace 314.3G/45447872i | repeat-01 collected 26/26 workers (60626 items) tests 5969 done 2 failed | 26 in flight, oldest 50s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
..... [276%]
........................................................................ [279%]
........................................................................ [282%]
......................[contention-diag] +902s soak 30p/247t rss 10.7G pss 10.0G swap 0.9G majflt 1152 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 2 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.24/0.23 io 2.18 cpu 29.33 | cgroup 10.6G/max oom_kill 0 | free scratch 314.3G/45447351i tmp 28.3G/998087i workspace 314.3G/45447351i | repeat-01 collected 26/26 workers (60626 items) tests 6142 done 2 failed | 26 in flight, oldest 65s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
.................................................. [286%]
........................................................................ [289%]
..............................................................[contention-diag] +918s soak 28p/208t rss 10.7G pss 10.0G swap 0.9G majflt 1152 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 35.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 2.99 cpu 31.6 | cgroup 10.6G/max oom_kill 0 | free scratch 314.3G/45446788i tmp 28.3G/998087i workspace 314.3G/45446788i | repeat-01 collected 26/26 workers (60626 items) tests 6324 done 2 failed | 26 in flight, oldest 57s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
.......... [292%]
........................................................................ [295%]
................[contention-diag] +933s soak 28p/232t rss 10.7G pss 10.0G swap 0.9G majflt 1153 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 35.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.8 cpu 29.52 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45446464i tmp 28.3G/998087i workspace 314.3G/45446464i | repeat-01 collected 26/26 workers (60626 items) tests 6424 done 2 failed | 26 in flight, oldest 72s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
........................................................ [299%]
......[contention-diag] +948s soak 30p/242t rss 10.7G pss 10.0G swap 0.9G majflt 1153 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G, 2 descendant rss 0.0G pss 0.0G | host avail 33.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 24.0 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45446227i tmp 28.3G/998087i workspace 314.3G/45446227i | repeat-01 collected 26/26 workers (60626 items) tests 6472 done 2 failed | 25 in flight, oldest 50s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_toggle_install_mark_updates_row_and_hints
.................................................................. [302%]
........................................................................ [305%]
....[contention-diag] +964s soak 29p/229t rss 10.8G pss 10.1G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 34.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 26.36 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45445785i tmp 28.3G/998087i workspace 314.3G/45445785i | repeat-01 collected 26/26 workers (60626 items) tests 6625 done 2 failed | 26 in flight, oldest 58s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
.................................................[contention-diag] +979s soak 29p/227t rss 10.8G pss 10.1G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 33.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 23.07 | cgroup 10.8G/max oom_kill 0 | free scratch 314.8G/45445557i tmp 28.3G/998087i workspace 314.8G/45445557i | scratch used 0.1G in 22181 entries | repeat-01 collected 26/26 workers (60626 items) tests 6672 done 2 failed | 26 in flight, oldest 51s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
................... [309%]
.......................................................[contention-diag] +994s soak 29p/243t rss 10.8G pss 10.1G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 25.25 | cgroup 10.8G/max oom_kill 0 | free scratch 314.8G/45445276i tmp 28.3G/998087i workspace 314.8G/45445276i | repeat-01 collected 26/26 workers (60626 items) tests 6751 done 2 failed | 25 in flight, oldest 47s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
................. [312%]
................[contention-diag] +1010s soak 30p/231t rss 10.9G pss 10.2G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.0G pss 0.0G | host avail 31.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.3 cpu 22.02 | cgroup 10.9G/max oom_kill 0 | free scratch 314.7G/45445090i tmp 28.3G/998087i workspace 314.7G/45445090i | repeat-01 collected 26/26 workers (60626 items) tests 6783 done 2 failed | 26 in flight, oldest 62s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........................................................ [315%]
........................................................................ [319%]
.....[contention-diag] +1025s soak 30p/220t rss 10.9G pss 10.2G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.0G pss 0.0G | host avail 31.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.72/0.65 io 0.3 cpu 22.76 | cgroup 10.7G/max oom_kill 0 | free scratch 314.7G/45444724i tmp 28.3G/998087i workspace 314.7G/45444724i | repeat-01 collected 26/26 workers (60626 items) tests 6914 done 2 failed | 26 in flight, oldest 54s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_f_opens_files_below_and_keeps_focus
................................................................... [322%]
........................................................................ [325%]
.........................[contention-diag] +1040s soak 29p/216t rss 10.9G pss 10.2G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.14/0.13 io 0.89 cpu 26.82 | cgroup 10.7G/max oom_kill 0 | free scratch 314.7G/45444230i tmp 28.3G/998087i workspace 314.7G/45444230i | repeat-01 collected 26/26 workers (60626 items) tests 7079 done 2 failed | 26 in flight, oldest 42s gw5 tests/ace/tui/test_artifacts_plans_filtering.py::test_committing_plan_query_updates_idle_bar
..............................[contention-diag] +1056s soak 30p/224t rss 11.0G pss 10.2G swap 0.9G majflt 1193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.1G pss 0.0G | host avail 29.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.36 cpu 20.56 | cgroup 10.7G/max oom_kill 0 | free scratch 314.5G/45444007i tmp 28.3G/998087i workspace 314.5G/45444007i | repeat-01 collected 26/26 workers (60626 items) tests 7108 done 2 failed | 26 in flight, oldest 47s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................. [329%]
........................................................................ [332%]
...........[contention-diag] +1071s soak 29p/235t rss 11.0G pss 10.3G swap 0.9G majflt 1176 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 32.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 20.53 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45443756i tmp 28.3G/998087i workspace 314.3G/45443756i | repeat-01 collected 26/26 workers (60626 items) tests 7187 done 2 failed | 25 in flight, oldest 62s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
............................................................. [335%]
.............................................................[contention-diag] +1086s soak 29p/235t rss 11.0G pss 10.3G swap 0.9G majflt 1177 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 32.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 21.5 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45443342i tmp 28.3G/998087i workspace 314.3G/45443342i | repeat-01 collected 26/26 workers (60626 items) tests 7332 done 2 failed | 26 in flight, oldest 77s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
........... [339%]
........................................................................ [342%]
..............................................[contention-diag] +1101s soak 28p/206t rss 11.0G pss 10.3G swap 0.9G majflt 1177 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G | host avail 34.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 21.0 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45442975i tmp 28.3G/998087i workspace 314.3G/45442975i | scratch used 0.2G in 24748 entries | repeat-01 collected 26/26 workers (60626 items) tests 7455 done 2 failed | 26 in flight, oldest 46s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......................... [345%]
........................................................................ [349%]
.................................[contention-diag] +1117s soak 28p/262t rss 11.0G pss 10.3G swap 0.9G majflt 1179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G | host avail 33.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.23 cpu 25.0 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45442580i tmp 28.3G/998087i workspace 314.3G/45442580i | repeat-01 collected 26/26 workers (60626 items) tests 7592 done 2 failed | 26 in flight, oldest 61s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
....................................... [352%]
........................................................................ [355%]
...............[contention-diag] +1132s soak 38p/267t rss 11.1G pss 10.3G swap 0.9G majflt 1179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 32.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.86 cpu 23.8 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45442131i tmp 28.3G/998087i workspace 314.3G/45442131i | repeat-01 collected 26/26 workers (60626 items) tests 7719 done 2 failed | 26 in flight, oldest 77s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
....................[contention-diag] +1148s soak 38p/264t rss 11.1G pss 10.3G swap 0.9G majflt 1179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 32.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.3 cpu 21.6 | cgroup 10.7G/max oom_kill 0 | free scratch 314.3G/45441992i tmp 28.3G/998087i workspace 314.3G/45441992i | repeat-01 collected 26/26 workers (60626 items) tests 7739 done 2 failed | 26 in flight, oldest 92s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......[contention-diag] +1163s soak 38p/285t rss 11.1G pss 10.3G swap 0.9G majflt 1179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 32.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.91 cpu 25.87 | cgroup 10.8G/max oom_kill 0 | free scratch 314.3G/45441890i tmp 28.3G/998087i workspace 314.3G/45441890i | repeat-01 collected 26/26 workers (60626 items) tests 7744 done 2 failed | 26 in flight, oldest 107s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.............................. [359%]
.........................[contention-diag] +1178s soak 38p/251t rss 11.1G pss 10.3G swap 0.9G majflt 1179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 32.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.19 cpu 24.72 | cgroup 10.8G/max oom_kill 0 | free scratch 314.3G/45441640i tmp 28.3G/998088i workspace 314.3G/45441640i | repeat-01 collected 26/26 workers (60626 items) tests 7798 done 2 failed | 26 in flight, oldest 57s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
...............[contention-diag] +1193s soak 39p/246t rss 11.3G pss 10.5G swap 0.9G majflt 1185 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 11 descendant rss 0.2G pss 0.1G | host avail 31.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.24 cpu 22.25 | cgroup 10.9G/max oom_kill 0 | free scratch 314.3G/45441492i tmp 28.3G/998088i workspace 314.3G/45441492i | repeat-01 collected 26/26 workers (60626 items) tests 7814 done 2 failed | 26 in flight, oldest 73s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
................................ [362%]
.............................................[contention-diag] +1209s soak 38p/258t rss 11.2G pss 10.4G swap 0.9G majflt 1179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 32.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.45 cpu 24.53 | cgroup 10.8G/max oom_kill 0 | free scratch 314.3G/45441213i tmp 28.3G/998088i workspace 314.3G/45441213i | repeat-01 collected 26/26 workers (60626 items) tests 7893 done 2 failed | 26 in flight, oldest 58s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
........................... [365%]
..............................[contention-diag] +1224s soak 38p/258t rss 11.2G pss 10.4G swap 0.9G majflt 1182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 31.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.1 cpu 22.88 | cgroup 10.8G/max oom_kill 0 | free scratch 314.3G/45440926i tmp 28.3G/998088i workspace 314.3G/45440926i | scratch used 0.2G in 26768 entries | repeat-01 collected 26/26 workers (60626 items) tests 7949 done 2 failed | 26 in flight, oldest 54s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
.......................................... [369%]
........................................................................ [372%]
.[contention-diag] +1240s soak 38p/243t rss 11.2G pss 10.4G swap 0.9G majflt 1195 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 30.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.17 cpu 22.9 | cgroup 10.9G/max oom_kill 0 | free scratch 314.3G/45440543i tmp 28.3G/998088i workspace 314.3G/45440543i | repeat-01 collected 26/26 workers (60626 items) tests 8063 done 2 failed | 26 in flight, oldest 70s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
........................................[contention-diag] +1255s soak 28p/231t rss 11.1G pss 10.4G swap 0.9G majflt 1200 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 28.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.22/0.22 io 3.22 cpu 22.8 | cgroup 10.8G/max oom_kill 0 | free scratch 314.3G/45440358i tmp 28.3G/998088i workspace 314.3G/45440358i | repeat-01 collected 26/26 workers (60626 items) tests 8104 done 2 failed | 26 in flight, oldest 44s gw20 tests/ace/tui/test_link_follow_seam.py::test_files_sync_reports_visible_and_missing
............................... [375%]
................................................[contention-diag] +1270s soak 29p/251t rss 11.2G pss 10.4G swap 0.9G majflt 1206 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 27.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.52/0.52 io 3.31 cpu 22.41 | cgroup 10.8G/max oom_kill 0 | free scratch 314.3G/45440088i tmp 28.3G/998088i workspace 314.3G/45440088i | repeat-01 collected 26/26 workers (60626 items) tests 8184 done 2 failed | 26 in flight, oldest 58s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_after_tools_returns_to_main_then_tools
........................ [379%]
........................................................................ [382%]
...................................[contention-diag] +1286s soak 28p/239t rss 11.2G pss 10.4G swap 0.9G majflt 1205 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 28.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 4.04 cpu 21.94 | cgroup 10.9G/max oom_kill 0 | free scratch 314.2G/45439697i tmp 28.3G/998088i workspace 314.2G/45439697i | repeat-01 collected 26/26 workers (60626 items) tests 8313 done 2 failed | 26 in flight, oldest 62s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
..................................... [385%]
........................................................................ [389%]
........................................................................ [392%]
.............[contention-diag] +1301s soak 28p/239t rss 11.2G pss 10.4G swap 0.9G majflt 1227 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 28.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 3.0 cpu 19.78 | cgroup 10.9G/max oom_kill 0 | free scratch 313.9G/45439171i tmp 28.3G/998088i workspace 313.9G/45439171i | repeat-01 collected 26/26 workers (60626 items) tests 8499 done 2 failed | 26 in flight, oldest 78s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
........................................................... [395%]
........................................................................ [399%]
........................................................................ [402%]
.................................................................[contention-diag] +1316s soak 28p/238t rss 11.2G pss 10.5G swap 0.9G majflt 1387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 32.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.51 cpu 23.07 | cgroup 10.9G/max oom_kill 0 | free scratch 313.7G/45438517i tmp 28.3G/998088i workspace 313.7G/45438517i | repeat-01 collected 26/26 workers (60626 items) tests 8768 done 2 failed | 26 in flight, oldest 81s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
....... [405%]
........................................................................ [409%]
..........[contention-diag] +1332s soak 28p/216t rss 11.2G pss 10.5G swap 0.9G majflt 1387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 29.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.18 cpu 17.55 | cgroup 11.0G/max oom_kill 0 | free scratch 321.8G/45446374i tmp 28.3G/998088i workspace 321.8G/45446374i | repeat-01 collected 26/26 workers (60626 items) tests 8866 done 2 failed | 26 in flight, oldest 96s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............................................................. [412%]
........................................................[contention-diag] +1347s soak 28p/225t rss 11.3G pss 10.5G swap 0.9G majflt 1387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 31.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.64 cpu 17.6 | cgroup 11.0G/max oom_kill 0 | free scratch 321.8G/45446032i tmp 28.3G/998088i workspace 321.8G/45446032i | scratch used 0.2G in 29784 entries | repeat-01 collected 26/26 workers (60626 items) tests 8982 done 2 failed | 26 in flight, oldest 111s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................ [415%]
..........................................................[contention-diag] +1362s soak 28p/242t rss 11.3G pss 10.5G swap 0.9G majflt 1398 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 31.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.8 cpu 18.76 | cgroup 11.0G/max oom_kill 0 | free scratch 321.8G/45445752i tmp 28.3G/998088i workspace 321.8G/45445752i | repeat-01 collected 26/26 workers (60626 items) tests 9056 done 2 failed | 26 in flight, oldest 127s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.............. [419%]
....................................................................[contention-diag] +1378s soak 28p/244t rss 11.3G pss 10.6G swap 0.9G majflt 1398 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 29.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.12 cpu 22.17 | cgroup 11.1G/max oom_kill 0 | free scratch 321.8G/45445464i tmp 28.3G/998088i workspace 321.8G/45445464i | repeat-01 collected 26/26 workers (60626 items) tests 9127 done 2 failed | 26 in flight, oldest 142s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.... [422%]
........................[contention-diag] +1393s soak 29p/262t rss 11.3G pss 10.6G swap 0.9G majflt 1401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 28.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.6 cpu 13.16 | cgroup 11.1G/max oom_kill 0 | free scratch 321.6G/45444062i tmp 28.3G/998088i workspace 321.6G/45444062i | repeat-01 collected 26/26 workers (60626 items) tests 9165 done 2 failed | 26 in flight, oldest 157s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................[contention-diag] +1408s soak 29p/243t rss 11.4G pss 10.6G swap 0.9G majflt 1416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 29.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.49 cpu 16.11 | cgroup 11.1G/max oom_kill 0 | free scratch 321.5G/45443742i tmp 28.3G/998088i workspace 321.5G/45443742i | repeat-01 collected 26/26 workers (60626 items) tests 9198 done 2 failed | 26 in flight, oldest 173s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............... [425%]
..............................................[contention-diag] +1424s soak 28p/233t rss 11.4G pss 10.6G swap 0.9G majflt 1416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 28.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.63 cpu 17.19 | cgroup 11.2G/max oom_kill 0 | free scratch 321.3G/45443499i tmp 28.3G/998088i workspace 321.3G/45443499i | repeat-01 collected 26/26 workers (60626 items) tests 9261 done 2 failed | 26 in flight, oldest 188s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.......................... [429%]
...............................................[contention-diag] +1439s soak 29p/252t rss 11.4G pss 10.6G swap 0.9G majflt 1426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.54 cpu 21.5 | cgroup 11.2G/max oom_kill 0 | free scratch 321.2G/45443216i tmp 28.3G/998088i workspace 321.2G/45443216i | repeat-01 collected 26/26 workers (60626 items) tests 9333 done 2 failed | 26 in flight, oldest 108s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
....................[contention-diag] +1454s soak 28p/259t rss 11.4G pss 10.6G swap 0.9G majflt 1426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 26.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.62/0.42 io 2.73 cpu 19.43 | cgroup 11.1G/max oom_kill 0 | free scratch 321.1G/45443089i tmp 28.3G/998088i workspace 321.1G/45443089i | repeat-01 collected 26/26 workers (60626 items) tests 9355 done 2 failed | 26 in flight, oldest 123s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..... [432%]
.......................................................[contention-diag] +1470s soak 30p/254t rss 11.4G pss 10.7G swap 1.0G majflt 1496 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 28.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.3/0.17 io 3.7 cpu 18.39 | cgroup 11.2G/max oom_kill 0 | free scratch 321.1G/45442907i tmp 28.3G/998088i workspace 321.1G/45442907i | scratch used 0.2G in 31444 entries | repeat-01 collected 26/26 workers (60626 items) tests 9412 done 2 failed | 26 in flight, oldest 139s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................. [435%]
........................................................................ [438%]
......................[contention-diag] +1485s soak 28p/241t rss 11.3G pss 10.7G swap 1.0G majflt 1457 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 28.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.24/0.21 io 3.65 cpu 21.98 | cgroup 11.2G/max oom_kill 0 | free scratch 321.0G/45442504i tmp 28.3G/998086i workspace 321.0G/45442504i | repeat-01 collected 26/26 workers (60626 items) tests 9523 done 2 failed | 26 in flight, oldest 154s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................................................. [442%]
........................................................................ [445%]
...........................................[contention-diag] +1501s soak 29p/259t rss 11.4G pss 10.7G swap 1.0G majflt 1491 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.27/0.17 io 3.09 cpu 25.62 | cgroup 11.2G/max oom_kill 0 | free scratch 321.0G/45442082i tmp 28.3G/998088i workspace 321.0G/45442082i | repeat-01 collected 26/26 workers (60626 items) tests 9678 done 2 failed | 26 in flight, oldest 170s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................. [448%]
...........................................[contention-diag] +1516s soak 29p/251t rss 11.4G pss 10.7G swap 1.0G majflt 1499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.04 io 1.37 cpu 26.91 | cgroup 11.2G/max oom_kill 0 | free scratch 321.0G/45441812i tmp 28.3G/998089i workspace 321.0G/45441812i | repeat-01 collected 26/26 workers (60626 items) tests 9762 done 2 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...........................[contention-diag] +1531s soak 28p/253t rss 11.4G pss 10.7G swap 1.0G majflt 1500 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.6G | host avail 33.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.42 cpu 25.64 | cgroup 11.3G/max oom_kill 0 | free scratch 321.0G/45441608i tmp 28.3G/998089i workspace 321.0G/45441608i | repeat-01 collected 26/26 workers (60626 items) tests 9790 done 2 failed | 26 in flight, oldest 90s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.. [452%]
.........................[contention-diag] +1547s soak 29p/262t rss 11.4G pss 10.8G swap 1.0G majflt 1509 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 34.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.34 cpu 29.65 | cgroup 11.3G/max oom_kill 0 | free scratch 321.0G/45441405i tmp 28.3G/998089i workspace 321.0G/45441405i | repeat-01 collected 26/26 workers (60626 items) tests 9814 done 2 failed | 26 in flight, oldest 105s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................... [455%]
........................................................................ [458%]
..[contention-diag] +1562s soak 28p/220t rss 11.4G pss 10.8G swap 1.0G majflt 1518 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.6G | host avail 34.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 32.24 | cgroup 11.3G/max oom_kill 0 | free scratch 321.0G/45441026i tmp 28.3G/998089i workspace 321.0G/45441026i | repeat-01 collected 26/26 workers (60626 items) tests 9935 done 2 failed | 26 in flight, oldest 120s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................................... [462%]
................................................................[contention-diag] +1577s soak 28p/231t rss 11.5G pss 10.8G swap 1.0G majflt 1531 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 33.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 32.09 | cgroup 11.3G/max oom_kill 0 | free scratch 321.0G/45440660i tmp 28.3G/998089i workspace 321.0G/45440660i | repeat-01 collected 26/26 workers (60626 items) tests 10072 done 2 failed | 26 in flight, oldest 135s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........ [465%]
.................[contention-diag] +1592s soak 28p/250t rss 11.5G pss 10.8G swap 0.9G majflt 1546 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 32.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.16/0.0 io 0.02 cpu 28.15 | cgroup 11.4G/max oom_kill 0 | free scratch 321.5G/45440520i tmp 28.3G/998089i workspace 321.5G/45440520i | scratch used 0.2G in 33827 entries | repeat-01 collected 26/26 workers (60626 items) tests 10090 done 2 failed | 25 in flight, oldest 151s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................................................... [468%]
..........[contention-diag] +1608s soak 28p/249t rss 11.5G pss 10.8G swap 0.9G majflt 1583 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.7G | host avail 30.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 0.0 cpu 23.0 | cgroup 11.4G/max oom_kill 0 | free scratch 321.4G/45440256i tmp 28.3G/998089i workspace 321.4G/45440256i | repeat-01 collected 26/26 workers (60626 items) tests 10160 done 2 failed | 26 in flight, oldest 166s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.....................[contention-diag] +1623s soak 28p/242t rss 11.5G pss 10.8G swap 0.9G majflt 1583 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.7G | host avail 30.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.69 | cgroup 11.4G/max oom_kill 0 | free scratch 321.2G/45440100i tmp 28.3G/998089i workspace 321.2G/45440100i | repeat-01 collected 26/26 workers (60626 items) tests 10181 done 2 failed | 26 in flight, oldest 182s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................................... [472%]
.............................................................[contention-diag] +1639s soak 29p/251t rss 11.6G pss 10.9G swap 0.9G majflt 1583 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.92 | cgroup 11.5G/max oom_kill 0 | free scratch 321.1G/45439764i tmp 28.3G/998089i workspace 321.1G/45439764i | repeat-01 collected 26/26 workers (60626 items) tests 10283 done 2 failed | 26 in flight, oldest 197s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........... [475%]
........................................................................ [478%]
...................................[contention-diag] +1654s soak 29p/244t rss 11.6G pss 10.9G swap 0.9G majflt 1583 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 24.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.48 | cgroup 11.5G/max oom_kill 0 | free scratch 321.1G/45439459i tmp 28.3G/998089i workspace 321.1G/45439459i | repeat-01 collected 26/26 workers (60626 items) tests 10401 done 2 failed | 26 in flight, oldest 212s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................... [482%]
........................................................................ [485%]
..................................[contention-diag] +1669s soak 30p/239t rss 11.7G pss 11.0G swap 0.9G majflt 1589 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.18 cpu 21.71 | cgroup 11.6G/max oom_kill 0 | free scratch 320.8G/45438586i tmp 28.3G/998089i workspace 320.8G/45438586i | repeat-01 collected 26/26 workers (60626 items) tests 10535 done 2 failed | 24 in flight, oldest 228s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................... [488%]
........................................................................ [492%]
.....................[contention-diag] +1685s soak 28p/257t rss 11.6G pss 10.9G swap 0.9G majflt 1592 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 27.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 25.03 | cgroup 11.5G/max oom_kill 0 | free scratch 320.8G/45437936i tmp 28.3G/998089i workspace 320.8G/45437936i | repeat-01 collected 26/26 workers (60626 items) tests 10676 done 2 failed | 26 in flight, oldest 243s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................... [495%]
.......[contention-diag] +1700s soak 29p/272t rss 11.6G pss 10.9G swap 0.9G majflt 1599 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 27.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 20.69 | cgroup 11.6G/max oom_kill 0 | free scratch 320.7G/45437962i tmp 28.3G/998089i workspace 320.7G/45437962i | repeat-01 collected 26/26 workers (60626 items) tests 10729 done 2 failed | 26 in flight, oldest 258s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................................. [498%]
............................[contention-diag] +1715s soak 28p/273t rss 11.6G pss 10.9G swap 0.9G majflt 1604 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 32.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 28.28 | cgroup 11.6G/max oom_kill 0 | free scratch 320.6G/45437624i tmp 28.3G/998089i workspace 320.6G/45437624i | scratch used 0.2G in 36293 entries | repeat-01 collected 26/26 workers (60626 items) tests 10817 done 2 failed | 26 in flight, oldest 274s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................[contention-diag] +1731s soak 30p/263t rss 11.6G pss 10.9G swap 0.9G majflt 1628 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 32.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 26.97 | cgroup 11.6G/max oom_kill 0 | free scratch 320.6G/45437322i tmp 28.3G/998089i workspace 320.6G/45437322i | repeat-01 collected 26/26 workers (60626 items) tests 10860 done 2 failed | 26 in flight, oldest 289s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......... [502%]
........................................................................ [505%]
.....[contention-diag] +1746s soak 31p/253t rss 11.6G pss 10.9G swap 0.9G majflt 1629 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 32.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.39 cpu 27.5 | cgroup 11.6G/max oom_kill 0 | free scratch 320.6G/45437068i tmp 28.3G/998089i workspace 320.6G/45437068i | repeat-01 collected 26/26 workers (60626 items) tests 10939 done 2 failed | 26 in flight, oldest 305s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................[contention-diag] +1762s soak 30p/266t rss 11.7G pss 11.0G swap 0.8G majflt 1655 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 25.22 | cgroup 11.7G/max oom_kill 0 | free scratch 320.6G/45436761i tmp 28.3G/998089i workspace 320.6G/45436761i | repeat-01 collected 26/26 workers (60626 items) tests 10993 done 2 failed | 26 in flight, oldest 42s gw8 tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_offline_toggle_load_does_not_overwrite_memo
...................... [508%]
........................[contention-diag] +1777s soak 31p/296t rss 11.7G pss 11.0G swap 0.8G majflt 1658 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 23.58 | cgroup 11.7G/max oom_kill 0 | free scratch 320.6G/45436573i tmp 28.3G/998089i workspace 320.6G/45436573i | repeat-01 collected 26/26 workers (60626 items) tests 11040 done 2 failed | 26 in flight, oldest 52s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.......................................[contention-diag] +1792s soak 31p/300t rss 11.7G pss 11.0G swap 0.8G majflt 1673 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 28.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 26.92 | cgroup 11.7G/max oom_kill 0 | free scratch 320.1G/45436400i tmp 28.3G/998089i workspace 320.1G/45436400i | repeat-01 collected 26/26 workers (60626 items) tests 11076 done 2 failed | 26 in flight, oldest 67s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
......... [512%]
........................................................................ [515%]
........................................................................ [518%]
.............[contention-diag] +1808s soak 28p/269t rss 11.7G pss 11.0G swap 0.8G majflt 1684 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G | host avail 29.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.24/0.24 io 0.0 cpu 23.45 | cgroup 11.7G/max oom_kill 0 | free scratch 319.8G/45435632i tmp 28.3G/998089i workspace 319.8G/45435632i | repeat-01 collected 26/26 workers (60626 items) tests 11238 done 2 failed | 26 in flight, oldest 82s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
........................................................... [522%]
........................................................................ [525%]
....................................................[contention-diag] +1823s soak 30p/261t rss 11.7G pss 11.0G swap 0.8G majflt 1734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.62 cpu 21.66 | cgroup 11.7G/max oom_kill 0 | free scratch 319.8G/45435083i tmp 28.3G/998089i workspace 319.8G/45435083i | repeat-01 collected 26/26 workers (60626 items) tests 11416 done 2 failed | 25 in flight, oldest 98s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.................... [528%]
...............................F[contention-failure] call tests/ace/tui/util/test_stall_watchdog_suspend.py::test_paused_watchdog_emits_no_stall_while_loop_blocked: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_paused_watchdog_emits_no_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efbe575bbf0>

    @pytest.mark.asyncio
    async def test_paused_watchdog_emits_no_stall_while_loop_blocked(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        path = tmp_path / "tui_stalls.jsonl"
        monkeypatch.setattr(tui_telemetry, "TUI_STALLS_JSONL", str(path))
        watchdog = _EventLoopStallWatchdog(
            asyncio.get_running_loop(),
            threshold_seconds=0.05,
            poll_interval_seconds=0.01,
        )
        try:
            watchdog.start()
            watchdog.pause()
            # Block the loop well past the threshold while paused.
            time.sleep(0.2)  # sase-test-wait: intentional loop block
            # Let the watchdog thread poll several times during the paused block.
            await asyncio.sleep(0.05)  # sase-test-wait: watchdog thread poll window
        finally:
            watchdog.resume()
            watchdog.stop()
    
>       assert not path.exists()
E       AssertionError: assert not True
E        +  where True = exists()
E        +    where exists = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_paused_watchdog_emits_no_0/tui_stalls.jsonl').exists

tests/ace/tui/util/test_stall_watchdog_suspend.py:82: AssertionError
........................................ [532%]
.......[contention-diag] +1838s soak 29p/245t rss 11.8G pss 11.0G swap 0.8G majflt 1689 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.15 cpu 24.91 | cgroup 11.8G/max oom_kill 0 | free scratch 320.1G/45434703i tmp 28.3G/998089i workspace 320.1G/45434703i | scratch used 0.2G in 38977 entries | repeat-01 collected 26/26 workers (60626 items) tests 11526 done 3 failed | 26 in flight, oldest 46s gw9 tests/ace/tui/test_plugins_catalog_scale_fixture.py::test_scale_catalog_fixture_filters_and_marks_at_n10
............................................................[contention-diag] +1854s soak 29p/256t rss 11.8G pss 11.1G swap 0.9G majflt 1689 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 1 descendant rss 0.1G pss 0.0G | host avail 28.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 23.33 | cgroup 11.8G/max oom_kill 0 | free scratch 320.1G/45434454i tmp 28.3G/998089i workspace 320.1G/45434454i | repeat-01 collected 26/26 workers (60626 items) tests 11586 done 3 failed | 26 in flight, oldest 44s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
..... [535%]
.........................[contention-diag] +1869s soak 30p/279t rss 11.8G pss 11.1G swap 0.9G majflt 1689 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 26.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 24.19 | cgroup 11.8G/max oom_kill 0 | free scratch 320.1G/45434277i tmp 28.3G/998089i workspace 320.1G/45434277i | repeat-01 collected 26/26 workers (60626 items) tests 11616 done 3 failed | 26 in flight, oldest 50s gw8 tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_mutation_completion_while_covered_starts_no_catalog_load
............................................... [538%]
.......................[contention-diag] +1884s soak 29p/266t rss 11.8G pss 11.1G swap 0.8G majflt 1689 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 26.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.17 | cgroup 11.8G/max oom_kill 0 | free scratch 320.0G/45433992i tmp 28.3G/998089i workspace 320.0G/45433992i | repeat-01 collected 26/26 workers (60626 items) tests 11687 done 3 failed | 26 in flight, oldest 52s gw23 tests/ace/tui/test_feature_flags_pane_journeys.py::test_flags_pane_enable_and_disable_write_state_and_request_restart
................................................. [542%]
......................[contention-diag] +1900s soak 34p/273t rss 11.9G pss 11.1G swap 0.8G majflt 1693 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 6 descendant rss 0.1G pss 0.1G | host avail 23.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.45 | cgroup 11.8G/max oom_kill 0 | free scratch 319.9G/45433823i tmp 28.3G/998089i workspace 319.9G/45433823i | repeat-01 collected 26/26 workers (60626 items) tests 11753 done 3 failed | 26 in flight, oldest 60s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
.....................[contention-diag] +1915s soak 31p/271t rss 11.9G pss 11.1G swap 0.8G majflt 1693 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 3 descendant rss 0.1G pss 0.0G | host avail 24.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.88 | cgroup 11.8G/max oom_kill 0 | free scratch 319.4G/45433453i tmp 28.3G/998089i workspace 319.4G/45433453i | repeat-01 collected 26/26 workers (60626 items) tests 11777 done 3 failed | 26 in flight, oldest 69s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
............................. [545%]
..........................[contention-diag] +1931s soak 30p/262t rss 11.8G pss 11.1G swap 0.8G majflt 1693 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 24.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 20.98 | cgroup 11.8G/max oom_kill 0 | free scratch 319.2G/45433307i tmp 28.3G/998089i workspace 319.2G/45433307i | repeat-01 collected 26/26 workers (60626 items) tests 11833 done 3 failed | 26 in flight, oldest 52s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.............................................. [548%]
........................[contention-diag] +1946s soak 34p/262t rss 11.9G pss 11.1G swap 0.8G majflt 1693 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 6 descendant rss 0.1G pss 0.0G | host avail 31.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.79 cpu 16.18 | cgroup 11.9G/max oom_kill 0 | free scratch 319.4G/45432044i tmp 28.3G/998089i workspace 319.4G/45432044i | repeat-01 collected 26/26 workers (60626 items) tests 11902 done 3 failed | 26 in flight, oldest 67s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................................................ [552%]
........................................[contention-diag] +1961s soak 29p/250t rss 11.8G pss 11.1G swap 0.8G majflt 1699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 30.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.95 cpu 12.02 | cgroup 11.8G/max oom_kill 0 | free scratch 319.3G/45431556i tmp 28.3G/998089i workspace 319.3G/45431556i | scratch used 0.2G in 40891 entries | repeat-01 collected 26/26 workers (60626 items) tests 11986 done 3 failed | 26 in flight, oldest 82s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................................ [555%]
................................................................[contention-diag] +1978s soak 29p/256t rss 11.9G pss 11.1G swap 0.8G majflt 1699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.42 cpu 14.55 | cgroup 11.9G/max oom_kill 0 | free scratch 319.3G/45412617i tmp 28.3G/997775i workspace 319.3G/45412616i | repeat-01 collected 26/26 workers (60626 items) tests 12087 done 3 failed | 26 in flight, oldest 98s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
........ [558%]
........................................................................ [562%]
.........................................[contention-diag] +1993s soak 29p/240t rss 11.9G pss 11.2G swap 0.9G majflt 1699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.1G pss 0.0G | host avail 24.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 18.41 cpu 9.18 | cgroup 11.9G/max oom_kill 0 | free scratch 319.1G/45405144i tmp 28.3G/997854i workspace 319.1G/45405144i | repeat-01 collected 26/26 workers (60626 items) tests 12202 done 3 failed | 25 in flight, oldest 48s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_unknown_name_toasts_error
............................... [565%]
........................................................................ [568%]
.......................................[contention-diag] +2008s soak 29p/253t rss 11.8G pss 11.1G swap 0.8G majflt 1701 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.77 cpu 10.7 | cgroup 11.8G/max oom_kill 0 | free scratch 319.1G/45402609i tmp 28.3G/998035i workspace 319.1G/45402609i | repeat-01 collected 26/26 workers (60626 items) tests 12343 done 3 failed | 26 in flight, oldest 56s gw9 tests/ace/tui/test_projects_pane.py::test_projects_session_round_trips_current_project_display
................................. [572%]
........................................................................ [575%]
........................................................................ [578%]
..........[contention-diag] +2024s soak 29p/265t rss 11.9G pss 11.1G swap 0.8G majflt 1716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 30.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.12 cpu 25.32 | cgroup 11.9G/max oom_kill 0 | free scratch 319.1G/45402074i tmp 28.3G/998035i workspace 319.1G/45402074i | repeat-01 collected 26/26 workers (60626 items) tests 12528 done 3 failed | 26 in flight, oldest 65s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.............................................................. [581%]
........................................................................ [585%]
........................................................................ [588%]
.....[contention-diag] +2039s soak 30p/258t rss 11.9G pss 11.2G swap 0.8G majflt 1721 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 2 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 33.65 | cgroup 11.9G/max oom_kill 0 | free scratch 319.1G/45401449i tmp 28.3G/998035i workspace 319.1G/45401449i | repeat-01 collected 26/26 workers (60626 items) tests 12748 done 3 failed | 26 in flight, oldest 48s gw5 tests/ace/tui/test_statistics_pane_projects.py::test_projects_paints_output_while_code_worker_is_blocked
................................................................... [591%]
........[contention-diag] +2054s soak 29p/263t rss 11.9G pss 11.2G swap 0.8G majflt 1726 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 25.5 | cgroup 11.9G/max oom_kill 0 | free scratch 319.1G/45400267i tmp 28.3G/998061i workspace 319.1G/45400267i | repeat-01 collected 26/26 workers (60626 items) tests 12820 done 3 failed | 26 in flight, oldest 41s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hint_line_switches_to_jump_variant
................................................................ [595%]
........................................................................ [598%]
...............................[contention-diag] +2070s soak 29p/265t rss 11.9G pss 11.2G swap 0.8G majflt 1738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 22.72 | cgroup 11.9G/max oom_kill 0 | free scratch 319.1G/45400828i tmp 28.3G/998063i workspace 319.1G/45400828i | repeat-01 collected 26/26 workers (60626 items) tests 12983 done 3 failed | 26 in flight, oldest 49s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
......................................... [601%]
........................................................................ [605%]
..[contention-diag] +2085s soak 33p/253t rss 11.9G pss 11.2G swap 0.8G majflt 1738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 5 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 17.86 | cgroup 11.9G/max oom_kill 0 | free scratch 319.1G/45400750i tmp 28.3G/998063i workspace 319.1G/45400750i | scratch used 0.2G in 43978 entries | repeat-01 collected 26/26 workers (60626 items) tests 13097 done 3 failed | 26 in flight, oldest 54s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
...................................................................... [608%]
........................................................................ [611%]
........................................................................ [615%]
...........[contention-diag] +2101s soak 33p/244t rss 12.0G pss 11.3G swap 0.8G majflt 1753 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 5 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.77 | cgroup 12.0G/max oom_kill 0 | free scratch 319.1G/45400070i tmp 28.3G/998063i workspace 319.1G/45400070i | repeat-01 collected 26/26 workers (60626 items) tests 13328 done 3 failed | 25 in flight, oldest 70s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.....................................................[contention-diag] +2116s soak 29p/234t rss 12.0G pss 11.2G swap 0.8G majflt 1769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 35.25 | cgroup 12.0G/max oom_kill 0 | free scratch 319.1G/45399467i tmp 28.3G/998063i workspace 319.1G/45399467i | repeat-01 collected 26/26 workers (60626 items) tests 13380 done 3 failed | 26 in flight, oldest 46s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_shift_tab_switches_admin_center_tab_on_yaml_backed_row
........ [618%]
.............................................................[contention-diag] +2131s soak 34p/264t rss 12.0G pss 11.3G swap 0.8G majflt 1773 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 11.0G, 6 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 31.86 | cgroup 12.0G/max oom_kill 0 | free scratch 319.1G/45399540i tmp 28.3G/998063i workspace 319.1G/45399540i | repeat-01 collected 26/26 workers (60626 items) tests 13450 done 3 failed | 26 in flight, oldest 52s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
........... [621%]
........................................................................ [625%]
........................................................................ [628%]
......[contention-diag] +2147s soak 33p/287t rss 12.1G pss 11.4G swap 0.8G majflt 1914 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 31.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 29.85 | cgroup 12.1G/max oom_kill 0 | free scratch 319.1G/45398962i tmp 28.3G/998063i workspace 319.1G/45398962i | repeat-01 collected 26/26 workers (60626 items) tests 13604 done 3 failed | 25 in flight, oldest 67s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.................................................................. [631%]
.........................................................[contention-diag] +2162s soak 35p/304t rss 12.2G pss 11.4G swap 0.8G majflt 1790 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 7 descendant rss 0.2G pss 0.2G | host avail 32.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 27.26 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45398347i tmp 28.3G/998063i workspace 319.0G/45398346i | repeat-01 collected 26/26 workers (60626 items) tests 13735 done 3 failed | 26 in flight, oldest 82s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............... [635%]
.....................[contention-diag] +2177s soak 34p/265t rss 12.2G pss 11.4G swap 0.8G majflt 1794 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 6 descendant rss 0.2G pss 0.1G | host avail 32.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.55 | cgroup 12.4G/max oom_kill 0 | free scratch 318.9G/45398026i tmp 28.3G/998063i workspace 318.9G/45398026i | repeat-01 collected 26/26 workers (60626 items) tests 13769 done 3 failed | 26 in flight, oldest 98s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
................................................... [638%]
....................................[contention-diag] +2193s soak 28p/241t rss 12.0G pss 11.3G swap 0.8G majflt 1799 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G | host avail 33.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.41 cpu 30.82 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45397759i tmp 28.3G/998063i workspace 319.0G/45397759i | repeat-01 collected 26/26 workers (60626 items) tests 13852 done 3 failed | 26 in flight, oldest 89s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
.................................... [641%]
........................................................................ [645%]
........................................................................ [648%]
.......................[contention-diag] +2208s soak 28p/245t rss 12.0G pss 11.3G swap 0.8G majflt 1801 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G | host avail 34.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.08 cpu 34.76 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45397025i tmp 28.3G/998063i workspace 319.0G/45397025i | scratch used 0.3G in 47591 entries | repeat-01 collected 26/26 workers (60626 items) tests 14060 done 3 failed | 26 in flight, oldest 60s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_task_uses_admin_center_trigger_and_progress
................................................. [651%]
.........[contention-diag] +2224s soak 29p/262t rss 12.0G pss 11.3G swap 0.8G majflt 1809 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 32.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 24.64 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45396779i tmp 28.3G/998063i workspace 319.0G/45396779i | repeat-01 collected 26/26 workers (60626 items) tests 14112 done 3 failed | 25 in flight, oldest 59s gw22 tests/ace/tui/test_statistics_footprint.py::test_footprint_copy_sends_selected_feature_id
............................................................... [655%]
........................................................................ [658%]
.[contention-diag] +2239s soak 29p/271t rss 12.1G pss 11.3G swap 0.8G majflt 1813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 32.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.93 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45396333i tmp 28.3G/998063i workspace 319.0G/45396333i | repeat-01 collected 26/26 workers (60626 items) tests 14255 done 3 failed | 26 in flight, oldest 54s gw6 tests/ace/tui/test_macro_browser_filter.py::test_cached_reactivation_restores_open_filter_or_list
....................................................................... [661%]
........................................................................ [665%]
.[contention-diag] +2254s soak 29p/255t rss 12.1G pss 11.4G swap 0.8G majflt 1813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 1 descendant rss 0.0G pss 0.0G | host avail 33.0G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.85 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45395865i tmp 28.3G/998063i workspace 319.0G/45395865i | repeat-01 collected 26/26 workers (60626 items) tests 14394 done 3 failed | 26 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
....................................................................... [668%]
.......................................................[contention-diag] +2270s soak 29p/251t rss 12.1G pss 11.4G swap 0.8G majflt 1820 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 1 descendant rss 0.0G pss 0.0G | host avail 32.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.74 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45395507i tmp 28.3G/998062i workspace 319.0G/45395507i | repeat-01 collected 26/26 workers (60626 items) tests 14526 done 3 failed | 26 in flight, oldest 78s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
................. [671%]
........................................................................ [675%]
............................................................[contention-diag] +2285s soak 29p/253t rss 12.1G pss 11.4G swap 0.7G majflt 1847 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 1 descendant rss 0.0G pss 0.0G | host avail 31.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.34 | cgroup 12.2G/max oom_kill 0 | free scratch 319.0G/45394358i tmp 28.3G/998063i workspace 319.0G/45394358i | repeat-01 collected 26/26 workers (60626 items) tests 14667 done 3 failed | 26 in flight, oldest 53s gw22 tests/ace/tui/test_statistics_footprint.py::test_footprint_keep_reason_is_recorded_by_a_worker
............ [678%]
........................................................................ [681%]
...................................................[contention-diag] +2300s soak 32p/258t rss 12.2G pss 11.4G swap 0.7G majflt 1863 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 4 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 24.41 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45394126i tmp 28.3G/998062i workspace 319.0G/45394126i | repeat-01 collected 26/26 workers (60626 items) tests 14806 done 3 failed | 25 in flight, oldest 47s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input
..................... [685%]
........................................................................ [688%]
..........[contention-diag] +2316s soak 35p/258t rss 12.2G pss 11.5G swap 0.7G majflt 1881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 7 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 19.19 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45393738i tmp 28.3G/998062i workspace 319.0G/45393738i | repeat-01 collected 26/26 workers (60626 items) tests 14905 done 3 failed | 26 in flight, oldest 51s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
.............................................................. [691%]
........................................................................ [695%]
[contention-diag] +2331s soak 31p/261t rss 12.2G pss 11.5G swap 0.7G majflt 1920 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.2G, 3 descendant rss 0.1G pss 0.1G | host avail 31.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 21.14 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45392398i tmp 28.3G/998062i workspace 319.0G/45392398i | scratch used 0.3G in 51945 entries | repeat-01 collected 26/26 workers (60626 items) tests 15035 done 3 failed | 26 in flight, oldest 66s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
........................................................................ [698%]
........................................................................ [701%]
...................................................[contention-diag] +2347s soak 33p/244t rss 12.2G pss 11.5G swap 0.7G majflt 1922 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.2G, 5 descendant rss 0.0G pss 0.0G | host avail 32.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 22.23 | cgroup 12.3G/max oom_kill 0 | free scratch 319.0G/45401872i tmp 28.3G/998062i workspace 319.0G/45401872i | repeat-01 collected 26/26 workers (60626 items) tests 15237 done 3 failed | 25 in flight, oldest 77s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
..................... [705%]
........................................................................ [708%]
..................................................[contention-diag] +2362s soak 30p/262t rss 12.3G pss 11.5G swap 0.7G majflt 1922 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 2 descendant rss 0.1G pss 0.0G | host avail 33.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.54 cpu 22.84 | cgroup 12.4G/max oom_kill 0 | free scratch 324.4G/45423725i tmp 28.3G/998062i workspace 324.4G/45423725i | repeat-01 collected 26/26 workers (60626 items) tests 15370 done 3 failed | 24 in flight, oldest 58s gw14 tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
...................... [711%]
........................................................................ [715%]
........................................................................ [718%]
.............[contention-diag] +2377s soak 34p/275t rss 12.3G pss 11.5G swap 0.7G majflt 1931 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 6 descendant rss 0.1G pss 0.0G | host avail 34.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 26.42 | cgroup 12.4G/max oom_kill 0 | free scratch 324.4G/45422943i tmp 28.3G/998062i workspace 324.4G/45422943i | repeat-01 collected 26/26 workers (60626 items) tests 15560 done 3 failed | 25 in flight, oldest 73s gw14 tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
........................................................... [721%]
........................................................................ [724%]
.......................[contention-diag] +2393s soak 41p/258t rss 12.4G pss 11.6G swap 0.8G majflt 1933 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 13 descendant rss 0.1G pss 0.1G | host avail 32.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 21.94 | cgroup 12.5G/max oom_kill 0 | free scratch 324.8G/45425648i tmp 28.3G/998062i workspace 324.8G/45425648i | repeat-01 collected 26/26 workers (60626 items) tests 15712 done 3 failed | 26 in flight, oldest 86s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................. [728%]
........................................................................ [731%]
........................................................................ [734%]
...............................[contention-diag] +2408s soak 35p/248t rss 12.4G pss 11.7G swap 0.7G majflt 1935 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.3G, 7 descendant rss 0.2G pss 0.1G | host avail 32.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 22.05 | cgroup 12.7G/max oom_kill 0 | free scratch 324.8G/45424803i tmp 28.3G/998062i workspace 324.8G/45424803i | repeat-01 collected 26/26 workers (60626 items) tests 15935 done 3 failed | 26 in flight, oldest 102s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
......................................... [738%]
........................................................................ [741%]
........................................................................ [744%]
........................................................................ [748%]
.........[contention-diag] +2424s soak 32p/235t rss 12.4G pss 11.7G swap 0.7G majflt 1974 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.3G, 4 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.71 cpu 24.42 | cgroup 12.5G/max oom_kill 0 | free scratch 324.8G/45423817i tmp 28.3G/998062i workspace 324.8G/45423817i | repeat-01 collected 26/26 workers (60626 items) tests 16205 done 3 failed | 26 in flight, oldest 117s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............................................................... [751%]
........................................................................ [754%]
........................................................................ [758%]
...........................................................[contention-diag] +2439s soak 33p/241t rss 12.4G pss 11.6G swap 0.7G majflt 1977 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.4G, 5 descendant rss 0.1G pss 0.1G | host avail 32.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.23 cpu 27.83 | cgroup 12.5G/max oom_kill 0 | free scratch 324.8G/45422772i tmp 28.3G/998062i workspace 324.8G/45422772i | repeat-01 collected 26/26 workers (60626 items) tests 16473 done 3 failed | 26 in flight, oldest 133s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............. [761%]
........................................................................ [764%]
........................................................................ [768%]
........................................................................ [771%]
...............................................................[contention-diag] +2454s soak 34p/267t rss 12.5G pss 11.7G swap 0.7G majflt 2007 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.4G, 6 descendant rss 0.1G pss 0.1G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 23.62 | cgroup 12.6G/max oom_kill 0 | free scratch 324.8G/45421665i tmp 28.3G/998062i workspace 324.8G/45421665i | scratch used 0.3G in 59348 entries | repeat-01 collected 26/26 workers (60626 items) tests 16746 done 3 failed | 25 in flight, oldest 148s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
......... [774%]
........................................................................ [778%]
........................................................................ [781%]
.................................................[contention-diag] +2470s soak 34p/284t rss 12.4G pss 11.7G swap 0.7G majflt 2007 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.4G, 6 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 23.83 | cgroup 12.6G/max oom_kill 0 | free scratch 324.8G/45420865i tmp 28.3G/998062i workspace 324.8G/45420865i | repeat-01 collected 26/26 workers (60626 items) tests 16962 done 3 failed | 26 in flight, oldest 164s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
....................... [784%]
........................................................................ [788%]
.....................[contention-diag] +2486s soak 36p/264t rss 12.6G pss 11.8G swap 0.7G majflt 2045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 8 descendant rss 0.2G pss 0.2G | host avail 30.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.8 cpu 21.34 | cgroup 12.9G/max oom_kill 0 | free scratch 324.8G/45422932i tmp 28.3G/998061i workspace 324.8G/45422932i | repeat-01 collected 26/26 workers (60626 items) tests 17082 done 3 failed | 26 in flight, oldest 106s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
................................................... [791%]
....................................[contention-diag] +2501s soak 32p/241t rss 12.5G pss 11.6G swap 0.7G majflt 2045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 4 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.26/0.26 io 0.25 cpu 23.63 | cgroup 12.7G/max oom_kill 0 | free scratch 324.8G/45422572i tmp 28.3G/998061i workspace 324.8G/45422572i | repeat-01 collected 26/26 workers (60626 items) tests 17163 done 3 failed | 26 in flight, oldest 121s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.................................... [794%]
........................................................................ [798%]
........................................................................ [801%]
...............[contention-diag] +2516s soak 30p/247t rss 12.4G pss 11.7G swap 0.7G majflt 2045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 2 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.09 cpu 26.98 | cgroup 12.6G/max oom_kill 0 | free scratch 324.8G/45422139i tmp 28.3G/998061i workspace 324.8G/45422139i | repeat-01 collected 26/26 workers (60626 items) tests 17353 done 3 failed | 26 in flight, oldest 130s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
......................................................... [804%]
........................................................................ [808%]
........................................................................ [811%]
........................................................................ [814%]
........................................................................ [818%]
....................................[contention-diag] +2532s soak 32p/266t rss 12.5G pss 11.7G swap 0.7G majflt 2045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.5G, 4 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.02 cpu 26.69 | cgroup 12.6G/max oom_kill 0 | free scratch 324.8G/45421129i tmp 28.3G/998061i workspace 324.8G/45421129i | repeat-01 collected 26/26 workers (60626 items) tests 17738 done 3 failed | 25 in flight, oldest 48s gw23 tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
.................................... [821%]
........................................................................ [824%]
......................................................[contention-diag] +2547s soak 33p/252t rss 12.5G pss 11.7G swap 0.7G majflt 2053 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.4G, 5 descendant rss 0.0G pss 0.0G | host avail 32.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 32.99 | cgroup 12.6G/max oom_kill 0 | free scratch 324.8G/45420754i tmp 28.3G/998061i workspace 324.8G/45420754i | repeat-01 collected 26/26 workers (60626 items) tests 17894 done 3 failed | 26 in flight, oldest 48s gw1 tests/test_command_palette_e2e.py::test_semicolon_opens_command_palette_from_agents_and_axe_tabs
.................. [828%]
........................................................................ [831%]
........................................................................ [834%]
...............................[contention-diag] +2562s soak 30p/235t rss 12.6G pss 11.8G swap 0.7G majflt 2055 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.5G, 2 descendant rss 0.1G pss 0.1G | host avail 32.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 32.36 | cgroup 12.7G/max oom_kill 0 | free scratch 324.8G/45420314i tmp 28.3G/998061i workspace 324.8G/45420314i | repeat-01 collected 26/26 workers (60626 items) tests 18086 done 3 failed | 25 in flight, oldest 62s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
......................................... [838%]
.....................................................[contention-diag] +2578s soak 31p/237t rss 12.5G pss 11.7G swap 0.7G majflt 2055 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.5G, 3 descendant rss 0.0G pss 0.0G | host avail 31.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 33.62 | cgroup 12.8G/max oom_kill 0 | free scratch 324.8G/45419936i tmp 28.3G/998061i workspace 324.8G/45419936i | scratch used 0.3G in 60990 entries | repeat-01 collected 26/26 workers (60626 items) tests 18190 done 3 failed | 26 in flight, oldest 75s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................... [841%]
........................................................................ [844%]
...............................................................[contention-diag] +2594s soak 35p/228t rss 12.5G pss 11.7G swap 0.7G majflt 2061 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.5G, 7 descendant rss 0.1G pss 0.0G | host avail 30.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 28.78 | cgroup 12.6G/max oom_kill 0 | free scratch 324.8G/45419401i tmp 28.3G/998061i workspace 324.8G/45419401i | repeat-01 collected 26/26 workers (60626 items) tests 18336 done 3 failed | 26 in flight, oldest 91s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
......... [848%]
........................................................................ [851%]
........................................................................ [854%]
........................................................................ [858%]
........................................................................ [861%]
........................................................................ [864%]
...........................................................[contention-diag] +2609s soak 33p/249t rss 12.5G pss 11.7G swap 0.7G majflt 2062 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.5G, 5 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 27.52 | cgroup 12.7G/max oom_kill 0 | free scratch 324.8G/45418492i tmp 28.3G/998061i workspace 324.8G/45418492i | repeat-01 collected 26/26 workers (60626 items) tests 18778 done 3 failed | 26 in flight, oldest 106s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............. [867%]
........................................................................ [871%]
........................................................................ [874%]
.......................[contention-diag] +2624s soak 33p/236t rss 12.6G pss 11.8G swap 0.7G majflt 2066 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.6G, 5 descendant rss 0.0G pss 0.0G | host avail 32.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 24.62 | cgroup 12.8G/max oom_kill 0 | free scratch 324.8G/45417746i tmp 28.3G/998061i workspace 324.8G/45417746i | repeat-01 collected 26/26 workers (60626 items) tests 18951 done 3 failed | 26 in flight, oldest 51s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
................................................. [877%]
........................................................................ [881%]
........................................................................ [884%]
........................................................................ [887%]
.................................................[contention-diag] +2640s soak 36p/222t rss 12.6G pss 11.8G swap 0.7G majflt 2087 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.6G, 8 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.57 cpu 36.96 | cgroup 12.8G/max oom_kill 0 | free scratch 324.7G/45416815i tmp 28.3G/998061i workspace 324.7G/45416815i | repeat-01 collected 26/26 workers (60626 items) tests 19262 done 3 failed | 25 in flight, oldest 66s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
....................... [891%]
........................................................................ [894%]
........................................................................ [897%]
...................[contention-diag] +2655s soak 31p/236t rss 12.6G pss 11.7G swap 0.7G majflt 2094 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.5G, 3 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 29.64 | cgroup 12.8G/max oom_kill 0 | free scratch 324.8G/45415437i tmp 28.3G/998061i workspace 324.8G/45415437i | repeat-01 collected 26/26 workers (60626 items) tests 19453 done 3 failed | 26 in flight, oldest 44s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_statistics_loads_only_after_its_tab_becomes_active
...............................s..................... [901%]
..............................................[contention-diag] +2670s soak 32p/247t rss 12.6G pss 11.8G swap 0.7G majflt 2095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 4 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 24.82 | cgroup 12.9G/max oom_kill 0 | free scratch 324.8G/45415217i tmp 28.3G/998061i workspace 324.8G/45415217i | repeat-01 collected 26/26 workers (60626 items) tests 19555 done 3 failed | 26 in flight, oldest 58s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
..................ss...... [904%]
........................................................................ [907%]
........................................................................ [911%]
........................................................................ [914%]
........................................................................ [917%]
.........[contention-diag] +2686s soak 33p/229t rss 12.7G pss 11.9G swap 0.7G majflt 2103 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 5 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.55 cpu 32.95 | cgroup 12.9G/max oom_kill 0 | free scratch 324.8G/45415091i tmp 28.3G/998061i workspace 324.8G/45415091i | repeat-01 collected 26/26 workers (60626 items) tests 19870 done 3 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............................................................... [921%]
........................................................................ [924%]
........................................................................ [927%]
..................................[contention-diag] +2701s soak 36p/262t rss 12.7G pss 11.9G swap 0.7G majflt 2113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 8 descendant rss 0.1G pss 0.0G | host avail 31.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.16 cpu 34.83 | cgroup 12.8G/max oom_kill 0 | free scratch 324.7G/45413662i tmp 28.3G/998061i workspace 324.7G/45413662i | scratch used 0.4G in 66759 entries | repeat-01 collected 26/26 workers (60626 items) tests 20101 done 3 failed | 26 in flight, oldest 89s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
...................................... [931%]
........................................................................ [934%]
........................................................................ [937%]
....................................................................[contention-diag] +2717s soak 34p/257t rss 12.7G pss 11.9G swap 0.7G majflt 2119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.19 cpu 33.0 | cgroup 12.9G/max oom_kill 0 | free scratch 324.7G/45413205i tmp 28.3G/998061i workspace 324.7G/45413205i | repeat-01 collected 26/26 workers (60626 items) tests 20371 done 3 failed | 26 in flight, oldest 105s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.... [941%]
........................................................................ [944%]
........................................................................ [947%]
..............................................................[contention-diag] +2732s soak 33p/254t rss 12.8G pss 12.0G swap 0.7G majflt 2122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 5 descendant rss 0.2G pss 0.1G | host avail 30.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 26.55 | cgroup 12.9G/max oom_kill 0 | free scratch 324.7G/45412910i tmp 28.3G/998061i workspace 324.7G/45412910i | repeat-01 collected 26/26 workers (60626 items) tests 20576 done 3 failed | 26 in flight, oldest 60s gw1 tests/test_command_palette_e2e.py::test_palette_escape_dismisses_from_each_tab
.......... [951%]
........................................................................ [954%]
........................................................................ [957%]
................[contention-diag] +2748s soak 35p/272t rss 12.8G pss 12.0G swap 0.7G majflt 2128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 7 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 31.08 | cgroup 12.9G/max oom_kill 0 | free scratch 324.7G/45412309i tmp 28.3G/998061i workspace 324.7G/45412309i | repeat-01 collected 26/26 workers (60626 items) tests 20744 done 3 failed | 25 in flight, oldest 46s gw13 tests/ace/tui/test_patch_filter_bar.py::test_patch_filter_parse_error_leaves_visible_list_unchanged
........................................................ [961%]
........................................................................ [964%]
........................................................................ [967%]
.........[contention-diag] +2763s soak 34p/257t rss 12.8G pss 12.0G swap 0.7G majflt 2137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 6 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.92 cpu 33.96 | cgroup 12.9G/max oom_kill 0 | free scratch 324.7G/45411494i tmp 28.3G/998061i workspace 324.7G/45411494i | repeat-01 collected 26/26 workers (60626 items) tests 20954 done 3 failed | 25 in flight, oldest 55s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
............................................................... [971%]
........................................................................ [974%]
...........................................................s............ [977%]
........................................................................ [981%]
.................................................[contention-diag] +2778s soak 44p/269t rss 13.0G pss 12.0G swap 0.7G majflt 2140 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 16 descendant rss 0.3G pss 0.2G | host avail 30.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 28.08 | cgroup 13.0G/max oom_kill 0 | free scratch 324.7G/45410566i tmp 28.3G/998061i workspace 324.7G/45410566i | repeat-01 collected 26/26 workers (60626 items) tests 21287 done 3 failed | 26 in flight, oldest 70s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
....................... [984%]
........................................................................ [987%]
........................................................................ [991%]
..................[contention-diag] +2794s soak 35p/252t rss 13.0G pss 12.1G swap 0.7G majflt 2141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 7 descendant rss 0.3G pss 0.2G | host avail 32.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 30.22 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45408959i tmp 28.3G/998061i workspace 324.7G/45408959i | repeat-01 collected 26/26 workers (60626 items) tests 21472 done 3 failed | 26 in flight, oldest 38s gw8 tests/ace/tui/test_usage_header.py::test_explicit_provider_argument_wins_over_header_selection
................................................s..... [994%]
........................................................................ [997%]
....................[contention-diag] +2809s soak 41p/274t rss 13.0G pss 12.1G swap 0.7G majflt 2146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 13 descendant rss 0.4G pss 0.2G | host avail 34.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.48/0.48 io 0.25 cpu 30.07 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45407381i tmp 28.3G/998061i workspace 324.7G/45407381i | repeat-01 collected 26/26 workers (60626 items) tests 21608 done 3 failed | 26 in flight, oldest 44s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.................................................... [1001%]
........................................................................ [1004%]
.............[contention-diag] +2824s soak 42p/276t rss 13.1G pss 12.1G swap 0.7G majflt 2146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 14 descendant rss 0.4G pss 0.3G | host avail 33.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 0.14 cpu 35.56 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45408728i tmp 28.3G/998061i workspace 324.7G/45408728i | scratch used 0.4G in 72238 entries | repeat-01 collected 26/26 workers (60626 items) tests 21730 done 3 failed | 26 in flight, oldest 59s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
........................................................... [1007%]
........................................................................ [1010%]
........................................................................ [1014%]
........................................................................ [1017%]
....................................................................[contention-diag] +2840s soak 39p/230t rss 12.9G pss 12.0G swap 0.7G majflt 2154 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 11 descendant rss 0.2G pss 0.2G | host avail 32.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.29 cpu 33.77 | cgroup 13.0G/max oom_kill 0 | free scratch 324.7G/45407815i tmp 28.3G/998061i workspace 324.7G/45407815i | repeat-01 collected 26/26 workers (60626 items) tests 22094 done 3 failed | 26 in flight, oldest 76s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.... [1020%]
........................................................................ [1024%]
........................................................................ [1027%]
........................................................................ [1030%]
...[contention-diag] +2856s soak 38p/239t rss 12.9G pss 12.0G swap 0.7G majflt 2160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 10 descendant rss 0.2G pss 0.2G | host avail 32.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 25.71 | cgroup 13.0G/max oom_kill 0 | free scratch 324.7G/45407182i tmp 28.3G/998061i workspace 324.7G/45407182i | repeat-01 collected 26/26 workers (60626 items) tests 22307 done 3 failed | 26 in flight, oldest 91s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
..................................................................... [1034%]
........................................................................ [1037%]
........................................................................ [1040%]
........................................................................ [1044%]
......................................[contention-diag] +2871s soak 38p/234t rss 13.1G pss 12.2G swap 0.7G majflt 2163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 10 descendant rss 0.4G pss 0.3G | host avail 32.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 34.78 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45406510i tmp 28.3G/998061i workspace 324.7G/45406510i | repeat-01 collected 26/26 workers (60626 items) tests 22610 done 3 failed | 26 in flight, oldest 106s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.................................. [1047%]
........................................................................ [1050%]
........................................................................ [1054%]
........................................................................ [1057%]
........................................................................ [1060%]
........................................................................ [1064%]
........................................................................ [1067%]
...............................................[contention-diag] +2886s soak 36p/198t rss 13.0G pss 12.1G swap 0.7G majflt 2163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.6G, 8 descendant rss 0.3G pss 0.2G | host avail 33.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.65 cpu 36.51 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45405130i tmp 28.3G/998061i workspace 324.7G/45405130i | repeat-01 collected 26/26 workers (60626 items) tests 23157 done 3 failed | 24 in flight, oldest 122s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
......................... [1070%]
........................................................................ [1074%]
........................................................................ [1077%]
........................................................................ [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
........................................................................ [1090%]
...[contention-diag] +2902s soak 35p/188t rss 13.0G pss 12.1G swap 0.7G majflt 2164 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 7 descendant rss 0.3G pss 0.3G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 29.77 | cgroup 13.2G/max oom_kill 0 | free scratch 324.7G/45404251i tmp 28.3G/998061i workspace 324.7G/45404251i | repeat-01 collected 26/26 workers (60626 items) tests 23597 done 3 failed | 26 in flight, oldest 69s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
..................................................................... [1094%]
........................................................................ [1097%]
........................................................................ [1100%]
........................................................................ [1104%]
...........................................[contention-diag] +2917s soak 35p/189t rss 12.9G pss 12.0G swap 0.7G majflt 2165 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 7 descendant rss 0.2G pss 0.1G | host avail 29.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 28.39 | cgroup 13.1G/max oom_kill 0 | free scratch 324.7G/45402981i tmp 28.3G/998061i workspace 324.7G/45402981i | repeat-01 collected 26/26 workers (60626 items) tests 23941 done 3 failed | 25 in flight, oldest 50s gw13 tests/ace/tui/test_patch_filter_bar.py::test_action_patches_filters_is_scoped_to_patches_pane
............................. [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
........................................................................ [1117%]
........................................................................ [1120%]
........................................................................ [1124%]
....................................................[contention-diag] +2933s soak 41p/180t rss 13.0G pss 12.1G swap 0.6G majflt 2179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 13 descendant rss 0.2G pss 0.1G | host avail 31.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 21.28 | cgroup 13.2G/max oom_kill 0 | free scratch 324.5G/45400940i tmp 28.3G/998060i workspace 324.5G/45400940i | repeat-01 collected 26/26 workers (60626 items) tests 24382 done 3 failed | 26 in flight, oldest 35s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.................... [1127%]
........................................................................ [1130%]
........................................................................ [1134%]
........................................................................ [1137%]
.........................................[contention-diag] +2948s soak 43p/194t rss 13.0G pss 12.1G swap 0.6G majflt 2752 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 15 descendant rss 0.2G pss 0.2G | host avail 31.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 20.42 | cgroup 13.1G/max oom_kill 0 | free scratch 324.0G/45399166i tmp 28.3G/998060i workspace 324.0G/45399166i | scratch used 0.4G in 79799 entries | repeat-01 collected 26/26 workers (60626 items) tests 24644 done 3 failed | 25 in flight, oldest 50s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................... [1140%]
........................................................................ [1144%]
........................................................................ [1147%]
........................................................................ [1150%]
.........................[contention-diag] +2964s soak 34p/184t rss 12.8G pss 12.0G swap 0.6G majflt 2180 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 6 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 24.8 | cgroup 13.1G/max oom_kill 0 | free scratch 324.0G/45398188i tmp 28.3G/998060i workspace 324.0G/45398188i | repeat-01 collected 26/26 workers (60626 items) tests 24918 done 3 failed | 26 in flight, oldest 66s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................... [1153%]
........................................................................ [1157%]
........................................................................ [1160%]
........................s............................................... [1163%]
........................................................................ [1167%]
...................................[contention-diag] +2979s soak 31p/175t rss 12.9G pss 12.0G swap 0.7G majflt 2187 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 3 descendant rss 0.1G pss 0.0G | host avail 29.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 22.2 | cgroup 13.1G/max oom_kill 0 | free scratch 324.0G/45397348i tmp 28.3G/998060i workspace 324.0G/45397348i | repeat-01 collected 26/26 workers (60626 items) tests 25296 done 3 failed | 26 in flight, oldest 81s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..................................... [1170%]
........................................................................ [1173%]
........................................................................ [1177%]
.................[contention-diag] +2995s soak 31p/178t rss 12.9G pss 12.0G swap 0.6G majflt 2187 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.5G pss 11.7G, 3 descendant rss 0.1G pss 0.0G | host avail 29.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 27.13 | cgroup 13.2G/max oom_kill 0 | free scratch 324.0G/45396816i tmp 28.3G/998060i workspace 324.0G/45396816i | repeat-01 collected 26/26 workers (60626 items) tests 25493 done 3 failed | 26 in flight, oldest 97s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................................... [1180%]
........................................................................ [1183%]
........................................................................ [1187%]
......................[contention-diag] +3010s soak 33p/178t rss 12.9G pss 12.0G swap 0.6G majflt 2191 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 5 descendant rss 0.1G pss 0.0G | host avail 28.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 31.66 | cgroup 13.2G/max oom_kill 0 | free scratch 323.9G/45396337i tmp 28.3G/998060i workspace 323.9G/45396337i | repeat-01 collected 26/26 workers (60626 items) tests 25717 done 3 failed | 26 in flight, oldest 112s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................................. [1190%]
........................................................................ [1193%]
.........................[contention-diag] +3025s soak 32p/184t rss 12.9G pss 12.0G swap 0.7G majflt 2192 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 4 descendant rss 0.1G pss 0.0G | host avail 25.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 21.67 | cgroup 13.2G/max oom_kill 0 | free scratch 323.7G/45396441i tmp 28.3G/998060i workspace 323.7G/45396441i | repeat-01 collected 26/26 workers (60626 items) tests 25865 done 3 failed | 25 in flight, oldest 127s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................... [1197%]
........................................................................ [1200%]
.............................[contention-diag] +3041s soak 30p/168t rss 12.9G pss 12.0G swap 0.6G majflt 2192 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 2 descendant rss 0.0G pss 0.0G | host avail 29.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 22.51 | cgroup 13.2G/max oom_kill 0 | free scratch 323.2G/45396080i tmp 28.3G/998060i workspace 323.2G/45396080i | repeat-01 collected 26/26 workers (60626 items) tests 26020 done 3 failed | 25 in flight, oldest 143s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................... [1203%]
........................................................................ [1207%]
........................................................................ [1210%]
..................................[contention-diag] +3056s soak 35p/175t rss 13.0G pss 12.1G swap 0.6G majflt 2193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 7 descendant rss 0.1G pss 0.1G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 28.18 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45395124i tmp 28.3G/998054i workspace 323.2G/45395124i | repeat-01 collected 26/26 workers (60626 items) tests 26241 done 3 failed | 25 in flight, oldest 158s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
...................................... [1213%]
........................................................................ [1217%]
.................................................................[contention-diag] +3071s soak 33p/182t rss 13.0G pss 12.1G swap 0.7G majflt 2193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 5 descendant rss 0.2G pss 0.1G | host avail 31.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 37.63 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45395099i tmp 28.3G/998054i workspace 323.2G/45395099i | scratch used 0.4G in 83798 entries | repeat-01 collected 26/26 workers (60626 items) tests 26402 done 3 failed | 25 in flight, oldest 173s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....... [1220%]
........................................................................ [1223%]
........................................................................ [1227%]
........................................................................ [1230%]
........................................................................ [1233%]
........................................................................ [1237%]
...........................................[contention-diag] +3088s soak 40p/173t rss 13.2G pss 12.2G swap 0.7G majflt 2193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 12 descendant rss 0.3G pss 0.2G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 31.04 | cgroup 13.4G/max oom_kill 0 | free scratch 323.2G/45393973i tmp 28.3G/998054i workspace 323.2G/45393973i | repeat-01 collected 26/26 workers (60626 items) tests 26811 done 3 failed | 25 in flight, oldest 190s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................. [1240%]
........................................................................ [1243%]
........................................................................ [1247%]
................................[contention-diag] +3103s soak 33p/168t rss 13.0G pss 12.1G swap 0.7G majflt 2193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 5 descendant rss 0.2G pss 0.1G | host avail 29.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 25.84 | cgroup 13.4G/max oom_kill 0 | free scratch 323.2G/45393463i tmp 28.3G/998054i workspace 323.2G/45393463i | repeat-01 collected 26/26 workers (60626 items) tests 27026 done 3 failed | 25 in flight, oldest 205s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................ [1250%]
........................................................................ [1253%]
...........................................[contention-diag] +3118s soak 38p/173t rss 13.1G pss 12.2G swap 0.7G majflt 2193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 10 descendant rss 0.2G pss 0.2G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 27.51 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45392581i tmp 28.3G/998054i workspace 323.2G/45392581i | repeat-01 collected 26/26 workers (60626 items) tests 27179 done 3 failed | 25 in flight, oldest 220s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................. [1257%]
........................................................................ [1260%]
........................................................................ [1263%]
.............[contention-diag] +3134s soak 39p/170t rss 13.0G pss 12.1G swap 0.6G majflt 2193 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 11 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 35.52 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45391887i tmp 28.3G/998054i workspace 323.2G/45391887i | repeat-01 collected 26/26 workers (60626 items) tests 27366 done 3 failed | 24 in flight, oldest 236s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................................... [1267%]
........................................................................ [1270%]
........................................................................ [1273%]
........................................................................ [1277%]
.....................................[contention-diag] +3149s soak 37p/174t rss 13.0G pss 12.1G swap 0.6G majflt 2196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 9 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.36 cpu 36.45 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45391062i tmp 28.3G/998054i workspace 323.2G/45391062i | repeat-01 collected 26/26 workers (60626 items) tests 27653 done 3 failed | 24 in flight, oldest 251s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................... [1280%]
........................................................................ [1283%]
........................................................................ [1287%]
........................................................................ [1290%]
........................................................................ [1293%]
............................................................[contention-diag] +3164s soak 41p/189t rss 13.1G pss 12.1G swap 0.6G majflt 2197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 13 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 25.98 | cgroup 13.4G/max oom_kill 0 | free scratch 323.2G/45389610i tmp 28.3G/998054i workspace 323.2G/45389610i | repeat-01 collected 26/26 workers (60626 items) tests 28058 done 3 failed | 25 in flight, oldest 164s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............ [1296%]
........................................................................ [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
........................................................................ [1310%]
........................[contention-diag] +3180s soak 34p/176t rss 13.1G pss 12.1G swap 0.6G majflt 2199 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.7G, 6 descendant rss 0.2G pss 0.1G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 30.29 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45389195i tmp 28.3G/998054i workspace 323.2G/45389195i | repeat-01 collected 26/26 workers (60626 items) tests 28380 done 3 failed | 25 in flight, oldest 180s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................ [1313%]
........................................................................ [1316%]
........................................................................ [1320%]
........................................................................ [1323%]
........................................................................ [1326%]
.........[contention-diag] +3195s soak 34p/171t rss 13.0G pss 12.1G swap 0.6G majflt 2201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.8G, 6 descendant rss 0.1G pss 0.1G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 0.04 cpu 34.98 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45387515i tmp 28.3G/998054i workspace 323.2G/45387515i | scratch used 0.5G in 91477 entries | repeat-01 collected 26/26 workers (60626 items) tests 28723 done 3 failed | 25 in flight, oldest 195s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................... [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
........................................................................ [1340%]
....................[contention-diag] +3211s soak 32p/165t rss 13.0G pss 12.1G swap 0.6G majflt 2203 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.6G pss 11.8G, 4 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.99 cpu 32.02 | cgroup 13.3G/max oom_kill 0 | free scratch 323.2G/45387264i tmp 28.3G/998054i workspace 323.2G/45387264i | repeat-01 collected 26/26 workers (60626 items) tests 29019 done 3 failed | 25 in flight, oldest 211s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................................................... [1343%]
........................................................................ [1346%]
........................................................................ [1350%]
........................................................................ [1353%]
........................................................................ [1356%]
..................................[contention-diag] +3227s soak 33p/166t rss 13.1G pss 12.2G swap 0.6G majflt 2203 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 29.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 23.53 | cgroup 13.5G/max oom_kill 0 | free scratch 323.2G/45386085i tmp 28.3G/998054i workspace 323.2G/45386085i | repeat-01 collected 26/26 workers (60626 items) tests 29401 done 3 failed | 25 in flight, oldest 227s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................................... [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
........................................................................ [1370%]
...................................................................[contention-diag] +3242s soak 37p/169t rss 13.2G pss 12.2G swap 0.7G majflt 2204 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.2G pss 0.2G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 30.74 | cgroup 13.5G/max oom_kill 0 | free scratch 323.2G/45385129i tmp 28.3G/998054i workspace 323.2G/45385129i | repeat-01 collected 26/26 workers (60626 items) tests 29728 done 3 failed | 24 in flight, oldest 242s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
..... [1373%]
........................................................................ [1376%]
........................................................................ [1380%]
........................................................................ [1383%]
........................................................................ [1386%]
........................................................................ [1390%]
..................................................................[contention-diag] +3257s soak 33p/164t rss 13.1G pss 12.1G swap 0.6G majflt 2205 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 36.5 | cgroup 13.4G/max oom_kill 0 | free scratch 323.2G/45383972i tmp 28.3G/998054i workspace 323.2G/45383972i | repeat-01 collected 26/26 workers (60626 items) tests 30131 done 3 failed | 25 in flight, oldest 257s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...... [1393%]
........................................................................ [1396%]
........................................................................ [1400%]
........................................................................ [1403%]
........................................................................ [1406%]
........................................................................ [1410%]
........................................[contention-diag] +3273s soak 33p/161t rss 13.2G pss 12.2G swap 0.6G majflt 2206 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 30.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.64 cpu 33.63 | cgroup 13.7G/max oom_kill 0 | free scratch 323.1G/45382281i tmp 28.3G/998035i workspace 323.1G/45382281i | repeat-01 collected 26/26 workers (60626 items) tests 30548 done 3 failed | 25 in flight, oldest 273s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................ [1413%]
........................................................................ [1416%]
........................................................................ [1420%]
........................................................................ [1423%]
..............................................................[contention-diag] +3288s soak 36p/181t rss 13.2G pss 12.3G swap 0.6G majflt 2206 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 8 descendant rss 0.2G pss 0.2G | host avail 29.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 26.54 | cgroup 13.5G/max oom_kill 0 | free scratch 323.2G/45381672i tmp 28.3G/998035i workspace 323.2G/45381672i | repeat-01 collected 26/26 workers (60626 items) tests 30876 done 3 failed | 25 in flight, oldest 288s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.......... [1426%]
........................................................................ [1430%]
..............................................[contention-diag] +3304s soak 34p/166t rss 13.2G pss 12.2G swap 0.6G majflt 2207 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 6 descendant rss 0.1G pss 0.1G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 26.34 | cgroup 13.5G/max oom_kill 0 | free scratch 323.2G/45380892i tmp 28.3G/998035i workspace 323.2G/45380892i | repeat-01 collected 26/26 workers (60626 items) tests 31004 done 3 failed | 25 in flight, oldest 303s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.......................... [1433%]
........................................................................ [1436%]
.....................................................................[contention-diag] +3319s soak 37p/170t rss 13.2G pss 12.2G swap 0.6G majflt 2207 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.2G pss 0.1G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.13 cpu 34.02 | cgroup 13.5G/max oom_kill 0 | free scratch 323.2G/45380557i tmp 28.3G/998035i workspace 323.2G/45380557i | scratch used 0.5G in 98531 entries | repeat-01 collected 26/26 workers (60626 items) tests 31142 done 3 failed | 25 in flight, oldest 319s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
... [1440%]
........................................................................ [1443%]
........................................................................ [1446%]
........................................................................ [1449%]
........................................................................ [1453%]
........................................................................ [1456%]
............................[contention-diag] +3335s soak 33p/166t rss 13.3G pss 12.3G swap 0.6G majflt 2219 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 5 descendant rss 0.2G pss 0.1G | host avail 30.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.21 cpu 32.21 | cgroup 13.6G/max oom_kill 0 | free scratch 323.1G/45379299i tmp 28.3G/998035i workspace 323.1G/45379299i | repeat-01 collected 26/26 workers (60626 items) tests 31562 done 3 failed | 25 in flight, oldest 335s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................ [1459%]
........................................................................ [1463%]
........................................................................ [1466%]
........................................................................ [1469%]
........................................................................ [1473%]
...................................................[contention-diag] +3351s soak 37p/186t rss 13.3G pss 12.3G swap 0.6G majflt 2219 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 9 descendant rss 0.2G pss 0.2G | host avail 30.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 26.46 | cgroup 13.5G/max oom_kill 0 | free scratch 323.1G/45379207i tmp 28.3G/998035i workspace 323.1G/45379207i | repeat-01 collected 26/26 workers (60626 items) tests 31944 done 3 failed | 23 in flight, oldest 279s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
..................... [1476%]
........................................................................ [1479%]
........................................................................ [1483%]
........................................................................ [1486%]
........................................................................ [1489%]
........................................................................ [1493%]
........................................................................ [1496%]
........................................................................ [1499%]
........................................................................ [1503%]
.....[contention-diag] +3366s soak 34p/159t rss 13.2G pss 12.2G swap 0.6G majflt 2252 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 6 descendant rss 0.1G pss 0.1G | host avail 30.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 28.15 | cgroup 13.6G/max oom_kill 0 | free scratch 323.1G/45377581i tmp 28.3G/998035i workspace 323.1G/45377581i | repeat-01 collected 26/26 workers (60626 items) tests 32543 done 3 failed | 24 in flight, oldest 294s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................................................................... [1506%]
........................................................................ [1509%]
........................................................................ [1513%]
.............................................[contention-diag] +3381s soak 33p/156t rss 13.1G pss 12.2G swap 0.6G majflt 2220 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.7G pss 11.8G, 5 descendant rss 0.1G pss 0.0G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 27.84 | cgroup 13.5G/max oom_kill 0 | free scratch 322.3G/45376560i tmp 28.3G/998035i workspace 322.3G/45376560i | repeat-01 collected 26/26 workers (60626 items) tests 32791 done 3 failed | 24 in flight, oldest 309s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................... [1516%]
........................................................................ [1519%]
........................................................................ [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1533%]
.............................[contention-diag] +3397s soak 33p/170t rss 13.3G pss 12.3G swap 0.6G majflt 2223 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 29.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 29.23 | cgroup 13.5G/max oom_kill 0 | free scratch 322.3G/45375832i tmp 28.3G/998035i workspace 322.3G/45375832i | repeat-01 collected 26/26 workers (60626 items) tests 33213 done 3 failed | 24 in flight, oldest 325s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................................... [1536%]
........................................................................ [1539%]
........................................................................ [1543%]
........................................................................ [1546%]
[contention-diag] +3412s soak 33p/155t rss 13.3G pss 12.3G swap 0.6G majflt 2302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 5 descendant rss 0.2G pss 0.1G | host avail 28.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 24.87 | cgroup 13.6G/max oom_kill 0 | free scratch 322.1G/45374286i tmp 28.3G/998035i workspace 322.1G/45374286i | repeat-01 collected 26/26 workers (60626 items) tests 33460 done 3 failed | 23 in flight, oldest 340s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................................................................ [1549%]
........................................................................ [1553%]
........................................................................ [1556%]
........................................................................ [1559%]
........................................................................ [1563%]
........................................................................ [1566%]
...[contention-diag] +3427s soak 36p/165t rss 13.3G pss 12.3G swap 0.6G majflt 2302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 8 descendant rss 0.2G pss 0.1G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 24.93 | cgroup 13.7G/max oom_kill 0 | free scratch 322.1G/45373600i tmp 28.3G/998035i workspace 322.1G/45373600i | repeat-01 collected 26/26 workers (60626 items) tests 33899 done 3 failed | 24 in flight, oldest 355s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
..................................................................... [1569%]
........................................................................ [1573%]
........................................................................ [1576%]
.........s.............................[contention-diag] +3443s soak 39p/168t rss 13.5G pss 12.4G swap 0.6G majflt 2302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 11 descendant rss 0.3G pss 0.2G | host avail 32.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 28.47 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45372448i tmp 28.3G/998035i workspace 322.1G/45372448i | scratch used 0.6G in 106132 entries | repeat-01 collected 26/26 workers (60626 items) tests 34151 done 3 failed | 24 in flight, oldest 371s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................................. [1579%]
........................................................................ [1583%]
........................................................................ [1586%]
........................................................................ [1589%]
............................................[contention-diag] +3459s soak 36p/169t rss 13.4G pss 12.4G swap 0.6G majflt 2302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 8 descendant rss 0.3G pss 0.3G | host avail 31.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.07 cpu 30.87 | cgroup 13.9G/max oom_kill 0 | free scratch 322.1G/45371715i tmp 28.3G/998035i workspace 322.1G/45371715i | repeat-01 collected 26/26 workers (60626 items) tests 34458 done 3 failed | 24 in flight, oldest 387s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
............................ [1592%]
........................................................................ [1596%]
........................................................................ [1599%]
................................[contention-diag] +3474s soak 37p/170t rss 13.4G pss 12.4G swap 0.6G majflt 2302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 9 descendant rss 0.3G pss 0.2G | host avail 32.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.42 cpu 28.96 | cgroup 13.9G/max oom_kill 0 | free scratch 322.1G/45371296i tmp 28.3G/998035i workspace 322.1G/45371296i | repeat-01 collected 26/26 workers (60626 items) tests 34661 done 3 failed | 24 in flight, oldest 402s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
........................................ [1602%]
........................................................................ [1606%]
........................................................................ [1609%]
........................................................................ [1612%]
........................................................................ [1616%]
.................[contention-diag] +3490s soak 35p/173t rss 13.2G pss 12.2G swap 0.6G majflt 2302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 7 descendant rss 0.1G pss 0.0G | host avail 32.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 28.07 | cgroup 13.6G/max oom_kill 0 | free scratch 322.1G/45370462i tmp 28.3G/998035i workspace 322.1G/45370462i | repeat-01 collected 26/26 workers (60626 items) tests 35008 done 3 failed | 24 in flight, oldest 418s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
....................................................... [1619%]
........................................................................ [1622%]
........................................................................ [1626%]
........................................................................ [1629%]
.................................................[contention-diag] +3505s soak 33p/175t rss 13.3G pss 12.3G swap 0.6G majflt 2308 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 32.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.58 cpu 31.69 | cgroup 13.6G/max oom_kill 0 | free scratch 322.1G/45369531i tmp 28.3G/998035i workspace 322.1G/45369531i | repeat-01 collected 26/26 workers (60626 items) tests 35317 done 3 failed | 24 in flight, oldest 433s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
....................... [1632%]
........................................................................ [1636%]
........................................................................ [1639%]
........................................................................ [1642%]
........................................................................ [1646%]
.....................................................[contention-diag] +3520s soak 34p/178t rss 13.3G pss 12.3G swap 0.6G majflt 2308 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 6 descendant rss 0.1G pss 0.1G | host avail 32.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.5 cpu 40.1 | cgroup 13.7G/max oom_kill 0 | free scratch 322.1G/45368437i tmp 28.3G/998035i workspace 322.1G/45368437i | repeat-01 collected 26/26 workers (60626 items) tests 35687 done 3 failed | 24 in flight, oldest 448s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
................... [1649%]
........................................................................ [1652%]
........................................................................ [1656%]
........................................................................ [1659%]
......................................................................[contention-diag] +3536s soak 33p/164t rss 13.3G pss 12.3G swap 0.6G majflt 2308 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 30.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 29.0 | cgroup 13.7G/max oom_kill 0 | free scratch 322.1G/45367594i tmp 28.3G/998035i workspace 322.1G/45367594i | repeat-01 collected 26/26 workers (60626 items) tests 35992 done 3 failed | 24 in flight, oldest 329s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.. [1662%]
........................................................................ [1666%]
........................................................................ [1669%]
........................................................................ [1672%]
........................................................................ [1676%]
........................................................................ [1679%]
..................................................................[contention-diag] +3551s soak 36p/175t rss 13.3G pss 12.3G swap 0.7G majflt 2309 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 8 descendant rss 0.2G pss 0.1G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 26.39 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45366236i tmp 28.3G/998035i workspace 322.1G/45366236i | repeat-01 collected 26/26 workers (60626 items) tests 36422 done 3 failed | 24 in flight, oldest 344s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...... [1682%]
........................................................................ [1686%]
........................................................................ [1689%]
........................................................................ [1692%]
........................................................................ [1696%]
........................................................................ [1699%]
............................................[contention-diag] +3566s soak 32p/177t rss 13.3G pss 12.3G swap 0.6G majflt 2326 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 4 descendant rss 0.1G pss 0.0G | host avail 32.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 24.29 | cgroup 13.7G/max oom_kill 0 | free scratch 322.1G/45364912i tmp 28.3G/998035i workspace 322.1G/45364912i | scratch used 0.6G in 113763 entries | repeat-01 collected 26/26 workers (60626 items) tests 36819 done 3 failed | 24 in flight, oldest 359s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1702%]
........................................................................ [1706%]
........................................................................ [1709%]
........................................................................ [1712%]
........................................................................ [1716%]
..................................[contention-diag] +3583s soak 34p/185t rss 13.3G pss 12.3G swap 0.6G majflt 2330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.8G pss 11.9G, 6 descendant rss 0.1G pss 0.1G | host avail 32.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 28.87 | cgroup 13.7G/max oom_kill 0 | free scratch 322.1G/45363562i tmp 28.3G/998035i workspace 322.1G/45363562i | repeat-01 collected 26/26 workers (60626 items) tests 37183 done 3 failed | 24 in flight, oldest 376s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...................................... [1719%]
........................................................................ [1722%]
........................................................................ [1726%]
........................................................................ [1729%]
...........[contention-diag] +3598s soak 36p/184t rss 13.4G pss 12.4G swap 0.6G majflt 2330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 8 descendant rss 0.2G pss 0.1G | host avail 32.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 26.85 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45362813i tmp 28.3G/998035i workspace 322.1G/45362813i | repeat-01 collected 26/26 workers (60626 items) tests 37446 done 3 failed | 24 in flight, oldest 391s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................................................. [1732%]
........................................................................ [1735%]
........................................................................ [1739%]
..................................[contention-diag] +3614s soak 32p/179t rss 13.3G pss 12.3G swap 0.6G majflt 2330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 31.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.4 cpu 28.42 | cgroup 13.7G/max oom_kill 0 | free scratch 322.1G/45362135i tmp 28.3G/998035i workspace 322.1G/45362135i | repeat-01 collected 26/26 workers (60626 items) tests 37683 done 3 failed | 24 in flight, oldest 406s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...................................... [1742%]
........................................................................ [1745%]
........................................................................ [1749%]
.............................................[contention-diag] +3629s soak 34p/181t rss 13.4G pss 12.3G swap 0.6G majflt 2330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 6 descendant rss 0.1G pss 0.1G | host avail 32.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.5 cpu 27.81 | cgroup 13.8G/max oom_kill 0 | free scratch 322.1G/45361081i tmp 28.3G/998035i workspace 322.1G/45361081i | repeat-01 collected 26/26 workers (60626 items) tests 37907 done 3 failed | 24 in flight, oldest 422s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
........................... [1752%]
........................................................................ [1755%]
........................................................................ [1759%]
......................................................[contention-diag] +3644s soak 41p/204t rss 13.5G pss 12.4G swap 0.6G majflt 2330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 13 descendant rss 0.2G pss 0.2G | host avail 32.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.48 cpu 34.15 | cgroup 13.9G/max oom_kill 0 | free scratch 322.1G/45360409i tmp 28.3G/998035i workspace 322.1G/45360409i | repeat-01 collected 26/26 workers (60626 items) tests 38141 done 3 failed | 24 in flight, oldest 437s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.................. [1762%]
.......s................................................................ [1765%]
..................................s..................................... [1769%]
........................................................................ [1772%]
........................................................................ [1775%]
........................................................................ [1779%]
...................[contention-diag] +3660s soak 39p/212t rss 13.5G pss 12.4G swap 0.6G majflt 2331 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 11 descendant rss 0.2G pss 0.2G | host avail 30.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 31.52 | cgroup 13.9G/max oom_kill 0 | free scratch 322.1G/45359138i tmp 28.3G/998035i workspace 322.1G/45359138i | repeat-01 collected 26/26 workers (60626 items) tests 38520 done 3 failed | 24 in flight, oldest 316s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 8 hazardous kill call(s)
..................................................... [1782%]
............................................................s........... [1785%]
........................................................................ [1789%]
...................................................................[contention-diag] +3675s soak 37p/199t rss 13.6G pss 12.6G swap 0.6G majflt 2333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.4G pss 0.3G | host avail 28.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 30.17 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45358690i tmp 28.3G/998035i workspace 322.1G/45358690i | repeat-01 collected 26/26 workers (60626 items) tests 38793 done 3 failed | 24 in flight, oldest 293s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..... [1792%]
........................................................................ [1795%]
........................................................................ [1799%]
........[contention-diag] +3690s soak 36p/186t rss 13.7G pss 12.6G swap 0.6G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 8 descendant rss 0.4G pss 0.4G | host avail 30.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 31.97 | cgroup 14.1G/max oom_kill 0 | free scratch 322.1G/45358067i tmp 28.3G/998035i workspace 322.1G/45358067i | scratch used 0.6G in 120491 entries | repeat-01 collected 26/26 workers (60626 items) tests 38937 done 3 failed | 23 in flight, oldest 308s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................................ [1802%]
........................................................................ [1805%]
........................................................................ [1809%]
........................................................................ [1812%]
...............................................[contention-diag] +3707s soak 34p/187t rss 13.6G pss 12.5G swap 0.6G majflt 2385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 6 descendant rss 0.3G pss 0.3G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 30.6 | cgroup 14.0G/max oom_kill 0 | free scratch 322.1G/45357337i tmp 28.3G/998035i workspace 322.1G/45357337i | repeat-01 collected 26/26 workers (60626 items) tests 39284 done 3 failed | 24 in flight, oldest 325s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
......................... [1815%]
........................................................................ [1819%]
........................................................................ [1822%]
........................................................................ [1825%]
.....................[contention-diag] +3722s soak 38p/190t rss 13.6G pss 12.6G swap 0.6G majflt 2385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 10 descendant rss 0.4G pss 0.3G | host avail 30.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 30.02 | cgroup 14.1G/max oom_kill 0 | free scratch 322.0G/45356570i tmp 28.3G/998035i workspace 322.0G/45356570i | repeat-01 collected 26/26 workers (60626 items) tests 39537 done 3 failed | 24 in flight, oldest 340s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................... [1829%]
........................................................................ [1832%]
........................................................................ [1835%]
...............................[contention-diag] +3738s soak 37p/193t rss 13.4G pss 12.4G swap 0.6G majflt 2385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.2G pss 0.2G | host avail 31.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 32.17 | cgroup 14.5G/max oom_kill 0 | free scratch 321.8G/45355595i tmp 28.3G/998035i workspace 321.8G/45355595i | repeat-01 collected 26/26 workers (60626 items) tests 39763 done 3 failed | 24 in flight, oldest 355s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
......................................... [1839%]
........................................................................ [1842%]
..............................................................[contention-diag] +3753s soak 37p/189t rss 13.6G pss 12.6G swap 0.6G majflt 2385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 9 descendant rss 0.3G pss 0.3G | host avail 30.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 28.66 | cgroup 14.7G/max oom_kill 0 | free scratch 321.7G/45355449i tmp 28.3G/998035i workspace 321.7G/45355449i | repeat-01 collected 26/26 workers (60626 items) tests 39944 done 3 failed | 24 in flight, oldest 371s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1845%]
........................................................................ [1849%]
........................................................................ [1852%]
........................................................................ [1855%]
........................................................................ [1859%]
......................................................[contention-diag] +3768s soak 35p/185t rss 13.6G pss 12.5G swap 0.6G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 7 descendant rss 0.3G pss 0.2G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.08 cpu 27.83 | cgroup 14.7G/max oom_kill 0 | free scratch 321.5G/45355006i tmp 28.3G/998035i workspace 321.5G/45355006i | repeat-01 collected 26/26 workers (60626 items) tests 40289 done 3 failed | 23 in flight, oldest 386s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................. [1862%]
........................................................................ [1865%]
........................................................................ [1869%]
........................................................................ [1872%]
........................................................................ [1875%]
...........................................[contention-diag] +3784s soak 39p/192t rss 13.8G pss 12.7G swap 0.6G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 11.9G, 11 descendant rss 0.5G pss 0.4G | host avail 29.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.24 cpu 26.02 | cgroup 14.4G/max oom_kill 0 | free scratch 322.0G/45353281i tmp 28.3G/998035i workspace 322.0G/45353281i | repeat-01 collected 26/26 workers (60626 items) tests 40644 done 3 failed | 24 in flight, oldest 401s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................. [1878%]
........................................................................ [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
..............................................................[contention-diag] +3799s soak 48p/202t rss 13.9G pss 12.8G swap 0.7G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.9G pss 12.0G, 20 descendant rss 0.6G pss 0.5G | host avail 27.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.55 cpu 24.44 | cgroup 14.5G/max oom_kill 0 | free scratch 322.0G/45350073i tmp 28.3G/998035i workspace 322.0G/45350073i | repeat-01 collected 26/26 workers (60626 items) tests 40956 done 3 failed | 24 in flight, oldest 417s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.s........ [1892%]
........................................................................ [1895%]
........................................................................ [1898%]
........................................................................ [1902%]
..........................................................[contention-diag] +3814s soak 38p/202t rss 13.8G pss 12.6G swap 0.6G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 10 descendant rss 0.4G pss 0.3G | host avail 29.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.96 cpu 26.04 | cgroup 14.3G/max oom_kill 0 | free scratch 321.9G/45331520i tmp 28.3G/998035i workspace 321.9G/45331520i | scratch used 0.7G in 128272 entries | repeat-01 collected 26/26 workers (60626 items) tests 41221 done 3 failed | 24 in flight, oldest 432s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............. [1905%]
........................................................................ [1908%]
........................................................................ [1912%]
........................................................................ [1915%]
................................[contention-diag] +3831s soak 37p/175t rss 13.8G pss 12.7G swap 0.6G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 9 descendant rss 0.4G pss 0.4G | host avail 30.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.31 cpu 25.61 | cgroup 14.3G/max oom_kill 0 | free scratch 321.9G/45329005i tmp 28.3G/998035i workspace 321.9G/45329005i | repeat-01 collected 26/26 workers (60626 items) tests 41497 done 3 failed | 24 in flight, oldest 158s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........................................ [1918%]
........................................................................ [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
........................................................................ [1935%]
........................................................................ [1938%]
.................................[contention-diag] +3846s soak 40p/174t rss 13.8G pss 12.7G swap 0.6G majflt 2386 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 12 descendant rss 0.5G pss 0.4G | host avail 29.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.38 cpu 26.89 | cgroup 14.3G/max oom_kill 0 | free scratch 321.9G/45327079i tmp 28.3G/998035i workspace 321.9G/45327079i | repeat-01 collected 26/26 workers (60626 items) tests 42003 done 3 failed | 24 in flight, oldest 173s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
....................................... [1942%]
........................................................................ [1945%]
........................................................................ [1948%]
........................................................................ [1952%]
......................................................................[contention-diag] +3862s soak 37p/185t rss 13.9G pss 12.7G swap 0.6G majflt 2557 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 9 descendant rss 0.5G pss 0.4G | host avail 29.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.6 cpu 28.3 | cgroup 14.5G/max oom_kill 0 | free scratch 321.9G/45326368i tmp 28.3G/998035i workspace 321.9G/45326368i | repeat-01 collected 26/26 workers (60626 items) tests 42314 done 3 failed | 24 in flight, oldest 189s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.. [1955%]
........................................................................ [1958%]
........................................................................ [1962%]
........................................................................ [1965%]
.......................................[contention-diag] +3877s soak 37p/198t rss 13.8G pss 12.8G swap 0.6G majflt 2391 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 9 descendant rss 0.5G pss 0.4G | host avail 30.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 2.55 cpu 27.42 | cgroup 14.5G/max oom_kill 0 | free scratch 321.9G/45324604i tmp 28.3G/998035i workspace 321.9G/45324604i | repeat-01 collected 26/26 workers (60626 items) tests 42582 done 3 failed | 24 in flight, oldest 204s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................. [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
........................................................................ [1978%]
....................................................................[contention-diag] +3892s soak 37p/192t rss 13.9G pss 12.9G swap 0.6G majflt 2391 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 9 descendant rss 0.6G pss 0.5G | host avail 30.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.94 cpu 28.84 | cgroup 14.6G/max oom_kill 0 | free scratch 321.9G/45324493i tmp 28.3G/998035i workspace 321.9G/45324493i | repeat-01 collected 26/26 workers (60626 items) tests 42905 done 3 failed | 23 in flight, oldest 220s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.... [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
........................................................................ [1992%]
........................................................................ [1995%]
........................................................................ [1998%]
........................................................................ [2002%]
...[contention-diag] +3908s soak 41p/195t rss 14.0G pss 12.9G swap 0.7G majflt 2393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 13 descendant rss 0.7G pss 0.6G | host avail 28.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.86 cpu 25.34 | cgroup 14.7G/max oom_kill 0 | free scratch 321.9G/45323224i tmp 28.3G/998035i workspace 321.9G/45323224i | repeat-01 collected 26/26 workers (60626 items) tests 43344 done 3 failed | 23 in flight, oldest 235s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
..................................................................... [2005%]
........................................................................ [2008%]
........................................................................ [2012%]
........................................................................ [2015%]
........................................................................ [2018%]
..................................................[contention-diag] +3923s soak 41p/206t rss 14.3G pss 13.1G swap 0.7G majflt 2393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 13 descendant rss 0.9G pss 0.7G | host avail 28.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.79 cpu 24.86 | cgroup 14.9G/max oom_kill 0 | free scratch 321.9G/45319925i tmp 28.3G/998035i workspace 321.9G/45319925i | repeat-01 collected 26/26 workers (60626 items) tests 43748 done 3 failed | 23 in flight, oldest 250s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
...................... [2021%]
........................................................................ [2025%]
........................................................................ [2028%]
........................................................................ [2031%]
..................................................[contention-diag] +3938s soak 42p/201t rss 14.2G pss 13.0G swap 0.6G majflt 2393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 14 descendant rss 0.7G pss 0.6G | host avail 29.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 26.05 | cgroup 14.8G/max oom_kill 0 | free scratch 321.8G/45303255i tmp 28.3G/998035i workspace 321.8G/45303255i | scratch used 0.7G in 136175 entries | repeat-01 collected 26/26 workers (60626 items) tests 43993 done 3 failed | 23 in flight, oldest 266s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
...................... [2035%]
........................................................................ [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
.......................................................[contention-diag] +3955s soak 45p/210t rss 14.2G pss 13.0G swap 0.7G majflt 2393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 17 descendant rss 0.7G pss 0.6G | host avail 30.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.82 cpu 28.5 | cgroup 14.8G/max oom_kill 0 | free scratch 321.8G/45301179i tmp 28.3G/998035i workspace 321.8G/45301179i | repeat-01 collected 26/26 workers (60626 items) tests 44403 done 3 failed | 21 in flight, oldest 282s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................. [2051%]
........................................................................ [2055%]
........................................................................ [2058%]
........................................................................ [2061%]
......................[contention-diag] +3970s soak 38p/185t rss 14.2G pss 13.1G swap 0.6G majflt 2393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.0G pss 12.0G, 10 descendant rss 0.7G pss 0.7G | host avail 29.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.01 cpu 29.51 | cgroup 14.9G/max oom_kill 0 | free scratch 321.8G/45300066i tmp 28.3G/998035i workspace 321.8G/45300066i | repeat-01 collected 26/26 workers (60626 items) tests 44653 done 3 failed | 21 in flight, oldest 298s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.................................................. [2065%]
........................................................................ [2068%]
........................................................................ [2071%]
.............[contention-diag] +3986s soak 41p/194t rss 14.3G pss 13.1G swap 0.7G majflt 2394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 13 descendant rss 0.8G pss 0.7G | host avail 28.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.04 cpu 26.9 | cgroup 15.0G/max oom_kill 0 | free scratch 321.8G/45299504i tmp 28.3G/998033i workspace 321.8G/45299504i | repeat-01 collected 26/26 workers (60626 items) tests 44868 done 3 failed | 22 in flight, oldest 313s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........................................................... [2075%]
........................................................................ [2078%]
........................................................................ [2081%]
........................................................................ [2085%]
.......................................................................s [2088%]
........................................................................ [2091%]
................................................................[contention-diag] +4001s soak 39p/189t rss 14.3G pss 13.2G swap 0.7G majflt 2393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.0G, 11 descendant rss 0.9G pss 0.8G | host avail 29.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.16 cpu 24.22 | cgroup 15.0G/max oom_kill 0 | free scratch 321.8G/45298406i tmp 28.3G/998033i workspace 321.8G/45298405i | repeat-01 collected 26/26 workers (60626 items) tests 45346 done 3 failed | 22 in flight, oldest 284s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........ [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
........................................................................ [2105%]
........................................................................ [2108%]
........................................................................ [2111%]
.........................................................[contention-diag] +4017s soak 36p/189t rss 14.2G pss 13.1G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.1G pss 12.1G, 8 descendant rss 0.7G pss 0.7G | host avail 29.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.47 cpu 23.69 | cgroup 14.9G/max oom_kill 0 | free scratch 321.8G/45296840i tmp 28.3G/998032i workspace 321.8G/45296840i | repeat-01 collected 26/26 workers (60626 items) tests 45737 done 3 failed | 21 in flight, oldest 299s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............... [2115%]
........................................................................ [2118%]
........................................................................ [2121%]
........................................................................ [2125%]
........................................................................ [2128%]
........................................................................ [2131%]
........................................................................ [2135%]
....................................................[contention-diag] +4032s soak 35p/190t rss 14.2G pss 13.1G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 7 descendant rss 0.7G pss 0.7G | host avail 28.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.76 cpu 22.9 | cgroup 15.0G/max oom_kill 0 | free scratch 321.8G/45295632i tmp 28.3G/998032i workspace 321.8G/45295632i | repeat-01 collected 26/26 workers (60626 items) tests 46232 done 3 failed | 22 in flight, oldest 314s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................... [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........................................................................ [2155%]
.................................................................[contention-diag] +4047s soak 38p/193t rss 14.5G pss 13.4G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 10 descendant rss 1.0G pss 0.9G | host avail 29.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.28 cpu 23.67 | cgroup 15.2G/max oom_kill 0 | free scratch 321.8G/45294903i tmp 28.3G/998032i workspace 321.8G/45294903i | repeat-01 collected 26/26 workers (60626 items) tests 46687 done 3 failed | 22 in flight, oldest 330s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
....... [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
........................................................................ [2168%]
........................................................................ [2171%]
........................................................................ [2174%]
........................................................................ [2178%]
......................................[contention-diag] +4063s soak 38p/190t rss 14.6G pss 13.5G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 10 descendant rss 1.1G pss 1.0G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 25.66 | cgroup 15.4G/max oom_kill 0 | free scratch 321.7G/45293700i tmp 28.3G/998032i workspace 321.7G/45293700i | scratch used 0.7G in 143826 entries | repeat-01 collected 26/26 workers (60626 items) tests 47153 done 3 failed | 22 in flight, oldest 345s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................. [2181%]
........................................................................ [2184%]
........................................................................ [2188%]
........................................................................ [2191%]
........................................................................ [2194%]
............................................[contention-diag] +4080s soak 35p/184t rss 14.5G pss 13.4G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 7 descendant rss 1.0G pss 0.9G | host avail 30.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.36 cpu 24.64 | cgroup 15.3G/max oom_kill 0 | free scratch 321.7G/45293047i tmp 28.3G/998037i workspace 321.7G/45293047i | repeat-01 collected 26/26 workers (60626 items) tests 47562 done 3 failed | 21 in flight, oldest 362s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................ [2198%]
........................................................................ [2201%]
........................................................................ [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2218%]
........................................................................ [2221%]
...........................................................[contention-diag] +4095s soak 36p/168t rss 14.5G pss 13.4G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 8 descendant rss 0.9G pss 0.9G | host avail 30.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.49 cpu 22.5 | cgroup 15.3G/max oom_kill 0 | free scratch 321.7G/45285000i tmp 28.3G/998036i workspace 321.7G/45285000i | repeat-01 collected 26/26 workers (60626 items) tests 48155 done 3 failed | 21 in flight, oldest 377s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............. [2224%]
........................................................................ [2228%]
........................................................................ [2231%]
........................................................................ [2234%]
..................................................................[contention-diag] +4110s soak 36p/174t rss 14.5G pss 13.4G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 8 descendant rss 0.9G pss 0.9G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.36 cpu 18.8 | cgroup 15.3G/max oom_kill 0 | free scratch 321.7G/45291491i tmp 28.3G/998036i workspace 321.7G/45291491i | repeat-01 collected 26/26 workers (60626 items) tests 48433 done 3 failed | 20 in flight, oldest 393s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...... [2238%]
........................................................................ [2241%]
........................................................................ [2244%]
........................................................................ [2248%]
........................................................................ [2251%]
........................................[contention-diag] +4126s soak 39p/178t rss 14.6G pss 13.5G swap 0.6G majflt 2404 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.1G pss 0.9G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.28 cpu 13.88 | cgroup 15.4G/max oom_kill 0 | free scratch 321.5G/45289290i tmp 28.3G/998036i workspace 321.5G/45289290i | repeat-01 collected 26/26 workers (60626 items) tests 48773 done 3 failed | 20 in flight, oldest 408s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................ [2254%]
........................................................................ [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
...............................[contention-diag] +4141s soak 41p/201t rss 14.9G pss 13.7G swap 0.6G majflt 2416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 13 descendant rss 1.3G pss 1.2G | host avail 29.4G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.49 cpu 18.75 | cgroup 15.7G/max oom_kill 0 | free scratch 321.4G/45288411i tmp 28.3G/998036i workspace 321.4G/45288411i | repeat-01 collected 26/26 workers (60626 items) tests 49122 done 3 failed | 19 in flight, oldest 418s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
......................................... [2271%]
........................................................................ [2274%]
........................................................................ [2278%]
........................................................................ [2281%]
..[contention-diag] +4157s soak 39p/176t rss 14.8G pss 13.7G swap 0.6G majflt 2406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 1.2G pss 1.2G | host avail 30.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 2.72 cpu 18.08 | cgroup 15.7G/max oom_kill 0 | free scratch 321.2G/45287547i tmp 28.3G/998036i workspace 321.2G/45287547i | repeat-01 collected 26/26 workers (60626 items) tests 49386 done 3 failed | 19 in flight, oldest 433s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................................................... [2284%]
........................................................................ [2288%]
........................................................................ [2291%]
........................................................................ [2294%]
........................................................................ [2298%]
........................................................................ [2301%]
........................................................................ [2304%]
..........................................[contention-diag] +4172s soak 42p/203t rss 15.1G pss 13.9G swap 0.6G majflt 2406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 14 descendant rss 1.5G pss 1.4G | host avail 27.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.93 cpu 19.09 | cgroup 15.9G/max oom_kill 0 | free scratch 321.1G/45286085i tmp 28.3G/998036i workspace 321.1G/45286085i | repeat-01 collected 26/26 workers (60626 items) tests 49917 done 3 failed | 19 in flight, oldest 449s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................. [2307%]
........................................................................ [2311%]
........................................................................ [2314%]
........................................................................ [2317%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
..............[contention-diag] +4188s soak 41p/185t rss 14.7G pss 13.6G swap 0.6G majflt 2408 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 13 descendant rss 1.1G pss 1.0G | host avail 24.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.48/0.3 io 1.63 cpu 16.86 | cgroup 15.6G/max oom_kill 0 | free scratch 321.0G/45284924i tmp 28.3G/998036i workspace 321.0G/45284924i | scratch used 0.8G in 151102 entries | repeat-01 collected 26/26 workers (60626 items) tests 50330 done 3 failed | 19 in flight, oldest 465s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......................................................... [2331%]
........................................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2341%]
........................................................................ [2344%]
.................................................................s...... [2347%]
........................................................................ [2351%]
.....[contention-diag] +4205s soak 41p/177t rss 14.6G pss 13.4G swap 0.6G majflt 2408 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 13 descendant rss 1.0G pss 1.0G | host avail 28.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.09/0.06 io 3.75 cpu 20.21 | cgroup 15.5G/max oom_kill 0 | free scratch 320.8G/45282660i tmp 28.3G/998036i workspace 320.8G/45282660i | repeat-01 collected 26/26 workers (60626 items) tests 50902 done 3 failed | 19 in flight, oldest 482s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................... [2354%]
........................................................................ [2357%]
........................................................................ [2361%]
.....................................................................[contention-diag] +4220s soak 39p/180t rss 14.7G pss 13.5G swap 0.6G majflt 2412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.1G pss 12.1G, 11 descendant rss 1.1G pss 1.0G | host avail 27.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 4.26 cpu 23.4 | cgroup 15.7G/max oom_kill 0 | free scratch 320.7G/45282494i tmp 28.3G/998036i workspace 320.7G/45282494i | repeat-01 collected 26/26 workers (60626 items) tests 51174 done 3 failed | 17 in flight, oldest 497s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
... [2364%]
........................................................................ [2367%]
........................................................................ [2371%]
........................................................................ [2374%]
........................................................................ [2377%]
........................................................................ [2381%]
................[contention-diag] +4236s soak 47p/191t rss 15.1G pss 13.8G swap 0.7G majflt 2412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 19 descendant rss 1.5G pss 1.3G | host avail 27.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.78 cpu 19.21 | cgroup 16.0G/max oom_kill 0 | free scratch 320.6G/45281303i tmp 28.3G/998036i workspace 320.6G/45281303i | repeat-01 collected 26/26 workers (60626 items) tests 51565 done 3 failed | 18 in flight, oldest 512s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................ [2384%]
........................................................................ [2387%]
........................................................................ [2391%]
........................................................................ [2394%]
........................................................................ [2397%]
.....[contention-diag] +4251s soak 38p/185t rss 14.8G pss 13.6G swap 0.7G majflt 2412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 1.2G pss 1.1G | host avail 30.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.02 cpu 16.91 | cgroup 15.8G/max oom_kill 0 | free scratch 320.3G/45279990i tmp 28.3G/998036i workspace 320.3G/45279990i | repeat-01 collected 26/26 workers (60626 items) tests 51845 done 3 failed | 17 in flight, oldest 528s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................... [2401%]
........................................................................ [2404%]
........................................................................ [2407%]
........................................................................ [2411%]
........................................................................ [2414%]
........................................................................ [2417%]
..................................................................[contention-diag] +4267s soak 33p/164t rss 14.5G pss 13.4G swap 0.6G majflt 2412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 5 descendant rss 0.9G pss 0.9G | host avail 31.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.99 cpu 23.61 | cgroup 15.7G/max oom_kill 0 | free scratch 320.2G/45278222i tmp 28.3G/998036i workspace 320.2G/45278222i | repeat-01 collected 26/26 workers (60626 items) tests 52407 done 3 failed | 18 in flight, oldest 543s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
...... [2421%]
........................................................................ [2424%]
........................................................................ [2427%]
........................................................................ [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
....................................................................[contention-diag] +4282s soak 38p/168t rss 14.7G pss 13.5G swap 0.6G majflt 2412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 1.1G pss 1.0G | host avail 30.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.24 cpu 25.4 | cgroup 15.8G/max oom_kill 0 | free scratch 320.2G/45277401i tmp 28.3G/998036i workspace 320.2G/45277401i | repeat-01 collected 26/26 workers (60626 items) tests 52812 done 3 failed | 18 in flight, oldest 559s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.... [2441%]
........................................................................ [2444%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2454%]
........................................................................ [2457%]
.....................................................[contention-diag] +4297s soak 34p/164t rss 14.6G pss 13.5G swap 0.6G majflt 2413 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 1.0G pss 0.9G | host avail 28.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.62 cpu 22.1 | cgroup 15.7G/max oom_kill 0 | free scratch 320.2G/45276276i tmp 28.3G/998036i workspace 320.2G/45276276i | repeat-01 collected 26/26 workers (60626 items) tests 53224 done 3 failed | 18 in flight, oldest 574s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................... [2460%]
........................................................................ [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
........................................................................ [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
.............................................................[contention-diag] +4313s soak 44p/183t rss 14.7G pss 13.5G swap 0.6G majflt 2413 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 16 descendant rss 1.1G pss 0.9G | host avail 26.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.7 cpu 19.63 | cgroup 15.7G/max oom_kill 0 | free scratch 320.2G/45274676i tmp 28.3G/998036i workspace 320.2G/45274676i | scratch used 0.8G in 160697 entries | repeat-01 collected 26/26 workers (60626 items) tests 53837 done 3 failed | 18 in flight, oldest 589s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........... [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
........................................................................ [2507%]
........................................................................ [2510%]
........................................................................ [2514%]
........................................................................ [2517%]
........................................................................ [2520%]
........................................................................ [2524%]
........................................................................ [2527%]
..[contention-diag] +4330s soak 35p/173t rss 13.8G pss 12.7G swap 0.6G majflt 2414 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.2G pss 0.1G | host avail 28.3G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 2.84 cpu 24.76 | cgroup 15.0G/max oom_kill 0 | free scratch 320.2G/45272799i tmp 28.3G/998036i workspace 320.2G/45272799i | repeat-01 collected 26/26 workers (60626 items) tests 54673 done 3 failed | 17 in flight, oldest 77s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
...................................................................... [2530%]
........................................................................ [2534%]
........................................................................ [2537%]
........................................................................ [2540%]
........................................................................ [2544%]
...........................................................s............ [2547%]
............[contention-diag] +4345s soak 39p/179t rss 14.0G pss 12.8G swap 0.6G majflt 2418 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 11 descendant rss 0.3G pss 0.3G | host avail 26.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 2.03 cpu 21.96 | cgroup 15.1G/max oom_kill 0 | free scratch 320.0G/45272478i tmp 28.3G/998035i workspace 320.0G/45272478i | repeat-01 collected 26/26 workers (60626 items) tests 55126 done 3 failed | 15 in flight, oldest 92s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............................................................ [2550%]
........................................................................ [2554%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2564%]
........................................................................ [2567%]
........................................................................ [2570%]
...................................[contention-diag] +4361s soak 35p/159t rss 13.8G pss 12.7G swap 0.6G majflt 2419 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 7 descendant rss 0.1G pss 0.1G | host avail 31.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.02 cpu 18.7 | cgroup 15.0G/max oom_kill 0 | free scratch 319.9G/45271433i tmp 28.3G/998036i workspace 319.9G/45271435i | repeat-01 collected 26/26 workers (60626 items) tests 55633 done 3 failed | 15 in flight, oldest 107s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
..................................... [2574%]
........................................................................ [2577%]
........................................................................ [2580%]
........................................................................ [2584%]
..............[contention-diag] +4376s soak 40p/171t rss 13.9G pss 12.8G swap 0.6G majflt 2419 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 12 descendant rss 0.3G pss 0.2G | host avail 30.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 12.14 | cgroup 15.1G/max oom_kill 0 | free scratch 319.9G/45270174i tmp 28.3G/998036i workspace 319.9G/45270174i | repeat-01 collected 26/26 workers (60626 items) tests 55957 done 3 failed | 15 in flight, oldest 123s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.......................................................... [2587%]
........................................................................ [2590%]
........................................................................ [2593%]
.......................s................................................ [2597%]
........................................................................ [2600%]
...[contention-diag] +4392s soak 43p/194t rss 14.3G pss 13.1G swap 0.6G majflt 2423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 15 descendant rss 0.6G pss 0.5G | host avail 31.5G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 15.04 | cgroup 15.4G/max oom_kill 0 | free scratch 319.9G/45256823i tmp 28.3G/998026i workspace 319.9G/45256823i | repeat-01 collected 26/26 workers (60626 items) tests 56304 done 3 failed | 14 in flight, oldest 138s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
..................................................................... [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
...[contention-diag] +4407s soak 41p/172t rss 14.2G pss 13.0G swap 0.7G majflt 2423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 13 descendant rss 0.6G pss 0.5G | host avail 25.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 2.71/2.53 io 9.34 cpu 11.75 | cgroup 15.3G/max oom_kill 0 | free scratch 319.6G/45242206i tmp 28.3G/997659i workspace 319.6G/45242206i | repeat-01 collected 26/26 workers (60626 items) tests 56590 done 3 failed | 14 in flight, oldest 154s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
..................................................................... [2617%]
........................................................................ [2620%]
........................................................................ [2623%]
........................................................................ [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
........................................................................ [2637%]
.........................................[contention-diag] +4423s soak 38p/166t rss 14.3G pss 13.1G swap 0.7G majflt 2423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 0.7G pss 0.5G | host avail 31.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.95/0.86 io 4.37 cpu 18.36 | cgroup 15.3G/max oom_kill 0 | free scratch 319.6G/45240046i tmp 28.3G/997982i workspace 319.6G/45240046i | repeat-01 collected 26/26 workers (60626 items) tests 57135 done 3 failed | 13 in flight, oldest 72s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................... [2640%]
........................................................................ [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
........................................................................ [2657%]
........................................................................ [2660%]
....................................[contention-diag] +4438s soak 34p/157t rss 13.9G pss 12.8G swap 0.6G majflt 2423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 0.3G pss 0.3G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.17 io 2.5 cpu 19.25 | cgroup 15.1G/max oom_kill 0 | free scratch 319.6G/45238692i tmp 28.3G/997982i workspace 319.6G/45238692i | scratch used 0.9G in 167247 entries | repeat-01 collected 26/26 workers (60626 items) tests 57550 done 3 failed | 13 in flight, oldest 87s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.................................... [2663%]
........................................................................ [2667%]
........................................................................ [2670%]
........................................................................ [2673%]
........................................................................ [2677%]
........................................................................ [2680%]
............................[contention-diag] +4455s soak 38p/167t rss 13.9G pss 12.7G swap 0.6G majflt 2424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 10 descendant rss 0.2G pss 0.2G | host avail 33.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.76 cpu 25.22 | cgroup 15.1G/max oom_kill 0 | free scratch 319.6G/45237605i tmp 28.3G/997982i workspace 319.6G/45237605i | repeat-01 collected 26/26 workers (60626 items) tests 58053 done 3 failed | 13 in flight, oldest 104s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................................ [2683%]
........................................................................ [2687%]
........................................................................ [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
........................................................................ [2700%]
........................................................................ [2703%]
......s................................................................. [2707%]
........[contention-diag] +4471s soak 34p/153t rss 13.9G pss 12.8G swap 0.6G majflt 2425 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 0.3G pss 0.2G | host avail 32.1G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.34 cpu 20.32 | cgroup 15.0G/max oom_kill 0 | free scratch 319.6G/45238284i tmp 28.3G/998010i workspace 319.6G/45238284i | repeat-01 collected 26/26 workers (60626 items) tests 58614 done 3 failed | 10 in flight, oldest 120s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................................................................ [2710%]
........................................................................ [2713%]
........................................................................ [2717%]
........................................................................ [2720%]
.................................[contention-diag] +4486s soak 37p/160t rss 13.7G pss 12.6G swap 0.6G majflt 2426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.1G pss 0.0G | host avail 31.6G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.26 cpu 18.57 | cgroup 14.9G/max oom_kill 0 | free scratch 319.6G/45239068i tmp 28.3G/998010i workspace 319.6G/45239068i | repeat-01 collected 26/26 workers (60626 items) tests 58921 done 3 failed | 8 in flight, oldest 135s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
....................................... [2723%]
........................................................................ [2727%]
........................................................................ [2730%]
........................................................................ [2733%]
........................................................................ [2736%]
........................................................................ [2740%]
..............................................[contention-diag] +4501s soak 37p/164t rss 13.7G pss 12.6G swap 0.6G majflt 2426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 9 descendant rss 0.1G pss 0.0G | host avail 32.2G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.24/0.24 io 1.31 cpu 15.27 | cgroup 14.9G/max oom_kill 0 | free scratch 319.6G/45238160i tmp 28.3G/998010i workspace 319.6G/45238160i | repeat-01 collected 26/26 workers (60626 items) tests 59364 done 3 failed | 8 in flight, oldest 24s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.......................... [2743%]
........................................................................ [2746%]
........................................................................ [2750%]
........................................................................ [2753%]
......................................................[contention-diag] +4517s soak 36p/157t rss 13.7G pss 12.6G swap 0.6G majflt 2426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 8 descendant rss 0.0G pss 0.0G | host avail 33.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 3.05 cpu 20.32 | cgroup 14.9G/max oom_kill 0 | free scratch 319.6G/45238069i tmp 28.3G/998010i workspace 319.6G/45238069i | repeat-01 collected 26/26 workers (60626 items) tests 59655 done 3 failed | 6 in flight, oldest 39s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.................. [2756%]
........................................................................ [2760%]
........................................................................ [2763%]
........................................................................ [2766%]
....................................[contention-diag] +4532s soak 34p/156t rss 13.7G pss 12.6G swap 0.6G majflt 2426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 6 descendant rss 0.0G pss 0.0G | host avail 32.8G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 5.68 cpu 22.09 | cgroup 14.9G/max oom_kill 0 | free scratch 319.6G/45238040i tmp 28.3G/998008i workspace 319.6G/45238040i | repeat-01 collected 26/26 workers (60626 items) tests 59936 done 3 failed | 4 in flight, oldest 55s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.................................... [2770%]
..ss.ss................................................................. [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
........................................................................ [2786%]
........................................................................ [2790%]
........................................................................ [2793%]
......................................................................[contention-diag] +4548s soak 32p/150t rss 13.7G pss 12.6G swap 0.6G majflt 2426 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 4 descendant rss 0.0G pss 0.0G | host avail 32.7G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.95 cpu 23.8 | cgroup 15.0G/max oom_kill 0 | free scratch 319.6G/45239322i tmp 28.3G/998010i workspace 319.6G/45239322i | repeat-01 collected 26/26 workers (60626 items) tests 60550 done 3 failed | 2 in flight, oldest 5s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
.. [2796%]
........................................................................ [2800%]
..                                                                       [100%][contention-diag] +4563s soak 32p/139t rss 13.7G pss 12.6G swap 0.6G majflt 2429 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.2G pss 12.1G, 4 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.98 cpu 14.72 | cgroup 14.9G/max oom_kill 0 | free scratch 319.6G/45240682i tmp 28.3G/998010i workspace 319.6G/45240682i | scratch used 0.9G in 165930 entries | repeat-01 collected 26/26 workers (60626 items) tests 60626 done 3 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_________ test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox __________
[gw9] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fab6c1b1640>

    async def test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
        async with AcePage(initial_tab="agents", size=(160, 40)) as page:
            await wait_for_startup(page)
            app = page.app
            _wire_corpus(app, ModelCorpus(_history()))
            note_inbox_applied_for_archive(app, load_state=complete_load())
            open_agents_archive_view(app)
            await _wait_for_rows(page)
    
            await page.press("J")
            pulse = app.query_one("#archive-pulse", ArchivePulse)
            assert pulse.has_class("-selected")
            assert app._agents_archive_view.archive.focused_section == ARCHIVE_SECTION_PULSE
            await page.pause()
            await page.press("enter")
>           await page.wait_for(
                lambda _s: app._agents_archive_view.active_view == AGENTS_VIEW_INBOX,
                timeout_message=lambda: (
                    "wait_for() timed out waiting for Inbox after pulse Enter —"
                    f" active_view={app._agents_archive_view.active_view!r}"
                    f" focused_section={app._agents_archive_view.archive.focused_section!r}"
                    f" pulse_selected={pulse.has_class('-selected')}"
                ),
            )

tests/ace/tui/test_agent_archive_column_app.py:218: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7fab6c67ec00>

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
E               AssertionError: wait_for() timed out waiting for Inbox after pulse Enter — active_view='archive' focused_section='pulse' pulse_selected=True

src/sase/ace/testing/wait.py:64: AssertionError
______________ test_hide_closed_default_is_visible_and_clearable _______________
[gw22] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw22/test_hide_closed_default_is_vi0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f1642467560>

    async def test_hide_closed_default_is_visible_and_clearable(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        value = snapshot(tmp_path, project=None)
        monkeypatch.setattr(
            beads_pane,
            "load_beads_snapshot",
            lambda _project, **_kwargs: value,
        )
    
        async with AcePage(initial_tab="patches") as page:
            await page.press(page.artifacts_digit("beads"))
            pane = page.query_one_widget("#artifacts-beads-pane", ArtifactsBeadsPane)
            await page.wait_for(lambda _state: pane.snapshot is value)
            assert pane.filters.excluded_statuses == ("closed",)
            bar = pane.query_one(BeadFilterBar)
            assert bar.display
            display = bar.query_one("#bead-filter-display", Static)
            await page.wait_for(lambda _state: "-status:closed" in display.render().plain)
    
            assert pane.select_entry_target(
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "epic", "alpha-1"))
            )
            pane.set_selected_epic_expanded(True)
            assert (
                ArtifactEntryTarget(pane_id="beads", parts=("alpha", "phase", "alpha-1.1"))
                not in pane.entry_targets()
            )
    
            await page.press("/")
>           assert bar._editing  # type: ignore[attr-defined]
            ^^^^^^^^^^^^^^^^^^^
E           AssertionError: assert False
E            +  where False = BeadFilterBar(id='bead-filter-bar', classes='persistent')._editing

tests/ace/tui/test_artifacts_beads_filtering.py:497: AssertionError
____________ test_paused_watchdog_emits_no_stall_while_loop_blocked ____________
[gw15] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_paused_watchdog_emits_no_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7efbe575bbf0>

    @pytest.mark.asyncio
    async def test_paused_watchdog_emits_no_stall_while_loop_blocked(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        path = tmp_path / "tui_stalls.jsonl"
        monkeypatch.setattr(tui_telemetry, "TUI_STALLS_JSONL", str(path))
        watchdog = _EventLoopStallWatchdog(
            asyncio.get_running_loop(),
            threshold_seconds=0.05,
            poll_interval_seconds=0.01,
        )
        try:
            watchdog.start()
            watchdog.pause()
            # Block the loop well past the threshold while paused.
            time.sleep(0.2)  # sase-test-wait: intentional loop block
            # Let the watchdog thread poll several times during the paused block.
            await asyncio.sleep(0.05)  # sase-test-wait: watchdog thread poll window
        finally:
            watchdog.resume()
            watchdog.stop()
    
>       assert not path.exists()
E       AssertionError: assert not True
E        +  where True = exists()
E        +    where exists = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_paused_watchdog_emits_no_0/tui_stalls.jsonl').exists

tests/ace/tui/util/test_stall_watchdog_suspend.py:82: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:241 TUI event loop stall detected: 0.053s pid=2171321
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    path = os.fspath(arg)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_panel_adapter.py::test_adapter_dismisses_on_escape
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/css/tokenizer.py:302: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for name, value in zip(expect.names, match.groups()[1:]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_project_management_modal_edit.py::test_project_management_modal_alias_editor_updates_selected_project
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/strip.py:111: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    self._offsets_cache: FIFOCache[tuple[int, int], Strip] = FIFOCache(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_collapsed_panel_selection.py::test_collapsed_nonfocused_panel_does_not_hide_expanded_selection
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_runner_slots_eligibility.py::test_slot_queue_derivation_matches_capacity_and_rejects_other_waits
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/models/agent_runner_slots.py:102: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    capacity_records = tuple(
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2171279) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=2171055) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=2171861) is multi-threaded, use of fork() may lead to deadlocks in the child.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=2171071) is multi-threaded, use of fork() may lead to deadlocks in the child.
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
  <frozen os>:888: DeprecationWarning: This process (pid=2171055) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=2171960) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
600.47s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
450.32s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
439.10s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
438.34s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
413.26s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
399.05s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
341.66s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
329.53s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
318.19s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
315.66s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
315.64s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
262.47s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
211.68s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
193.59s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
190.95s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
181.49s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
174.16s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
166.68s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
156.55s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
155.15s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
=========================== short test summary info ============================
FAILED tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
FAILED tests/ace/tui/test_artifacts_beads_filtering.py::test_hide_closed_default_is_visible_and_clearable
FAILED tests/ace/tui/util/test_stall_watchdog_suspend.py::test_paused_watchdog_emits_no_stall_while_loop_blocked
==== 3 failed, 60603 passed, 21 skipped, 111 warnings in 4564.94s (1:16:04) ====
[contention-diag] +4572s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 0 | 1 parent rss 0.0G pss 0.0G | host avail 42.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.18 cpu 8.91 | cgroup 2.4G/max oom_kill 0 | free scratch 319.6G/45240713i tmp 28.3G/998010i workspace 319.6G/45240713i | repeat-01 collected 26/26 workers (60626 items) tests 60626 done 3 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4572s, 298 samples, 0 signal(s); peaks: cgroup_current 16.0G, min_free_scratch 313.7G, min_free_tmp 28.3G, min_free_workspace 313.7G, min_inodes_scratch 45237605, min_inodes_tmp 997659, min_inodes_workspace 45237605, min_mem_available 23.2G, min_swap_free 53.8G, oom_kill_delta 0, pressure_memory_full 2.53, pswpin_delta 77342, pswpout_delta 18598, scratch_bytes 0.9G, soak_procs 48, soak_pss 13.9G, soak_rss 15.1G, soak_swap 1.1G, soak_threads 304

contention tally: 3 node(s) failed across 1 repeat(s) in 4571.7s; red repeats: 1
  1/1  tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox  (repeats 1)
  1/1  tests/ace/tui/test_artifacts_beads_filtering.py::test_hide_closed_default_is_visible_and_clearable  (repeats 1)
  1/1  tests/ace/tui/util/test_stall_watchdog_suspend.py::test_paused_watchdog_emits_no_stall_while_loop_blocked  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
failed  exit=1  duration=4572223ms

