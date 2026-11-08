# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-2)

- **TIMESTAMP:** 2026-11-08 09:53:51 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-2

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after hang-guard, zombie-reap, and TUI wait repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase tool run e8016d0bc981b5fdd809eb76d51f6ccf
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5670 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 1521856, sampler pid 1522358 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-3512554-1794144897496074800.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 73 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 39.7G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.32 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 302.5G/45496490i tmp 29.7G/1015954i workspace 302.5G/45496490i | scratch used 0.0G in 13 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.1G pss 1.8G swap 0.0G majflt 137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.0G pss 1.7G | host avail 37.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.33 cpu 17.66 | cgroup 1.9G/max oom_kill 0 | free scratch 302.5G/45496407i tmp 29.7G/1015954i workspace 302.5G/45496407i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 3.4G pss 3.1G swap 1.1G majflt 704 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.3G pss 3.0G | host avail 37.0G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.05 cpu 24.37 | cgroup 3.2G/max oom_kill 0 | free scratch 302.5G/45496403i tmp 29.7G/1015955i workspace 302.5G/45496403i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +45s soak 28p/80t rss 4.5G pss 4.2G swap 1.3G majflt 738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.4G pss 4.1G | host avail 33.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.97 cpu 20.3 | cgroup 4.3G/max oom_kill 0 | free scratch 302.5G/45496386i tmp 29.7G/1015955i workspace 302.5G/45496386i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +61s soak 28p/88t rss 5.3G pss 4.9G swap 1.3G majflt 1075 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.2G pss 4.8G | host avail 30.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.1 cpu 19.87 | cgroup 5.2G/max oom_kill 0 | free scratch 302.5G/45496385i tmp 29.7G/1015954i workspace 302.5G/45496385i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 29p/89t rss 6.1G pss 5.7G swap 1.3G majflt 1172 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.9G pss 5.6G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.8 cpu 24.37 | cgroup 6.0G/max oom_kill 0 | free scratch 302.5G/45496389i tmp 29.7G/1015954i workspace 302.5G/45496389i | repeat-01 collected 3/26 workers (6927 items) tests 0 done 0 failed
contention shards: 26 workers collected 60607 items in total (2079-2555 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
..............................[contention-diag] +91s soak 29p/86t rss 6.6G pss 6.1G swap 1.2G majflt 1727 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.4G pss 6.0G, 1 descendant rss 0.0G pss 0.0G | host avail 29.8G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.99 cpu 18.21 | cgroup 6.6G/max oom_kill 0 | free scratch 302.2G/45495227i tmp 29.7G/1015953i workspace 302.2G/45495227i | repeat-01 collected 26/26 workers (60607 items) tests 106 done 0 failed | 24 in flight, oldest 1s gw15 tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
.......................................... [  9%]
........................................................................ [ 12%]
........................................................................ [ 15%]
........................................................................ [ 18%]
........................................................................ [ 21%]
........................................................................ [ 25%]
........................................................................ [ 28%]
........................................................................ [ 31%]
........................................................................ [ 34%]
........................................................................ [ 37%]
........................................................................ [ 40%]
...............................[contention-diag] +106s soak 29p/133t rss 7.1G pss 6.6G swap 1.2G majflt 2617 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.9G pss 6.5G, 1 descendant rss 0.0G pss 0.0G | host avail 33.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.26 cpu 18.99 | cgroup 7.1G/max oom_kill 0 | free scratch 302.5G/45493270i tmp 29.7G/1015953i workspace 302.5G/45493270i | repeat-01 collected 26/26 workers (60607 items) tests 950 done 0 failed | 26 in flight, oldest 14s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
......................................... [ 43%]
........................................................................ [ 47%]
........................................................................ [ 50%]
.....................[contention-diag] +122s soak 30p/145t rss 7.5G pss 7.0G swap 1.1G majflt 2799 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.2G pss 6.7G, 2 descendant rss 0.2G pss 0.2G | host avail 32.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.3 cpu 18.99 | cgroup 7.4G/max oom_kill 0 | free scratch 302.5G/45492627i tmp 29.7G/1015953i workspace 302.5G/45492627i | scratch used 0.0G in 3311 entries | repeat-01 collected 26/26 workers (60607 items) tests 1169 done 0 failed | 25 in flight, oldest 29s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
................................................... [ 53%]
........................................................................ [ 56%]
........................................................................ [ 59%]
.......................[contention-diag] +137s soak 31p/181t rss 7.6G pss 7.1G swap 1.1G majflt 2896 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.4G pss 6.9G, 3 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.03 cpu 16.56 | cgroup 7.5G/max oom_kill 0 | free scratch 302.4G/45491455i tmp 29.7G/1015953i workspace 302.4G/45491455i | repeat-01 collected 26/26 workers (60607 items) tests 1384 done 0 failed | 26 in flight, oldest 45s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
................................................. [ 62%]
........................................................................ [ 65%]
........................................................................ [ 69%]
...................................[contention-diag] +152s soak 31p/168t rss 7.8G pss 7.3G swap 1.1G majflt 3108 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.5G pss 7.0G, 3 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.24 cpu 12.79 | cgroup 7.7G/max oom_kill 0 | free scratch 302.3G/45490250i tmp 29.7G/1015940i workspace 302.3G/45490250i | repeat-01 collected 26/26 workers (60607 items) tests 1595 done 0 failed | 26 in flight, oldest 59s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
..................................... [ 72%]
........................................................................ [ 75%]
........................................................................ [ 78%]
........[contention-diag] +167s soak 33p/175t rss 8.0G pss 7.4G swap 1.1G majflt 3111 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.2G, 5 descendant rss 0.1G pss 0.0G | host avail 28.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.57 cpu 11.08 | cgroup 7.9G/max oom_kill 0 | free scratch 302.1G/45488529i tmp 29.7G/1015940i workspace 302.1G/45488529i | repeat-01 collected 26/26 workers (60607 items) tests 1792 done 0 failed | 25 in flight, oldest 74s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
................................................................ [ 81%]
.................................[contention-diag] +183s soak 36p/213t rss 8.1G pss 7.5G swap 1.1G majflt 3129 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.9G pss 7.3G, 8 descendant rss 0.1G pss 0.0G | host avail 27.4G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.18 cpu 11.25 | cgroup 8.0G/max oom_kill 0 | free scratch 302.0G/45487690i tmp 29.7G/1015940i workspace 302.0G/45487690i | repeat-01 collected 26/26 workers (60607 items) tests 1903 done 0 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................... [ 84%]
........................................................................ [ 87%]
........................................................................ [ 91%]
........................................................................ [ 94%]
........................................................................ [ 97%]
..................[contention-diag] +198s soak 40p/229t rss 8.5G pss 7.8G swap 1.1G majflt 3202 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.5G, 12 descendant rss 0.3G pss 0.2G | host avail 26.6G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.52 cpu 12.41 | cgroup 8.4G/max oom_kill 0 | free scratch 301.8G/45487778i tmp 29.7G/1015940i workspace 301.8G/45487778i | repeat-01 collected 26/26 workers (60607 items) tests 2246 done 0 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................... [100%]
........................................................................ [103%]
.......[contention-diag] +213s soak 35p/202t rss 8.7G pss 8.0G swap 1.1G majflt 3288 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.7G, 7 descendant rss 0.2G pss 0.2G | host avail 27.2G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.48 cpu 16.1 | cgroup 8.6G/max oom_kill 0 | free scratch 301.7G/45487367i tmp 29.7G/1015940i workspace 301.7G/45487367i | repeat-01 collected 26/26 workers (60607 items) tests 2369 done 0 failed | 26 in flight, oldest 97s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................. [106%]
..................................................................[contention-diag] +228s soak 31p/230t rss 8.6G pss 8.0G swap 1.1G majflt 3294 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.7G, 3 descendant rss 0.2G pss 0.2G | host avail 28.2G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.73 cpu 18.41 | cgroup 8.6G/max oom_kill 0 | free scratch 301.6G/45487048i tmp 29.7G/1015940i workspace 301.6G/45487048i | repeat-01 collected 26/26 workers (60607 items) tests 2500 done 0 failed | 25 in flight, oldest 112s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...... [109%]
........................................................................ [113%]
........................................................................ [116%]
[contention-diag] +244s soak 37p/240t rss 8.7G pss 8.1G swap 1.1G majflt 3338 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 9 descendant rss 0.2G pss 0.1G | host avail 25.2G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.61 cpu 17.62 | cgroup 8.7G/max oom_kill 0 | free scratch 301.6G/45486612i tmp 29.7G/1015938i workspace 301.6G/45486612i | scratch used 0.0G in 7318 entries | repeat-01 collected 26/26 workers (60607 items) tests 2654 done 0 failed | 26 in flight, oldest 127s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................................................ [119%]
........................................................................ [122%]
..................................................................[contention-diag] +259s soak 41p/232t rss 9.0G pss 8.3G swap 1.1G majflt 3401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 7.9G, 13 descendant rss 0.4G pss 0.2G | host avail 27.7G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 2.52 cpu 19.08 | cgroup 8.9G/max oom_kill 0 | free scratch 301.6G/45485942i tmp 29.7G/1015940i workspace 301.6G/45485942i | repeat-01 collected 26/26 workers (60607 items) tests 2869 done 0 failed | 26 in flight, oldest 143s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...... [125%]
........................................................................ [128%]
...............................................[contention-diag] +274s soak 35p/212t rss 9.0G pss 8.3G swap 1.1G majflt 3532 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.5G pss 8.0G, 7 descendant rss 0.3G pss 0.2G | host avail 26.8G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.81 cpu 16.62 | cgroup 8.9G/max oom_kill 0 | free scratch 301.4G/45485554i tmp 29.7G/1015940i workspace 301.4G/45485554i | repeat-01 collected 26/26 workers (60607 items) tests 2998 done 0 failed | 26 in flight, oldest 158s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................... [131%]
.......[contention-diag] +290s soak 33p/233t rss 8.9G pss 8.2G swap 1.0G majflt 3564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 28.1G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.98 cpu 15.48 | cgroup 8.9G/max oom_kill 0 | free scratch 302.0G/45485354i tmp 29.7G/1015940i workspace 302.0G/45485354i | repeat-01 collected 26/26 workers (60607 items) tests 3029 done 0 failed | 26 in flight, oldest 173s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................. [135%]
........................................................................ [138%]
[contention-diag] +305s soak 34p/247t rss 8.9G pss 8.3G swap 1.0G majflt 3566 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 6 descendant rss 0.1G pss 0.0G | host avail 28.4G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.28 cpu 18.75 | cgroup 8.9G/max oom_kill 0 | free scratch 301.8G/45484899i tmp 29.7G/1015940i workspace 301.8G/45484899i | repeat-01 collected 26/26 workers (60607 items) tests 3162 done 0 failed | 26 in flight, oldest 188s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................................................ [141%]
........................................................................ [144%]
..........[contention-diag] +320s soak 39p/264t rss 9.3G pss 8.6G swap 1.1G majflt 3570 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 11 descendant rss 0.3G pss 0.2G | host avail 28.2G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.27 cpu 20.31 | cgroup 9.2G/max oom_kill 0 | free scratch 301.7G/45484112i tmp 29.7G/1015934i workspace 301.7G/45484112i | repeat-01 collected 26/26 workers (60607 items) tests 3317 done 0 failed | 25 in flight, oldest 204s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................................. [147%]
........................................................................ [150%]
........................................................................ [153%]
...[contention-diag] +335s soak 33p/251t rss 9.1G pss 8.4G swap 1.0G majflt 3572 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.3G, 5 descendant rss 0.1G pss 0.0G | host avail 30.1G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.36 cpu 21.56 | cgroup 9.1G/max oom_kill 0 | free scratch 301.6G/45483179i tmp 29.7G/1015915i workspace 301.6G/45483179i | repeat-01 collected 26/26 workers (60607 items) tests 3510 done 0 failed | 26 in flight, oldest 219s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................................... [157%]
..................................................................[contention-diag] +350s soak 33p/263t rss 9.1G pss 8.5G swap 1.0G majflt 3576 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 5 descendant rss 0.1G pss 0.0G | host avail 26.4G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.29 cpu 20.18 | cgroup 9.1G/max oom_kill 0 | free scratch 301.5G/45482777i tmp 29.7G/1015914i workspace 301.5G/45482777i | repeat-01 collected 26/26 workers (60607 items) tests 3665 done 0 failed | 26 in flight, oldest 234s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...... [160%]
........................................................................ [163%]
.....[contention-diag] +366s soak 35p/253t rss 9.3G pss 8.6G swap 1.0G majflt 3596 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 7 descendant rss 0.1G pss 0.1G | host avail 28.7G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.75 cpu 18.62 | cgroup 9.3G/max oom_kill 0 | free scratch 301.5G/45482472i tmp 29.7G/1015914i workspace 301.5G/45482472i | scratch used 0.1G in 10645 entries | repeat-01 collected 26/26 workers (60607 items) tests 3742 done 0 failed | 26 in flight, oldest 249s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..........................................................[contention-diag] +381s soak 36p/267t rss 9.3G pss 8.7G swap 1.0G majflt 3596 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 8 descendant rss 0.1G pss 0.0G | host avail 32.1G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.63 cpu 19.15 | cgroup 9.3G/max oom_kill 0 | free scratch 301.5G/45482138i tmp 29.7G/1015914i workspace 301.5G/45482138i | repeat-01 collected 26/26 workers (60607 items) tests 3806 done 0 failed | 26 in flight, oldest 265s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......... [166%]
...................................................[contention-diag] +397s soak 40p/256t rss 9.5G pss 8.8G swap 1.1G majflt 3596 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 12 descendant rss 0.3G pss 0.2G | host avail 27.3G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.75 cpu 12.26 | cgroup 9.5G/max oom_kill 0 | free scratch 301.6G/45479678i tmp 29.7G/1015912i workspace 301.6G/45479678i | repeat-01 collected 26/26 workers (60607 items) tests 3860 done 0 failed | 26 in flight, oldest 280s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................... [169%]
........................................................................ [172%]
........[contention-diag] +412s soak 39p/257t rss 9.4G pss 8.7G swap 1.0G majflt 3596 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 11 descendant rss 0.1G pss 0.0G | host avail 24.4G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.44/0.44 io 1.2 cpu 8.55 | cgroup 9.4G/max oom_kill 0 | free scratch 301.3G/45477829i tmp 29.7G/1015911i workspace 301.3G/45477829i | repeat-01 collected 26/26 workers (60607 items) tests 3964 done 0 failed | 26 in flight, oldest 296s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................ [175%]
....[contention-diag] +427s soak 40p/272t rss 9.6G pss 8.9G swap 1.0G majflt 3596 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 12 descendant rss 0.2G pss 0.1G | host avail 23.8G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 0.51 cpu 12.58 | cgroup 9.5G/max oom_kill 0 | free scratch 301.1G/45477468i tmp 29.7G/1015911i workspace 301.1G/45477468i | repeat-01 collected 26/26 workers (60607 items) tests 4032 done 0 failed | 26 in flight, oldest 311s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................................... [179%]
..........................[contention-diag] +443s soak 43p/281t rss 9.8G pss 9.1G swap 1.1G majflt 3606 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 15 descendant rss 0.4G pss 0.3G | host avail 19.3G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.26/0.26 io 0.54 cpu 13.66 | cgroup 9.5G/max oom_kill 0 | free scratch 300.8G/45477110i tmp 29.7G/1015912i workspace 300.8G/45477110i | repeat-01 collected 26/26 workers (60607 items) tests 4127 done 0 failed | 26 in flight, oldest 326s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................. [182%]
...............................[contention-diag] +458s soak 40p/244t rss 9.6G pss 8.9G swap 1.0G majflt 3601 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 12 descendant rss 0.2G pss 0.1G | host avail 26.4G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 0.53 cpu 14.11 | cgroup 9.4G/max oom_kill 0 | free scratch 301.0G/45476764i tmp 29.7G/1015912i workspace 301.0G/45476764i | repeat-01 collected 26/26 workers (60607 items) tests 4200 done 0 failed | 26 in flight, oldest 342s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................................... [185%]
........................................................................ [188%]
....[contention-diag] +473s soak 34p/257t rss 9.6G pss 8.9G swap 1.0G majflt 3679 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 6 descendant rss 0.1G pss 0.0G | host avail 23.1G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.63 cpu 15.33 | cgroup 9.4G/max oom_kill 0 | free scratch 300.9G/45476317i tmp 29.7G/1015912i workspace 300.9G/45476317i | repeat-01 collected 26/26 workers (60607 items) tests 4322 done 0 failed | 26 in flight, oldest 357s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................[contention-diag] +488s soak 35p/265t rss 9.7G pss 9.0G swap 1.0G majflt 3729 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 7 descendant rss 0.1G pss 0.0G | host avail 22.7G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 18.03 | cgroup 9.5G/max oom_kill 0 | free scratch 300.9G/45475944i tmp 29.7G/1015910i workspace 300.9G/45475944i | scratch used 0.1G in 12875 entries | repeat-01 collected 26/26 workers (60607 items) tests 4361 done 0 failed | 26 in flight, oldest 372s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................... [191%]
........................................................................ [194%]
.................................................[contention-diag] +504s soak 30p/244t rss 9.7G pss 9.1G swap 1.0G majflt 3732 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 23.95 | cgroup 9.5G/max oom_kill 0 | free scratch 300.8G/45475706i tmp 29.7G/1015912i workspace 300.8G/45475706i | repeat-01 collected 26/26 workers (60607 items) tests 4507 done 0 failed | 26 in flight, oldest 388s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................... [197%]
..................[contention-diag] +519s soak 28p/261t rss 9.7G pss 9.0G swap 1.0G majflt 3732 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G | host avail 23.7G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 24.6 | cgroup 9.5G/max oom_kill 0 | free scratch 300.7G/45475493i tmp 29.7G/1015912i workspace 300.7G/45475493i | repeat-01 collected 26/26 workers (60607 items) tests 4552 done 0 failed | 26 in flight, oldest 403s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................[contention-diag] +535s soak 30p/250t rss 9.7G pss 9.1G swap 1.0G majflt 3831 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.0G pss 0.0G | host avail 19.2G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 18.11 | cgroup 9.6G/max oom_kill 0 | free scratch 300.8G/45475303i tmp 29.7G/1015912i workspace 300.8G/45475303i | repeat-01 collected 26/26 workers (60607 items) tests 4571 done 0 failed | 26 in flight, oldest 106s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
..................[contention-diag] +550s soak 30p/220t rss 9.8G pss 9.1G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 2 descendant rss 0.1G pss 0.0G | host avail 24.1G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 12.57 | cgroup 9.6G/max oom_kill 0 | free scratch 300.9G/45475134i tmp 29.7G/1015912i workspace 300.9G/45475134i | repeat-01 collected 26/26 workers (60607 items) tests 4586 done 0 failed | 26 in flight, oldest 51s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
.................. [201%]
....................[contention-diag] +565s soak 31p/221t rss 9.9G pss 9.3G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 3 descendant rss 0.1G pss 0.1G | host avail 21.5G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 11.75 | cgroup 9.8G/max oom_kill 0 | free scratch 300.7G/45474904i tmp 29.7G/1015912i workspace 300.7G/45474904i | repeat-01 collected 26/26 workers (60607 items) tests 4625 done 0 failed | 26 in flight, oldest 67s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
.................................................... [204%]
............................[contention-diag] +581s soak 28p/254t rss 9.8G pss 9.2G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G | host avail 25.2G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 12.2 | cgroup 9.7G/max oom_kill 0 | free scratch 300.3G/45474584i tmp 29.7G/1015912i workspace 300.3G/45474584i | repeat-01 collected 26/26 workers (60607 items) tests 4705 done 0 failed | 26 in flight, oldest 65s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
............................................ [207%]
....................[contention-diag] +596s soak 28p/249t rss 9.8G pss 9.2G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 20.1G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 10.56 | cgroup 9.7G/max oom_kill 0 | free scratch 300.2G/45474325i tmp 29.7G/1015912i workspace 300.2G/45474325i | repeat-01 collected 26/26 workers (60607 items) tests 4768 done 0 failed | 26 in flight, oldest 80s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
..............................[contention-diag] +611s soak 29p/240t rss 9.9G pss 9.3G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 1 descendant rss 0.1G pss 0.0G | host avail 23.1G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.99 | cgroup 9.8G/max oom_kill 0 | free scratch 300.1G/45474162i tmp 29.7G/1015911i workspace 300.1G/45474162i | scratch used 0.1G in 14787 entries | repeat-01 collected 26/26 workers (60607 items) tests 4800 done 0 failed | 26 in flight, oldest 84s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
..........[contention-diag] +627s soak 30p/244t rss 10.0G pss 9.3G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 2 descendant rss 0.1G pss 0.1G | host avail 20.5G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 13.62 | cgroup 9.9G/max oom_kill 0 | free scratch 300.0G/45473967i tmp 29.7G/1015913i workspace 300.0G/45473967i | repeat-01 collected 26/26 workers (60607 items) tests 4809 done 0 failed | 26 in flight, oldest 99s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
............ [210%]
.....................................[contention-diag] +642s soak 28p/249t rss 9.9G pss 9.3G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 23.5G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 13.82 | cgroup 9.9G/max oom_kill 0 | free scratch 300.2G/45473610i tmp 29.7G/1015913i workspace 300.2G/45473610i | repeat-01 collected 26/26 workers (60607 items) tests 4859 done 0 failed | 26 in flight, oldest 59s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
.............[contention-diag] +657s soak 28p/254t rss 10.0G pss 9.3G swap 1.0G majflt 3754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 26.5G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.11 cpu 9.58 | cgroup 9.9G/max oom_kill 0 | free scratch 303.1G/45495706i tmp 29.7G/1015912i workspace 303.1G/45495706i | repeat-01 collected 26/26 workers (60607 items) tests 4868 done 0 failed | 26 in flight, oldest 59s gw16 tests/ace/tui/test_agent_panel_layout_ladder.py::test_flag_on_oo_walks_ladder_and_oO_steps_back
...................... [213%]
........................................................................ [216%]
...........[contention-diag] +673s soak 29p/240t rss 10.1G pss 9.4G swap 1.0G majflt 3769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 21.8G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.18 cpu 9.08 | cgroup 10.0G/max oom_kill 0 | free scratch 303.2G/45494644i tmp 29.7G/1015912i workspace 303.2G/45494644i | repeat-01 collected 26/26 workers (60607 items) tests 4973 done 0 failed | 26 in flight, oldest 61s gw8 tests/ace/tui/test_artifacts_split_modes.py::test_split_actions_are_scoped_to_every_artifacts_subtab
.............[contention-diag] +688s soak 29p/241t rss 10.1G pss 9.5G swap 1.0G majflt 3769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.1G pss 0.0G | host avail 21.0G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 12.16 | cgroup 10.0G/max oom_kill 0 | free scratch 303.0G/45494453i tmp 29.7G/1015912i workspace 303.0G/45494453i | repeat-01 collected 26/26 workers (60607 items) tests 4991 done 0 failed | 26 in flight, oldest 76s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...........................[contention-diag] +703s soak 28p/225t rss 10.1G pss 9.4G swap 1.0G majflt 3796 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G | host avail 19.0G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.52 cpu 14.52 | cgroup 10.0G/max oom_kill 0 | free scratch 302.9G/45494217i tmp 29.7G/1015913i workspace 302.9G/45494217i | repeat-01 collected 26/26 workers (60607 items) tests 5014 done 0 failed | 26 in flight, oldest 57s gw0 tests/ace/tui/test_copy_as_palette_entrypoints.py::test_percent_opens_palette_for_each_live_artifacts_subtab[beads]
..........[contention-diag] +719s soak 28p/242t rss 10.0G pss 9.4G swap 1.1G majflt 3801 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G | host avail 15.9G/62.7G swapfree 53.5G/64.0G oom_kill +0 | psi10 mem 0.38/0.26 io 1.08 cpu 13.16 | cgroup 9.8G/max oom_kill 0 | free scratch 302.7G/45494072i tmp 29.7G/1015913i workspace 302.7G/45494072i | repeat-01 collected 26/26 workers (60607 items) tests 5029 done 0 failed | 26 in flight, oldest 49s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_guards_pass_through_and_toggle_opens_archive
........... [219%]
..............................[contention-diag] +734s soak 30p/236t rss 10.2G pss 9.5G swap 1.1G majflt 3807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 2 descendant rss 0.1G pss 0.1G | host avail 15.3G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.42/0.39 io 2.38 cpu 12.91 | cgroup 10.1G/max oom_kill 0 | free scratch 302.7G/45493745i tmp 29.7G/1015913i workspace 302.7G/45493745i | scratch used 0.1G in 16353 entries | repeat-01 collected 26/26 workers (60607 items) tests 5063 done 0 failed | 26 in flight, oldest 56s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_panel_action_override_takes_effect_in_mounted_pilot
.......................................... [223%]
.................................................[contention-diag] +751s soak 29p/243t rss 10.2G pss 9.5G swap 1.1G majflt 3812 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.1G pss 0.0G | host avail 16.7G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.15/0.1 io 0.79 cpu 8.01 | cgroup 10.0G/max oom_kill 0 | free scratch 302.7G/45493344i tmp 29.7G/1015913i workspace 302.7G/45493344i | repeat-01 collected 26/26 workers (60607 items) tests 5159 done 0 failed | 26 in flight, oldest 58s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
....................... [226%]
...[contention-diag] +766s soak 28p/236t rss 10.1G pss 9.5G swap 1.1G majflt 3814 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 18.3G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 0.55 cpu 11.06 | cgroup 9.9G/max oom_kill 0 | free scratch 302.4G/45493082i tmp 29.7G/1015913i workspace 302.4G/45493082i | repeat-01 collected 26/26 workers (60607 items) tests 5186 done 0 failed | 26 in flight, oldest 63s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
..................................................................... [229%]
........................................................................ [232%]
.........[contention-diag] +782s soak 28p/250t rss 10.2G pss 9.5G swap 1.1G majflt 3823 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G | host avail 20.2G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 12.68 | cgroup 9.9G/max oom_kill 0 | free scratch 302.0G/45492565i tmp 29.7G/1015913i workspace 302.0G/45492564i | repeat-01 collected 26/26 workers (60607 items) tests 5325 done 0 failed | 25 in flight, oldest 54s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_arrival_then_clear_name_keeps_selection
............................................................... [235%]
........................................................................ [238%]
................[contention-diag] +797s soak 29p/231t rss 10.2G pss 9.6G swap 1.1G majflt 3858 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 1 descendant rss 0.1G pss 0.0G | host avail 22.5G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.36 cpu 14.19 | cgroup 10.0G/max oom_kill 0 | free scratch 302.4G/45492097i tmp 29.7G/1015913i workspace 302.4G/45492097i | repeat-01 collected 26/26 workers (60607 items) tests 5481 done 0 failed | 26 in flight, oldest 57s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_configured_toggle_key_appears_in_rail_and_rebinding_changes_it
........................................................ [241%]
.................................[contention-diag] +812s soak 32p/260t rss 10.3G pss 9.7G swap 1.1G majflt 3871 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G, 4 descendant rss 0.1G pss 0.1G | host avail 21.3G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.99 cpu 16.76 | cgroup 10.1G/max oom_kill 0 | free scratch 302.7G/45491566i tmp 29.7G/1015913i workspace 302.7G/45491566i | repeat-01 collected 26/26 workers (60607 items) tests 5573 done 0 failed | 26 in flight, oldest 70s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
....................................... [245%]
........................[contention-diag] +828s soak 28p/248t rss 10.3G pss 9.6G swap 1.1G majflt 3880 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 21.6G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 2.27 cpu 16.65 | cgroup 10.1G/max oom_kill 0 | free scratch 302.4G/45491276i tmp 29.7G/1015913i workspace 302.4G/45491276i | repeat-01 collected 26/26 workers (60607 items) tests 5639 done 0 failed | 26 in flight, oldest 86s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
...............................................[contention-diag] +843s soak 30p/247t rss 10.3G pss 9.6G swap 1.1G majflt 3881 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G, 2 descendant rss 0.0G pss 0.0G | host avail 27.0G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.64 cpu 10.34 | cgroup 10.2G/max oom_kill 0 | free scratch 302.3G/45491055i tmp 29.7G/1015911i workspace 302.3G/45491055i | repeat-01 collected 26/26 workers (60607 items) tests 5687 done 0 failed | 26 in flight, oldest 78s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
. [248%]
................................................[contention-diag] +858s soak 29p/267t rss 10.3G pss 9.7G swap 1.1G majflt 3884 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 26.6G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.4 cpu 9.08 | cgroup 10.2G/max oom_kill 0 | free scratch 302.0G/45490741i tmp 29.7G/1015913i workspace 302.0G/45490741i | scratch used 0.1G in 18909 entries | repeat-01 collected 26/26 workers (60607 items) tests 5734 done 0 failed | 26 in flight, oldest 93s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................ [251%]
..........................[contention-diag] +874s soak 30p/246t rss 10.5G pss 9.8G swap 1.1G majflt 3886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 27.0G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 10.45 | cgroup 10.3G/max oom_kill 0 | free scratch 304.4G/45495705i tmp 29.7G/1015913i workspace 304.4G/45495705i | repeat-01 collected 26/26 workers (60607 items) tests 5777 done 0 failed | 26 in flight, oldest 109s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.............................................. [254%]
............................[contention-diag] +889s soak 30p/255t rss 10.5G pss 9.8G swap 1.1G majflt 3887 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 2 descendant rss 0.1G pss 0.1G | host avail 28.2G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 15.11 | cgroup 10.2G/max oom_kill 0 | free scratch 304.3G/45497625i tmp 29.7G/1015913i workspace 304.3G/45497625i | repeat-01 collected 26/26 workers (60607 items) tests 5858 done 0 failed | 26 in flight, oldest 124s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............................................ [257%]
....................................................[contention-diag] +904s soak 29p/258t rss 10.4G pss 9.8G swap 1.1G majflt 3899 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 18.87 | cgroup 10.2G/max oom_kill 0 | free scratch 304.3G/45497244i tmp 29.7G/1015913i workspace 304.3G/45497244i | repeat-01 collected 26/26 workers (60607 items) tests 5955 done 0 failed | 26 in flight, oldest 139s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.................... [260%]
...................................................................[contention-diag] +920s soak 29p/249t rss 10.5G pss 9.8G swap 1.1G majflt 3909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 17.42 | cgroup 10.3G/max oom_kill 0 | free scratch 304.1G/45496499i tmp 29.7G/1015913i workspace 304.1G/45496499i | repeat-01 collected 26/26 workers (60607 items) tests 6040 done 0 failed | 26 in flight, oldest 154s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..... [263%]
........................................................................ [267%]
........................................................................ [270%]
..........................[contention-diag] +935s soak 29p/216t rss 10.6G pss 9.9G swap 1.1G majflt 8636 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 1 descendant rss 0.1G pss 0.1G | host avail 30.3G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 1.18/0.0 io 0.18 cpu 13.23 | cgroup 10.4G/max oom_kill 0 | free scratch 303.7G/45495097i tmp 29.7G/1015913i workspace 303.7G/45495097i | repeat-01 collected 26/26 workers (60607 items) tests 6211 done 0 failed | 25 in flight, oldest 57s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_menu_moves_with_fixed_arrows_when_history_rebound
.............................................. [273%]
........................................................................ [276%]
........................................................................ [279%]
......................................[contention-diag] +950s soak 29p/225t rss 10.6G pss 9.9G swap 1.0G majflt 8663 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.29/0.0 io 0.1 cpu 17.05 | cgroup 10.4G/max oom_kill 0 | free scratch 303.6G/45494241i tmp 29.7G/1015913i workspace 303.6G/45494241i | repeat-01 collected 26/26 workers (60607 items) tests 6438 done 0 failed | 25 in flight, oldest 45s gw0 tests/ace/tui/test_plan_decision_ace_render_rail.py::test_compact_verdict_stays_inside_rail_with_stylesheet
.................................. [282%]
...................................[contention-diag] +966s soak 28p/244t rss 10.6G pss 9.9G swap 1.0G majflt 8664 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 26.5G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 0.12 cpu 18.14 | cgroup 10.4G/max oom_kill 0 | free scratch 303.6G/45493937i tmp 29.7G/1015913i workspace 303.6G/45493937i | repeat-01 collected 26/26 workers (60607 items) tests 6514 done 0 failed | 26 in flight, oldest 60s gw0 tests/ace/tui/test_plan_decision_ace_render_rail.py::test_compact_verdict_stays_inside_rail_with_stylesheet
..................................... [285%]
........................................................................ [289%]
.................[contention-diag] +981s soak 29p/256t rss 10.6G pss 10.0G swap 1.0G majflt 8676 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 1 descendant rss 0.0G pss 0.0G | host avail 22.9G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.13 cpu 16.69 | cgroup 10.4G/max oom_kill 0 | free scratch 303.6G/45493586i tmp 29.7G/1015913i workspace 303.6G/45493586i | scratch used 0.1G in 21877 entries | repeat-01 collected 26/26 workers (60607 items) tests 6625 done 0 failed | 26 in flight, oldest 75s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
....................................................... [292%]
....................................................................[contention-diag] +997s soak 28p/221t rss 10.7G pss 10.0G swap 1.0G majflt 8725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G | host avail 19.3G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 18.07 | cgroup 10.5G/max oom_kill 0 | free scratch 303.5G/45493156i tmp 29.7G/1015913i workspace 303.5G/45493156i | repeat-01 collected 26/26 workers (60607 items) tests 6763 done 0 failed | 26 in flight, oldest 45s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
.... [295%]
.........................................[contention-diag] +1012s soak 28p/212t rss 10.7G pss 10.0G swap 1.0G majflt 8741 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G | host avail 20.0G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 14.74 | cgroup 10.5G/max oom_kill 0 | free scratch 303.0G/45492914i tmp 29.7G/1015913i workspace 303.0G/45492914i | repeat-01 collected 26/26 workers (60607 items) tests 6805 done 0 failed | 26 in flight, oldest 43s gw0 tests/ace/tui/test_plan_decision_ace_render_rail.py::test_decision_rail_widths_and_narrow_dock
............................... [298%]
...........................[contention-diag] +1028s soak 29p/235t rss 10.7G pss 10.0G swap 1.0G majflt 8744 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 24.8G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 15.79 | cgroup 10.5G/max oom_kill 0 | free scratch 302.9G/45492613i tmp 29.7G/1015913i workspace 302.9G/45492613i | repeat-01 collected 26/26 workers (60607 items) tests 6867 done 0 failed | 26 in flight, oldest 46s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_f_opens_files_below_and_keeps_focus
............................................. [301%]
........................................................................ [304%]
........................................................................ [307%]
....[contention-diag] +1043s soak 29p/231t rss 10.8G pss 10.1G swap 1.0G majflt 8751 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 25.0G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.24 cpu 14.85 | cgroup 10.6G/max oom_kill 0 | free scratch 301.6G/45491904i tmp 29.7G/1015913i workspace 301.6G/45491904i | repeat-01 collected 26/26 workers (60607 items) tests 7053 done 0 failed | 26 in flight, oldest 60s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
.................................................................... [310%]
..........................[contention-diag] +1058s soak 30p/219t rss 10.9G pss 10.1G swap 1.0G majflt 8758 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 2 descendant rss 0.1G pss 0.1G | host avail 29.9G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 16.94 | cgroup 10.6G/max oom_kill 0 | free scratch 301.4G/45490838i tmp 29.7G/1015913i workspace 301.4G/45490839i | repeat-01 collected 26/26 workers (60607 items) tests 7153 done 0 failed | 26 in flight, oldest 47s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_clicking_idle_file_bar_opens_the_filter_session
...........[contention-diag] +1074s soak 30p/241t rss 10.9G pss 10.2G swap 1.1G majflt 8758 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 2 descendant rss 0.1G pss 0.1G | host avail 30.5G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 12.71 | cgroup 10.6G/max oom_kill 0 | free scratch 301.4G/45491755i tmp 29.7G/1015907i workspace 301.4G/45491755i | repeat-01 collected 26/26 workers (60607 items) tests 7164 done 0 failed | 26 in flight, oldest 50s gw5 tests/ace/tui/test_artifacts_plans_filtering.py::test_clicking_idle_plan_bar_opens_the_filter_session
................................... [314%]
....................................................[contention-diag] +1089s soak 29p/244t rss 10.8G pss 10.1G swap 1.0G majflt 8766 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.45 cpu 13.5 | cgroup 10.6G/max oom_kill 0 | free scratch 301.3G/45474778i tmp 29.7G/1015860i workspace 301.3G/45474778i | repeat-01 collected 26/26 workers (60607 items) tests 7252 done 0 failed | 26 in flight, oldest 50s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
.................... [317%]
........................................................................ [320%]
.................................[contention-diag] +1104s soak 29p/239t rss 10.8G pss 10.1G swap 1.0G majflt 8767 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 28.5G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.54/0.54 io 13.49 cpu 10.69 | cgroup 10.6G/max oom_kill 0 | free scratch 301.1G/45462206i tmp 29.7G/1015683i workspace 301.1G/45462206i | scratch used 0.2G in 24359 entries | repeat-01 collected 26/26 workers (60607 items) tests 7360 done 0 failed | 26 in flight, oldest 65s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
....................................... [323%]
.....................[contention-diag] +1120s soak 29p/239t rss 10.9G pss 10.2G swap 1.1G majflt 8769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 31.3G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 5.81 cpu 19.33 | cgroup 10.7G/max oom_kill 0 | free scratch 301.0G/45458512i tmp 29.7G/1015853i workspace 301.0G/45458512i | repeat-01 collected 26/26 workers (60607 items) tests 7437 done 0 failed | 26 in flight, oldest 64s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
................................................... [326%]
.................................................................[contention-diag] +1136s soak 28p/214t rss 10.8G pss 10.1G swap 1.0G majflt 8771 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G | host avail 31.5G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 1.42 cpu 25.37 | cgroup 10.6G/max oom_kill 0 | free scratch 301.0G/45458019i tmp 29.7G/1015853i workspace 301.0G/45458019i | repeat-01 collected 26/26 workers (60607 items) tests 7544 done 0 failed | 24 in flight, oldest 39s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_not_project_term_is_not_inverted_by_seed
....... [329%]
........................................................................ [332%]
........................................................................ [336%]
....[contention-diag] +1151s soak 38p/269t rss 11.0G pss 10.2G swap 1.0G majflt 8777 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 30.8G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 27.76 | cgroup 10.7G/max oom_kill 0 | free scratch 301.0G/45457563i tmp 29.7G/1015853i workspace 301.0G/45457563i | repeat-01 collected 26/26 workers (60607 items) tests 7701 done 0 failed | 26 in flight, oldest 46s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_real_mount_opens_existing_entry_in_unfocused_browse_mode
.....................................[contention-diag] +1166s soak 38p/265t rss 11.0G pss 10.2G swap 1.0G majflt 8786 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 31.0G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 20.31 | cgroup 10.7G/max oom_kill 0 | free scratch 301.0G/45457407i tmp 29.7G/1015881i workspace 301.0G/45457407i | repeat-01 collected 26/26 workers (60607 items) tests 7744 done 0 failed | 26 in flight, oldest 55s gw20 tests/ace/tui/test_link_follow_seam.py::test_closed_phase_follow_selects_without_hanging
..........[contention-diag] +1182s soak 38p/259t rss 11.0G pss 10.2G swap 1.0G majflt 8787 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 30.9G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 18.7 | cgroup 10.7G/max oom_kill 0 | free scratch 301.3G/45468178i tmp 29.7G/1015880i workspace 301.3G/45468178i | repeat-01 collected 26/26 workers (60607 items) tests 7755 done 0 failed | 26 in flight, oldest 70s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
.......[contention-diag] +1197s soak 38p/289t rss 11.0G pss 10.2G swap 1.0G majflt 8788 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 29.3G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 19.65 | cgroup 10.7G/max oom_kill 0 | free scratch 301.3G/45467983i tmp 29.7G/1015880i workspace 301.3G/45467983i | repeat-01 collected 26/26 workers (60607 items) tests 7760 done 0 failed | 26 in flight, oldest 85s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
.............. [339%]
..........................................................[contention-diag] +1212s soak 31p/267t rss 10.9G pss 10.2G swap 1.0G majflt 8841 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 3 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.84 cpu 22.22 | cgroup 10.7G/max oom_kill 0 | free scratch 301.3G/45467199i tmp 29.7G/1015880i workspace 301.3G/45467199i | repeat-01 collected 26/26 workers (60607 items) tests 7833 done 0 failed | 26 in flight, oldest 88s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.............. [342%]
........[contention-diag] +1227s soak 39p/253t rss 11.1G pss 10.3G swap 1.0G majflt 8802 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 11 descendant rss 0.1G pss 0.1G | host avail 28.5G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 24.65 | cgroup 10.8G/max oom_kill 0 | free scratch 301.3G/45467565i tmp 29.7G/1015880i workspace 301.3G/45467565i | scratch used 0.2G in 26378 entries | repeat-01 collected 26/26 workers (60607 items) tests 7854 done 0 failed | 26 in flight, oldest 103s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................................................................ [345%]
........................................................................ [348%]
........[contention-diag] +1243s soak 38p/265t rss 11.0G pss 10.2G swap 1.0G majflt 8813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 27.4G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 24.19 | cgroup 10.7G/max oom_kill 0 | free scratch 301.3G/45467114i tmp 29.7G/1015880i workspace 301.3G/45467114i | repeat-01 collected 26/26 workers (60607 items) tests 7997 done 0 failed | 26 in flight, oldest 119s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................................................................ [351%]
.........................[contention-diag] +1258s soak 38p/271t rss 11.1G pss 10.3G swap 1.0G majflt 8821 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 26.6G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 29.29 | cgroup 10.8G/max oom_kill 0 | free scratch 301.3G/45466778i tmp 29.7G/1015880i workspace 301.3G/45466778i | repeat-01 collected 26/26 workers (60607 items) tests 8083 done 0 failed | 26 in flight, oldest 85s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
..................[contention-diag] +1273s soak 30p/243t rss 11.0G pss 10.3G swap 1.0G majflt 8821 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 2 descendant rss 0.0G pss 0.0G | host avail 25.8G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 35.72 | cgroup 10.8G/max oom_kill 0 | free scratch 301.3G/45466610i tmp 29.7G/1015880i workspace 301.3G/45466610i | repeat-01 collected 26/26 workers (60607 items) tests 8106 done 0 failed | 26 in flight, oldest 59s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
............................. [354%]
........[contention-diag] +1289s soak 28p/244t rss 11.0G pss 10.3G swap 1.0G majflt 8833 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G | host avail 23.3G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.6 | cgroup 10.8G/max oom_kill 0 | free scratch 301.5G/45466415i tmp 29.7G/1015880i workspace 301.5G/45466415i | repeat-01 collected 26/26 workers (60607 items) tests 8143 done 0 failed | 26 in flight, oldest 44s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_filtered_patch_reveals_its_stack
................................................................ [358%]
........................................[contention-diag] +1304s soak 28p/223t rss 11.0G pss 10.3G swap 1.0G majflt 8844 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 28.8G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.0 cpu 23.84 | cgroup 10.8G/max oom_kill 0 | free scratch 301.7G/45465815i tmp 29.7G/1015880i workspace 301.7G/45465815i | repeat-01 collected 26/26 workers (60607 items) tests 8247 done 0 failed | 26 in flight, oldest 43s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
................................ [361%]
........................................................................ [364%]
............[contention-diag] +1319s soak 28p/243t rss 11.0G pss 10.3G swap 1.0G majflt 8844 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 27.5G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.0 cpu 22.38 | cgroup 10.8G/max oom_kill 0 | free scratch 301.7G/45465792i tmp 29.7G/1015880i workspace 301.7G/45465792i | repeat-01 collected 26/26 workers (60607 items) tests 8364 done 0 failed | 26 in flight, oldest 58s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
............................................................ [367%]
........................................................................ [370%]
..................................................[contention-diag] +1334s soak 28p/272t rss 11.1G pss 10.4G swap 1.0G majflt 8865 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G | host avail 25.4G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.61 | cgroup 10.9G/max oom_kill 0 | free scratch 301.7G/45465307i tmp 29.7G/1015880i workspace 301.7G/45465307i | repeat-01 collected 26/26 workers (60607 items) tests 8543 done 0 failed | 26 in flight, oldest 73s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
...................... [373%]
........................................................................ [376%]
........................................................................ [380%]
........................................................................ [383%]
....................[contention-diag] +1350s soak 29p/228t rss 11.1G pss 10.4G swap 1.0G majflt 8867 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 22.2G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 23.46 | cgroup 10.9G/max oom_kill 0 | free scratch 301.7G/45464654i tmp 29.7G/1015880i workspace 301.7G/45464654i | scratch used 0.2G in 29248 entries | repeat-01 collected 26/26 workers (60607 items) tests 8802 done 0 failed | 26 in flight, oldest 87s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................... [386%]
....[contention-diag] +1365s soak 28p/224t rss 11.1G pss 10.4G swap 1.0G majflt 9036 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.2G | host avail 23.0G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 20.73 | cgroup 10.9G/max oom_kill 0 | free scratch 301.4G/45464421i tmp 29.7G/1015880i workspace 301.4G/45464421i | repeat-01 collected 26/26 workers (60607 items) tests 8857 done 0 failed | 26 in flight, oldest 102s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..................................................................[contention-diag] +1381s soak 29p/242t rss 11.2G pss 10.4G swap 1.0G majflt 9080 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 24.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 23.78 | cgroup 10.9G/max oom_kill 0 | free scratch 301.3G/45464170i tmp 29.7G/1015880i workspace 301.3G/45464170i | repeat-01 collected 26/26 workers (60607 items) tests 8925 done 0 failed | 26 in flight, oldest 117s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.. [389%]
........................................................................ [392%]
........................................................................ [395%]
.......................................[contention-diag] +1396s soak 28p/244t rss 11.2G pss 10.4G swap 1.0G majflt 9084 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 24.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 24.15 | cgroup 11.0G/max oom_kill 0 | free scratch 301.3G/45463588i tmp 29.7G/1015880i workspace 301.3G/45463588i | repeat-01 collected 26/26 workers (60607 items) tests 9089 done 0 failed | 26 in flight, oldest 133s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................. [398%]
........................................................................ [402%]
.................................................................[contention-diag] +1412s soak 28p/236t rss 11.2G pss 10.5G swap 1.1G majflt 9088 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 22.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 21.81 | cgroup 11.0G/max oom_kill 0 | free scratch 301.0G/45463076i tmp 29.7G/1015880i workspace 301.0G/45463076i | repeat-01 collected 26/26 workers (60607 items) tests 9281 done 0 failed | 26 in flight, oldest 148s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
....... [405%]
....................................[contention-diag] +1427s soak 31p/267t rss 11.3G pss 10.5G swap 1.1G majflt 9090 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 3 descendant rss 0.1G pss 0.0G | host avail 28.4G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.77 cpu 24.54 | cgroup 11.0G/max oom_kill 0 | free scratch 301.2G/45462927i tmp 29.7G/1015879i workspace 301.2G/45462927i | repeat-01 collected 26/26 workers (60607 items) tests 9320 done 0 failed | 26 in flight, oldest 163s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................... [408%]
...[contention-diag] +1442s soak 29p/248t rss 11.3G pss 10.5G swap 1.1G majflt 9106 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.0G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.76 cpu 38.88 | cgroup 11.0G/max oom_kill 0 | free scratch 301.2G/45462715i tmp 29.7G/1015879i workspace 301.2G/45462715i | repeat-01 collected 26/26 workers (60607 items) tests 9362 done 0 failed | 26 in flight, oldest 69s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.......................[contention-diag] +1457s soak 29p/257t rss 11.3G pss 10.5G swap 1.1G majflt 9119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 29.0G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.7 cpu 28.83 | cgroup 11.0G/max oom_kill 0 | free scratch 301.2G/45462229i tmp 29.7G/1015879i workspace 301.2G/45462229i | repeat-01 collected 26/26 workers (60607 items) tests 9383 done 0 failed | 26 in flight, oldest 84s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.............................................. [411%]
.[contention-diag] +1473s soak 33p/286t rss 11.3G pss 10.6G swap 1.0G majflt 9182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G, 5 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 22.19 | cgroup 11.1G/max oom_kill 0 | free scratch 301.2G/45461934i tmp 29.7G/1015879i workspace 301.2G/45461934i | scratch used 0.2G in 31394 entries | repeat-01 collected 26/26 workers (60607 items) tests 9429 done 0 failed | 26 in flight, oldest 100s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.........................................................[contention-diag] +1488s soak 28p/241t rss 11.3G pss 10.5G swap 1.0G majflt 9197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 31.5G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 21.9 | cgroup 11.1G/max oom_kill 0 | free scratch 301.2G/45461723i tmp 29.7G/1015874i workspace 301.2G/45461723i | repeat-01 collected 26/26 workers (60607 items) tests 9486 done 0 failed | 26 in flight, oldest 115s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.............. [414%]
................[contention-diag] +1504s soak 28p/238t rss 11.3G pss 10.6G swap 1.0G majflt 9203 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G | host avail 32.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 28.09 | cgroup 11.1G/max oom_kill 0 | free scratch 301.2G/45461581i tmp 29.7G/1015879i workspace 301.2G/45461581i | repeat-01 collected 26/26 workers (60607 items) tests 9520 done 0 failed | 26 in flight, oldest 130s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
........................................................ [417%]
......[contention-diag] +1519s soak 29p/259t rss 11.4G pss 10.6G swap 1.0G majflt 9210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 27.01 | cgroup 11.1G/max oom_kill 0 | free scratch 301.2G/45461306i tmp 29.7G/1015879i workspace 301.2G/45461306i | repeat-01 collected 26/26 workers (60607 items) tests 9569 done 0 failed | 26 in flight, oldest 146s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................[contention-diag] +1534s soak 29p/260t rss 11.4G pss 10.6G swap 1.0G majflt 9274 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 29.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 22.85 | cgroup 11.2G/max oom_kill 0 | free scratch 301.2G/45461134i tmp 29.7G/1015879i workspace 301.2G/45461134i | repeat-01 collected 26/26 workers (60607 items) tests 9610 done 0 failed | 26 in flight, oldest 161s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
...........................[contention-diag] +1550s soak 28p/242t rss 11.4G pss 10.6G swap 1.0G majflt 9280 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.5G | host avail 30.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 25.78 | cgroup 11.2G/max oom_kill 0 | free scratch 301.2G/45461017i tmp 29.7G/1015879i workspace 301.2G/45461017i | repeat-01 collected 26/26 workers (60607 items) tests 9635 done 0 failed | 26 in flight, oldest 81s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........... [420%]
.........................................[contention-diag] +1565s soak 28p/249t rss 11.4G pss 10.6G swap 1.0G majflt 9284 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 32.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.12 | cgroup 11.2G/max oom_kill 0 | free scratch 301.2G/45460797i tmp 29.7G/1015879i workspace 301.2G/45460797i | repeat-01 collected 26/26 workers (60607 items) tests 9688 done 0 failed | 26 in flight, oldest 96s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................... [424%]
........................................................................ [427%]
..........................[contention-diag] +1580s soak 28p/247t rss 11.4G pss 10.6G swap 1.0G majflt 9287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 32.7G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.96 | cgroup 11.2G/max oom_kill 0 | free scratch 301.2G/45458046i tmp 29.7G/1015879i workspace 301.2G/45458046i | repeat-01 collected 26/26 workers (60607 items) tests 9804 done 0 failed | 25 in flight, oldest 111s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................. [430%]
........................................................................ [433%]
........................................................................ [436%]
..............................................[contention-diag] +1596s soak 28p/242t rss 11.4G pss 10.6G swap 1.0G majflt 9302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 32.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 22.16 | cgroup 11.2G/max oom_kill 0 | free scratch 301.2G/45452974i tmp 29.7G/1015879i workspace 301.2G/45452974i | scratch used 0.2G in 33557 entries | repeat-01 collected 26/26 workers (60607 items) tests 10039 done 0 failed | 26 in flight, oldest 127s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................... [439%]
........................................................[contention-diag] +1611s soak 28p/264t rss 11.4G pss 10.7G swap 1.0G majflt 9340 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 30.6G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 19.43 | cgroup 11.2G/max oom_kill 0 | free scratch 301.1G/45438846i tmp 29.7G/1015879i workspace 301.1G/45438846i | repeat-01 collected 26/26 workers (60607 items) tests 10132 done 0 failed | 26 in flight, oldest 142s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [442%]
.......[contention-diag] +1626s soak 28p/283t rss 11.4G pss 10.7G swap 1.0G majflt 9380 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G | host avail 33.2G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 26.1 | cgroup 11.3G/max oom_kill 0 | free scratch 301.1G/45438664i tmp 29.7G/1015879i workspace 301.1G/45438664i | repeat-01 collected 26/26 workers (60607 items) tests 10156 done 0 failed | 26 in flight, oldest 158s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.........................................[contention-diag] +1642s soak 29p/277t rss 11.6G pss 10.8G swap 1.0G majflt 9410 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 31.1G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 25.29 | cgroup 11.4G/max oom_kill 0 | free scratch 301.1G/45440429i tmp 29.7G/1015879i workspace 301.1G/45440429i | repeat-01 collected 26/26 workers (60607 items) tests 10196 done 0 failed | 26 in flight, oldest 173s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................ [446%]
............................................[contention-diag] +1657s soak 30p/264t rss 11.5G pss 10.7G swap 1.0G majflt 9415 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.5G, 2 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.33 | cgroup 11.3G/max oom_kill 0 | free scratch 301.1G/45437816i tmp 29.7G/1015879i workspace 301.1G/45437816i | repeat-01 collected 26/26 workers (60607 items) tests 10260 done 0 failed | 26 in flight, oldest 188s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................ [449%]
..............................................[contention-diag] +1672s soak 29p/268t rss 11.5G pss 10.7G swap 1.0G majflt 9424 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 30.3G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.31 | cgroup 11.3G/max oom_kill 0 | free scratch 301.1G/45426675i tmp 29.7G/1015879i workspace 301.1G/45426675i | repeat-01 collected 26/26 workers (60607 items) tests 10342 done 0 failed | 26 in flight, oldest 204s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................... [452%]
......................................................[contention-diag] +1688s soak 28p/257t rss 11.5G pss 10.7G swap 1.0G majflt 9432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 29.0G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.24/0.24 io 0.0 cpu 24.22 | cgroup 11.3G/max oom_kill 0 | free scratch 301.0G/45419169i tmp 29.7G/1015879i workspace 301.0G/45419169i | repeat-01 collected 26/26 workers (60607 items) tests 10421 done 0 failed | 26 in flight, oldest 219s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [455%]
........................................................................ [458%]
.............................[contention-diag] +1703s soak 28p/264t rss 11.5G pss 10.7G swap 1.0G majflt 9439 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 26.4G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.05 cpu 25.8 | cgroup 11.4G/max oom_kill 0 | free scratch 301.0G/45418799i tmp 29.7G/1015879i workspace 301.0G/45418799i | repeat-01 collected 26/26 workers (60607 items) tests 10541 done 0 failed | 26 in flight, oldest 234s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................................[contention-diag] +1718s soak 29p/280t rss 11.6G pss 10.8G swap 1.0G majflt 9439 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 55.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.8 | cgroup 11.4G/max oom_kill 0 | free scratch 300.7G/45418643i tmp 29.7G/1015879i workspace 300.7G/45418643i | scratch used 0.2G in 35555 entries | repeat-01 collected 26/26 workers (60607 items) tests 10578 done 0 failed | 26 in flight, oldest 249s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..... [461%]
......................................[contention-diag] +1734s soak 28p/275t rss 11.5G pss 10.8G swap 1.0G majflt 9445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G | host avail 22.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.81 | cgroup 11.4G/max oom_kill 0 | free scratch 300.1G/45418254i tmp 29.7G/1015879i workspace 300.1G/45418254i | repeat-01 collected 26/26 workers (60607 items) tests 10621 done 0 failed | 26 in flight, oldest 265s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
....................[contention-diag] +1749s soak 28p/275t rss 11.5G pss 10.7G swap 1.0G majflt 9473 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 28.3G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 17.03 | cgroup 11.4G/max oom_kill 0 | free scratch 300.3G/45418025i tmp 29.7G/1015879i workspace 300.3G/45418025i | repeat-01 collected 26/26 workers (60607 items) tests 10642 done 0 failed | 26 in flight, oldest 280s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............. [464%]
.......................................[contention-diag] +1764s soak 28p/278t rss 11.5G pss 10.7G swap 1.0G majflt 9487 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G | host avail 30.1G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.74 cpu 18.33 | cgroup 11.4G/max oom_kill 0 | free scratch 300.1G/45417508i tmp 29.7G/1015879i workspace 300.1G/45417508i | repeat-01 collected 26/26 workers (60607 items) tests 10687 done 0 failed | 26 in flight, oldest 296s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................. [468%]
........................................................................ [471%]
...[contention-diag] +1780s soak 33p/279t rss 11.6G pss 10.8G swap 1.0G majflt 9512 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 5 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 25.02 | cgroup 11.4G/max oom_kill 0 | free scratch 300.1G/45417131i tmp 29.7G/1015879i workspace 300.1G/45417131i | repeat-01 collected 26/26 workers (60607 items) tests 10796 done 0 failed | 26 in flight, oldest 311s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................................... [474%]
...................................................[contention-diag] +1795s soak 28p/281t rss 11.6G pss 10.8G swap 1.0G majflt 9568 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G | host avail 30.2G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 26.33 | cgroup 11.5G/max oom_kill 0 | free scratch 300.1G/45416784i tmp 29.7G/1015879i workspace 300.1G/45416784i | repeat-01 collected 26/26 workers (60607 items) tests 10921 done 0 failed | 26 in flight, oldest 65s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
..................... [477%]
........................................................................ [480%]
....................................................................[contention-diag] +1810s soak 32p/302t rss 11.7G pss 10.9G swap 1.0G majflt 9603 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 4 descendant rss 0.1G pss 0.0G | host avail 27.0G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 24.83 | cgroup 11.5G/max oom_kill 0 | free scratch 300.1G/45416318i tmp 29.7G/1015879i workspace 300.1G/45416318i | repeat-01 collected 26/26 workers (60607 items) tests 11081 done 0 failed | 26 in flight, oldest 80s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.... [483%]
........................................................................ [486%]
....................................................................[contention-diag] +1826s soak 32p/280t rss 11.7G pss 10.9G swap 1.0G majflt 9878 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 4 descendant rss 0.2G pss 0.1G | host avail 26.5G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.0 cpu 23.98 | cgroup 11.6G/max oom_kill 0 | free scratch 300.1G/45415830i tmp 29.7G/1015879i workspace 300.1G/45415830i | repeat-01 collected 26/26 workers (60607 items) tests 11226 done 0 failed | 26 in flight, oldest 62s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
.... [490%]
........................................................................ [493%]
.............[contention-diag] +1841s soak 30p/264t rss 11.6G pss 10.8G swap 1.0G majflt 9876 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 2 descendant rss 0.0G pss 0.0G | host avail 24.5G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.0 cpu 25.46 | cgroup 11.5G/max oom_kill 0 | free scratch 300.1G/45415626i tmp 29.7G/1015879i workspace 300.1G/45415626i | scratch used 0.2G in 38087 entries | repeat-01 collected 26/26 workers (60607 items) tests 11297 done 0 failed | 26 in flight, oldest 50s gw12 tests/ace/tui/test_plugins_browser_pane_marks.py::test_plugin_marks_do_not_constrain_unmarked_cli_update
........................................................... [496%]
..........................................[contention-diag] +1857s soak 30p/268t rss 11.7G pss 10.9G swap 1.0G majflt 9889 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 23.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.93 | cgroup 11.6G/max oom_kill 0 | free scratch 299.7G/45415258i tmp 29.7G/1015879i workspace 299.7G/45415258i | repeat-01 collected 26/26 workers (60607 items) tests 11416 done 0 failed | 26 in flight, oldest 46s gw5 tests/ace/tui/test_plugins_browser_pane_all_current.py::test_updates_pane_failed_core_probe_suppresses_all_current_banner
.............................. [499%]
...................................[contention-diag] +1872s soak 30p/283t rss 11.7G pss 10.8G swap 1.0G majflt 9893 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 25.8G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.87/0.87 io 0.42 cpu 12.1 | cgroup 11.5G/max oom_kill 0 | free scratch 300.1G/45413896i tmp 29.7G/1015877i workspace 300.1G/45413896i | repeat-01 collected 26/26 workers (60607 items) tests 11482 done 0 failed | 26 in flight, oldest 51s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
..................................... [502%]
....................[contention-diag] +1888s soak 31p/276t rss 11.7G pss 10.9G swap 1.0G majflt 9905 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.17/0.17 io 0.13 cpu 14.9 | cgroup 11.5G/max oom_kill 0 | free scratch 300.1G/45409867i tmp 29.7G/1015879i workspace 300.1G/45409862i | repeat-01 collected 26/26 workers (60607 items) tests 11532 done 0 failed | 26 in flight, oldest 55s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_summary_counts
.................................................... [505%]
...............[contention-diag] +1903s soak 29p/258t rss 11.7G pss 10.8G swap 1.1G majflt 9915 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.9G/62.7G swapfree 55.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 10.79 cpu 11.99 | cgroup 11.5G/max oom_kill 0 | free scratch 299.6G/45386243i tmp 29.7G/1015537i workspace 299.6G/45386243i | repeat-01 collected 26/26 workers (60607 items) tests 11597 done 0 failed | 24 in flight, oldest 68s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
......................................................... [508%]
..........................................................[contention-diag] +1918s soak 29p/258t rss 11.6G pss 10.7G swap 1.2G majflt 12466 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 27.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 3.82/3.26 io 19.23 cpu 8.88 | cgroup 11.2G/max oom_kill 0 | free scratch 299.4G/45381944i tmp 29.7G/1015804i workspace 299.4G/45381945i | repeat-01 collected 26/26 workers (60607 items) tests 11717 done 0 failed | 26 in flight, oldest 52s gw17 tests/ace/tui/test_projects_pane_current_project_seed.py::test_reload_reruns_current_project_resolve
.............. [512%]
........................................................................ [515%]
....[contention-diag] +1934s soak 29p/268t rss 11.6G pss 10.7G swap 1.2G majflt 12955 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 31.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.77/0.65 io 5.86 cpu 16.78 | cgroup 11.3G/max oom_kill 0 | free scratch 299.8G/45383080i tmp 29.7G/1015825i workspace 299.8G/45383080i | repeat-01 collected 26/26 workers (60607 items) tests 11807 done 0 failed | 26 in flight, oldest 54s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
...................[contention-diag] +1949s soak 31p/273t rss 11.7G pss 10.8G swap 1.2G majflt 13161 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.6G, 3 descendant rss 0.1G pss 0.0G | host avail 31.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.13 io 1.98 cpu 21.79 | cgroup 11.3G/max oom_kill 0 | free scratch 299.8G/45382804i tmp 29.7G/1015825i workspace 299.8G/45382804i | repeat-01 collected 26/26 workers (60607 items) tests 11829 done 0 failed | 26 in flight, oldest 70s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
................................................. [518%]
.....................................................[contention-diag] +1964s soak 28p/255t rss 11.6G pss 10.7G swap 1.2G majflt 13235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.6G | host avail 29.6G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.66 cpu 21.02 | cgroup 11.3G/max oom_kill 0 | free scratch 299.8G/45382446i tmp 29.7G/1015851i workspace 299.8G/45382446i | scratch used 0.2G in 40463 entries | repeat-01 collected 26/26 workers (60607 items) tests 11929 done 0 failed | 26 in flight, oldest 56s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................... [521%]
......................................[contention-diag] +1980s soak 31p/264t rss 11.8G pss 10.8G swap 1.2G majflt 13408 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.6G, 3 descendant rss 0.1G pss 0.0G | host avail 27.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.41 cpu 14.17 | cgroup 11.3G/max oom_kill 0 | free scratch 299.8G/45382478i tmp 29.7G/1015853i workspace 299.8G/45382478i | repeat-01 collected 26/26 workers (60607 items) tests 11988 done 0 failed | 26 in flight, oldest 72s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.................................. [524%]
........................................................................ [527%]
...................................[contention-diag] +1996s soak 31p/261t rss 11.7G pss 10.8G swap 1.2G majflt 13434 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 3 descendant rss 0.1G pss 0.1G | host avail 28.1G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 15.99 | cgroup 11.4G/max oom_kill 0 | free scratch 299.8G/45381099i tmp 29.7G/1015852i workspace 299.8G/45381099i | repeat-01 collected 26/26 workers (60607 items) tests 12130 done 0 failed | 26 in flight, oldest 87s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
..................................... [530%]
.................[contention-diag] +2011s soak 33p/251t rss 11.8G pss 10.8G swap 1.2G majflt 13445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 5 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.42 cpu 19.3 | cgroup 11.5G/max oom_kill 0 | free scratch 299.8G/45381777i tmp 29.7G/1015853i workspace 299.8G/45381777i | repeat-01 collected 26/26 workers (60607 items) tests 12180 done 0 failed | 26 in flight, oldest 103s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
....................................................... [534%]
........................................................................ [537%]
..................................[contention-diag] +2026s soak 29p/264t rss 11.7G pss 10.8G swap 1.2G majflt 13535 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 28.8G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 21.74 | cgroup 11.4G/max oom_kill 0 | free scratch 299.8G/45381214i tmp 29.7G/1015852i workspace 299.8G/45381214i | repeat-01 collected 26/26 workers (60607 items) tests 12344 done 0 failed | 26 in flight, oldest 54s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
...................................... [540%]
.............................................[contention-diag] +2042s soak 30p/265t rss 11.7G pss 10.8G swap 1.2G majflt 13597 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.1G pss 0.0G | host avail 25.9G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 20.48 | cgroup 11.4G/max oom_kill 0 | free scratch 299.8G/45380921i tmp 29.7G/1015852i workspace 299.8G/45380921i | repeat-01 collected 26/26 workers (60607 items) tests 12422 done 0 failed | 26 in flight, oldest 48s gw23 tests/ace/tui/test_link_follow_planner.py::test_epic_context_selects_and_expands
........................... [543%]
...........................................................[contention-diag] +2057s soak 30p/243t rss 11.8G pss 10.8G swap 1.2G majflt 13617 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.1G pss 0.0G | host avail 21.7G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 12.14 | cgroup 11.5G/max oom_kill 0 | free scratch 299.7G/45379525i tmp 29.7G/1015852i workspace 299.7G/45379525i | repeat-01 collected 26/26 workers (60607 items) tests 12514 done 0 failed | 26 in flight, oldest 47s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_digit_owns_hidden_member_jump_state[None]
............. [546%]
........................................................................ [549%]
........................................................................ [552%]
........................................................................ [556%]
..........[contention-diag] +2072s soak 31p/244t rss 11.8G pss 10.8G swap 1.1G majflt 13823 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 25.0G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 14.31 | cgroup 11.4G/max oom_kill 0 | free scratch 299.7G/45374309i tmp 29.7G/1015852i workspace 299.7G/45374310i | repeat-01 collected 26/26 workers (60607 items) tests 12736 done 0 failed | 26 in flight, oldest 46s gw21 tests/ace/tui/test_plugins_browser_pane_inventory.py::test_filter_miss_everywhere_keeps_generic_message
.............................................................. [559%]
................................................................[contention-diag] +2088s soak 30p/268t rss 11.8G pss 10.9G swap 1.1G majflt 13861 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 22.8G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.75/0.36 io 15.47 cpu 10.82 | cgroup 11.5G/max oom_kill 0 | free scratch 299.2G/45349506i tmp 29.7G/1015599i workspace 299.2G/45349506i | scratch used 0.1G in 22431 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 12876 done 0 failed | 26 in flight, oldest 61s gw21 tests/ace/tui/test_plugins_browser_pane_inventory.py::test_filter_miss_everywhere_keeps_generic_message
........ [562%]
....................................................[contention-diag] +2105s soak 31p/289t rss 11.8G pss 10.9G swap 1.1G majflt 14432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 29.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.12/0.05 io 14.92 cpu 12.04 | cgroup 11.5G/max oom_kill 0 | free scratch 299.5G/45350770i tmp 29.7G/1015798i workspace 299.5G/45350770i | repeat-01 collected 26/26 workers (60607 items) tests 12937 done 0 failed | 26 in flight, oldest 72s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.................... [565%]
........................................................................ [568%]
................................................................[contention-diag] +2120s soak 28p/247t rss 11.8G pss 10.9G swap 1.1G majflt 14600 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G | host avail 30.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 3.92 cpu 25.26 | cgroup 11.5G/max oom_kill 0 | free scratch 299.5G/45349917i tmp 29.7G/1015797i workspace 299.5G/45349917i | repeat-01 collected 26/26 workers (60607 items) tests 13088 done 0 failed | 26 in flight, oldest 68s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
........ [571%]
........................................................................ [574%]
........................................................................ [578%]
........................................................................ [581%]
..............................................[contention-diag] +2136s soak 29p/240t rss 11.8G pss 10.9G swap 1.1G majflt 14710 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 29.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 24.82 | cgroup 11.6G/max oom_kill 0 | free scratch 299.5G/45349185i tmp 29.7G/1015798i workspace 299.5G/45349185i | repeat-01 collected 26/26 workers (60607 items) tests 13361 done 0 failed | 26 in flight, oldest 83s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.......................... [584%]
........................................................................ [587%]
......................................[contention-diag] +2151s soak 30p/265t rss 11.8G pss 10.9G swap 1.1G majflt 14774 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 27.88 | cgroup 11.6G/max oom_kill 0 | free scratch 299.5G/45348819i tmp 29.7G/1015815i workspace 299.5G/45348819i | repeat-01 collected 26/26 workers (60607 items) tests 13501 done 0 failed | 26 in flight, oldest 59s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
.................................[contention-diag] +2166s soak 32p/279t rss 12.0G pss 11.1G swap 1.1G majflt 14956 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 4 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 19.94 | cgroup 11.7G/max oom_kill 0 | free scratch 299.5G/45348656i tmp 29.7G/1015826i workspace 299.5G/45348656i | repeat-01 collected 26/26 workers (60607 items) tests 13533 done 0 failed | 26 in flight, oldest 48s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_leaves_projects_tab_with_shift_tab
. [590%]
...................[contention-diag] +2182s soak 35p/281t rss 12.0G pss 11.1G swap 1.1G majflt 14949 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 7 descendant rss 0.1G pss 0.1G | host avail 29.4G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 23.75 | cgroup 11.7G/max oom_kill 0 | free scratch 299.4G/45347639i tmp 29.7G/1015826i workspace 299.4G/45347639i | repeat-01 collected 26/26 workers (60607 items) tests 13554 done 0 failed | 26 in flight, oldest 62s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
..................................................... [593%]
..................................................................[contention-diag] +2197s soak 32p/264t rss 11.9G pss 10.9G swap 1.1G majflt 14978 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.3/0.3 io 0.69 cpu 17.82 | cgroup 11.8G/max oom_kill 0 | free scratch 299.1G/45347911i tmp 29.7G/1015826i workspace 299.1G/45347911i | repeat-01 collected 26/26 workers (60607 items) tests 13667 done 0 failed | 26 in flight, oldest 77s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
...... [596%]
........................................................................ [600%]
........................................................................ [603%]
[contention-diag] +2212s soak 31p/249t rss 11.9G pss 11.0G swap 1.1G majflt 14986 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 3 descendant rss 0.0G pss 0.0G | host avail 32.5G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.35 cpu 22.44 | cgroup 11.7G/max oom_kill 0 | free scratch 297.9G/45347305i tmp 29.7G/1015826i workspace 297.9G/45347305i | scratch used 0.3G in 46686 entries | repeat-01 collected 26/26 workers (60607 items) tests 13820 done 0 failed | 26 in flight, oldest 76s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.............................[contention-diag] +2228s soak 33p/246t rss 11.9G pss 11.0G swap 1.1G majflt 15122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 5 descendant rss 0.0G pss 0.0G | host avail 29.6G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.11 cpu 28.14 | cgroup 11.8G/max oom_kill 0 | free scratch 297.8G/45347048i tmp 29.7G/1015826i workspace 297.8G/45347048i | repeat-01 collected 26/26 workers (60607 items) tests 13849 done 0 failed | 26 in flight, oldest 91s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
........................................... [606%]
...............................................[contention-diag] +2244s soak 33p/253t rss 11.9G pss 11.0G swap 1.1G majflt 15127 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.8G, 5 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 22.79 | cgroup 11.8G/max oom_kill 0 | free scratch 298.1G/45346787i tmp 29.7G/1015826i workspace 298.1G/45346787i | repeat-01 collected 26/26 workers (60607 items) tests 13938 done 0 failed | 26 in flight, oldest 107s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
......................... [609%]
........................................................................ [612%]
......................[contention-diag] +2259s soak 29p/269t rss 11.9G pss 11.0G swap 1.1G majflt 15184 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 26.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 23.56 | cgroup 11.8G/max oom_kill 0 | free scratch 297.9G/45346123i tmp 29.7G/1015826i workspace 297.9G/45346123i | repeat-01 collected 26/26 workers (60607 items) tests 14060 done 0 failed | 26 in flight, oldest 48s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_task_failure_reports_unsuccessful
.................................................. [615%]
...........................................................[contention-diag] +2274s soak 33p/256t rss 12.0G pss 11.0G swap 1.1G majflt 15196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 5 descendant rss 0.1G pss 0.0G | host avail 23.2G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 22.28 | cgroup 12.0G/max oom_kill 0 | free scratch 297.9G/45345840i tmp 29.7G/1015826i workspace 297.9G/45345840i | repeat-01 collected 26/26 workers (60607 items) tests 14168 done 0 failed | 26 in flight, oldest 54s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
............. [618%]
........................................................................ [621%]
........................................................................ [625%]
........................................................................ [628%]
.[contention-diag] +2290s soak 30p/240t rss 12.0G pss 11.1G swap 1.1G majflt 15290 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.1G pss 0.1G | host avail 24.4G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 23.44 | cgroup 12.0G/max oom_kill 0 | free scratch 297.6G/45344314i tmp 29.7G/1015826i workspace 297.6G/45344314i | repeat-01 collected 26/26 workers (60607 items) tests 14374 done 0 failed | 26 in flight, oldest 70s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
....................................................................... [631%]
........................................................................ [634%]
[contention-diag] +2305s soak 29p/251t rss 12.0G pss 11.0G swap 1.1G majflt 15352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 22.3G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.34 cpu 21.46 | cgroup 11.9G/max oom_kill 0 | free scratch 297.3G/45344256i tmp 29.7G/1015826i workspace 297.3G/45344256i | repeat-01 collected 26/26 workers (60607 items) tests 14539 done 0 failed | 26 in flight, oldest 43s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_complete_clears_marks_toasts_and_reloads
........................................................................ [637%]
........................................................................ [640%]
...............................[contention-diag] +2320s soak 30p/264t rss 12.0G pss 11.1G swap 1.1G majflt 15482 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 26.4G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.81 cpu 19.87 | cgroup 12.0G/max oom_kill 0 | free scratch 297.0G/45343374i tmp 29.7G/1015826i workspace 297.0G/45343374i | repeat-01 collected 26/26 workers (60607 items) tests 14710 done 0 failed | 26 in flight, oldest 47s gw9 tests/ace/tui/test_projects_pane.py::test_new_project_binding_is_scoped_and_filter_safe
......................................... [643%]
........................................................................ [647%]
.....................[contention-diag] +2336s soak 30p/259t rss 12.0G pss 11.1G swap 1.1G majflt 15643 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.9G, 2 descendant rss 0.0G pss 0.0G | host avail 30.3G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.94 cpu 21.67 | cgroup 12.0G/max oom_kill 0 | free scratch 296.9G/45342541i tmp 29.7G/1015826i workspace 296.9G/45342541i | scratch used 0.3G in 50850 entries | repeat-01 collected 26/26 workers (60607 items) tests 14848 done 0 failed | 26 in flight, oldest 58s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
................................................... [650%]
........................................................................ [653%]
........................................................................ [656%]
.................................................[contention-diag] +2351s soak 30p/241t rss 12.1G pss 11.1G swap 1.1G majflt 15670 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.9G, 2 descendant rss 0.1G pss 0.0G | host avail 29.0G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.38 cpu 20.16 | cgroup 12.0G/max oom_kill 0 | free scratch 296.7G/45341430i tmp 29.7G/1015826i workspace 296.7G/45341430i | repeat-01 collected 26/26 workers (60607 items) tests 15088 done 0 failed | 26 in flight, oldest 57s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
....................... [659%]
........................................................................ [662%]
........................................................................ [665%]
..............................................[contention-diag] +2367s soak 31p/241t rss 12.1G pss 11.2G swap 1.1G majflt 15810 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 3 descendant rss 0.1G pss 0.0G | host avail 27.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.57 cpu 22.7 | cgroup 12.0G/max oom_kill 0 | free scratch 296.6G/45340335i tmp 29.7G/1015826i workspace 296.6G/45340335i | repeat-01 collected 26/26 workers (60607 items) tests 15294 done 0 failed | 26 in flight, oldest 73s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
.......................... [669%]
........................................................................ [672%]
........................................................................ [675%]
.................[contention-diag] +2382s soak 32p/249t rss 12.1G pss 11.2G swap 1.1G majflt 15909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 4 descendant rss 0.0G pss 0.0G | host avail 26.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.36 cpu 21.65 | cgroup 12.0G/max oom_kill 0 | free scratch 296.5G/45339435i tmp 29.7G/1015826i workspace 296.5G/45339435i | repeat-01 collected 26/26 workers (60607 items) tests 15495 done 0 failed | 26 in flight, oldest 72s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
....................................................... [678%]
........................................................................ [681%]
....................................................[contention-diag] +2397s soak 33p/261t rss 12.2G pss 11.2G swap 1.1G majflt 16012 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 5 descendant rss 0.1G pss 0.0G | host avail 24.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.06 cpu 20.31 | cgroup 12.1G/max oom_kill 0 | free scratch 296.4G/45338919i tmp 29.7G/1015826i workspace 296.4G/45338919i | repeat-01 collected 26/26 workers (60607 items) tests 15674 done 0 failed | 26 in flight, oldest 87s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................... [684%]
........................................................................ [687%]
........................................................................ [691%]
..........[contention-diag] +2412s soak 34p/261t rss 12.2G pss 11.2G swap 1.0G majflt 16270 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 11.0G, 6 descendant rss 0.1G pss 0.0G | host avail 26.1G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.09 cpu 20.2 | cgroup 12.1G/max oom_kill 0 | free scratch 296.1G/45337093i tmp 29.7G/1015826i workspace 296.1G/45337093i | repeat-01 collected 26/26 workers (60607 items) tests 15847 done 0 failed | 26 in flight, oldest 102s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.............................................................. [694%]
........................................................................ [697%]
........................................................................ [700%]
..............................................[contention-diag] +2428s soak 35p/261t rss 12.4G pss 11.3G swap 1.0G majflt 16323 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 7 descendant rss 0.2G pss 0.1G | host avail 25.9G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 26.19 | cgroup 12.1G/max oom_kill 0 | free scratch 296.0G/45333851i tmp 29.7G/1015826i workspace 296.0G/45333851i | repeat-01 collected 26/26 workers (60607 items) tests 16085 done 0 failed | 26 in flight, oldest 118s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.......................... [703%]
........................................................................ [706%]
........................................................................ [709%]
........................................................................ [713%]
[contention-diag] +2443s soak 35p/246t rss 12.3G pss 11.3G swap 1.0G majflt 16479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 7 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.66 cpu 22.64 | cgroup 12.2G/max oom_kill 0 | free scratch 295.8G/45316329i tmp 29.7G/1015826i workspace 295.8G/45316329i | repeat-01 collected 26/26 workers (60607 items) tests 16302 done 0 failed | 26 in flight, oldest 133s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................................................ [716%]
........................................................................ [719%]
........................................................................ [722%]
........................................................................ [725%]
........[contention-diag] +2458s soak 34p/284t rss 12.3G pss 11.3G swap 1.0G majflt 17064 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 6 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.82 cpu 22.55 | cgroup 12.2G/max oom_kill 0 | free scratch 295.5G/45313568i tmp 29.7G/1015826i workspace 295.5G/45313568i | scratch used 0.3G in 58475 entries | repeat-01 collected 26/26 workers (60607 items) tests 16625 done 0 failed | 25 in flight, oldest 148s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................................ [728%]
........................................................................ [731%]
...............................[contention-diag] +2474s soak 32p/281t rss 12.3G pss 11.3G swap 1.0G majflt 16672 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 4 descendant rss 0.1G pss 0.1G | host avail 28.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.22 cpu 20.68 | cgroup 12.2G/max oom_kill 0 | free scratch 295.6G/45312875i tmp 29.7G/1015826i workspace 295.6G/45312875i | repeat-01 collected 26/26 workers (60607 items) tests 16800 done 0 failed | 26 in flight, oldest 164s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
......................................... [735%]
........................................................................ [738%]
..................................................[contention-diag] +2490s soak 33p/271t rss 12.4G pss 11.4G swap 1.0G majflt 16977 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.1G, 5 descendant rss 0.1G pss 0.1G | host avail 27.6G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.05 cpu 19.76 | cgroup 12.3G/max oom_kill 0 | free scratch 295.2G/45315173i tmp 29.7G/1015826i workspace 295.2G/45315173i | repeat-01 collected 26/26 workers (60607 items) tests 16961 done 0 failed | 26 in flight, oldest 100s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
...................... [741%]
........................................................................ [744%]
........................................................................ [747%]
........................................................................ [750%]
..........[contention-diag] +2505s soak 32p/246t rss 12.4G pss 11.4G swap 1.0G majflt 17043 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 4 descendant rss 0.1G pss 0.0G | host avail 26.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.45 cpu 20.51 | cgroup 12.4G/max oom_kill 0 | free scratch 294.6G/45313788i tmp 29.7G/1015825i workspace 294.6G/45313788i | repeat-01 collected 26/26 workers (60607 items) tests 17213 done 0 failed | 26 in flight, oldest 116s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.............................................................. [753%]
........................................................................ [757%]
........................................................................ [760%]
.......[contention-diag] +2520s soak 33p/220t rss 12.4G pss 11.4G swap 1.0G majflt 17570 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 5 descendant rss 0.1G pss 0.0G | host avail 28.1G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.2/0.2 io 2.27 cpu 16.77 | cgroup 12.4G/max oom_kill 0 | free scratch 294.2G/45311963i tmp 29.7G/1015825i workspace 294.2G/45311962i | repeat-01 collected 26/26 workers (60607 items) tests 17428 done 0 failed | 25 in flight, oldest 97s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
................................................................. [763%]
........................................................................ [766%]
........................................................................ [769%]
........................................................................ [772%]
.......................[contention-diag] +2536s soak 38p/234t rss 12.3G pss 11.3G swap 1.0G majflt 17612 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 10 descendant rss 0.0G pss 0.0G | host avail 27.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 2.36 cpu 13.02 | cgroup 12.4G/max oom_kill 0 | free scratch 293.5G/45310550i tmp 29.7G/1015823i workspace 293.5G/45310550i | repeat-01 collected 26/26 workers (60607 items) tests 17719 done 0 failed | 26 in flight, oldest 112s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
................................................. [775%]
........................................................................ [779%]
........................................................................ [782%]
...................[contention-diag] +2551s soak 30p/238t rss 12.3G pss 11.3G swap 1.0G majflt 17675 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 2 descendant rss 0.0G pss 0.0G | host avail 29.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.14 cpu 15.31 | cgroup 12.2G/max oom_kill 0 | free scratch 293.3G/45310161i tmp 29.7G/1015823i workspace 293.3G/45310161i | repeat-01 collected 26/26 workers (60607 items) tests 17938 done 0 failed | 26 in flight, oldest 39s gw21 tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
..................................................... [785%]
........................................................................ [788%]
.........................................[contention-diag] +2566s soak 33p/264t rss 12.4G pss 11.4G swap 1.0G majflt 17721 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 5 descendant rss 0.0G pss 0.0G | host avail 29.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.63 cpu 20.06 | cgroup 12.3G/max oom_kill 0 | free scratch 291.2G/45299527i tmp 29.7G/1015823i workspace 291.2G/45299527i | repeat-01 collected 26/26 workers (60607 items) tests 18110 done 0 failed | 26 in flight, oldest 54s gw21 tests/footprint/test_tui.py::test_tui_contract_pilot_records_each_seam_once
............................... [791%]
........................................................................ [794%]
........................................................................ [797%]
...........................................................[contention-diag] +2582s soak 34p/235t rss 12.5G pss 11.5G swap 1.0G majflt 17748 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.2G, 6 descendant rss 0.2G pss 0.1G | host avail 28.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.88 cpu 20.3 | cgroup 12.4G/max oom_kill 0 | free scratch 291.0G/45288407i tmp 29.7G/1015823i workspace 291.0G/45288407i | scratch used 0.3G in 61359 entries | repeat-01 collected 26/26 workers (60607 items) tests 18320 done 0 failed | 26 in flight, oldest 60s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
............. [801%]
........................................................................ [804%]
........................................................................ [807%]
.........................................................[contention-diag] +2598s soak 31p/235t rss 12.4G pss 11.4G swap 1.0G majflt 17814 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 3 descendant rss 0.1G pss 0.0G | host avail 25.6G/62.7G swapfree 53.0G/64.0G oom_kill +0 | psi10 mem 0.71/0.0 io 4.97 cpu 14.24 | cgroup 12.5G/max oom_kill 0 | free scratch 290.9G/45287560i tmp 29.7G/1015823i workspace 290.9G/45287560i | repeat-01 collected 26/26 workers (60607 items) tests 18555 done 0 failed | 26 in flight, oldest 52s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............... [810%]
....................................................................[contention-diag] +2614s soak 34p/243t rss 12.4G pss 11.3G swap 1.1G majflt 17859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 6 descendant rss 0.0G pss 0.0G | host avail 21.5G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 0.89/0.0 io 2.74 cpu 11.15 | cgroup 12.3G/max oom_kill 0 | free scratch 290.8G/45287395i tmp 29.7G/1015823i workspace 290.8G/45287395i | repeat-01 collected 26/26 workers (60607 items) tests 18642 done 0 failed | 26 in flight, oldest 67s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.... [813%]
........................................................................ [816%]
..............[contention-diag] +2629s soak 37p/247t rss 12.4G pss 11.4G swap 1.1G majflt 17950 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 9 descendant rss 0.1G pss 0.1G | host avail 23.6G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.22/0.0 io 3.09 cpu 12.21 | cgroup 12.4G/max oom_kill 0 | free scratch 291.0G/45286829i tmp 29.7G/1015823i workspace 291.0G/45286829i | repeat-01 collected 26/26 workers (60607 items) tests 18722 done 0 failed | 26 in flight, oldest 83s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
.......................................................... [819%]
........................................................................ [823%]
........................................................................ [826%]
........................................................................ [829%]
...................................[contention-diag] +2645s soak 32p/247t rss 12.4G pss 11.4G swap 1.1G majflt 18017 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 4 descendant rss 0.1G pss 0.1G | host avail 22.8G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 2.83 cpu 15.25 | cgroup 12.4G/max oom_kill 0 | free scratch 290.5G/45284031i tmp 29.7G/1015823i workspace 290.5G/45284031i | repeat-01 collected 26/26 workers (60607 items) tests 19029 done 0 failed | 26 in flight, oldest 98s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
..................................... [832%]
........................................................................ [835%]
........................................................................ [838%]
........................................................................ [841%]
.......................s................................................ [845%]
..............[contention-diag] +2660s soak 39p/240t rss 12.4G pss 11.4G swap 1.1G majflt 18045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 11 descendant rss 0.1G pss 0.1G | host avail 23.2G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 3.95 cpu 14.1 | cgroup 12.4G/max oom_kill 0 | free scratch 290.3G/45268429i tmp 29.7G/1015823i workspace 290.3G/45268429i | repeat-01 collected 26/26 workers (60607 items) tests 19356 done 0 failed | 26 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
.......................................................... [848%]
........................................................................ [851%]
................................s..s.................................... [854%]
.......................[contention-diag] +2675s soak 33p/248t rss 12.4G pss 11.3G swap 1.1G majflt 18092 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 5 descendant rss 0.1G pss 0.0G | host avail 23.6G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.94 cpu 14.76 | cgroup 12.4G/max oom_kill 0 | free scratch 290.2G/45264089i tmp 29.7G/1015823i workspace 290.2G/45264089i | repeat-01 collected 26/26 workers (60607 items) tests 19606 done 0 failed | 26 in flight, oldest 43s gw1 tests/test_command_palette_e2e.py::test_colon_opens_command_line_from_axe_tab
................................................. [857%]
......................................................[contention-diag] +2691s soak 32p/245t rss 12.4G pss 11.4G swap 1.1G majflt 18271 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 4 descendant rss 0.1G pss 0.0G | host avail 22.5G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.27/0.27 io 2.33 cpu 13.96 | cgroup 12.4G/max oom_kill 0 | free scratch 290.0G/45263750i tmp 29.7G/1015823i workspace 290.0G/45263750i | repeat-01 collected 26/26 workers (60607 items) tests 19688 done 0 failed | 26 in flight, oldest 59s gw1 tests/test_command_palette_e2e.py::test_colon_opens_command_line_from_axe_tab
.................. [860%]
........................................................................ [863%]
........................................................................ [867%]
........................................................................ [870%]
.............................................[contention-diag] +2706s soak 30p/255t rss 12.4G pss 11.4G swap 1.1G majflt 18376 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 2 descendant rss 0.0G pss 0.0G | host avail 28.5G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 1.47 cpu 14.15 | cgroup 12.4G/max oom_kill 0 | free scratch 290.1G/45262637i tmp 29.7G/1015823i workspace 290.1G/45262637i | scratch used 0.3G in 49471 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 19936 done 0 failed | 26 in flight, oldest 47s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................... [873%]
........................................................................ [876%]
......s................................................................. [879%]
.......................................................[contention-diag] +2723s soak 36p/266t rss 12.5G pss 11.4G swap 1.1G majflt 18577 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 8 descendant rss 0.1G pss 0.1G | host avail 25.7G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.04/0.01 io 2.69 cpu 17.5 | cgroup 12.5G/max oom_kill 0 | free scratch 290.6G/45261074i tmp 29.7G/1015809i workspace 290.6G/45261074i | repeat-01 collected 26/26 workers (60607 items) tests 20211 done 0 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
................. [882%]
........................................................................ [885%]
.............................................[contention-diag] +2739s soak 33p/255t rss 12.5G pss 11.4G swap 1.1G majflt 18635 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 5 descendant rss 0.1G pss 0.1G | host avail 25.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 11.63/9.79 io 11.77 cpu 12.3 | cgroup 12.4G/max oom_kill 0 | free scratch 290.5G/45259558i tmp 29.7G/1015809i workspace 290.5G/45259558i | repeat-01 collected 26/26 workers (60607 items) tests 20344 done 0 failed | 26 in flight, oldest 80s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................... [889%]
........................................................................ [892%]
....[contention-diag] +2754s soak 32p/274t rss 12.5G pss 11.4G swap 1.1G majflt 18783 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 4 descendant rss 0.0G pss 0.0G | host avail 23.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 2.87/2.41 io 5.59 cpu 15.11 | cgroup 12.4G/max oom_kill 0 | free scratch 290.5G/45259234i tmp 29.7G/1015809i workspace 290.5G/45259234i | repeat-01 collected 26/26 workers (60607 items) tests 20448 done 0 failed | 26 in flight, oldest 95s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................................................................... [895%]
..............................................................[contention-diag] +2770s soak 33p/255t rss 12.5G pss 11.4G swap 1.1G majflt 18971 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 5 descendant rss 0.1G pss 0.0G | host avail 21.6G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.64/0.55 io 2.12 cpu 14.78 | cgroup 12.4G/max oom_kill 0 | free scratch 290.3G/45257629i tmp 29.7G/1015809i workspace 290.3G/45257629i | repeat-01 collected 26/26 workers (60607 items) tests 20576 done 0 failed | 26 in flight, oldest 111s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.......... [898%]
........................................................................ [901%]
........................................................................ [904%]
................................[contention-diag] +2785s soak 37p/231t rss 12.6G pss 11.5G swap 1.1G majflt 19107 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 9 descendant rss 0.1G pss 0.1G | host avail 21.6G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.27/0.11 io 1.63 cpu 14.23 | cgroup 12.5G/max oom_kill 0 | free scratch 289.8G/45256622i tmp 29.7G/1015811i workspace 289.8G/45256622i | repeat-01 collected 26/26 workers (60607 items) tests 20753 done 0 failed | 26 in flight, oldest 54s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
........................................ [907%]
........................................................................ [910%]
........................................................................ [914%]
........................................[contention-diag] +2800s soak 47p/216t rss 12.6G pss 11.4G swap 1.2G majflt 19158 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 19 descendant rss 0.2G pss 0.1G | host avail 26.2G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.06/0.02 io 3.58 cpu 10.95 | cgroup 12.5G/max oom_kill 0 | free scratch 289.8G/45254999i tmp 29.7G/1015811i workspace 289.8G/45254999i | repeat-01 collected 26/26 workers (60607 items) tests 20982 done 0 failed | 26 in flight, oldest 34s gw20 tests/autonomy_contract/test_record_flag_states.py::test_launch_row_outcomes_match_contract[bare]
................................ [917%]
........................................................................ [920%]
........................................................................ [923%]
........................................................................ [926%]
.................................[contention-diag] +2816s soak 33p/211t rss 12.6G pss 11.5G swap 1.1G majflt 19293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G, 5 descendant rss 0.2G pss 0.1G | host avail 32.2G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.16/0.0 io 3.55 cpu 14.73 | cgroup 12.5G/max oom_kill 0 | free scratch 289.8G/45254328i tmp 29.7G/1015811i workspace 289.8G/45254327i | repeat-01 collected 26/26 workers (60607 items) tests 21261 done 0 failed | 25 in flight, oldest 46s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
....................................... [929%]
........................................................................ [932%]
........................................................................ [936%]
........................................................................ [939%]
..............................[contention-diag] +2831s soak 36p/216t rss 12.6G pss 11.5G swap 1.2G majflt 19519 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.1G, 8 descendant rss 0.2G pss 0.2G | host avail 25.1G/62.7G swapfree 53.6G/64.0G oom_kill +0 | psi10 mem 0.88/0.6 io 11.25 cpu 13.64 | cgroup 12.5G/max oom_kill 0 | free scratch 289.5G/45226407i tmp 29.7G/1015227i workspace 289.5G/45226407i | scratch used 0.1G in 13768 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 21541 done 0 failed | 26 in flight, oldest 61s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
.......................................... [942%]
........................................F[contention-failure] call tests/fakey/test_cli.py::test_sigterm_during_barrier_exits_cleanly: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw23/test_sigterm_during_barrier_ex0')

    @pytest.mark.skipif(os.name != "posix", reason="SIGTERM behavior is POSIX-specific")
    def test_sigterm_during_barrier_exits_cleanly(tmp_path: Path) -> None:
        state = tmp_path / "state"
        started = tmp_path / "started"
        scenario = tmp_path / "terminate.yml"
        scenario.write_text(
            f"steps:\n  - signal: {started}\n"
            f"  - wait_for: {{path: {tmp_path / 'never'}, timeout: 10}}\n"
        )
        process = subprocess.Popen(
            [sys.executable, "-m", "sase.fakey.cli", "-s", str(scenario)],
            stdin=subprocess.PIPE,
            stdout=subprocess.PIPE,
            stderr=subprocess.PIPE,
            text=True,
            env=_environment(state),
        )
        try:
            assert process.stdin is not None
            process.stdin.close()
            deadline = time.monotonic() + 2
            while not started.exists() and time.monotonic() < deadline:
                time.sleep(min(0.01, max(0.0, deadline - time.monotonic())))
>           assert started.exists()
E           AssertionError: assert False
E            +  where False = exists()
E            +    where exists = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw23/test_sigterm_during_barrier_ex0/started').exists

tests/fakey/test_cli.py:264: AssertionError
..........................[contention-diag] +2848s soak 34p/198t rss 12.6G pss 11.4G swap 1.3G majflt 19888 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 6 descendant rss 0.2G pss 0.2G | host avail 24.0G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 15.66/12.6 io 32.35 cpu 8.11 | cgroup 12.5G/max oom_kill 0 | free scratch 290.3G/45227214i tmp 29.7G/1015684i workspace 290.3G/45227214i | repeat-01 collected 26/26 workers (60607 items) tests 21667 done 1 failed | 26 in flight, oldest 50s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
..... [945%]
........................................................................ [948%]
........................................................................ [951%]
........................................................................ [954%]
..[contention-diag] +2864s soak 43p/220t rss 12.7G pss 11.5G swap 1.3G majflt 20162 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.1G, 15 descendant rss 0.3G pss 0.2G | host avail 23.8G/62.7G swapfree 52.8G/64.0G oom_kill +0 | psi10 mem 3.16/2.54 io 16.12 cpu 8.77 | cgroup 12.5G/max oom_kill 0 | free scratch 290.1G/45223425i tmp 29.7G/1015756i workspace 290.1G/45223425i | repeat-01 collected 26/26 workers (60607 items) tests 21874 done 1 failed | 25 in flight, oldest 66s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
...................................................................... [958%]
........................................................................ [961%]
....F[contention-failure] call tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read: self = <Popen: returncode: -9 args: ('/tmp/sase-1rq-runtime-py312/bin/python', '-mp...>
timeout = 60

    def wait(self, timeout=None):
        """Wait for child process to terminate; returns self.returncode."""
        if timeout is not None:
            endtime = _time() + timeout
        try:
>           return self._wait(timeout=timeout)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:1264: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ('/tmp/sase-1rq-runtime-py312/bin/python', '-mp...>
timeout = 60

    def _wait(self, timeout):
        """Internal implementation of wait() on POSIX."""
        if self.returncode is not None:
            return self.returncode
    
        if timeout is not None:
            endtime = _time() + timeout
            # Enter a busy loop if we have a timeout.  This busy loop was
            # cribbed from Lib/threading.py in Thread.wait() at r71065.
            delay = 0.0005 # 500 us -> initial delay of 1 ms
            while True:
                if self._waitpid_lock.acquire(False):
                    try:
                        if self.returncode is not None:
                            break  # Another thread waited.
                        (pid, sts) = self._try_wait(os.WNOHANG)
                        assert pid == self.pid or pid == 0
                        if pid == self.pid:
                            self._handle_exitstatus(sts)
                            break
                    finally:
                        self._waitpid_lock.release()
                remaining = self._remaining_time(endtime)
                if remaining <= 0:
>                   raise TimeoutExpired(self.args, timeout)
E                   subprocess.TimeoutExpired: Command '('/tmp/sase-1rq-runtime-py312/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0/runpytest-0', '-p', 'no:randomly', '-c', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml', '--rootdir', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_poisoner_leaves_blocked_refresh_worker', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_victim_first_reads_use_only_successor_patched_paths')' timed out after 60 seconds

/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:2045: TimeoutExpired

During handling of the above exception, another exception occurred:

pytester = <Pytester PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0')>

    def test_blocked_refre
................................................................... [964%]
........................................................................ [967%]
....................................[contention-diag] +2879s soak 35p/203t rss 12.4G pss 11.2G swap 1.3G majflt 20608 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 7 descendant rss 0.1G pss 0.1G | host avail 21.9G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 1.33/0.51 io 13.94 cpu 8.35 | cgroup 12.2G/max oom_kill 0 | free scratch 290.0G/45223624i tmp 29.7G/1015756i workspace 290.0G/45223624i | repeat-01 collected 26/26 workers (60607 items) tests 22201 done 2 failed | 26 in flight, oldest 44s gw1 tests/test_command_palette_e2e.py::test_palette_executes_refresh_from_axe_tab
.................................... [970%]
........................................................................ [973%]
........................................................................ [976%]
........................................................................ [980%]
.......................................................................[contention-diag] +2894s soak 34p/178t rss 12.5G pss 11.3G swap 1.3G majflt 20747 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 6 descendant rss 0.1G pss 0.1G | host avail 18.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.57/0.31 io 16.63 cpu 8.42 | cgroup 12.2G/max oom_kill 0 | free scratch 289.9G/45222891i tmp 29.7G/1015769i workspace 289.9G/45222891i | repeat-01 collected 26/26 workers (60607 items) tests 22531 done 2 failed | 26 in flight, oldest 53s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_refresh_and_hidden_tab_keep_the_active_view_rail
. [983%]
........................................................................ [986%]
........................................................................ [989%]
..................................[contention-diag] +2910s soak 34p/195t rss 12.5G pss 11.3G swap 1.4G majflt 20861 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.1G pss 11.0G, 6 descendant rss 0.2G pss 0.2G | host avail 15.5G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 2.75/1.74 io 14.22 cpu 9.13 | cgroup 11.7G/max oom_kill 0 | free scratch 289.8G/45221684i tmp 29.7G/1015784i workspace 289.8G/45221684i | repeat-01 collected 26/26 workers (60607 items) tests 22702 done 2 failed | 26 in flight, oldest 54s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.................................s.... [992%]
...........................s............................................ [995%]
........................................................................ [998%]
........................................................................ [1002%]
..........[contention-diag] +2925s soak 39p/203t rss 12.5G pss 11.3G swap 1.4G majflt 21020 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 11 descendant rss 0.2G pss 0.1G | host avail 15.3G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 1.46/1.07 io 8.48 cpu 8.21 | cgroup 11.6G/max oom_kill 0 | free scratch 289.7G/45219066i tmp 29.7G/1015784i workspace 289.7G/45219066i | repeat-01 collected 26/26 workers (60607 items) tests 22978 done 2 failed | 26 in flight, oldest 70s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.............................................................. [1005%]
........................................................................ [1008%]
........................................................................ [1011%]
........................................................................ [1014%]
........................................................................ [1017%]
..........................[contention-diag] +2941s soak 35p/211t rss 12.4G pss 11.3G swap 1.4G majflt 21430 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 11.0G, 7 descendant rss 0.1G pss 0.1G | host avail 15.2G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.36/0.21 io 5.52 cpu 9.21 | cgroup 11.7G/max oom_kill 0 | free scratch 289.4G/45210014i tmp 29.7G/1015784i workspace 289.4G/45210014i | repeat-01 collected 26/26 workers (60607 items) tests 23331 done 2 failed | 26 in flight, oldest 85s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.............................................. [1020%]
........................................................................ [1024%]
........................................................................ [1027%]
.....................................................................[contention-diag] +2956s soak 34p/207t rss 12.3G pss 11.2G swap 1.4G majflt 21834 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 6 descendant rss 0.1G pss 0.1G | host avail 15.3G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.26/0.05 io 8.26 cpu 9.14 | cgroup 11.6G/max oom_kill 0 | free scratch 289.5G/45204299i tmp 29.7G/1015784i workspace 289.5G/45204299i | scratch used 0.0G in 5826 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 23565 done 2 failed | 25 in flight, oldest 101s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
... [1030%]
........................................................................ [1033%]
........................................................................ [1036%]
........................................................................ [1039%]
.......................[contention-diag] +2974s soak 42p/210t rss 12.5G pss 11.3G swap 1.5G majflt 22595 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 14 descendant rss 0.3G pss 0.2G | host avail 20.2G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 0.43/0.04 io 6.05 cpu 9.62 | cgroup 12.0G/max oom_kill 0 | free scratch 289.4G/45197718i tmp 29.7G/1015784i workspace 289.4G/45197718i | repeat-01 collected 26/26 workers (60607 items) tests 23854 done 2 failed | 26 in flight, oldest 118s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
................................................. [1042%]
........................................................................ [1046%]
........................................................................ [1049%]
........................................................................ [1052%]
.............[contention-diag] +2989s soak 33p/188t rss 12.3G pss 11.1G swap 1.5G majflt 22953 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 5 descendant rss 0.1G pss 0.1G | host avail 18.2G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 0.37/0.0 io 7.09 cpu 9.49 | cgroup 11.8G/max oom_kill 0 | free scratch 289.3G/45190503i tmp 29.7G/1015784i workspace 289.3G/45190503i | repeat-01 collected 26/26 workers (60607 items) tests 24112 done 2 failed | 26 in flight, oldest 133s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........................................................... [1055%]
........................................................................ [1058%]
........................................................................ [1061%]
........................................................................ [1064%]
.....[contention-diag] +3004s soak 35p/182t rss 12.4G pss 11.2G swap 1.5G majflt 23814 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 7 descendant rss 0.2G pss 0.1G | host avail 18.2G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 0.24/0.0 io 5.09 cpu 9.12 | cgroup 11.9G/max oom_kill 0 | free scratch 289.3G/45184909i tmp 29.7G/1015784i workspace 289.3G/45184909i | repeat-01 collected 26/26 workers (60607 items) tests 24403 done 2 failed | 26 in flight, oldest 149s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
................................................................... [1068%]
........................................................................ [1071%]
........................................................................ [1074%]
.........................................[contention-diag] +3020s soak 31p/187t rss 12.3G pss 11.1G swap 1.6G majflt 24793 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 20.1G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 1.51/0.0 io 5.7 cpu 9.49 | cgroup 11.8G/max oom_kill 0 | free scratch 289.3G/45180217i tmp 29.7G/1015784i workspace 289.3G/45180217i | repeat-01 collected 26/26 workers (60607 items) tests 24658 done 2 failed | 24 in flight, oldest 164s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
............................... [1077%]
........................................................................ [1080%]
........................................................................ [1083%]
........................................................................ [1086%]
..........................................................[contention-diag] +3035s soak 35p/190t rss 12.2G pss 11.1G swap 1.5G majflt 25715 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.0G pss 0.0G | host avail 19.4G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 1.03/0.0 io 4.27 cpu 10.2 | cgroup 11.8G/max oom_kill 0 | free scratch 289.3G/45174733i tmp 29.7G/1015784i workspace 289.3G/45174733i | repeat-01 collected 26/26 workers (60607 items) tests 24965 done 2 failed | 25 in flight, oldest 180s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.............. [1090%]
........................................................................ [1093%]
...............................................................s........ [1096%]
........................................................................ [1099%]
.............................................[contention-diag] +3050s soak 39p/187t rss 12.4G pss 11.2G swap 1.5G majflt 27712 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 11 descendant rss 0.2G pss 0.1G | host avail 19.1G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.96/0.0 io 4.91 cpu 9.87 | cgroup 12.0G/max oom_kill 0 | free scratch 289.2G/45169378i tmp 29.7G/1015784i workspace 289.2G/45169378i | repeat-01 collected 26/26 workers (60607 items) tests 25245 done 2 failed | 26 in flight, oldest 195s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........................... [1102%]
........................................................................ [1105%]
.................................................[contention-diag] +3066s soak 40p/191t rss 12.4G pss 11.2G swap 1.5G majflt 27924 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 12 descendant rss 0.2G pss 0.1G | host avail 17.8G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 0.19/0.0 io 3.35 cpu 9.45 | cgroup 11.9G/max oom_kill 0 | free scratch 289.2G/45164517i tmp 29.7G/1015784i workspace 289.2G/45164517i | repeat-01 collected 26/26 workers (60607 items) tests 25390 done 2 failed | 25 in flight, oldest 210s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
....................... [1108%]
........................................................................ [1112%]
........................................................................ [1115%]
........................................................................ [1118%]
........................................................................ [1121%]
...[contention-diag] +3082s soak 35p/169t rss 12.4G pss 11.2G swap 1.6G majflt 28519 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 7 descendant rss 0.2G pss 0.1G | host avail 16.7G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 0.4/0.0 io 4.23 cpu 8.66 | cgroup 11.9G/max oom_kill 0 | free scratch 289.2G/45161306i tmp 29.7G/1015784i workspace 289.2G/45161306i | scratch used 0.1G in 16757 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 25686 done 2 failed | 26 in flight, oldest 226s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
..................................................................... [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
..[contention-diag] +3099s soak 34p/171t rss 12.3G pss 11.1G swap 1.6G majflt 29007 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 6 descendant rss 0.2G pss 0.1G | host avail 18.8G/62.7G swapfree 50.7G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 5.48 cpu 8.98 | cgroup 11.9G/max oom_kill 0 | free scratch 294.2G/45159442i tmp 29.7G/1015784i workspace 294.2G/45159442i | repeat-01 collected 26/26 workers (60607 items) tests 25919 done 2 failed | 26 in flight, oldest 243s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...................................................................... [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
........................................................................ [1143%]
..................................................[contention-diag] +3114s soak 37p/178t rss 12.4G pss 11.1G swap 1.6G majflt 29362 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.8G, 9 descendant rss 0.2G pss 0.1G | host avail 16.5G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.19/0.0 io 3.53 cpu 9.22 | cgroup 12.0G/max oom_kill 0 | free scratch 294.2G/45154745i tmp 29.7G/1015784i workspace 294.2G/45154745i | repeat-01 collected 26/26 workers (60607 items) tests 26257 done 2 failed | 26 in flight, oldest 259s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
...................... [1146%]
........................................................................ [1149%]
........................................................................ [1152%]
........................................................................ [1156%]
........................................................................ [1159%]
.[contention-diag] +3130s soak 31p/159t rss 12.3G pss 11.1G swap 1.6G majflt 29882 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 15.5G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 10.04 cpu 8.49 | cgroup 12.0G/max oom_kill 0 | free scratch 294.2G/45150822i tmp 29.7G/1015784i workspace 294.2G/45150822i | repeat-01 collected 26/26 workers (60607 items) tests 26564 done 2 failed | 25 in flight, oldest 274s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
....................................................................... [1162%]
........................................................................ [1165%]
........................................................................ [1168%]
.....................................................................[contention-diag] +3145s soak 35p/171t rss 12.4G pss 11.2G swap 1.6G majflt 30182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.2G pss 0.1G | host avail 16.2G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 12.62 cpu 8.5 | cgroup 12.1G/max oom_kill 0 | free scratch 294.1G/45146909i tmp 29.7G/1015783i workspace 294.1G/45146909i | repeat-01 collected 26/26 workers (60607 items) tests 26844 done 2 failed | 26 in flight, oldest 153s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
... [1171%]
........................................................................ [1174%]
........................................................................ [1178%]
........................................................................ [1181%]
...................................................[contention-diag] +3160s soak 34p/169t rss 12.4G pss 11.2G swap 1.6G majflt 30637 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 6 descendant rss 0.2G pss 0.1G | host avail 15.7G/62.7G swapfree 52.6G/64.0G oom_kill +0 | psi10 mem 0.18/0.09 io 11.38 cpu 8.32 | cgroup 12.0G/max oom_kill 0 | free scratch 294.1G/45144442i tmp 29.7G/1015781i workspace 294.1G/45144442i | repeat-01 collected 26/26 workers (60607 items) tests 27116 done 2 failed | 26 in flight, oldest 169s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..................... [1184%]
........................................................................ [1187%]
........................................................................ [1190%]
.............................................................[contention-diag] +3176s soak 35p/176t rss 12.5G pss 11.2G swap 1.6G majflt 30935 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.2G pss 0.1G | host avail 15.4G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 7.94 cpu 8.8 | cgroup 12.0G/max oom_kill 0 | free scratch 294.1G/45141375i tmp 29.7G/1015783i workspace 294.1G/45141375i | repeat-01 collected 26/26 workers (60607 items) tests 27332 done 2 failed | 26 in flight, oldest 184s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........... [1193%]
........................................................................ [1196%]
........................................................................ [1200%]
........................................................................ [1203%]
........................................................................ [1206%]
.[contention-diag] +3191s soak 36p/170t rss 12.5G pss 11.2G swap 1.6G majflt 31141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.9G, 8 descendant rss 0.2G pss 0.1G | host avail 16.3G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.58 cpu 9.55 | cgroup 12.1G/max oom_kill 0 | free scratch 293.8G/45138635i tmp 29.7G/1015783i workspace 293.8G/45138635i | repeat-01 collected 26/26 workers (60607 items) tests 27633 done 2 failed | 24 in flight, oldest 200s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................................................... [1209%]
........................................................................ [1212%]
........................................................................ [1215%]
........................................................................ [1218%]
........................................................................ [1221%]
........................................................................ [1225%]
...[contention-diag] +3206s soak 35p/175t rss 12.5G pss 11.3G swap 1.6G majflt 31865 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.8G, 7 descendant rss 0.2G pss 0.2G | host avail 15.7G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 6.71 cpu 9.19 | cgroup 12.0G/max oom_kill 0 | free scratch 294.1G/45132920i tmp 29.7G/1015783i workspace 294.1G/45132920i | scratch used 0.1G in 21830 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 28036 done 2 failed | 25 in flight, oldest 215s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..................................................................... [1228%]
........................................................................ [1231%]
......................................[contention-diag] +3224s soak 36p/176t rss 12.2G pss 11.0G swap 1.7G majflt 32128 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.7G, 8 descendant rss 0.1G pss 0.1G | host avail 15.4G/62.7G swapfree 52.4G/64.0G oom_kill +0 | psi10 mem 1.78/0.19 io 6.2 cpu 9.74 | cgroup 11.6G/max oom_kill 0 | free scratch 294.0G/45122194i tmp 29.7G/1015783i workspace 294.0G/45122194i | repeat-01 collected 26/26 workers (60607 items) tests 28255 done 2 failed | 25 in flight, oldest 232s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................. [1234%]
........................................................................ [1237%]
........................................................................ [1240%]
........................................................................ [1243%]
[contention-diag] +3239s soak 34p/172t rss 12.0G pss 10.7G swap 2.1G majflt 34659 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 6 descendant rss 0.1G pss 0.1G | host avail 15.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 5.06/0.9 io 7.08 cpu 8.95 | cgroup 11.3G/max oom_kill 0 | free scratch 293.9G/45111559i tmp 29.7G/1015783i workspace 293.9G/45111559i | repeat-01 collected 26/26 workers (60607 items) tests 28504 done 2 failed | 25 in flight, oldest 248s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................................................ [1247%]
........................................................................ [1250%]
......[contention-diag] +3255s soak 33p/167t rss 11.8G pss 10.5G swap 2.3G majflt 42304 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.2G, 5 descendant rss 0.1G pss 0.1G | host avail 13.7G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 6.44/1.65 io 11.97 cpu 9.65 | cgroup 11.0G/max oom_kill 0 | free scratch 293.9G/45107500i tmp 29.7G/1015783i workspace 293.9G/45107500i | repeat-01 collected 26/26 workers (60607 items) tests 28660 done 2 failed | 25 in flight, oldest 263s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................................................. [1253%]
........................................................................ [1256%]
............................[contention-diag] +3270s soak 35p/170t rss 11.8G pss 10.6G swap 2.2G majflt 54802 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.3G, 7 descendant rss 0.1G pss 0.0G | host avail 15.0G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 1.3/0.33 io 8.33 cpu 10.41 | cgroup 11.1G/max oom_kill 0 | free scratch 293.9G/45103368i tmp 29.7G/1015783i workspace 293.9G/45103368i | repeat-01 collected 26/26 workers (60607 items) tests 28825 done 2 failed | 24 in flight, oldest 211s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................................ [1259%]
........................................................................ [1262%]
........................................................................ [1265%]
..............................................[contention-diag] +3285s soak 35p/174t rss 11.9G pss 10.7G swap 2.2G majflt 56538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 7 descendant rss 0.1G pss 0.1G | host avail 14.4G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.31/0.08 io 8.73 cpu 10.2 | cgroup 11.2G/max oom_kill 0 | free scratch 293.9G/45100831i tmp 29.7G/1015783i workspace 293.9G/45100831i | repeat-01 collected 26/26 workers (60607 items) tests 29055 done 2 failed | 25 in flight, oldest 226s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.......................... [1269%]
........................................................................ [1272%]
........................................................................ [1275%]
.......................................................................[contention-diag] +3301s soak 34p/169t rss 12.0G pss 10.7G swap 2.2G majflt 57447 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 6 descendant rss 0.2G pss 0.1G | host avail 14.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.01 io 5.16 cpu 9.29 | cgroup 11.2G/max oom_kill 0 | free scratch 293.8G/45097262i tmp 29.7G/1015783i workspace 293.8G/45097262i | repeat-01 collected 26/26 workers (60607 items) tests 29289 done 2 failed | 25 in flight, oldest 241s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
. [1278%]
........................................................................ [1281%]
........................................................................ [1284%]
........................................................................ [1287%]
.........................................................[contention-diag] +3316s soak 32p/161t rss 11.9G pss 10.6G swap 2.1G majflt 58509 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 4 descendant rss 0.1G pss 0.0G | host avail 14.0G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 3.69 cpu 8.22 | cgroup 11.2G/max oom_kill 0 | free scratch 293.6G/45092617i tmp 29.7G/1015783i workspace 293.6G/45092617i | repeat-01 collected 26/26 workers (60607 items) tests 29576 done 2 failed | 25 in flight, oldest 257s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............... [1291%]
........................................................................ [1294%]
........................................................................ [1297%]
........................................................................ [1300%]
........................................................................ [1303%]
...........[contention-diag] +3331s soak 36p/170t rss 12.1G pss 10.7G swap 2.1G majflt 59444 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 8 descendant rss 0.2G pss 0.1G | host avail 13.5G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.26 cpu 9.13 | cgroup 11.3G/max oom_kill 0 | free scratch 293.3G/45086655i tmp 29.7G/1015783i workspace 293.3G/45086655i | scratch used 0.0G in 5484 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 29862 done 2 failed | 25 in flight, oldest 272s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................................................. [1306%]
........................................................................ [1309%]
........................................................................ [1313%]
.............................................................[contention-diag] +3349s soak 36p/187t rss 12.1G pss 10.8G swap 2.1G majflt 60028 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 8 descendant rss 0.2G pss 0.2G | host avail 12.3G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 11.49 cpu 8.26 | cgroup 11.3G/max oom_kill 0 | free scratch 293.2G/45081188i tmp 29.7G/1015782i workspace 293.2G/45081188i | repeat-01 collected 26/26 workers (60607 items) tests 30141 done 2 failed | 24 in flight, oldest 289s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
........... [1316%]
........................................................................ [1319%]
........................................................................ [1322%]
........................................................................ [1325%]
........................................................................ [1328%]
...............[contention-diag] +3364s soak 35p/171t rss 12.0G pss 10.6G swap 2.2G majflt 62407 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.3G, 7 descendant rss 0.1G pss 0.1G | host avail 13.1G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.27/0.0 io 10.05 cpu 8.04 | cgroup 11.0G/max oom_kill 0 | free scratch 293.1G/45078859i tmp 29.7G/1015783i workspace 293.1G/45078859i | repeat-01 collected 26/26 workers (60607 items) tests 30455 done 2 failed | 23 in flight, oldest 305s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
......................................................... [1331%]
........................................................................ [1335%]
........................................................................ [1338%]
........................................................................ [1341%]
....................................................................[contention-diag] +3380s soak 38p/170t rss 11.8G pss 10.5G swap 2.3G majflt 63335 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 11.9G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 13.34 cpu 8.22 | cgroup 10.8G/max oom_kill 0 | free scratch 293.0G/45075508i tmp 29.7G/1015779i workspace 293.0G/45075508i | repeat-01 collected 26/26 workers (60607 items) tests 30805 done 2 failed | 25 in flight, oldest 320s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.... [1344%]
........................................................................ [1347%]
........................................................................ [1350%]
........................................................................ [1353%]
........................................................................ [1357%]
........................................................................ [1360%]
..........................[contention-diag] +3395s soak 33p/163t rss 11.6G pss 10.2G swap 2.6G majflt 67490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 9.9G, 5 descendant rss 0.1G pss 0.1G | host avail 10.9G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 2.69/0.22 io 13.25 cpu 7.94 | cgroup 10.5G/max oom_kill 0 | free scratch 292.9G/45072834i tmp 29.7G/1015771i workspace 292.9G/45072834i | repeat-01 collected 26/26 workers (60607 items) tests 31188 done 2 failed | 25 in flight, oldest 336s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.............................................. [1363%]
........................................................................ [1366%]
.......................................................................[contention-diag] +3410s soak 34p/175t rss 11.3G pss 10.0G swap 3.0G majflt 80739 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 6 descendant rss 0.2G pss 0.1G | host avail 10.6G/62.7G swapfree 49.7G/64.0G oom_kill +0 | psi10 mem 6.78/0.52 io 7.77 cpu 9.41 | cgroup 10.4G/max oom_kill 0 | free scratch 292.8G/45066644i tmp 29.7G/1015771i workspace 292.8G/45066644i | repeat-01 collected 26/26 workers (60607 items) tests 31384 done 2 failed | 25 in flight, oldest 351s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
. [1369%]
........................................................................ [1372%]
........................................................................ [1375%]
........................................................................ [1379%]
........................................................................ [1382%]
........................................................................ [1385%]
.....................................[contention-diag] +3426s soak 34p/165t rss 11.3G pss 10.0G swap 2.9G majflt 84238 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 10.9G pss 9.7G, 6 descendant rss 0.2G pss 0.1G | host avail 10.6G/62.7G swapfree 49.7G/64.0G oom_kill +0 | psi10 mem 3.12/0.1 io 5.56 cpu 9.82 | cgroup 10.3G/max oom_kill 0 | free scratch 292.5G/45060311i tmp 29.7G/1015771i workspace 292.5G/45060311i | repeat-01 collected 26/26 workers (60607 items) tests 31775 done 2 failed | 23 in flight, oldest 367s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
................................... [1388%]
........................................................................ [1391%]
........................................................................ [1394%]
........................................................................ [1397%]
........................................................................ [1401%]
........................................................................ [1404%]
..........[contention-diag] +3441s soak 34p/165t rss 11.5G pss 10.2G swap 2.9G majflt 87944 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.0G pss 9.7G, 6 descendant rss 0.3G pss 0.3G | host avail 11.8G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 2.74/0.02 io 4.06 cpu 9.86 | cgroup 10.6G/max oom_kill 0 | free scratch 292.5G/45053226i tmp 29.7G/1015759i workspace 292.5G/45053226i | repeat-01 collected 26/26 workers (60607 items) tests 32179 done 2 failed | 25 in flight, oldest 382s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.............................................................. [1407%]
........................................................................ [1410%]
.........................................................[contention-diag] +3456s soak 34p/164t rss 11.5G pss 10.2G swap 2.9G majflt 94037 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.0G pss 9.7G, 6 descendant rss 0.3G pss 0.2G | host avail 12.3G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 2.3/0.0 io 3.65 cpu 9.9 | cgroup 10.6G/max oom_kill 0 | free scratch 292.3G/45048891i tmp 29.7G/1015759i workspace 292.3G/45048891i | scratch used 0.1G in 10332 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 32361 done 2 failed | 25 in flight, oldest 397s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............... [1413%]
........................................................................ [1416%]
........................................................................ [1419%]
........................................................................ [1423%]
..........................................[contention-diag] +3474s soak 33p/170t rss 11.7G pss 10.3G swap 2.7G majflt 111311 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 9.9G, 5 descendant rss 0.3G pss 0.2G | host avail 13.7G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 2.29/0.0 io 3.74 cpu 7.78 | cgroup 11.1G/max oom_kill 0 | free scratch 291.8G/45042601i tmp 29.7G/1015758i workspace 291.8G/45042601i | repeat-01 collected 26/26 workers (60607 items) tests 32649 done 2 failed | 25 in flight, oldest 415s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.............................. [1426%]
........................................................................ [1429%]
........................................................................ [1432%]
........................................................................ [1435%]
........................................................................ [1438%]
.................[contention-diag] +3489s soak 34p/180t rss 11.6G pss 10.2G swap 2.7G majflt 117886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 9.9G, 6 descendant rss 0.2G pss 0.1G | host avail 13.7G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 3.19/0.38 io 4.12 cpu 9.41 | cgroup 10.8G/max oom_kill 0 | free scratch 291.7G/45038593i tmp 29.7G/1015759i workspace 291.7G/45038593i | repeat-01 collected 26/26 workers (60607 items) tests 32990 done 2 failed | 25 in flight, oldest 430s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
....................................................... [1441%]
........................................................................ [1445%]
........................................................................ [1448%]
........................................................................ [1451%]
.....[contention-diag] +3505s soak 36p/186t rss 11.5G pss 10.2G swap 2.7G majflt 118987 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 9.9G, 8 descendant rss 0.1G pss 0.1G | host avail 13.6G/62.7G swapfree 49.7G/64.0G oom_kill +0 | psi10 mem 1.02/0.07 io 6.02 cpu 9.61 | cgroup 10.8G/max oom_kill 0 | free scratch 291.7G/45033300i tmp 29.7G/1015759i workspace 291.7G/45033300i | repeat-01 collected 26/26 workers (60607 items) tests 33248 done 2 failed | 25 in flight, oldest 445s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 4 hazardous kill call(s)
................................................................... [1454%]
........................................................................ [1457%]
........................................................................ [1460%]
........................................................................ [1463%]
.............[contention-diag] +3520s soak 32p/184t rss 11.3G pss 10.0G swap 3.0G majflt 120729 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 4 descendant rss 0.1G pss 0.1G | host avail 11.3G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 0.54/0.2 io 7.14 cpu 8.8 | cgroup 10.5G/max oom_kill 0 | free scratch 291.6G/45028540i tmp 29.7G/1015759i workspace 291.6G/45028540i | repeat-01 collected 26/26 workers (60607 items) tests 33548 done 2 failed | 25 in flight, oldest 355s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
........................................................... [1467%]
........................................................................ [1470%]
.....................................................[contention-diag] +3535s soak 36p/189t rss 11.3G pss 9.9G swap 3.0G majflt 128160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 8 descendant rss 0.1G pss 0.1G | host avail 11.3G/62.7G swapfree 48.5G/64.0G oom_kill +0 | psi10 mem 0.25/0.17 io 5.94 cpu 9.13 | cgroup 10.4G/max oom_kill 0 | free scratch 291.6G/45024870i tmp 29.7G/1015759i workspace 291.6G/45024870i | repeat-01 collected 26/26 workers (60607 items) tests 33735 done 2 failed | 25 in flight, oldest 370s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................... [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1482%]
........................................................................ [1485%]
........................................................................ [1489%]
.......[contention-diag] +3551s soak 36p/193t rss 11.2G pss 9.8G swap 3.2G majflt 139330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.8G pss 9.5G, 8 descendant rss 0.2G pss 0.1G | host avail 9.7G/62.7G swapfree 47.5G/64.0G oom_kill +0 | psi10 mem 0.56/0.46 io 7.2 cpu 8.07 | cgroup 10.3G/max oom_kill 0 | free scratch 291.4G/45020616i tmp 29.7G/1015759i workspace 291.4G/45020616i | repeat-01 collected 26/26 workers (60607 items) tests 34126 done 2 failed | 25 in flight, oldest 386s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................................................................. [1492%]
........................................................................ [1495%]
........................................................................ [1498%]
........................................................................ [1501%]
.........[contention-diag] +3566s soak 32p/173t rss 11.2G pss 9.9G swap 3.0G majflt 151850 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 4 descendant rss 0.1G pss 0.1G | host avail 10.0G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.29/0.27 io 7.52 cpu 8.45 | cgroup 10.3G/max oom_kill 0 | free scratch 290.9G/45016764i tmp 29.7G/1015759i workspace 290.9G/45016764i | repeat-01 collected 26/26 workers (60607 items) tests 34408 done 2 failed | 25 in flight, oldest 401s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
............................................................... [1504%]
........................................................................ [1507%]
........................................................................ [1510%]
........................................................................ [1514%]
.................................[contention-diag] +3582s soak 39p/209t rss 11.3G pss 10.0G swap 3.0G majflt 154345 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 11 descendant rss 0.1G pss 0.1G | host avail 11.5G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 5.2/3.81 io 10.6 cpu 8.44 | cgroup 10.3G/max oom_kill 0 | free scratch 289.6G/45014692i tmp 29.7G/1015759i workspace 289.6G/45014692i | scratch used 0.0G in 2692 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 34681 done 2 failed | 25 in flight, oldest 417s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
....................................... [1517%]
........................................................................ [1520%]
....................................................................[contention-diag] +3599s soak 31p/174t rss 11.3G pss 9.9G swap 3.0G majflt 155253 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 3 descendant rss 0.1G pss 0.1G | host avail 16.1G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 0.85/0.63 io 4.81 cpu 9.32 | cgroup 10.5G/max oom_kill 0 | free scratch 289.3G/45008629i tmp 29.7G/1015759i workspace 289.3G/45008629i | repeat-01 collected 26/26 workers (60607 items) tests 34914 done 2 failed | 25 in flight, oldest 434s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
.... [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
...............................F[contention-failure] call tests/test_notification_modal_scroll.py::test_uppercase_g_reaches_detail_bottom_from_real_input_path[#notification-list-shift+g-G]: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw17/test_uppercase_g_reaches_detai0')
key = 'shift+g', character = 'G', focus_selector = '#notification-list'

    @pytest.mark.parametrize(
        ("key", "character"),
        [
            ("G", "G"),
            ("shift+g", None),
            ("shift+g", "G"),
            ("g", "G"),
        ],
    )
    @pytest.mark.parametrize(
        "focus_selector", ["#notification-list", "#notification-file-scroll"]
    )
    async def test_uppercase_g_reaches_detail_bottom_from_real_input_path(
        tmp_path: Path,
        key: str,
        character: str | None,
        focus_selector: str,
    ) -> None:
        path = tmp_path / "long.txt"
        path.write_text("\n".join(f"line {i:03d}" for i in range(240)), encoding="utf-8")
        notification = _make_notification("n1")
        notification.files = [str(path)]
        dismissed: list[object | None] = []
    
        async with _StyledTestApp().run_test(size=(120, 40)) as pilot:
            modal = NotificationModal([notification])
            pilot.app.push_screen(modal, callback=dismissed.append)
            await pilot.pause()
            await pilot.pause()
    
            scroll = modal.query_one("#notification-file-scroll", VerticalScroll)
            await wait_for(pilot, lambda: scroll.max_scroll_y > 0)
    
            modal.query_one(focus_selector).focus()
            scroll.scroll_to(y=min(100, scroll.max_scroll_y - 1), animate=False)
            await pilot.pause()
            assert 0 < scroll.scroll_y < scroll.max_scroll_y
    
            bottom = MagicMock(wraps=modal.action_scroll_file_bottom)
            top = MagicMock(wraps=modal.action_scroll_file_top)
            modal.action_scroll_file_bottom = bottom  # type: ignore[method-assign]
            modal.action_scroll_file_top = top  # type: ignore[method-assign]
    
            pilot.app.post_message(events.Key(key, character))
            await pilot.pause()
    
>           assert scroll.scroll_y == scroll.max_scroll_y
E           AssertionError: assert 100 == 221
E            +  where 100 = VerticalScroll(id='notification-file-scroll').scroll_y
E            +  and   221 = VerticalScroll(id='notification-file-scroll').max_scroll_y

tests/test_notification_modal_scroll.py:69: AssertionError
........................................ [1532%]
........................................................................ [1536%]
..............F[contention-failure] call tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw8/test_provider_drain_e2e_relaun0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f3099489af0>

    def test_provider_drain_e2e_relaunches_stranded_agent(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        harness = FakeyRetryHarness(tmp_path, monkeypatch, max_retries=1, wait_times=[0])
        _configure_reroute_environment(monkeypatch, harness)
        second_artifacts = _seed_second_agent(harness)
        # The best-effort usage-refresh limit-event trigger is orthogonal to
        # drain ownership (covered by test_usage_refresh.py); disable it so it
        # does not add an unrelated submit_proc_request call to this drill.
        monkeypatch.setattr(
            "sase.llm_provider.usage_limit_disable._trigger_usage_refresh_after_limit",
            lambda provider, outcome: None,
        )
    
        from sase.procs import submit_proc_request as real_submit_proc_request
    
        captured_requests: list[ProcSubmitRequest] = []
        captured_procs: list[Proc] = []
    
        def _capturing_submit(request: ProcSubmitRequest) -> Proc:
            captured_requests.append(request)
            proc = real_submit_proc_request(request)
            captured_procs.append(proc)
            return proc
    
        with patch(
            "sase.procs.submit_proc_request", side_effect=_capturing_submit
        ) as mock_submit:
            _run_trigger_to_disable(harness, monkeypatch)
    
        # Exactly one active hard disable for fakey, written by the trigger's
        # own real usage-limit failure.
        disables = get_active_provider_disables()
        assert set(disables) == {"fakey"}
        assert disables["fakey"].source == "usage_limit"
        assert disables["fakey"].is_hard
    
        # Exactly one agent.drain proc submitted, with the exact argv and
        # concurrency key the automatic path promises.
        mock_submit.assert_called_once()
        request = captured_requests[0]
        assert request.argv == [
            "sase",
            "agent",
            "drain",
            "fakey",
            "--yes",
            "--json",
            "--limit",
            "20",
        ]
        assert request.operation == AGENT_DRAIN
        assert request.concurrency_keys == ["provider-drain:fakey"]
        assert request.operation_payload is not None
        assert request.operation_payload["notify"] is True
        assert request.operation_payload["trigger_artifacts_dir"] == str(harness.artifacts)
    
        proc = captured_procs[0]
        finished = wait_for_proc(proc.proc_id, timeout=_DRAIN_WAIT_TIMEOUT)
    
        result = _read_drain_result(proc.proc_id)
        payload = result.payload
        assert payload is not None, f"drain reported no payload: {result.error}"
        assert payload["provider"] == "fakey"
        moves = payload["moves"]
        assert len(moves) == 1
        moved = mo
......................................................... [1539%]
........................................................................ [1542%]
...[contention-diag] +3615s soak 33p/184t rss 11.3G pss 10.0G swap 3.0G majflt 156384 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.0G pss 9.6G, 5 descendant rss 0.1G pss 0.1G | host avail 17.2G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 0.17/0.12 io 4.49 cpu 8.68 | cgroup 11.0G/max oom_kill 0 | free scratch 289.1G/45005972i tmp 29.7G/1015759i workspace 289.1G/45005974i | repeat-01 collected 26/26 workers (60607 items) tests 35341 done 4 failed | 25 in flight, oldest 170s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
..................................................................... [1545%]
........................................................................ [1548%]
........................................................................ [1551%]
...........................................[contention-diag] +3630s soak 32p/187t rss 11.3G pss 10.0G swap 3.0G majflt 156862 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.0G pss 9.7G, 4 descendant rss 0.1G pss 0.1G | host avail 18.0G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 22.92 cpu 7.21 | cgroup 10.9G/max oom_kill 0 | free scratch 288.9G/44991848i tmp 29.7G/1015759i workspace 288.9G/44991848i | repeat-01 collected 26/26 workers (60607 items) tests 35606 done 4 failed | 25 in flight, oldest 186s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
............................. [1554%]
........................................................................ [1558%]
........................................................................ [1561%]
.......[contention-diag] +3646s soak 29p/165t rss 11.2G pss 9.9G swap 3.0G majflt 157358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 11.0G pss 9.7G, 1 descendant rss 0.0G pss 0.0G | host avail 14.5G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 31.45 cpu 5.97 | cgroup 10.9G/max oom_kill 0 | free scratch 288.6G/44978898i tmp 29.7G/1015321i workspace 288.6G/44978898i | repeat-01 collected 26/26 workers (60607 items) tests 35774 done 4 failed | 21 in flight, oldest 202s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
................................................................. [1564%]
.......................................................................[contention-diag] +3662s soak 36p/183t rss 11.3G pss 9.9G swap 3.1G majflt 157607 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 10.9G pss 9.6G, 8 descendant rss 0.1G pss 0.1G | host avail 15.9G/62.7G swapfree 46.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 34.05 cpu 6.11 | cgroup 10.4G/max oom_kill 0 | free scratch 289.0G/44970150i tmp 29.7G/1015299i workspace 289.0G/44970150i | repeat-01 collected 26/26 workers (60607 items) tests 35915 done 4 failed | 20 in flight, oldest 218s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
. [1567%]
........................................................................ [1570%]
........................................................................ [1573%]
........................................................................ [1576%]
....................................................................[contention-diag] +3678s soak 33p/173t rss 11.1G pss 9.7G swap 3.2G majflt 158333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.5G, 5 descendant rss 0.1G pss 0.1G | host avail 18.3G/62.7G swapfree 45.5G/64.0G oom_kill +0 | psi10 mem 7.19/5.36 io 24.72 cpu 6.8 | cgroup 10.1G/max oom_kill 0 | free scratch 288.9G/44967248i tmp 29.7G/1015703i workspace 288.9G/44967248i | repeat-01 collected 26/26 workers (60607 items) tests 36210 done 4 failed | 25 in flight, oldest 234s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
.... [1580%]
........................................................................ [1583%]
........................................................................ [1586%]
........................................................................ [1589%]
.........................................................s.[contention-diag] +3694s soak 31p/185t rss 11.2G pss 9.8G swap 3.2G majflt 159826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.6G, 3 descendant rss 0.1G pss 0.1G | host avail 18.4G/62.7G swapfree 45.5G/64.0G oom_kill +0 | psi10 mem 1.99/1.32 io 10.07 cpu 9.08 | cgroup 10.2G/max oom_kill 0 | free scratch 289.0G/44965882i tmp 29.7G/1015704i workspace 289.0G/44965882i | repeat-01 collected 26/26 workers (60607 items) tests 36474 done 4 failed | 25 in flight, oldest 249s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
............. [1592%]
........................................................................ [1595%]
........................................................................ [1598%]
........................................................................ [1602%]
........................................................................ [1605%]
........................................................................ [1608%]
......s................................................................. [1611%]
[contention-diag] +3709s soak 35p/195t rss 11.3G pss 9.9G swap 3.2G majflt 161880 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.6G, 7 descendant rss 0.2G pss 0.1G | host avail 18.4G/62.7G swapfree 45.6G/64.0G oom_kill +0 | psi10 mem 1.04/0.26 io 4.72 cpu 9.68 | cgroup 10.3G/max oom_kill 0 | free scratch 289.0G/44962597i tmp 29.7G/1015703i workspace 289.0G/44962597i | scratch used 0.1G in 8354 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 36885 done 4 failed | 25 in flight, oldest 264s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
........................................................................ [1614%]
........................................................................ [1617%]
........................................................................ [1620%]
.............................................................[contention-diag] +3726s soak 33p/191t rss 11.4G pss 9.9G swap 3.2G majflt 165638 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.6G, 5 descendant rss 0.2G pss 0.2G | host avail 16.3G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 1.44/0.04 io 7.58 cpu 8.38 | cgroup 10.5G/max oom_kill 0 | free scratch 289.0G/44959565i tmp 29.7G/1015731i workspace 289.0G/44959565i | repeat-01 collected 26/26 workers (60607 items) tests 37190 done 4 failed | 22 in flight, oldest 282s gw15 tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales | 7 hazardous kill call(s)
........... [1624%]
........................................................................ [1627%]
........................................................................ [1630%]
..........................................[contention-diag] +3742s soak 34p/184t rss 11.3G pss 9.9G swap 3.2G majflt 169361 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.7G, 6 descendant rss 0.2G pss 0.1G | host avail 16.0G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.71/0.0 io 9.63 cpu 8.71 | cgroup 10.4G/max oom_kill 0 | free scratch 289.0G/44957694i tmp 29.7G/1015732i workspace 289.0G/44957694i | repeat-01 collected 26/26 workers (60607 items) tests 37409 done 4 failed | 24 in flight, oldest 257s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 7 hazardous kill call(s)
.............................. [1633%]
........................................................................ [1636%]
............................................................[contention-diag] +3757s soak 35p/173t rss 11.2G pss 9.9G swap 3.1G majflt 173628 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.7G, 7 descendant rss 0.1G pss 0.0G | host avail 17.2G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.58/0.0 io 13.0 cpu 7.06 | cgroup 10.4G/max oom_kill 0 | free scratch 289.0G/44955866i tmp 29.7G/1015732i workspace 289.0G/44955866i | repeat-01 collected 26/26 workers (60607 items) tests 37563 done 4 failed | 24 in flight, oldest 177s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
............ [1639%]
........................................................................ [1642%]
........................................................................ [1646%]
........................................................................ [1649%]
.....................................................................[contention-diag] +3773s soak 33p/194t rss 11.3G pss 9.9G swap 3.1G majflt 174906 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 9.7G, 5 descendant rss 0.1G pss 0.1G | host avail 17.3G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 0.11/0.0 io 11.3 cpu 7.65 | cgroup 10.5G/max oom_kill 0 | free scratch 289.0G/44953381i tmp 29.7G/1015732i workspace 289.0G/44953381i | repeat-01 collected 26/26 workers (60607 items) tests 37858 done 4 failed | 23 in flight, oldest 192s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
... [1652%]
........................................................................ [1655%]
........................................................................ [1658%]
........................................................................ [1661%]
........................................................................ [1664%]
........................................................................ [1668%]
................................[contention-diag] +3788s soak 33p/189t rss 11.3G pss 9.9G swap 3.2G majflt 176158 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.7G, 5 descendant rss 0.2G pss 0.1G | host avail 17.2G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 0.78/0.0 io 9.33 cpu 8.18 | cgroup 10.5G/max oom_kill 0 | free scratch 288.9G/44950413i tmp 29.7G/1015732i workspace 288.9G/44950413i | repeat-01 collected 26/26 workers (60607 items) tests 38238 done 4 failed | 22 in flight, oldest 208s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 7 hazardous kill call(s)
........................................ [1671%]
........................................................................ [1674%]
........................................................................ [1677%]
........................................................................ [1680%]
........................................................................ [1683%]
........................................................................ [1686%]
........................................................................ [1690%]
..........................[contention-diag] +3804s soak 40p/179t rss 11.4G pss 10.0G swap 3.2G majflt 176988 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.7G, 12 descendant rss 0.3G pss 0.2G | host avail 18.0G/62.7G swapfree 48.3G/64.0G oom_kill +0 | psi10 mem 0.6/0.36 io 9.98 cpu 8.42 | cgroup 10.7G/max oom_kill 0 | free scratch 288.9G/44947220i tmp 29.7G/1015732i workspace 288.9G/44947220i | repeat-01 collected 26/26 workers (60607 items) tests 38740 done 4 failed | 23 in flight, oldest 223s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............................................. [1693%]
........................................................................ [1696%]
........................................................................ [1699%]
........................................................................ [1702%]
.....................................[contention-diag] +3819s soak 32p/174t rss 11.3G pss 9.9G swap 3.2G majflt 177526 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.6G, 4 descendant rss 0.2G pss 0.1G | host avail 14.4G/62.7G swapfree 47.7G/64.0G oom_kill +0 | psi10 mem 1.61/0.99 io 13.54 cpu 8.37 | cgroup 10.3G/max oom_kill 0 | free scratch 288.9G/44942873i tmp 29.7G/1015732i workspace 288.9G/44942873i | repeat-01 collected 26/26 workers (60607 items) tests 39050 done 4 failed | 24 in flight, oldest 239s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................... [1705%]
........................................................................ [1708%]
........................................................................ [1712%]
........................................................................ [1715%]
........[contention-diag] +3835s soak 43p/181t rss 11.4G pss 9.9G swap 3.3G majflt 178262 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.6G, 15 descendant rss 0.3G pss 0.2G | host avail 15.1G/62.7G swapfree 47.0G/64.0G oom_kill +0 | psi10 mem 3.64/2.34 io 12.32 cpu 7.26 | cgroup 10.3G/max oom_kill 0 | free scratch 288.9G/44943594i tmp 29.7G/1015732i workspace 288.9G/44943594i | scratch used 0.0G in 6151 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 39278 done 4 failed | 24 in flight, oldest 255s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................................ [1718%]
........................................................................ [1721%]
........................................................................ [1724%]
........................................................................ [1727%]
.................[contention-diag] +3853s soak 32p/174t rss 11.3G pss 9.9G swap 3.3G majflt 179371 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.6G, 4 descendant rss 0.2G pss 0.1G | host avail 16.9G/62.7G swapfree 47.3G/64.0G oom_kill +0 | psi10 mem 0.64/0.38 io 18.53 cpu 7.38 | cgroup 10.3G/max oom_kill 0 | free scratch 288.9G/44949358i tmp 29.7G/1015724i workspace 288.9G/44949358i | repeat-01 collected 26/26 workers (60607 items) tests 39601 done 4 failed | 24 in flight, oldest 272s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....................................................... [1730%]
........................................................................ [1734%]
........................................................................ [1737%]
....[contention-diag] +3868s soak 36p/190t rss 11.3G pss 9.8G swap 3.2G majflt 180042 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.7G, 8 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.09 io 25.45 cpu 6.72 | cgroup 10.3G/max oom_kill 0 | free scratch 288.7G/44932737i tmp 29.7G/1015497i workspace 288.7G/44932736i | repeat-01 collected 26/26 workers (60607 items) tests 39814 done 4 failed | 22 in flight, oldest 288s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....................................[contention-diag] +3884s soak 35p/189t rss 11.4G pss 9.9G swap 3.2G majflt 188699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.0G pss 9.7G, 7 descendant rss 0.2G pss 0.1G | host avail 32.6G/62.7G swapfree 49.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 24.58 cpu 7.34 | cgroup 10.5G/max oom_kill 0 | free scratch 288.7G/44933132i tmp 29.7G/1015658i workspace 288.7G/44933132i | repeat-01 collected 26/26 workers (60607 items) tests 39842 done 4 failed | 24 in flight, oldest 303s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................ [1740%]
........................................................................ [1743%]
........................................................................ [1746%]
........................................................................ [1749%]
........................................................................ [1752%]
........................................................................ [1756%]
...............[contention-diag] +3899s soak 36p/181t rss 11.5G pss 10.0G swap 3.1G majflt 199691 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.0G pss 9.7G, 8 descendant rss 0.1G pss 0.1G | host avail 35.0G/62.7G swapfree 49.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 9.95 cpu 16.76 | cgroup 10.5G/max oom_kill 0 | free scratch 288.7G/44931187i tmp 29.7G/1015679i workspace 288.7G/44931187i | repeat-01 collected 26/26 workers (60607 items) tests 40248 done 4 failed | 24 in flight, oldest 319s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
......................................................... [1759%]
........................................................................ [1762%]
........................................................................ [1765%]
........................................................................ [1768%]
........................................[contention-diag] +3914s soak 36p/197t rss 11.5G pss 10.0G swap 3.1G majflt 200612 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.1G pss 9.7G, 8 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 49.2G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 7.87 cpu 20.14 | cgroup 10.6G/max oom_kill 0 | free scratch 288.7G/44929771i tmp 29.7G/1015679i workspace 288.7G/44929771i | repeat-01 collected 26/26 workers (60607 items) tests 40573 done 4 failed | 24 in flight, oldest 334s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................ [1771%]
........................................................................ [1774%]
........................................................................ [1778%]
........................................................................ [1781%]
..........................................................[contention-diag] +3930s soak 33p/192t rss 11.5G pss 10.0G swap 3.0G majflt 201647 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.1G pss 9.7G, 5 descendant rss 0.1G pss 0.0G | host avail 34.7G/62.7G swapfree 49.2G/64.0G oom_kill +0 | psi10 mem 1.19/0.02 io 6.51 cpu 22.16 | cgroup 10.7G/max oom_kill 0 | free scratch 288.7G/44928823i tmp 29.7G/1015692i workspace 288.7G/44928823i | repeat-01 collected 26/26 workers (60607 items) tests 40879 done 4 failed | 23 in flight, oldest 349s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............. [1784%]
........................................................................ [1787%]
.......s................................................................ [1790%]
........................................................................ [1793%]
....................................................[contention-diag] +3945s soak 43p/194t rss 11.6G pss 10.1G swap 3.0G majflt 202044 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.1G pss 9.7G, 15 descendant rss 0.2G pss 0.1G | host avail 34.9G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 0.55/0.0 io 3.3 cpu 16.6 | cgroup 10.8G/max oom_kill 0 | free scratch 288.6G/44927316i tmp 29.7G/1015707i workspace 288.6G/44927316i | repeat-01 collected 26/26 workers (60607 items) tests 41154 done 4 failed | 23 in flight, oldest 365s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.................... [1796%]
........................................................................ [1800%]
........................................................................ [1803%]
........................................................................ [1806%]
........................................................................ [1809%]
........................................................................ [1812%]
........................................................................ [1815%]
........................................................................ [1818%]
...[contention-diag] +3960s soak 39p/173t rss 11.6G pss 10.1G swap 3.0G majflt 202508 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.1G pss 9.7G, 11 descendant rss 0.2G pss 0.1G | host avail 34.2G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 0.13/0.0 io 3.69 cpu 18.56 | cgroup 10.7G/max oom_kill 0 | free scratch 288.6G/44927162i tmp 29.7G/1015707i workspace 288.6G/44927162i | scratch used 0.2G in 26336 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 41588 done 4 failed | 24 in flight, oldest 380s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.....................s............................................... [1821%]
........................................................................ [1825%]
........................................................................ [1828%]
........................................................................ [1831%]
........................................................................ [1834%]
........................................................................ [1837%]
........................................................[contention-diag] +3978s soak 35p/174t rss 11.5G pss 10.1G swap 3.0G majflt 203550 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.1G pss 9.8G, 7 descendant rss 0.1G pss 0.0G | host avail 33.2G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 5.85 cpu 19.72 | cgroup 10.8G/max oom_kill 0 | free scratch 288.6G/44925527i tmp 29.7G/1015707i workspace 288.6G/44925527i | repeat-01 collected 26/26 workers (60607 items) tests 42150 done 4 failed | 23 in flight, oldest 251s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................ [1840%]
........................................................................ [1843%]
........................................................................ [1847%]
........................................................................ [1850%]
........................................................................ [1853%]
........................................................................ [1856%]
........................................................................ [1859%]
...............................[contention-diag] +3993s soak 34p/182t rss 11.6G pss 10.1G swap 3.0G majflt 204645 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.2G pss 9.8G, 6 descendant rss 0.1G pss 0.1G | host avail 34.1G/62.7G swapfree 49.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.16 cpu 22.45 | cgroup 10.9G/max oom_kill 0 | free scratch 288.6G/44922651i tmp 29.7G/1015707i workspace 288.6G/44922651i | repeat-01 collected 26/26 workers (60607 items) tests 42648 done 4 failed | 23 in flight, oldest 266s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
......................................... [1862%]
........................................................................ [1865%]
........................................................................ [1869%]
........................................................................ [1872%]
........................................................................ [1875%]
.........................[contention-diag] +4008s soak 39p/191t rss 11.7G pss 10.3G swap 3.0G majflt 205756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.2G pss 9.8G, 11 descendant rss 0.2G pss 0.2G | host avail 33.3G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 5.04 cpu 21.25 | cgroup 11.0G/max oom_kill 0 | free scratch 292.5G/44934825i tmp 29.7G/1015707i workspace 292.5G/44934825i | repeat-01 collected 26/26 workers (60607 items) tests 42987 done 4 failed | 24 in flight, oldest 282s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
............................................... [1878%]
........................................................................ [1881%]
........................................................................ [1884%]
........................................................................ [1887%]
[contention-diag] +4024s soak 44p/211t rss 11.9G pss 10.4G swap 3.0G majflt 206202 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.2G pss 9.8G, 16 descendant rss 0.4G pss 0.3G | host avail 32.2G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 4.58 cpu 21.09 | cgroup 11.2G/max oom_kill 0 | free scratch 292.5G/44933565i tmp 29.7G/1015707i workspace 292.5G/44933565i | repeat-01 collected 26/26 workers (60607 items) tests 43262 done 4 failed | 24 in flight, oldest 297s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
........................................................................ [1891%]
........................................................................ [1894%]
........................................................................ [1897%]
...[contention-diag] +4039s soak 41p/196t rss 12.2G pss 10.6G swap 3.0G majflt 206786 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.2G pss 9.8G, 13 descendant rss 0.6G pss 0.5G | host avail 33.5G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.93 cpu 25.52 | cgroup 11.4G/max oom_kill 0 | free scratch 292.5G/44933121i tmp 29.7G/1015707i workspace 292.5G/44933121i | repeat-01 collected 26/26 workers (60607 items) tests 43477 done 4 failed | 24 in flight, oldest 307s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
..................................................................... [1900%]
........................................................................ [1903%]
.............................................................[contention-diag] +4055s soak 44p/197t rss 12.2G pss 10.6G swap 3.0G majflt 207326 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.2G pss 9.9G, 16 descendant rss 0.6G pss 0.5G | host avail 32.5G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.01 cpu 23.2 | cgroup 11.5G/max oom_kill 0 | free scratch 292.5G/44931720i tmp 29.7G/1015707i workspace 292.5G/44931720i | repeat-01 collected 26/26 workers (60607 items) tests 43687 done 4 failed | 23 in flight, oldest 322s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
........... [1906%]
........................................................................ [1909%]
........................................................................ [1913%]
.......[contention-diag] +4070s soak 37p/204t rss 12.2G pss 10.7G swap 3.0G majflt 208445 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.3G pss 9.9G, 9 descendant rss 0.6G pss 0.5G | host avail 35.7G/62.7G swapfree 49.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.19 cpu 23.6 | cgroup 11.5G/max oom_kill 0 | free scratch 292.5G/44931906i tmp 29.7G/1015707i workspace 292.5G/44931906i | repeat-01 collected 26/26 workers (60607 items) tests 43853 done 4 failed | 24 in flight, oldest 338s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
................................................................. [1916%]
........................................................................ [1919%]
........................................................................ [1922%]
........................................................................ [1925%]
..........................................................[contention-diag] +4085s soak 39p/192t rss 12.2G pss 10.7G swap 3.0G majflt 208723 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.3G pss 9.9G, 11 descendant rss 0.6G pss 0.5G | host avail 33.6G/62.7G swapfree 49.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.17 cpu 18.69 | cgroup 11.5G/max oom_kill 0 | free scratch 292.5G/44931272i tmp 29.7G/1015707i workspace 292.5G/44931273i | scratch used 0.2G in 36073 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 44138 done 4 failed | 23 in flight, oldest 353s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.............. [1928%]
........................................................................ [1931%]
........................................................................ [1935%]
........................................................................ [1938%]
....................................................[contention-diag] +4103s soak 38p/198t rss 12.1G pss 10.6G swap 2.9G majflt 209721 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.3G pss 9.9G, 10 descendant rss 0.5G pss 0.4G | host avail 32.8G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.56 cpu 12.03 | cgroup 11.5G/max oom_kill 0 | free scratch 292.3G/44928335i tmp 29.7G/1015707i workspace 292.3G/44928336i | repeat-01 collected 26/26 workers (60607 items) tests 44457 done 4 failed | 24 in flight, oldest 370s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................... [1941%]
........................................................................ [1944%]
........................................................................ [1947%]
........................................................................ [1950%]
........................................................................ [1953%]
........................................................................ [1957%]
...............................................[contention-diag] +4118s soak 35p/185t rss 12.1G pss 10.6G swap 2.9G majflt 210432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.3G pss 9.9G, 7 descendant rss 0.4G pss 0.3G | host avail 33.4G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.81 cpu 13.11 | cgroup 11.6G/max oom_kill 0 | free scratch 292.1G/44926701i tmp 29.7G/1015705i workspace 292.1G/44926701i | repeat-01 collected 26/26 workers (60607 items) tests 44901 done 4 failed | 24 in flight, oldest 386s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......................... [1960%]
........................................................................ [1963%]
........................................................................ [1966%]
........................................................................ [1969%]
..................[contention-diag] +4133s soak 45p/192t rss 12.3G pss 10.7G swap 2.9G majflt 210891 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.3G pss 9.9G, 17 descendant rss 0.6G pss 0.5G | host avail 32.1G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 1.37/1.37 io 6.36 cpu 13.38 | cgroup 11.8G/max oom_kill 0 | free scratch 292.0G/44925673i tmp 29.7G/1015707i workspace 292.0G/44925673i | repeat-01 collected 26/26 workers (60607 items) tests 45155 done 4 failed | 24 in flight, oldest 401s gw9 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
...................................................... [1972%]
........................................................................ [1975%]
........................................................................ [1979%]
.......................................[contention-diag] +4149s soak 51p/209t rss 12.4G pss 10.8G swap 2.9G majflt 211353 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 23 descendant rss 0.7G pss 0.6G | host avail 33.9G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.33/0.33 io 5.57 cpu 14.63 | cgroup 11.8G/max oom_kill 0 | free scratch 292.0G/44925813i tmp 29.7G/1015707i workspace 292.0G/44925813i | repeat-01 collected 26/26 workers (60607 items) tests 45379 done 4 failed | 23 in flight, oldest 151s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................. [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
........................................................................ [1991%]
........................................................................ [1994%]
........................................................................ [1997%]
...........................................[contention-diag] +4164s soak 39p/192t rss 12.5G pss 10.9G swap 2.9G majflt 211652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 11 descendant rss 0.8G pss 0.7G | host avail 30.6G/62.7G swapfree 50.7G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 5.54 cpu 14.54 | cgroup 11.9G/max oom_kill 0 | free scratch 291.9G/44924758i tmp 29.7G/1015707i workspace 291.9G/44924758i | repeat-01 collected 26/26 workers (60607 items) tests 45830 done 4 failed | 22 in flight, oldest 166s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................. [2001%]
........................................................................ [2004%]
........................................................................ [2007%]
........................................................................ [2010%]
........................................................................ [2013%]
........................................................................ [2016%]
.........................................[contention-diag] +4180s soak 40p/185t rss 12.4G pss 10.9G swap 2.9G majflt 212260 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 12 descendant rss 0.7G pss 0.6G | host avail 32.9G/62.7G swapfree 50.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.66 cpu 13.63 | cgroup 11.9G/max oom_kill 0 | free scratch 291.8G/44924164i tmp 29.7G/1015707i workspace 291.8G/44924164i | repeat-01 collected 26/26 workers (60607 items) tests 46261 done 4 failed | 21 in flight, oldest 181s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................... [2019%]
........................................................................ [2023%]
........................................................................ [2026%]
........................................................................ [2029%]
........................................................................ [2032%]
........................................................................ [2035%]
.........................................[contention-diag] +4195s soak 36p/189t rss 12.4G pss 10.9G swap 2.9G majflt 213233 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 8 descendant rss 0.6G pss 0.6G | host avail 33.8G/62.7G swapfree 50.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.16 cpu 14.46 | cgroup 11.9G/max oom_kill 0 | free scratch 291.8G/44923714i tmp 29.7G/1015706i workspace 291.8G/44923714i | repeat-01 collected 26/26 workers (60607 items) tests 46694 done 4 failed | 20 in flight, oldest 197s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................... [2038%]
........................................................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
........................................................................ [2054%]
........................................................................ [2057%]
...............[contention-diag] +4210s soak 40p/179t rss 12.6G pss 11.0G swap 2.9G majflt 213959 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 12 descendant rss 0.9G pss 0.8G | host avail 33.9G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.2 cpu 18.33 | cgroup 12.1G/max oom_kill 0 | free scratch 291.7G/44922446i tmp 29.7G/1015706i workspace 291.7G/44922446i | scratch used 0.3G in 49570 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 47124 done 4 failed | 21 in flight, oldest 212s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
......................................................... [2060%]
........................................................................ [2063%]
........................................................................ [2067%]
........................................................................ [2070%]
........................................................................ [2073%]
........................................................................ [2076%]
........................................................................ [2079%]
........................................................................ [2082%]
................[contention-diag] +4228s soak 39p/173t rss 12.6G pss 11.0G swap 2.9G majflt 214255 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 11 descendant rss 0.8G pss 0.7G | host avail 33.6G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.67 cpu 16.44 | cgroup 12.2G/max oom_kill 0 | free scratch 291.7G/44920830i tmp 29.7G/1015707i workspace 291.7G/44920830i | repeat-01 collected 26/26 workers (60607 items) tests 47745 done 4 failed | 20 in flight, oldest 229s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................ [2085%]
........................................................................ [2089%]
........................................................................ [2092%]
........................................................................ [2095%]
............................................................[contention-diag] +4243s soak 44p/188t rss 12.7G pss 11.1G swap 2.9G majflt 214576 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 16 descendant rss 0.9G pss 0.8G | host avail 34.0G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 1.89 cpu 23.02 | cgroup 12.3G/max oom_kill 0 | free scratch 291.7G/44919796i tmp 29.7G/1015707i workspace 291.7G/44919796i | repeat-01 collected 26/26 workers (60607 items) tests 48067 done 4 failed | 21 in flight, oldest 245s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............ [2098%]
........................................................................ [2101%]
........................................................................ [2104%]
........................................................................ [2107%]
........................................................................ [2110%]
..................[contention-diag] +4259s soak 44p/182t rss 12.6G pss 11.0G swap 2.9G majflt 215059 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.4G pss 10.0G, 16 descendant rss 0.8G pss 0.7G | host avail 33.5G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.29/0.0 io 0.77 cpu 23.39 | cgroup 12.1G/max oom_kill 0 | free scratch 291.7G/44919148i tmp 29.7G/1015707i workspace 291.7G/44919148i | repeat-01 collected 26/26 workers (60607 items) tests 48377 done 4 failed | 19 in flight, oldest 260s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................................... [2114%]
........................................................................ [2117%]
........................................................................ [2120%]
........................................................................ [2123%]
........................................................................ [2126%]
..[contention-diag] +4274s soak 43p/190t rss 12.7G pss 11.1G swap 2.8G majflt 215316 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.5G pss 10.0G, 15 descendant rss 0.9G pss 0.8G | host avail 32.8G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 0.45 cpu 21.31 | cgroup 12.3G/max oom_kill 0 | free scratch 291.7G/44918608i tmp 29.7G/1015707i workspace 291.7G/44918608i | repeat-01 collected 26/26 workers (60607 items) tests 48729 done 4 failed | 20 in flight, oldest 276s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................................................................... [2129%]
........................................................................ [2132%]
........................................................................ [2136%]
........................................................................ [2139%]
........................................................................ [2142%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
....................................................[contention-diag] +4290s soak 42p/185t rss 12.6G pss 11.1G swap 2.9G majflt 215482 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.5G pss 10.0G, 14 descendant rss 0.8G pss 0.7G | host avail 33.6G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.15/0.0 io 0.66 cpu 21.8 | cgroup 12.2G/max oom_kill 0 | free scratch 291.7G/44916760i tmp 29.7G/1015707i workspace 291.7G/44916760i | repeat-01 collected 26/26 workers (60607 items) tests 49359 done 4 failed | 20 in flight, oldest 291s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................... [2154%]
........................................................................ [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
........................................................................ [2167%]
........................................................................ [2170%]
........................................................................ [2173%]
........................................................................ [2176%]
........................................................................ [2180%]
......................................[contention-diag] +4305s soak 45p/200t rss 12.8G pss 11.2G swap 2.8G majflt 215784 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.5G pss 10.1G, 17 descendant rss 0.9G pss 0.8G | host avail 32.9G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 0.31 cpu 22.25 | cgroup 12.4G/max oom_kill 0 | free scratch 291.7G/44915573i tmp 29.7G/1015707i workspace 291.7G/44915572i | repeat-01 collected 26/26 workers (60607 items) tests 50000 done 4 failed | 18 in flight, oldest 307s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................. [2183%]
........................................................................ [2186%]
........................................................................ [2189%]
........................................................................ [2192%]
........................................................................ [2195%]
.............................s.......................................... [2198%]
........................................................................ [2202%]
.............................................................[contention-diag] +4320s soak 42p/193t rss 12.8G pss 11.2G swap 2.8G majflt 215893 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.5G pss 10.1G, 14 descendant rss 0.9G pss 0.8G | host avail 31.7G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.89 cpu 22.25 | cgroup 12.5G/max oom_kill 0 | free scratch 291.7G/44915120i tmp 29.7G/1015707i workspace 291.7G/44915120i | repeat-01 collected 26/26 workers (60607 items) tests 50509 done 4 failed | 15 in flight, oldest 322s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........... [2205%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2217%]
........................................................................ [2220%]
........................................................................ [2224%]
........................................................................ [2227%]
...........................................[contention-diag] +4336s soak 37p/181t rss 12.7G pss 11.1G swap 2.8G majflt 216282 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.5G pss 10.1G, 9 descendant rss 0.8G pss 0.7G | host avail 32.3G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 22.63 | cgroup 12.4G/max oom_kill 0 | free scratch 291.7G/44913984i tmp 29.7G/1015707i workspace 291.7G/44913984i | scratch used 0.4G in 76903 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 51053 done 4 failed | 18 in flight, oldest 338s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................. [2230%]
........................................................................ [2233%]
........................................................................ [2236%]
........................................................................ [2239%]
........................................................................ [2242%]
........................................................................ [2246%]
........................................................................ [2249%]
........................................................................ [2252%]
........................................................................ [2255%]
......[contention-diag] +4353s soak 38p/169t rss 12.7G pss 11.2G swap 2.8G majflt 217555 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.5G pss 10.1G, 10 descendant rss 0.8G pss 0.7G | host avail 31.4G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.67 cpu 20.05 | cgroup 12.5G/max oom_kill 0 | free scratch 291.3G/44911687i tmp 29.7G/1015707i workspace 291.3G/44911687i | repeat-01 collected 26/26 workers (60607 items) tests 51656 done 4 failed | 17 in flight, oldest 355s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
..............................s................................... [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
........................................................................ [2274%]
........................................................................ [2277%]
.........[contention-diag] +4369s soak 37p/179t rss 12.9G pss 11.4G swap 2.8G majflt 217907 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 9 descendant rss 1.0G pss 0.9G | host avail 30.2G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.69 cpu 13.51 | cgroup 12.7G/max oom_kill 0 | free scratch 290.9G/44907592i tmp 29.7G/1015707i workspace 290.9G/44907592i | repeat-01 collected 26/26 workers (60607 items) tests 52189 done 4 failed | 18 in flight, oldest 370s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................................................... [2280%]
........................................................................ [2283%]
........................................................................ [2286%]
........................................................................ [2290%]
........................................................................ [2293%]
........................................................................ [2296%]
........................................................................ [2299%]
....................................................[contention-diag] +4384s soak 40p/174t rss 13.1G pss 11.5G swap 2.9G majflt 218290 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 12 descendant rss 1.2G pss 1.1G | host avail 29.8G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 10.25 | cgroup 12.9G/max oom_kill 0 | free scratch 290.4G/44904821i tmp 29.7G/1015707i workspace 290.4G/44904821i | repeat-01 collected 26/26 workers (60607 items) tests 52747 done 4 failed | 17 in flight, oldest 386s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................... [2302%]
........................................................................ [2305%]
........................................................................ [2308%]
........................................................................ [2312%]
........................................................................ [2315%]
......[contention-diag] +4399s soak 36p/177t rss 13.0G pss 11.5G swap 2.8G majflt 218965 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 8 descendant rss 1.1G pss 1.0G | host avail 30.0G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 11.01 | cgroup 13.0G/max oom_kill 0 | free scratch 290.0G/44901418i tmp 29.7G/1015707i workspace 290.0G/44901418i | repeat-01 collected 26/26 workers (60607 items) tests 53066 done 4 failed | 18 in flight, oldest 401s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................................................. [2318%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2330%]
........................................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2340%]
........................................................................ [2343%]
.............[contention-diag] +4415s soak 37p/177t rss 12.9G pss 11.4G swap 2.7G majflt 219306 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 9 descendant rss 1.0G pss 0.9G | host avail 29.7G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 17.21 | cgroup 13.0G/max oom_kill 0 | free scratch 289.9G/44899501i tmp 29.7G/1015707i workspace 289.9G/44899501i | repeat-01 collected 26/26 workers (60607 items) tests 53721 done 4 failed | 18 in flight, oldest 417s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................................................... [2346%]
........................................................................ [2349%]
........................................................................ [2352%]
........................................................................ [2356%]
........................................................................ [2359%]
.[contention-diag] +4430s soak 41p/184t rss 13.0G pss 11.4G swap 2.7G majflt 219823 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 13 descendant rss 1.0G pss 0.9G | host avail 29.6G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.61 cpu 17.56 | cgroup 13.1G/max oom_kill 0 | free scratch 289.9G/44899095i tmp 29.7G/1015707i workspace 289.9G/44899095i | repeat-01 collected 26/26 workers (60607 items) tests 54065 done 4 failed | 16 in flight, oldest 432s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
....................................................................... [2362%]
........................................................................ [2365%]
........................................................................ [2368%]
........................................................................ [2371%]
....................................[contention-diag] +4446s soak 41p/178t rss 13.0G pss 11.4G swap 2.7G majflt 220014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 13 descendant rss 1.0G pss 0.9G | host avail 26.7G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 2.94 cpu 21.99 | cgroup 13.1G/max oom_kill 0 | free scratch 289.8G/44898277i tmp 29.7G/1015707i workspace 289.8G/44898277i | repeat-01 collected 26/26 workers (60607 items) tests 54362 done 4 failed | 16 in flight, oldest 447s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................... [2374%]
........................................................................ [2378%]
........................................................................ [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
........................................................................ [2390%]
........................................................................ [2393%]
........................................................................ [2396%]
........................................................................ [2400%]
.[contention-diag] +4461s soak 41p/181t rss 13.0G pss 11.4G swap 2.8G majflt 220364 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 13 descendant rss 1.0G pss 1.0G | host avail 24.4G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.68/0.35 io 6.07 cpu 17.13 | cgroup 13.1G/max oom_kill 0 | free scratch 289.6G/44897687i tmp 29.7G/1015707i workspace 289.6G/44897687i | scratch used 0.4G in 84350 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 54951 done 4 failed | 16 in flight, oldest 463s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
....................................................................... [2403%]
........................................................................ [2406%]
........................................................................ [2409%]
........................................................................ [2412%]
............................s........................................... [2415%]
..............................[contention-diag] +4479s soak 39p/170t rss 13.1G pss 11.5G swap 2.7G majflt 220795 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 11 descendant rss 1.1G pss 1.0G | host avail 23.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.39/0.2 io 5.73 cpu 10.92 | cgroup 13.2G/max oom_kill 0 | free scratch 289.0G/44895818i tmp 29.7G/1015707i workspace 289.0G/44895818i | repeat-01 collected 26/26 workers (60607 items) tests 55393 done 4 failed | 15 in flight, oldest 480s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......................................... [2418%]
........................................................................ [2421%]
...............................................s................[contention-diag] +4494s soak 38p/182t rss 13.1G pss 11.6G swap 2.7G majflt 221061 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 10 descendant rss 1.2G pss 1.1G | host avail 23.5G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.07/0.04 io 4.16 cpu 9.94 | cgroup 13.3G/max oom_kill 0 | free scratch 288.7G/44895212i tmp 29.7G/1015705i workspace 288.7G/44895212i | repeat-01 collected 26/26 workers (60607 items) tests 55569 done 4 failed | 14 in flight, oldest 496s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........ [2425%]
........................................................................ [2428%]
........................................................................ [2431%]
........................................................................ [2434%]
........................................................................ [2437%]
......................................................................[contention-diag] +4510s soak 38p/160t rss 13.0G pss 11.5G swap 2.7G majflt 221113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.1G, 10 descendant rss 1.0G pss 1.0G | host avail 23.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.2/0.19 io 2.02 cpu 8.65 | cgroup 13.2G/max oom_kill 0 | free scratch 297.1G/44979969i tmp 29.7G/1015705i workspace 297.1G/44979969i | repeat-01 collected 26/26 workers (60607 items) tests 55917 done 4 failed | 14 in flight, oldest 511s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.. [2440%]
........................................................................ [2443%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2453%]
........................................................................ [2456%]
........................................................................ [2459%]
.....[contention-diag] +4525s soak 37p/170t rss 13.2G pss 11.6G swap 2.7G majflt 221987 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.6G pss 10.2G, 9 descendant rss 1.2G pss 1.1G | host avail 22.4G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.67/0.6 io 2.83 cpu 10.68 | cgroup 13.1G/max oom_kill 0 | free scratch 295.7G/44978032i tmp 29.7G/1015706i workspace 295.7G/44978032i | repeat-01 collected 26/26 workers (60607 items) tests 56374 done 4 failed | 14 in flight, oldest 527s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................................................... [2462%]
........................................................................ [2465%]
........................................................................ [2469%]
.....................................................[contention-diag] +4540s soak 39p/179t rss 13.1G pss 11.6G swap 2.7G majflt 222578 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.7G pss 10.2G, 11 descendant rss 1.1G pss 1.0G | host avail 21.1G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 1.04/0.3 io 3.55 cpu 14.58 | cgroup 12.5G/max oom_kill 0 | free scratch 295.5G/44978038i tmp 29.7G/1015707i workspace 295.5G/44978038i | repeat-01 collected 26/26 workers (60607 items) tests 56639 done 4 failed | 13 in flight, oldest 542s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................... [2472%]
........................................................................ [2475%]
........................................................................ [2478%]
........................................................................ [2481%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2491%]
......................................[contention-diag] +4556s soak 34p/165t rss 13.0G pss 11.4G swap 2.7G majflt 223134 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.7G pss 10.2G, 6 descendant rss 0.9G pss 0.9G | host avail 24.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.31/0.12 io 2.73 cpu 17.84 | cgroup 12.4G/max oom_kill 0 | free scratch 295.4G/44978460i tmp 29.7G/1015707i workspace 295.4G/44978460i | repeat-01 collected 26/26 workers (60607 items) tests 57120 done 4 failed | 10 in flight, oldest 557s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................. [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2503%]
........................................................................ [2506%]
........................................................................ [2509%]
........................................................................ [2513%]
........................................................[contention-diag] +4571s soak 33p/162t rss 12.1G pss 10.6G swap 2.6G majflt 223403 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.7G pss 10.2G, 5 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.02 io 0.61 cpu 16.1 | cgroup 11.5G/max oom_kill 0 | free scratch 295.3G/44977875i tmp 29.7G/1015707i workspace 295.3G/44977875i | repeat-01 collected 26/26 workers (60607 items) tests 57646 done 4 failed | 9 in flight, oldest 73s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................ [2516%]
........................................................................ [2519%]
........................................................................ [2522%]
........................................................................ [2525%]
........................................................................ [2528%]
........................................................................ [2531%]
........................................................................ [2535%]
.......................[contention-diag] +4586s soak 35p/162t rss 12.1G pss 10.6G swap 2.6G majflt 223909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 7 descendant rss 0.0G pss 0.0G | host avail 26.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.28 cpu 16.59 | cgroup 11.6G/max oom_kill 0 | free scratch 295.2G/44974913i tmp 29.7G/1015707i workspace 295.2G/44974913i | scratch used 0.3G in 56697 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 58099 done 4 failed | 9 in flight, oldest 88s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................................................. [2538%]
........................................................................ [2541%]
........................................................................ [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
........................................................................ [2553%]
........................................................................ [2557%]
..................[contention-diag] +4604s soak 42p/175t rss 12.2G pss 10.6G swap 2.6G majflt 224180 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 14 descendant rss 0.1G pss 0.0G | host avail 25.5G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.75 cpu 21.8 | cgroup 11.7G/max oom_kill 0 | free scratch 295.1G/44974382i tmp 29.7G/1015707i workspace 295.1G/44974382i | repeat-01 collected 26/26 workers (60607 items) tests 58605 done 4 failed | 8 in flight, oldest 105s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
...................................................... [2560%]
........................................................................ [2563%]
........................................................................ [2566%]
........................................................................ [2569%]
........................................................................ [2572%]
........................................................................ [2575%]
........................................................................ [2579%]
.......................[contention-diag] +4619s soak 36p/164t rss 12.2G pss 10.6G swap 2.6G majflt 224630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 8 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 25.53 | cgroup 11.7G/max oom_kill 0 | free scratch 294.9G/44972833i tmp 29.7G/1015707i workspace 294.9G/44972833i | repeat-01 collected 26/26 workers (60607 items) tests 59133 done 4 failed | 8 in flight, oldest 8s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
................................................. [2582%]
........................................................................ [2585%]
........................................................................ [2588%]
........................................................................ [2591%]
.......................................ssss............................. [2594%]
...........................................................s............ [2597%]
.....................................................................[contention-diag] +4634s soak 35p/154t rss 12.3G pss 10.7G swap 2.7G majflt 225055 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 7 descendant rss 0.1G pss 0.1G | host avail 22.4G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 20.36 | cgroup 11.7G/max oom_kill 0 | free scratch 294.7G/44971853i tmp 29.7G/1015707i workspace 294.7G/44971853i | repeat-01 collected 26/26 workers (60607 items) tests 59606 done 4 failed | 7 in flight, oldest 24s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
... [2601%]
........................................................................ [2604%]
........................................................................ [2607%]
........................................................................ [2610%]
....................................................................[contention-diag] +4650s soak 35p/156t rss 12.4G pss 10.8G swap 2.7G majflt 225180 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 7 descendant rss 0.2G pss 0.2G | host avail 22.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 18.67 | cgroup 11.9G/max oom_kill 0 | free scratch 294.5G/44972692i tmp 29.7G/1015707i workspace 294.5G/44972692i | repeat-01 collected 26/26 workers (60607 items) tests 59900 done 4 failed | 5 in flight, oldest 39s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.... [2613%]
........................................................................ [2616%]
........................................................................ [2619%]
........................................................................ [2623%]
........................................................................ [2626%]
........................................................................ [2629%]
..........[contention-diag] +4665s soak 34p/153t rss 12.3G pss 10.8G swap 2.6G majflt 225287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 6 descendant rss 0.2G pss 0.2G | host avail 26.8G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 10.98 | cgroup 11.9G/max oom_kill 0 | free scratch 293.9G/44969403i tmp 29.7G/1015707i workspace 293.9G/44969403i | repeat-01 collected 26/26 workers (60607 items) tests 60242 done 4 failed | 4 in flight, oldest 55s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.............................................................. [2632%]
........................................................................ [2635%]
........................................................................ [2638%]
....[contention-diag] +4680s soak 33p/151t rss 12.1G pss 10.6G swap 2.6G majflt 225819 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.2G, 5 descendant rss 0.0G pss 0.0G | host avail 26.5G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.17 cpu 6.67 | cgroup 11.8G/max oom_kill 0 | free scratch 293.5G/44969730i tmp 29.7G/1015707i workspace 293.5G/44969730i | repeat-01 collected 26/26 workers (60607 items) tests 60465 done 4 failed | 2 in flight, oldest 2s gw9 tests/tool/test_detach_watchdog.py::test_watchdog_stops_unjoined_run_when_starter_dies | 10 hazardous kill call(s)
.................................................................... [2641%]
......................................[contention-diag] +4696s soak 35p/154t rss 12.2G pss 10.7G swap 2.6G majflt 225987 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.3G, 7 descendant rss 0.1G pss 0.1G | host avail 27.9G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 1.72 | cgroup 11.8G/max oom_kill 0 | free scratch 293.1G/44969313i tmp 29.7G/1015707i workspace 293.1G/44969313i | repeat-01 collected 26/26 workers (60607 items) tests 60586 done 4 failed | 1 in flight, oldest 2s gw9 tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors | 10 hazardous kill call(s)
.................                  [100%][contention-diag] +4711s soak 33p/137t rss 12.2G pss 10.6G swap 2.6G majflt 227776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 11.7G pss 10.3G, 5 descendant rss 0.0G pss 0.0G | host avail 26.0G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.62 cpu 5.96 | cgroup 11.8G/max oom_kill 0 | free scratch 290.6G/44959924i tmp 29.7G/1015707i workspace 290.6G/44959924i | scratch used 0.4G in 68774 entries (truncated) | repeat-01 collected 26/26 workers (60607 items) tests 60596 done 4 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
__________________ test_sigterm_during_barrier_exits_cleanly ___________________
[gw23] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw23/test_sigterm_during_barrier_ex0')

    @pytest.mark.skipif(os.name != "posix", reason="SIGTERM behavior is POSIX-specific")
    def test_sigterm_during_barrier_exits_cleanly(tmp_path: Path) -> None:
        state = tmp_path / "state"
        started = tmp_path / "started"
        scenario = tmp_path / "terminate.yml"
        scenario.write_text(
            f"steps:\n  - signal: {started}\n"
            f"  - wait_for: {{path: {tmp_path / 'never'}, timeout: 10}}\n"
        )
        process = subprocess.Popen(
            [sys.executable, "-m", "sase.fakey.cli", "-s", str(scenario)],
            stdin=subprocess.PIPE,
            stdout=subprocess.PIPE,
            stderr=subprocess.PIPE,
            text=True,
            env=_environment(state),
        )
        try:
            assert process.stdin is not None
            process.stdin.close()
            deadline = time.monotonic() + 2
            while not started.exists() and time.monotonic() < deadline:
                time.sleep(min(0.01, max(0.0, deadline - time.monotonic())))
>           assert started.exists()
E           AssertionError: assert False
E            +  where False = exists()
E            +    where exists = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw23/test_sigterm_during_barrier_ex0/started').exists

tests/fakey/test_cli.py:264: AssertionError
_______ test_blocked_refresh_worker_does_not_poison_a_later_config_read ________
[gw15] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

self = <Popen: returncode: -9 args: ('/tmp/sase-1rq-runtime-py312/bin/python', '-mp...>
timeout = 60

    def wait(self, timeout=None):
        """Wait for child process to terminate; returns self.returncode."""
        if timeout is not None:
            endtime = _time() + timeout
        try:
>           return self._wait(timeout=timeout)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:1264: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ('/tmp/sase-1rq-runtime-py312/bin/python', '-mp...>
timeout = 60

    def _wait(self, timeout):
        """Internal implementation of wait() on POSIX."""
        if self.returncode is not None:
            return self.returncode
    
        if timeout is not None:
            endtime = _time() + timeout
            # Enter a busy loop if we have a timeout.  This busy loop was
            # cribbed from Lib/threading.py in Thread.wait() at r71065.
            delay = 0.0005 # 500 us -> initial delay of 1 ms
            while True:
                if self._waitpid_lock.acquire(False):
                    try:
                        if self.returncode is not None:
                            break  # Another thread waited.
                        (pid, sts) = self._try_wait(os.WNOHANG)
                        assert pid == self.pid or pid == 0
                        if pid == self.pid:
                            self._handle_exitstatus(sts)
                            break
                    finally:
                        self._waitpid_lock.release()
                remaining = self._remaining_time(endtime)
                if remaining <= 0:
>                   raise TimeoutExpired(self.args, timeout)
E                   subprocess.TimeoutExpired: Command '('/tmp/sase-1rq-runtime-py312/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0/runpytest-0', '-p', 'no:randomly', '-c', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml', '--rootdir', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_poisoner_leaves_blocked_refresh_worker', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_victim_first_reads_use_only_successor_patched_paths')' timed out after 60 seconds

/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/subprocess.py:2045: TimeoutExpired

During handling of the above exception, another exception occurred:

pytester = <Pytester PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0')>

    def test_blocked_refresh_worker_does_not_poison_a_later_config_read(
        pytester: pytest.Pytester,
    ) -> None:
>       result = pytester.runpytest_subprocess(
            "-p",
            "no:randomly",
            "-c",
            str(_ROOT / "pyproject.toml"),
            "--rootdir",
            str(_ROOT),
            f"{_THIS_FILE}::test_poisoner_leaves_blocked_refresh_worker",
            f"{_THIS_FILE}::test_victim_first_reads_use_only_successor_patched_paths",
            timeout=60,
        )
E       _pytest.pytester.Pytester.TimeoutExpired: 60 second timeout expired running: ('/tmp/sase-1rq-runtime-py312/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0/runpytest-0', '-p', 'no:randomly', '-c', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml', '--rootdir', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_poisoner_leaves_blocked_refresh_worker', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_victim_first_reads_use_only_successor_patched_paths')

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py:112: TimeoutExpired
----------------------------- Captured stdout call -----------------------------
running: /tmp/sase-1rq-runtime-py312/bin/python -mpytest --basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0/runpytest-0 -p no:randomly -c /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml --rootdir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_poisoner_leaves_blocked_refresh_worker /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_config_cache_isolation.py::test_victim_first_reads_use_only_successor_patched_paths
     in: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw15/test_blocked_refresh_worker_does_not_poison_a_later_config_read0
_ test_uppercase_g_reaches_detail_bottom_from_real_input_path[#notification-list-shift+g-G] _
[gw17] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw17/test_uppercase_g_reaches_detai0')
key = 'shift+g', character = 'G', focus_selector = '#notification-list'

    @pytest.mark.parametrize(
        ("key", "character"),
        [
            ("G", "G"),
            ("shift+g", None),
            ("shift+g", "G"),
            ("g", "G"),
        ],
    )
    @pytest.mark.parametrize(
        "focus_selector", ["#notification-list", "#notification-file-scroll"]
    )
    async def test_uppercase_g_reaches_detail_bottom_from_real_input_path(
        tmp_path: Path,
        key: str,
        character: str | None,
        focus_selector: str,
    ) -> None:
        path = tmp_path / "long.txt"
        path.write_text("\n".join(f"line {i:03d}" for i in range(240)), encoding="utf-8")
        notification = _make_notification("n1")
        notification.files = [str(path)]
        dismissed: list[object | None] = []
    
        async with _StyledTestApp().run_test(size=(120, 40)) as pilot:
            modal = NotificationModal([notification])
            pilot.app.push_screen(modal, callback=dismissed.append)
            await pilot.pause()
            await pilot.pause()
    
            scroll = modal.query_one("#notification-file-scroll", VerticalScroll)
            await wait_for(pilot, lambda: scroll.max_scroll_y > 0)
    
            modal.query_one(focus_selector).focus()
            scroll.scroll_to(y=min(100, scroll.max_scroll_y - 1), animate=False)
            await pilot.pause()
            assert 0 < scroll.scroll_y < scroll.max_scroll_y
    
            bottom = MagicMock(wraps=modal.action_scroll_file_bottom)
            top = MagicMock(wraps=modal.action_scroll_file_top)
            modal.action_scroll_file_bottom = bottom  # type: ignore[method-assign]
            modal.action_scroll_file_top = top  # type: ignore[method-assign]
    
            pilot.app.post_message(events.Key(key, character))
            await pilot.pause()
    
>           assert scroll.scroll_y == scroll.max_scroll_y
E           AssertionError: assert 100 == 221
E            +  where 100 = VerticalScroll(id='notification-file-scroll').scroll_y
E            +  and   221 = VerticalScroll(id='notification-file-scroll').max_scroll_y

tests/test_notification_modal_scroll.py:69: AssertionError
______________ test_provider_drain_e2e_relaunches_stranded_agent _______________
[gw8] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw8/test_provider_drain_e2e_relaun0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f3099489af0>

    def test_provider_drain_e2e_relaunches_stranded_agent(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        harness = FakeyRetryHarness(tmp_path, monkeypatch, max_retries=1, wait_times=[0])
        _configure_reroute_environment(monkeypatch, harness)
        second_artifacts = _seed_second_agent(harness)
        # The best-effort usage-refresh limit-event trigger is orthogonal to
        # drain ownership (covered by test_usage_refresh.py); disable it so it
        # does not add an unrelated submit_proc_request call to this drill.
        monkeypatch.setattr(
            "sase.llm_provider.usage_limit_disable._trigger_usage_refresh_after_limit",
            lambda provider, outcome: None,
        )
    
        from sase.procs import submit_proc_request as real_submit_proc_request
    
        captured_requests: list[ProcSubmitRequest] = []
        captured_procs: list[Proc] = []
    
        def _capturing_submit(request: ProcSubmitRequest) -> Proc:
            captured_requests.append(request)
            proc = real_submit_proc_request(request)
            captured_procs.append(proc)
            return proc
    
        with patch(
            "sase.procs.submit_proc_request", side_effect=_capturing_submit
        ) as mock_submit:
            _run_trigger_to_disable(harness, monkeypatch)
    
        # Exactly one active hard disable for fakey, written by the trigger's
        # own real usage-limit failure.
        disables = get_active_provider_disables()
        assert set(disables) == {"fakey"}
        assert disables["fakey"].source == "usage_limit"
        assert disables["fakey"].is_hard
    
        # Exactly one agent.drain proc submitted, with the exact argv and
        # concurrency key the automatic path promises.
        mock_submit.assert_called_once()
        request = captured_requests[0]
        assert request.argv == [
            "sase",
            "agent",
            "drain",
            "fakey",
            "--yes",
            "--json",
            "--limit",
            "20",
        ]
        assert request.operation == AGENT_DRAIN
        assert request.concurrency_keys == ["provider-drain:fakey"]
        assert request.operation_payload is not None
        assert request.operation_payload["notify"] is True
        assert request.operation_payload["trigger_artifacts_dir"] == str(harness.artifacts)
    
        proc = captured_procs[0]
        finished = wait_for_proc(proc.proc_id, timeout=_DRAIN_WAIT_TIMEOUT)
    
        result = _read_drain_result(proc.proc_id)
        payload = result.payload
        assert payload is not None, f"drain reported no payload: {result.error}"
        assert payload["provider"] == "fakey"
        moves = payload["moves"]
        assert len(moves) == 1
        moved = moves[0]
        assert moved["name"] == _SECOND_AGENT_NAME
        # This is the one classification decision this drill exists to prove:
        # once fakey is hard-disabled, plan_launch_units routes the second
        # agent's reroute-alias prompt onto codex instead of reporting it
        # stranded. That part of the production path works correctly.
        assert moved["route"]["kind"] == "reroute"
        assert moved["route"]["target_provider"] == "codex"
    
        # The second agent's original row is gone: it was really stopped
        # (dismissed) and its artifacts wiped as part of the real restart.
        assert not second_artifacts.exists()
    
        assert finished.status == "success"
        assert result.success is True
        assert payload["counts"] == {
            "moves": 1,
            "relaunched": 1,
            "failed": 0,
            "skipped": 0,
        }
        replacement = payload["results"][0]
        assert replacement["status"] == "ok"
        launched = replacement["launched"]
        assert launched is not None
        assert isinstance(launched["pid"], int)
        assert launched["pid"] > 0
        assert launched["artifacts_dir"] != str(second_artifacts)
        replacement_artifacts = Path(launched["artifacts_dir"])
        replacement_meta_path = replacement_artifacts / "agent_meta.json"
        replacement_meta = _wait_for_json(
            replacement_meta_path,
            lambda payload: (
                payload.get("name") == _SECOND_AGENT_NAME
                and payload.get("llm_provider") == "codex"
            ),
        )
        assert replacement_meta["name"] == _SECOND_AGENT_NAME
        assert replacement_meta["llm_provider"] == "codex"
        # The child may later fail because this hermetic drill forces actual
        # execution back through the disabled fakey binary; that must not turn the
        # already-completed drain relaunch into a failed drain move.
        replacement_done_path = replacement_artifacts / "done.json"
>       replacement_done = _wait_for_json(
            replacement_done_path,
            lambda payload: (
                "LLM provider 'fakey' is temporarily disabled"
                in str(payload.get("error") or "")
            ),
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/fakey/test_provider_drain_e2e.py:323: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw8/test_provider_drain_e2e_relaun0/sase-home/projects/home/artifacts/ace-run/202611/08/20261108093400/done.json')
predicate = <function test_provider_drain_e2e_relaunches_stranded_agent.<locals>.<lambda> at 0x7f309b486f20>

    def _wait_for_json(
        path: Path,
        predicate: Callable[[dict[str, Any]], bool],
        *,
        timeout: float = 30.0,
    ) -> dict[str, Any]:
        deadline = time.monotonic() + timeout
        last_error: Exception | None = None
        while time.monotonic() < deadline:
            if path.is_file():
                try:
                    payload = json.loads(path.read_text(encoding="utf-8"))
                except (OSError, json.JSONDecodeError) as exc:
                    last_error = exc
                else:
                    if isinstance(payload, dict) and predicate(payload):
                        return payload
            time.sleep(0.01)  # sase-test-wait: poll for the child-written JSON
        suffix = f": {last_error}" if last_error is not None else ""
>       raise AssertionError(f"timed out waiting for matching JSON in {path}{suffix}")
E       AssertionError: timed out waiting for matching JSON in /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw8/test_provider_drain_e2e_relaun0/sase-home/projects/home/artifacts/ace-run/202611/08/20261108093400/done.json

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/fakey/test_provider_drain_e2e.py:77: AssertionError
----------------------------- Captured stdout call -----------------------------
╭────── 🤖 Workflow-Tmp_261108_093318-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

✅ Waiting for Fakey completed in 00:01╭─────── 🤖 Workflow-Tmp_261108_093318-Main [Big]_Error Agent - Prompt ────────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_261108_093318-Main [Big]_Error Agent - Response ───────╮
│                                                                              │
│  Error running LLM provider command (exit code 1)                            │
│  stderr: FAKEY-RETRYABLE: FAKEY-USAGE-LIMIT hit                              │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
----------------------------- Captured stderr call -----------------------------
FAKEY-RETRYABLE: FAKEY-USAGE-LIMIT hit
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

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_prewarm_waits_for_idle_ui
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/main.py:726: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    remove_mods = pm._conftest_plugins.difference(my_conftestmodules)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_pane_review.py::test_review_chip_sums_across_scopes
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:478: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    _safe_super(NonCallableMock, self).__init__(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/dom.py:1735: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    return self._classes.issuperset(class_names)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_chip_that_exists_only_via_authored_link
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/strip.py:111: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    self._offsets_cache: FIFOCache[tuple[int, int], Strip] = FIFOCache(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/typing.py:2187: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def cast(typ, val):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/json/decoder.py:354: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object _record_history_async.<locals>._record at 0x7fcd701f7e20>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/test_agent_display_group_fold_repaint.py::test_expand_repaints_and_restores_rows
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    payload = binding(
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

tests/ace/tui/test_commits_pane_grouping.py::test_collapsing_a_repo_group_hides_its_commit
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object AgentMetadataPagerMixin._open_agent_metadata_pager at 0x7f56589bb0f0>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=1523319) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1522814) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=1522479) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
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

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1522554) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:888: DeprecationWarning: This process (pid=1522479) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1523482) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
568.78s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
446.98s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
446.58s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
407.54s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
405.54s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
386.19s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
348.07s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
323.61s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
308.31s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
282.24s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
279.62s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
272.00s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
269.60s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
205.06s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
174.71s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
173.98s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
171.92s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
168.08s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
158.73s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
158.61s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
=========================== short test summary info ============================
FAILED tests/fakey/test_cli.py::test_sigterm_during_barrier_exits_cleanly - A...
FAILED tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
FAILED tests/test_notification_modal_scroll.py::test_uppercase_g_reaches_detail_bottom_from_real_input_path[#notification-list-shift+g-G]
FAILED tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent
==== 4 failed, 60583 passed, 21 skipped, 111 warnings in 4715.66s (1:18:35) ====
[contention-diag] +4723s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 480 | 1 parent rss 0.0G pss 0.0G | host avail 36.1G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.99 cpu 3.71 | cgroup 1.2G/max oom_kill 0 | free scratch 290.6G/44959944i tmp 29.7G/1015707i workspace 290.6G/44959944i | repeat-01 collected 26/26 workers (60607 items) tests 60607 done 4 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4723s, 306 samples, 0 signal(s); peaks: cgroup_current 13.3G, min_free_scratch 288.6G, min_free_tmp 29.7G, min_free_workspace 288.6G, min_inodes_scratch 44895212, min_inodes_tmp 1015227, min_inodes_workspace 44895212, min_mem_available 9.7G, min_swap_free 45.5G, oom_kill_delta 0, pressure_memory_full 12.6, pswpin_delta 2052796, pswpout_delta 4511632, scratch_bytes 0.4G, soak_procs 51, soak_pss 11.6G, soak_rss 13.2G, soak_swap 3.3G, soak_threads 302

contention tally: 4 node(s) failed across 1 repeat(s) in 4723.3s; red repeats: 1
  1/1  tests/fakey/test_cli.py::test_sigterm_during_barrier_exits_cleanly  (repeats 1)
  1/1  tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent  (repeats 1)
  1/1  tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read  (repeats 1)
  1/1  tests/test_notification_modal_scroll.py::test_uppercase_g_reaches_detail_bottom_from_real_input_path[#notification-list-shift+g-G]  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
failed  exit=1  duration=4724556ms

